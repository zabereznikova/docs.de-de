---
title: 'Exemplarische Vorgehensweise: Effizienzverbesserung durch Verwendung von BatchBlock und BatchedJoinBlock'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, improving efficiency
ms.assetid: 5beb4983-80c2-4f60-8c51-a07f9fd94cb3
ms.openlocfilehash: d9c4b2d5cfab28f10be82724f46660e4b42ce410
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829920"
---
# <a name="walkthrough-using-batchblock-and-batchedjoinblock-to-improve-efficiency"></a>Exemplarische Vorgehensweise: Effizienzverbesserung durch Verwendung von BatchBlock und BatchedJoinBlock

Die TPL-Datenflussbibliothek stellt die <xref:System.Threading.Tasks.Dataflow.BatchBlock%601?displayProperty=nameWithType>- und die <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602?displayProperty=nameWithType>-Klasse bereit, sodass Sie Daten aus einer oder mehreren Quellen empfangen und puffern und diese Daten dann als Auflistung weitergeben können. Dieser Batchverarbeitungsmechanismus ist hilfreich, wenn Sie Daten aus einer oder mehreren Quellen sammeln und dann mehrere Datenelemente als Batch verarbeiten. Stellen Sie sich beispielsweise eine Anwendung vor, die Datensätze mithilfe von Datenfluss in eine Datenbank einfügt. Dieser Vorgang kann effizienter werden, wenn mehrere Elemente gleichzeitig statt hintereinander eingefügt werden. In diesem Dokument wird beschrieben, wie mit der <xref:System.Threading.Tasks.Dataflow.BatchBlock%601>-Klasse die Effizienz solcher Datenbankeinfügevorgänge verbessert wird. Außerdem wird beschrieben, wie mit der <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602>-Klasse sowohl die Ergebnisse als auch Ausnahmen erfasst werden, die auftreten, während das Programm aus einer Datenbank liest.

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="prerequisites"></a>Voraussetzungen

1. Lesen Sie den Abschnitt „Gruppierungsblöcke“ im Dokument [Datenfluss](dataflow-task-parallel-library.md), bevor Sie mit dieser exemplarischen Vorgehensweise beginnen.

2. Stellen Sie sicher, dass Sie über eine Kopie der Northwind-Datenbank (Northwind.sdf) auf Ihrem Computer verfügen. Diese Datei befindet sich normalerweise im Ordner %Programme%\Microsoft SQL Server Compact Edition\v3.5\Samples\\\.

    > [!IMPORTANT]
    > In einigen Versionen von Windows können Sie keine Verbindung zu „Northwind.sdf“ herstellen, wenn Visual Studio nicht im Administratormodus ausgeführt wird. Starten Sie zum Herstellen einer Verbindung mit „Northwind.sdf“ Visual Studio oder eine Developer-Eingabeaufforderung für Visual Studio im Modus **Als Administrator ausführen**.

Diese exemplarische Vorgehensweise enthält folgende Abschnitte:

- [Erstellen der Konsolenanwendung](#creating)

- [Definieren der Klasse für Mitarbeiter](#employeeClass)

- [Definieren der Datenbankvorgänge für Mitarbeiter](#operations)

- [Hinzufügen von Mitarbeiterdaten zur Datenbank ohne Pufferung](#nonBuffering)

- [Verwenden von Pufferung beim Hinzufügen von Mitarbeiterdaten zur Datenbank](#buffering)

- [Verwenden einer gepufferten Gruppierung zum Lesen von Mitarbeiterdaten aus der Datenbank](#bufferedJoin)

- [Vollständiges Beispiel](#complete)

<a name="creating"></a>

## <a name="creating-the-console-application"></a>Erstellen der Konsolenanwendung

1. Erstellen Sie in Visual Studio ein Visual C#- oder Visual Basic-Projekt des Typs **Konsolenanwendung**. In diesem Dokument hat das Projekt den Namen `DataflowBatchDatabase`.

2. Fügen Sie im Projekt einen Verweis auf „System.Data.SqlServerCe.dll“ und einen Verweis auf „System.Threading.Tasks.Dataflow.dll“ hinzu.

3. Stellen Sie sicher, dass „Form1.cs“ („Form1.vb“ für Visual Basic) die folgenden `using`-Anweisungen (`Imports` in Visual Basic) enthält.

    [!code-csharp[TPLDataflow_BatchDatabase#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#1)]
    [!code-vb[TPLDataflow_BatchDatabase#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#1)]

4. Fügen Sie der `Program`-Klasse die folgenden Datenmember hinzu.

    [!code-csharp[TPLDataflow_BatchDatabase#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#2)]
    [!code-vb[TPLDataflow_BatchDatabase#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#2)]

<a name="employeeClass"></a>

## <a name="defining-the-employee-class"></a>Definieren der Klasse für Mitarbeiter

Fügen Sie der `Program`-Klasse die `Employee`-Klasse hinzu.

[!code-csharp[TPLDataflow_BatchDatabase#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#3)]
[!code-vb[TPLDataflow_BatchDatabase#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#3)]

Die `Employee`-Klasse enthält die drei Eigenschaften `EmployeeID`, `LastName` und `FirstName`. Diese Eigenschaften entsprechen den Spalten `Employee ID`, `Last Name` und `First Name` in der Tabelle `Employees` der Northwind-Datenbank. Bei dieser Demonstration wird von der `Employee`-Klasse auch die `Random`-Methode definiert, die ein `Employee`-Objekt erstellt, das Zufallswerte für die zugehörigen Eigenschaften enthält.

<a name="operations"></a>

## <a name="defining-employee-database-operations"></a>Definieren der Datenbankvorgänge für Mitarbeiter

Fügen Sie der `Program`-Klasse die Methoden `InsertEmployees`, `GetEmployeeCount` und `GetEmployeeID` hinzu.

[!code-csharp[TPLDataflow_BatchDatabase#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#4)]
[!code-vb[TPLDataflow_BatchDatabase#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#4)]

Die `InsertEmployees`-Methode fügt der Datenbank neue Mitarbeiterdatensätze hinzu. Die `GetEmployeeCount`-Methode ruft die Anzahl von Einträgen in der Tabelle `Employees` ab. Die `GetEmployeeID`-Methode ruft den Bezeichner des ersten Mitarbeiters mit dem angegebenen Namen ab. Jede dieser Methoden nimmt eine Verbindungszeichenfolge zur Northwind-Datenbank an und verwendet Funktionen im `System.Data.SqlServerCe`-Namespace, um mit der Datenbank zu kommunizieren.

<a name="nonBuffering"></a>

## <a name="adding-employee-data-to-the-database-without-using-buffering"></a>Hinzufügen von Mitarbeiterdaten zur Datenbank ohne Pufferung

Fügen Sie der `Program`-Klasse die Methoden `AddEmployees` und `PostRandomEmployees` hinzu.

[!code-csharp[TPLDataflow_BatchDatabase#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#5)]
[!code-vb[TPLDataflow_BatchDatabase#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#5)]

Die `AddEmployees`-Methode fügt der Datenbank mithilfe von Datenfluss zufällige Mitarbeiterdaten hinzu. Sie erstellt ein <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>-Objekt, das die `InsertEmployees`-Methode aufruft, um der Datenbank einen Mitarbeitereintrag hinzuzufügen. Die `AddEmployees`-Methode ruft dann die `PostRandomEmployees`-Methode auf, um mehrere `Employee`-Objekte an das <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>-Objekt zu senden. Die `AddEmployees`-Methode wartet dann, bis alle Einfügevorgänge abgeschlossen sind.

<a name="buffering"></a>

## <a name="using-buffering-to-add-employee-data-to-the-database"></a>Verwenden von Pufferung beim Hinzufügen von Mitarbeiterdaten zur Datenbank

Fügen Sie der `Program`-Klasse die `AddEmployeesBatched`-Methode hinzu.

[!code-csharp[TPLDataflow_BatchDatabase#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#6)]
[!code-vb[TPLDataflow_BatchDatabase#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#6)]

Diese Methode ähnelt `AddEmployees`, außer dass sie auch die <xref:System.Threading.Tasks.Dataflow.BatchBlock%601>-Klasse verwendet, um mehrere `Employee`-Objekte zu puffern, bevor diese Objekte an das <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>-Objekt gesendet werden. Da die <xref:System.Threading.Tasks.Dataflow.BatchBlock%601>-Klasse mehrere Elemente als Auflistung weitergibt, wird das <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>-Objekt so geändert, dass es auf ein Array von `Employee`-Objekten angewendet wird. Wie bei der Methode `AddEmployees` ruft `AddEmployeesBatched` die `PostRandomEmployees`-Methode auf, um mehrere `Employee`-Objekte zu senden. `AddEmployeesBatched` sendet diese Objekte jedoch an das <xref:System.Threading.Tasks.Dataflow.BatchBlock%601>-Objekt. Die `AddEmployeesBatched`-Methode wartet ebenfalls, bis alle Einfügevorgänge abgeschlossen sind.

<a name="bufferedJoin"></a>

## <a name="using-buffered-join-to-read-employee-data-from-the-database"></a>Verwenden einer gepufferten Gruppierung zum Lesen von Mitarbeiterdaten aus der Datenbank

Fügen Sie der `Program`-Klasse die `GetRandomEmployees`-Methode hinzu.

[!code-csharp[TPLDataflow_BatchDatabase#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#7)]
[!code-vb[TPLDataflow_BatchDatabase#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#7)]

Diese Methode gibt Informationen über zufällige Mitarbeiter in der Konsole aus. Sie erstellt mehrere zufällige `Employee`-Objekte ruft die `GetEmployeeID`-Methode auf, um den eindeutigen Bezeichner für die einzelnen Objekte abzurufen. Da die `GetEmployeeID`-Methode eine Ausnahme auslöst, wenn kein entsprechender Mitarbeiter mit dem angegebenen Vor- und Nachnamen vorhanden ist, verwendet die `GetRandomEmployees`-Methode die <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602>-Klasse, um `Employee`-Objekte für erfolgreiche Aufrufe von `GetEmployeeID` und <xref:System.Exception?displayProperty=nameWithType>-Objekte für fehlgeschlagene Aufrufe zu speichern. Das <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>-Objekt in diesem Beispiel wird auf ein <xref:System.Tuple%602>-Objekt angewendet, das eine Liste von `Employee`-Objekten und eine Liste von <xref:System.Exception>-Objekten enthält. Das <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602>-Objekt gibt diese Daten weiter, wenn die Summe empfangenen `Employee`- und <xref:System.Exception>-Objekte die Batchgröße erreicht.

<a name="complete"></a>

## <a name="the-complete-example"></a>Vollständiges Beispiel

Das folgende Beispiel enthält den vollständigen Code. Die `Main`-Methode vergleicht die Zeitspanne, die erforderlich ist, um Datenbankeinfügungen im Batch durchzuführen, mit der Zeitspanne zum Durchführen von Datenbankeinfügungen ohne Verwendung von Batches. Außerdem wird damit die Verwendung einer gepufferten Gruppierung demonstriert, um Mitarbeiterdaten aus der Datenbank zu lesen und Fehler zu melden.

[!code-csharp[TPLDataflow_BatchDatabase#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#100)]
[!code-vb[TPLDataflow_BatchDatabase#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#100)]

## <a name="see-also"></a>Weitere Informationen

- [Dataflow (Datenfluss)](dataflow-task-parallel-library.md)
