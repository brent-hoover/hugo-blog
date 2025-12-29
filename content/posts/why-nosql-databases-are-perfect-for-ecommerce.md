+++
date = 2024-06-21T01:14:29Z
description = ""
draft = false
slug = "why-nosql-databases-are-perfect-for-ecommerce"
title = "Why NoSQL Databases are Perfect for Ecommerce"

+++


People get very passionate about database technologies. There’s nothing more critical than your data, after all. Make the wrong choice, and you could be setting yourself up for failure.

When it comes to managing data, every database management system (DBMS) has its strengths and weaknesses, and each one is good at some things and not so good at others. So why did we use MongoDB to power Reaction over a more ‘traditional’ MySQL database? I feel like our reasoning grew out of a single core concept: Mongo’s document structure works the same way that ecommerce works.

You might be asking, “So what does this mean, exactly?” In this piece, I’ll explain just that.


Solving the Impedance Mismatch Problem

The impedance mismatch problem refers to the inherent challenges of mapping objects to a table within the context of a relational database management system (RDBMS). This is why millions of hours-and dollars-are spent on object relational mappers (ORMs), which allow you to work around the natural mismatched state of RDMS systems.

What does this mismatch look like? I’ll demonstrate in a couple instances of pseudo-code from each type of system. Here is what getting an order would look like in a typical RDBMS/SQL system:

SELECT * FROM ORDERS o INNER JOIN ORDER_DETAILS od ON o.ID = od.ID INNER JOIN PAYMENTS p ON p.ORDER_ID = o.ID INNER JOIN SHIPMENTS s ON s.ORDER_ID = o.ID INNER JOIN ACCOUNTS a on o.ACCOUNT_ID = a.ID WHERE o.ID = '1234'

This is not a particularly complex layout, but you can already see where things get complicated. You’ll need to understand the layouts of each of these tables (and even know they exist) and be able to carefully stitch together all this data into one cohesive document. Here, each JOIN adds another lookup to another table, adding time and overhead to each request.

Contrast this with finding an order in Mongo, the database that powers Reaction.

db.getCollection('Orders').findOne({ _id: "RNo7qFZjedma4MqsQ" });

There’s more to Mongo than just making the code simpler and easier to read. The order in which you fetch out of the database is structured around the way it’s conceived in your mind. It represents the order in whatever state it’s in, with all its history and detail. Hence, there’s no “mismatch” between how you deal with data in the application, and how it’s stored in the database.


Performance Advantages

Besides this conceptual advantage, there are two real-world advantages that NoSQL brings us: 1) speed and 2) scalability.

Speed

Fetching a complete record by a single key (which is how queries are done most of the time) is much, much faster than trying to fetch data from multiple tables. Other systems, such as EAV architecture, have gone to great lengths to get the sort of flexibility you have with Mongo, but at the expense of performance. No joins results in lightning-fast lookups and fetches.

Scalability

Because records in Mongo are stored in one discreet entry, it becomes much less difficult to shard databases across however many servers. This simplifies the act of horizontal scaling. With RDBM systems, you have all these discreet tables that need to be kept together, and although sharding with RDBM systems is possible and commonly done, it’s much more complex and usually only allows sharding of certain parts of the database.

Other Features

In addition to the advantages listed above, Mongo has many great built-in features, such as:

 * Map/reduce, for working over extremely large datasets
 * Text search, which we use to power our product search)
 * Geo-lookups
 * … and so much more!

And best of all, these features all come straight out of the box.


But Is It Reliable?

Most objections about NoSQL usually have to do with the perception that NoSQL databases in general, and Mongo in particular, have problems with reliability, and thus such databases are not suited for ecommerce systems, which thrive on financial transactions. Early adopters of NoSQL had concerns with data security, duplication and atomicity issues, but those issues have been addressed in current versions of MongoDB. In addition, using the Wired Tiger storage engine, which Reaction Commerce uses by default, provides an extra layer of data reliability.

Although database systems can fail from time to time-all high-availability architectures need to take this into account-when it comes to reliability, Mongo has some distinct advantages around the ease of clustering. Let’s get more into that.

Redundancy is one of the primary tenants of high availability, and clustering is one of the most common ways to introduce it with databases. It allows your application to see a group of redundant servers-usually in a primary/secondary configuration, where one server is essentially a “hot copy” of the primary server-as one server. No changes to your application or configuration are required, and if there’s a failure with the primary server, the secondary server jumps in and takes over. All of this is transparent to the client.

If you’ve ever set up a DB cluster using MySQL or Postgres, then you know that setting things up correctly is no small feat. It involves adding several fairly obscure config files and hoping that you’ve selected the correct mode and settings. Clustering in Mongo only requires setting up the servers and issuing some commands on one of them. You can get more specific in your configuration, but most typical primary/secondary configurations only involve specifying which servers are performing which roles. Then, syncing starts immediately.


What About ACID Compliance?

ACID (Atomicity, Consistency, Isolation, Durability) is a concept that was originally designed around RDBM systems, so some of these criteria don’t make sense in a document database. For example, atomicity, consistency, and isolation really only apply to the concept of writing an order that is written entirely to all its component tables ( ORDER_DETAIL, ORDER_HEADER, ORDER_HISTORY). However, in a document database, that's the default behavior, since all the data for a particular order is stored within the single order document. The idea of trying to ensure that CASCADEs and TRIGGER s all work correctly does not apply, and the idea of keeping partial updates invisible to other threads doesn't apply, because all updates are applied in one transaction. In addition, Mongo provides atomicity/transactions to this extent:

In MongoDB, a write operation is atomic on the level of a single document, even if the operation modifies multiple embedded documents within a single document.

So as long as all your updates are applied in a single write operation, Mongo provides “all or nothing” atomicity. Reaction has ensured that we don’t use JOINs or other cross-collection technique to ensure that transactions are both fast and safe.


…and Data Integrity?

Another common concern about NoSQL databases is that there is no “schema” or set of data integrity rules that prevents an errant programmer from writing out information to the data store incorrectly. Schemas catch bugs that could damage data integrity before they can ever reach real data.

This is a legitimate concern, one which Reaction addresses by using the “ simple-schema” package (which, despite its name, is quite sophisticated). This package is now a standard part of Meteor, but we were early adopters. The simple-schema package allows program authors to define a schema in code and attach it to a Mongo collection at a global level. As a result, all data that is inserted or updated must conform to the schema without any additional effort by other developers. Again, this type of schema avoids the “mismatch” of trying to get tables of data to match with data sets that are naturally nested. It also makes working with the API fluent and intuitive.


Summary

While RDBM systems have served us well for many years, a new era of ecommerce requires new tools and techniques. We believe that Mongo provides the speed, scalability, and flexibility necessary to meet the challenges of a hyper-competitive marketplace.

To access and manage your database, we recommend downloading a simple GUI, like Robo 3T.