---
title: 'Tutorial: Batchverarbeitung mit .NET für Apache Spark'
description: Erfahren Sie, wie Sie Batchverarbeitung mithilfe von .NET für Apache Spark ausführen.
author: mamccrea
ms.author: mamccrea
ms.date: 12/13/2019
ms.topic: tutorial
ms.openlocfilehash: bd91fb401b9beb6ae74c4599b25e43284473f8b0
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75466424"
---
# <a name="tutorial-do-batch-processing-with-net-for-apache-spark"></a>Tutorial: Ausführen von Batchverarbeitung mit .NET für Apache Spark

In diesem Tutorial erfahren Sie, wie Sie Batchverarbeitung mithilfe von .NET für Apache Spark ausführen. Batchverarbeitung ist die Transformation von ruhenden Daten, was bedeutet, dass die Quelldaten bereits in den Datenspeicher geladen wurden. 

Batchverarbeitung erfolgt in der Regel über große, flache Datasets, die für eine weitere Analyse vorbereitet werden müssen. Protokollverarbeitung und Data Warehousing sind gängige Batchverarbeitungsszenarien. In diesem Szenario analysieren Sie Informationen zu GitHub-Projekten, z. B. wie häufig verschiedene Projekte geforkt oder wann Projekte zuletzt aktualisiert wurden. 

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
>
> * Erstellen und Ausführen einer .NET für Apache Spark-Anwendung
> * Lesen von Daten in einen DataFrame und Aufbereiten der Daten für die Analyse
> * Verarbeiten der Daten mithilfe von Spark SQL

## <a name="prerequisites"></a>Voraussetzungen 

Wenn Sie zum ersten Mal mit .NET für Apache Spark arbeiten, lesen Sie das Tutorial [Erste Schritte mit .NET for Apache Spark](../tutorials/get-started.md), um zu erfahren, wie Sie Ihre Umgebung vorbereiten und Ihre erste .NET für Apache Spark-Anwendung ausführen können.

## <a name="download-the-sample-data"></a>Herunterladen der Beispieldaten

[GHTorrent](http://ghtorrent.org/) überwacht alle öffentlichen GitHub-Ereignisse, z. B. Informationen zu Projekten, Commits und Watchern, und speichert die Ereignisse und deren Struktur in Datenbanken. Daten, die über verschiedene Zeiträume erfasst werden, sind als herunterladbare Archive verfügbar. Da die Speicherabbilddateien sehr groß sind, wird in diesem Leitfaden eine [gekürzte Version der Speicherabbilddatei](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/projects_smaller.csv) verwendet, die von GitHub heruntergeladen werden kann.

> [!NOTE]
> Das GHTorrent-DataSet wird in einem dualen Lizenzierungsschema ([Creative Commons +](https://wiki.creativecommons.org/wiki/CCPlus)) verteilt. Bei nichtkommerzieller Verwendung (einschließlich, aber nicht beschränkt auf Schulungs-, Forschungs- oder persönliche Zwecke) wird das DataSet unter der [CC-BY-SA-Lizenz](https://creativecommons.org/licenses/by-sa/4.0/) verteilt.

## <a name="create-a-console-application"></a>Erstellen einer Konsolenanwendung

1. Führen Sie in der Eingabeaufforderung die folgenden Befehle aus, um eine neue Konsolenanwendung zu erstellen:

   ```dotnetcli
   dotnet new console -o mySparkBatchApp
   cd mySparkBatchApp
   ```

   Der `dotnet`-Befehl erstellt für Sie eine `new`-Anwendung des Typs `console`. Der `-o`-Parameter erstellt ein Verzeichnis namens *mySparkBatchApp*, in dem Ihre App gespeichert wird, und füllt es mit den erforderlichen Dateien auf. Mit dem Befehl `cd mySparkBatchApp` wird das Verzeichnis in das soeben erstellte App-Verzeichnis geändert.

1. Wenn Sie .NET für Apache Spark in einer App verwenden möchten, installieren Sie das Microsoft.Spark-Paket. Führen Sie in der Konsole den folgenden Befehl aus:

   ```dotnetcli
   dotnet add package Microsoft.Spark
   ```

## <a name="create-a-sparksession"></a>Erstellen einer SparkSession

1. Fügen Sie in *mySparkBatchApp* oben in der Datei *Program.cs* die folgenden zusätzlichen `using`-Anweisungen hinzu.

   ```csharp
   using System;
   using Microsoft.Spark.Sql;
   using static Microsoft.Spark.Sql.Functions;
   ```

1. Fügen Sie Ihrem Projektnamespace den folgenden Code hinzu. *s_referenceData* wird später im Programm verwendet, um basierend auf dem Datum zu filtern.

   ```csharp
   static readonly DateTime s_referenceDate = new DateTime(2015, 10, 20);
   ```

1. Fügen Sie in der Main-Methode den folgenden Code hinzu, um eine neue SparkSession einzurichten. Die SparkSession ist der Einstiegspunkt in die Programmierung von Spark mit dem Dataset und der DataFrame-API. Der Aufruf des `spark`-Objekts ermöglicht im gesamten Programm den Zugriff auf Spark- und DataFrame-Funktionalität.

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName("GitHub and Spark Batch")
        .GetOrCreate();
   ```

## <a name="prepare-the-data"></a>Vorbereiten der Daten

1. Lesen Sie die Eingabedatei in ein `DataFrame`-Objekt, bei dem es sich um eine verteilte Sammlung von Daten handelt, die in benannten Spalten organisiert ist. Sie können die Spalten für die Daten über <xref:Microsoft.Spark.Sql.DataFrame.Schema%2A> festlegen. Verwenden Sie die <xref:Microsoft.Spark.Sql.DataFrame.Show%2A>-Methode, um die Daten in Ihrem DataFrame anzuzeigen. Stellen Sie sicher, dass Sie den Pfad der CSV-Datei auf den Speicherort der von Ihnen heruntergeladenen GitHub-Daten aktualisieren.

   ```csharp
   DataFrame projectsDf = spark
       .Read()
       .Schema("id INT, url STRING, owner_id INT, " +
       "name STRING, descriptor STRING, language STRING, " +
       "created_at STRING, forked_from INT, deleted STRING" +
       "updated_at STRING")
       .Csv("filepath");

   projectsDf.Show();
   ```

1. Verwenden Sie die <xref:Microsoft.Spark.Sql.DataFrame.Na%2A>-Methode, um Zeilen mit N/V-Werten (NULL-Werten) zu löschen, und die <xref:Microsoft.Spark.Sql.DataFrame.Drop%2A>-Methode, um bestimmte Spalten aus den Daten zu entfernen. Dies hilft, Fehler zu vermeiden, wenn Sie versuchen, NULL-Daten oder Spalten zu analysieren, die für die endgültige Analyse nicht relevant sind.

   ```csharp
   // Drop any rows with NA values
   DataFrameNaFunctions dropEmptyProjects = projectsDf.Na();
   DataFrame cleanedProjects = dropEmptyProjects.Drop("any");

   // Remove unnecessary columns
   cleanedProjects = cleanedProjects.Drop("id", "url", "owner_id");
   cleanedProjects.Show();
   ```

## <a name="analyze-the-data"></a>Analysieren der Daten

Spark SQL ermöglicht Ihnen, SQL-Aufrufe für Ihre Daten durchführen. Es ist üblich, benutzerdefinierte Funktionen und Spark SQL zu kombinieren, um eine benutzerdefinierte Funktion auf alle Zeilen Ihres DataFrame anzuwenden.

Sie können `spark.Sql` speziell aufrufen, um standardmäßige SQL-Aufrufe in anderen App-Typen zu imitieren. Sie können auch Methoden wie <xref:Microsoft.Spark.Sql.DataFrame.GroupBy%2A> und <xref:Microsoft.Spark.Sql.DataFrame.Agg%2A> zum speziellen Kombinieren, Filtern und Ausführen von Berechnungen für Ihre Daten aufzurufen.

Das Ziel dieser App besteht darin, Einblicke in die GitHub-Projektdaten zu erhalten. Fügen Sie dem Programm die folgenden Codeausschnitte hinzu, um die Daten zu analysieren.

1. Durch Hinzufügen des folgenden Codeblocks wird ermittelt, wie oft jede Sprache geforkt wurde. Zunächst werden die Daten nach der Sprache gruppiert. Anschließend wird die durchschnittliche Anzahl der Forks aus jeder Sprache ermittelt.

   ```csharp
   // Average number of times each language has been forked
   DataFrame groupedDF = cleanedProjects
       .GroupBy("language")
       .Agg(Avg(cleanedProjects["forked_from"]);
   ```

1. Fügen Sie den folgenden Codeblock hinzu, um die durchschnittliche Anzahl der Forks in absteigender Reihenfolge zu sortieren, um zu ermitteln, welche Sprachen am meisten geforkt werden. Dies bedeutet, die größte Anzahl von Forks zuerst angezeigt wird.

   ```csharp
   // Sort by most forked languages first
   groupedDF.OrderBy(Desc("avg(forked_from)")).Show(); 
   ```

1. Der nächste Codeblock zeigt Ihnen, wann Projekte zuletzt aktualisiert wurden. Sie registrieren eine neue benutzerdefinierte Funktion namens *MyUDF* und vergleichen sie mit einem Datum (*s_referenceDate*), das am Anfang des Tutorials deklariert wurde. Das Datum für jedes Projekt wird mit dem Verweisdatum verglichen. Anschließend wird Spark SQL verwendet, um die benutzerdefinierte Funktion für jede Zeile der Daten aufzurufen, um jedes Projekt im Dataset zu analysieren.

   ```csharp
   spark.Udf().Register<string, bool>(
       "MyUDF",
       (date) => DateTime.TryParse(date, out DateTime convertedDate) &&
           (convertedDate > s_referenceDate);   
   cleanedProjects.CreateOrReplaceTempView("dateView"); 

   DataFrame dateDf = spark.Sql(
       "SELECT *, MyUDF(dateView.updated_at) AS datebefore FROM dateView");
   dateDf.Show();
   ```

1. Rufen Sie `spark.Stop()` auf, um die SparkSession zu beenden.

## <a name="use-spark-submit-to-run-your-app"></a>Verwenden von spark-submit zum Ausführen Ihrer App

1. Verwenden Sie den folgenden Befehl, um die .NET-App zu erstellen:

   ```dotnetcli
   dotnet build
   ```

1. Führen Sie Ihre App mit `spark-submit` aus. Aktualisieren Sie unbedingt den folgenden Befehl mit dem aktuellen Pfad zu Ihrer JAR-Datei für Microsoft Spark.

   ```console
   spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local /<path>/to/microsoft-spark-<version>.jar dotnet /<path>/to/netcoreapp<version>/GitHubProjects.dll
   ```

## <a name="get-the-code"></a>Abrufen des Codes

Die [vollständige Lösung](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/GitHubProjects.cs) finden Sie auf GitHub.

## <a name="next-steps"></a>Nächste Schritte

Fahren Sie mit dem nächsten Artikel fort, um zu erfahren, wie Sie Streamingdaten mit .NET für Apache Spark verarbeiten.
> [!div class="nextstepaction"]
> [Tutorial: Strukturiertes Streaming mit .NET für Apache Spark](streaming.md)
