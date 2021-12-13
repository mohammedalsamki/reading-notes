# class 32

## <ins>*DRF Permissions*

premissions as defined by apple 
> Authentication or identification by itself is not usually sufficient to gain access to information or code. For that, the entity requesting access must have authorization..
 

 Permissions in REST framework are always defined as a list of permission classes.

 When the permissions checks fail either a "403 Forbidden" or a "401 Unauthorized" response will be returned, according to the following rules:

- The request was successfully authenticated, but permission was denied. — An HTTP 403 Forbidden response will be returned.
- The request was not successfully authenticated, and the highest priority authentication class does not use WWW-Authenticate headers. — An HTTP 403 Forbidden response will be returned.
- The request was not successfully authenticated, and the highest priority authentication class does use WWW-Authenticate headers. — An HTTP 401 Unauthorized response, with an appropriate WWW-Authenticate header will be returned.
 
### <ins> Object level permissions

> Object level permissions are used to determine if a user should be allowed to act on a particular object
 
Object level permissions are run by REST framework's generic views when `.get_object()`
 
 ### Setting the permission policy
` DEFAULT_PERMISSION_CLASSES `

```py 
REST_FRAMEWORK = {
    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.IsAuthenticated',
    ]
}
```

#### API Reference

## AllowAny

allow unrestricted access, **regardless of if the request was authenticated or unauthenticated**.

## IsAuthenticated

deny permission to any unauthenticated user, and allow permission otherwise.

## IsAdminUser

deny permission to any user, unless `user.is_staff` is `True` in which case permission will be allowed.

## IsAuthenticatedOrReadOnly
allow authenticated users to perform any request. Requests for unauthorised users will only be permitted if the request method is one of the "safe" methods; `GET`, `HEAD` or `OPTIONS`.


