---
title: Verwenden von ML.NET in einem Standpunktanalyse-Szenario mit binärer Klassifizierung
description: Erfahren Sie, wie Sie ML.NET in einem Szenario mit binärer Klassifizierung verwenden, um zu erfahren, wie Sie die Standpunktvorhersage verwenden, um die geeignete Aktion auszuführen.
ms.date: 12/20/2018
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 90f3b79226b16ac1ea4cbbe49ce07d95a138323b
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2018
ms.locfileid: "53779138"
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
> * Vorhersagen einer einzelnen Instanz an Testdatenergebnissen mit dem Modell
> * Vorhersagen der Testdatenergebnisse mit einem geladenen Modell

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
2. **Vorbereiten Ihrer Daten**
   * **Laden der Daten**
   * **Extrahieren von Funktionen (Transformieren von Daten)**
3. **Erstellen und trainieren** 
   * **Trainieren des Modells**
   * **Evaluieren des Modells**
4. **Run**
   * **Modellverbrauch**

### <a name="understand-the-problem"></a>Das Problem verstehen

Sie müssen das Problem zuerst verstehen, damit Sie es in Teile aufschlüsseln können, die das Erstellen und Trainieren des Modells erleichtern. Das Aufschlüsseln des Problems ermöglicht es Ihnen, die Ergebnisse vorherzusagen und auszuwerten.

Das Problem besteht bei diesem Tutorial darin, aus den auf der Website eingehenden Kommentaren den Standpunkt zu ermitteln, um die geeignete Aktion auszuführen.

Sie können das Problem nach dem Standpunkttext und dem Standpunktwert für die Daten aufschlüsseln, mit denen Sie das Modell trainieren möchten, und einem vorhergesagten Standpunktwert, den Sie auswerten und dann praktisch verwenden können.

Sie müssen dann den Standpunkt **bestimmen**, was Ihnen die Auswahl der Machine Learning-Aufgabe erleichtert.

## <a name="select-the-appropriate-machine-learning-task"></a>Auswählen der entsprechenden Machine Learning-Aufgabe

Von diesem Problem kennen Sie die folgenden Fakten:

Trainingsdaten: Websitekommentare können schädlich (1) oder unschädlich (0) sein (**Standpunkt**).
Sagen Sie den **Standpunkt** eines neuen Websitekommentars voraus, schädlich oder unschädlich, wie in den folgenden Beispielen:

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

1. Öffnen Sie Visual Studio 2017. Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus. Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **.NET Core** aus. Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)**. Geben Sie „SentimentAnalysis“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.

2. Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um die Datasetdateien zu speichern:

    Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus. Geben Sie „Data“ ein, und drücken Sie die EINGABETASTE.

3. Installieren des **Microsoft.ML NuGet-Pakets**:

    Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte „Durchsuchen“ aus, suchen Sie nach **Microsoft.ML**, und wählen Sie das Paket in der Liste sowie anschließend die Schaltfläche **Installieren** aus. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.

### <a name="prepare-your-data"></a>Vorbereiten Ihrer Daten

1. Laden Sie die Datasets [WikiPedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) und [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) herunter, und speichern Sie sie im zuvor erstellten Ordner *Data*. Das erste Dataset trainiert das Machine Learning-Modell, und das zweite kann verwendet werden, um zu evaluieren, wie genau das Modell ist.

2. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die \*.tsv-Dateien, und wählen Sie **Eigenschaften** aus. Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.

### <a name="create-classes-and-define-paths"></a>Erstellen von Klassen und Definieren von Pfaden

Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#1 "Add necessary usings")]

Sie müssen drei globale Felder erstellen, die die Pfade zu den zuletzt heruntergeladenen Dateien enthalten, und eine globale Variable für den `TextLoader`:

* `_trainDataPath` enthält den Pfad zu dem Dataset, das zum Trainieren des Modells verwendet wird.
* `_testDataPath` enthält den Pfad zu dem Dataset, das zum Evaluieren des Modells verwendet wird.
* `_modelPath` enthält den Pfad zu dem Speicherort, in dem das trainierte Modell gespeichert ist.
* `_textLoader` ist der zum Laden und Transformieren der Datasets verwendete <xref:Microsoft.ML.Runtime.Data.TextLoader>.

Fügen Sie den folgenden Code der Zeile direkt über der `Main`-Methode hinzu, um diese Pfade und die `_textLoader`-Variable anzugeben:

[!code-csharp[Declare global variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#2 "Declare global variables")]

Sie müssen einige Klassen für die Eingabedaten und Vorhersagen erstellen. Fügen Sie dem Projekt eine neue Klasse hinzu:

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.

1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentData.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.

    Die Datei *SentimentData.cs* wird im Code-Editor geöffnet. Fügen Sie am Anfang der Datei *SentimentData.cs* die folgende `using`-Anweisung hinzu:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#1 "Add necessary usings")]

Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code mit den beiden Klassen `SentimentData` und `SentimentPrediction` der Datei *SentimentData.cs* hinzu:

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#2 "Declare data record types")]

`SentimentData` ist die Klasse des Eingabedatasets und verfügt über eine `float`-Variable (`Sentiment`), die einen entweder positiven oder negativen Wert für den Standpunkt enthält, und eine String-Variable für den Kommentar (`SentimentText`). Beiden Feldern sind `Column`-Attribute angefügt. Dieses Attribut beschreibt die Reihenfolge der Felder in der Datendatei, und welches das `Label`-Feld ist. Die `SentimentPrediction`-Klasse wird für die Vorhersage verwendet, nachdem das Modell trainiert wurde. Er verfügt über einen einzelnen booleschen Wert (`Sentiment`) und ein `PredictedLabel` `ColumnName`-Attribut. Das `Label` dient zum Erstellen und Trainieren des Modells, und es wird auch mit einem zweiten Dataset verwendet, um das Modell zu evaluieren. Das `PredictedLabel` wird während der Vorhersage und Evaluierung verwendet. Für die Evaluierung werden eine Eingabe mit Trainingsdaten, die vorhergesagten Werte und das Modell verwendet.

Beim Erstellen eines Modells mit ML.NET erstellen Sie zunächst einen `MLContext`. Dies ist im Prinzip vergleichbar mit der Verwendung von `DbContext` in Entity Framework. Die Umgebung bietet einen Kontext für Ihren ML-Job, der für die Verfolgung und Protokollierung von Ausnahmen verwendet werden kann.

### <a name="initialize-variables-in-main"></a>Initialisieren von Variablen in Main

Erstellen Sie eine Variable namens `mlContext`, und initialisieren Sie sie mit einer neuen `MLContext`-Instanz.  Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` mit dem folgenden Code in der `Main`-Methode:

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#3 "Create the ML Context")]

Als nächstes initialisieren Sie zum Laden der Daten die globale Variable `_textLoader`, um sie wiederzuverwenden.  Beachten Sie, die Sie einen `TextReader` verwenden. Wenn Sie einen `TextLoader` mithilfe eines `TextReader` erstellen, übergeben Sie den erforderlichen Kontext und die <xref:Microsoft.ML.Runtime.Data.TextLoader.Arguments>-Klasse, um eine Anpassung zu ermöglichen.

 Geben Sie das Datenschema an, indem Sie ein Array von <xref:Microsoft.ML.Runtime.Data.TextLoader.Column>-Objekten an das Ladeprogramm übergeben, das alle Spaltennamen und deren Typen enthält. Das Datenschema wurde bereits beim Erstellen der `SentimentData`-Klasse definiert. Für unser Schema ist die erste Spalte (Bezeichnung) ein <xref:System.Boolean> (die Vorhersage) und die zweite Spalte (SentimentText) ist die Eigenschaft des Typs „Text/Zeichenfolge“, der für die Vorhersage des Standpunkts verwendet wird.
Die `TextReader`-Klasse gibt einen vollständig initialisierten <xref:Microsoft.ML.Runtime.Data.TextLoader> zurück.  

Um die globale Variable `_textLoader` zu initialisieren, um sie für die benötigten Datasets wiederzuverwenden, fügen Sie nach der Initialisierung von `mlContext` den folgenden Code hinzu:

[!code-csharp[initTextReader](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#4 "Initialize the TextReader")]

Fügen Sie den folgenden Text als nächste Codezeile in die `Main`-Methode ein:

[!code-csharp[Train](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#5 "Train your model")]

Die `Train`-Methode führt die folgenden Aufgaben aus:

* Laden der Daten.
* Extrahieren und Transformieren der Daten.
* Trainieren des Modells.
* Vorhersagen des Standpunkts anhand der Testdaten.
* Zurückgeben des Modells.

Erstellen Sie die `Train`-Methode mit dem folgenden Code direkt nach der `Main`-Methode:

```csharp
 public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

Beachten Sie, dass zwei Parameter an die Train-Methode übergeben werden; ein `MLContext` für den Kontext (`mlContext`) und eine <xref:System.String> für den Datensetpfad (`dataPath`). Sie werden diese Methode mehr als einmal zum Trainieren und Testen verwenden.

## <a name="load-the-data"></a>Laden der Daten

Sie laden die Daten mithilfe der globalen Variablen `_textLoader` mit dem `dataPath`-Parameter. Zurückgegeben wird ein <xref:Microsoft.ML.Runtime.Data.IDataView>. Als Ein- und Ausgabe von `Transforms` ist ein `DataView` der grundlegende Datenpipelinetyp, vergleichbar mit `IEnumerable` für `LINQ`.

In ML.NET ähneln die Daten einer SQL-Ansicht. Sie werden verzögert ausgewertet, sind schematisiert und heterogen. Das Objekt ist der erste Teil der Pipeline und lädt die Daten. Für dieses Tutorial lädt es ein Dataset mit Kommentaren und entsprechend schädlichen oder unschädlichen Standpunkten. Damit wird das Modell erstellt und trainiert.

 Fügen Sie den folgenden Code am Ende der ersten Zeile der `Train`-Methode hinzu.

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#6 "loading training dataset")]

## <a name="extract-and-transform-the-data"></a>Extrahieren und Transformieren der Daten

Vorverarbeitung und Bereinigung von Daten sind wichtige Aufgaben, die durchgeführt werden, bevor ein Dataset effektiv für Machine Learning verwendet wird. Rohdaten sind häufig verunreinigt und unzuverlässig, und es können darin Werte fehlen. Die Verwendung von Daten ohne diese Modellierungsaufgaben kann irreführende Ergebnisse erzeugen.

Mit den Transformationspipelines von ML.NET können Sie einen benutzerdefinierten Satz von Transformationen erstellen, die vor dem Trainieren oder Testen auf Ihre Daten angewendet werden. Die Transformationen dienen in erster Linie der [Datenfeaturebereitstellung](../resources/glossary.md#feature-engineering). Machine Learning-Algorithmen verstehen die mit [Features ausgestatteten](../resources/glossary.md#feature) Daten, sodass der nächste Schritt darin besteht, unsere Textdaten in ein Format zu transformieren, das unsere ML-Algorithmen erkennen. Dieses Format ist ein [numerischer Vektor](../resources/glossary.md#numerical-feature-vector).

Rufen Sie anschließend `mlContext.Transforms.Text.FeaturizeText` auf, wodurch die Textspalte (`SentimentText`) in einen numerischen Vektor namens `Features` konvertiert wird, den der Machine Learning-Algorithmus verwendet. Dies ist ein Wrapperaufruf, der <xref:Microsoft.ML.Runtime.Data.EstimatorChain%601> zurückgibt, das effektiv eine Pipeline ist. Geben Sie den Namen `pipeline` ein, da Sie den Trainer an die `EstimatorChain` anfügen. Fügen Sie das zur nächsten Codezeile hinzu:

[!code-csharp[TextFeaturizingEstimator](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#7 "Add a TextFeaturizingEstimator")]

Dies ist der Vorverarbeitungs-/Featurebereitstellungsschritt. Die Verwendung zusätzlicher in ML.NET verfügbarer Komponenten kann bessere Ergebnisse mit dem Modell ermöglichen.

## <a name="choose-a-learning-algorithm"></a>Auswählen eines Lernalgorithmus

Um die Trainer hinzuzufügen, rufen Sie die `mlContext.Transforms.Text.FeaturizeText`-Wrappermethode auf, die ein <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer>-Objekt zurückgibt. Das ist ein Entscheidungsstruktur-Lernmodul, das Sie in dieser Pipeline verwenden. Der `FastTreeBinaryClassificationTrainer` wird an die `pipeline` angefügt, und akzeptiert den mit Features ausgestatteten `SentimentText` (`Features`) und die `Label`-Eingabeparameter, um aus den historischen Daten zu lernen.

Fügen Sie der `Train`-Methode folgenden Code hinzu:

[!code-csharp[FastTreeBinaryClassificationTrainer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#8 "Add a FastTreeBinaryClassificationTrainer")]

## <a name="train-the-model"></a>Trainieren des Modells

Sie trainieren das Modell <xref:Microsoft.ML.Data.TransformerChain%601> basierend auf dem Dataset, das geladen und transformiert worden ist. Sobald die Schätzung definiert ist, trainieren Sie Ihr Modell mit <xref:Microsoft.ML.Runtime.Data.EstimatorChain%601.Fit%2A> und stellen die bereits geladenen Trainingsdaten zur Verfügung. Damit wird ein Modell zurückgegeben, das für Vorhersagen verwendet werden kann. `pipeline.Fit()` trainiert die Pipeline und gibt einen `Transformer` basierend auf der eingegebenen `DataView` zurück. Das Experiment wird erst ausgeführt, wenn dies geschieht.

Fügen Sie der `Train`-Methode folgenden Code hinzu:

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#9 "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a>Speichern und Zurückgeben des trainierten Modells zur Verwendung für die Evaluierung

An diesem Punkt haben Sie ein Modell vom Typ <xref:Microsoft.ML.Data.TransformerChain%601>, das in eine der vorhandenen oder neuen .NET-Anwendungen integriert werden kann. Geben Sie das Modell am Ende der `Train`-Methode zurück.

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#10 "Return the model")]

## <a name="evaluate-the-model"></a>Evaluieren des Modells

Da Sie nun das Modell erstellt und trainiert haben, müssen Sie es zur Qualitätssicherung und Validierung mit einem anderen Dataset evaluieren. In der `Evaluate`-Methode wird das in `Train` erstellte Modell zur Evaluierung übergeben. Erstellen Sie die `Evaluate`-Methode direkt nach `Train` wie im folgenden Code:

```csharp
public static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```

Die `Evaluate`-Methode führt die folgenden Aufgaben aus:

* Laden des Testdatasets.
* Erstellen des binären Auswerters.
* Evaluieren des Modells und Erstellen von Metriken.
* Anzeigen der Metriken.

Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `Train`-Methodenaufruf hinzu:

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#11 "Call the Evaluate method")]

Sie laden das Testdatenset mit der zuvor initialisierten globalen Variablen `_textLoader` und dem globalen Feld `_testDataPath`. Sie können das Modell unter Verwendung dieses Datasets in Form einer Qualitätsüberprüfung evaluieren. Fügen Sie der `Evaluate`-Methode folgenden Code hinzu:

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#12 "Load the test dataset")]

Als nächstes verwenden Sie den Machine Learning-Parameter `model` (einen Transformator), um die Features einzugeben und die Vorhersagen zurückzugeben. Fügen Sie der `Evaluate`-Methode folgenden Code als nächste Zeile hinzu:

[!code-csharp[PredictWithTransformer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#13 "Predict using the Transformer")]

Die `BinaryClassificationContext.Evaluate`-Methode berechnet die Qualitätsmetriken für das `PredictionModel` mit dem angegebenen Dataset. Das zurückgegebene `BinaryClassificationEvaluator.CalibratedResult`-Objekt enthält alle von Auswertern der binären Klassifizierung berechneten Metriken. Um diese zur Bestimmung der Qualität des Modells anzuzeigen, müssen Sie die Metriken zuerst abzurufen. Fügen Sie der `Evaluate`-Methode folgenden Code als nächste Zeile hinzu:

[!code-csharp[ComputeMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#14 "Compute Metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a>Anzeigen der Metriken zur Modellvalidierung

Verwenden Sie den folgenden Code, um die Metriken anzuzeigen, die Ergebnisse freizugeben und dann mit ihnen zu arbeiten:

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#15 "Display selected metrics")]

Um das Modell vor der Rückgabe in einer ZIP-Datei zu speichern, fügen Sie den folgenden Code als nächste Zeile in `TrainFinalModel` hinzu, um die `SaveModelAsFile`-Methode aufzurufen:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#23 "Save the model")]

## <a name="save-the-model-as-azip-file"></a>Speichern des Modells als ZIP-Datei

Erstellen Sie die `SaveModelAsFile`-Methode mit dem folgenden Code direkt nach der `Evaluate`-Methode:

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

Die `SaveModelAsFile`-Methode führt die folgenden Aufgaben aus:

* Speichern Sie das Modells als ZIP-Datei.

Erstellen Sie anschließend eine Methode zum Speichern des Modells, damit es wiederverwendet und in anderen Anwendungen integriert werden kann. Der `ITransformer` enthält eine <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.Runtime.IHostEnvironment,System.IO.Stream)>-Methode mit dem globalen Feld `_modelPath` und einem <xref:System.IO.Stream>. Um die als ZIP-Datei zu speichern, erstellen Sie den `FileStream` unmittelbar vor dem Aufruf der `SaveTo`-Methode. Fügen Sie der `SaveModelAsFile`-Methode folgenden Code als nächste Zeile hinzu:

[!code-csharp[SaveToMethod](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#24 "Add the SaveTo Method")]

Sie können auch anzeigen, wo die Datei geschrieben wurde, indem Sie mit dem folgenden Code eine Konsolenmeldung mit dem `_modelPath` schreiben:

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="predict-the-test-data-outcome-with-the-model-and-a-single-comment"></a>Vorhersagen der Testdatenergebnissen mit dem Modell und einem einzelnen Kommentar

Erstellen Sie die `Predict`-Methode mit dem folgenden Code direkt nach der `Evaluate`-Methode:

```csharp
private static void Predict(MLContext mlContext, ITransformer model)
{

}
```

Die `Predict`-Methode führt die folgenden Aufgaben aus:

* Erstellen eines einzelnen Kommentars aus Testdaten.
* Vorhersagen des Standpunkts anhand der Testdaten.
* Kombinieren von Testdaten und Vorhersagen für die Berichterstattung.
* Anzeigen der vorhergesagten Ergebnisse.

Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `Evaluate`-Methodenaufruf hinzu:

[!code-csharp[CallPredict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#16 "Call the Predict method")]

Das `model` ist ein `transformer`, der auf vielen Datenzeilen arbeitet, wohingegen ein sehr gängiges Produktionsszenario die Notwendigkeit von Vorhersagen für einzelne Beispiele ist. <xref:Microsoft.ML.Runtime.Data.PredictionFunction%602> ist ein Wrapper, der von der `MakePredictionFunction`-Methode zurückgegeben wird. Fügen wir den folgenden Code hinzu, um die PredictionFunction als erste Zeile in der `Predict`-Methode zu erstellen:

[!code-csharp[MakePredictionFunction](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#17 "Create the PredictionFunction")]
  
Fügen Sie einen Kommentar hinzu, um die Vorhersage des trainierten Modells in der `Predict`-Methode zu testen, indem Sie eine `SentimentData`-Instanz erstellen:

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#18 "Create test data for single prediction")]


 Damit können Sie den schädlichen oder unschädlichen Standpunkt einer einzelnen Instanz der Kommentardaten vorhersagen. Verwenden Sie zum Abrufen einer Vorhersage <xref:Microsoft.ML.Runtime.Data.PredictionFunction%602.Predict(%600)> für die Daten. Beachten Sie, dass die Eingabedaten eine Zeichenfolge sind und das Modell die Featurebereitstellungsschritt umfasst. Die Pipeline ist während Training und Vorhersage synchronisiert. Sie mussten keinen Vorverarbeitungs-/Featurebereitstellungscode speziell für Vorhersagen schreiben, und die gleiche API wird sowohl für Batch- als auch einmalige Vorhersagen eingesetzt.

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#19 "Create a prediction of sentiment")]

### <a name="model-operationalization-prediction"></a>Operationalisierung des Modells: Vorhersage

Anzeigen von `SentimentText` und entsprechender Standpunktvorhersage, um die Ergebnisse freizugeben und entsprechend mit ihnen zu agieren. Dies wird als Operationalisierung bezeichnet, wobei die zurückgegebenen Daten als Teil der Betriebsrichtlinien verwendet werden. Erstellen Sie mit dem folgenden <xref:System.Console.WriteLine?displayProperty=nameWithType>-Code eine Anzeige für die Ergebnisse:

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#20 "Display prediction output")]

## <a name="predict-the-test-data-outcomes-with-the-saved-model"></a>Vorhersagen der Testdatenergebnisse mit dem gespeicherten Modell

Erstellen Sie die `PredictWithModelLoadedFromFile`-Methode mit dem folgenden Code direkt vor der `SaveModelAsFile`-Methode:

```csharp
public static void PredictWithModelLoadedFromFile(MLContext mlContext)
{

}
```

Die `PredictWithModelLoadedFromFile`-Methode führt die folgenden Aufgaben aus:

* Erstellen von Batchtestdaten.
* Vorhersagen des Standpunkts anhand der Testdaten.
* Kombinieren von Testdaten und Vorhersagen für die Berichterstattung.
* Anzeigen der vorhergesagten Ergebnisse.

Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `Predict`-Methodenaufruf hinzu:

[!code-csharp[CallPredictModelLoaded](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#25 "Call the PredictWithModelLoadedFromFile method")]

Fügen Sie einige Kommentare zum Testen der Vorhersagen des trainierten Modells in der `PredictWithModelLoadedFromFile`-Methode hinzu:

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#26 "Create test data for predictions")]

Das des Modells [!code-csharp[LoadTheModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#27 "Load the model")]

Nun besitzen Sie ein Modell, mit dem Sie den schädlichen oder nicht schädlichen Standpunkt der Kommentardaten unter Verwendung der <xref:Microsoft.ML.Core.Data.ITransformer.Transform(Microsoft.ML.Runtime.Data.IDataView)>-Methode vorhersagen können. Verwenden Sie zum Abrufen einer Vorhersage `Predict` mit neuen Daten. Beachten Sie, dass die Eingabedaten eine Zeichenfolge sind und das Modell die Featurebereitstellungsschritt umfasst. Die Pipeline ist während Training und Vorhersage synchronisiert. Sie mussten keinen Vorverarbeitungs-/Featurebereitstellungscode speziell für Vorhersagen schreiben, und die gleiche API wird sowohl für Batch- als auch einmalige Vorhersagen eingesetzt. Fügen Sie für die Vorhersage den folgenden Code zur `PredictWithModelLoadedFromFile`-Methode hinzu:

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#28 "Create predictions of sentiments")]

### <a name="model-operationalization-prediction"></a>Operationalisierung des Modells: Vorhersage

Anzeigen von `SentimentText` und entsprechender Standpunktvorhersage, um die Ergebnisse freizugeben und entsprechend mit ihnen zu agieren. Dies wird als Operationalisierung bezeichnet, wobei die zurückgegebenen Daten als Teil der Betriebsrichtlinien verwendet werden. Erstellen Sie mit dem folgenden <xref:System.Console.WriteLine?displayProperty=nameWithType>-Code eine Kopfzeile für die Ergebnisse:

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#29 "Display prediction outputs")]

Kombinieren Sie vor der Anzeige der vorhergesagten Ergebnisse Standpunkt und Vorhersage, um den ursprünglichen Kommentar mit dem vorhergesagten Standpunkt anzuzeigen. Der folgende Code verwendet hierzu die <xref:System.Linq.Enumerable.Zip%2A>-Methode, darum fügen Sie diesen Code als Nächstes hinzu:

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#30 "Build the pairs of sentiment data and predictions")]

Da Sie nun `SentimentText` und `Sentiment` in einer Klasse kombiniert haben, können Sie die Ergebnisse mithilfe der <xref:System.Console.WriteLine?displayProperty=nameWithType>-Methode anzeigen:

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#31 "Display the predictions")]

Da abgeleitete Tupelelementnamen ein neues Feature in C# 7.1 sind und die Standardsprachversion des Projekts C# 7.0 ist, müssen Sie die Sprachversion auf C# 7.1 oder höher ändern.
Klicken Sie hierzu im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektknoten, und wählen Sie **Eigenschaften** aus. Wählen Sie die Registerkarte **Build** aus, und klicken Sie auf **Erweitert**. Wählen Sie in der Dropdownliste **C# 7.1** (oder eine höhere Version) aus. Klicken Sie auf die Schaltfläche **OK**.

## <a name="results"></a>Ergebnisse

Die Ergebnisse sollten den unten dargestellten ähneln. Während der Pipelineverarbeitung werden Meldungen angezeigt. Sie können Warnungen oder Verarbeitungsmeldungen sehen. Diese wurden der Übersichtlichkeit halber aus den folgenden Ergebnissen entfernt.

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 94.44%
Auc: 98.77%
F1Score: 94.74%
=============== End of model evaluation ===============

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This is a very rude movie | Prediction: Toxic | Probability: 0.5297049
=============== End of Predictions ===============

=============== New iteration of Model ===============
=============== Create and Train the Model ===============
=============== End of training ===============


The model is saved to: C:\Tutorial\SentimentAnalysis\bin\Debug\netcoreapp2.0\Data\Model.zip

=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This is a very rude movie | Prediction: Toxic | Probability: 0.4585565
Sentiment: He is the best, and the article should say that. | Prediction: Not Toxic | Probability: 0.9924279

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
