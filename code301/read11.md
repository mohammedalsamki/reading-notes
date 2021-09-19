# <BrowserRouter>
A <Router> that uses the HTML5 history API (pushState, replaceState and the popstate event) to keep your UI in sync with the URL.<BrowserRouter
  basename={optionalString}
  forceRefresh={optionalBool}
  getUserConfirmation={optionalFunc}
  keyLength={optionalNumber}
>
  <App />
</BrowserRouter>
basename: string
The base URL for all locations. If your app is served from a sub-directory on your server, you’ll want to set this to the sub-directory. A properly formatted basename should have a leading slash, but no trailing slash.<BrowserRouter basename="/calendar">
    <Link to="/today"/> // renders <a href="/calendar/today">
    <Link to="/tomorrow"/> // renders <a href="/calendar/tomorrow">
    ...
</BrowserRouter>
getUserConfirmation: func
A function to use to confirm navigation. Defaults to using window.confirm.<BrowserRouter
  getUserConfirmation={(message, callback) => {
    // this is the default behavior
    const allowTransition = window.confirm(message);
    callback(allowTransition);
  }}
/>
forceRefresh: bool
If true the router will use full page refreshes on page navigation. You may want to use this to imitate the way a traditional server-rendered app would work with full page refreshes between page navigation.<BrowserRouter forceRefresh={true} />
keyLength: number
The length of location.key. Defaults to 6.<BrowserRouter keyLength={12} />
children: node
The child elements to render.Note: On React < 16 you must use a single child element since a render method cannot return more than one element. If you need more than one element, you might try wrapping them in an extra <div>.
<HashRouter>
A <Router> that uses the hash portion of the URL (i.e. window.location.hash) to keep your UI in sync with the URL.IMPORTANT NOTE: Hash history does not support location.key or location.state. In previous versions we attempted to shim the behavior but there were edge-cases we couldn’t solve. Any code or plugin that needs this behavior won’t work. As this technique is only intended to support legacy browsers, we encourage you to configure your server to work with <BrowserHistory> instead.<HashRouter
  basename={optionalString}
  getUserConfirmation={optionalFunc}
  hashType={optionalString}
>
  <App />
</HashRouter>
basename: string
The base URL for all locations. A properly formatted basename should have a leading slash, but no trailing slash.<HashRouter basename="/calendar"/>
<Link to="/today"/> // renders <a href="#/calendar/today">
getUserConfirmation: func
A function to use to confirm navigation. Defaults to using window.confirm.<HashRouter
  getUserConfirmation={(message, callback) => {
    // this is the default behavior
    const allowTransition = window.confirm(message);
    callback(allowTransition);
  }}
/>
hashType: string
The type of encoding to use for window.location.hash. Available values are:
"slash" - Creates hashes like #/ and #/sunshine/lollipops
"noslash" - Creates hashes like # and #sunshine/lollipops
"hashbang" - Creates “ajax crawlable” (deprecated by Google) hashes like #!/ and #!/sunshine/lollipops
Defaults to "slash".
children: node
A single child element to render.
<Link>
Provides declarative, accessible navigation around your application.<Link to="/about">About</Link>
to: string
A string representation of the Link location, created by concatenating the location’s pathname, search, and hash properties.<Link to="/courses?sort=name" />
to: object
An object that can have any of the following properties:
pathname: A string representing the path to link to.
search: A string representation of query parameters.
hash: A hash to put in the URL, e.g. #a-hash.
state: State to persist to the location.
<Link
  to={{
    pathname: "/courses",
    search: "?sort=name",
    hash: "#the-hash",
    state: { fromDashboard: true }
  }}
/>
to: function
A function to which current location is passed as an argument and which should return location representation as a string or as an object<Link to={location => ({ ...location, pathname: "/courses" })} />
<Link to={location => `${location.pathname}?sort=name`} />
replace: bool
When true, clicking the link will replace the current entry in the history stack instead of adding a new one.<Link to="/courses" replace />
innerRef: function
As of React Router 5.1, if you are using React 16 you should not need this prop because we forward the ref to the underlying <a>. Use a normal ref instead.Allows access to the underlying ref of the component.<Link
  to="/"
  innerRef={node => {
    // `node` refers to the mounted DOM element
    // or null when unmounted
  }}
/>
innerRef: RefObject
As of React Router 5.1, if you are using React 16 you should not need this prop because we forward the ref to the underlying <a>. Use a normal ref instead.Get the underlying ref of the component using React.createRef.let anchorRef = React.createRef()

<Link to="/" innerRef={anchorRef} />
component: React.Component
If you would like utilize your own navigation component, you can simply do so by passing it through the component prop.const FancyLink = React.forwardRef((props, ref) => (
  <a ref={ref} {...props}>💅 {props.children}</a>
))

<Link to="/" component={FancyLink} />
others
You can also pass props you’d like to be on the <a> such as a title, id, className, etc.
