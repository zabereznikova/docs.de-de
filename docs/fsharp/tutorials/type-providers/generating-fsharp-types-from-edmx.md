---
title: 'Exemplarische Vorgehensweise: Generieren von F#-Typen aus einer EDMX-Schemadatei (F#)'
description: "Informationen Sie zum Erstellen von f#-Typen für Daten, dargestellt durch das Entity Data Model (EDM) in f# 3.0, wobei das Schema in einer EDMX-Datei angegeben ist."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 81adb2eb-625f-4ad8-aeaa-8f672a6d79a2
ms.openlocfilehash: 1df0344e8dab2b40d82d1b9c61ccd2f026906243
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2017
---
# <a name="walkthrough-generating-f-types-from-an-edmx-schema-file"></a>Exemplarische Vorgehensweise: Generieren von F#-Typen aus einer EDMX-Schemadatei

> [!NOTE]
Dieses Handbuch wurde für f# 3.0 geschrieben und wird aktualisiert.  Unter [FSharp.Data](http://fsharp.github.io/FSharp.Data/) finden Sie aktuelle plattformübergeifende Typanbieter.

> [!NOTE]
Die API-Referenz Links gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

In dieser exemplarischen Vorgehensweise für F# 3.0 wird gezeigt, wie Sie Typen für Daten erstellen, die vom Entity Data Model (EDM) dargestellt werden. Dessen Schema wird in einer EDMX-Datei angegeben. In dieser exemplarischen Vorgehensweise wird außerdem gezeigt, wie Sie den EdmxFile-Typanbieter verwenden. Bevor Sie beginnen, sollten Sie überlegen, ob ein SqlEntityConnection-Typanbieter eine besser geeignete Option ist. Der SqlEntityConnection-Typanbieter eignet sich sehr gut für Szenarien, in denen Sie in der Entwicklungsphase des Projekts eine Verbindung mit einer aktiven Datenbank herstellen können, wobei es Ihnen nichts ausmacht, zur Kompilierzeit die Verbindungszeichenfolge anzugeben. Diese Typanbieter weist jedoch die Einschränkung auf, dass er geringere Datenbankfunktionen als der EdmxFile-Typanbieter verfügbar macht. Wenn keine aktive Datenbankverbindung für ein Datenbankprojekt vorhanden ist, das das Entity Data Model verwendet, können Sie die EDMX-Datei zum Codieren für die Datenbank verwenden. Wenn Sie den EdmxFile-Typanbieter verwenden, führt der F#-Compiler EdmGen.exe aus, um die vom Typanbieter bereitgestellten Typen zu generieren.

Diese exemplarische Vorgehensweise veranschaulicht die folgenden Aufgaben, die Sie in der angegebenen Reihenfolge ausführen müssen, um die exemplarische Vorgehensweise erfolgreich abzuschließen:


- Erstellen einer EDMX-Datei
<br />

- Erstellen des Projekts
<br />

- Suchen oder Erstellen der Entity Data Model-Verbindungszeichenfolge
<br />

- Konfigurieren des Typanbieters
<br />

- Abfragen der Daten
<br />

- Aufrufen einer gespeicherten Prozedur
<br />


## <a name="prerequisites"></a>Erforderliche Komponenten

## <a name="creating-an-edmx-file"></a>Erstellen einer EDMX-Datei
Wenn Sie bereits über eine EDMX-Datei verfügen, können Sie diesen Schritt überspringen.


#### <a name="to-create-an-edmx-file"></a>So erstellen Sie eine EDMX-Datei

- Wenn Sie eine EDMX-Datei noch nicht haben, können Sie den Anweisungen am Ende dieser exemplarischen Vorgehensweise im Schritt [konfigurieren das Entity Data Model](generating-fsharp-types-from-edmx.md#configuring-the-entity-data-model).
<br />

## <a name="creating-the-project"></a>Erstellen des Projekts
In diesem Schritt erstellen Sie ein Projekt und fügen die entsprechenden Verweise hinzu, um den EDMX-Typanbieter zu verwenden.


#### <a name="to-create-and-set-up-an-f-project"></a>So erstellen und richten Sie ein F#-Projekt ein

1. Schließen Sie das vorherige Projekt und erstellen Sie ein neues Projekt mit dem Namen SchoolEDM.
<br />

2. In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für **Verweise**, und wählen Sie dann **Verweis hinzufügen**.
<br />

3. In der **Assemblys** Bereich, wählen Sie die **Framework** Knoten.
<br />

4. Wählen Sie in der Liste der verfügbaren Assemblys, die **System.Data.Entity** und **System.Data.Linq** Assemblys, und wählen Sie dann die **hinzufügen** Hinzufügen von Verweisen auf diese Schaltfläche die Assemblys dem Projekt.
<br />

5. In der **Assemblys** wählen Sie im Bereich der **Erweiterungen** Knoten.
<br />

6. In der Liste der verfügbaren Erweiterungen fügen Sie einen Verweis auf die Assembly FSharp.Data.TypeProviders hinzu.
<br />

7. Fügen Sie den folgenden Code hinzu, um die entsprechende Namespaces zu öffnen.
<br />

```fsharp
open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

## <a name="finding-or-creating-the-connection-string-for-the-entity-data-model"></a>Suchen oder Erstellen der Verbindungszeichenfolge für das Entity Data Model
Die Verbindungszeichenfolge für das Entity Data Model (EDMX-Verbindungszeichenfolge) enthält nicht nur die Verbindungszeichenfolge für den Datenbankanbieter, sondern auch zusätzliche Informationen. Beispielsweise kann eine EDMX-Verbindungszeichenfolge für eine einfache SQL Server-Datenbank wie folgt lauten.

```fsharp
let edmConnectionString = "metadata=res://*/;provider=System.Data.SqlClient;Provider Connection String='Server=SERVER\Instance;Initial Catalog=DatabaseName;Integrated Security=SSPI;'"
```

Weitere Informationen zu EDMX-Verbindungszeichenfolgen finden Sie unter [Verbindungszeichenfolgen](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).


#### <a name="to-find-or-create-the-connection-string-for-the-entity-data-model"></a>Suchen oder Erstellen der Verbindungszeichenfolge für das Entity Data Model

1. EDMX-Verbindungszeichenfolgen können manuell schwer zu erstellen sein, sodass Sie Zeit sparen, wenn Sie sie programmgesteuert generieren. Wenn Sie Ihre EDMX-Verbindungszeichenfolge kennen, können Sie diesen Schritt überspringen und die Verbindungszeichenfolge einfach im nächsten Schritt verwenden. Verwenden Sie andernfalls den folgenden Code, um die EDMX-Verbindungszeichenfolge aus einer Datenbankverbindungszeichenfolge zu generieren, die Sie bereitstellen.
<br />

```fsharp
open System
open System.Data
open System.Data.SqlClient
open System.Data.EntityClient
open System.Data.Metadata.Edm

let getEDMConnection(dbConnectionString) =
  let dbConnection = new SqlConnection(dbConnectionString)
  let resourceArray = [| "res://*/" |]
  let assemblyList = [| System.Reflection.Assembly.GetCallingAssembly() |]
  let metaData = MetadataWorkspace(resourceArray, assemblyList)
  new EntityConnection(metaData, dbConnection)
```

## <a name="configuring-the-type-provider"></a>Konfigurieren des Typanbieters
In diesem Schritt erstellen und konfigurieren Sie den Typanbieter mit der EDMX-Verbindungszeichenfolge, und Sie generieren Typen für das Schema, das in der EDMX-Datei definiert ist.


#### <a name="to-configure-the-type-provider-and-generate-types"></a>So konfigurieren Sie den Typanbieter und generieren Typen

1. Kopieren Sie die EDMX-Datei, die Sie im ersten Schritt dieser exemplarischen Vorgehensweise generiert haben, in den Projektordner.
<br />

2. Öffnen Sie im Kontextmenü für den Projektknoten in Ihrem F#-Projekt, wählen Sie **vorhandenes Element hinzufügen**, und wählen Sie dann die EDMX-Datei dem Projekt hinzugefügt.
<br />

3. Geben Sie den folgenden Code ein, um den Typanbieter für die EDMX-Datei zu aktivieren. Ersetzen Sie *Server*\*Instanz * durch den Namen des Servers, auf dem SQL Server und den Namen Ihrer Instanz ausgeführt wird, und verwenden Sie den Namen der EDMX-Datei aus dem ersten Schritt in dieser exemplarischen Vorgehensweise.
<br />

```fsharp
type edmx = EdmxFile<"Model1.edmx", ResolutionFolder = @"<path-tofolder-that-containsyour.edmx-file>">

use edmConnection =
  getEDMConnection("Data Source=SERVER\instance;Initial Catalog=School;Integrated Security=true;")
use context = new edmx.SchoolModel.SchoolEntities(edmConnection)
```

## <a name="querying-the-data"></a>Abfragen der Daten
In diesem Schritt verwenden Sie F#-Abfrageausdrücke, um die Datenbank abzufragen.


#### <a name="to-query-the-data"></a>So fragen Sie Daten ab

- Geben Sie den folgenden Code ein, um die Daten im Entity Data Model abzufragen.
<br />

```fsharp
query { 
  for course in context.Courses do
  select course 
} |> Seq.iter (fun course -> printfn "%s" course.Title)

query { 
  for person in context.Person do
  select person 
} |> Seq.iter (fun person -> printfn "%s %s" person.FirstName person.LastName)

// Add a where clause to filter results
query { 
  for course in context.Courses do
  where (course.DepartmentID = 1)
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

// Join two tables
query { 
  for course in context.Courses do
  join dept in context.Departments on (course.DepartmentID = dept.DepartmentID)
  select (course, dept.Name) 
} |> Seq.iter (fun (course, deptName) -> printfn "%s %s" course.Title deptName)
```

## <a name="calling-a-stored-procedure"></a>Aufrufen einer gespeicherten Prozedur
Sie können gespeicherte Prozeduren aufrufen, indem Sie den EDMX-Typanbieter verwenden. In der folgenden Prozedur enthält die Datenbank School eine gespeicherte Prozedur **UpdatePerson**, die einen Datensatz aktualisiert, wenn neue Werte für die Spalten. Sie können diese gespeicherte Prozedur verwenden, da sie als Methode des DataContext-Typs verfügbar gemacht ist.


#### <a name="to-call-a-stored-procedure"></a>So rufen Sie eine gespeicherte Prozedur auf

- Fügen Sie folgenden Code hinzu, um Datensätze zu aktualisieren.
<br />

```fsharp
// Call a stored procedure.
let nullable value = new System.Nullable<_>(value)

// Assume now that you must correct someone's hire date.
// Throw an exception if more than one matching person is found.
let changeHireDate(lastName, firstName, hireDate) =

  query { 
    for person in context.People do
    where (person.LastName = lastName &&
           person.FirstName = firstName)
    exactlyOne 
  } |> (fun person ->
            context.UpdatePerson(nullable person.PersonID, person.LastName, person.FirstName, nullable hireDate, person.EnrollmentDate))

changeHireDate("Abercrombie", "Kim", DateTime.Parse("1/12/1998"))
|> printfn "Result: %d"
```

Bei erfolgreicher Ausführung lautet das Ergebnis 1. Beachten Sie, dass **ExactlyOne** im Abfrageausdruck verwendet werden, um sicherzustellen, dass nur ein Ergebnis zurückgegeben, andernfalls, eine Ausnahme ausgelöst wird. Darüber hinaus um einfacher mit Werten zu arbeiten, können Sie die einfache **NULL-Werte zulassen** -Funktion, die in diesem Code erstellen Sie einen NULL-Werte zulassen Wandelt einen normalen Wert definiert ist.

<br />

## <a name="configuring-the-entity-data-model"></a>Konfigurieren des Entity Data Model
Dieses Verfahren ist nur erforderlich, wenn Sie wissen möchten, wie ein vollständiges Entity Data Model aus einer Datenbank generiert wird und Sie dafür keine Testdatenbank besitzen.


#### <a name="to-configure-the-entity-data-model"></a>So konfigurieren Sie das Entity Data Model

1. Wählen Sie in der Menüleiste **SQL**, **Transact-SQL-Editor**, **neue Abfrage** zum Erstellen einer Datenbank. Wenn Sie dazu aufgefordert werden, geben Sie Ihren Datenbankserver und die Datenbankinstanz an.
<br />

2. Kopieren Sie den Inhalt des Datenbankskripts, der die Datenbank Student erstellt wie beschrieben in der [Dokumentation zu Entity Framework](http://msdn.microsoft.com/data/JJ614587.aspx) im Data Developer Center.
<br />

3. Führen Sie das SQL-Skript, durch Auswählen der Symbolleisten-Schaltfläche mit dem Triangle-Symbol, oder wählen die Tastenkombination STRG + Q.
<br />

4. In **Server-Explorer**, öffnen Sie das Kontextmenü für **Datenverbindungen**, wählen Sie **Verbindung hinzufügen**, und geben Sie dann den Namen des Datenbankservers, den Namen der Instanz , und die Datenbank "School".
<br />

5. Erstellen Sie ein C#- oder Visual Basic-Konsolenanwendung-Projekt, öffnen Sie das Kontextmenü, wählen Sie **neues Element hinzufügen**, und wählen Sie dann **ADO.NET Entity Data Model**.
<br />  Der Assistent für Entity Data Model wird geöffnet. Mit diesem Assistenten können Sie auswählen, wie Sie das Entity Data Model erstellen möchten.
<br />

6. Klicken Sie unter **Modellinhalte**, wählen die **aus Datenbank generieren** Kontrollkästchen.
<br />

7. Auf der nächsten Seite wählen Sie als Datenverbindung die neu erstellte Datenbank School aus.
<br />  Diese Verbindung entspricht in etwa  **&lt;Servername&gt;.&lt; InstanceName&gt;. School.dbo**.
<br />

8. Kopieren Sie die Entitätsverbindungszeichenfolge in die Zwischenablage, da sie später wichtig sein kann.
<br />

9. Vergewissern Sie sich dieses Kontrollkästchen, um die Entität-Verbindungszeichenfolge zum Speichern der **"App.config"** Datei ausgewählt ist, und notieren Sie sich den Zeichenfolgenwert in das Textfeld mit dem Sie später, suchen Sie die Verbindungszeichenfolge bei Bedarf.
<br />

10. Wählen Sie in der nächsten Seite **Tabellen** und **gespeicherten Prozeduren und Funktionen**.
<br />  Durch Auswahl dieser Knoten der obersten Ebene wählen Sie alle Tabellen, gespeicherten Prozeduren und Funktionen aus. Sie können diese auch einzeln auswählen.
<br />

11. Stellen Sie sicher, dass die Kontrollkästchen für die anderen Einstellungen aktiviert sind.
<br />  Die erste **in den Singular oder Plural setzen generierte Objektnamen** Kontrollkästchen gibt an, ob Singularformen plural entsprechend Konventionen Benennen von Objekten, die Datenbanktabellen darstellen. Die **Fremdschlüsselspalten in das Modell einbeziehen** Kontrollkästchen bestimmt, ob Felder eingeschlossen werden für die dient zum Verknüpfen mit anderer Felder in der Objekttypen, die für das Schema der Datenbank generiert werden sollen. Das dritte Kontrollkästchen gibt an, ob gespeicherte Prozeduren und Funktionen in das Modell eingeschlossen werden sollen.
<br />

12. Wählen Sie die **Fertig stellen** Schaltfläche, um eine EDMX-Datei zu generieren, die ein Entity Data Model enthält, die auf die Datenbank "School" basiert.
<br />  Eine Datei **Model1.edmx**, wird dem Projekt hinzugefügt und ein Datenbankdiagramm wird angezeigt.
<br />

13. Wählen Sie in der Menüleiste **Ansicht**, **Weitere Fenster**, **Entity Data Model-Browser** können Sie alle Details des Modells anzeigen oder **Entity Data Model-Mappingdetails**  um ein Fenster zu öffnen, wird die Zuordnung des generierten Objektmodells Datenbanktabellen und-Spalten.
<br />


## <a name="next-steps"></a>Nächste Schritte
Untersuchen von anderen Abfragen anhand der verfügbaren Abfrageoperatoren gemäß [Abfrageausdrücke](../../language-reference/query-expressions.md).


## <a name="see-also"></a>Siehe auch
[Typanbieter](index.md)

[EdmxFile-Typanbieter](https://msdn.microsoft.com/visualfsharpdocs/conceptual/edmxfile-type-provider-%5bfsharp%5d)

[Exemplarische Vorgehensweise: Zugreifen auf eine SQL-Datenbank mithilfe von Typanbietern und Entitäten](accessing-a-sql-database-entities.md)

[Entity Framework](http://msdn.microsoft.com/data/ef)

[Übersicht über die EDMX-Datei](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)

[EDM-Generator &#40; EdmGen.exe &#41;](https://msdn.microsoft.com/library/bb387165)

