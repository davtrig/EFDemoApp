# EFDemoApp
Template app of the best practices for Entity Framework, and what to be careful about

Considerations to have:
- Always check the migrations to be sure they are efficient, for example, 
  don't use nvarchar(max) instead of varchar(200) or lower, if it's not necessary, you can do this with [MaxLength] tags above the entity and/or [Column(TypeName = "varchar(10)].
- Check if [Required] tags make sense.
- When writing LINQ queries, don't use Includes unless stricly necessary, and know the implicaitons of using said Include, and its costs
- Make sure you don't call c# methods in a db query, until after you download the data. 
  Note that if you use c# methods after the query, it will download all the data, and only then filter it.
  So, if possible, filter before you download the data.
- Check the weight of the db operations in SSMS, and what can be done to improve the performance
