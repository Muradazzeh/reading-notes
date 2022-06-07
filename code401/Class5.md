##  Class 04 sequelize-normalization
* Sequelize supports the standard associations: One-To-One, One-To-Many and Many-To-Many.

* To do this, Sequelize provides four types of associations that should be combined to create them:

    * The HasOne association
    * The BelongsTo association
    * The HasMany association
    * The BelongsToMany association
## Defining the Sequelize associations
```
const A = sequelize.define('A', /* ... */);
const B = sequelize.define('B', /* ... */);

A.hasOne(B); // A HasOne B
A.belongsTo(B); // A BelongsTo B
A.hasMany(B); // A HasMany B
A.belongsToMany(B, { through: 'C' }); // A BelongsToMany B through the junction table C
```
* The A.hasOne(B) association means that a One-To-One relationship exists between A and B, with the foreign key being defined in the target model (B).

 * The A.belongsTo(B) association means that a One-To-One relationship exists between A and B, with the foreign key being defined in the source model (A).

* The A.hasMany(B) association means that a One-To-Many relationship exists between A and B, with the foreign key being defined in the target model (B).

### One-To-One relationships
* We want to establish a One-To-One relationship between Foo and Bar. We know that in a relational database, this will be done by establishing a foreign key in one of the tables 
* Implementation
The main setup to achieve the goal is as follows:
````
Table1.hasOne(Table2);
Table2.belongsTo(Table1);
````
* Since no option was passed, Sequelize will infer what to do from the names of the models. In this case, Sequelize knows that a Table1 Id column must be added to Table2.

* Customizing the foreign key
``` 
// Option 1
Foo.hasOne(Bar, {
  foreignKey: 'myFooId'
});
Bar.belongsTo(Foo);

// Option 2
Foo.hasOne(Bar, {
  foreignKey: {
    name: 'myFooId'
  }
});
Bar.belongsTo(Foo);

// Option 3
Foo.hasOne(Bar);
Bar.belongsTo(Foo, {
  foreignKey: 'myFooId'
});

// Option 4
Foo.hasOne(Bar);
Bar.belongsTo(Foo, {
  foreignKey: {
    name: 'myFooId'
  }
});
````
## One-To-Many relationships
* One-To-Many associations are connecting one source with multiple targets, while all these targets are connected only with this single source

* Implementation
The main way to do this is as follows:
````
Team.hasMany(Player);
Player.belongsTo(Team);
````
## Many-To-Many relationships
* Many-To-Many associations connect one source with multiple targets, while all these targets can in turn be connected to other sources beyond the first.
````
const Movie = sequelize.define('Movie', { name: DataTypes.STRING });
const Actor = sequelize.define('Actor', { name: DataTypes.STRING });
Movie.belongsToMany(Actor, { through: 'ActorMovies' });
Actor.belongsToMany(Movie, { through: 'ActorMovies' });
````
## Fetching associations - Eager Loading vs Lazy Loading

* The concepts of Eager Loading and Lazy Loading are fundamental to understand how fetching associations work in Sequelize. Lazy Loading refers to the technique of fetching the associated data only when you really want it; Eager Loading, on the other hand, refers to the technique of fetching everything at once, since the beginning, with a larger query

## Association Aliases & Custom Foreign Keys
* There are three ways to specify a different name for the foreign key:

By providing the foreign key name directly
By defining an Alias
By doing both things

## Special methods/mixins added to instances 
* When an association is defined between two models, the instances of those models gain special methods to interact with their associated counterparts.

For example, if we have two models, Foo and Bar, and they are associated, their instances will have the following methods/mixins available, depending on the association type:

Foo.hasOne(Bar)

