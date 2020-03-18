---
title: 'Tutorial: Kategorisieren von Supportproblemen (Multiklassenklassifizierung)'
description: Erfahren Sie hier, wie Sie mit ML.NET in einem Szenario zur Multiklassenklassifizierung GitHub-Issues klassifizieren, um sie einem bestimmten Bereich zuzuweisen.
ms.date: 01/30/2020
ms.topic: tutorial
ms.custom: mvc, title-hack-0516
ms.openlocfilehash: 50980cd933054825bf21f955b0341dd8e66f3e62
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "78239936"
---
# <a name="tutorial-categorize-support-issues-using-multiclass-classification-with-mlnet"></a>Tutorial: Kategorisieren von Supportproblemen unter Verwendung von Multiklassenklassifizierung mit ML.NET

In diesem Beispieltutorial wird veranschaulicht, wie Sie ML.NET zum Erstellen eines Klassifizierers für GitHub-Issues über eine .NET Core-Konsolenanwendung mithilfe von C# in Visual Studio verwenden können, um ein Modell zu trainieren, dass die Bereichsbezeichnung für ein GitHub-Issue klassifiziert und vorhersagt.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> * Vorbereiten Ihrer Daten
> * Transformieren der Daten
> * Trainieren des Modells
> * Evaluieren des Modells
> * Vorhersagen treffen mit dem trainierten Modell
> * Bereitstellen eines geladenen Modells und Vorhersagen mit diesem treffen

Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).

## <a name="prerequisites"></a>Voraussetzungen

* [Visual Studio 2017 Version 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.

* Die [durch Tabstopp getrennte Datei mit Github-Issues (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).
* Die [durch Tabstopp getrennte Testdatei für Github-Issues (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).

## <a name="create-a-console-application"></a>Erstellen einer Konsolenanwendung

### <a name="create-a-project"></a>Erstellen eines Projekts

1. Öffnen Sie Visual Studio 2017. Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus. Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **.NET Core** aus. Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)** . Geben Sie „GitHubIssueClassification“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.

2. Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um die Datasetdateien zu speichern:

    Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus. Geben Sie „Data“ ein, und drücken Sie die EINGABETASTE.

3. Erstellen Sie ein Verzeichnis mit dem Namen *Models* in Ihrem Projekt, um Ihr Modell zu speichern:

    Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus. Geben Sie „Models“ ein, und drücken Sie die EINGABETASTE.

4. Installieren des **Microsoft.ML NuGet-Pakets**:

    Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie als Paketquelle „nuget.org“ aus. Klicken Sie dann auf die Registerkarte „Durchsuchen“ aus, suchen Sie nach **Microsoft.ML**, und klicken Sie anschließend auf **Installieren**. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.

### <a name="prepare-your-data"></a>Vorbereiten Ihrer Daten

1. Laden Sie die Datasets [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) und [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) herunter, und speichern Sie sie im zuvor erstellten Ordner *Daten*. Das erste Dataset trainiert das Machine Learning-Modell, und das zweite kann verwendet werden, um zu evaluieren, wie genau das Modell ist.

2. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die \*.tsv-Dateien, und wählen Sie **Eigenschaften** aus. Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.

### <a name="create-classes-and-define-paths"></a>Erstellen von Klassen und Definieren von Pfaden

Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:

[!code-csharp[AddUsings](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#AddUsings)]

Erstellen Sie drei globale Felder, die die Pfade zu den zuletzt heruntergeladenen Dateien sowie globale Variablen für `MLContext`, `DataView` und `PredictionEngine` enthalten:

* `_trainDataPath` enthält den Pfad zu dem Dataset, das zum Trainieren des Modells verwendet wird.
* `_testDataPath` enthält den Pfad zu dem Dataset, das zum Evaluieren des Modells verwendet wird.
* `_modelPath` enthält den Pfad zu dem Speicherort, in dem das trainierte Modell gespeichert ist.
* `_mlContext` ist die <xref:Microsoft.ML.MLContext>-Klasse, die den Verarbeitungskontext enthält.
* `_trainingDataView` ist die zum Verarbeiten des Trainingsdatasets verwendete <xref:Microsoft.ML.IDataView>-Schnittstelle.
* `_predEngine` ist die für einzelne Vorhersagen verwendete <xref:Microsoft.ML.PredictionEngine%602>-Klasse.

Fügen Sie den folgenden Code der Zeile direkt über der `Main`-Methode hinzu, um diese Pfade und die anderen Variablen anzugeben:

[!code-csharp[DeclareGlobalVariables](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#DeclareGlobalVariables)]

Erstellen Sie einige Klassen für Ihre Eingabedaten und Vorhersagen. Fügen Sie dem Projekt eine neue Klasse hinzu:

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.

1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *GitHubIssueData.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.

    Die Datei *GitHubIssueData.cs* wird im Code-Editor geöffnet. Fügen Sie am Anfang der Datei *GitHubIssueData.cs* die folgende `using`-Anweisung hinzu:

[!code-csharp[AddUsings](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/GitHubIssueData.cs#AddUsings)]

Entfernen Sie die vorhandene Klassendefinition, und fügen Sie der Datei *GitHubIssueData.cs* den folgenden Code mit den beiden Klassen `GitHubIssue` und `IssuePrediction` hinzu:

[!code-csharp[DeclareGlobalVariables](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/GitHubIssueData.cs#DeclareTypes)]

`label` ist die Spalte, die vorhergesagt werden soll. Die identifizierten `Features` sind die Eingaben, die Sie für das Modell zum Vorhersagen der Bezeichnung bereitstellen.

Verwenden Sie das [LoadColumnAttribute](xref:Microsoft.ML.Data.LoadColumnAttribute), um die Indizes der Quellspalten im Dataset festzulegen.

`GitHubIssue` ist die Klasse des Eingabedatasets mit den folgenden <xref:System.String>-Feldern:

* Die erste Spalte: `ID` (ID des GitHub-Issues)
* Die zweite Spalte: `Area` (Vorhersage für das Training)
* Die dritte Spalte `Title` (Titel des GitHub-Issues) ist das erste `feature` zur Vorhersage von `Area`
* Die vierte Spalte `Description` ist das zweite `feature` für die Vorhersage von `Area`

Die `IssuePrediction`-Klasse wird für die Vorhersage verwendet, nachdem das Modell trainiert wurde. Sie verfügt über ein einzelnes `string`- (`Area`) und ein `PredictedLabel` `ColumnName`-Attribut.  Das `PredictedLabel` wird während der Vorhersage und Evaluierung verwendet. Für die Evaluierung werden eine Eingabe mit Trainingsdaten, die vorhergesagten Werte und das Modell verwendet.

Alle ML.NET-Operationen beginnen in der [MLContext](xref:Microsoft.ML.MLContext)-Klasse. Beim Initialisieren von `mlContext` wird eine neue ML.NET-Umgebung erstellt, die für alle Objekte des Workflows für die Modellerstellung gemeinsam genutzt werden kann. Die Klasse ähnelt dem Konzept von `DBContext` in `Entity Framework`.

### <a name="initialize-variables-in-main"></a>Initialisieren von Variablen in Main

Initialisieren Sie die globale Variable `_mlContext` mit einer neuen Instanz von `MLContext` mit einem zufälligen Ausgangswert (`seed: 0`), um in mehreren Trainings wiederholbare/deterministische Ergebnisse zu erhalten.  Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` mit dem folgenden Code in der `Main`-Methode:

[!code-csharp[CreateMLContext](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CreateMLContext)]

## <a name="load-the-data"></a>Laden der Daten

Für ML.NET wird die [IDataView-Klasse](xref:Microsoft.ML.IDataView) als flexible, effiziente Möglichkeit zum Beschreiben von Tabellendaten in Zahlen- oder Textform verwendet. Mit `IDataView` können entweder Textdateien geladen werden, oder es kann ein Echtzeitladevorgang durchgeführt werden (z.B. SQL-Datenbank- oder Protokolldateien).

Fügen Sie nach der Initialisierung von `mlContext` den folgenden Code hinzu, um die globale Variable `_trainingDataView` zur Verwendung für die Pipeline zu initialisieren und zu laden:

[!code-csharp[LoadTrainData](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#LoadTrainData)]

Die [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)-Methode definiert das Datenschema und liest die Datei ein. Diese Methode akzeptiert Datenpfadvariablen und gibt ein `IDataView`-Objekt zurück.

Fügen Sie den folgenden Text als nächste Codezeile in die `Main`-Methode ein:

[!code-csharp[CallProcessData](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CallProcessData)]

Die `ProcessData`-Methode führt die folgenden Aufgaben aus:

* Extrahieren und Transformieren der Daten.
* Zurückgeben der Verarbeitungspipeline

Erstellen Sie die `ProcessData`-Methode mit dem folgenden Code direkt nach der `Main`-Methode:

```csharp
public static IEstimator<ITransformer> ProcessData()
{

}
```

## <a name="extract-features-and-transform-the-data"></a>Extrahieren von Features und Transformieren der Daten

Da Sie die GitHub-Bereichsbezeichnung für ein `GitHubIssue` vorhersagen möchten, verwenden Sie die [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A)-Methode, um die `Area`-Spalte in eine `Label`-Spalte eines numerischen Typs zu transformieren (ein Format, das von Klassifizierungsalgorithmen akzeptiert wird), und fügen Sie sie als neue Datasetspalte hinzu:

[!code-csharp[MapValueToKey](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#MapValueToKey)]

Rufen Sie als Nächstes `mlContext.Transforms.Text.FeaturizeText` auf, wodurch die Textspalten (`Title` und `Description`) jeweils in einen numerischen Vektor namens `TitleFeaturized` und `DescriptionFeaturized` transformiert werden. Fügen Sie an die Pipeline die Featurebereitstellung für beide Spalten mit dem folgenden Code an:

[!code-csharp[FeaturizeText](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#FeaturizeText)]

Im letzten Schritt der Vorbereitung der Daten werden alle Feature-Spalten mithilfe der [Concatenate()](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A)-Methode in die Spalte **Features** kombiniert. Standardmäßig verarbeitet ein Lernalgorithmus nur Merkmale aus der Spalte **Features**. Fügen Sie an die Pipeline diese Transformation mit dem folgenden Code an:

[!code-csharp[Concatenate](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#Concatenate)]

 Fügen Sie anschließend wie im folgenden Code veranschaulicht eine <xref:Microsoft.ML.Data.EstimatorChain%601.AppendCacheCheckpoint%2A>-Methode zum Zwischenspeichern von DataView an. Dadurch erhalten Sie beim mehrmaligen Durchlaufen der Daten mit dem Cache möglicherweise eine bessere Leistung:

[!code-csharp[AppendCache](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#AppendCache)]

> [!WARNING]
> Verwenden Sie AppendCacheCheckpoint für kleine/mittlere Datasets, um die Zeit für das Training zu reduzieren. Verwenden Sie dies NICHT bei der Verarbeitung sehr großer Datasets (entfernen Sie .AppendCacheCheckpoint()).

Geben Sie die Pipeline am Ende der `ProcessData`-Methode zurück.

[!code-csharp[ReturnPipeline](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#ReturnPipeline)]

In diesem Schritt wird die Vorverarbeitung/Featurebereitstellung behandelt. Die Verwendung zusätzlicher in ML.NET verfügbarer Komponenten kann bessere Ergebnisse mit dem Modell ermöglichen.

## <a name="build-and-train-the-model"></a>Erstellen und Trainieren des Modells

Fügen Sie der `BuildAndTrainModel`-Methode den folgenden Aufruf als nächste Codezeile der `Main`-Methode hinzu:

[!code-csharp[CallBuildAndTrainModel](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CallBuildAndTrainModel)]

Die `BuildAndTrainModel`-Methode führt die folgenden Aufgaben aus:

* Erstellen der Algorithmusklasse für das Training
* Trainieren des Modells.
* Vorhersagen des Bereichs basierend auf den Trainingsdaten
* Zurückgeben des Modells.

Erstellen Sie die `BuildAndTrainModel`-Methode mit dem folgenden Code direkt nach der `Main`-Methode:

```csharp
public static IEstimator<ITransformer> BuildAndTrainModel(IDataView trainingDataView, IEstimator<ITransformer> pipeline)
{

}
```

### <a name="about-the-classification-task"></a>Informationen zur Klassifizierungsaufgabe

Die Klassifizierung ist eine Machine Learning-Aufgabe, die Daten zum **Bestimmen** von Kategorie, Typ oder Klasse eines Elements oder einer Datenzeile verwendet, und ist oft eine der folgenden Typen:

* Binär: entweder A oder B.
* Multiklasse: mehrere Kategorien, die mit einem einzelnen Modell vorhergesagt werden können.

Verwenden Sie für diese Art von Problemen einen Lernalgorithmus für die Klassifizierung, da es wahrscheinlicher ist, dass Ihre Vorhersage einer Problemkategorie einer von vielen Kategorien (Multiklasse) als einer von zwei (Binär) entspricht.

Fügen Sie den unten aufgeführten Code als erste Codezeilen in `BuildAndTrainModel()` ein, um den Machine Learning-Algorithmus festzulegen und ihn an die Datentransformationsdefinitionen anzufügen:

[!code-csharp[AddTrainer](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#AddTrainer)]

Der [SdcaMaximumEntropy](xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer) Algorithmus für die Multiklassenklassifizierung. Dieser wird an die `pipeline` angefügt und akzeptiert die mit Features ausgestatteten `Title`- und `Description`-Parameter (`Features`) sowie die `Label`-Eingabeparameter, um aus den historischen Daten zu lernen.

### <a name="train-the-model"></a>Trainieren des Modells

Fügen Sie den unten aufgeführten Code als nächste Codezeilen in die `BuildAndTrainModel()`-Methode ein, um das Modell an die `splitTrainSet`-Daten anzupassen und das trainierte Modell zurückzugeben:

[!code-csharp[TrainModel](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#TrainModel)]

Mit der `Fit()`-Methode wird Ihr Modell trainiert, indem das Dataset transformiert und das Training angewendet wird.

Die [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) ist eine Hilfs-API, mit der Sie eine einzelne Instanz der Daten übergeben und dafür dann eine Vorhersage treffen können. Fügen Sie das als nächste Zeile in der `BuildAndTrainModel()`-Methode hinzu:

[!code-csharp[CreatePredictionEngine1](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CreatePredictionEngine1)]

### <a name="predict-with-the-trained-model"></a>Vorhersagen treffen mit dem trainierten Modell

Fügen Sie ein GitHub-Issue hinzu, um die Vorhersage des trainierten Modells in der `Predict`-Methode zu testen, indem Sie eine `GitHubIssue`-Instanz erstellen:

[!code-csharp[CreateTestIssue1](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CreateTestIssue1)]

Die [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A)-Funktion trifft eine Vorhersage für eine einzelne Datenzeile:

[!code-csharp[Predict](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#Predict)]

### <a name="using-the-model-prediction-results"></a>Verwenden des Modells: Vorhersageergebnisse

Zeigen Sie `GitHubIssue` und die entsprechende Vorhersage der `Area`-Bezeichnung an, um die Ergebnisse freizugeben und entsprechenden Aktionen auszuführen.  Erstellen Sie mit dem folgenden <xref:System.Console.WriteLine?displayProperty=nameWithType>-Code eine Anzeige für die Ergebnisse:

[!code-csharp[OutputPrediction](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#OutputPrediction)]

### <a name="return-the-model-trained-to-use-for-evaluation"></a>Zurückgeben des für die Evaluierung trainierten Modells

Geben Sie das Modell am Ende der `BuildAndTrainModel`-Methode zurück.

[!code-csharp[ReturnModel](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#ReturnModel)]

## <a name="evaluate-the-model"></a>Evaluieren des Modells

Da Sie nun das Modell erstellt und trainiert haben, müssen Sie es zur Qualitätssicherung und Validierung mit einem anderen Dataset evaluieren. In der `Evaluate`-Methode wird das in `BuildAndTrainModel` erstellte Modell zur Evaluierung übergeben. Erstellen Sie die `Evaluate`-Methode direkt nach `BuildAndTrainModel` wie im folgenden Code:

```csharp
public static void Evaluate(DataViewSchema trainingDataViewSchema)
{

}
```

Die `Evaluate`-Methode führt die folgenden Aufgaben aus:

* Laden des Testdatasets.
* Erstellen des Multiklassenauswerters
* Evaluieren des Modells und Erstellen von Metriken.
* Anzeigen der Metriken.

Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `BuildAndTrainModel`-Methodenaufruf hinzu:

[!code-csharp[CallEvaluate](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CallEvaluate)]

Wie zuvor beim Trainingsdataset laden Sie das Testdataset, indem Sie den folgenden Code zur `Evaluate`-Methode hinzufügen:

[!code-csharp[LoadTestDataset](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#LoadTestDataset)]

Die [Evaluate()](xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A)-Methode berechnet die Qualitätsmetriken für das Modell mit dem angegebenen Dataset. Das zurückgegebene <xref:Microsoft.ML.Data.MulticlassClassificationMetrics>-Objekt enthält alle von Auswertern der Multiklassenklassifizierung berechneten Metriken.
Um diese Metriken zum Ermitteln der Modellqualität anzuzeigen, müssen Sie sie zunächst abrufen.
Beachten Sie die Verwendung der [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A)-Methode der globalen Machine Learning-Variable `_trainedModel` (ein [Transformator](xref:Microsoft.ML.ITransformer)), um die Features einzugeben und die Vorhersagen zurückzugeben. Fügen Sie der `Evaluate`-Methode folgenden Code als nächste Zeile hinzu:

[!code-csharp[Evaluate](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#Evaluate)]

Für die Multiklassenklassifizierung werden die folgenden Metriken ausgewertet:

* Mikrogenauigkeit: Jedes Beispiel/Klasse-Paar trägt zu gleichen Teilen zur Genauigkeitsmetrik bei.  Die Mikrogenauigkeit sollte so nahe wie möglich bei 1 liegen.

* Makrogenauigkeit: Jede Klasse trägt zu gleichen Teilen zur Genauigkeitsmetrik bei. Minderheitsklassen werden gleich wie größere Klassen gewichtet. Die Makrogenauigkeit sollte so nahe wie möglich bei 1 liegen.

* Protokollverlust: Siehe [Protokollverlust](../resources/glossary.md#log-loss). Der Protokollverlust sollte so nahe wie möglich bei 0 liegen.

* Verringerung des Protokollverlusts: Dieser liegt zwischen -inf und 1.00, wobei „1.00“ perfekte Vorhersagen und „0“ durchschnittliche Vorhersagen bedeutet. Die Verringerung des Protokollverlusts sollte so nahe wie möglich bei 0 liegen.

### <a name="displaying-the-metrics-for-model-validation"></a>Anzeigen der Metriken zur Modellvalidierung

Verwenden Sie den folgenden Code, um die Metriken anzuzeigen, die Ergebnisse freizugeben und dann mit ihnen zu arbeiten:

[!code-csharp[DisplayMetrics](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#DisplayMetrics)]

### <a name="save-the-model-to-a-file"></a>Speichern des Modells in einer Datei

Wenn Sie mit Ihrem Modell zufrieden sind, speichern Sie es in einer Datei, um Vorhersagen zu einem späteren Zeitpunkt oder in einer anderen Anwendung zu treffen. Fügen Sie der `Evaluate` -Methode folgenden Code hinzu.

[!code-csharp[SnippetCallSaveModel](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#SnippetCallSaveModel)]

Erstellen Sie die `SaveModelAsFile`-Methode unter der `Evaluate`-Methode.

```csharp
private static void SaveModelAsFile(MLContext mlContext,DataViewSchema trainingDataViewSchema, ITransformer model)
{

}
```

Fügen Sie der `SaveModelAsFile`-Methode den folgenden Code hinzu. Dieser Code verwendet die [`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save*)-Methode, um das trainierte Modell zu serialisieren und als ZIP-Datei zu speichern.

[!code-csharp[SnippetSaveModel](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#SnippetSaveModel)]

## <a name="deploy-and-predict-with-a-model"></a>Bereitstellen eines Modells und Treffen von Vorhersagen

Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `Evaluate`-Methodenaufruf hinzu:

[!code-csharp[CallPredictIssue](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CallPredictIssue)]

Erstellen Sie die `PredictIssue`-Methode unmittelbar nach der `Evaluate`-Methode (und direkt vor der `SaveModelAsFile`-Methode) mithilfe des folgenden Codes:

```csharp
private static void PredictIssue()
{

}
```

Die `PredictIssue`-Methode führt die folgenden Aufgaben aus:

* Laden des gespeicherte Modells
* Erstellen eines einzelnen Issues aus Testdaten
* Vorhersagen des Bereichs basierend auf Testdaten
* Kombinieren von Testdaten und Vorhersagen für die Berichterstattung.
* Anzeigen der vorhergesagten Ergebnisse.

Laden Sie das gespeicherte Modell in Ihre Anwendung, indem Sie der `PredictIssue`-Methode den folgenden Code hinzufügen:

[!code-csharp[SnippetLoadModel](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#SnippetLoadModel)]

Fügen Sie ein GitHub-Issue hinzu, um die Vorhersage des trainierten Modells in der `Predict`-Methode zu testen, indem Sie eine `GitHubIssue`-Instanz erstellen:

[!code-csharp[AddTestIssue](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#AddTestIssue)]

Erstellen Sie wie zuvor eine `PredictionEngine`-Instanz mit dem folgenden Code:

[!code-csharp[CreatePredictionEngine](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CreatePredictionEngine)]

Die [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) ist eine Hilfs-API, mit der Sie eine Vorhersage für eine einzelne Instanz der Daten treffen können. [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) ist nicht threadsicher. Die Verwendung in Singlethread-oder Prototypumgebungen ist zulässig. Zur Verbesserung der Leistung und Threadsicherheit in Produktionsumgebungen verwenden Sie den `PredictionEnginePool`-Dienst, der einen [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) aus [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)-Objekten für die Verwendung in Ihrer gesamten Anwendung erstellt. Informationen zur [Verwendung von `PredictionEnginePool` in einer ASP.NET Core-Web-API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application) finden Sie in dieser Anleitung.

> [!NOTE]
> Die `PredictionEnginePool`-Diensterweiterung ist derzeit als Vorschauversion verfügbar.

Verwenden Sie die `PredictionEngine`, um die GitHub-Bereichsbezeichnung vorherzusagen, indem Sie den folgenden Code zur `PredictIssue`-Methode für die Vorhersage hinzufügen:

[!code-csharp[PredictIssue](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#PredictIssue)]

### <a name="using-the-loaded-model-for-prediction"></a>Verwenden des geladenen Modells für Vorhersagen

Zeigen Sie `Area` an, um das Issue zu kategorisieren und eine entsprechende Aktion auszuführen. Erstellen Sie mit dem folgenden <xref:System.Console.WriteLine?displayProperty=nameWithType>-Code eine Anzeige für die Ergebnisse:

[!code-csharp[DisplayResults](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#DisplayResults)]

## <a name="results"></a>Ergebnisse

Die Ergebnisse sollten den unten dargestellten ähneln. Während der Pipelineverarbeitung werden Meldungen angezeigt. Sie können Warnungen oder Verarbeitungsmeldungen sehen. Diese Nachrichten wurden der Übersichtlichkeit halber aus den folgenden Ergebnissen entfernt.

```console
=============== Single Prediction just-trained-model - Result: area-System.Net ===============
*************************************************************************************************************
*       Metrics for Multi-class Classification model - Test Data
*------------------------------------------------------------------------------------------------------------
*       MicroAccuracy:    0.738
*       MacroAccuracy:    0.668
*       LogLoss:          .919
*       LogLossReduction: .643
*************************************************************************************************************
=============== Single Prediction - Result: area-System.Data ===============
```

Herzlichen Glückwunsch! Sie haben jetzt erfolgreich ein Machine Learning-Modell zur Klassifizierung und Vorhersage der Bereichsbezeichnung für ein GitHub-Issue erstellt. Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> * Vorbereiten Ihrer Daten
> * Transformieren der Daten
> * Trainieren des Modells
> * Evaluieren des Modells
> * Vorhersagen treffen mit dem trainierten Modell
> * Bereitstellen eines geladenen Modells und Vorhersagen mit diesem treffen

Wechseln Sie zum nächsten Tutorial, um mehr zu erfahren.
> [!div class="nextstepaction"]
> [Vorhersage des Taxifahrtpreises](predict-prices.md)
