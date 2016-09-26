# SQLite-Net.Extensions.Readers
Extension readers for praeclarum/sqlite-net project.

This extension let to query the database without binding to a specific class.
The results are Dictionnary of <string, object>. Each key contains ColumnName, Value contains data.

To use the Query, you can call the method ExecuteReader on SQLiteConnection object.
This method is available into the namespace SQLite_Net.Extensions.Readers.

## Example

	void ExecuteCustomQuery(SQLiteConnection connection)
	{
		var tableName = "<SetTableName>";
		// Execute reader :
		var readerResults = connection.ExecuteReader("SELECT * FROM " + tableName);
		Console.WriteLine("Read data from table " + tableName);
		// Showing results :
		foreach (var readerItem in readerItems)
			Console.WriteLine(string.Join(";", readerItem.Fields.Select(e => e + ":" + readerItem[e])));
			
		Console.WriteLine("End read data");
	}
