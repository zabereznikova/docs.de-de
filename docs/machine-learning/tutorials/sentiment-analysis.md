---
title: 'Tutorial: Analysieren von Websitekommentaren – binäre Klassifizierung'
description: Dieses Tutorial zeigt Ihnen, wie Sie eine .NET Core-Konsolenanwendung erstellen, die den Standpunkt in Websitekommentaren klassifiziert und die entsprechenden Maßnahmen ergreift. Die binäre Standpunktklassifizierung verwendet C# in Visual Studio.
ms.date: 06/30/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: de8ea511b3d421e391b182a6de079b854d3f2390
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281756"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-with-binary-classification-in-mlnet"></a>Tutorial: Standpunktanalyse für Websitekommentare mit binärer Klassifikation in ML.NET

Dieses Tutorial zeigt Ihnen, wie Sie eine .NET Core-Konsolenanwendung erstellen, die den Standpunkt in Websitekommentaren klassifiziert und die entsprechenden Maßnahmen ergreift. Die binäre Standpunktklassifizierung verwendet C# in Visual Studio 2017.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> - Erstellen einer Konsolenanwendung
> - Vorbereiten von Daten
> - Laden der Daten
> - Erstellen und Trainieren des Modells
> - Evaluieren des Modells
> - Verwenden des Modells für Vorhersagen
> - Anzeigen der Ergebnisse

Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).

## <a name="prerequisites"></a>Voraussetzungen

- [Visual Studio 2017 Version 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“

- [Dataset „UCI Sentiment Labeled Sentences“](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (ZIP-Datei)

## <a name="create-a-console-application"></a>Erstellen einer Konsolenanwendung

1. Erstellen Sie eine **.NET Core-Konsolenanwendung** mit dem Namen „SentimentAnalysis“.

2. Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um die Datasetdateien zu speichern.

3. Installieren des **Microsoft.ML NuGet-Pakets**:

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie „nuget.org“ als Paketquelle aus und anschließend die Registerkarte **Durchsuchen**. Suchen Sie nach **Microsoft.ML**, wählen Sie das gewünschte Paket aus, und wählen Sie dann die Schaltfläche **Installieren** aus. Fahren Sie mit der Installation fort, indem Sie den Lizenzbedingungen für das von Ihnen gewählte Paket zustimmen.

## <a name="prepare-your-data"></a>Vorbereiten Ihrer Daten

> [!NOTE]
> Die für dieses Tutorial verwendeten Datasets stammen aus „From Group to Individual Labels using Deep Features“, Kotzias et. al., KDD 2015, und werden im UCI Machine Learning Repository – Dua, D. und Karra Taniskidou, E. gehostet. (2017). UCI Machine Learning Repository [http://archive.ics.uci.edu/ml ]. Irvine, CA: University of California, School of Information and Computer Science.

1. Laden Sie die ZIP-Datei des [Datasets „UCI Sentiment Labeled Sentences“](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) herunter, und entzippen Sie sie.

2. Kopieren Sie die `yelp_labelled.txt`-Datei in das Verzeichnis *Data*, das Sie erstellt haben.

3. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die Datei `yelp_labeled.txt`, und wählen Sie **Eigenschaften** aus. Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.

### <a name="create-classes-and-define-paths"></a>Erstellen von Klassen und Definieren von Pfaden

1. Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:

    [!code-csharp[AddUsings](./snippets/sentiment-analysis/csharp/Program.cs#AddUsings "Add necessary usings")]

1. Fügen Sie den folgenden Code in der Zeile direkt über der `Main`-Methode hinzu, um ein Feld zu erstellen, das den Dateipfad des zuletzt heruntergeladenen Datasets enthält:

    [!code-csharp[Declare global variables](./snippets/sentiment-analysis/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

1. Erstellen Sie anschließend Klassen für Ihre Eingabedaten und Vorhersagen. Fügen Sie dem Projekt eine neue Klasse hinzu:

    - Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.

    - Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentData.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.

1. Die Datei *SentimentData.cs* wird im Code-Editor geöffnet. Fügen Sie am Anfang der Datei *SentimentData.cs* die folgende `using`-Anweisung hinzu:

    [!code-csharp[AddUsings](./snippets/sentiment-analysis/csharp/SentimentData.cs#AddUsings "Add necessary usings")]

1. Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code mit den beiden Klassen `SentimentData` und `SentimentPrediction` der Datei *SentimentData.cs* hinzu:

    [!code-csharp[DeclareTypes](./snippets/sentiment-analysis/csharp/SentimentData.cs#DeclareTypes "Declare data record types")]

### <a name="how-the-data-was-prepared"></a>Vorbereitung der Daten

Die `SentimentData`-Klasse des Eingabedatasets hat eine `string` für Benutzerkommentare (`SentimentText`) und einen `bool` (`Sentiment`) Wert von entweder 1 (positiv) oder 0 (negativ) für den Standpunkt. Beide Felder haben [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29)-Attribute, die an sie angefügt sind, wodurch die Reihenfolge der Datendateien für jedes Feld beschrieben wird.  Darüber hinaus hat die `Sentiment`-Eigenschaft ein [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A)-Attribut, um es als `Label`-Feld festzulegen. Die folgende Beispieldatei verfügt nicht über eine Kopfzeile und sieht wie folgt aus:

|SentimentText                         |Standpunkt (Bezeichnung) |
|--------------------------------------|----------|
|Die Kellnerin hat etwas langsam bedient.|    0     |
|Die Kruste ist nicht gut.                    |    0     |
|Toll... Mir hat das Restaurant gefallen.              |    1     |
|Wir wurden schnell bedient.              |    1     |

`SentimentPrediction` ist die nach dem Modelltraining verwendete Vorhersageklasse. Diese erbt von `SentimentData`, sodass die Eingabe `SentimentText` zusammen mit der Ausgabevorhersage angezeigt werden kann. Der boolesche Wert `Prediction` ist der Wert, den das Modell vorhersagt, wenn für dieses eine neue Eingabe für `SentimentText` bereitgestellt wird.

Die Ausgabeklasse `SentimentPrediction` enthält zwei weitere Eigenschaften, die von dem Modell berechnet werden: `Score`, die Rohbewertung, die vom Modell berechnet wird, und `Probability`, der für die Wahrscheinlichkeit, dass der Text eine positive Stimmung vermittelt, kalibrierte Wert.

Für dieses Tutorial ist `Prediction` die wichtigste Eigenschaft.

## <a name="load-the-data"></a>Laden der Daten

Daten werden in ML.NET als [IDataView-Klasse](xref:Microsoft.ML.IDataView) dargestellt. Mit `IDataView` können Tabellendaten (Zahlen und Text) flexibel und effizient beschrieben werden. Daten können aus einer Textdatei oder in Echtzeit (z. B. aus einer SQL-Datenbank oder aus Protokolldateien) in ein `IDataView`-Objekt geladen werden.

Die [MLContext-Klasse](xref:Microsoft.ML.MLContext) ist der Ausgangspunkt für alle ML.NET-Vorgänge. Beim Initialisieren von `mlContext` wird eine neue ML.NET-Umgebung erstellt, die für alle Objekte des Workflows für die Modellerstellung gemeinsam genutzt werden kann. Die Klasse ähnelt dem Konzept von `DBContext` in Entity Framework.

Sie bereiten die App vor und laden anschließend die Daten:

1. Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` in der `Main`-Methode durch den folgenden Code, um die mlContext-Variable zu deklarieren und zu initialisieren:

    [!code-csharp[CreateMLContext](./snippets/sentiment-analysis/csharp/Program.cs#CreateMLContext "Create the ML Context")]

2. Fügen Sie den folgenden Text als nächste Codezeile in die `Main()`-Methode ein:

    [!code-csharp[CallLoadData](./snippets/sentiment-analysis/csharp/Program.cs#CallLoadData)]

3. Erstellen Sie die `LoadData()`-Methode mit dem folgenden Code direkt nach der `Main()`-Methode:

    ```csharp
    public static TrainTestData LoadData(MLContext mlContext)
    {

    }
    ```

    Die `LoadData()`-Methode führt die folgenden Aufgaben aus:

    - Laden der Daten.
    - Teilt das geladene Dataset in Trainings- und Testdatasets auf.
    - Gibt die aufgeteilten Trainings- und Testdatasets zurück.

4. Fügen Sie den folgenden Code am Ende der ersten Zeile der `LoadData()`-Methode hinzu.

    [!code-csharp[LoadData](./snippets/sentiment-analysis/csharp/Program.cs#LoadData "loading dataset")]

    Die [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)-Methode definiert das Datenschema und liest in der Datei. Diese Methode akzeptiert Datenpfadvariablen und gibt ein `IDataView`-Objekt zurück.

### <a name="split-the-dataset-for-model-training-and-testing"></a>Aufteilen des Datasets für Modelltraining und -test

Wenn Sie ein Modell vorbereiten, verwenden Sie einen Teil des Datasets, um es zu trainieren, und einen anderen Teil, um die Genauigkeit des Modells zu testen.

1. Um die geladenen Daten in die erforderlichen Datasets aufzuteilen, fügen Sie den folgenden Code als nächste Zeile in die `LoadData()`-Methode ein:

    [!code-csharp[SplitData](./snippets/sentiment-analysis/csharp/Program.cs#SplitData "Split the Data")]

    Der vorherige Code verwendet die [TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A)-Methode, um das geladene Dataset in Trainings- und Testdatasets aufzuteilen und diese in der <xref:Microsoft.ML.DataOperationsCatalog.TrainTestData>-Klasse zurückzugeben. Geben Sie den Prozentsatz der Daten des Testsatzes mit dem `testFraction`-Parameter an. Der Standard ist 10 %. In diesem Fall verwenden Sie 20 %, um mehr Daten auszuwerten.

2. Geben Sie `splitDataView` am Ende der `LoadData()`-Methode zurück:

    [!code-csharp[ReturnSplitData](./snippets/sentiment-analysis/csharp/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a>Erstellen und Trainieren des Modells

1. Fügen Sie der `BuildAndTrainModel`-Methode den folgenden Aufruf als nächste Codezeile der `Main()`-Methode hinzu:

    [!code-csharp[CallBuildAndTrainModel](./snippets/sentiment-analysis/csharp/Program.cs#CallBuildAndTrainModel)]

    Die `BuildAndTrainModel()`-Methode führt die folgenden Aufgaben aus:

    - Extrahieren und Transformieren der Daten.
    - Trainieren des Modells.
    - Vorhersagen des Standpunkts anhand der Testdaten.
    - Zurückgeben des Modells.

2. Erstellen Sie die `BuildAndTrainModel()`-Methode mit dem folgenden Code direkt nach der `Main()`-Methode:

    ```csharp
    public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
    {

    }
    ```

### <a name="extract-and-transform-the-data"></a>Extrahieren und Transformieren der Daten

1. Rufen Sie `FeaturizeText` als die nächste Codezeile auf:

    [!code-csharp[FeaturizeText](./snippets/sentiment-analysis/csharp/Program.cs#FeaturizeText "Featurize the text")]

    Die `FeaturizeText()`-Methode im vorherigen Code konvertiert die Textspalte (`SentimentText`) in eine Spalte vom Typ `Features` mit numerischem Schlüssel, die vom Machine Learning-Algorithmus verwendet wird, und fügt sie als neue Datasetspalte hinzu:

    |SentimentText                         |Standpunkt |Features              |
    |--------------------------------------|----------|----------------------|
    |Die Kellnerin hat etwas langsam bedient.|    0     |[0,76, 0,65, 0,44, …] |
    |Die Kruste ist nicht gut.                    |    0     |[0,98, 0,43, 0,54, …] |
    |Toll... Mir hat das Restaurant gefallen.              |    1     |[0,35, 0,73, 0,46, …] |
    |Wir wurden schnell bedient.              |    1     |[0,39, 0, 0,75, …]    |

### <a name="add-a-learning-algorithm"></a>Hinzufügen eines Lernalgorithmus

Diese App verwendet einen Klassifizierungsalgorithmus, der Elemente oder Datenzeilen kategorisiert. Die App kategorisiert Websitekommentare entweder als positiv oder negativ. Also verwenden Sie die binäre Klassifizierungsaufgabe.

Fügen Sie den unten aufgeführten Code als nächste Codezeilen in `BuildAndTrainModel()` ein, um die Machine Learning-Aufgabe festzulegen und ihn an die Datentransformationsdefinitionen anzufügen:

[!code-csharp[SdcaLogisticRegressionBinaryTrainer](./snippets/sentiment-analysis/csharp/Program.cs#AddTrainer "Add a SdcaLogisticRegressionBinaryTrainer")]

[SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) ist Ihr Klassifizierungsalgorithmus für das Training. Dieser wird an den `estimator` angefügt, und akzeptiert den mit Features ausgestatteten `SentimentText` (`Features`) und die `Label`-Eingabeparameter, um aus den historischen Daten zu lernen.

### <a name="train-the-model"></a>Trainieren des Modells

Fügen Sie den unten aufgeführten Code als nächste Codezeilen in die `BuildAndTrainModel()`-Methode ein, um das Modell an die `splitTrainSet`-Daten anzupassen und das trainierte Modell zurückzugeben:

[!code-csharp[TrainModel](./snippets/sentiment-analysis/csharp/Program.cs#TrainModel "Train the model")]

Mit der [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29)-Methode wird Ihr Modell trainiert, indem das Dataset transformiert und das Training angewendet wird.

### <a name="return-the-model-trained-to-use-for-evaluation"></a>Zurückgeben des für die Evaluierung trainierten Modells

 Geben Sie das Modell am Ende der `BuildAndTrainModel()`-Methode zurück:

[!code-csharp[ReturnModel](./snippets/sentiment-analysis/csharp/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a>Evaluieren des Modells

Verwenden Sie nach dem Training Ihres Modells Ihre Testdaten, um die Leistung Ihres Modells zu validieren.

1. Erstellen Sie mit dem folgenden Code die `Evaluate()`-Methode direkt nach `BuildAndTrainModel()`:

    ```csharp
    public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
    {

    }
    ```

    Die `Evaluate()`-Methode führt die folgenden Aufgaben aus:

    - Laden des Testdatasets.
    - Erstellen des Auswerters der binären Klassifizierung.
    - Evaluieren des Modells und Erstellen von Metriken.
    - Anzeigen der Metriken.

2. Fügen Sie einen Aufruf der neuen Methode aus der `Main()`-Methode mit dem folgenden Code direkt unter dem `BuildAndTrainModel()`-Methodenaufruf hinzu:

    [!code-csharp[CallEvaluate](./snippets/sentiment-analysis/csharp/Program.cs#CallEvaluate "Call the Evaluate method")]

3. Fügen Sie `Evaluate()` den folgenden Code hinzu, um die `splitTestSet`-Daten zu transformieren:

    [!code-csharp[PredictWithTransformer](./snippets/sentiment-analysis/csharp/Program.cs#TransformData "Predict using the Transformer")]

    Der vorherige Code verwendet die [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A)-Methode trifft Vorhersagen für mehrere bereitgestellte Eingabezeilen eines Testdatasets.

4. Fügen Sie den unten aufgeführten Code als nächste Codezeile in die `Evaluate()`-Methode ein, um das Modell auszuwerten:

    [!code-csharp[ComputeMetrics](./snippets/sentiment-analysis/csharp/Program.cs#Evaluate "Compute Metrics")]

Nach der Vorhersagekonfiguration (`predictions`) wertet die [Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A)-Methode das Modell aus. Dabei werden die Vorhersagewerte mit den tatsächlichen `Labels` im Testdataset verglichen und die [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) für das Modell zurückgegeben.

### <a name="displaying-the-metrics-for-model-validation"></a>Anzeigen der Metriken zur Modellvalidierung

Zeigen Sie die Metriken mithilfe des folgenden Codes an:

[!code-csharp[DisplayMetrics](./snippets/sentiment-analysis/csharp/Program.cs#DisplayMetrics "Display selected metrics")]

- Die `Accuracy`-Metrik ermittelt die Genauigkeit eines Modells, d.h. den Anteil der korrekten Vorhersagen im Testsatz.

- Die `AreaUnderRocCurve`-Metrik gibt an, wie sicher das Modell die positiven und negativen Klassen korrekt klassifiziert. Sie möchten, dass der `AreaUnderRocCurve` so nah wie möglich bei 1 liegt.

- Die `F1Score`-Metrik ermittelt den F1-Score des Modells, der ein Maß für das Gleichgewicht zwischen [Genauigkeit](../resources/glossary.md#precision) und [Wiederkennung](../resources/glossary.md#recall) ist.  Sie möchten, dass der `F1Score` so nah wie möglich bei 1 liegt.

### <a name="predict-the-test-data-outcome"></a>Vorhersagen der Testdatenergebnisse

1. Erstellen Sie die `UseModelWithSingleItem()`-Methode mit dem folgenden Code direkt nach der `Evaluate()`-Methode:

    ```csharp
    private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
    {

    }
    ```

    Die `UseModelWithSingleItem()`-Methode führt die folgenden Aufgaben aus:

    - Erstellen eines einzelnen Kommentars aus Testdaten.
    - Vorhersagen des Standpunkts anhand der Testdaten.
    - Kombinieren von Testdaten und Vorhersagen für die Berichterstattung.
    - Anzeigen der vorhergesagten Ergebnisse.

2. Fügen Sie einen Aufruf der neuen Methode aus der `Main()`-Methode mit dem folgenden Code direkt unter dem `Evaluate()`-Methodenaufruf hinzu:

    [!code-csharp[CallUseModelWithSingleItem](./snippets/sentiment-analysis/csharp/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

3. Fügen Sie den folgenden Code hinzu, um die erste Zeile in der `UseModelWithSingleItem()`-Methode zu erstellen:

    [!code-csharp[CreatePredictionEngine](./snippets/sentiment-analysis/csharp/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]

    Die [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) ist eine Hilfs-API, mit der Sie eine Vorhersage für eine einzelne Instanz der Daten treffen können. [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) ist nicht threadsicher. Die Verwendung in Singlethread-oder Prototypumgebungen ist zulässig. Zur Verbesserung der Leistung und Threadsicherheit in Produktionsumgebungen verwenden Sie den `PredictionEnginePool`-Dienst, der einen [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) aus [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)-Objekten für die Verwendung in Ihrer gesamten Anwendung erstellt. Informationen zur [Verwendung von `PredictionEnginePool` in einer ASP.NET Core-Web-API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application) finden Sie in dieser Anleitung.

    > [!NOTE]
    > Die `PredictionEnginePool`-Diensterweiterung ist derzeit als Vorschauversion verfügbar.

4. Fügen Sie einen Kommentar hinzu, um die Vorhersage des trainierten Modells in der `UseModelWithSingleItem()`-Methode zu testen, indem Sie eine `SentimentData`-Instanz erstellen:

    [!code-csharp[PredictionData](./snippets/sentiment-analysis/csharp/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

5. Übergeben Sie die Testkommentardaten an die [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602), indem Sie Folgendes als nächste Codezeilen in der `UseModelWithSingleItem()`-Methode hinzufügen:

    [!code-csharp[Predict](./snippets/sentiment-analysis/csharp/Program.cs#Predict "Create a prediction of sentiment")]

    Die [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A)-Funktion trifft eine Vorhersage für eine einzelne Datenzeile.

6. Mithilfe des folgenden Codes können Sie den `SentimentText` und den dazugehörige Standpunkt anzeigen:

    [!code-csharp[OutputPrediction](./snippets/sentiment-analysis/csharp/Program.cs#OutputPrediction "Display prediction output")]

## <a name="use-the-model-for-prediction"></a>Verwenden des Modells für eine Vorhersage

### <a name="deploy-and-predict-batch-items"></a>Bereitstellen und Vorhersagen von Batchelementen

1. Erstellen Sie die `UseModelWithBatchItems()`-Methode mit dem folgenden Code direkt nach der `UseModelWithSingleItem()`-Methode:

    ```csharp
    public static void UseModelWithBatchItems(MLContext mlContext, ITransformer model)
    {

    }
    ```

    Die `UseModelWithBatchItems()`-Methode führt die folgenden Aufgaben aus:

    - Erstellen von Batchtestdaten.
    - Vorhersagen des Standpunkts anhand der Testdaten.
    - Kombinieren von Testdaten und Vorhersagen für die Berichterstattung.
    - Anzeigen der vorhergesagten Ergebnisse.

2. Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `UseModelWithSingleItem()`-Methodenaufruf hinzu:

    [!code-csharp[CallPredictModelBatchItems](./snippets/sentiment-analysis/csharp/Program.cs#CallUseModelWithBatchItems "Call the CallUseModelWithBatchItems method")]

3. Fügen Sie einige Kommentare zum Testen der Vorhersagen des trainierten Modells in der `UseModelWithBatchItems()`-Methode hinzu:

    [!code-csharp[PredictionData](./snippets/sentiment-analysis/csharp/Program.cs#CreateTestIssues "Create test data for predictions")]

### <a name="predict-comment-sentiment"></a>Vorhersagen des Standpunkts in einem Kommentar

Verwenden Sie das Modell, um den Standpunkt der Kommentardaten mit der [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A)-Methode vorherzusagen:

[!code-csharp[Predict](./snippets/sentiment-analysis/csharp/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="combine-and-display-the-predictions"></a>Kombinieren und Anzeigen von Vorhersagen

Erstellen Sie mit dem folgenden Code einen Header für die Vorhersagen:

[!code-csharp[OutputHeaders](./snippets/sentiment-analysis/csharp/Program.cs#AddInfoMessage "Display prediction outputs")]

Da `SentimentPrediction` von `SentimentData` geerbt wird, füllt die `Transform()`-Methode den `SentimentText` mit den vorhergesagten Feldern aus. Im Laufe des ML.NET-Prozesses fügt jede Komponente Spalten hinzu, sodass die Ergebnisse leicht angezeigt werden können:

[!code-csharp[DisplayPredictions](./snippets/sentiment-analysis/csharp/Program.cs#DisplayResults "Display the predictions")]

## <a name="results"></a>Ergebnisse

Die Ergebnisse sollten den unten dargestellten ähneln. Während der Verarbeitung werden Meldungen angezeigt. Sie können Warnungen oder Verarbeitungsmeldungen sehen. Diese wurden der Übersichtlichkeit halber aus den folgenden Ergebnissen entfernt.

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 83.96%
Auc: 90.51%
F1Score: 84.04%

=============== End of model evaluation ===============

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This was a very bad steak | Prediction: Negative | Probability: 0.1027377
=============== End of Predictions ===============

=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This was a horrible meal | Prediction: Negative | Probability: 0.1369192
Sentiment: I love this spaghetti. | Prediction: Positive | Probability: 0.9960636
=============== End of predictions ===============

=============== End of process ===============
Press any key to continue . . .

```

Herzlichen Glückwunsch! Sie haben jetzt erfolgreich ein Machine Learning-Modell zum Klassifizieren und Vorhersagen von Standpunkten in Mitteilungen erstellt.

Erfolgreiche Modelle zu erstellen ist ein iterativer Prozess. Dieses Modell hat erst geringere Qualität, da das Tutorial kleine Datasets verwendet, um schnelles Modelltraining zu ermöglichen. Wenn Sie nicht mit der Modellqualität zufrieden sind, können Sie versuchen, sie durch die Bereitstellung größerer Trainingsdatasets oder die Auswahl anderer Trainingsalgorithmen mit anderen [Hyperparametern](../resources/glossary.md#hyperparameter) für jeden Algorithmus zu verbessern.

Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> - Erstellen einer Konsolenanwendung
> - Vorbereiten von Daten
> - Laden der Daten
> - Erstellen und Trainieren des Modells
> - Evaluieren des Modells
> - Verwenden des Modells für Vorhersagen
> - Anzeigen der Ergebnisse

Wechseln Sie zum nächsten Tutorial, um mehr zu erfahren.
> [!div class="nextstepaction"]
> [Klassifizierung von Issues](github-issue-classification.md)
