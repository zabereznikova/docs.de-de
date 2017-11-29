---
title: 'Exemplarische Vorgehensweise: Zugreifen auf eine SQL-Datenbank mithilfe von Typanbietern (F#)'
description: "Erfahren Sie, wie den SqlDataConnection (LINQ to SQL) vom Typanbieter in f# 3.0-Typen für SQL-Datenbank zu generieren, wenn Sie eine live-Datenbank verbunden."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1c413eb0-16a5-4c1a-9a4e-ad6877e645d6
ms.openlocfilehash: c99afc1121b4f0d6d05ef82681a32437ede06e42
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers"></a>Exemplarische Vorgehensweise: Zugreifen auf eine SQL-Datenbank mithilfe von Typanbietern

> [!NOTE]
Dieses Handbuch wurde für f# 3.0 geschrieben und wird aktualisiert.  Unter [FSharp.Data](http://fsharp.github.io/FSharp.Data/) finden Sie aktuelle plattformübergeifende Typanbieter.

> [!NOTE]
Die API-Referenz Links gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

In dieser exemplarischen Vorgehensweise wird erläutert, wie der SqlDataConnection (LINQ to SQL)-Typanbieter verwendet wird, der in f# 3.0 zum Generieren von Typen für Daten in einer SQL­Datenbank, wenn Sie eine live-Verbindung mit einer Datenbank haben verfügbar ist. Wenn Sie verfügen nicht über eine live-Verbindung mit einer Datenbank, aber Sie eine LINQ to SQL-Schema-Datei (DBML-Datei müssen), finden Sie unter [Exemplarische Vorgehensweise: Generieren von f#-Typen aus einer DBML-Datei](generating-fsharp-types-from-dbml.md).

In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben beschrieben. Diese Aufgaben müssen in genau dieser Reihenfolge für die exemplarische Vorgehensweise erfolgreich ausgeführt werden:


- Eine Testdatenbank vorbereiten

- Erstellen des Projekts

- Einrichten eines typanbieters

- Abfragen der Daten

- Arbeiten mit auf NULL festlegbare Felder

- Aufrufen einer gespeicherten Prozedur

- Aktualisieren der Datenbank

- Ausführen von Transact-SQL-code

- Verwenden die vollständige Datenkontext

- Löschen von Daten

- Erstellen Sie eine Testdatenbank (nach Bedarf)

## <a name="preparing-a-test-database"></a>Eine Testdatenbank vorbereiten
Erstellen Sie auf einem Server, auf der SQL Server ausgeführt wird eine Datenbank für Testzwecke verwenden. Sie können die Datenbank verwenden Erstellungsskript am unteren Rand dieser Seite im Abschnitt [erstellen eine Testdatenbank](#creating-a-test-database) dazu.


#### <a name="to-prepare-a-test-database"></a>Eine Testdatenbank vorbereiten

MyDatabase-Erstellungsskript ausführen möchten, öffnen die **Ansicht** Menü, und wählen Sie dann **Objekt-Explorer von SQL Server** , oder wählen Sie die STRG +\, Tasten STRG + S. In **Objekt-Explorer von SQL Server** Fenster, öffnen Sie das Kontextmenü für die entsprechende Instanz, wählen Sie **neue Abfrage**, kopieren Sie das Skript am unteren Rand dieser Seite, und klicken Sie dann das Skript in Editor einfügen. Um das SQL-Skript auszuführen, wählen Sie die Symbolleiste auf das Symbol mit dem dreieckiges Symbol, oder wählen Sie die Tastenkombination STRG + Q. Weitere Informationen zu **Objekt-Explorer von SQL Server**, finden Sie unter [Entwicklung verbundener Datenbanken](https://msdn.microsoft.com/library/hh272679(VS.103).aspx).


## <a name="creating-the-project"></a>Erstellen des Projekts
Als Nächstes erstellen Sie ein f#-Anwendungsprojekt.


#### <a name="to-create-and-set-up-the-project"></a>So erstellen und richten Sie das Projekt ein

1. Erstellen Sie ein neues F#-Anwendungsprojekt.

2. Fügen Sie Verweise auf [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3), als auch `System.Data`, und `System.Data.Linq`.

3. Die folgenden Codezeilen am Anfang der F#-Codedatei Program.fs hinzufügen, um die entsprechende Namespaces zu öffnen.

  ```fsharp
open System
open System.Data
open System.Data.Linq
open Microsoft.FSharp.Data.TypeProviders
open Microsoft.FSharp.Linq
```

4. Wie bei den meisten F#-Programmen, führen Sie den Code in dieser exemplarischen Vorgehensweise als kompiliertes Programm oder können interaktiv als Skript ausführen. Wenn Sie Skripts verwenden möchten, öffnen Sie das Kontextmenü für den Projektknoten **neues Element hinzufügen**, fügen Sie ein f#-Skriptdatei hinzu, und fügen Sie den Code in den einzelnen Schritten, um das Skript. Sie müssen die folgenden Zeilen am Anfang der Datei zum Laden der Assemblyverweise hinzufügen.

  ```fsharp
#r "System.Data.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

  Sie können jeden Codeblock dann auswählen, wie Sie ihn hinzufügen, und drücken Sie Alt + Eingabe, für die Ausführung in f# Interactive.

## <a name="setting-up-a-type-provider"></a>Einrichten eines typanbieters
In diesem Schritt erstellen Sie einen Typanbieter für das Datenbankschema.


#### <a name="to-set-up-the-type-provider-from-a-direct-database-connection"></a>So richten Sie den Typanbieter aus eine direkte datenbankverbindung ein

Es gibt zwei wichtige Codezeilen, die Sie benötigen, um die Typen zu erstellen, die Sie verwenden können, um den Typanbieter mit einer SQL-Datenbank abzufragen. Zuerst, instanziieren Sie den Typanbieter an. Zu diesem Zweck erstellen illustriert typabkürzung für eine `SqlDataConnection` mit einem statischen generischen Parameter. `SqlDataConnection`ist ein SQL-Typ-Anbieter und sollte nicht mit verwechselt werden `SqlConnection` -Typ, bei der Programmierung von ADO.NET verwendet. Wenn Sie mit einer Datenbank, die Sie herstellen möchten, und eine Verbindungszeichenfolge besitzen, verwenden Sie den folgenden Code zum Aufrufen des typanbieters. Ersetzen Sie durch Ihre eigene Verbindungszeichenfolge für die Beispielzeichenfolge angegeben. Bei der Server "EigenerServer" und die Datenbankinstanz Instanz ist, der Datenbankname ist MyDatabase und die Datenbank, und klicken Sie dann auf die Verbindungszeichenfolge Zugriff auf Windows-Authentifizierung verwendet werden sollen, als wäre angenommen, in der folgende Beispielcode.

```fsharp
type dbSchema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;">
let db = dbSchema.GetDataContext()

// Enable the logging of database activity to the console.
db.DataContext.Log <- System.Console.Out
```

Nachdem Sie einen Typ haben `dbSchema`, d. h. einen übergeordneten Typ, der die generierten Typen enthält, die Datenbanktabellen darstellen. Außerdem haben Sie ein Objekt, das `db`, die als Mitglieder aller Tabellen in der Datenbank hat. Die Tabellennamen sind Eigenschaften, und der Typ dieser Eigenschaften wird vom F#-Compiler generiert. Die Typen selbst angezeigt wird, als geschachtelte Typen unter `dbSchema.ServiceTypes`. Alle Zeilen dieser Tabellen abgerufenen Daten ist daher eine Instanz des entsprechenden Typs, der für diese Tabelle generiert wurde. Der Name des Typs ist `ServiceTypes.Table1`.

Überprüfen Sie die Zeile, der festlegt, zum Kennenlernen wie die Programmiersprache f# Abfragen in SQL-Abfragen interpretiert, die `Log` Eigenschaft auf den Datenkontext.

Fügen Sie den folgenden Code, um die Typen erstellt, indem die Typanbieter weiter zu erkunden.

```fsharp
let table1 = db.Table1
```

Zeigen Sie auf `table1` , dessen Typ finden Sie unter. Der Typ ist `System.Data.Linq.Table<dbSchema.ServiceTypes.Table1>` und das generische Argument impliziert, dass der Datentyp jeder Zeile den generierten Typ `dbSchema.ServiceTypes.Table1`. Der Compiler erstellt einen ähnlichen Typ für jede Tabelle in der Datenbank.

## <a name="querying-the-data"></a>Abfragen der Daten
In diesem Schritt schreiben Sie eine Abfrage mithilfe von f#-Abfrageausdrücke.


#### <a name="to-query-the-data"></a>So fragen Sie Daten ab

1. Nun erstellen Sie eine Abfrage für diese Tabelle in der Datenbank. Fügen Sie den folgenden Code hinzu.

  ```fsharp
   let query1 =
     query {
       for row in db.Table1 do
       select row
     }
   query1 |> Seq.iter (fun row -> printfn "%s %d" row.Name row.TestData1)
```

  Die Darstellung des Worts `query` gibt an, dass dies ein Abfrageausdruck den Wert, einen Typ von Ausdruck für die Berechnung, die eine Auflistung von einer typischen Datenbankabfrage ähnliche Ergebnisse generiert. Wenn Sie auf Abfrage zeigen, sehen Sie, dass er eine Instanz des [Linq.QueryBuilder-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.querybuilder-class-%5bfsharp%5d), ein Typ, der abfrageberechnungsausdruck definiert. Wenn Sie zeigen `query1`, sehen Sie, dass er eine Instanz des `System.Linq.IQueryable`. Wie der Name bereits vermuten lässt, `System.Linq.IQueryable` Daten, die abgefragt werden können, nicht das Ergebnis einer Abfrage darstellt. Eine Abfrage wird verzögert ausgewertet, welche darauf hin, dass die Datenbank nur abgefragt, wenn die Abfrage ausgewertet wird. Die letzte Zeile übergibt die Abfrage über `Seq.iter`. Abfragen werden aufzählbare und wie Sequenzen durchlaufen werden können. Weitere Informationen finden Sie unter [Abfrageausdrücke](../../language-reference/query-expressions.md).

2. Einen Abfrageoperator jetzt der Abfrage hinzufügen. Es gibt eine Anzahl von Abfrageoperatoren verfügbar, die Sie verwenden können, um komplexere Abfragen zu erstellen. Dieses Beispiel zeigt auch, können Sie die Abfragevariable vermeiden und stattdessen einen Pipeline-Operator verwenden.

  ```fsharp
   query {
     for row in db.Table1 do
     where (row.TestData1 > 2)
     select row
   } |> Seq.iter (fun row -> printfn "%d %s" row.TestData1 row.Name)
```

3. Fügen Sie eine komplexere Abfrage mit einem Join von zwei Tabellen hinzu.

  ```fsharp
   query {
     for row1 in db.Table1 do
     join row2 in db.Table2 on (row1.Id = row2.Id)
     select (row1, row2)
   } |> Seq.iteri (fun index (row1, row2) ->
                   if (index = 0) then printfn "Table1.Id TestData1 TestData2 Name Table2.Id TestData1 TestData2 Name"
                   printfn "%d %d %f %s %d %d %f %s" row1.Id row1.TestData1 row1.TestData2 row1.Name
                     row2.Id (row2.TestData1.GetValueOrDefault()) (row2.TestData2.GetValueOrDefault()) row2.Name)
```

4. In realen Code werden die Parameter in der Abfrage in der Regel Werte oder Variablen, Konstanten nicht kompilieren. Fügen Sie den folgenden Code, der eine Abfrage in einer Funktion umschließt, die einen Parameter und ruft dann die Funktion mit dem Wert 10, ein.

  ```fsharp
   let findData param =
     query {
       for row in db.Table1 do
       where (row.TestData1 = param)
       select row
     }

   findData 10 |> Seq.iter (fun row -> printfn "Found row: %d %d %f %s" row.Id row.TestData1 row.TestData2 row.Name)
```

## <a name="working-with-nullable-fields"></a>Arbeiten mit auf NULL festlegbare Felder
In Datenbanken Felder werden häufig null-Werte zulassen. Die normale numerische Datentypen kann nicht für Daten verwenden, die NULL-Werte zulässt, da diese Typen nicht die als ein möglicher Wert null, in das Typsystem von .NET. Aus diesem Grund werden diese Werte von Instanzen dargestellt `System.Nullable` Typ. Anstatt auf den Wert der Suchfelder direkt mit dem Namen des Felds zuzugreifen, müssen Sie einige zusätzliche Schritte hinzufügen. Sie können die `System.Nullable.Value` Eigenschaft Zugriff auf den zugrunde liegenden Wert eines Typs mit NULL-Werte zulässt. Die `System.Nullable.Value` -Eigenschaft löst eine Ausnahme aus, wenn das Objekt anstatt einen Wert null ist. Können Sie die `System.Nullable.HasValue` boolesche Methode, um zu bestimmen, ob ein Wert vorhanden ist, oder verwenden Sie `System.Nullable.GetValueOrDefault()` sorgen, dass Sie einen tatsächlichen Wert in allen Fällen. Bei Verwendung von `System.Nullable.GetValueOrDefault()` ein NULL-Wert in der Datenbank vorhanden ist, und sie wird ersetzt zeigen Sie mit einem Wert wie eine leere Zeichenfolge für Zeichenfolgentypen, 0 für ganzzahlige Typen oder 0,0 für veränderliche Typen.

Wenn Sie Gleichheitstests oder Vergleiche auf Werten in ausgeführt werden müssen eine `where` -Klausel in einer Abfrage können Sie NULL-Werte zu Operatoren in der [Linq.NullableOperators-Modul](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d). Diese Verhalten sich wie die reguläre Vergleichsoperatoren `=`, `>`, `<=`usw., außer dass ein Fragezeichen angezeigt, auf die links oder rechts vom Operator, in denen die NULL-Werte sind. Z. B. den Operator `>?` ist ein größer-als-Operator mit einem NULL-Werte auf der rechten Seite. Die Möglichkeit, die diese Operatoren funktionieren wird, wenn die beiden Seiten des Ausdrucks null ist, der ausgewertete Ausdruck `false`. In einem `where` -Klausel, dies im Allgemeinen bedeutet, dass die Zeilen, die mindestens ein Feld enthalten nicht aktiviert und nicht in den Abfrageergebnissen zurückgegeben werden.


#### <a name="to-work-with-nullable-fields"></a>Zur Bearbeitung auf NULL festlegbare Felder

Im folgenden Codebeispiel wird das Arbeiten mit NULL-Werte; Angenommen, **TestData1** ist ein Ganzzahlfeld, die NULL-Werte zulässt.

```fsharp
query {
  for row in db.Table2 do
  where (row.TestData1.HasValue && row.TestData1.Value > 2)
  select row
} |> Seq.iter (fun row -> printfn "%d %s" row.TestData1.Value row.Name)

query {
  for row in db.Table2 do
  // Use a nullable operator ?>
  where (row.TestData1 ?> 2)
  select row
} |> Seq.iter (fun row -> printfn "%d %s" (row.TestData1.GetValueOrDefault()) row.Name)
```

## <a name="calling-a-stored-procedure"></a>Aufrufen einer gespeicherten Prozedur
Alle gespeicherten Prozeduren für die Datenbank können von f# aufgerufen werden. Müssen Sie den statischen Parameter festlegen `StoredProcedures` zu `true` in der Anbieter Typinstanziierung. Der vom Typanbieter `SqlDataConnection` enthält mehrere statische Methoden, die Sie verwenden können, um die Typen zu konfigurieren, die generiert werden. Eine vollständige Beschreibung dieser, finden Sie unter [SqlDataConnection-Typanbieter](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d). Eine Methode für den Datentyp der Kontext wird für jede gespeicherte Prozedur generiert.


#### <a name="to-call-a-stored-procedure"></a>So rufen Sie eine gespeicherte Prozedur auf

Wenn die gespeicherten Prozeduren mit Parametern, die NULL zulassen, müssen Sie eine entsprechende übergeben `System.Nullable` Wert. Der Rückgabewert einer gespeicherten Prozedur-Methode, die einen Skalarwert oder eine Tabelle zurückgibt `System.Data.Linq.ISingleResult`, enthält Eigenschaften, die Sie Zugriff auf die zurückgegebenen Daten zu ermöglichen. Das Typargument für `System.Data.Linq.ISingleResult` richtet sich nach dem bestimmten Verfahren und ist auch die Typen, die der vom Typanbieter generiert. Für eine gespeicherte Prozedur namens `Procedure1`, der Typ ist `Procedure1Result`. Der Typ `Procedure1Result` enthält die Namen der Spalten in einer zurückgegebenen Tabelle oder für eine gespeicherte Prozedur, die einen skalaren Wert zurückgibt, den Rückgabewert dar.

Im folgende Code wird davon ausgegangen, dass eine Prozedur `Procedure1` für die Datenbank, die zwei NULL-Werte zu ganzen Zahlen als Parameter annimmt, führt eine Abfrage, die eine Spalte mit dem Namen zurückgibt `TestData1`, und gibt eine ganze Zahl zurück.

```fsharp
type schema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;", StoredProcedures = true>

let testdb = schema.GetDataContext()

let nullable value = new System.Nullable<_>(value)

let callProcedure1 a b =
  let results = testdb.Procedure1(nullable a, nullable b)
  for result in results do
    printfn "%d" (result.TestData1.GetValueOrDefault())
  results.ReturnValue :?> int

printfn "Return Value: %d" (callProcedure1 10 20)
```

## <a name="updating-the-database"></a>Aktualisieren der Datenbank
Die LINQ-DataContext-Typs enthält Methoden, die zum Ausführen der transaktiven Datenbankupdates vollständig typisierte Weise mit den generierten Typen zu vereinfachen.


#### <a name="to-update-the-database"></a>So aktualisieren Sie die Datenbank

1. Im folgenden Code werden mehrere Zeilen in der Datenbank hinzugefügt. Wenn Sie nur eine Zeile hinzufügen, können Sie `System.Data.Linq.Table.InsertOnSubmit()` an die neue Zeile hinzufügen. Wenn Sie mehrere Zeilen einfügen, platzieren Sie sie in einer Auflistung, und rufen `System.Data.Linq.Table.InsertAllOnSubmit(System.Collections.Generic.IEnumerable)`. Wenn Sie eine der folgenden Methoden aufrufen, wird die Datenbank nicht sofort geändert. Rufen Sie `System.Data.Linq.DataContext.SubmitChanges` um die Änderungen zu übernehmen. Standardmäßig alles, was haben Sie vor dem Aufrufen `System.Data.Linq.DataContext.SubmitChanges` ist implizit Teil derselben Transaktion.

 ```fsharp
   let newRecord = new dbSchema.ServiceTypes.Table1(Id = 100,
                                                    TestData1 = 35, 
                                                    TestData2 = 2.0,
                                                    Name = "Testing123")

   let newValues =
     [ for i in [1 .. 10] ->
       new dbSchema.ServiceTypes.Table3(Id = 700 + i,
         Name = "Testing" + i.ToString(),
         Data = i) ]

   // Insert the new data into the database.
   db.Table1.InsertOnSubmit(newRecord)
   db.Table3.InsertAllOnSubmit(newValues)

   try
     db.DataContext.SubmitChanges()
     printfn "Successfully inserted new rows."
   with
   | exn -> printfn "Exception:\n%s" exn.Message
```

2. Bereinigen Sie nun die Zeilen ein, durch den Aufruf eines Löschvorgang an.

  ```fsharp
   // Now delete what was added.
   db.Table1.DeleteOnSubmit(newRecord)
   db.Table3.DeleteAllOnSubmit(newValues)

   try
     db.DataContext.SubmitChanges()
     printfn "Successfully deleted all pending rows."
   with
   | exn -> printfn "Exception:\n%s" exn.Message
```

## <a name="executing-transact-sql-code"></a>Ausführen von Transact-SQL-code
Sie können auch Transact-SQL angeben, direkt mithilfe der `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` Methode für die `DataContext` Klasse.


#### <a name="to-execute-custom-sql-commands"></a>Benutzerdefinierte SQL-Befehle ausführen

Der folgende Code zeigt, wie zum Senden von SQL-Befehlen, einen Datensatz in eine Tabelle einzufügen und einen Datensatz aus einer Tabelle zu löschen.

```fsharp
try
  db.DataContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (102, 'Testing', 55)") |> ignore
with
| exn -> printfn "Exception:\n%s" exn.Message

try //AND Name = 'Testing' AND Data = 55
  db.DataContext.ExecuteCommand("DELETE FROM Table3 WHERE Id = 102 ") |> ignore
with
| exn -> printfn "Exception:\n%s" exn.Message
```

## <a name="using-the-full-data-context"></a>Verwenden die vollständige Datenkontext
In den vorherigen Beispielen die `GetDataContext` Methode wurde verwendet, um den so genannten Abrufen der *vereinfachter Datenkontext* für das Datenbankschema. Der vereinfachte Datenkontext ist einfacher zu verwenden, wenn Sie Abfragen erstellen, da nicht so viele Elemente vorhanden sind. Wenn Sie die Eigenschaften in IntelliSense durchsuchen, können Sie daher auf die Datenbankstruktur, z. B. Tabellen und gespeicherten Prozeduren konzentrieren. Es ist jedoch ein Limit, was Sie, mit der vereinfachte Datenkontext tun können. Eine vollständige Datenkontext, der die Möglichkeit bietet, die andere Aktionen ausführen. ist auch verfügbar befindet sich diese die `ServiceTypes` und den Namen der *DataContext* statischen Parameter, wenn Sie diese Option angegeben. Wenn sie nicht bereitgestellt, wird der Name des Datentyps Kontext für Sie von SqlMetal.exe basierend auf der anderen Eingabe generiert. Vollständige Datenkontext erbt von `System.Data.Linq.DataContext` und macht die Member der Basisklasse, einschließlich von Verweisen auf ADO.NET-Datentypen wie z. B. die `Connection` -Objekt, Methoden, z. B. `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` und `System.Data.Linq.DataContext.ExecuteQuery(System.String,System.Object[])` , Sie verwenden können, Schreiben von Abfragen in SQL und auch eine Möglichkeit zum Arbeiten mit Transaktionen explizit.


#### <a name="to-use-the-full-data-context"></a>Verwenden Sie die vollständige Datenkontext

Der folgende Code zeigt ein Kontextobjekt für die gesamten Daten abrufen und verwenden, um Befehle direkt für die Datenbank auszuführen. In diesem Fall werden zwei Befehle als Teil der gleichen Transaktion ausgeführt.

```fsharp
let dbConnection = testdb.Connection
let fullContext = new dbSchema.ServiceTypes.MyDatabase(dbConnection)

dbConnection.Open()

let transaction = dbConnection.BeginTransaction()
fullContext.Transaction <- transaction

try
  let result1 = fullContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (102, 'A', 55)")
  printfn "ExecuteCommand Result: %d" result1
  let result2 = fullContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (103, 'B', -2)")
  printfn "ExecuteCommand Result: %d" result2
  if (result1 <> 1 || result2 <> 1) then
    transaction.Rollback()
    printfn "Rolled back creation of two new rows."
  else
    transaction.Commit()
  printfn "Successfully committed two new rows."
with
| exn ->
  transaction.Rollback()
  printfn "Rolled back creation of two new rows due to exception:\n%s" exn.Message

dbConnection.Close()
```

## <a name="deleting-data"></a>Löschen von Daten
Dieser Schritt wird gezeigt, wie Sie Zeilen aus einer Tabelle löschen.


#### <a name="to-delete-rows-from-the-database"></a>So löschen Sie Zeilen aus der Datenbank

Nun Bereinigen einer durch Schreiben einer Funktion, die Zeilen aus einer angegebenen Tabelle, eine Instanz von löscht Zeilen hinzugefügt der `System.Data.Linq.Table` Klasse. Klicken Sie dann schreiben Sie eine Abfrage aus, um alle Zeilen suchen, die Sie löschen möchten, und übergeben Sie die Ergebnisse der Abfrage in der `deleteRows` Funktion. Dieser Code nutzt die Fähigkeit, teilweise Anwendung von Funktionsargumenten bereitzustellen.

```fsharp
let deleteRowsFrom (table:Table<_>) rows =
  table.DeleteAllOnSubmit(rows)

query {
  for rows in db.Table3 do
  where (rows.Id > 10)
  select rows
} |> deleteRowsFrom db.Table3

db.DataContext.SubmitChanges()
printfn "Successfully deleted rows with Id greater than 10 in Table3."
```

## <a name="creating-a-test-database"></a>Erstellen eine Testdatenbank
In diesem Abschnitt wird gezeigt, wie die Testdatenbank einrichten, um in dieser exemplarischen Vorgehensweise verwenden.

Beachten Sie, dass wenn Sie die Datenbank auf irgendeine Weise ändern, Sie den Typanbieter zurücksetzen müssen. Um den Typanbieter zurückzusetzen, neu erstellen Sie oder bereinigen Sie das Projekt, das die zuvor erstellte Anbieter enthält.


#### <a name="to-create-the-test-database"></a>Die Testdatenbank erstellen

1. In **Server-Explorer**, öffnen Sie das Kontextmenü für die **Datenverbindungen** Knoten, und wählen Sie **Verbindung hinzufügen**. Die **Verbindung hinzufügen** Dialogfeld wird angezeigt.

2. In der **Servernamen** Feld, geben Sie den Namen einer Instanz von SQL Server, die Sie administrativen Zugriff haben oder wenn Sie keinen Zugriff auf einen Server angeben (localdb\v11. 0). SQL Express LocalDB stellt einen einfachen Datenbankserver für Entwicklung und Tests auf dem Computer an. Erstellt ein neuer Knoten im **Server-Explorer** unter **Datenverbindungen**. Weitere Informationen zu LocalDB, finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer lokalen Datenbankdatei in Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).

3. Öffnen Sie das Kontextmenü für den neuen Verbindungsknoten, und wählen Sie **neue Abfrage**.

4. Kopieren Sie das folgende SQL-Skript, fügen Sie ihn in den Abfrage-Editor, und wählen Sie dann die **Execute** Schaltfläche auf der Symbolleiste, oder wählen Sie die Tastenkombination STRG + UMSCHALT + E.

```sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO

USE [master];
GO

IF EXISTS (SELECT * FROM sys.databases WHERE name = 'MyDatabase')
  DROP DATABASE MyDatabase;
GO

-- Create the MyDatabase database.
CREATE DATABASE MyDatabase;
GO

-- Specify a simple recovery model 
-- to keep the log growth to a minimum.
ALTER DATABASE MyDatabase 
SET RECOVERY SIMPLE;
GO

USE MyDatabase;
GO

-- Create the Table1 table.
CREATE TABLE [dbo].[Table1] (
  [Id]        INT        NOT NULL,
  [TestData1] INT        NOT NULL,
  [TestData2] FLOAT (53) NOT NULL,
  [Name]      NTEXT      NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
);

-- Create the Table2 table.
CREATE TABLE [dbo].[Table2] (
  [Id]        INT        NOT NULL,
  [TestData1] INT        NULL,
  [TestData2] FLOAT (53) NULL,
  [Name]      NTEXT      NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
);


-- Create the Table3 table.
CREATE TABLE [dbo].[Table3] (
  [Id]   INT           NOT NULL,
  [Name] NVARCHAR (50) NOT NULL,
  [Data] INT           NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
  );
GO

CREATE PROCEDURE [dbo].[Procedure1]
  @param1 int = 0,
  @param2 int
AS
SELECT TestData1 FROM Table1
RETURN 0
GO

USE MyDatabase

-- Insert data into the Table1 table.
INSERT INTO Table1 (Id, TestData1, TestData2, Name)
  VALUES(1, 10, 5.5, 'Testing1');
INSERT INTO Table1 (Id, TestData1, TestData2, Name)
  VALUES(2, 20, -1.2, 'Testing2');

-- Insert data into the Table2 table.
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(1, 10, 5.5, 'Testing1');
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(2, 20, -1.2, 'Testing2');
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(3, NULL, NULL, 'Testing3');

-- Insert data into the Table3 table.
INSERT INTO Table3 (Id, Name, Data)
  VALUES (1, 'Testing1', 10);
INSERT INTO Table3 (Id, Name, Data)
  VALUES (2, 'Testing2', 100);
```


## <a name="see-also"></a>Siehe auch
[Typanbieter](index.md)

[SqlDataConnection-Typanbieter](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d)

[Exemplarische Vorgehensweise: Generieren von f#-Typen aus einer DBML-Datei](generating-fsharp-types-from-dbml.md)

[Abfrageausdrücke](../../language-reference/query-expressions.md)

[LINQ to SQL](https://msdn.microsoft.com/library/bb386976)

[SqlMetal.exe &#40; Tool zur Codegenerierung &#41;](https://msdn.microsoft.com/library/bb386987)
