---
title: Verwenden von ML.NET in einem Standpunktanalyse-Szenario mit binärer Klassifizierung
description: Erfahren Sie, wie Sie ML.NET in einem Szenario mit binärer Klassifizierung verwenden, um zu erfahren, wie Sie die Standpunktvorhersage verwenden, um die geeignete Aktion auszuführen.
ms.date: 03/07/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: d7e46b489506f4adad843ba5315afde4c7689b4e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723321"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a>Tutorial: Verwenden von ML.NET in einem Standpunktanalyse-Szenario mit binärer Klassifizierung

Dieses Beispieltutorial veranschaulicht das Verwenden von ML.NET zum Erstellen eines Standpunktklassifizierers zum Vorhersagen eines positiven oder negativen Standpunkts über eine .NET Core-Konsolenanwendung mithilfe von C# in Visual Studio 2017. In der Welt von Machine Learning wird diese Art von Vorhersage als binäre Klassifizierung bezeichnet.

> [!NOTE]
> Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden. Weitere Informationen finden Sie in [der ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Dieses Tutorial und das zugehörige Beispiel verwenden zurzeit **ML.NET Version 0.11**. Weitere Informationen finden Sie in den Anmerkungen zur Version im [Dotnet/Machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> * Das Problem verstehen
> * Auswählen des entsprechenden Machine Learning-Algorithmus
> * Vorbereiten Ihrer Daten
> * Transformieren der Daten
> * Trainieren des Modells
> * Evaluieren des Modells
> * Vorhersagen treffen mit dem trainierten Modell
> * Bereitstellen eines geladenen Modells und Vorhersagen mit diesem treffen

## <a name="sentiment-analysis-sample-overview"></a>Übersicht über das Standpunktanalyse-Beispiel

Das Beispiel ist eine Konsolen-App, die ML.NET verwendet, um ein Modell zu trainieren, das den Standpunkt als positiv oder negativ klassifiziert und vorhersagt. Das von der University of California, Irvine (UCI), stammende Yelp-Standpunktdataset ist in ein Trainingsdataset und ein Testdataset unterteilt. Das Beispiel wertet das Modell mit dem Testdataset für die Qualitätsanalyse aus. 

Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).

## <a name="prerequisites"></a>Erforderliche Komponenten

* [Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.

* [Die Dataset-ZIP-Datei „UCI Sentiment Labeled Sentences“](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)

## <a name="machine-learning-workflow"></a>Machine Learning-Workflow

Dieses Tutorial folgt einem Machine Learning-Workflow, der den geordneten Ablauf des Prozesses ermöglicht.

Die Workflowphasen lauten wie folgt:

1. **Verstehen des Problems**
2. **Vorbereiten Ihrer Daten**
   * **Laden der Daten**
   * **Extrahieren von Funktionen (Transformieren von Daten)**
3. **Erstellen und trainieren** 
   * **Trainieren des Modells**
   * **Evaluieren des Modells**
4. **Bereitstellen des Modells**
   * **Vorhersagen treffen mit dem Modell**

### <a name="understand-the-problem"></a>Das Problem verstehen

Sie müssen das Problem zuerst verstehen, damit Sie es in Teile aufschlüsseln können, die das Erstellen und Trainieren des Modells erleichtern. Das Aufschlüsseln des Problems ermöglicht es Ihnen, die Ergebnisse vorherzusagen und auszuwerten.

Das Problem besteht bei diesem Tutorial darin, aus den auf der Website eingehenden Kommentaren den Standpunkt zu ermitteln, um die geeignete Aktion auszuführen.

Sie können das Problem nach dem Standpunkttext und dem Standpunktwert für die Daten aufschlüsseln, mit denen Sie das Modell trainieren möchten, und einem vorhergesagten Standpunktwert, den Sie auswerten und dann praktisch verwenden können.

Sie müssen dann den Standpunkt **bestimmen**, was Ihnen die Auswahl der Machine Learning-Aufgabe erleichtert.

## <a name="select-the-appropriate-machine-learning-algorithm"></a>Auswählen des entsprechenden Machine Learning-Algorithmus

Von diesem Problem kennen Sie die folgenden Fakten:

Trainingsdaten: Websitekommentare können positiv (1) oder negativ (0) sein (**Standpunkt**).

Sagen Sie den **Standpunkt** eines neuen Websitekommentars voraus, positiv oder negativ, wie in den folgenden Beispielen:

* Ich liebe das Bedienpersonal hier. Sie bringen‘s.
* Hier gibt‘s die schlechteste Suppe.

Der Machine Learning-Algorithmus für die Klassifizierung ist für dieses Szenario am besten geeignet.

### <a name="about-the-classification-algorithm"></a>Informationen zum Klassifizierungsalgorithmus

Die Klassifizierung ist ein Machine Learning-Algorithmus, der Daten zum **Bestimmen** von Kategorie, Typ oder Klasse eines Elements oder einer Datenzeile verwendet. Beispielsweise können Sie mit der Klassifizierung:

* Einen Standpunkt als positiv oder negativ identifizieren.
* E-Mails als Spam, Junk oder gut klassifizieren.
* Bestimmen, ob die Gewebeprobe eines Patienten Krebszellen enthält.
* Kunden nach ihrer Neigung kategorisieren, auf eine Werbekampagne zu reagieren.

Klassifizierungsalgorithmen zählen häufig zu einem der folgenden Typen:

* Binär: entweder A oder B.
* Multiklasse: mehrere Kategorien, die mit einem einzelnen Modell vorhergesagt werden können.

Da die Websitekommentare als positiv oder negativ klassifiziert werden müssen, verwenden Sie den Algorithmus für die Binärklassifizierung. 

## <a name="create-a-console-application"></a>Erstellen einer Konsolenanwendung

1. Öffnen Sie Visual Studio 2017. Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus. Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **.NET Core** aus. Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)**. Geben Sie „SentimentAnalysis“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.

2. Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um die Datasetdateien zu speichern:

    Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus. Geben Sie „Data“ ein, und drücken Sie die EINGABETASTE.

3. Installieren des **Microsoft.ML NuGet-Pakets**:

    Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte „Durchsuchen“ aus, suchen Sie nach **Microsoft.ML**, und wählen Sie das Paket in der Liste sowie anschließend die Schaltfläche **Installieren** aus. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.

### <a name="prepare-your-data"></a>Vorbereiten Ihrer Daten

1. Laden Sie [die Dataset-ZIP-Datei „UCI Sentiment Labeled Sentences“ (siehe Zitate im folgenden Hinweis)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) herunter, und entzippen Sie sie.

2. Kopieren Sie die `yelp_labelled.txt`-Datei in das Verzeichnis *Data*, das Sie erstellt haben.

> [!NOTE]
> Die in diesem Tutorial verwendeten Datasets stammen aus „From Group to Individual Labels using Deep Features“, Kotzias et al., KDD 2015, und werden im UCI Machine Learning Repository – Dua, D. und Karra Taniskidou, E. gehostet. (2017). UCI Machine Learning Repository [http://archive.ics.uci.edu/ml]. Irvine, CA: University of California, School of Information and Computer Science.

3. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die Datei `yelp_labeled.txt`, und wählen Sie **Eigenschaften** aus. Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.

### <a name="create-classes-and-define-paths"></a>Erstellen von Klassen und Definieren von Pfaden

Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddUsings "Add necessary usings")]

Sie müssen zwei globale Felder zum Speichern des gerade heruntergeladenen Datasetdateipfads und des gespeicherten Modelldateipfads erstellen:

* `_dataPath` enthält den Pfad zu dem Dataset, das zum Trainieren des Modells verwendet wird.
* `_modelPath` enthält den Pfad zu dem Speicherort, in dem das trainierte Modell gespeichert ist.

Fügen Sie den folgenden Code der Zeile direkt über der `Main`-Methode hinzu, um diese Pfade anzugeben:

[!code-csharp[Declare global variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DeclareGlobalVariables "Declare global variables")]

Sie müssen einige Klassen für die Eingabedaten und Vorhersagen erstellen. Fügen Sie dem Projekt eine neue Klasse hinzu:

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.

1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentData.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.

    Die Datei *SentimentData.cs* wird im Code-Editor geöffnet. Fügen Sie am Anfang der Datei *SentimentData.cs* die folgende `using`-Anweisung hinzu:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#AddUsings "Add necessary usings")]

Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code mit den beiden Klassen `SentimentData` und `SentimentPrediction` der Datei *SentimentData.cs* hinzu:

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#DeclareTypes "Declare data record types")]

Die Klasse des Eingabedatasets, `SentimentData`, hat eine `string`-Variable für den Kommentar (`SentimentText`) und eine `bool`-Variable (`Sentiment`), die entweder einen positiven oder negativen Wert für den Standpunkt enthält. Beiden Feldern sind <xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29>-Attribute angefügt. Dieses Attribut beschreibt die Reihenfolge der Felder in der Datendatei.  Darüber hinaus hat die `Sentiment`-Eigenschaft ein <xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A>, um es als `Label`-Feld festzulegen. Die `SentimentPrediction`-Klasse wird für die Vorhersage verwendet, nachdem das Modell trainiert wurde. Er verfügt über einen einzelnen booleschen Wert (`Sentiment`) und ein `PredictedLabel` `ColumnName`-Attribut. Das `Label` dient zum Erstellen und Trainieren des Modells, und es wird auch mit dem Split out-Testdataset verwendet, um das Modell zu evaluieren. Das `PredictedLabel` wird während der Vorhersage und Evaluierung verwendet. Für die Evaluierung werden eine Eingabe mit Trainingsdaten, die vorhergesagten Werte und das Modell verwendet.

Beim Erstellen eines Modells mit ML.NET erstellen Sie zunächst einen <xref:Microsoft.ML.MLContext>. `MLContext` ist im Prinzip vergleichbar mit der Verwendung von `DbContext` in Entity Framework. Die Umgebung bietet einen Kontext für Ihren ML-Job, der für die Verfolgung und Protokollierung von Ausnahmen verwendet werden kann.

### <a name="initialize-variables-in-main"></a>Initialisieren von Variablen in Main

Erstellen Sie eine Variable namens `mlContext`, und initialisieren Sie sie mit einer neuen `MLContext`-Instanz.  Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` mit dem folgenden Code in der `Main`-Methode:

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateMLContext "Create the ML Context")]

Fügen Sie den folgenden Text als nächste Codezeile in die `Main`-Methode ein:

[!code-csharp[CallLoadData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallLoadData)]

Die `LoadData`-Methode führt die folgenden Aufgaben aus:

* Laden der Daten.
* Teilt das geladene Dataset in Trainings- und Testdatasets auf.
* Gibt die aufgeteilten Trainings- und Testdatasets zurück.

Erstellen Sie die `LoadData`-Methode mit dem folgenden Code direkt nach der `Main`-Methode:

```csharp
public static (IDataView trainSet, IDataView testSet) LoadData(MLContext mlContext)
{

}
```
## <a name="load-the-data"></a>Laden der Daten

Da der zuvor von Ihnen erstellte `SentimentData`-Datenmodelltyp dem Schema des Datasets entspricht, können Sie das Initialisieren, Zuordnen und Laden des Datasets mit dem `MLContext.Data.ReadFromTextFile`-Wrapper für <xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29> in einer Codezeile zusammenfassen. Zurückgegeben wird ein <xref:Microsoft.Data.DataView.IDataView>. 

 Als Ein- und Ausgabe von `Transforms` ist ein `DataView` der grundlegende Datenpipelinetyp, vergleichbar mit `IEnumerable` für `LINQ`.

In ML.NET ähneln die Daten einer SQL-Ansicht. Sie werden verzögert ausgewertet, sind schematisiert und heterogen. Das Objekt ist der erste Teil der Pipeline und lädt die Daten. Für dieses Tutorial lädt es ein Dataset mit Kommentaren und entsprechend schädlichen oder unschädlichen Standpunkten. Damit wird das Modell erstellt und trainiert.

 Fügen Sie den folgenden Code am Ende der ersten Zeile der `LoadData`-Methode hinzu.

[!code-csharp[LoadData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadData "loading dataset")]

### <a name="split-the-dataset-for-model-training-and-testing"></a>Aufteilen des Datasets für Modelltraining und -test

Als Nächstes benötigen Sie ein Trainingsdataset zum Trainieren des Modells und ein Testdataset zum Evaluieren des Modells. Verwenden Sie den `MLContext.BinaryClassification.TrainTestSplit`, der <xref:Microsoft.ML.StaticPipe.TrainingStaticExtensions.TrainTestSplit%2A> umschließt, um das geladene Dataset in Trainings- und Testdatasets aufzuteilen und in <xref:Microsoft.ML.TrainCatalogBase.TrainTestData> zurückzusenden. Sie können den Anteil der Daten für das Testset mit dem `testFraction`-Parameter angeben. Der Standardwert ist 10%, aber Sie verwenden in diesem Fall 20%, um mehr Daten für die Auswertung zu verwenden.  

Um die geladenen Daten in die erforderlichen Datasets aufzuteilen, fügen Sie den folgenden Code als nächste Zeile in die `LoadData`-Methode ein:

[!code-csharp[SplitData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SplitData "Split the Data")]

Geben Sie `splitDataView` am Ende der `LoadData`-Methode zurück:

[!code-csharp[ReturnSplitData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a>Erstellen und Trainieren des Modells

Fügen Sie der `BuildAndTrainModel`-Methode den folgenden Aufruf als nächste Codezeile der `Main`-Methode hinzu:

[!code-csharp[CallBuildAndTrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallBuildAndTrainModel)]

Die `BuildAndTrainModel`-Methode führt die folgenden Aufgaben aus:

* Extrahieren und Transformieren der Daten.
* Trainieren des Modells.
* Vorhersagen des Standpunkts anhand der Testdaten.
* Zurückgeben des Modells.

Erstellen Sie die `Train`-Methode mit dem folgenden Code direkt nach der `Main`-Methode:

```csharp
public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
{

}
```

Beachten Sie, dass zwei Parameter an die Train-Methode übergeben werden; ein `MLContext` für den Kontext (`mlContext`) und eine `IDataView` für das Trainingsdatenset (`splitTrainSet`). 

## <a name="extract-and-transform-the-data"></a>Extrahieren und Transformieren der Daten

Vorverarbeitung und Bereinigung von Daten sind wichtige Aufgaben, die durchgeführt werden, bevor ein Dataset effektiv für Machine Learning verwendet wird. Rohdaten sind häufig verunreinigt und unzuverlässig, und es können darin Werte fehlen. Die Verwendung von Daten ohne diese Modellierungsaufgaben kann irreführende Ergebnisse erzeugen.

Mit den Transformationspipelines von ML.NET können Sie einen benutzerdefinierten Satz von Transformationen erstellen, die vor dem Trainieren oder Testen auf Ihre Daten angewendet werden. Die Transformationen dienen in erster Linie der [Datenfeaturebereitstellung](../resources/glossary.md#feature-engineering). Machine Learning-Algorithmen verstehen die mit [Features ausgestatteten](../resources/glossary.md#feature) Daten, sodass der nächste Schritt darin besteht, unsere Textdaten in ein Format zu transformieren, das unsere ML-Algorithmen erkennen. Dieses Format ist ein [numerischer Vektor](../resources/glossary.md#numerical-feature-vector).

Rufen Sie anschließend `mlContext.Transforms.Text.FeaturizeText` auf, wodurch die Textspalte (`SentimentText`) in einen numerischen Vektor namens `Features` konvertiert wird, den der Machine Learning-Algorithmus verwendet. Dies ist ein Wrapperaufruf, der <xref:Microsoft.ML.Data.EstimatorChain%601> zurückgibt, das effektiv eine Pipeline ist. Geben Sie den Namen `pipeline` ein, da Sie den Trainer an die `EstimatorChain` anfügen. Fügen Sie das zur nächsten Codezeile hinzu:

[!code-csharp[FeaturizeText](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#FeaturizeText "Featurize the text")]

>[!WARNING]
> Die ML.NET-Version 0.10 hat die Reihenfolge der Transformationsparameter geändert. Dies führt erst dann zu einem Fehler, wenn Sie die Anwendung ausführen und das Modell erstellen. Verwenden Sie für Transformationen die Parameternamen, wie Sie im vorherigen Codeausschnitt dargestellt sind.

Dies ist der Vorverarbeitungs-/Featurebereitstellungsschritt. Die Verwendung zusätzlicher in ML.NET verfügbarer Komponenten kann bessere Ergebnisse mit dem Modell ermöglichen.

## <a name="choose-a-learning-algorithm"></a>Auswählen eines Lernalgorithmus

Um die Trainer hinzuzufügen, rufen Sie die `mlContext.BinaryClassification.Trainers.FastTree`-Wrappermethode auf, die ein <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer>-Objekt zurückgibt. Das ist ein Entscheidungsstruktur-Lernmodul, das Sie in dieser Pipeline verwenden. Der `FastTreeBinaryClassificationTrainer` wird an die `pipeline` angefügt, und akzeptiert den mit Features ausgestatteten `SentimentText` (`Features`) und die `Label`-Eingabeparameter, um aus den historischen Daten zu lernen.

Fügen Sie der `BuildAndTrainModel`-Methode folgenden Code hinzu:

[!code-csharp[FastTreeBinaryClassificationTrainer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddTrainer "Add a FastTreeBinaryClassificationTrainer")]

## <a name="train-the-model"></a>Trainieren des Modells

Sie trainieren das Modell <xref:Microsoft.ML.Data.TransformerChain%601> basierend auf dem Dataset, das geladen und transformiert worden ist. Sobald die Schätzung definiert ist, trainieren Sie Ihr Modell mit der <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A>-Methode und stellen die bereits geladenen Trainingsdaten zur Verfügung. Damit wird ein Modell zurückgegeben, das für Vorhersagen verwendet werden kann. `pipeline.Fit()` trainiert die Pipeline und gibt einen `Transformer` basierend auf der eingegebenen `DataView` zurück. Das Experiment wird erst ausgeführt, wenn die `.Fit()`-Methode ausgeführt wird.

Fügen Sie der `BuildAndTrainModel`-Methode folgenden Code hinzu:

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TrainModel "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a>Speichern und Zurückgeben des trainierten Modells zur Verwendung für die Evaluierung

An diesem Punkt haben Sie ein Modell vom Typ <xref:Microsoft.ML.Data.TransformerChain%601>, das in eine der vorhandenen oder neuen .NET-Anwendungen integriert werden kann. Geben Sie das Modell am Ende der `BuildAndTrainModel`-Methode zurück.

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a>Evaluieren des Modells

Da Sie nun das Modell erstellt und trainiert haben, müssen Sie es zur Qualitätssicherung und Validierung mit einem anderen Dataset evaluieren. In der `Evaluate`-Methode wird das in `BuildAndTrainModel` erstellte Modell zur Evaluierung übergeben. Erstellen Sie die `Evaluate`-Methode direkt nach `BuildAndTrainModel` wie im folgenden Code:

```csharp
public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
{

}
```

Die `Evaluate`-Methode führt die folgenden Aufgaben aus:

* Laden des Testdatasets.
* Erstellt den Auswerter der binären Klassifizierung.
* Evaluieren des Modells und Erstellen von Metriken.
* Anzeigen der Metriken.

Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `Train`-Methodenaufruf hinzu:

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallEvaluate "Call the Evaluate method")]

Als nächstes verwenden Sie den Machine Learning-Parameter `model` (einen Transformator) und den `splitTestSet`-Parameter, um die Features einzugeben und die Vorhersagen zurückzugeben. Fügen Sie der `Evaluate`-Methode folgenden Code als nächste Zeile hinzu:

[!code-csharp[PredictWithTransformer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TransformData "Predict using the Transformer")]

Die `mlContext.BinaryClassification.Evaluate`-Methode berechnet die Qualitätsmetriken für das `PredictionModel` mit dem angegebenen Dataset. Das zurückgegebene <xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics>-Objekt enthält alle von Auswertern der binären Klassifizierung berechneten Metriken. Um diese zur Bestimmung der Qualität des Modells anzuzeigen, müssen Sie die Metriken zuerst abzurufen. Fügen Sie der `Evaluate`-Methode folgenden Code als nächste Zeile hinzu:

[!code-csharp[ComputeMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Evaluate "Compute Metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a>Anzeigen der Metriken zur Modellvalidierung

Verwenden Sie den folgenden Code, um die Metriken anzuzeigen, die Ergebnisse freizugeben und dann mit ihnen zu arbeiten:

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayMetrics "Display selected metrics")]

Um das Modell vor der Rückgabe in einer ZIP-Datei zu speichern, fügen Sie den folgenden Code als nächste Zeile in `Evaluate` hinzu, um die `SaveModelAsFile`-Methode aufzurufen:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallSaveModel "Save the model")]

## <a name="save-the-model-as-azip-file"></a>Speichern des Modells als ZIP-Datei

Erstellen Sie die `SaveModelAsFile`-Methode mit dem folgenden Code direkt nach der `Evaluate`-Methode:

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

Die `SaveModelAsFile`-Methode führt die folgenden Aufgaben aus:

* Speichern Sie das Modells als ZIP-Datei.

Erstellen Sie anschließend eine Methode zum Speichern des Modells, damit es wiederverwendet und in anderen Anwendungen integriert werden kann. Der `ITransformer` enthält eine <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)>-Methode mit dem globalen Feld `_modelPath` und einem <xref:System.IO.Stream>. Um die als ZIP-Datei zu speichern, erstellen Sie den `FileStream` unmittelbar vor dem Aufruf der `SaveTo`-Methode. Fügen Sie der `SaveModelAsFile`-Methode folgenden Code als nächste Zeile hinzu:

[!code-csharp[SaveToMethod](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SaveModel "Add the SaveTo Method")]

## <a name="deploy-and-predict-with-a-loaded-model"></a>Bereitstellen eines geladenen Modells und Vorhersagen mit diesem treffen

Sie können auch anzeigen, wo die Datei geschrieben wurde, indem Sie mit dem folgenden Code eine Konsolenmeldung mit dem `_modelPath` schreiben:

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="predict-the-test-data-outcome-with-the-saved-model"></a>Vorhersagen des Testdatenergebnisses mit dem gespeicherten Modell

Erstellen Sie die `UseModelWithSingleItem`-Methode mit dem folgenden Code direkt nach der `Evaluate`-Methode:

```csharp
private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
{

}
```

Die `UseModelWithSingleItem`-Methode führt die folgenden Aufgaben aus:

* Erstellen eines einzelnen Kommentars aus Testdaten.
* Vorhersagen des Standpunkts anhand der Testdaten.
* Kombinieren von Testdaten und Vorhersagen für die Berichterstattung.
* Anzeigen der vorhergesagten Ergebnisse.

Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `Evaluate`-Methodenaufruf hinzu:

[!code-csharp[CallUseModelWithSingleItem](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

Das `model` ist ein `transformer`, der auf vielen Datenzeilen arbeitet, wohingegen ein sehr gängiges Produktionsszenario die Notwendigkeit von Vorhersagen für einzelne Beispiele ist. <xref:Microsoft.ML.PredictionEngine%602> ist ein Wrapper, der von der `CreatePredictionEngine`-Methode zurückgegeben wird. Fügen wir den folgenden Code hinzu, um die `PredictionEngine` als erste Zeile in der `Predict`-Methode zu erstellen:

[!code-csharp[CreatePredictionEngine](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]
  
Fügen Sie einen Kommentar hinzu, um die Vorhersage des trainierten Modells in der `Predict`-Methode zu testen, indem Sie eine `SentimentData`-Instanz erstellen:

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

 Damit können Sie den positiven oder negativen Standpunkt einer einzelnen Instanz der Kommentardaten vorhersagen. Verwenden Sie zum Abrufen einer Vorhersage <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> für die Daten. Beachten Sie, dass die Eingabedaten eine Zeichenfolge sind und das Modell die Featurebereitstellungsschritt umfasst. Die Pipeline ist während Training und Vorhersage synchronisiert. Sie mussten keinen Vorverarbeitungs-/Featurebereitstellungscode speziell für Vorhersagen schreiben, und die gleiche API wird sowohl für Batch- als auch einmalige Vorhersagen eingesetzt.

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Predict "Create a prediction of sentiment")]

### <a name="use-the-model-prediction"></a>Verwenden des Modells: Vorhersage

Anzeigen von `SentimentText` und entsprechender Standpunktvorhersage, um die Ergebnisse freizugeben und entsprechend mit ihnen zu agieren. Dies wird als Operationalisierung bezeichnet, wobei die zurückgegebenen Daten als Teil der Betriebsrichtlinien verwendet werden. Erstellen Sie mit dem folgenden <xref:System.Console.WriteLine?displayProperty=nameWithType>-Code eine Anzeige für die Ergebnisse:

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#OutputPrediction "Display prediction output")]

## <a name="deploy-and-predict-with-a-loaded-model"></a>Bereitstellen eines geladenen Modells und Vorhersagen mit diesem treffen

Erstellen Sie die `UseLoadedModelWithBatchItems`-Methode mit dem folgenden Code direkt vor der `SaveModelAsFile`-Methode:

```csharp
public static void UseLoadedModelWithBatchItems(MLContext mlContext)
{

}
```

Die `UseLoadedModelWithBatchItems`-Methode führt die folgenden Aufgaben aus:

* Erstellen von Batchtestdaten.
* Vorhersagen des Standpunkts anhand der Testdaten.
* Kombinieren von Testdaten und Vorhersagen für die Berichterstattung.
* Anzeigen der vorhergesagten Ergebnisse.

Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `UseModelWithSingleItem`-Methodenaufruf hinzu:

[!code-csharp[CallPredictModelLoaded](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseLoadedModelWithBatchItems "Call the CallUseLoadedModelWithBatchItems method")]

Fügen Sie einige Kommentare zum Testen der Vorhersagen des trainierten Modells in der `UseLoadedModelWithBatchItems`-Methode hinzu:

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssues "Create test data for predictions")]

Das des Modells

[!code-csharp[LoadTheModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadModel "Load the model")]

Nun besitzen Sie ein Modell, mit dem Sie den schädlichen oder nicht schädlichen Standpunkt der Kommentardaten unter Verwendung der <xref:Microsoft.ML.ITransformer.Transform%2A>-Methode vorhersagen können. Verwenden Sie zum Abrufen einer Vorhersage `Predict` mit neuen Daten. Beachten Sie, dass die Eingabedaten eine Zeichenfolge sind und das Modell die Featurebereitstellungsschritt umfasst. Die Pipeline ist während Training und Vorhersage synchronisiert. Sie mussten keinen Vorverarbeitungs-/Featurebereitstellungscode speziell für Vorhersagen schreiben, und die gleiche API wird sowohl für Batch- als auch einmalige Vorhersagen eingesetzt. Fügen Sie für die Vorhersage den folgenden Code zur `UseLoadedModelWithBatchItems`-Methode hinzu:

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="use-the-loaded-model-for-prediction"></a>Verwenden des geladenen Modells für Vorhersagen

Anzeigen von `SentimentText` und entsprechender Standpunktvorhersage, um die Ergebnisse freizugeben und entsprechend mit ihnen zu agieren. Dies wird als Operationalisierung bezeichnet, wobei die zurückgegebenen Daten als Teil der Betriebsrichtlinien verwendet werden. Erstellen Sie mit dem folgenden <xref:System.Console.WriteLine?displayProperty=nameWithType>-Code eine Kopfzeile für die Ergebnisse:

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddInfoMessage "Display prediction outputs")]

Kombinieren Sie vor der Anzeige der vorhergesagten Ergebnisse Standpunkt und Vorhersage, um den ursprünglichen Kommentar mit dem vorhergesagten Standpunkt anzuzeigen. Der folgende Code verwendet hierzu die <xref:System.Linq.Enumerable.Zip%2A>-Methode, darum fügen Sie diesen Code als Nächstes hinzu:

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#BuildSentimentPredictionPairs "Build the pairs of sentiment data and predictions")]

Da Sie nun `SentimentText` und `Sentiment` in einer Klasse kombiniert haben, können Sie die Ergebnisse mithilfe der <xref:System.Console.WriteLine?displayProperty=nameWithType>-Methode anzeigen:

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayResults "Display the predictions")]

Da abgeleitete Tupelelementnamen ein neues Feature in C# 7.1 sind und die Standardsprachversion des Projekts C# 7.0 ist, müssen Sie die Sprachversion auf C# 7.1 oder höher ändern.
Klicken Sie hierzu im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektknoten, und wählen Sie **Eigenschaften** aus. Wählen Sie die Registerkarte **Build** aus, und klicken Sie auf **Erweitert**. Wählen Sie in der Dropdownliste **C# 7.1** (oder eine höhere Version) aus. Klicken Sie auf die Schaltfläche **OK**.

## <a name="results"></a>Ergebnisse

Die Ergebnisse sollten den unten dargestellten ähneln. Während der Pipelineverarbeitung werden Meldungen angezeigt. Sie können Warnungen oder Verarbeitungsmeldungen sehen. Diese wurden der Übersichtlichkeit halber aus den folgenden Ergebnissen entfernt.

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 79.14%
Auc: 86.27%
F1Score: 80.60%

=============== End of model evaluation ===============
The model is saved to C:\Tutorials\SentimentAnalysis\bin\Debug\netcoreapp2.1\Data\Model.zip

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This was a very bad steak | Prediction: Negative | Probability: 0.4641322
=============== End of Predictions ===============


=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This was a horrible meal | Prediction: Negative | Probability: 0.1391833
Sentiment: I love this spaghetti. | Prediction: Positive | Probability: 0.9819039
=============== End of predictions ===============

=============== End of process ===============
Press any key to continue . . .

```

Herzlichen Glückwunsch! Sie haben jetzt erfolgreich ein Machine Learning-Modell zum Klassifizieren und Vorhersagen von Standpunkten in Mitteilungen erstellt. 

Erfolgreiche Modelle zu erstellen ist ein iterativer Prozess. Dieses Modell hat erst geringere Qualität, da das Tutorial kleine Datasets verwendet, um schnelles Modelltraining zu ermöglichen. Wenn Sie nicht mit der Modellqualität zufrieden sind, können Sie versuchen, sie durch die Bereitstellung größerer Trainingsdatasets oder die Auswahl anderer Trainingsalgorithmen mit anderen Hyperparametern für jeden Algorithmus zu verbessern.

Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> * Das Problem verstehen
> * Auswählen des entsprechenden Machine Learning-Algorithmus
> * Vorbereiten Ihrer Daten
> * Transformieren der Daten
> * Trainieren des Modells
> * Evaluieren des Modells
> * Vorhersagen treffen mit dem trainierten Modell
> * Bereitstellen eines geladenen Modells und Vorhersagen mit diesem treffen

Wechseln Sie zum nächsten Tutorial, um mehr zu erfahren.
> [!div class="nextstepaction"]
> [Klassifizierung von Issues](github-issue-classification.md)
