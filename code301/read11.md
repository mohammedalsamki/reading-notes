Model()
Parameters
doc «Object» values for initial set
optional «[fields]» object containing the fields that were selected in the query which returned this document. You do not need to set this parameter to ensure Mongoose handles your query projection.
[skipId=false] «Boolean» optional boolean. If true, mongoose doesn't add an _id field to the document.
A Model is a class that's your primary tool for interacting with MongoDB. An instance of a Model is called a Document.

In Mongoose, the term "Model" refers to subclasses of the mongoose.Model class. You should not use the mongoose.Model class directly. The mongoose.model() and connection.model() functions create subclasses of mongoose.Model as shown below.

Example:
// `UserModel` is a "Model", a subclass of `mongoose.Model`.
const UserModel = mongoose.model('User', new Schema({ name: String }));

// You can use a Model to create new documents using `new`:
const userDoc = new UserModel({ name: 'Foo' });
await userDoc.save();

// You also use a model to create queries:
const userFromDb = await UserModel.findOne({ name: 'Foo' });
Model.aggregate()
Parameters
[pipeline] «Array» aggregation pipeline as an array of objects
[options] «Object» aggregation options
[callback] «Function»
Returns:
«Aggregate»
Performs aggregations on the models collection.

If a callback is passed, the aggregate is executed and a Promise is returned. If a callback is not passed, the aggregate itself is returned.

This function triggers the following middleware.

aggregate()
Example:
// Find the max balance of all accounts
const res = await Users.aggregate([
  { $group: { _id: null, maxBalance: { $max: '$balance' }}},
  { $project: { _id: 0, maxBalance: 1 }}
]);

console.log(res); // [ { maxBalance: 98000 } ]

// Or use the aggregation pipeline builder.
const res = await Users.aggregate().
  group({ _id: null, maxBalance: { $max: '$balance' } }).
  project('-id maxBalance').
  exec();
console.log(res); // [ { maxBalance: 98 } ]
NOTE:
Mongoose does not cast aggregation pipelines to the model's schema because $project and $group operators allow redefining the "shape" of the documents at any stage of the pipeline, which may leave documents in an incompatible format. You can use the mongoose-cast-aggregation plugin to enable minimal casting for aggregation pipelines.
The documents returned are plain javascript objects, not mongoose documents (since any shape of document can be returned).
More About Aggregations:
Mongoose Aggregate
An Introduction to Mongoose Aggregate
MongoDB Aggregation docs
Model.buildBulkWriteOperations()
Parameters
options «Object»
options.skipValidation «Boolean» defaults to false, when set to true, building the write operations will bypass validating the documents.
@param {[Document]} documents The array of documents to build write operations of

Model.bulkSave()
Parameters
documents «[Document]»
takes an array of documents, gets the changes and inserts/updates documents in the database according to whether or not the document is new, or whether it has changes or not.

bulkSave uses bulkWrite under the hood, so it's mostly useful when dealing with many documents (10K+)

Model.bulkWrite()
Parameters
ops «Array»
[ops.insertOne.document] «Object» The document to insert
[opts.updateOne.filter] «Object» Update the first document that matches this filter
[opts.updateOne.update] «Object» An object containing update operators
[opts.updateOne.upsert=false] «Boolean» If true, insert a doc if none match
[opts.updateOne.timestamps=true] «Boolean» If false, do not apply timestamps to the operation
[opts.updateOne.collation] «Object» The MongoDB collation to use
[opts.updateOne.arrayFilters] «Array» The array filters used in update
[opts.updateMany.filter] «Object» Update all the documents that match this filter
[opts.updateMany.update] «Object» An object containing update operators
[opts.updateMany.upsert=false] «Boolean» If true, insert a doc if no documents match filter
[opts.updateMany.timestamps=true] «Boolean» If false, do not apply timestamps to the operation
[opts.updateMany.collation] «Object» The MongoDB collation to use
[opts.updateMany.arrayFilters] «Array» The array filters used in update
[opts.deleteOne.filter] «Object» Delete the first document that matches this filter
[opts.deleteMany.filter] «Object» Delete all documents that match this filter
[opts.replaceOne.filter] «Object» Replace the first document that matches this filter
[opts.replaceOne.replacement] «Object» The replacement document
[opts.replaceOne.upsert=false] «Boolean» If true, insert a doc if no documents match filter
[options] «Object»
[options.ordered=true] «Boolean» If true, execute writes in order and stop at the first error. If false, execute writes in parallel and continue until all writes have either succeeded or errored.
[options.session=null] «ClientSession» The session associated with this bulk write. See transactions docs.
[options.w=1] «String|number» The write concern. See Query#w() for more information.
[options.wtimeout=null] «number» The write concern timeout.
[options.j=true] «Boolean» If false, disable journal acknowledgement
[options.bypassDocumentValidation=false] «Boolean» If true, disable MongoDB server-side schema validation for all writes in this bulk.
[options.strict=null] «Boolean» Overwrites the strict option on schema. If false, allows filtering and writing fields not defined in the schema for all writes in this bulk.
[callback] «Function» callback function(error, bulkWriteOpResult) {}
Returns:
«Promise» resolves to a BulkWriteOpResult if the operation succeeds
Sends multiple insertOne, updateOne, updateMany, replaceOne, deleteOne, and/or deleteMany operations to the MongoDB server in one command. This is faster than sending multiple independent operations (e.g. if you use create()) because with bulkWrite() there is only one round trip to MongoDB.

Mongoose will perform casting on all operations you provide.

This function does not trigger any middleware, neither save(), nor update(). If you need to trigger save() middleware for every document use create() instead.

Example:
Character.bulkWrite([
  {
    insertOne: {
      document: {
        name: 'Eddard Stark',
        title: 'Warden of the North'
      }
    }
  },
  {
    updateOne: {
      filter: { name: 'Eddard Stark' },
      // If you were using the MongoDB driver directly, you'd need to do
      // `update: { $set: { title: ... } }` but mongoose adds $set for
      // you.
      update: { title: 'Hand of the King' }
    }
  },
  {
    deleteOne: {
      {
        filter: { name: 'Eddard Stark' }
      }
    }
  }
]).then(res => {
 // Prints "1 1 1"
 console.log(res.insertedCount, res.modifiedCount, res.deletedCount);
});
The supported operations are:

insertOne
updateOne
updateMany
deleteOne
deleteMany
replaceOne
