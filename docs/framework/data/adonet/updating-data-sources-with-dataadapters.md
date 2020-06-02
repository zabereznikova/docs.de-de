---
title: Aktualisieren von Datenquellen mit "DataAdapters"
description: Erfahren Sie, wie die Update-Methode von DataAdapter Änderungen von einem DataSet zurück in die Datenquelle in ADO.NET-Anwendungen auflöst.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d1bd9a8c-0e29-40e3-bda8-d89176b72fb1
ms.openlocfilehash: e2348a3a89aa1c28856bfc21aaa25f2c8327aac7
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286183"
---
# <a name="updating-data-sources-with-dataadapters"></a>Aktualisieren von Datenquellen mit "DataAdapters"

Zum Aktualisieren von Datenquellen mit den Änderungen, die an einem `Update` vorgenommen wurden, wird die <xref:System.Data.Common.DataAdapter>-Methode des <xref:System.Data.DataSet> aufgerufen. Als Argumente akzeptiert die `Update`-Methode, genau wie die `Fill`-Methode, eine Instanz eines `DataSet` sowie ein optionales <xref:System.Data.DataTable>-Objekt oder einen `DataTable`-Namen. Die `DataSet`-Instanz ist das `DataSet`, das die vorgenommenen Änderungen enthält, und der `DataTable`-Wert gibt die Tabelle an, aus der die Änderungen abgerufen werden sollen. Wenn keine `DataTable` angegeben ist, wird die erste `DataTable` im `DataSet` verwendet.

Wenn die `Update`-Methode aufgerufen wird, analysiert der `DataAdapter` die vorgenommenen Änderungen und führt dann den entsprechenden Befehl (INSERT, UPDATE oder DELETE) aus. Wenn der `DataAdapter` eine Änderung an einer <xref:System.Data.DataRow> feststellt, verwendet er zum Verarbeiten der Änderung den <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A>, den <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> oder den <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A>. Dies gibt Ihnen die Gelegenheit, die Leistung der ADO.NET-Anwendung zu optimieren, indem Sie in der Entwurfsphase eine Befehlssyntax festlegen und, sofern möglich, gespeicherte Prozeduren verwenden. Sie müssen die Befehle vor dem Aufrufen von `Update` explizit festlegen. Wenn `Update` aufgerufen wird und der entsprechende Befehl für ein bestimmtes Update nicht vorhanden ist (wenn z. B. `DeleteCommand` für gelöschte Zeilen fehlt), wird eine Ausnahme ausgelöst.

> [!NOTE]
> Wenn Sie zum Bearbeiten oder Löschen von Daten mit einem `DataAdapter` gespeicherte SQL Server-Prozeduren verwenden, müssen Sie sicherstellen, dass in der Definition der gespeicherten Prozedur nicht SET NOCOUNT ON verwendet wird. Anderenfalls ist die zurückgegebene Anzahl der betroffenen Zeilen gleich Null (0), was der `DataAdapter` als Parallelitätskonflikt interpretiert. In diesem Fall wird eine <xref:System.Data.DBConcurrencyException> ausgelöst.

Command-Parameter können verwendet werden, um Ein- und Ausgabewerte für eine SQL-Anweisung oder eine gespeicherte Prozedur für jede geänderte Zeile in einem `DataSet` anzugeben. Weitere Informationen finden Sie unter [DataAdapter-Parameter](dataadapter-parameters.md).

> [!NOTE]
> Wichtig ist dabei, zwischen dem Löschen einer Zeile in einer <xref:System.Data.DataTable> und dem Entfernen der Zeile zu unterscheiden. Wenn Sie die `Remove`-Methode oder die `RemoveAt`-Methode aufrufen, wird die Zeile sofort entfernt. Wenn Sie anschließend die `DataTable` oder das `DataSet` an einen `DataAdapter` übergeben und `Update` aufrufen, bleiben die entsprechenden Zeilen in der Datenquelle unangetastet. Wenn Sie die Methode `Delete` verwenden, bleibt die Zeile in der `DataTable` erhalten, wird aber als zu löschen markiert. Das anschließende Übergeben der `DataTable` oder des `DataSet` an einen `DataAdapter` und das Aufrufen von `Update` führt dazu, dass die entsprechende Zeile in der Datenquelle gelöscht wird.

Wenn Ihre `DataTable` einer einzelnen Datenbanktabelle zugeordnet ist oder aus einer einzelnen Datenbanktabelle generiert wurde, können Sie mithilfe des <xref:System.Data.Common.DbCommandBuilder>-Objekts automatisch das `DeleteCommand`-, das `InsertCommand`- und das `UpdateCommand`-Objekt für den `DataAdapter` generieren. Weitere Informationen finden Sie unter [Erstellen von Befehlen mit CommandBuilder](generating-commands-with-commandbuilders.md).

## <a name="using-updatedrowsource-to-map-values-to-a-dataset"></a>Verwenden von "UpdatedRowSource" zum Zuordnen von Werten zu einem "DataSet"

Mit der -Eigenschaft eines -Objekts können Sie steuern, wie die von der Datenquelle zurückgegebenen Werte nach einem Aufruf der Update-Methode eines  der  erneut zugeordnet werden. Durch Festlegen eines der `UpdatedRowSource`-Enumerationswerte für die <xref:System.Data.UpdateRowSource>-Eigenschaft kann gesteuert werden, ob die von den `DataAdapter`-Befehlen zurückgegebenen Ausgabeparameter ignoriert oder auf die geänderte Zeile im `DataSet` angewendet werden. Es kann auch festgelegt werden, ob die erste zurückgegebene Zeile (wenn vorhanden) auf die geänderte Zeile in der `DataTable` angewendet wird.

In der folgenden Tabelle werden die verschiedenen Werte der `UpdateRowSource`-Enumeration und deren Auswirkungen auf das Verhalten eines mit einem `DataAdapter` verwendeten Befehls beschrieben.

|"UpdatedRowSource"-Enumeration|BESCHREIBUNG|
|----------------------------------|-----------------|
|<xref:System.Data.UpdateRowSource.Both>|Sowohl die Ausgabeparameter als auch die erste Zeile eines zurückgegebenen Resultset können der geänderten Zeile im `DataSet` zugeordnet werden.|
|<xref:System.Data.UpdateRowSource.FirstReturnedRecord>|Nur die Daten in der ersten Zeile eines zurückgegebenen Resultset können der geänderten Zeile im `DataSet` zugeordnet werden.|
|<xref:System.Data.UpdateRowSource.None>|Alle Ausgabeparameter oder Zeilen eines zurückgegebenen Resultset werden ignoriert.|
|<xref:System.Data.UpdateRowSource.OutputParameters>|Der geänderten Zeile im `DataSet` können nur Ausgabeparameter zugeordnet werden.|

Die `Update`-Methode aktualisiert die Datenquelle mit den vorgenommenen Änderungen. Die Daten in der Datenquelle können aber seit dem letzten Füllen des `DataSet` durch andere Clients geändert worden sein. Wenn Sie das `DataSet` mit den aktuellen Daten aktualisieren möchten, verwenden Sie den `DataAdapter` und die `Fill`-Methode. Der Tabelle werden neue Zeilen hinzugefügt, und aktualisierte Informationen werden in die vorhandenen Zeilen eingefügt. Die `Fill`-Methode überprüft die Primärschlüsselwerte der Zeilen im `DataSet` und der vom `SelectCommand` zurückgegebenen Zeilen und bestimmt so, ob eine neue Zeile hinzugefügt oder die bestehende Zeile aktualisiert werden soll. Wenn die `Fill`-Methode einen Primärschlüsselwert für eine Zeile im `DataSet` findet, der mit einem Primärschlüsselwert einer Zeile in den vom `SelectCommand` zurückgegebenen Ergebnissen übereinstimmt, aktualisiert sie die vorhandene Zeile mit den Informationen aus der vom `SelectCommand` zurückgegebenen Zeile und legt den <xref:System.Data.DataRow.RowState%2A> der vorhandenen Zeile auf `Unchanged` fest. Wenn der Primärschlüsselwert einer vom `SelectCommand` zurückgegebenen Zeile keinem der Primärschlüsselwerte der Zeilen im `DataSet` entspricht, fügt die `Fill`-Methode eine neue Zeile mit dem `RowState``Unchanged` hinzu.

> [!NOTE]
> Wenn der `SelectCommand` die Ergebnisse eines OUTER JOIN zurückgibt, legt der `DataAdapter` keinen `PrimaryKey`-Wert für die resultierende `DataTable` fest. Sie müssen den `PrimaryKey` selbst definieren, um sicherzustellen, dass doppelte Zeilen ordnungsgemäß aufgelöst werden. Weitere Informationen finden Sie unter [Definieren von primär Schlüsseln](./dataset-datatable-dataview/defining-primary-keys.md).

Um Ausnahmen zu behandeln, die beim Aufrufen der-Methode auftreten können `Update` , können Sie das-Ereignis verwenden, `RowUpdated` um auf Fehler beim Aktualisieren von Zeilen zu reagieren (siehe [Handling DataAdapter-Ereignisse](handling-dataadapter-events.md)), oder Sie können auf festlegen, `DataAdapter.ContinueUpdateOnError` bevor Sie `true` aufrufen `Update` , und auf die in der-Eigenschaft einer bestimmten Zeile gespeicherten Fehlerinformationen reagieren, `RowError` Wenn das Update fertig ist (siehe [Zeilen Fehlerinformationen](./dataset-datatable-dataview/row-error-information.md)).

> [!NOTE]
> `AcceptChanges` `DataSet` Wenn Sie für, oder aufrufen, werden `DataTable` `DataRow` alle `Original` Werte für ein `DataRow` mit den `Current` Werten für die überschrieben `DataRow` . Wenn die Feldwerte, mit denen die Zeile als eindeutig identifiziert wird, geändert wurden, stimmen die `AcceptChanges`-Werte nicht mehr mit den Werten in der Datenquelle überein, nachdem `Original` aufgerufen wurde. `AcceptChanges` wird während eines Aufrufs der Update-Methode eines `DataAdapter` automatisch für jede Zeile aufgerufen. Sie können die Originalwerte während eines Aufrufs der Update-Methode beibehalten, indem Sie zuerst die -Eigenschaft des  auf false setzen oder indem Sie einen Ereignishandler für das -Ereignis erstellen und den  auf  festlegen. Weitere Informationen finden Sie unter Zusammenführen von [DataSet-Inhalten](./dataset-datatable-dataview/merging-dataset-contents.md) und [Verarbeiten von DataAdapter-Ereignissen](handling-dataadapter-events.md).

## <a name="example"></a>Beispiel

In den folgenden Beispielen wird veranschaulicht, wie Updates für geänderte Zeilen durch explizites Festlegen des `UpdateCommand` von `DataAdapter` und durch Aufrufen der-Methode durchgeführt werden `Update` . Beachten Sie, dass der in der WHERE-Klausel der UPDATE-Anweisung festgelegte Parameterwert angibt, dass der `Original`-Wert der `SourceColumn` verwendet wird. Dies ist wichtig, weil der `Current`-Wert möglicherweise geändert wurde und u. U. nicht mehr mit dem Wert in der Datenquelle übereinstimmt. Beim `Original`-Wert handelt es sich um den Wert, mit dem die `DataTable` aus der Datenquelle aufgefüllt wurde.

[!code-csharp[DataWorks SqlClient.DataAdapterUpdate#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.DataAdapterUpdate/CS/source.cs#1)]
[!code-vb[DataWorks SqlClient.DataAdapterUpdate#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.DataAdapterUpdate/VB/source.vb#1)]

## <a name="autoincrement-columns"></a>"AutoIncrement"-Spalten

Wenn die Tabellen aus der Datenquelle automatisch inkrementierende Spalten besitzen, können Sie die Spalten im `DataSet` füllen. Geben Sie dazu die automatisch inkrementierenden Werte als Ausgabeparameter einer gespeicherten Prozedur zurück, und ordnen Sie diesen Parameter einer Spalte in einer Tabelle zu, indem Sie den automatisch inkrementierenden Wert in der ersten Zeile eines von einer gespeicherten Prozedur oder einer SQL-Anweisung zurückgegebenen Resultset zurückgeben oder indem Sie das `RowUpdated`-Ereignis des `DataAdapter` verwenden, um eine weitere SELECT-Anweisung auszuführen. Weitere Informationen und ein Beispiel finden Sie unter [Abrufen von Identitäts-oder](retrieving-identity-or-autonumber-values.md)Auto Sequenz Werten.

## <a name="ordering-of-inserts-updates-and-deletes"></a>Reihenfolge von Einfüge-, Update- und Löschvorgängen

In vielen Fällen ist die Reihenfolge, in der die am `DataSet` vorgenommenen Änderungen zur Datenquelle gesendet werden, sehr wichtig. Wenn beispielsweise ein Primärschlüsselwert für eine vorhandene Zeile aktualisiert und eine neue Zeile mit dem neuen Primärschlüsselwert als Fremdschlüssel hinzugefügt wurde, muss das Update vor der Einfügung verarbeitet werden.

Mithilfe der `Select`-Methode der `DataTable` können Sie ein `DataRow`-Array zurückgeben, das nur auf Zeilen mit einem bestimmten `RowState` verweist. Anschließend können Sie das zurückgegebene `DataRow`-Array an die `Update`-Methode des `DataAdapter` übergeben, damit die geänderten Zeilen verarbeitet werden. Wenn Sie eine Teilmenge von Zeilen angeben, die aktualisiert werden sollen, können Sie die Reihenfolge steuern, in der Einfügungen, Updates und Löschvorgänge verarbeitet werden.

## <a name="example"></a>Beispiel

Durch den folgenden Code wird beispielsweise sichergestellt, dass die gelöschten Zeilen der Tabelle zuerst verarbeitet werden, anschließend die aktualisierten Zeilen und dann die eingefügten Zeilen.

```vb
Dim table As DataTable = dataSet.Tables("Customers")

' First process deletes.
dataSet.Update(table.Select(Nothing, Nothing, _
  DataViewRowState.Deleted))

' Next process updates.
adapter.Update(table.Select(Nothing, Nothing, _
  DataViewRowState.ModifiedCurrent))

' Finally, process inserts.
adapter.Update(table.Select(Nothing, Nothing, _
  DataViewRowState.Added))
```

```csharp
DataTable table = dataSet.Tables["Customers"];

// First process deletes.
adapter.Update(table.Select(null, null, DataViewRowState.Deleted));

// Next process updates.
adapter.Update(table.Select(null, null,
  DataViewRowState.ModifiedCurrent));

// Finally, process inserts.
adapter.Update(table.Select(null, null, DataViewRowState.Added));
```

## <a name="use-a-dataadapter-to-retrieve-and-update-data"></a>Verwenden von "DataAdapter" zum Abrufen und Aktualisieren von Daten

Sie können DataAdapter verwenden, um die Daten abzurufen und zu aktualisieren.

- Im Beispiel wird DataAdapter.AcceptChangesDuringFill verwendet, um die Daten in der Datenbank zu klonen. Wenn die Eigenschaft auf False festgelegt ist, wird AcceptChanges beim Auffüllen der Datenbank nicht aufgerufen, und die neu hinzugefügten Zeilen werden als eingefügte Zeilen behandelt. Daher werden im Beispiel diese Zeilen zum Einfügen der neuen Zeilen in die Datenbank verwendet.

- In den Beispielen wird DataAdapter.TableMappings verwendet, um die Zuordnung zwischen der Quelltabelle und der DataTable zu definieren.

- Im Beispiel wird DataAdapter.FillLoadOption verwendet, um zu bestimmen, wie die DataTable aus DbDataReader vom Adapter aufgefüllt wird. Beim Erstellen einer DataTable können die Daten aus der Datenbank nur in die aktuelle oder ursprüngliche Version geschrieben werden, wenn die Eigenschaft auf LoadOption.Upsert oder LoadOption.PreserveChanges festgelegt wird.

- Im Beispiel wird die Tabelle auch mithilfe von DbDataAdapter.UpdateBatchSize zum Ausführen von Batchvorgängen aktualisiert.

Bevor Sie dieses Beispiel kompilieren und ausführen, müssen Sie die Beispieldatenbank erstellen:

```sql
USE [master]
GO

CREATE DATABASE [MySchool]

GO

USE [MySchool]
GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Course]([CourseID] [nvarchar](10) NOT NULL,
[Year] [smallint] NOT NULL,
[Title] [nvarchar](100) NOT NULL,
[Credits] [int] NOT NULL,
[DepartmentID] [int] NOT NULL,
 CONSTRAINT [PK_Course] PRIMARY KEY CLUSTERED
(
[CourseID] ASC,
[Year] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]

GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Department]([DepartmentID] [int] IDENTITY(1,1) NOT NULL,
[Name] [nvarchar](50) NOT NULL,
[Budget] [money] NOT NULL,
[StartDate] [datetime] NOT NULL,
[Administrator] [int] NULL,
 CONSTRAINT [PK_Department] PRIMARY KEY CLUSTERED
(
[DepartmentID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]

GO

INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C1045', 2012, N'Calculus', 4, 7)
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C1061', 2012, N'Physics', 4, 1)
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C2021', 2012, N'Composition', 3, 2)
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C2042', 2012, N'Literature', 4, 2)

SET IDENTITY_INSERT [dbo].[Department] ON

INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (1, N'Engineering', 350000.0000, CAST(0x0000999C00000000 AS DateTime), 2)
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (2, N'English', 120000.0000, CAST(0x0000999C00000000 AS DateTime), 6)
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (4, N'Economics', 200000.0000, CAST(0x0000999C00000000 AS DateTime), 4)
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (7, N'Mathematics', 250024.0000, CAST(0x0000999C00000000 AS DateTime), 3)
SET IDENTITY_INSERT [dbo].[Department] OFF

ALTER TABLE [dbo].[Course]  WITH CHECK ADD  CONSTRAINT [FK_Course_Department] FOREIGN KEY([DepartmentID])
REFERENCES [dbo].[Department] ([DepartmentID])
GO
ALTER TABLE [dbo].[Course] CHECK CONSTRAINT [FK_Course_Department]
GO
```

C#-und Visual Basic Projekte mit diesem Codebeispiel finden Sie unter [Codebeispiele für Entwickler](https://code.msdn.microsoft.com/site/search?f%5B0%5D.Type=SearchText&f%5B0%5D.Value=How%20to%20use%20DataAdapter%20to%20retrieve%20and%20update%20data&f%5B1%5D).

```csharp
using System;
using System.Data;
using System.Data.Common;
using System.Data.SqlClient;
using System.Linq;
using CSDataAdapterOperations.Properties;

namespace CSDataAdapterOperations.Properties {
   internal sealed partial class Settings : global::System.Configuration.ApplicationSettingsBase {

      private static Settings defaultInstance = ((Settings)(global::System.Configuration.ApplicationSettingsBase.Synchronized(new Settings())));

      public static Settings Default {
         get {
            return defaultInstance;
         }
      }

      [global::System.Configuration.ApplicationScopedSettingAttribute()]
      [global::System.Configuration.DefaultSettingValueAttribute("Data Source=(local);Initial Catalog=MySchool;Integrated Security=True")]
      public string MySchoolConnectionString {
         get {
            return ((string)(this["MySchoolConnectionString"]));
         }
      }
   }
}

class Program {
   static void Main(string[] args) {
      Settings settings = new Settings();

      // Copy the data from the database.  Get the table Department and Course from the database.
      String selectString = @"SELECT [DepartmentID],[Name],[Budget],[StartDate],[Administrator]
                                     FROM [MySchool].[dbo].[Department];

                                   SELECT [CourseID],@Year as [Year],Max([Title]) as [Title],
                                   Max([Credits]) as [Credits],Max([DepartmentID]) as [DepartmentID]
                                   FROM [MySchool].[dbo].[Course]
                                   Group by [CourseID]";

      DataSet mySchool = new DataSet();

      SqlCommand selectCommand = new SqlCommand(selectString);
      SqlParameter parameter = selectCommand.Parameters.Add("@Year", SqlDbType.SmallInt, 2);
      parameter.Value = new Random(DateTime.Now.Millisecond).Next(9999);

      // Use DataTableMapping to map the source tables and the destination tables.
      DataTableMapping[] tableMappings = {new DataTableMapping("Table", "Department"), new DataTableMapping("Table1", "Course")};
      CopyData(mySchool, settings.MySchoolConnectionString, selectCommand, tableMappings);

      Console.WriteLine("The following tables are from the database.");
      foreach (DataTable table in mySchool.Tables) {
         Console.WriteLine(table.TableName);
         ShowDataTable(table);
      }

      // Roll back the changes
      DataTable department = mySchool.Tables["Department"];
      DataTable course = mySchool.Tables["Course"];

      department.Rows[0]["Name"] = "New" + department.Rows[0][1];
      course.Rows[0]["Title"] = "New" + course.Rows[0]["Title"];
      course.Rows[0]["Credits"] = 10;

      Console.WriteLine("After we changed the tables:");
      foreach (DataTable table in mySchool.Tables) {
         Console.WriteLine(table.TableName);
         ShowDataTable(table);
      }

      department.RejectChanges();
      Console.WriteLine("After use the RejectChanges method in Department table to roll back the changes:");
      ShowDataTable(department);

      DataColumn[] primaryColumns = { course.Columns["CourseID"] };
      DataColumn[] resetColumns = { course.Columns["Title"] };
      ResetCourse(course, settings.MySchoolConnectionString, primaryColumns, resetColumns);
      Console.WriteLine("After use the ResetCourse method in Course table to roll back the changes:");
      ShowDataTable(course);

      // Batch update the table.
      String insertString = @"Insert into [MySchool].[dbo].[Course]([CourseID],[Year],[Title],
                                   [Credits],[DepartmentID])
             values (@CourseID,@Year,@Title,@Credits,@DepartmentID)";
      SqlCommand insertCommand = new SqlCommand(insertString);
      insertCommand.Parameters.Add("@CourseID", SqlDbType.NVarChar, 10, "CourseID");
      insertCommand.Parameters.Add("@Year", SqlDbType.SmallInt, 2, "Year");
      insertCommand.Parameters.Add("@Title", SqlDbType.NVarChar, 100, "Title");
      insertCommand.Parameters.Add("@Credits", SqlDbType.Int, 4, "Credits");
      insertCommand.Parameters.Add("@DepartmentID", SqlDbType.Int, 4, "DepartmentID");

      const Int32 batchSize = 10;
      BatchInsertUpdate(course, settings.MySchoolConnectionString, insertCommand, batchSize);
   }

   private static void CopyData(DataSet dataSet, String connectionString, SqlCommand selectCommand, DataTableMapping[] tableMappings) {
      using (SqlConnection connection = new SqlConnection(connectionString)) {
         selectCommand.Connection = connection;

         connection.Open();

         using (SqlDataAdapter adapter = new SqlDataAdapter(selectCommand)) {adapter.TableMappings.AddRange(tableMappings);
            // If set the AcceptChangesDuringFill as the false, AcceptChanges will not be called on a
            // DataRow after it is added to the DataTable during any of the Fill operations.
            adapter.AcceptChangesDuringFill = false;

            adapter.Fill(dataSet);
         }
      }
   }

   // Roll back only one column or several columns data of the Course table by call ResetDataTable method.
   private static void ResetCourse(DataTable table, String connectionString,
       DataColumn[] primaryColumns, DataColumn[] resetColumns) {
      table.PrimaryKey = primaryColumns;

      // Build the query string
      String primaryCols = String.Join(",", primaryColumns.Select(col => col.ColumnName));
      String resetCols = String.Join(",", resetColumns.Select(col => $"Max({col.ColumnName}) as {col.ColumnName}"));

      String selectString = $"Select {primaryCols},{resetCols} from Course Group by {primaryCols}");

      SqlCommand selectCommand = new SqlCommand(selectString);

      ResetDataTable(table, connectionString, selectCommand);
   }

   // RejectChanges will roll back all changes made to the table since it was loaded, or the last time AcceptChanges
   // was called. When you copy from the database, you can lose all the data after calling RejectChanges
   // The ResetDataTable method rolls back one or more columns of data.
   private static void ResetDataTable(DataTable table, String connectionString,
       SqlCommand selectCommand) {
      using (SqlConnection connection = new SqlConnection(connectionString)) {
         selectCommand.Connection = connection;

         connection.Open();

         using (SqlDataAdapter adapter = new SqlDataAdapter(selectCommand)) {
            // The incoming values for this row will be written to the current version of each
            // column. The original version of each column's data will not be changed.
            adapter.FillLoadOption = LoadOption.Upsert;

            adapter.Fill(table);
         }
      }
   }

   private static void BatchInsertUpdate(DataTable table, String connectionString,
       SqlCommand insertCommand, Int32 batchSize) {
      using (SqlConnection connection = new SqlConnection(connectionString)) {
         insertCommand.Connection = connection;
         // When setting UpdateBatchSize to a value other than 1, all the commands
         // associated with the SqlDataAdapter have to have their UpdatedRowSource
         // property set to None or OutputParameters. An exception is thrown otherwise.
         insertCommand.UpdatedRowSource = UpdateRowSource.None;

         connection.Open();

         using (SqlDataAdapter adapter = new SqlDataAdapter()) {
            adapter.InsertCommand = insertCommand;
            // Gets or sets the number of rows that are processed in each round-trip to the server.
            // Setting it to 1 disables batch updates, as rows are sent one at a time.
            adapter.UpdateBatchSize = batchSize;

            adapter.Update(table);

            Console.WriteLine("Successfully to update the table.");
         }
      }
   }

   private static void ShowDataTable(DataTable table) {
      foreach (DataColumn col in table.Columns) {
         Console.Write("{0,-14}", col.ColumnName);
      }
      Console.WriteLine("{0,-14}", "RowState");

      foreach (DataRow row in table.Rows) {
         foreach (DataColumn col in table.Columns) {
            if (col.DataType.Equals(typeof(DateTime)))
               Console.Write("{0,-14:d}", row[col]);
            else if (col.DataType.Equals(typeof(Decimal)))
               Console.Write("{0,-14:C}", row[col]);
            else
               Console.Write("{0,-14}", row[col]);
         }
         Console.WriteLine("{0,-14}", row.RowState);
      }
   }
}
```

## <a name="see-also"></a>Siehe auch

- ["DataAdapters" und "DataReaders"](dataadapters-and-datareaders.md)
- [Zeilenstatus und Zeilenversionen](./dataset-datatable-dataview/row-states-and-row-versions.md)
- ["AcceptChanges" und "RejectChanges"](./dataset-datatable-dataview/acceptchanges-and-rejectchanges.md)
- [Zusammenführen von DataSet-Inhalten](./dataset-datatable-dataview/merging-dataset-contents.md)
- [Abrufen von Identity- oder Autonumber-Werten](retrieving-identity-or-autonumber-values.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
