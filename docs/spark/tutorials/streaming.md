---
title: Tutorial zu Structured Streaming mit .NET für Apache Spark
description: In diesem Tutorial erfahren Sie, wie Sie .NET für Apache Spark für Spark Structured Streaming verwenden.
author: mamccrea
ms.author: mamccrea
ms.date: 12/04/2019
ms.topic: tutorial
ms.openlocfilehash: d0fe79ef79125c06be9acd8ba80001a33e150adb
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802858"
---
# <a name="tutorial-structured-streaming-with-net-for-apache-spark"></a>Tutorial: Structured Streaming mit .NET für Apache Spark 

Dieses Tutorial zeigt Ihnen, wie Sie Spark Structured Streaming mit .NET for Apache Spark aufrufen können. Spark Structured Streaming ist die Unterstützung von Apache Spark für die Verarbeitung von Echtzeitdatenströmen. Datenstromverarbeitung bedeutet, dass Livedaten während ihrer Erstellung analysiert werden.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
>
> * Erstellen und Ausführen einer .NET für Apache Spark-Anwendung
> * Verwenden von netcat zum Erstellen eines Datenstroms
> * Verwenden von benutzerdefinierten Funktionen und SparkSQL zur Analyse von Streamingdaten

## <a name="prerequisites"></a>Erforderliche Komponenten

Wenn dies Ihre erste .NET für Apache Spark-Anwendung ist, beginnen Sie mit dem [Tutorial „Erste Schritte“](get-started.md), um sich mit den Grundlagen vertraut zu machen.

## <a name="create-a-console-application"></a>Erstellen einer Konsolenanwendung

1. Führen Sie in der Eingabeaufforderung die folgenden Befehle aus, um eine neue Konsolenanwendung zu erstellen:

   ```console
   dotnet new console -o mySparkStreamingApp
   cd mySparkStreamingApp
   ```

   Der `dotnet`-Befehl erstellt für Sie eine `new`-Anwendung des Typs `console`. Der `-o`-Parameter erstellt ein Verzeichnis namens *mySparkStreamingApp*, in dem Ihre App gespeichert wird, und füllt es mit den erforderlichen Dateien auf. Mit dem Befehl `cd mySparkStreamingApp` wird das Verzeichnis in das soeben erstellte App-Verzeichnis geändert.

1. Wenn Sie .NET für Apache Spark in einer App verwenden möchten, installieren Sie das Microsoft.Spark-Paket. Führen Sie in der Konsole den folgenden Befehl aus:

   ```console
   dotnet add package Microsoft.Spark
   ```

## <a name="establish-and-connect-to-a-data-stream"></a>Einrichten eines Datenstroms und Herstellen einer Verbindung

Eine beliebte Methode zum Testen der Datenstromverarbeitung ist **netcat**. netcat (auch als *nc*bezeichnet) ermöglicht Ihnen das Lesen von Daten aus und Schreiben von Daten in Netzwerkverbindungen. Sie stellen in einem Terminalfenster eine Netzwerkverbindung mit netcat her. 

### <a name="create-a-data-stream-with-netcat"></a>Erstellen eines Datenstroms mit netcat

1. [Laden Sie netcat herunter](https://sourceforge.net/projects/nc110/files/). Extrahieren Sie dann die Datei aus der heruntergeladenen ZIP-Datei, und fügen Sie das von Ihnen extrahierte Verzeichnis an Ihre Umgebungsvariable PATH an.

2. Um eine neue Verbindung herzustellen, öffnen Sie eine neue Konsole und führen den folgenden Befehl aus, der sich an Port 9999 mit localhost verbindet.

   Unter Windows:

   ```console
   nc -vvv -l -p 9999
   ```

   Unter Linux:

   ```console
   nc -lk 9999
   ```

   Ihr Spark-Programm lauscht auf Ihre Eingaben an dieser Eingabeaufforderung.

### <a name="create-a-sparksession"></a>Erstellen einer SparkSession

1. Fügen Sie in *mySparkStreamingApp* oben in der Datei *Program.cs* die folgenden zusätzlichen `using`-Anweisungen hinzu:

   ```csharp
   using System;
   using Microsoft.Spark.Sql;
   using Microsoft.Spark.Sql.Streaming;
   using static Microsoft.Spark.Sql.Functions;
   ```

1. Fügen Sie der `Main`-Methode den folgenden Code hinzu, um eine neue `SparkSession` zu erstellen. Die Spark-Sitzung ist der Einstiegspunkt in die Programmierung von Spark mit der Dataset- und DataFrame-API.

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName("Streaming example with a UDF")
        .GetOrCreate();
   ```

   Der Aufruf des oben erstellten *spark*-Objekts ermöglicht im gesamten Programm den Zugriff auf Spark- und DataFrame-Funktionalität.

### <a name="connect-to-a-stream-with-readstream"></a>Herstellen einer Verbindung mit einem Datenstrom mit ReadStream()

Die `ReadStream()`-Methode gibt das Element `DataStreamReader` zurück, das zum Einlesen von Streamingdaten als `DataFrame` verwendet werden kann. Fügen Sie die Host- und Portinformationen hinzu, um Ihrer Spark-App anzugeben, wo ihre Streamingdaten zu erwarten sind.

```csharp
DataFrame lines = spark
    .ReadStream()
    .Format("socket")
    .Option("host", hostname)
    .Option("port", port)
    .Load();
```

## <a name="register-a-user-defined-function"></a>Registrieren einer benutzerdefinierten Funktion

Sie können in Spark-Anwendungen mithilfe *benutzerdefinierter Funktionen* Berechnungen und Analysen Ihrer Daten durchführen.

Fügen Sie der `Main`-Methode den folgenden Code hinzu, um die benutzerdefinierte Funktion `udfArray` zu registrieren. 

```csharp
Func<Column, Column> udfArray =
    Udf<string, string[]>((str) => new string[] { str, $"{str} {str.Length}" });
```

Diese benutzerdefinierte Funktion verarbeitet jede vom netcat-Terminal empfangene Zeichenfolge, um ein Array zu erstellen. Es enthält (in *str*) die ursprüngliche Zeichenfolge gefolgt von der ursprünglichen Zeichenfolge verkettet mit der Länge der ursprünglichen Zeichenfolge. 

Wenn Sie beispielsweise im netcat-Terminal *Hello world* eingeben, wird ein Array mit den folgenden Elementen erzeugt:

* array\[0] = Hello world
* array\[1] = Hello world 11

## <a name="use-sparksql"></a>Verwenden von SparkSQL

Verwenden Sie SparkSQL, um verschiedene Funktionen auf die in Ihrem DataFrame gespeicherten Daten anzuwenden. Es ist üblich, benutzerdefinierte Funktionen und SparkSQL zu kombinieren, um eine benutzerdefinierte Funktion auf jede Zeile in einem DataFrame anzuwenden.

```csharp
DataFrame arrayDF = lines.Select(Explode(udfArray(lines["value"])));
```

Dieser Codeausschnitt wendet *udfArray* auf alle Werte in Ihrem DataFrame an, der alle Zeichenfolgen darstellt, die von Ihrem netcat-Terminal gelesen wird. Wenden Sie die SparkSQL-Methode <xref:Microsoft.Spark.Sql.Functions.Explode%2A> an, um jeden Eintrag Ihres Arrays in einer eigenen Zeile zu platzieren. Verwenden Sie schließlich <xref:Microsoft.Spark.Sql.DataFrame.Select%2A>, um die von Ihnen generierten Spalten im neuen DataFrame *arrayDF* zu platzieren.

## <a name="display-your-stream"></a>Anzeigen Ihres Datenstroms

Verwenden Sie <xref:Microsoft.Spark.Sql.DataFrame.WriteStream>, um Eigenschaften Ihrer Ausgabe festzulegen, wie z. B. das Ausgeben von Ergebnissen in der Konsole und das Anzeigen nur der letzten Ausgabe.

```csharp
StreamingQuery query = arrayDf
    .WriteStream()
    .Format("console")
    .Start();
```

## <a name="run-your-code"></a>Ausführen Ihres Codes

Beim strukturierten Streaming in Spark werden die Daten in einer Folge kleiner **Batches** verarbeitet.  Wenn Sie Ihr Programm ausführen, können Sie an der Eingabeaufforderung, über die Sie die Verbindung mit netcat herstellen, mit der Eingabe beginnen. Bei jedem Drücken der EINGABETASTE nach Eingabe von Daten in diese Eingabeaufforderung betrachtet Spark Ihre Eingabe als Batch und führt die benutzerdefinierte Funktion aus.

### <a name="use-spark-submit-to-run-your-app"></a>Verwenden von spark-submit zum Ausführen Ihrer App

Nach dem Start einer neuen netcat-Sitzung öffnen Sie ein neues Terminal, und führen Sie den Befehl `spark-submit` aus, der dem folgenden Befehl ähnelt:

```powershell
spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local /path/to/microsoft-spark-<version>.jar Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredNetworkCharacterCount localhost 9999
```

> [!NOTE]
> Aktualisieren Sie unbedingt den obigen Befehl mit dem aktuellen Pfad zu Ihrer JAR-Datei für Microsoft Spark. Der obige Befehl geht auch davon aus, dass Ihr netcat-Server auf localhost an Port 9999 ausgeführt wird.

## <a name="get-the-code"></a>Abrufen des Codes

In diesem Tutorial wird das Beispiel [StructuredNetworkCharacterCharacterCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkCharacterCount.cs) verwendet. Auf GitHub gibt es jedoch drei weitere vollständige Beispiele für die Verarbeitung von Datenströmen:

* [StructuredNetworkWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs): dient zum Zählen der Wörter in Daten, die aus einer beliebigen Quell gestreamt werden
* [StructuredNetworkWordCountWindowed.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCountWindowed.cs): dient zum Zählen der Wörter in Daten mit Windowinglogik
* [StructuredKafkaWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs): dient zum Zählen der Wörter in Daten, die aus Kafka gestreamt werden

## <a name="next-steps"></a>Nächste Schritte

Fahren Sie mit dem nächsten Artikel fort, um zu erfahren, wie Sie Ihre .NET für Apache Spark-Anwendung in Databricks bereitstellen.
> [!div class="nextstepaction"]
> [Tutorial: Bereitstellen einer .NET für Apache Spark-Anwendung in Databricks](databricks-deployment.md)
