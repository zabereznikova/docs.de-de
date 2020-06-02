---
title: Abrufen von Identity- oder Autonumber-Werten
description: Erfahren Sie, wie Sie Identitäts-und autonome Werte von primär Schlüsseln in relationalen Datenbanken abrufen und neue Identitäts Werte in ADO.net zusammenführen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6b7f9cb-81be-44e1-bb94-56137954876d
ms.openlocfilehash: dbbc013a5b6c83391a29109beca44120c68d827f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286571"
---
# <a name="retrieving-identity-or-autonumber-values"></a>Abrufen von Identity- oder Autonumber-Werten

Ein Primärschlüssel in einer relationalen Datenbank ist eine Spalte oder eine Kombination aus Spalten, die stets eindeutige Werte enthält. Wenn Sie den Primärschlüsselwert kennen, können Sie die Zeile lokalisieren, die den Wert enthält. Relationale Datenbank-Engines, wie SQL Server, Oracle und Microsoft Access/Jet, unterstützen das Erstellen automatisch inkrementierender Spalten, die als Primärschlüssel verwendet werden können. Diese Werte werden vom Server generiert, wenn einer Tabelle Zeilen hinzugefügt werden. In SQL Server legen Sie die Identität einer Spalte fest, in Oracle erstellen Sie eine Sequenz, und in Microsoft Access erstellen Sie eine AutoWert-Spalte.

Eine  kann durch Festlegen der -Eigenschaft auf true auch zum Generieren automatisch inkrementierender Werte verwendet werden. Wenn aber mehrere Clientanwendungen unabhängig voneinander automatisch inkrementierende Werte generieren, kann es passieren, dass zum Schluss in getrennten Instanzen einer <xref:System.Data.DataTable> doppelte Werte vorhanden sind. Wenn der Server angewiesen wird, automatisch inkrementierende Werte zu generieren, entfallen potenzielle Konflikte, weil jeder Benutzer für jede eingefügte Zeile den generierten Wert abrufen kann.

Bei einem Aufruf der `Update`-Methode eines `DataAdapter` kann die Datenbank Daten zurück an Ihre ADO.NET-Anwendung senden, und zwar entweder als Ausgabeparameter oder als ersten zurückgegebenen Datensatz des Resultsets einer SELECT-Anweisung, die im selben Batch wie die INSERT-Anweisung ausgeführt wird. ADO.NET kann diese Werte abrufen und die entsprechenden Spalten in der zu aktualisierenden <xref:System.Data.DataRow> aktualisieren.

Einige Datenbank-Engines, z.B. die Microsoft Access Jet-Datenbank-Engine, bieten keine Unterstützung für Ausgabeparameter und sind nicht in der Lage, mehrere Anweisungen in einem einzelnen Batch zu verarbeiten. Wenn Sie mit der Jet-Datenbank-Engine arbeiten, können Sie den neuen, für eine eingefügte Zeile generierten AutoWert-Wert abrufen, indem Sie in einem Ereignishandler für das `RowUpdated`-Ereignis des `DataAdapter` einen separaten SELECT-Befehl ausführen.

> [!NOTE]
> Statt automatisch inkrementierende Werte zu verwenden, können Sie auch mit der <xref:System.Guid.NewGuid%2A>-Methode eines <xref:System.Guid>-Objekts eine GUID auf dem Clientcomputer generieren, die jedes Mal, wenn eine neue Zeile eingefügt wird, auf den Server kopiert werden kann. Die `NewGuid`-Methode generiert einen 16-Byte-Binärwert, der mit einem Algorithmus erstellt wird, der dafür sorgt, dass mit hoher Wahrscheinlichkeit kein Wert doppelt vorhanden ist. In einer SQL Server-Datenbank werden GUIDs in einer `uniqueidentifier`-Spalte gespeichert, die SQL Server automatisch mit der Transact-SQL-`NEWID()`-Funktion generieren kann. Die Verwendung einer GUID als Primärschlüssel kann zu Leistungseinbußen führen. SQL Server bietet Unterstützung für die- `NEWSEQUENTIALID()` Funktion, die eine sequenzielle GUID generiert, die nicht unbedingt global eindeutig ist, aber effizienter indiziert werden kann.

## <a name="retrieving-sql-server-identity-column-values"></a>Abrufen von SQL Server-Identitätsspaltenwerten

Wenn Sie mit Microsoft SQL Server arbeiten, können Sie eine gespeicherte Prozedur mit einem Ausgabeparameter erstellen, um den Identitätswert für eine eingefügte Zeile zu erhalten. In der folgenden Tabelle werden die drei Transact-SQL-Funktionen in SQL Server beschrieben, mit denen Werte aus Identitätsspalten abgerufen werden können.

|Funktion|BESCHREIBUNG|
|--------------|-----------------|
|SCOPE_IDENTITY|Gibt den letzten Identitätswert innerhalb des aktuellen Ausführungsbereichs zurück. SCOPE_IDENTITY empfiehlt sich für die meisten Szenarien.|
|@@IDENTITY|Enthält den letzten Identitätswert, der in einer der Tabellen in der aktuellen Sitzung generiert wurde. @ @IDENTITY kann von Triggern beeinflusst werden und gibt möglicherweise nicht den erwarteten Identitäts Wert zurück.|
|IDENT_CURRENT|Gibt den letzten Identitätswert zurück, der für eine bestimmte Tabelle in einer der Sitzungen und in einem der Bereiche generiert wurde.|

 Die folgende gespeicherte Prozedur veranschaulicht, wie Sie eine Zeile in die **Kategorietabelle** einfügen und einen Output-Parameter verwenden, um den neuen Identitäts Wert zurückzugeben, der von der Transact-SQL-SCOPE_IDENTITY ()-Funktion generiert wurde.

```sql
CREATE PROCEDURE dbo.InsertCategory
  @CategoryName nvarchar(15),
  @Identity int OUT
AS
INSERT INTO Categories (CategoryName) VALUES(@CategoryName)
SET @Identity = SCOPE_IDENTITY()
```

Die gespeicherte Prozedur kann dann als Quelle des <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> eines <xref:System.Data.SqlClient.SqlDataAdapter>-Objekts angegeben werden. Die <xref:System.Data.SqlClient.SqlCommand.CommandType%2A>-Eigenschaft des <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> muss auf <xref:System.Data.CommandType.StoredProcedure> festgelegt werden. Die Identitätsausgabe wird abgerufen, indem ein <xref:System.Data.SqlClient.SqlParameter> mit dem <xref:System.Data.ParameterDirection>-Wert <xref:System.Data.ParameterDirection.Output> erstellt wird. Wenn der `InsertCommand` verarbeitet wird, wird der automatisch inkrementierte Identitäts Wert zurückgegeben und in der **CategoryID** -Spalte der aktuellen Zeile abgelegt, wenn Sie die- <xref:System.Data.SqlClient.SqlCommand.UpdatedRowSource%2A> Eigenschaft des INSERT-Befehls auf `UpdateRowSource.OutputParameters` oder festlegen `UpdateRowSource.Both` .

Wenn Ihr Einfügebefehl einen Batch ausführt, der sowohl eine INSERT-Anweisung als auch eine SELECT-Anweisung enthält, die den neuen Identitätswert zurückgibt, können Sie den neuen Wert abrufen, indem Sie für die `UpdatedRowSource`-Eigenschaft des Einfügebefehls den Wert `UpdateRowSource.FirstReturnedRecord` festlegen.

[!code-csharp[DataWorks SqlClient.RetrieveIdentityStoredProcedure#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.RetrieveIdentityStoredProcedure/CS/source.cs#1)]
[!code-vb[DataWorks SqlClient.RetrieveIdentityStoredProcedure#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.RetrieveIdentityStoredProcedure/VB/source.vb#1)]

## <a name="merging-new-identity-values"></a>Zusammenführen neuer Identitätswerte

Häufig wird die `GetChanges`-Methode einer `DataTable` verwendet, um eine Kopie zu erstellen, die nur geänderte Zeilen enthält. Beim Aufrufen der `Update`-Methode eines `DataAdapter` kommt dann die neue Kopie zum Einsatz. Diese Vorgehensweise ist vor allem dann sinnvoll, wenn Sie die geänderten Zeilen in eine separate Komponente marshallen müssen, die das Update ausführt. Im Anschluss an das Update kann die Kopie die neuen Identitätswerte enthalten, die dann in der ursprünglichen `DataTable` wieder zusammengeführt werden müssen. Die neuen Identitätswerte weichen wahrscheinlich von den ursprünglichen Werten in der `DataTable` ab. Um die Zusammenführung zu erreichen, müssen die ursprünglichen Werte der **AutoIncrement** -Spalten in der Kopie beibehalten werden, damit vorhandene Zeilen im Original gefunden und aktualisiert werden können `DataTable` , anstatt neue Zeilen mit den neuen Identitäts Werten anzufügen. Standardmäßig gehen diese ursprünglichen Werte aber nach einem Aufruf der `Update`-Methode eines `DataAdapter` verloren, weil für jede aktualisierte `AcceptChanges` implizit `DataRow` aufgerufen wird.

Zum Beibehalten der ursprünglichen Werte einer `DataColumn` in einer `DataRow` während eines `DataAdapter`-Updates gibt es die folgenden beiden Möglichkeiten:

- Die erste Methode besteht darin, für die `AcceptChangesDuringUpdate`-Eigenschaft des `DataAdapter``false` festzulegen. Dies wirkt sich auf jede `DataRow` in der zu aktualisierenden `DataTable` aus. Weitere Informationen sowie ein Codebeispiel finden Sie unter <xref:System.Data.Common.DataAdapter.AcceptChangesDuringUpdate%2A>.

- Die zweite Methode besteht darin, Code im `RowUpdated`-Ereignishandler des `DataAdapter` zu schreiben und damit den <xref:System.Data.Common.RowUpdatedEventArgs.Status%2A> auf <xref:System.Data.UpdateStatus.SkipCurrentRow> zu setzen. Die `DataRow` wird zwar aktualisiert, aber die einzelnen ursprünglichen `DataColumn`-Werte bleiben erhalten. Diese Methode ermöglicht es Ihnen, die ursprünglichen Werte für einige Zeilen beizubehalten und für andere nicht. Ihr Code kann z. B. die ursprünglichen Werte für hinzugefügte Zeilen beibehalten, während die ursprünglichen Werte für bearbeitete oder gelöschte Zeilen verloren gehen, indem er zunächst den <xref:System.Data.Common.RowUpdatedEventArgs.StatementType%2A> prüft und dann den <xref:System.Data.Common.RowUpdatedEventArgs.Status%2A> nur für die Zeilen mit dem <xref:System.Data.UpdateStatus.SkipCurrentRow>`StatementType` auf `Insert` setzt.

Wenn bei einem `DataRow`-Update eine dieser beiden Methoden zur Beibehaltung von ursprünglichen Werten in einer `DataAdapter` verwendet wird, führt ADO.NET eine Reihe von Aktionen aus, um die aktuellen `DataRow`-Werte auf die neuen Werte zu setzen, die von Ausgabeparametern oder der ersten zurückgegebenen Zeile eines Resultsets zurückgegeben werden. Die einzelnen ursprünglichen `DataColumn`-Werte bleiben dabei erhalten. Als Erstes wird die `AcceptChanges`-Methode der `DataRow` aufgerufen, um die aktuellen Werte als ursprüngliche Werte beizubehalten. Anschließend werden die neuen Werte zugewiesen. Als Nächstes wird bei `DataRows`, deren <xref:System.Data.DataRow.RowState%2A>-Eigenschaft den Wert <xref:System.Data.DataRowState.Added> hat, der `RowState`-Wert in <xref:System.Data.DataRowState.Modified> geändert, was u. U. nicht den Erwartungen entspricht.

Wie die Befehlsergebnisse auf jede zu aktualisierende <xref:System.Data.DataRow> angewendet werden, richtet sich nach der <xref:System.Data.Common.DbCommand.UpdatedRowSource%2A>-Eigenschaft des jeweiligen <xref:System.Data.Common.DbCommand>. Diese Eigenschaft wird auf einen Wert aus der `UpdateRowSource`-Enumeration festgelegt.

Die folgende Tabelle zeigt, wie sich die `UpdateRowSource`-Enumerationswerte auf die <xref:System.Data.DataRow.RowState%2A>-Eigenschaft aktualisierter Zeilen auswirken.

|Membername|BESCHREIBUNG|
|-----------------|-----------------|
|<xref:System.Data.UpdateRowSource.Both>|`AcceptChanges` wird aufgerufen, und die Ausgabeparameterwerte und/oder die Werte der ersten Zeile aller zurückgegebenen Resultsets werden in der zu aktualisierenden `DataRow` platziert. Wenn es keine zu übernehmenden Werte gibt, lautet der `RowState`<xref:System.Data.DataRowState.Unchanged>.|
|<xref:System.Data.UpdateRowSource.FirstReturnedRecord>|Wenn eine Zeile zurückgegeben wurde, wird `AcceptChanges` aufgerufen und die Zeile wird der geänderten Zeile in der `DataTable` zugeordnet, wobei der `RowState` auf `Modified` gesetzt wird. Wenn keine Zeile zurückgegeben wird, wird `AcceptChanges` nicht aufgerufen, und der `RowState` bleibt `Added`.|
|<xref:System.Data.UpdateRowSource.None>|Alle zurückgegebenen Parameter oder Zeilen werden ignoriert. `AcceptChanges` wird nicht aufgerufen, und der `RowState` bleibt `Added`.|
|<xref:System.Data.UpdateRowSource.OutputParameters>|`AcceptChanges` wird aufgerufen, und alle Ausgabeparameter werden der geänderten Zeile in der `DataTable` zugeordnet, wobei der `RowState` auf `Modified` gesetzt wird. Wenn keine Ausgabeparameter vorhanden sind, lautet der `RowState``Unchanged`.|

### <a name="example"></a>Beispiel

Dieses Beispiel zeigt das Extrahieren geänderter Zeilen aus einer `DataTable` und das Verwenden eines <xref:System.Data.SqlClient.SqlDataAdapter>, um die Datenquelle zu aktualisieren und einen neuen Wert aus der Identitätsspalte abzurufen. Der <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> führt zwei Transact-SQL-Anweisungen aus: Die erste Anweisung ist die INSERT-Anweisung, und die zweite Anweisung ist eine SELECT-Anweisung, die zum Abrufen des Identitätswerts die Funktion SCOPE_IDENTITY verwendet.

```sql
INSERT INTO dbo.Shippers (CompanyName)
VALUES (@CompanyName);
SELECT ShipperID, CompanyName FROM dbo.Shippers
WHERE ShipperID = SCOPE_IDENTITY();
```

Die `UpdatedRowSource`-Eigenschaft des Einfügebefehls wird auf `UpdateRowSource.FirstReturnedRow` gesetzt, und die <xref:System.Data.MissingSchemaAction>-Eigenschaft des `DataAdapter` wird auf `MissingSchemaAction.AddWithKey` gesetzt. Die `DataTable` wird gefüllt, und der Code fügt der `DataTable` eine neue Zeile hinzu. Die geänderten Zeilen werden dann in eine neue `DataTable` extrahiert, die an den `DataAdapter` übergeben wird, der dann wiederum den Server aktualisiert.

[!code-csharp[DataWorks SqlClient.MergeIdentity#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.MergeIdentity/CS/source.cs#1)]
[!code-vb[DataWorks SqlClient.MergeIdentity#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.MergeIdentity/VB/source.vb#1)]

Der `OnRowUpdated`-Ereignishandler prüft den <xref:System.Data.Common.RowUpdatedEventArgs.StatementType%2A> der <xref:System.Data.SqlClient.SqlRowUpdatedEventArgs>, um festzustellen, ob es sich bei der Zeile um eine Einfügung handelt. Wenn ja, wird die <xref:System.Data.Common.RowUpdatedEventArgs.Status%2A>-Eigenschaft auf <xref:System.Data.UpdateStatus.SkipCurrentRow> gesetzt. Die Zeile wird aktualisiert, aber die ursprünglichen Werte in der Zeile werden beibehalten. Im Hauptteil der Prozedur wird die <xref:System.Data.DataSet.Merge%2A>-Methode aufgerufen, um den neuen Identitätswert in der ursprünglichen `DataTable` zusammenzuführen. Zum Schluss wird die `AcceptChanges`-Methode aufgerufen.

[!code-csharp[DataWorks SqlClient.MergeIdentity#2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.MergeIdentity/CS/source.cs#2)]
[!code-vb[DataWorks SqlClient.MergeIdentity#2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.MergeIdentity/VB/source.vb#2)]

## <a name="retrieving-microsoft-access-autonumber-values"></a>Abrufen von Microsoft Access-AutoWert-Werten

Dieser Abschnitt enthält ein Beispiel, das die Vorgehensweise beim Abrufen von `Autonumber`-Werten aus einer Jet 4.0-Datenbank zeigt. Die Jet-Datenbank-Engine bietet keine Unterstützung für die Ausführung mehrerer Anweisungen in einem Batch oder für die Verwendung von Ausgabeparametern. Es ist daher nicht möglich, mit einer der beiden Möglichkeiten den neuen `Autonumber`-Wert zurückzugeben, der einer eingefügten Zeile zugewiesen wurde. Sie können jedoch dem-Ereignishandler Code hinzufügen `RowUpdated` , der eine separate SELECT @-Anweisung ausführt, @IDENTITY um den neuen `Autonumber` Wert abzurufen.

### <a name="example"></a>Beispiel

Statt mit `MissingSchemaAction.AddWithKey` Schemainformationen hinzuzufügen, konfiguriert dieses Beispiel eine `DataTable` mit dem korrekten Schema, bevor der <xref:System.Data.OleDb.OleDbDataAdapter> zum Füllen der `DataTable` aufgerufen wird. In diesem Fall wird die Spalte **CategoryID** so konfiguriert, dass der Wert, dem jede eingefügte Zeile zugewiesen wird, mit 0 (null) verringert wird, indem <xref:System.Data.DataColumn.AutoIncrement%2A> auf `true` , <xref:System.Data.DataColumn.AutoIncrementSeed%2A> auf 0 und <xref:System.Data.DataColumn.AutoIncrementStep%2A> auf-1 festgelegt wird. Der Code fügt dann zwei neue Zeilen hinzu und verwendet `GetChanges`, um die geänderten Zeilen einer neuen `DataTable` hinzuzufügen, die an die `Update`-Methode übergeben wird.

[!code-csharp[DataWorks OleDb.JetAutonumberMerge#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks OleDb.JetAutonumberMerge/CS/source.cs#1)]
[!code-vb[DataWorks OleDb.JetAutonumberMerge#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks OleDb.JetAutonumberMerge/VB/source.vb#1)]

Der `RowUpdated`-Ereignishandler verwendet dieselbe geöffnete <xref:System.Data.OleDb.OleDbConnection> wie die `Update`-Anweisung des `OleDbDataAdapter`. Er prüft den `StatementType` der <xref:System.Data.OleDb.OleDbRowUpdatedEventArgs> auf eingefügte Zeilen. Für jede eingefügte Zeile <xref:System.Data.OleDb.OleDbCommand> wird ein neues erstellt, um die SELECT @- @IDENTITY Anweisung für die Verbindung auszuführen. dabei wird der neue Wert zurückgegeben `Autonumber` , der in der **CategoryID** -Spalte des platziert wird `DataRow` . Die `Status`-Eigenschaft wird dann auf `UpdateStatus.SkipCurrentRow` gesetzt, um den versteckten Aufruf von `AcceptChanges` zu unterdrücken. Im Hauptteil der Prozedur wird die `Merge`-Methode aufgerufen, um die beiden `DataTable`-Objekte zusammenzuführen. Zum Schluss erfolgt ein Aufruf der `AcceptChanges`-Methode.

[!code-csharp[DataWorks OleDb.JetAutonumberMerge#2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks OleDb.JetAutonumberMerge/CS/source.cs#2)]
[!code-vb[DataWorks OleDb.JetAutonumberMerge#2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks OleDb.JetAutonumberMerge/VB/source.vb#2)]

### <a name="retrieving-identity-values"></a>Abrufen von Identitätswerten

Wir legen häufig die Spalte als Identität fest, wenn die Werte in der Spalte eindeutig sein müssen. Und manchmal brauchen wir den Identitätswert neuer Daten. In diesem Beispiel wird veranschaulicht, wie Sie Identitätswerte abrufen:

- Erstellt eine gespeichertes Verfahren, um Daten einzufügen und einen Identitätswert zurückzugeben.

- Führt einen Befehl zum Einfügen der neuen Daten und zum Anzeigen des Ergebnisses aus

- Verwendet <xref:System.Data.SqlClient.SqlDataAdapter>, um neue Daten einzufügen und das Ergebnis anzuzeigen.

Vor dem Kompilieren und Ausführen des Beispiels müssen Sie die Beispieldatenbank mithilfe des folgenden Skripts erstellen:

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
CREATE procedure [dbo].[CourseExtInfo] @CourseId int
as
select c.CourseID,c.Title,c.Credits,d.Name as DepartmentName
from Course as c left outer join Department as d on c.DepartmentID=d.DepartmentID
where c.CourseID=@CourseId

GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
create procedure [dbo].[DepartmentInfo] @DepartmentId int,@CourseCount int output
as
select @CourseCount=Count(c.CourseID)
from course as c
where c.DepartmentID=@DepartmentId

select d.DepartmentID,d.Name,d.Budget,d.StartDate,d.Administrator
from Department as d
where d.DepartmentID=@DepartmentId

GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
Create PROCEDURE [dbo].[GetDepartmentsOfSpecifiedYear]
@Year int,@BudgetSum money output
AS
BEGIN
        SELECT @BudgetSum=SUM([Budget])
  FROM [MySchool].[dbo].[Department]
  Where YEAR([StartDate])=@Year

SELECT [DepartmentID]
      ,[Name]
      ,[Budget]
      ,[StartDate]
      ,[Administrator]
  FROM [MySchool].[dbo].[Department]
  Where YEAR([StartDate])=@Year

END
GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE PROCEDURE [dbo].[GradeOfStudent]
-- Add the parameters for the stored procedure here
@CourseTitle nvarchar(100),@FirstName nvarchar(50),
@LastName nvarchar(50),@Grade decimal(3,2) output
AS
BEGIN
select @Grade=Max(Grade)
from [dbo].[StudentGrade] as s join [dbo].[Course] as c on
s.CourseID=c.CourseID join [dbo].[Person] as p on s.StudentID=p.PersonID
where c.Title=@CourseTitle and p.FirstName=@FirstName
and p.LastName= @LastName
END
GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE PROCEDURE [dbo].[InsertPerson]
-- Add the parameters for the stored procedure here
@FirstName nvarchar(50),@LastName nvarchar(50),
@PersonID int output
AS
BEGIN
    insert [dbo].[Person](LastName,FirstName) Values(@LastName,@FirstName)

    set @PersonID=SCOPE_IDENTITY()
END
Go

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

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
SET ANSI_PADDING ON
GO
CREATE TABLE [dbo].[Person]([PersonID] [int] IDENTITY(1,1) NOT NULL,
[LastName] [nvarchar](50) NOT NULL,
[FirstName] [nvarchar](50) NOT NULL,
[HireDate] [datetime] NULL,
[EnrollmentDate] [datetime] NULL,
[Picture] [varbinary](max) NULL,
 CONSTRAINT [PK_School.Student] PRIMARY KEY CLUSTERED
(
[PersonID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]

GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[StudentGrade]([EnrollmentID] [int] IDENTITY(1,1) NOT NULL,
[CourseID] [nvarchar](10) NOT NULL,
[StudentID] [int] NOT NULL,
[Grade] [decimal](3, 2) NOT NULL,
 CONSTRAINT [PK_StudentGrade] PRIMARY KEY CLUSTERED
(
[EnrollmentID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]

GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
create view [dbo].[EnglishCourse]
as
select c.CourseID,c.Title,c.Credits,c.DepartmentID
from Course as c join Department as d on c.DepartmentID=d.DepartmentID
where d.Name=N'English'

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
SET IDENTITY_INSERT [dbo].[Person] ON

INSERT [dbo].[Person] ([PersonID], [LastName], [FirstName], [HireDate], [EnrollmentDate]) VALUES (1, N'Hu', N'Nan', NULL, CAST(0x0000A0BF00000000 AS DateTime))
INSERT [dbo].[Person] ([PersonID], [LastName], [FirstName], [HireDate], [EnrollmentDate]) VALUES (2, N'Norman', N'Laura', NULL, CAST(0x0000A0BF00000000 AS DateTime))
INSERT [dbo].[Person] ([PersonID], [LastName], [FirstName], [HireDate], [EnrollmentDate]) VALUES (3, N'Olivotto', N'Nino', NULL, CAST(0x0000A0BF00000000 AS DateTime))
INSERT [dbo].[Person] ([PersonID], [LastName], [FirstName], [HireDate], [EnrollmentDate]) VALUES (4, N'Anand', N'Arturo', NULL, CAST(0x0000A0BF00000000 AS DateTime))
INSERT [dbo].[Person] ([PersonID], [LastName], [FirstName], [HireDate], [EnrollmentDate]) VALUES (5, N'Jai', N'Damien', NULL, CAST(0x0000A0BF00000000 AS DateTime))
INSERT [dbo].[Person] ([PersonID], [LastName], [FirstName], [HireDate], [EnrollmentDate]) VALUES (6, N'Holt', N'Roger', CAST(0x000097F100000000 AS DateTime), NULL)
INSERT [dbo].[Person] ([PersonID], [LastName], [FirstName], [HireDate], [EnrollmentDate]) VALUES (7, N'Martin', N'Randall', CAST(0x00008B1A00000000 AS DateTime), NULL)
SET IDENTITY_INSERT [dbo].[Person] OFF
SET IDENTITY_INSERT [dbo].[StudentGrade] ON

INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (1, N'C1045', 1, CAST(3.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (2, N'C1045', 2, CAST(3.00 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (3, N'C1045', 3, CAST(2.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (4, N'C1045', 4, CAST(4.00 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (5, N'C1045', 5, CAST(3.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (6, N'C1061', 1, CAST(4.00 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (7, N'C1061', 3, CAST(3.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (8, N'C1061', 4, CAST(2.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (9, N'C1061', 5, CAST(1.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (10, N'C2021', 1, CAST(2.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (11, N'C2021', 2, CAST(3.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (12, N'C2021', 4, CAST(3.00 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (13, N'C2021', 5, CAST(3.00 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (14, N'C2042', 1, CAST(2.00 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (15, N'C2042', 2, CAST(3.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (16, N'C2042', 3, CAST(4.00 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (17, N'C2042', 5, CAST(3.00 AS Decimal(3, 2)))
SET IDENTITY_INSERT [dbo].[StudentGrade] OFF
ALTER TABLE [dbo].[Course]  WITH CHECK ADD  CONSTRAINT [FK_Course_Department] FOREIGN KEY([DepartmentID])
REFERENCES [dbo].[Department] ([DepartmentID])
GO
ALTER TABLE [dbo].[Course] CHECK CONSTRAINT [FK_Course_Department]
GO
ALTER TABLE [dbo].[StudentGrade]  WITH CHECK ADD  CONSTRAINT [FK_StudentGrade_Student] FOREIGN KEY([StudentID])
REFERENCES [dbo].[Person] ([PersonID])
GO
ALTER TABLE [dbo].[StudentGrade] CHECK CONSTRAINT [FK_StudentGrade_Student]
GO
```

Das Codebeispiel folgt:

> [!TIP]
> Das Codebeispiel bezieht sich auf eine Access-Datenbankdatei namens MySchool.mdb. Sie können mySchool. mdb (als Teil des vollständigen c#-oder Visual Basic-Beispielprojekts) von [Code.msdn.Microsoft.com](https://code.msdn.microsoft.com/How-to-Retrieve-the-511acece)herunterladen.

```csharp
using System;
using System.Data;
using System.Data.OleDb;
using System.Data.SqlClient;

class Program {
   static void Main(string[] args) {
      String SqlDbConnectionString = "Data Source=(local);Initial Catalog=MySchool;Integrated Security=True;Asynchronous Processing=true;";

      InsertPerson(SqlDbConnectionString, "Janice", "Galvin");
      Console.WriteLine();

      InsertPersonInAdapter(SqlDbConnectionString, "Peter", "Krebs");
      Console.WriteLine();

      String oledbConnectionString = "Provider=Microsoft.Jet.OLEDB.4.0; Data Source=Database\\MySchool.mdb";
      InsertPersonInJet4Database(oledbConnectionString, "Janice", "Galvin");
      Console.WriteLine();

      Console.WriteLine("Please press any key to exit.....");
      Console.ReadKey();
   }

   // Using stored procedure to insert a new row and retrieve the identity value
   static void InsertPerson(String connectionString, String firstName, String lastName) {
      String commandText = "dbo.InsertPerson";

      using (SqlConnection conn = new SqlConnection(connectionString)) {
         using (SqlCommand cmd = new SqlCommand(commandText, conn)) {
            cmd.CommandType = CommandType.StoredProcedure;

            cmd.Parameters.Add(new SqlParameter("@FirstName", firstName));
            cmd.Parameters.Add(new SqlParameter("@LastName", lastName));
            SqlParameter personId = new SqlParameter("@PersonID", SqlDbType.Int);
            personId.Direction = ParameterDirection.Output;
            cmd.Parameters.Add(personId);

            conn.Open();
            cmd.ExecuteNonQuery();

            Console.WriteLine("Person Id of new person:{0}", personId.Value);
         }
      }
   }

   // Using stored procedure in adapter to insert new rows and update the identity value.
   static void InsertPersonInAdapter(String connectionString, String firstName, String lastName) {
      String commandText = "dbo.InsertPerson";
      using (SqlConnection conn = new SqlConnection(connectionString)) {
         SqlDataAdapter mySchool = new SqlDataAdapter("Select PersonID,FirstName,LastName from [dbo].[Person]", conn);

         mySchool.InsertCommand = new SqlCommand(commandText, conn);
         mySchool.InsertCommand.CommandType = CommandType.StoredProcedure;

         mySchool.InsertCommand.Parameters.Add(
             new SqlParameter("@FirstName", SqlDbType.NVarChar, 50, "FirstName"));
         mySchool.InsertCommand.Parameters.Add(
             new SqlParameter("@LastName", SqlDbType.NVarChar, 50, "LastName"));

         SqlParameter personId = mySchool.InsertCommand.Parameters.Add(new SqlParameter("@PersonID", SqlDbType.Int, 0, "PersonID"));
         personId.Direction = ParameterDirection.Output;

         DataTable persons = new DataTable();
         mySchool.Fill(persons);

         DataRow newPerson = persons.NewRow();
         newPerson["FirstName"] = firstName;
         newPerson["LastName"] = lastName;
         persons.Rows.Add(newPerson);

         mySchool.Update(persons);
         Console.WriteLine("Show all persons:");
         ShowDataTable(persons, 14);
      }
   }

   /// For a Jet 4.0 database, we need use the single statement and event handler to insert new rows and retrieve the identity value.
   static void InsertPersonInJet4Database(String connectionString, String firstName, String lastName) {
      String commandText = "Insert into Person(FirstName,LastName) Values(?,?)";
      using (OleDbConnection conn = new OleDbConnection(connectionString)) {
         OleDbDataAdapter mySchool = new OleDbDataAdapter("Select PersonID,FirstName,LastName from Person", conn);

         // Create Insert Command
         mySchool.InsertCommand = new OleDbCommand(commandText, conn);
         mySchool.InsertCommand.CommandType = CommandType.Text;

         mySchool.InsertCommand.Parameters.Add(new OleDbParameter("@FirstName", OleDbType.VarChar, 50, "FirstName"));
         mySchool.InsertCommand.Parameters.Add(new OleDbParameter("@LastName", OleDbType.VarChar, 50, "LastName"));
         mySchool.InsertCommand.UpdatedRowSource = UpdateRowSource.Both;

         DataTable persons = CreatePersonsTable();

         mySchool.Fill(persons);

         DataRow newPerson = persons.NewRow();
         newPerson["FirstName"] = firstName;
         newPerson["LastName"] = lastName;
         persons.Rows.Add(newPerson);

         DataTable dataChanges = persons.GetChanges();

         mySchool.RowUpdated += OnRowUpdated;

         mySchool.Update(dataChanges);

         Console.WriteLine("Data before merging:");
         ShowDataTable(persons, 14);
         Console.WriteLine();

         persons.Merge(dataChanges);
         persons.AcceptChanges();

         Console.WriteLine("Data after merging");
         ShowDataTable(persons, 14);
      }
   }

   static void OnRowUpdated(object sender, OleDbRowUpdatedEventArgs e) {
      if (e.StatementType == StatementType.Insert) {
         // Retrieve the identity value
         OleDbCommand cmdNewId = new OleDbCommand("Select @@IDENTITY", e.Command.Connection);
         e.Row["PersonID"] = (Int32)cmdNewId.ExecuteScalar();

         // After the status is changed, the original values in the row are preserved. And the
         // Merge method will be called to merge the new identity value into the original DataTable.
         e.Status = UpdateStatus.SkipCurrentRow;
      }
   }

   // Create the Persons table before filling.
   private static DataTable CreatePersonsTable() {
      DataTable persons = new DataTable();

      DataColumn personId = new DataColumn();
      personId.DataType = Type.GetType("System.Int32");
      personId.ColumnName = "PersonID";
      personId.AutoIncrement = true;
      personId.AutoIncrementSeed = 0;
      personId.AutoIncrementStep = -1;
      persons.Columns.Add(personId);

      DataColumn firstName = new DataColumn();
      firstName.DataType = Type.GetType("System.String");
      firstName.ColumnName = "FirstName";
      persons.Columns.Add(firstName);

      DataColumn lastName = new DataColumn();
      lastName.DataType = Type.GetType("System.String");
      lastName.ColumnName = "LastName";
      persons.Columns.Add(lastName);

      DataColumn[] pkey = { personId };
      persons.PrimaryKey = pkey;

      return persons;
   }

   private static void ShowDataTable(DataTable table, Int32 length) {
      foreach (DataColumn col in table.Columns) {
         Console.Write("{0,-" + length + "}", col.ColumnName);
      }
      Console.WriteLine();

      foreach (DataRow row in table.Rows) {
         foreach (DataColumn col in table.Columns) {
            if (col.DataType.Equals(typeof(DateTime)))
               Console.Write("{0,-" + length + ":d}", row[col]);
            else if (col.DataType.Equals(typeof(Decimal)))
               Console.Write("{0,-" + length + ":C}", row[col]);
            else
               Console.Write("{0,-" + length + "}", row[col]);
         }

         Console.WriteLine();
      }
   }
}
```

## <a name="see-also"></a>Siehe auch

- [Abrufen und Ändern von Daten in ADO.NET](retrieving-and-modifying-data.md)
- ["DataAdapters" und "DataReaders"](dataadapters-and-datareaders.md)
- [Zeilenstatus und Zeilenversionen](./dataset-datatable-dataview/row-states-and-row-versions.md)
- ["AcceptChanges" und "RejectChanges"](./dataset-datatable-dataview/acceptchanges-and-rejectchanges.md)
- [Zusammenführen von DataSet-Inhalten](./dataset-datatable-dataview/merging-dataset-contents.md)
- [Aktualisieren von Datenquellen mit "DataAdapters"](updating-data-sources-with-dataadapters.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
