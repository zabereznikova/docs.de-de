---
title: "Exemplarische Vorgehensweise: Zugreifen auf eine SQL-Datenbank mithilfe von Typanbietern und Entitäten (F#)"
description: "Weitere Informationen Sie zum Zugreifen auf typisierte Daten für eine SQL­Datenbank basierend auf dem ADO.NET Entity Data Model in f# 3.0."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: dc82a932-5401-4d19-9fb3-92c50d8db514
ms.openlocfilehash: e0e78e06fa1129ba5eeb73bc36c14343c93d6927
ms.sourcegitcommit: e2bf8e6bc365bd9a0e86fe81eeae7d14f85f48c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2018
---
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers-and-entities"></a>Exemplarische Vorgehensweise: Zugreifen auf eine SQL-Datenbank mithilfe von Typanbietern und Entitäten

> [!NOTE]
Dieses Handbuch wurde für f# 3.0 geschrieben und wird aktualisiert.  Unter [FSharp.Data](http://fsharp.github.io/FSharp.Data/) finden Sie aktuelle plattformübergeifende Typanbieter.

> [!NOTE]
Die API-Referenz Links gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

In dieser exemplarischen Vorgehensweise für F# 3.0 wird gezeigt, wie Sie auf typisierte Daten einer SQL-Datenbank zugreifen, die auf dem ADO.NET Entity Data Model basiert. In der exemplarischen Vorgehensweise wird erläutert, wie Sie den F#-Typanbieter `SqlEntityConnection` zur Verwendung mit einer SQL-Datenbank einrichten, wie Sie Datenabfragen schreiben, gespeicherte Prozeduren in der Datenbank aufrufen und wie einige der ADO.NET Entity Framework-Typen und -Methoden verwendet werden, um die Datenbank zu aktualisieren.

Die exemplarische Vorgehensweise veranschaulicht die folgenden Aufgaben, die Sie in der angegebenen Reihenfolge ausführen müssen, um die exemplarische Vorgehensweise erfolgreich abzuschließen:


- Erstellen der Datenbank "School".
<br />

- Erstellen und Konfigurieren eines F#-Projekts
<br />

- Konfigurieren des typanbieters und Verbinden mit dem Entity Data Model
<br />

- Die Datenbank Abfragen
<br />

- Aktualisieren der Datenbank
<br />


## <a name="prerequisites"></a>Erforderliche Komponenten
Zum Abschließen dieser Schritte benötigen Sie Zugriff auf einen SQL Server, auf dem Sie eine Datenbank erstellen können.

## <a name="create-the-school-database"></a>Erstellen der Datenbank "School".
Sie können die Datenbank School auf jedem Server erstellen, auf dem SQL Server ausgeführt wird und auf den Sie administrativen Zugriff haben, oder Sie können LocalDB verwenden.


#### <a name="to-create-the-school-database"></a>So erstellen Sie die Datenbank School

1. In **Server-Explorer**, öffnen Sie das Kontextmenü für die **Datenverbindungen** Knoten, und wählen Sie dann **Verbindung hinzufügen**.
<br />  Die **Verbindung hinzufügen** Dialogfeld wird angezeigt.
<br />

2. In der **Servernamen** Feld, geben Sie den Namen einer Instanz von SQL Server, auf die Sie Administratorzugriff haben, oder (localdb\v11. 0) angeben, wenn Sie keinen Zugriff auf einen Server haben.
<br />  SQL Server Express LocalDB stellt einen einfachen Datenbankserver für Entwicklung und Tests auf dem Computer bereit. Weitere Informationen zu LocalDB, finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer lokalen Datenbankdatei in Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).
<br />  Erstellt ein neuer Knoten im **Server-Explorer** unter **Datenverbindungen**.
<br />

3. Öffnen Sie das Kontextmenü für den neuen Verbindungsknoten, und wählen Sie dann **neue Abfrage**.
<br />

4. Open [Erstellen der Beispieldatenbank "School"](https://msdn.microsoft.com/library/bb399731(v=vs.100).aspx) auf der Microsoft-Website, und klicken Sie dann kopieren und Einfügen Datenbankskripts, erstellt die Datenbank "School" in das Editorfenster ein.
<br />


## <a name="BKMK_CreateConfigFSProj"> </a>

## <a name="create-and-configure-an-f-project"></a>Erstellen und Konfigurieren eines F#-Projekts
In diesem Schritt erstellen Sie ein Projekt, das einen Typanbieter verwendet.


#### <a name="to-create-and-configure-an-f-project"></a>So erstellen und konfigurieren Sie ein F#-Projekt

1. Schließen Sie das vorherige Projekt, erstellen Sie ein anderes Projekt, und nennen sie **SchoolEDM**.
<br />

2. In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für **Verweise**, und wählen Sie dann **Verweis hinzufügen**.
<br />

3. Wählen Sie die **Framework** Knoten, und klicken Sie dann in der **Framework** wählen Sie **"System.Data"**, **System.Data.Entity**, und **System.Data.Linq**.
<br />

4. Wählen Sie die **Erweiterungen** Knoten, fügen einen Verweis auf die [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3) Assembly, und wählen Sie dann die **OK** Schaltfläche, um das Dialogfeld zu schließen.
<br />

5. Fügen Sie den folgenden Code hinzu, um ein internes Modul zu definieren und entsprechende Namespaces zu öffnen. Der Typanbieter kann Typen nur in einen privaten oder einen internen Namespace einfügen.
<br />

```fsharp
module internal SchoolEDM

open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

6. Um den Code in dieser exemplarischen Vorgehensweise interaktiv als Skript und nicht als kompiliertes Programm auszuführen, öffnen Sie das Kontextmenü für den Projektknoten, wählen Sie **neues Element hinzufügen**, fügen Sie ein f#-Skriptdatei hinzu, und fügen Sie den Code in den einzelnen Schritten, um das Skript. Zum Laden der Assemblyverweise müssen Sie die folgenden Zeilen hinzufügen.
<br />

```fsharp
#r "System.Data.Entity.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

7. Heben Sie jeden Codeblock beim Hinzufügen hervor und wählen Sie die Tasten ALT+EINGABE, um ihn in F# Interactive auszuführen.
<br />

## <a name="configure-the-type-provider-and-connect-to-the-entity-data-model"></a>Konfigurieren des Typanbieters und Verbinden mit dem Entity Data Model
In diesem Schritt richten Sie einen Typanbieter mit einer Datenverbindung ein und erhalten einen Datenkontext, der Ihnen die Arbeit mit Daten ermöglicht.


#### <a name="to-configure-the-type-provider-and-connect-to-the-entity-data-model"></a>So konfigurieren Sie den Typanbieter und stellen eine Verbindung mit dem Entity Data Model her

1. Geben Sie den folgenden Code ein, um den `SqlEntityConnection`-Typanbieter zu konfigurieren, der F#-Typen basierend auf dem zuvor erstellten Entity Data Model generiert. Verwenden Sie anstelle der vollständigen EDMX-Verbindungszeichenfolge nur die SQL-Verbindungszeichenfolge.
<br />

```fsharp
type private EntityConnection = SqlEntityConnection<ConnectionString="Server=SERVER\InstanceName;Initial Catalog=School;Integrated Security=SSPI;MultipleActiveResultSets=true",Pluralize = true>
```

  Mit diesem Vorgang wird ein Typanbieter mit der zuvor erstellten Datenbankverbindung eingerichtet. Die `MultipleActiveResultSets`-Eigenschaft ist erforderlich, wenn Sie das ADO.NET Entity Framework verwenden, da diese Eigenschaft die asynchrone, gleichzeitige Ausführung mehrerer Datenbankbefehle in einer Verbindung ermöglicht und dieser Fall in ADO.NET Entity Framework-Code häufig auftritt. Weitere Informationen finden Sie unter [Multiple Active Result Sets (MARS)](/sql/relational-databases/native-client/features/using-multiple-active-result-sets-mars).
<br />

2. Rufen Sie den Datenkontext ab. Dies ist ein Objekt, das die Datenbanktabellen als Eigenschaften und die gespeicherten Prozeduren und Funktionen der Datenbank als Methoden enthält.
<br />

```fsharp
let context = EntityConnection.GetDataContext()
```

## <a name="querying-the-database"></a>Abfragen der Datenbank
In diesem Schritt verwenden Sie F#-Abfrageausdrücke, um verschiedene Abfragen in der Datenbank auszuführen.


#### <a name="to-query-the-data"></a>So fragen Sie Daten ab

- Geben Sie den folgenden Code ein, um Daten aus dem Entity Data Model abzufragen. Beachten Sie die Auswirkungen von Pluralize = true: Die Datenbanktabelle Course wird in Courses, und Person wird in People geändert.
<br />

```fsharp
query { 
  for course in context.Courses do
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

query { 
  for person in context.People do
  select person 
} |> Seq.iter (fun person -> printfn "%s %s" person.FirstName person.LastName)

// Add a where clause to filter results.
query {
  for course in context.Courses do
  where (course.DepartmentID = 1)
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

// Join two tables.
query { 
  for course in context.Courses do
  join dept in context.Departments on (course.DepartmentID = dept.DepartmentID)
  select (course, dept.Name) 
} |> Seq.iter (fun (course, deptName) -> printfn "%s %s" course.Title deptName)
```

## <a name="updating-the-database"></a>Aktualisieren der Datenbank
Zum Aktualisieren der Datenbank verwenden Sie die Entity Framework-Klassen und -Methoden. Sie können zwei Typen von Datenkontexten für den SQLEntityConnection-Typanbieter verwenden. Der erste ist der vereinfachte Datenkontext `ServiceTypes.SimpleDataContextTypes.EntityContainer`, der nur die Eigenschaften bereitstellt, die die Datenbanktabellen und -spalten darstellen. Der zweite, vollständige Datenkontext ist eine Instanz der Entity Framework-Klasse `System.Data.Objects.ObjectContext`, die die Methode `System.Data.Objects.ObjectContext.AddObject(System.String,System.Object)` enthält, um Zeilen zur Datenbank hinzuzufügen. Das Entity Framework erkennt die Tabellen und die Beziehungen zwischen ihnen, sodass die Datenbankkonsistenz erzwungen wird.


#### <a name="to-update-the-database"></a>So aktualisieren Sie die Datenbank

1. Fügen Sie dem Programm folgenden Code hinzu. In diesem Beispiel fügen Sie zwei Objekte mit einer gegenseitigen Beziehung sowie eine Lehrkraft- und eine Bürozuweisung hinzu. Die Tabelle `OfficeAssignments` enthält die Spalte `InstructorID`, die auf die Spalte `PersonID` in der Tabelle `Person` verweist.
<br />

```fsharp
// The full data context
let fullContext = context.DataContext

// A helper function.
let nullable value = new System.Nullable<_>(value)

let addInstructor(lastName, firstName, hireDate, office) =
  let hireDate = DateTime.Parse(hireDate)
  let newPerson = new EntityConnection.ServiceTypes.Person(LastName = lastName,
                                                           FirstName = firstName,
                                                           HireDate = nullable hireDate)
  fullContext.AddObject("People", newPerson)

  let newOffice = new EntityConnection.ServiceTypes.OfficeAssignment(Location = office)

  fullContext.AddObject("OfficeAssignments", newOffice)
  fullContext.CommandTimeout <- nullable 1000
  fullContext.SaveChanges() |> printfn "Saved changes: %d object(s) modified."

addInstructor("Parker", "Darren", "1/1/1998", "41/3720")
```

In der Datenbank werden erst dann Änderungen vorgenommen, wenn Sie `System.Data.Objects.ObjectContext.SaveChanges` aufrufen.
<br />

2. Löschen Sie jetzt die Objekte, die Sie hinzugefügt haben, um den ursprünglichen Zustand der Datenbank wiederherzustellen.
<br />

```fsharp
let deleteInstructor(lastName, firstName) =
  query {
    for person in context.People do
    where (person.FirstName = firstName &&
           person.LastName = lastName)
    select person
  } |> Seq.iter (fun person->
                    query {
                      for officeAssignment in context.OfficeAssignments do
                      where (officeAssignment.Person.PersonID = person.PersonID)
                      select officeAssignment
                    } |> Seq.iter (fun officeAssignment -> fullContext.DeleteObject(officeAssignment))

                    fullContext.DeleteObject(person))

  // The call to SaveChanges should be outside of any iteration on the queries.
  fullContext.SaveChanges() |> printfn "Saved changed: %d object(s) modified."

deleteInstructor("Parker", "Darren")
```

>[!WARNING] 
Wenn Sie einen Abfrageausdruck verwenden, denken Sie daran, dass Abfragen verzögert ausgewertet werden. Die Datenbank bleibt daher bei allen verketteten Auswertungen zum Lesen geöffnet, so z. B. auch während der Verarbeitung der Lambda-Ausdrucksblöcke nach jedem Abfrageausdruck. Jeder Datenbankvorgang, der explizit oder implizit eine Transaktion verwendet, darf erst erfolgen, wenn die Lesevorgänge abgeschlossen sind.


## <a name="next-steps"></a>Nächste Schritte
Untersuchen Sie anhand der Operatoren für die Abfrage zur Verfügung, in anderen Abfrageoptionen [Abfrageausdrücke](../../language-reference/query-expressions.md), und überprüfen Sie auch die [ADO.NET Entity Framework](https://msdn.microsoft.com/library/bb399572) zu verstehen, welche Funktionen verfügbar, Sie ist Sie verwenden diese zuvor erstellte Anbieter.


## <a name="see-also"></a>Siehe auch
[Typanbieter](index.md)  
[SqlEntityConnection-Typanbieter](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqlentityconnection-type-provider-%5bfsharp%5d)  
[Exemplarische Vorgehensweise: Generieren von f#-Typen aus einer EDMX-Schemadatei](generating-fsharp-types-from-edmx.md)  
[ADO.NET Entity Framework](https://msdn.microsoft.com/library/bb399572)  
[Übersicht über die EDMX-Datei](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
[EDM-Generator &#40; EdmGen.exe &#41;](https://msdn.microsoft.com/library/bb387165)  
