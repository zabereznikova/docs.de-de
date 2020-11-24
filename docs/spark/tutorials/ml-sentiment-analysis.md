---
title: Tutorial zur Standpunktanalyse mit .NET für Apache Spark und ML.NET
description: In diesem Tutorial erfahren Sie, wie Sie ML.NET mit .NET für Apache Spark für eine Standpunktanalyse verwenden.
author: mamccrea
ms.author: mamccrea
ms.date: 10/09/2020
ms.topic: tutorial
ms.openlocfilehash: 1c2c966a4ff50a9d2f6951e20d909c5c20c75bfb
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688240"
---
# <a name="tutorial-sentiment-analysis-with-net-for-apache-spark-and-mlnet"></a>Tutorial: Standpunktanalyse mit .NET für Apache Spark und ML.NET

In diesem Tutorial erfahren Sie, wie Sie ML.NET mit .NET für Apache Spark eine Standpunktanalyse für Onlinebewertungen durchführen. [ML.NET](http://dot.net/ml) ist ein kostenloses, plattformübergreifendes Open Source-Framework für maschinelles Lernen. Sie können ML.NET mit .NET für Apache Spark nutzen, um Training und Vorhersage von Machine Learning-Algorithmen zu skalieren.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
>
> * Erstellen eines Modells für die Standpunktanalyse mit dem ML.NET-Modell-Generator in Visual Studio
> * Erstellen einer .NET für Apache Spark-Konsolen-App
> * Schreiben und Implementieren einer benutzerdefinierten Funktion
> * Ausführen einer .NET für Apache Spark-Konsolen-App

## <a name="prerequisites"></a>Voraussetzungen

* Wenn Sie noch keine .NET für Apache Spark-Anwendung entwickelt haben, beginnen Sie mit dem [Tutorial „Erste Schritte“](get-started.md), um sich mit den Grundlagen vertraut zu machen. Sorgen Sie dafür, dass alle Voraussetzungen für das Tutorial „Erste Schritte“ erfüllt sind, bevor Sie mit diesem Tutorial fortfahren.

* In diesem Tutorial wird der ML.NET-Modell-Generator (Vorschau) verwendet, eine grafische Benutzeroberfläche, die in Visual Studio zur Verfügung steht. Falls Sie Visual Studio noch nicht erworben haben, können Sie die [Community-Version von Visual Studio](https://visualstudio.microsoft.com/downloads/) kostenlos herunterladen.

* Außerdem müssen Sie den ML.NET-Modell-Generator (Vorschau) [herunterladen und installieren](https://marketplace.visualstudio.com/items?itemName=MLNET.07).

* Laden Sie die Yelp-Bewertungsdatasets [yelptest.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptest.csv) und [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv) herunter.

## <a name="review-the-data"></a>Überprüfen der Daten

Die Yelp-Datasets enthalten Yelp-Onlinebewertungen zu verschiedenen Diensten. Öffnen Sie [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv), und beachten Sie die Struktur der Daten. Die erste Spalte enthält den Text der Bewertung, und die zweite Spalte enthält Stimmungspunktzahlen. Wenn die Stimmungspunktzahl 1 lautet, ist die Bewertung positiv. Lautet die Stimmungspunktzahl 0, ist die Bewertung negativ.

Die folgende Tabelle enthält einige Beispieldaten:

|ReviewText|Standpunkt|
|-|-|
|Toll... Mir hat das Restaurant gefallen.|    1|
|Die Kruste ist nicht gut.|    0|

## <a name="build-your-machine-learning-model"></a>Erstellen Ihres Machine Learning-Modells

1. Öffnen Sie Visual Studio, und erstellen Sie eine neue C#-Konsolen-App (.NET Core). Geben Sie dem Projekt den Namen *MLSparkModel*.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt *MLSparkModel*. Wählen Sie anschließend **hinzufügen > Machine Learning** aus.

1. Wählen Sie im ML.NET-Modell-Generator die Kachel für das Szenario **Standpunktanalyse** aus.

1. Laden Sie auf der Seite **Daten hinzufügen** das Dataset *yelptrain.csv* hoch.

1. Wählen Sie im Dropdownmenü **Vorherzusagende Spalten** die Option *Stimmung* aus.

1. Legen Sie auf der Seite **Trainieren** die Trainingszeit auf *60 Sekunden* fest, und klicken Sie auf **Training starten**. Verfolgen Sie den Status Ihres Trainings unter **Fortschritt**.

1. Sobald der Modell-Generator das Training abgeschlossen hat, können Sie die Trainingsergebnisse **Auswerten**. Sie können in das Textfeld unter **Modell testen** einen Satz eingeben und auf **Vorhersage** klicken, um die Ausgabe anzuzeigen.

1. Wählen Sie **Code** und anschließend **Projekte hinzufügen** aus, um das ML-Modell zur Projektmappe hinzuzufügen.

1. Beachten Sie, dass Ihrer Projektmappe zwei Projekte hinzugefügt werden: **MLSparkModelML.ConsoleApp** und **MLSparkModelML.Model**.

1. Doppelklicken Sie auf Ihr C#-Projekt *MLSpark* und beachten Sie, dass der folgende Projektverweis hinzugefügt wurde.

   ```xml
   <ItemGroup>
       <ProjectReference Include="..\MLSparkModelML.Model\MLSparkModelML.Model.csproj" />
   </ItemGroup>
   ```

## <a name="create-a-console-app"></a>Erstellen einer Konsolenanwendung

Der Modell-Generator erstellt eine Konsolen-App für Sie.

1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt **MLSparkModelML.Console**, und wählen Sie **NuGet-Pakete verwalten** aus.

1. Suchen Sie nach **Microsoft.Spark**, und installieren Sie das Paket. **Microsoft.ML** wird vom Modell-Generator automatisch für Sie installiert.

### <a name="create-a-sparksession"></a>Erstellen einer SparkSession

1. Öffnen Sie die Datei *Program.cs* für **MLSparkModelML.ConsoleApp**. Diese Datei wurde vom Modell-Generator automatisch generiert. Löschen Sie die `using`-Anweisungen, die Inhalte der Main()-Methode und die `CreateSingleDataSample`-Region.

1. Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:

   ```csharp
   using System;
   using System.Collections.Generic;
   using Microsoft.ML;
   using Microsoft.ML.Data;
   using Microsoft.Spark.Sql;
   using MLSparkModelML.Model;
   ```

1. Ändern Sie `DATA_FILEPATH` in den Pfad zu Ihrer Datei *yelptest.csv*.

1. Fügen Sie der `Main`-Methode den folgenden Code hinzu, um eine neue `SparkSession` zu erstellen. Die Spark-Sitzung ist der Einstiegspunkt in die Programmierung von Spark mit der Dataset- und DataFrame-API.

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName(".NET for Apache Spark Sentiment Analysis")
        .GetOrCreate();
   ```

   Der Aufruf des oben erstellten *spark*-Objekts ermöglicht im gesamten Programm den Zugriff auf Spark- und DataFrame-Funktionalität.

### <a name="create-a-dataframe-and-print-to-console"></a>Erstellen eines DataFrame und Ausgabe an die Konsole

Lesen Sie die Yelp-Bewertungsdaten aus der Datei *yelptest.csv* als `DataFrame` ein. Verwenden Sie die Optionen `header` und `inferSchema`. Die Option `header` liest die erste Zeile von *yelptest.csv* als Spaltennamen anstelle von Daten. Mit der Option `inferSchema` werden Spaltentypen basierend auf den Daten abgeleitet.

```csharp
DataFrame df = spark
    .ReadStream()
    .Option("header", true)
    .Option("inferSchema", true)
    .Csv(DATA_FILEPATH);

df.Show();
```

### <a name="register-a-user-defined-function"></a>Registrieren einer benutzerdefinierten Funktion

Sie können in Spark-Anwendungen mithilfe *benutzerdefinierter Funktionen* Berechnungen und Analysen für Ihre Daten ausführen. In diesem Tutorial verwenden Sie ML.NET mit einer benutzerdefinierten Funktion, um jede Yelp-Bewertung auszuwerten.

Fügen Sie der `Main`-Methode den folgenden Code hinzu, um die benutzerdefinierte Funktion `MLudf` zu registrieren.

```csharp
spark.Udf()
    .Register<string, bool>("MLudf", predict);
```

Diese benutzerdefinierte Funktion verwendet eine Yelp-Bewertungszeichenfolge als Eingabe und gibt für positive oder negative Standpunkte TRUE bzw. FALSE zurück. Die Funktion verwendet die *predict()* -Methode, die Sie in einem späteren Schritt definieren.

### <a name="use-spark-sql-to-call-the-udf"></a>Verwenden von Spark SQL zum Aufrufen der benutzerdefinierten Funktion

Nachdem Sie Ihre Daten eingelesen und ML eingebunden haben, verwenden Sie Spark SQL, um die benutzerdefinierte Funktion aufzurufen, mit der eine Standpunktanalyse für jede Zeile Ihres DataFrame durchgeführt wird. Fügen Sie der `Main`-Methode den folgenden Code hinzu:

```csharp
// Use Spark SQL to call ML.NET UDF
// Display results of sentiment analysis on reviews
df.CreateOrReplaceTempView("Reviews");
DataFrame sqlDf = spark.Sql("SELECT ReviewText, MLudf(ReviewText) FROM Reviews");
sqlDf.Show();

// Print out first 20 rows of data
// Prevent data getting cut off by setting truncate = 0
sqlDf.Show(20, 0, false);

spark.Stop();
```

### <a name="create-predict-method"></a>Erstellen der predict()-Methode

Fügen Sie vor Ihrer `Main()`-Methode den folgenden Code ein. Diese Code ähnelt der Ausgabe des Modell-Generators in *ConsumeModel.cs*. Durch das Verschieben dieser Methode in Ihre Konsole wird das Modell immer dann geladen, wenn Sie Ihre App ausführen.

```csharp
private static readonly PredictionEngine<ModelInput, ModelOutput> _predictionEngine;

static Program()
{
    MLContext mlContext = new MLContext();
    ITransformer model = mlContext.Model.Load("MLModel.zip", out DataViewSchema schema);
    _predictionEngine = mlContext.Model.CreatePredictionEngine<ModelInput, ModelOutput>(model);
}

static bool predict(string text)
{
    ModelInput input = new ModelInput
    {
        ReviewText = text
    };

    return _predictionEngine.Predict(input).Prediction;
}
```

## <a name="add-the-model-to-your-console-app"></a>Hinzufügen des Modells zu Ihrer Konsolen-App

Kopieren Sie im Projektmappen-Explorer die Datei *MLModel.zip* aus dem Projekt **MLSparkModelML.Model**, und fügen Sie sie in das Projekt **MLSparkModelML.ConsoleApp** ein. Es wird automatisch ein Verweis in *MLSparkModelML.ConsoleApp.csproj* eingefügt.

## <a name="run-your-code"></a>Ausführen Ihres Codes

Verwenden Sie `spark-submit`, um Ihren Code auszuführen. Navigieren Sie mithilfe der Eingabeaufforderung zum Stammordner der App, und führen Sie die folgenden Befehle aus.

Bereinigen Sie zunächst Ihre App, und veröffentlichen Sie sie.

```dotnetcli
dotnet clean
dotnet publish
```

Navigieren Sie dann zum Veröffentlichungsordner der Konsolen-App, und führen Sie den folgenden `spark-submit`-Befehl aus. Denken Sie daran, den obigen Befehl mit dem tatsächlichen Pfad zu Ihrer JAR-Datei für Microsoft Spark zu aktualisieren.

```dotnetcli
%SPARK_HOME%\bin\spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local microsoft-spark-2-4_2.11-1.0.0.jar dotnet MLSparkModelML.ConsoleApp.dll
```

## <a name="get-the-code"></a>Abrufen des Codes

Der Code in diesem Tutorial ähnelt dem im Beispiel [Standpunktanalyse mit Big Data](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment).

## <a name="next-steps"></a>Nächste Schritte

Fahren Sie mit dem nächsten Artikel fort, um zu erfahren, wie Sie ein strukturiertes Streaming mit .NET für Apache Spark durchführen.
> [!div class="nextstepaction"]
> [Tutorial: Strukturiertes Streaming mit .NET für Apache Spark](streaming.md)
