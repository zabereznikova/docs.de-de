---
title: 'Tutorial: Analysieren der Überprüfungsstimmung mithilfe eines TensorFlow-Modells'
description: In diesem Tutorial wird gezeigt, wie Sie ein vortrainiertes TensorFlow-Modell verwenden, um die Stimmung in Websitekommentaren zu klassifizieren. Der binäre Stimmungsklassifizierer ist eine C#-Konsolenanwendung, die mit Visual Studio entwickelt wurde.
ms.date: 11/15/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 7a6043f56a2ecaca633ba5545170f27a85a22efc
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092394"
---
# <a name="tutorial-analyze-sentiment-of-movie-reviews-using-a-pre-trained-tensorflow-model-in-mlnet"></a>Tutorial: Analysieren der Stimmung von Filmkritiken mithilfe eines vortrainierten TensorFlow-Modells in ML.NET

In diesem Tutorial wird gezeigt, wie Sie ein vortrainiertes TensorFlow-Modell verwenden, um die Stimmung in Websitekommentaren zu klassifizieren. Der binäre Stimmungsklassifizierer ist eine C#-Konsolenanwendung, die mit Visual Studio entwickelt wurde.

Das in diesem Tutorial verwendete TensorFlow-Modell wurde mithilfe der Filmkritiken aus der IMDB-Datenbank trainiert. Sobald Sie die Entwicklung der Anwendung abgeschlossen haben, können Sie Filmkritiktext bereitstellen. Die Anwendung informiert Sie dann, ob die Rezension eine positive oder negative Stimmung hat.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> * Laden eines vortrainierten TensorFlow-Modells
> * Umwandeln von Websitekommentartext in für das Modell geeignete Merkmale
> * Verwenden des Modells für Vorhersagen

Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF).

## <a name="prerequisites"></a>Voraussetzungen

* [Visual Studio 2017 Version 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.

## <a name="setup"></a>Setup

### <a name="create-the-application"></a>Erstellen der Anwendung

1. Erstellen Sie eine **.NET Core-Konsolenanwendung** mit dem Namen „TextClassificationTF“.

2. Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um die Datasetdateien zu speichern.

3. Installieren des **Microsoft.ML NuGet-Pakets**:

    Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie „nuget.org“ als Paketquelle aus und anschließend die Registerkarte **Durchsuchen**. Suchen Sie nach **Microsoft.ML**, wählen Sie das gewünschte Paket aus, und wählen Sie dann die Schaltfläche **Installieren** aus. Fahren Sie mit der Installation fort, indem Sie den Lizenzbedingungen für das von Ihnen gewählte Paket zustimmen. Wiederholen Sie diese Schritte für **Microsoft.ML.TensorFlow** und **SciSharp.TensorFlow.Redist**.

### <a name="add-the-tensorflow-model-to-the-project"></a>Hinzufügen des TensorFlow-Modells zum Projekt

> [!NOTE]
> Das Modell für dieses Tutorial stammt aus dem GitHub-Repository [dotnet/machinelearning-testdata](https://github.com/dotnet/machinelearning-testdata/tree/master/Microsoft.ML.TensorFlow.TestModels/sentiment_model). Das Modell weist das SavedModel-Format von TensorFlow auf.

1. Laden Sie die ZIP-Datei [sentiment_model](https://github.com/dotnet/samples/blob/master/machine-learning/models/textclassificationtf/sentiment_model.zip?raw=true) herunter, und entpacken Sie sie.

    Die ZIP-Datei enthält Folgendes:

    * `saved_model.pb`: Das TensorFlow-Modell selbst. Das Modell nimmt ein Integerarray mit einer festen Länge (Größe 600) von Merkmalen an, die den Text in einer IMDB-Kritikzeichenfolge darstellen, und gibt zwei Wahrscheinlichkeiten aus, die die Summe 1 bilden: die Wahrscheinlichkeit, dass die Eingabekritik eine positive Stimmung aufweist, und die Wahrscheinlichkeit, dass die Eingabekritik eine negative Stimmung hat.
    * `imdb_word_index.csv`: Eine Zuordnung von einzelnen Wörtern zu einem ganzzahligen Wert. Die Zuordnung wird verwendet, um die Eingabemerkmale für das TensorFlow-Modell zu generieren.

2. Kopieren Sie den Inhalt des innersten `sentiment_model`-Verzeichnisses in Ihr *TextClassificationTF*-Projektverzeichnis `sentiment_model`. Dieses Verzeichnis enthält das Modell und die zusätzlich für dieses Tutorial erforderlichen Unterstützungsdateien wie in der folgenden Abbildung gezeigt:

   ![Inhalt des Verzeichnisses „sentiment_model“](./media/text-classification-tf/sentiment-model-files.png)

3. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf jede Datei im Verzeichnis `sentiment_model`und im Unterverzeichnis, und wählen Sie **Eigenschaften** aus. Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.

### <a name="add-using-statements-and-global-variables"></a>Hinzufügen von using-Anweisungen und globalen Variablen

1. Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:

   [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TextClassificationTF/Program.cs#AddUsings "Add necessary usings")]

1. Erstellen Sie zwei globale Variablen direkt über der `Main`-Methode, um den gespeicherten Pfad der Modelldatei sowie die Länge des Merkmalsvektors aufzunehmen.

   [!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TextClassificationTF/Program.cs#DeclareGlobalVariables "Declare global variables")]

    * `_modelPath` ist der Dateipfad des trainierten Modells.
    * `FeatureLength` ist die Länge des ganzzahligen Merkmalsarrays, das vom Modell erwartet wird.

### <a name="model-the-data"></a>Modellieren der Daten

Filmkritiken sind Freiformtext. Ihre Anwendung konvertiert den Text in das vom Modell erwartete Eingabeformat in einer Reihe diskreter Schritte.

Der erste besteht darin, den Text in separate Wörter aufzuteilen und die bereitgestellte Zuordnungsdatei zu verwenden, um jedes Wort einer ganzzahligen Codierung zuzuordnen. Das Ergebnis dieser Transformation ist ein Intergerarray variabler Länge mit einer Länge, die der Anzahl der Wörter im Satz entspricht.

|Eigenschaft| Wert|Typ|
|-------------|-----------------------|------|
|ReviewText|this film is really good|string|
|VariableLengthFeatures|14,22,9,66,78,... |int[]|

Die Größe des Merkmalsarrays variabler Länge wird dann in eine feste Länge von 600 geändert. Dies ist die Länge, die das TensorFlow-Modell erwartet.

|Eigenschaft| Wert|Typ|
|-------------|-----------------------|------|
|ReviewText|this film is really good|string|
|VariableLengthFeatures|14,22,9,66,78,... |int[]|
|Features|14,22,9,66,78,... |int[600]|

1. Erstellen Sie eine Klasse für Ihre Eingabedaten nach der `Main`-Methode:

    [!code-csharp[MovieReviewClass](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#MovieReviewClass "Declare movie review type")]

    Die Eingabedatenklasse (`MovieReview`) verfügt über ein `string`-Element für Benutzerkommentare (`ReviewText`).

1. Erstellen Sie nach der `Main`-Methode eine Klasse für die Merkmale mit variabler Länge:

    [!code-csharp[VariableLengthFeatures](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#VariableLengthFeatures "Declare variable length features type")]

    Die `VariableLengthFeatures`-Eigenschaft verfügt über ein Attribut [VectorType](xref:Microsoft.ML.Data.VectorTypeAttribute.%23ctor%2A), um sie als Vektor festzulegen.  Alle Vektorelemente müssen denselben Typ aufweisen. In Datasets mit einer großen Anzahl von Spalten verringert das Laden mehrerer Spalten als einzelner Vektor die Anzahl der Datenübergabevorgänge, wenn Sie Datentransformationen anwenden.

    Diese Klasse wird in der `ResizeFeatures`-Aktion verwendet. Die Namen ihrer Eigenschaften (in diesem Fall nur ein Name) werden verwendet, um anzugeben, welche Spalten in der DataView als _Eingabe_ für die benutzerdefinierte Zuordnungsaktion verwendet werden können.

1. Erstellen Sie nach der `Main`-Methode eine Klasse für die Merkmale mit fester Länge:

    [!code-csharp[FixedLengthFeatures](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#FixedLengthFeatures)]

    Diese Klasse wird in der `ResizeFeatures`-Aktion verwendet. Die Namen ihrer Eigenschaften (in diesem Fall nur ein Name) werden verwendet, um anzugeben, welche Spalten in der DataView als _Ausgabe_ für die benutzerdefinierte Zuordnungsaktion verwendet werden können.

    Beachten Sie, dass der Name der `Features`-Eigenschaft durch das TensorFlow-Modell bestimmt wird. Der Name dieser Eigenschaft kann nicht geändert werden.

1. Erstellen Sie eine Klasse für die Vorhersage nach der `Main`-Methode:

    [!code-csharp[Prediction](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#Prediction "Declare prediction class")]

    `MovieReviewSentimentPrediction` ist die nach dem Modelltraining verwendete Vorhersageklasse. `MovieReviewSentimentPrediction` weist ein einzelnes `float`-Array (`Prediction`) und ein `VectorType`-Attribut auf.

### <a name="create-the-mlcontext-lookup-dictionary-and-action-to-resize-features"></a>Erstellen von der MLContext-Klasse, des Nachschlagewörterbuchs und der Aktion zum Ändern der Größe von Merkmalen

Die [MLContext-Klasse](xref:Microsoft.ML.MLContext) ist der Ausgangspunkt für alle ML.NET-Vorgänge. Beim Initialisieren von `mlContext` wird eine neue ML.NET-Umgebung erstellt, die für alle Objekte des Workflows für die Modellerstellung gemeinsam genutzt werden kann. Die Klasse ähnelt dem Konzept von `DBContext` in Entity Framework.

1. Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` in der `Main`-Methode durch den folgenden Code, um die mlContext-Variable zu deklarieren und zu initialisieren:

   [!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CreateMLContext "Create the ML Context")]

1. Erstellen Sie ein Wörterbuch, um Wörter als Integerwerte zu codieren, indem Sie die [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A)-Methode zum Laden von Zuordnungsdaten aus einer Datei verwenden, wie in der folgenden Tabelle gezeigt:

    |Word     |Index    |
    |---------|---------|
    |kids     |  362    |
    |want     |  181    |
    |wrong    |  355    |
    |effects  |  302    |
    |feeling  |  547    |

    Fügen Sie den folgenden Code hinzu, um die Nachschlagezuordnung zu erstellen:

    [!code-csharp[CreateLookupMap](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CreateLookupMap)]

1. Fügen Sie mit den nächsten Codezeilen eine `Action` hinzu, um die Größe des Wortintegerarrays variabler Länge in ein Integerarray fester Größe zu ändern:

   [!code-csharp[ResizeFeatures](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#ResizeFeatures)]

## <a name="load-the-pre-trained-tensorflow-model"></a>Laden des vortrainierten TensorFlow-Modells

1. Fügen Sie Code hinzu, um das TensorFlow-Modell zu laden:

    [!code-csharp[LoadTensorFlowModel](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#LoadTensorFlowModel)]

    Nachdem das Modell geladen wurde, können Sie sein Eingabe- und Ausgabeschema extrahieren. Die Schemas werden nur aus Interesse und zu Lernzwecken angezeigt. Sie benötigen diesen Code nicht, damit die endgültige Anwendung funktioniert:

    [!code-csharp[GetModelSchema](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#GetModelSchema)]

    Das Eingabeschema ist das Array fester Länge von ganzzahlig codierten Wörtern. Das Ausgabeschema ist ein Floatarray von Wahrscheinlichkeiten, das angibt, ob die Stimmung einer Kritik negativ oder positiv ist. Die Summe dieser Werte ist 1, da die Wahrscheinlichkeit, dass die Kritik positiv ist, das Komplement für die Wahrscheinlichkeit ist, dass die Stimmung negativ ist.

## <a name="create-the-mlnet-pipeline"></a>Erstellen der ML.NET-Pipeline

1. Erstellen Sie die Pipeline, und teilen Sie den Eingabetext mithilfe der Transformation [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) in der nächsten Codezeile in Wörter auf:

   [!code-csharp[TokenizeIntoWords](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#TokenizeIntoWords)]

   Die Transformation [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) verwendet Leerzeichen, um den Text bzw. die Zeichenfolge in Wörter zu analysieren. Sie erstellt eine neue Spalte und teilt jede Eingabezeichenfolge in einen Vektor von Teilzeichenfolgen basierend auf dem benutzerdefinierten Trennzeichen auf.

1. Ordnen Sie die Wörter mithilfe der Nachschlagetabelle, die Sie oben deklariert haben, ihrer Integercodierung zu:

    [!code-csharp[MapValue](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#MapValue)]

1. Ändern Sie die Größe der Integercodierungen variabler Länge in die für das Modell erforderliche feste Länge:

    [!code-csharp[CustomMapping](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CustomMapping)]

1. Klassifizieren Sie die Eingabe mit dem geladenen TensorFlow-Modell:

    [!code-csharp[ScoreTensorFlowModel](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#ScoreTensorFlowModel)]

    Die Ausgabe des TensorFlow-Modells wird als `Prediction/Softmax` bezeichnet. Beachten Sie, dass der Name `Prediction/Softmax` durch das TensorFlow-Modell bestimmt wird. Dieser Name kann nicht geändert werden.

1. Erstellen Sie eine neue Spalte für die Ausgabevorhersage:

    [!code-csharp[SnippetCopyColumns](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#SnippetCopyColumns)]

    Sie müssen die `Prediction/Softmax`-Spalte in eine Spalte mit einem Namen kopieren, der als Eigenschaft in einer C#-Klasse verwendet werden kann: `Prediction`. Das Zeichen `/` ist in einem C# Eigenschaftsnamen unzulässig.

## <a name="create-the-mlnet-model-from-the-pipeline"></a>Erstellen des ML.NET-Modells aus der Pipeline

1. Fügen Sie den Code hinzu, um das Modell aus der Pipeline zu erstellen:

    [!code-csharp[SnippetCreateModel](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#SnippetCreateModel)]

    Ein ML.NET-Modell wird aus der Kette der Kalkulatoren in der Pipeline erstellt, indem die `Fit`-Methode aufgerufen wird. In diesem Fall passen wir keine Daten an, um das Modell zu erstellen, da das TensorFlow-Modell bereits vortrainiert wurde. Wir stellen ein leeres Datenansichtsobjekt bereit, um die Anforderungen der `Fit`-Methode zu erfüllen.

## <a name="use-the-model-to-make-a-prediction"></a>Verwenden des Modells für Vorhersagen

1. Fügen Sie die `PredictSentiment`-Methode unter der `Main`-Methode hinzu:

    ```csharp
    public static void PredictSentiment(MLContext mlContext, ITransformer model)
    {

    }
    ```

1. Fügen wir den folgenden Code hinzu, um die `PredictionEngine` als erste Zeile in der `PredictSentiment()`-Methode zu erstellen:

    [!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CreatePredictionEngine)]

    Die [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) ist eine Hilfs-API, mit der Sie eine Vorhersage für eine einzelne Instanz der Daten treffen können. [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) ist nicht threadsicher. Die Verwendung in Singlethread-oder Prototypumgebungen ist zulässig. Zur Verbesserung der Leistung und Threadsicherheit in Produktionsumgebungen verwenden Sie den `PredictionEnginePool`-Dienst, der einen [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) aus [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)-Objekten für die Verwendung in Ihrer gesamten Anwendung erstellt. Informationen zur [Verwendung von `PredictionEnginePool` in einer ASP.NET Core-Web-API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application) finden Sie in dieser Anleitung.

    > [!NOTE]
    > Die `PredictionEnginePool`-Diensterweiterung ist derzeit als Vorschauversion verfügbar.

1. Fügen Sie einen Kommentar hinzu, um die Vorhersage des trainierten Modells in der `Predict()`-Methode zu testen, indem Sie eine `MovieReview`-Instanz erstellen:

    [!code-csharp[CreateTestData](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CreateTestData)]

1. Übergeben Sie die Testkommentardaten an die `Prediction Engine`, indem Sie die folgenden Codezeilen in der `PredictSentiment()`-Methode hinzufügen:

    [!code-csharp[Predict](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#Predict)]

1. Die [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A)-Funktion trifft eine Vorhersage für eine einzelne Datenzeile:

    |Eigenschaft| Wert|Typ|
    |-------------|-----------------------|------|
    |Vorhersage|[0,5459937, 0,454006255]|float[]|

1. Mithilfe des folgenden Codes können Sie die Stimmungsvorhersage anzeigen:

    [!code-csharp[DisplayPredictions](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#DisplayPredictions)]

1. Fügen Sie am Ende der `Main`-Methode einen Aufruf von `PredictSentiment` hinzu:

    [!code-csharp[CallPredictSentiment](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CallPredictSentiment)]

## <a name="results"></a>Ergebnisse

Erstellen Sie Ihre Anwendung, und führen Sie sie aus.

Die Ergebnisse sollten den unten dargestellten ähneln. Während der Verarbeitung werden Meldungen angezeigt. Sie können Warnungen oder Verarbeitungsmeldungen sehen. Diese Nachrichten wurden der Übersichtlichkeit halber aus den folgenden Ergebnissen entfernt.

```console
Number of classes: 2
Is sentiment/review positive ? Yes
```

Herzlichen Glückwunsch! Sie haben jetzt erfolgreich ein Machine Learning-Modell zum Klassifizieren und Vorhersagen von Stimmungen in Mitteilungen durch die Wiederverwendung eines vortrainierten `TensorFlow`-Modells in ML.NET erstellt.

Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF).

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> * Laden eines vortrainierten TensorFlow-Modells
> * Umwandeln von Websitekommentartext in für das Modell geeignete Merkmale
> * Verwenden des Modells für Vorhersagen
