
Why we need EntityFramework?
===
* Entity framework can release developer from remember the structure of databases.
* Developer can stay on Oject Oriented progarming and if you are familar with Linq, you will benefit from EF.

## What is Entities?
* Entities is a trongly typed class, the full name is <span style="color:green">Entity Data Model</span>, which is mapping to a physical database
* For example, we have a car entity class, we wanna add one record to database named AutoLot. We need a autolotEntities(this is object context) to add a car object to this context and save the changes.
* what happened is a connection to db is opened, then ef transfer that code to sql statements and then update db.

## EF API
* EF API is built on DOTNET infrastructure. we need to use the data provider in the infrastructure, then we can call ef api.
* The microsoft sql server data provider is already there in system.data.entity.dll, there is two key namespaces in this assembly
   
    *<span style = "color:green">Object Services</span>*
    * object services is the part that manage entities (client-side). which means all the class inheritance EntityObject base class.
    
    *<span style = "color:green">Entity Client</span>*
    * ob
    *
   ### Tracking queries vs No-Tracking queries
   * the entity instance is default set to tracking queries, which means, if we make some changes to the entity instance, the ef core will keep tracking those changes , if we call savechanges() , those change will be update in physical database.
   * No-tracking queries is useful when we want to retrieve some data readonly, ef will not tracking the changes we made.
   * its easy to swap from tracking to no-tracking, we can set at context instance level.
   <span style = "color:green">context.ChangeTracker.QueryTrackingBehavior = QueryTrackingBehavior.NoTracking; </span>