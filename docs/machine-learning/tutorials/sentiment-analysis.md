---
title: Verwenden von ML.NET in einem Standpunktanalyse-Szenario mit binärer Klassifizierung
description: Erfahren Sie, wie Sie ML.NET in einem Szenario mit binärer Klassifizierung verwenden, um zu erfahren, wie Sie die Standpunktvorhersage verwenden, um die geeignete Aktion auszuführen.
ms.date: 06/04/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 898b4664120b6eeb0ef18aac3acdc94b0ca0bacd
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2018
ms.locfileid: "36314837"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a>Tutorial: Verwenden von ML.NET in einem Standpunktanalyse-Szenario mit binärer Klassifizierung

> [!NOTE]
> Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden. Weitere Informationen finden Sie in [der ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Dieses Beispieltutorial veranschaulicht das Verwenden von ML.NET zum Erstellen eines Standpunktklassifizierers über eine .NET Core-Konsolenanwendung mithilfe von C# in Visual Studio 2017.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> * Das Problem verstehen
> * Auswählen der entsprechenden Machine Learning-Aufgabe
> * Vorbereiten Ihrer Daten
> * Erstellen der Lernpipeline
> * Laden eines Klassifizierers
> * Trainieren des Modells
> * Auswerten des Modells mit einem anderen Dataset
> * Vorhersagen der Testdatenergebnisse mit dem Modell

## <a name="sentiment-analysis-sample-overview"></a>Übersicht über das Standpunktanalyse-Beispiel

Das Beispiel ist eine Konsolen-App, die ML.NET verwendet, um ein Modell zu trainieren, das den Standpunkt als positiv oder negativ klassifiziert und vorhersagt. Sie wertet das Modell auch mit einem zweiten Dataset für die Qualitätsanalyse aus. Die Standpunktdatasets stammen aus dem Projekt WikiDetox.

## <a name="prerequisites"></a>Erforderliche Komponenten

* [Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.

* Die [tabstoppgetrennte Wikipedia-Detox-Zeilendatendatei (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).
* Die [tabstoppgetrennte Wikipedia-Detox-Zeilentestdatei (wikiPedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).

## <a name="machine-learning-workflow"></a>Machine Learning-Workflow

Dieses Tutorial folgt einem Machine Learning-Workflow, der den geordneten Ablauf des Prozesses ermöglicht.

Die Workflowphasen lauten wie folgt:

1. **Verstehen des Problems**
2. **Erfassen der Daten**
3. **Vorverarbeitung der Daten und Feature Engineering**
4. **Trainieren und Vorhersagen des Modells**
5. **Evaluieren des Modells**
6. **Operationalisierung des Modells**

### <a name="understand-the-problem"></a>Das Problem verstehen

Sie müssen das Problem zuerst verstehen, damit Sie es in Teile aufschlüsseln können, die das Erstellen und Trainieren des Modells erleichtern. Schlüsseln Sie das Problem auf, um die Ergebnisse vorherzusagen und auszuwerten.

Das Problem besteht bei diesem Tutorial darin, aus den auf der Website eingehenden Kommentaren den Standpunkt zu ermitteln, um die geeignete Aktion auszuführen.

Sie können das Problem nach dem Standpunkttext und dem Standpunktwert für die Daten aufschlüsseln, mit denen Sie das Modell trainieren möchten, und einem vorhergesagten Standpunktwert, den Sie auswerten und dann praktisch verwenden können.

Sie müssen dann den Standpunkt **bestimmen**, was Ihnen die Auswahl der Machine Learning-Aufgabe erleichtert.

## <a name="select-the-appropriate-machine-learning-task"></a>Auswählen der entsprechenden Machine Learning-Aufgabe

Von diesem Problem kennen Sie die folgenden Fakten:

Trainingsdaten: Websitekommentare können positiv oder negativ sein (**Standpunkt**).
Sagen Sie den **Standpunkt** eines neuen Websitekommentars voraus, positiv oder negativ, wie in den folgenden Beispielen:

* Bitte schreiben Sie keinen Unsinn in Wikipedia.
* Er ist der beste, und das müsste der Artikel hervorheben.

Die Machine Learning-Aufgabe zum Klassifizieren eignet sich optimal für dieses Szenario.

### <a name="about-the-classification-task"></a>Informationen zur Klassifizierungsaufgabe

Die Klassifizierung ist eine Machine Learning-Aufgabe, die Daten zum **Bestimmen** von Kategorie, Typ oder Klasse eines Elements oder einer Datenzeile verwendet. Beispielsweise können Sie mit der Klassifizierung:

* Einen Standpunkt als positiv oder negativ identifizieren.
* E-Mails als Spam, Junk oder gut klassifizieren.
* Bestimmen, ob die Gewebeprobe eines Patienten Krebszellen enthält.
* Kunden nach ihrer Neigung kategorisieren, auf eine Werbekampagne zu reagieren.

Klassifizierungsaufgaben zählen häufig zu einem der folgenden Typen:

* Binär: entweder A oder B.
* Multiklasse: mehrere Kategorien, die mit einem einzelnen Modell vorhergesagt werden können.

## <a name="create-a-console-application"></a>Erstellen einer Konsolenanwendung

1. Öffnen Sie Visual Studio 2017. Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus. Klicken Sie im Dialogfeld *Neues Projekt** auf den Knoten **Visual C#** und anschließend auf den Knoten **.NET Core**. Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)**. Geben Sie „SentimentAnalysis“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.

2. Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um die Datasetdateien zu speichern:

    Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus. Geben Sie „Data“ ein, und drücken Sie die EINGABETASTE.

3. Installieren des **Microsoft.ML NuGet-Pakets**:

    Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte „Durchsuchen“ aus, suchen Sie nach **Microsoft.ML**, und wählen Sie das Paket in der Liste sowie anschließend die Schaltfläche **Installieren** aus. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.

### <a name="prepare-your-data"></a>Vorbereiten Ihrer Daten

1. Laden Sie die Datasets [WikiPedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) und [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) herunter, und speichern Sie sie im zuvor erstellten Ordner *Data*. Das erste Dataset trainiert das Machine Learning-Modell, und das zweite kann verwendet werden, um zu evaluieren, wie genau das Modell ist.

2. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die \*.tsv-Dateien, und wählen Sie **Eigenschaften** aus. Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Immer**.

### <a name="create-classes-and-define-paths"></a>Erstellen von Klassen und Definieren von Pfaden

Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#1 "Add necessary usings")]

Sie müssen drei globale Variablen erstellen, die den Pfad zu den zuletzt heruntergeladenen Dateien enthalten:

* `_dataPath` enthält den Pfad zu dem Dataset, das zum Trainieren des Modells verwendet wird.
* `_testDataPath` enthält den Pfad zu dem Dataset, das zum Evaluieren des Modells verwendet wird.
* `_modelPath` enthält den Pfad zu dem Speicherort, in dem das trainierte Modell gespeichert ist.

Fügen Sie den folgenden Code der Zeile direkt oberhalb der `Main`-Methode hinzu, um die zuletzt heruntergeladenen Dateien anzugeben:

[!code-csharp[Declare file variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#2 "Declare variables to store data files")]

Sie müssen einige Klassen für die Eingabedaten und Vorhersagen erstellen. Fügen Sie dem Projekt eine neue Klasse hinzu:

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.

1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentData.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.

    Die Datei *SentimentData.cs* wird im Code-Editor geöffnet. Fügen Sie am Anfang der Datei *SentimentData.cs* die folgende `using`-Anweisung hinzu:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#1 "Add necessary usings")]

Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code mit den beiden Klassen `SentimentData` und `SentimentPrediction` der Datei *SentimentData.cs* hinzu:

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#2 "Declare data record types")]

`SentimentData` ist die Klasse des Eingabedatasets und verfügt über eine `float`-Variable (`Sentiment`), die einen entweder positiven oder negativen Wert für den Standpunkt enthält, und eine String-Variable für den Kommentar (`SentimentText`). Beiden Feldern sind `Column`-Attribute angefügt. Dieses Attribut beschreibt die Reihenfolge der Felder in der Datendatei, und welches das `Label`-Feld ist. Die `SentimentPrediction`-Klasse wird für die Vorhersage verwendet, nachdem das Modell trainiert wurde. Er verfügt über einen einzelnen booleschen Wert (`Sentiment`) und ein `PredictedLabel` `ColumnName`-Attribut. Das `Label` dient zum Erstellen und Trainieren des Modells, und es wird auch mit einem zweiten Dataset verwendet, um das Modell zu evaluieren. Das `PredictedLabel` wird während der Vorhersage und Evaluierung verwendet. Für die Evaluierung werden eine Eingabe mit Trainingsdaten, die vorhergesagten Werte und das Modell verwendet.

Ändern Sie in der Datei *Program.cs* die Signatur der `Main`-Methode durch Ersetzen von `void` mit `async Task`, wie im folgenden Beispiel gezeigt:

```csharp
static async Task Main(string[] args) 
{

}
```

Fügen Sie `async` zu `Main` mit einem <xref:System.Threading.Tasks.Task>-Rückgabetyp hinzu, da Sie das Modell später in einer ZIP-Datei speichern, und das Programm warten muss, bis diese externe Aufgabe abgeschlossen ist.

> [!NOTE]
> Mithilfe einer *async main*-Methode können Sie `await` in Ihrer `Main`-Methode verwenden. Weitere Informationen finden Sie im C#-Programmierhandbuch im Thema [Main() und Befehlszeilenargumente (C#-Programmierhandbuch)](../../../docs/csharp/programming-guide/main-and-command-args/index.md) .

Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` mit dem folgenden Code in der `Main`-Methode:

[!code-csharp[Train](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#3 "Train your model")]

Die `Train`-Methode führt die folgenden Aufgaben aus:

* Laden oder Erfassen der Daten.
* Vorverarbeitung und Featurebereitstellung der Daten.
* Trainieren des Modells.
* Vorhersagen des Standpunkts anhand der Testdaten.

Erstellen Sie die `Train`-Methode direkt nach der `Main`-Methode mit dem folgenden Code:

```csharp
public static async Task<PredictionModel<SentimentData, SentimentPrediction>> Train()
{

}
```

## <a name="ingest-the-data"></a>Erfassen der Daten

Initialisieren Sie eine neue Instanz der <xref:Microsoft.ML.LearningPipeline>, die das Laden von Daten, Datenverarbeitung/-featurebereitstellung und Modell enthält. Fügen Sie den folgenden Code am Ende der ersten Zeile der `Train`-Methode hinzu.

[!code-csharp[LearningPipeline](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#5 "Create a learning pipeline")]

Das <xref:Microsoft.ML.Data.TextLoader>-Objekt ist der erste Teil der Pipeline und lädt die Trainingsdateidaten.

[!code-csharp[TextLoader](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#6 "Add a text loader to the pipeline")]

## <a name="data-preprocess-and-feature-engineering"></a>Vorverarbeitung der Daten und Feature Engineering

Vorverarbeitung und Bereinigung von Daten sind wichtige Aufgaben, die durchgeführt werden, bevor ein Dataset effektiv für Machine Learning verwendet wird. Rohdaten sind häufig verunreinigt und unzuverlässig, und es können darin Werte fehlen. Die Verwendung von Daten ohne diese Modellierungsaufgaben kann irreführende Ergebnisse erzeugen. Mit den Transformationspipelines von ML.NET können Sie einen benutzerdefinierten Satz von Transformationen erstellen, die vor dem Trainieren oder Testen auf Ihre Daten angewendet werden. Die Transformationen dienen in erster Linie der Datenfeaturebereitstellung. Der Vorteil einer Transformationspipeline besteht darin, dass Sie sie nach der Transformationspipeline-Definition speichern können, um sie auf Testdaten anzuwenden.

Wenden Sie einen <xref:Microsoft.ML.Transforms.TextFeaturizer> an, um die `SentimentText`-Spalte in einen [numerischen Vektor](../resources/glossary.md#numerical-feature-vector) namens `Features` zu konvertieren, den der Machine Learning-Algorithmus verwendet. Dies ist der Vorverarbeitungs-/Featurebereitstellungsschritt. Die Verwendung zusätzlicher in ML.NET verfügbarer Komponenten kann bessere Ergebnisse mit dem Modell ermöglichen. Fügen Sie der Pipeline `TextFeaturizer` als nächste Codezeile hinzu:

[!code-csharp[TextFeaturizer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#7 "Add a TextFeaturizer to the pipeline")]

## <a name="choose-a-learning-algorithm"></a>Auswählen eines Lernalgorithmus

Das <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier>-Objekt ist ein Entscheidungsstruktur-Lernmodul, das Sie in dieser Pipeline verwenden. Ähnlich wie der Featurebereitstellungsschritt führt das Ausprobieren verschiedener in ML.NET verfügbarer Lernmodule und Ändern ihrer Parameter zu unterschiedlichen Ergebnissen. Bei der Optimierung können Sie [Hyperparameter](../resources/glossary.md#hyperparameter) wie <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumTrees>, <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumLeaves> und <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.MinDocumentsInLeafs> festlegen. Diese Hyperparameter werden vor jeglichen Auswirkungen auf das Modell festgelegt und sind modellspezifisch. Sie werden zur Optimierung der Entscheidungsstrukturleistung verwendet, sodass größere Werte sich negativ auf die Leistung auswirken können.

Fügen Sie der `Train`-Methode den folgenden Code hinzu:

[!code-csharp[BinaryClassifier](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#8 "Add a fast binary tree classifier")]

## <a name="train-the-model"></a>Trainieren des Modells

Sie trainieren das Modell <xref:Microsoft.ML.PredictionModel%602> basierend auf dem Dataset, das geladen und transformiert worden ist. `pipeline.Train<SentimentData, SentimentPrediction>()` trainiert die Pipeline (lädt die Daten, trainiert den Featurebereitsteller und das Lernmodul). Das Experiment wird erst ausgeführt, wenn dies geschieht.

Fügen Sie der `Train`-Methode den folgenden Code hinzu:

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#9 "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a>Speichern und Zurückgeben des trainierten Modells zur Verwendung für die Evaluierung

An diesem Punkt haben Sie ein Modell, das in eine der vorhandenen oder neuen .NET-Anwendungen integriert werden kann. Fügen Sie den folgenden Code der nächsten Zeile in `Train` hinzu, um das Modell vor der Rückgabe in einer ZIP-Datei zu speichern:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#10 "Save the model")]

Geben Sie das Modell am Ende der `Train`-Methode zurück.

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#11 "Return the model")]

## <a name="evaluate-the-model"></a>Evaluieren des Modells

Da Sie nun das Modell erstellt und trainiert haben, müssen Sie es zur Qualitätssicherung und Validierung mit einem anderen Dataset evaluieren. In der `Evaluate`-Methode wird das in `Train` erstellte Modell zur Evaluierung übergeben. Erstellen Sie die `Evaluate`-Methode direkt nach `Train` wie im folgenden Code:

```csharp
public static void Evaluate(PredictionModel<SentimentData, SentimentPrediction> model)
{

}
```

Die `Evaluate`-Methode führt die folgenden Aufgaben aus:

* Laden des Testdatasets.
* Erstellen des binären Auswerters.
* Evaluieren des Modells und Erstellen von Metriken.
* Anzeigen der Metriken.

Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `Train`-Methodenaufruf hinzu:

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#12 "Call the Evaluate method")]

Die <xref:Microsoft.ML.Data.TextLoader>-Klasse lädt das neue Testdataset mit dem gleichen Schema. Sie können das Modell unter Verwendung dieses Datasets in Form einer Qualitätsüberprüfung evaluieren. Fügen Sie der `Evaluate`-Methode den folgenden Code hinzu:

[!code-csharp[LoadText](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#13 "Load the test dataset")]

Das <xref:Microsoft.ML.Models.BinaryClassificationEvaluator>-Objekt berechnet die Qualitätsmetriken für das `PredictionModel` mit dem angegebenen Dataset. Fügen Sie zur Anzeige dieser Metriken den Auswerter als nächste Zeile mit folgendem Code der `Evaluate`-Methode hinzu:

[!code-csharp[BinaryEvaluator](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#14 "Create the binary evaluator")]

Die <xref:Microsoft.ML.Models.BinaryClassificationMetrics> enthält alle von Auswertern der binären Klassifizierung berechneten Metriken. Um diese zur Bestimmung der Qualität des Modells anzuzeigen, müssen Sie die Metriken zuerst abzurufen. Fügen Sie den folgenden Code hinzu:

[!code-csharp[CreateMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#15 "Evaluate the model and create metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a>Anzeigen der Metriken zur Modellvalidierung

Verwenden Sie den folgenden Code, um die Metriken anzuzeigen, die Ergebnisse freizugeben und dann mit ihnen zu arbeiten:

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#16 "Display selected metrics")]

## <a name="predict-the-test-data-outcomes-with-the-model"></a>Vorhersagen der Testdatenergebnisse mit dem Modell

Erstellen Sie die `Predict`-Methode mit dem folgenden Code direkt nach der `Evaluate`-Methode:

```csharp
public static void Predict(PredictionModel<SentimentData, SentimentPrediction> model)
{

}
```

Die `Predict`-Methode führt die folgenden Aufgaben aus:

* Erstellen von Testdaten.
* Vorhersagen des Standpunkts anhand der Testdaten.
* Kombinieren von Testdaten und Vorhersagen für die Berichterstattung.
* Anzeigen der vorhergesagten Ergebnisse.

Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `Evaluate`-Methodenaufruf hinzu:

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#17 "Call the Predict method")]

Fügen Sie einige Kommentare zum Testen der Vorhersagen des trainierten Modells in der `Predict`-Methode hinzu:

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#18 "Create test data for predictions")]

Nun besitzen Sie ein Modell, mit dem Sie den positiven oder negative Standpunkt der Kommentardaten unter Verwendung der <xref:Microsoft.ML.PredictionModel.Predict%2A?displayProperty=nameWithType>-Methode vorhersagen können. Verwenden Sie zum Abrufen einer Vorhersage `Predict` mit neuen Daten. Beachten Sie, dass die Eingabedaten eine Zeichenfolge sind und das Modell die Featurebereitstellungsschritt umfasst. Die Pipeline ist während Training und Vorhersage synchronisiert. Sie mussten keinen Vorverarbeitungs-/Featurebereitstellungscode speziell für Vorhersagen schreiben, und die gleiche API wird sowohl für Batch- als auch einmalige Vorhersagen eingesetzt.

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#19 "Create predictions of sentiments")]

### <a name="model-operationalization-prediction"></a>Operationalisierung des Modells: Vorhersage

Anzeigen von `SentimentText` und entsprechender Standpunktvorhersage, um die Ergebnisse freizugeben und entsprechend mit ihnen zu agieren. Dies wird als Operationalisierung bezeichnet, wobei die zurückgegebenen Daten als Teil der Betriebsrichtlinien verwendet werden. Erstellen Sie mit dem folgenden <xref:System.Console.WriteLine?displayProperty=nameWithType>-Code eine Kopfzeile für die Ergebnisse:

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#20 "Display prediction outputs")]

Kombinieren Sie vor der Anzeige der vorhergesagten Ergebnisse Standpunkt und Vorhersage, um den ursprünglichen Kommentar mit dem vorhergesagten Standpunkt anzuzeigen. Der folgende Code verwendet hierzu die <xref:System.Linq.Enumerable.Zip%2A>-Methode, darum fügen Sie diesen Code als Nächstes hinzu:

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#21 "Build the pairs of sentiment data and predictions")]

Da Sie nun `SentimentText` und `Sentiment` in einer Klasse kombiniert haben, können Sie die Ergebnisse mithilfe der <xref:System.Console.WriteLine?displayProperty=nameWithType>-Methode anzeigen:

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#22 "Display the predictions")]

Da abgeleitete Tupelelementnamen ein neues Feature in C# 7.1 sind und die Standardsprachversion des Projekts C# 7.0 ist, müssen Sie die Sprachversion auf C# 7.1 oder höher ändern.
Klicken Sie hierzu im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektknoten, und wählen Sie **Eigenschaften** aus. Wählen Sie die Registerkarte **Build** aus, und klicken Sie auf **Erweitert**. Wählen Sie in der Dropdownliste **C# 7.1** (oder eine höhere Version) aus. Klicken Sie auf die Schaltfläche **OK**.

## <a name="results"></a>Ergebnisse

Die Ergebnisse sollten den unten dargestellten ähneln. Während der Pipelineverarbeitung werden Meldungen angezeigt. Sie können Warnungen oder Verarbeitungsmeldungen sehen. Diese wurden der Übersichtlichkeit halber aus den folgenden Ergebnissen entfernt.

```

PredictionModel quality metrics evaluation
------------------------------------------
Accuracy: 66.67%
Auc: 94.44%
F1Score: 75.00%

Sentiment Predictions
---------------------
Sentiment: Please refrain from adding nonsense to Wikipedia. | Prediction: Negative
Sentiment: He is the best, and the article should say that. | Prediction: Positive

```

Herzlichen Glückwunsch! Sie haben jetzt erfolgreich ein Machine Learning-Modell zum Klassifizieren und Vorhersagen von Standpunkten in Mitteilungen erstellt. Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> * Das Problem verstehen
> * Auswählen der entsprechenden Machine Learning-Aufgabe
> * Vorbereiten Ihrer Daten
> * Erstellen der Lernpipeline
> * Laden eines Klassifizierers
> * Trainieren des Modells
> * Auswerten des Modells mit einem anderen Dataset
> * Vorhersagen der Testdatenergebnisse mit dem Modell

Wechseln Sie zum nächsten Tutorial, um mehr zu erfahren.
> [!div class="nextstepaction"]
> [Vorhersage des Taxifahrtpreises](taxi-fare.md)
