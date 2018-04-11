---
title: 'Exemplarische Vorgehensweise: Generieren von F#-Typen aus einer DBML-Datei (F#)'
description: Informationen Sie zum Erstellen, f#-Typen für Daten aus einer Datenbank in f# 3.0 wenn Schemainformationen in einer DBML-Datei codiert.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 6fbb6ccc-248f-4226-95e9-f6f99541dbe4
ms.openlocfilehash: 3cd8df9becac0d1a8842eb22e2f772eee6307acf
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/10/2018
---
# <a name="walkthrough-generating-f-types-from-a-dbml-file"></a>Exemplarische Vorgehensweise: Generieren von F#-Typen aus einer DBML-Datei

> [!NOTE]
Dieses Handbuch wurde für f# 3.0 geschrieben und wird aktualisiert.  Unter [FSharp.Data](https://fsharp.github.io/FSharp.Data/) finden Sie aktuelle plattformübergeifende Typanbieter.

> [!NOTE]
Die API-Referenz Links gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

Diese exemplarische Vorgehensweise für f# 3.0 wird beschrieben, wie Typen für Daten aus einer Datenbank erstellen, wenn Sie Schemainformationen in einer DBML-Datei codiert haben wird. LINQ to SQL verwendet Dateiformat zur Darstellung des Datenbankschemas. Sie können eine LINQ to SQL-Schema-Datei in Visual Studio mithilfe des objektrelationalen (O/R)-Designers generieren. Weitere Informationen finden Sie unter [O/R-Designer (Übersicht)](https://msdn.microsoft.com/library/bb384511.aspx) und [Codegenerierung in LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).

Die Database Markup Language (DBML)-Typanbieter ermöglicht Ihnen, Code zu schreiben, die Typen auf Grundlage eines Datenbankschemas, ohne dass Ihnen die Angabe eine statischen Verbindungszeichenfolge zum Zeitpunkt der Kompilierung verwendet. Das ist hilfreich, wenn müssen Sie die Möglichkeit zu ermöglichen, dass der endgültige Anwendung verwendet werden, eine andere Datenbank, unterschiedliche Anmeldeinformationen oder eine andere Verbindungszeichenfolge als an denjenigen, die Sie verwenden, um die Anwendung zu entwickeln. Wenn Sie eine direkte datenbankverbindung, die Sie zum Zeitpunkt der Kompilierung verwenden können und dies ist die Datenbank und die Anmeldeinformationen, die Sie in der integrierten Anwendung verwendet werden, können Sie auch SQLDataConnection-Typanbieter verwenden. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Zugreifen auf eine SQL-Datenbank von mithilfe von Typanbietern](accessing-a-sql-database.md).

In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben beschrieben. Sie sollten in dieser Reihenfolge für die exemplarische Vorgehensweise erfolgreich abgeschlossen werden:


- Erstellen eine DBML-Datei
<br />

- Zum Erstellen und Einrichten einer f#-Projekt
<br />

- Konfigurieren des typanbieters und generieren Typen
<br />

- Abfragen der Datenbank
<br />


## <a name="prerequisites"></a>Erforderliche Komponenten

## <a name="creating-a-dbml-file"></a>Erstellen eine DBML-Datei
Wenn Sie keine Datenbank getestet haben, erstellen Sie eine mithilfe der Anweisungen im unteren Bereich des [Exemplarische Vorgehensweise: Zugreifen auf eine SQL-Datenbank von mithilfe von Typanbietern](accessing-a-sql-database.md). Wenn Sie diese Anleitungen befolgen, erstellen Sie eine Datenbank mit dem Namen MyDatabase, die ein paar einfache Tabellen und gespeicherten Prozeduren auf dem SQL Server enthält.

Wenn Sie bereits eine DBML-Datei verfügen, können Sie zum Abschnitt überspringen **erstellen und Festlegen einer F#-Projekt**. Andernfalls können Sie eine DBML-Datei erhält eine vorhandene SQL­Datenbank erstellen und mithilfe der Befehlszeile tool SqlMetal.exe.


#### <a name="to-create-a-dbml-file-by-using-sqlmetalexe"></a>So erstellen eine DBML-Datei mithilfe von SqlMetal.exe

1. Öffnen einer **Entwicklereingabeaufforderung**.
<br />

2. Stellen Sie sicher, dass Sie Zugriff auf SqlMetal.exe dazugehörenden haben `SqlMetal.exe /?` an der Eingabeaufforderung. SqlMetal.exe ist in der Regel unter installiert die **Microsoft-SDKs** Ordner **Programmdateien** oder **Programmdateien (x86)**.
<br />

3. Führen Sie SqlMetal.exe mit den folgenden Befehlszeilenoptionen ein. Ersetzen Sie einen geeigneten Pfad anstelle von `c:\destpath` erstellen die DBML-Datei, und fügen Sie entsprechende Werte für den Datenbankserver, Instanz, Namen und den Datenbanknamen.
<br />

```
  SqlMetal.exe /sprocs /dbml:C:\destpath\MyDatabase.dbml /server:SERVER\INSTANCE /database:MyDatabase
```

>[!NOTE]
Wenn SqlMetal.exe Probleme beim Erstellen der Datei aufgrund von Berechtigungsproblemen verfügt, ändern Sie das aktuelle Verzeichnis in einem Ordner, dem Sie haben Schreibzugriff auf.


4. Sie können auch die anderen verfügbaren Befehlszeilenoptionen betrachten. Es gibt z. B. Optionen, die Sie verwenden können, wenn Sie Sichten und SQL-Funktionen, die in die generierten Typen enthalten soll. Weitere Informationen finden Sie unter [SqlMetal.exe &#40;Tool zur Codegenerierung&#41;](https://msdn.microsoft.com/library/bb386987).
<br />


## <a name="creating-and-setting-up-an-f-project"></a>Zum Erstellen und Einrichten einer f#-Projekt
In diesem Schritt erstellen Sie ein Projekt und fügen die entsprechenden Verweise, um die DBML-Typanbieter verwendet wird.


#### <a name="to-create-and-set-up-an-f-project"></a>So erstellen und richten Sie ein F#-Projekt ein

1. Fügen Sie der Projektmappe ein neues F#-Konsolenanwendungsprojekt hinzu.
<br />

2. In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für **Verweise**, und wählen Sie dann **Verweis hinzufügen**.
<br />

3. In der **Assemblys** Bereich, wählen Sie die **Framework** Knoten, und wählen Sie dann in der Liste der verfügbaren Assemblys, die **"System.Data"** und **System.Data.Linq**  Assemblys.
<br />

4. In der **Assemblys** Bereich auswählen **Erweiterungen**, und wählen Sie dann in der Liste der verfügbaren Assemblys **FSharp.Data.TypeProviders**.
<br />

5. Wählen Sie die **OK** Schaltfläche, um Verweise auf diese Assemblys dem Projekt hinzuzufügen.
<br />

6. (Optional) Kopieren Sie die DBML-Datei, die Sie im vorherigen Schritt erstellt haben, und fügen Sie die Datei im Ordner "main" für das Projekt. Dieser Ordner enthält die Projektdatei (.fsproj) und die Codedateien. Wählen Sie in der Menüleiste **Projekt**, **vorhandenes Element hinzufügen**, und geben Sie dann die DBML-Datei, um sie zu Ihrem Projekt hinzuzufügen. Wenn Sie diese Schritte abgeschlossen haben, können Sie den statischen ResolutionFolder-Parameter im nächsten Schritt auslassen.
<br />

## <a name="configuring-the-type-provider"></a>Konfigurieren des Typanbieters
In diesem Abschnitt erstellen einen Typanbieter und Generieren von Typen aus dem Schema, das in der DBML-Datei beschrieben wird.


#### <a name="to-configure-the-type-provider-and-generate-the-types"></a>So konfigurieren den Typanbieter und generieren Typen

- Fügen Sie Code, der geöffnet wird die **TypeProviders** Namespace und instanziiert den Typanbieter für die DBML-Datei, die Sie verwenden möchten. Wenn Sie die DBML-Datei dem Projekt hinzugefügt haben, können Sie den statischen ResolutionFolder-Parameter auslassen.
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type dbml = DbmlFile<"MyDatabase.dbml", ResolutionFolder = @"<path-to-folder-that-contains-.dbml-file>">

// This connection string can be specified at run time.
let connectionString = "Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;"
let dataContext = new dbml.Mydatabase(connectionString)
```

DataContext-Typs ermöglicht den Zugriff auf die generierten Typen und erbt von `System.Data.Linq.DataContext`. DbmlFile-Typanbieter verfügt über verschiedene statischen Parametern, die Sie festlegen können. Beispielsweise können Sie einen anderen Namen für den DataContext-Typ verwenden, durch Angabe `DataContext=MyDataContext`. In diesem Fall ähnelt der Code im folgende Beispiel:
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type dbml = DbmlFile<"MyDatabase.dbml", ContextTypeName = "MyDataContext">

// This connection string can be specified at run time.
let connectionString = "Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;"
let db = new dbml.MyDataContext(connectionString)
```

## <a name="querying-the-database"></a>Abfragen der Datenbank
In diesem Abschnitt verwenden Sie f#-Abfrageausdrücke, um die Datenbank abzufragen.


#### <a name="to-query-the-data"></a>So fragen Sie Daten ab

- Fügen Sie Code zum Abfragen der Datenbank.
<br />

```fsharp
  query {
    for row in db.Table1 do
    where (row.TestData1 > 2)
    select row
  } |> Seq.iter (fun row -> printfn "%d %s" row.TestData1 row.Name)
```

## <a name="next-steps"></a>Nächste Schritte
Sie können fortfahren verwenden andere Abfrageausdrücke, oder rufen Sie eine datenbankverbindung aus den Datenkontext und normale Datenvorgänge in ADO.NET ausführen. Zusätzliche Schritte finden Sie in den Abschnitten nach "Die Abfragedaten" in [Exemplarische Vorgehensweise: Zugreifen auf eine SQL-Datenbank von mithilfe von Typanbietern](accessing-a-sql-database.md).


## <a name="see-also"></a>Siehe auch
[DbmlFile-Typanbieter](https://msdn.microsoft.com/visualfsharpdocs/conceptual/dbmlfile-type-provider-%5bfsharp%5d)

[Typanbieter](index.md)

[Exemplarische Vorgehensweise: Zugreifen auf eine SQL-Datenbank mithilfe von Typanbietern](accessing-a-sql-database.md)

[SqlMetal.exe &#40;Tool zum Generieren von Code&#41;](https://msdn.microsoft.com/library/bb386987)

[Abfrageausdrücke](../../language-reference/query-expressions.md)
