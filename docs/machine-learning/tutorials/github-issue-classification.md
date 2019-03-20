---
title: Verwenden von ML.NET in einem Szenario zur Multiklassenklassifizierung von GitHub-Issues
description: Erfahren Sie hier, wie Sie mit ML.NET in einem Szenario zur Multiklassenklassifizierung GitHub-Issues klassifizieren, um sie einem bestimmten Bereich zuzuweisen.
ms.date: 03/12/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 1031ac8a592c968e22745de4be966392733597dd
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2019
ms.locfileid: "57846310"
---
# <a name="tutorial-use-mlnet-in-a-multiclass-classification-scenario-to-classify-github-issues"></a>Tutorial: Verwenden von ML.NET zur Klassifizierung von GitHub-Issues in einem Szenario mit Multiklassenklassifizierung

In diesem Beispieltutorial wird veranschaulicht, wie Sie ML.NET zum Erstellen eines Klassifizierers für GitHub-Issues über eine .NET Core-Konsolenanwendung mithilfe von C# in Visual Studio 2017 verwenden können.

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

> [!NOTE]
> Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden. Weitere Informationen finden Sie in [der ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Dieses Tutorial und das zugehörige Beispiel verwenden zurzeit **ML.NET Version 0.11**. Weitere Informationen finden Sie in den Anmerkungen zur Version im [Dotnet/Machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

## <a name="github-issue-sample-overview"></a>Beispielübersicht für ein GitHub-Issue

Das Beispiel ist eine Konsolen-App, die ML.NET zum Trainieren eines Modells verwendet, das für ein GitHub-Issue die Bezeichnung „Area“ (Bereich) klassifiziert und vorhersagt. Sie wertet das Modell auch mit einem zweiten Dataset für die Qualitätsanalyse aus. Die Datasets des Issues stammen aus dem GitHub-Repository „dotnet/coreFX“.

Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).

## <a name="prerequisites"></a>Erforderliche Komponenten

* [Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.

* Die [durch Tabstopp getrennte Datei mit Github-Issues (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).
* Die [durch Tabstopp getrennte Testdatei für Github-Issues (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).

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

Sie müssen das Problem zuerst verstehen, damit Sie es in Teile aufschlüsseln können, die das Erstellen und Trainieren des Modells erleichtern. Durch Aufschlüsseln des Problems können Sie die Ergebnisse vorhersagen und auswerten.

In diesem Tutorial wird behandelt, wie Sie erkennen können, zu welchem Bereich ein eingehendes GitHub-Issue gehört, um es anschließend für die Priorisierung und Planung korrekt zu bezeichnen.

Sie können das Problem in die folgenden Einzelteile aufschlüsseln:

* Titeltext des Issues
* Beschreibungstext des Issues
* Wert für den Bereich der Modelltrainingsdaten
* vorhergesagter Wert für den Bereich zur Auswertung und anschließenden praktischen Verwendung

Anschließend müssen Sie den Bereich **bestimmen**. Dadurch wird die Auswahl der Machine Learning-Aufgabe erleichtert.

## <a name="select-the-appropriate-machine-learning-algorithm"></a>Auswählen des entsprechenden Machine Learning-Algorithmus

Von diesem Problem kennen Sie die folgenden Fakten:

Trainingsdaten:

GitHub-Issues können, wie in den folgenden Beispielen veranschaulicht wird, in verschiedenen Bereichen (**Area**) bezeichnet werden:

* area-System.Numerics
* area-System.Xml
* area-Infrastructure
* area-System.Linq
* area-System.IO

Sagen Sie den **Bereich** eines neuen GitHub-Issues wie in den folgenden Beispielen veranschaulicht vorher:

* Contract.Assert im Vergleich zu Debug.Assert
* Festlegen von Feldern in System.Xml als schreibgeschützt

Der Machine Learning-Algorithmus für die Klassifizierung ist für dieses Szenario am besten geeignet.

### <a name="about-the-classification-learning-algorithm"></a>Informationen zum Lernalgorithmus für die Klassifizierung

Die Klassifizierung ist ein Machine Learning-Algorithmus, der Daten zum **Bestimmen** von Kategorie, Typ oder Klasse eines Elements oder einer Datenzeile verwendet. Beispielsweise können Sie mit der Klassifizierung:

* Einen Standpunkt als positiv oder negativ identifizieren.
* E-Mails als Spam, Junk oder gut klassifizieren.
* Bestimmen, ob die Gewebeprobe eines Patienten Krebszellen enthält.
* Kunden nach ihrer Neigung kategorisieren, auf eine Werbekampagne zu reagieren.

Die Anwendungsfälle des Lernalgorithmus für die Klassifizierung weisen meist einen der folgenden Typen auf:

* Binär: entweder A oder B.
* Multiklasse: mehrere Kategorien, die mit einem einzelnen Modell vorhergesagt werden können.

Verwenden Sie für diese Art von Problemen einen Lernalgorithmus für die Klassifizierung, da es wahrscheinlicher ist, dass Ihre Vorhersage einer Problemkategorie einer von vielen Kategorien (Multiklasse) als einer von zwei (Binär) entspricht.

## <a name="create-a-console-application"></a>Erstellen einer Konsolenanwendung

### <a name="create-a-project"></a>Erstellen eines Projekts

1. Öffnen Sie Visual Studio 2017. Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus. Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **.NET Core** aus. Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)**. Geben Sie „GitHubIssueClassification“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.

2. Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um die Datasetdateien zu speichern:

    Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus. Geben Sie „Data“ ein, und drücken Sie die EINGABETASTE.

3. Erstellen Sie ein Verzeichnis mit dem Namen *Models* in Ihrem Projekt, um Ihr Modell zu speichern:

    Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus. Geben Sie „Models“ ein, und drücken Sie die EINGABETASTE.

4. Installieren des **Microsoft.ML NuGet-Pakets**:

    Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte „Durchsuchen“ aus, suchen Sie nach **Microsoft.ML**, und wählen Sie das Paket in der Liste sowie anschließend die Schaltfläche **Installieren** aus. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.

### <a name="prepare-your-data"></a>Vorbereiten Ihrer Daten

1. Laden Sie die Datasets [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) und [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) herunter, und speichern Sie sie im zuvor erstellten Ordner *Daten*. Das erste Dataset trainiert das Machine Learning-Modell, und das zweite kann verwendet werden, um zu evaluieren, wie genau das Modell ist.

2. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die \*.tsv-Dateien, und wählen Sie **Eigenschaften** aus. Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.

### <a name="create-classes-and-define-paths"></a>Erstellen von Klassen und Definieren von Pfaden

Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddUsings)]

Erstellen Sie drei globale Felder, die die Pfade zu den zuletzt heruntergeladenen Dateien sowie globale Variablen für `MLContext`, `DataView`, `PredictionEngine` und `TextLoader` enthalten:

* `_trainDataPath` enthält den Pfad zu dem Dataset, das zum Trainieren des Modells verwendet wird.
* `_testDataPath` enthält den Pfad zu dem Dataset, das zum Evaluieren des Modells verwendet wird.
* `_modelPath` enthält den Pfad zu dem Speicherort, in dem das trainierte Modell gespeichert ist.
* `_mlContext` ist die <xref:Microsoft.ML.MLContext>-Klasse, die den Verarbeitungskontext enthält.
* `_trainingDataView` ist die zum Verarbeiten des Trainingsdatasets verwendete <xref:Microsoft.Data.DataView.IDataView>-Schnittstelle.
* `_predEngine` ist die für einzelne Vorhersagen verwendete <xref:Microsoft.ML.PredictionEngine%602>-Klasse.
* `_reader` ist der zum Laden und Transformieren der Datasets verwendete <xref:Microsoft.ML.Data.TextLoader>.

Fügen Sie den folgenden Code der Zeile direkt über der `Main`-Methode hinzu, um diese Pfade und die anderen Variablen anzugeben:

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DeclareGlobalVariables)]

Erstellen Sie einige Klassen für Ihre Eingabedaten und Vorhersagen. Fügen Sie dem Projekt eine neue Klasse hinzu:

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.

1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *GitHubIssueData.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.

    Die Datei *GitHubIssueData.cs* wird im Code-Editor geöffnet. Fügen Sie am Anfang der Datei *GitHubIssueData.cs* die folgende `using`-Anweisung hinzu:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#AddUsings)]

Entfernen Sie die vorhandene Klassendefinition, und fügen Sie der Datei *GitHubIssueData.cs* den folgenden Code mit den beiden Klassen `GitHubIssue` und `IssuePrediction` hinzu:

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#DeclareTypes)]

`GitHubIssue` ist die Klasse des Eingabedatasets mit den folgenden <xref:System.String>-Feldern:

* `ID` enthält einen Wert für die ID des GitHub-Issues.
* `Area` enthält einen Wert für die `Area`-Bezeichnung.
* `Title` enthält den Titel des GitHub-Issues.
* `Description` enthält die Beschreibung des GitHub-Issues.

Die `IssuePrediction`-Klasse wird für die Vorhersage verwendet, nachdem das Modell trainiert wurde. Sie verfügt über ein einzelnes `string`- (`Area`) und ein `PredictedLabel` `ColumnName`-Attribut. Das `Label` dient zum Erstellen und Trainieren des Modells, und es wird auch mit einem zweiten Dataset verwendet, um das Modell zu evaluieren. Das `PredictedLabel` wird während der Vorhersage und Evaluierung verwendet. Für die Evaluierung werden eine Eingabe mit Trainingsdaten, die vorhergesagten Werte und das Modell verwendet.

Beim Erstellen eines Modells mit ML.NET erstellen Sie zunächst eine <xref:Microsoft.ML.MLContext>-Klasse. `MLContext` ist im Prinzip vergleichbar mit der Verwendung von `DbContext` in Entity Framework. Die Umgebung bietet einen Kontext für Ihren ML-Job, der für die Verfolgung und Protokollierung von Ausnahmen verwendet werden kann.

### <a name="initialize-variables-in-main"></a>Initialisieren von Variablen in Main

Initialisieren Sie die globale Variable `_mlContext` mit einer neuen Instanz von `MLContext` mit einem zufälligen Ausgangswert (`seed: 0`), um in mehreren Trainings wiederholbare/deterministische Ergebnisse zu erhalten.  Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` mit dem folgenden Code in der `Main`-Methode:

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateMLContext)]

## <a name="load-the-data"></a>Laden der Daten

Initialisieren Sie anschließend die globale <xref:Microsoft.Data.DataView.IDataView>-Variable `_trainingDataView`, und laden Sie die Daten mit dem `_trainDataPath`-Parameter.

 Als Ein- und Ausgabe von [`Transforms`](../basic-concepts-model-training-in-mldotnet.md#transformer) ist ein `DataView` der grundlegende Datenpipelinetyp, vergleichbar mit `IEnumerable` für `LINQ`.

In ML.NET ähneln die Daten einer `SQL view`. Sie werden verzögert ausgewertet, sind schematisiert und heterogen. Das Objekt ist der erste Teil der Pipeline und lädt die Daten. In diesem Tutorial wird ein Dataset mit dem Titel und der Beschreibung des Issues und der entsprechenden GitHub-Bezeichnung des Bereichs geladen. Mit `DataView` wird das Modell erstellt und trainiert.

Da der zuvor von Ihnen erstellte `GitHubIssue`-Datenmodelltyp dem Schema des Datasets entspricht, können Sie das Initialisieren, Zuordnen und Laden des Datasets in einer Codezeile zusammenfassen.

Laden Sie die Daten mithilfe des `MLContext.Data.LoadFromTextFile`-Wrappers für die [LoadFromTextFile-Methode](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29). Es wird eine <xref:Microsoft.Data.DataView.IDataView> zurückgegeben, die das Datasetschema aus dem `GitHubIssue`-Datenmodelltyp ableitet und den Datasetheader verwendet. 

Das Datenschema wurde bereits beim Erstellen der `GitHubIssue`-Klasse definiert. Für Ihr Schema gilt:

* Die erste Spalte: `ID` (ID des GitHub-Issues)
* Die zweite Spalte: `Area` (Vorhersage für das Training)
* Die dritte Spalte `Title` (Titel des GitHub-Issues) ist das erste [Feature](../resources/glossary.md##feature) zur Vorhersage von `Area`.
* Die vierte Spalte `Description` ist das zweite Feature für die Vorhersage von `Area`.

Fügen Sie nach der Initialisierung von `mlContext` den folgenden Code hinzu, um die globale Variable `_trainingDataView` zur Verwendung für die Pipeline zu initialisieren und zu laden:

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTrainData)]

Fügen Sie den folgenden Text als nächste Codezeile in die `Main`-Methode ein:

[!code-csharp[CallProcessData](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallProcessData)]

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

Vorverarbeitung und Bereinigung von Daten sind wichtige Aufgaben, die durchgeführt werden, bevor ein Dataset effektiv für Machine Learning verwendet wird. Rohdaten sind häufig verunreinigt und unzuverlässig, und es können darin Werte fehlen. Die Verwendung von Daten ohne diese Modellierungsaufgaben kann irreführende Ergebnisse erzeugen.

Mit den Transformationspipelines von ML.NET können Sie benutzerdefinierte `transforms`-Klassen erstellen, die vor dem Trainieren oder Testen auf Ihre Daten angewendet werden. Die Transformationen dienen in erster Linie der [Datenfeaturebereitstellung](../resources/glossary.md#feature-engineering). Machine Learning-Algorithmen verstehen die mit [Features ausgestatteten](../resources/glossary.md#feature) Daten, sodass der nächste Schritt darin besteht, unsere Textdaten in ein Format zu transformieren, das unsere ML-Algorithmen erkennen. Dieses Format ist ein [numerischer Vektor](../resources/glossary.md#numerical-feature-vector).

In den nächsten Schritten werden die Spalten mit den zuvor in der `GitHubIssue`-Klasse definierten Namen bezeichnet.

Wenn das Modell trainiert und ausgewertet wurde, gelten die Werte in der Spalte **Label** standardmäßig als richtige Werte, die vorhergesagt werden. Da die GitHub-Bezeichnung des Bereichs für ein `GitHubIssue` vorhergesagt werden soll, kopieren Sie die Spalte `Area` in die Spalte **Bezeichnung**. Verwenden Sie hierfür `MLContext.Transforms.Conversion.MapValueToKey` (einen Wrapper für die Transformationsklasse <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A>).  `MapValueToKey` gibt <xref:Microsoft.ML.Data.EstimatorChain%601> zurück, das eine Pipeline ist. Geben Sie den Namen `pipeline` ein, da Sie den Trainer an die `EstimatorChain` anfügen. Fügen Sie die nächste Codezeile hinzu:

[!code-csharp[MapValueToKey](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#MapValueToKey)]

 Dadurch werden verschiedene numerische Schlüsselwerte den verschiedenen Werten in jeder Spalte zugeordnet und vom Machine Learning-Algorithmus verwendet. Rufen Sie als Nächstes `mlContext.Transforms.Text.FeaturizeText` auf, wodurch die Textspalten (`Title` und `Description`) jeweils in einen numerischen Vektor namens `TitleFeaturized` und `DescriptionFeaturized` konvertiert werden. Fügen Sie an die Pipeline die Featurebereitstellung für beide Spalten mit dem folgenden Code an:

[!code-csharp[FeaturizeText](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#FeaturizeText)]

>[!WARNING]
> Die ML.NET-Version 0.10 hat die Reihenfolge der Transformationsparameter geändert. Erst beim Erstellen des Projekts wird ein Fehler ausgelöst. Verwenden Sie für Transformationen die Parameternamen, wie Sie im vorherigen Codeausschnitt dargestellt sind.

Im letzten Schritt der Vorbereitung der Daten werden alle Feature-Spalten mithilfe der Transformationsklasse `Concatenate` in die Spalte **Features** kombiniert. Standardmäßig verarbeitet ein Lernalgorithmus nur Merkmale aus der Spalte **Features**. Fügen Sie an die Pipeline diese Transformation mit dem folgenden Code an:

[!code-csharp[Concatenate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Concatenate)]

 Fügen Sie anschließend wie im folgenden Code veranschaulicht eine <xref:Microsoft.ML.Data.EstimatorChain%601.AppendCacheCheckpoint%2A>-Methode zum Zwischenspeichern von DataView an. Dadurch erhalten Sie beim mehrmaligen Durchlaufen der Daten mit dem Cache möglicherweise eine bessere Leistung:

[!code-csharp[AppendCache](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AppendCache)]

> [!WARNING]
> Verwenden Sie AppendCacheCheckpoint für kleine/mittlere Datasets, um die Zeit für das Training zu reduzieren. Verwenden Sie dies NICHT bei der Verarbeitung sehr großer Datasets (entfernen Sie .AppendCacheCheckpoint()).

Geben Sie die Pipeline am Ende der `ProcessData`-Methode zurück.

[!code-csharp[ReturnPipeline](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnPipeline)]

In diesem Schritt wird die Vorverarbeitung/Featurebereitstellung behandelt. Die Verwendung zusätzlicher in ML.NET verfügbarer Komponenten kann bessere Ergebnisse mit dem Modell ermöglichen.

## <a name="build-and-train-the-model"></a>Erstellen und Trainieren des Modells

Fügen Sie der `BuildAndTrainModel`-Methode den folgenden Aufruf als nächste Codezeile der `Main`-Methode hinzu:

[!code-csharp[CallBuildAndTrainModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallBuildAndTrainModel)]

Die `BuildAndTrainModel`-Methode führt die folgenden Aufgaben aus:

* Erstellen der Algorithmusklasse für das Training
* Trainieren des Modells.
* Vorhersagen des Bereichs basierend auf den Trainingsdaten
* Speichern des Modells in einer `.zip`-Datei
* Zurückgeben des Modells.

Erstellen Sie die `BuildAndTrainModel`-Methode mit dem folgenden Code direkt nach der `Main`-Methode:

```csharp
public static IEstimator<ITransformer> BuildAndTrainModel(IDataView trainingDataView, IEstimator<ITransformer> pipeline)
{

}
```

Beachten Sie, dass der BuildAndTrainModel-Methode zwei Parameter übergeben werden: `IDataView` für das Trainingsdataset (`trainingDataView`) und <xref:Microsoft.ML.Data.EstimatorChain%601> für die in ProcessData erstellte Verarbeitungspipeline (`pipeline`).

 Fügen Sie den folgenden Code am Ende der ersten Zeile der `BuildAndTrainModel`-Methode hinzu.

### <a name="choose-a-learning-algorithm"></a>Auswählen eines Lernalgorithmus

Rufen Sie zum Hinzufügen des Lernalgorithmus die Wrappermethode `mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent` auf, die ein <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer>-Objekt zurückgibt.  `SdcaMultiClassTrainer` wird an die `pipeline` angefügt und akzeptiert die mit Features ausgestatteten `Title`- und `Description`-Parameter (`Features`) sowie die `Label`-Eingabeparameter, um aus den historischen Daten zu lernen. Ordnen Sie außerdem die Bezeichnung dem Wert zu, um den ursprünglichen lesbaren Zustand wiederherzustellen. Führen Sie diese beiden Aktionen mithilfe des folgenden Codes aus:

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTrainer)]

### <a name="train-the-model"></a>Trainieren des Modells

Sie trainieren das Modell <xref:Microsoft.ML.Data.TransformerChain%601> basierend auf dem Dataset, das geladen und transformiert worden ist. Sobald die Schätzung definiert ist, trainieren Sie Ihr Modell mit <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> und stellen die bereits geladenen Trainingsdaten zur Verfügung. Diese Methode gibt ein Modell zurück, das für Vorhersagen verwendet werden kann. `trainingPipeline.Fit()` trainiert die Pipeline und gibt einen `Transformer` basierend auf der eingegebenen `DataView` zurück. Das Experiment wird erst ausgeführt, wenn die `.Fit()`-Methode ausgeführt wird.

Fügen Sie der `BuildAndTrainModel`-Methode folgenden Code hinzu:

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#TrainModel)]

Das `model` ist ein `transformer`, der auf vielen Datenzeilen arbeitet, doch die Notwendigkeit, Vorhersagen für einzelne Beispiele zu treffen, ist ein sehr gängiges Produktionsszenario. <xref:Microsoft.ML.PredictionEngine%602> ist ein Wrapper, der von der `CreatePredictionEngine`-Methode zurückgegeben wird. Fügen Sie den folgenden Code hinzu, um `PredictionEngine` als nächste Zeile in der `BuildAndTrainModel`-Methode zu erstellen:

[!code-csharp[CreatePredictionEngine1](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine1)]

### <a name="predict-with-the-trained-model"></a>Vorhersagen treffen mit dem trainierten Modell

Fügen Sie ein GitHub-Issue hinzu, um die Vorhersage des trainierten Modells in der `Predict`-Methode zu testen, indem Sie eine `GitHubIssue`-Instanz erstellen:

[!code-csharp[CreateTestIssue1](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateTestIssue1)]

Damit können Sie die `Area`-Bezeichnung einer einzelnen Instanz der Daten des Issues vorhersagen. Verwenden Sie zum Abrufen einer Vorhersage <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> für die Daten. Die Eingabedaten sind eine Zeichenfolge, und das Modell enthält die Featurebereitstellung. Die Pipeline ist während Training und Vorhersage synchronisiert. Sie mussten keinen Vorverarbeitungs-/Featurebereitstellungscode speziell für Vorhersagen schreiben, und die gleiche API wird sowohl für Batch- als auch einmalige Vorhersagen eingesetzt.

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Predict)]

### <a name="using-the-model-prediction-results"></a>Verwenden des Modells: Vorhersageergebnisse

Zeigen Sie `GitHubIssue` und die entsprechende Vorhersage der `Area`-Bezeichnung an, um die Ergebnisse freizugeben und entsprechenden Aktionen auszuführen.  Erstellen Sie mit dem folgenden <xref:System.Console.WriteLine?displayProperty=nameWithType>-Code eine Anzeige für die Ergebnisse:

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#OutputPrediction)]

### <a name="return-the-model-trained-to-use-for-evaluation"></a>Zurückgeben des für die Evaluierung trainierten Modells

Geben Sie das Modell am Ende der `BuildAndTrainModel`-Methode zurück.

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnModel)]

## <a name="evaluate-the-model"></a>Evaluieren des Modells

Da Sie nun das Modell erstellt und trainiert haben, müssen Sie es zur Qualitätssicherung und Validierung mit einem anderen Dataset evaluieren. In der `Evaluate`-Methode wird das in `BuildAndTrainModel` erstellte Modell zur Evaluierung übergeben. Erstellen Sie die `Evaluate`-Methode direkt nach `BuildAndTrainModel` wie im folgenden Code:

```csharp
public static void Evaluate()
{

}
```

Die `Evaluate`-Methode führt die folgenden Aufgaben aus:

* Laden des Testdatasets.
* Erstellen des Multiklassenauswerters
* Evaluieren des Modells und Erstellen von Metriken.
* Anzeigen der Metriken.

Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `BuildAndTrainModel`-Methodenaufruf hinzu:

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallEvaluate)]

Sie können die Initialisierung, Zuordnung und das Laden des Testdatasets wie beim Trainingsdataset in einer Codezeile zusammenfassen. Sie können das Modell unter Verwendung dieses Datasets in Form einer Qualitätsüberprüfung evaluieren. Fügen Sie der `Evaluate`-Methode folgenden Code hinzu:

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTestDataset)]

`MulticlassClassificationContext.Evaluate` ist ein Wrapper für die <xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A>-Methode, die die Qualitätsmetriken für das Modell mit dem angegebenen Dataset berechnet. Das zurückgegebene <xref:Microsoft.ML.Data.MultiClassClassifierMetrics>-Objekt enthält alle von Auswertern der Multiklassenklassifizierung berechneten Metriken.
Um diese Metriken zum Ermitteln der Modellqualität anzuzeigen, müssen Sie sie zunächst abrufen.
Beachten Sie die Verwendung der `Transform`-Methode der globalen Machine Learning-Variable `_trainedModel` (ein Transformator), um die Funktionen einzugeben und die Vorhersagen zurückzugeben. Fügen Sie der `Evaluate`-Methode folgenden Code als nächste Zeile hinzu:

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Evaluate)]

Für die Multiklassenklassifizierung werden die folgenden Metriken ausgewertet:

* Mikrogenauigkeit: Jedes Beispiel/Klasse-Paar trägt zu gleichen Teilen zur Genauigkeitsmetrik bei.  Die Mikrogenauigkeit sollte so nahe wie möglich bei 1 liegen.

* Makrogenauigkeit: Jede Klasse trägt zu gleichen Teilen zur Genauigkeitsmetrik bei. Minderheitsklassen werden gleich wie größere Klassen gewichtet. Die Makrogenauigkeit sollte so nahe wie möglich bei 1 liegen.

* Protokollverlust: Siehe [Protokollverlust](../resources/glossary.md#log-loss). Der Protokollverlust sollte so nahe wie möglich bei 0 liegen.

* Verringerung des Protokollverlusts: Liegt zwischen [-inf, 100], wobei „100“ perfekte Vorhersagen und „0“ durchschnittliche Vorhersagen bedeutet. Die Verringerung des Protokollverlusts sollte so nahe wie möglich bei 0 liegen.

### <a name="displaying-the-metrics-for-model-validation"></a>Anzeigen der Metriken zur Modellvalidierung

Verwenden Sie den folgenden Code, um die Metriken anzuzeigen, die Ergebnisse freizugeben und dann mit ihnen zu arbeiten:

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayMetrics)]

### <a name="save-the-trained-and-evaluated-model"></a>Speichern des trainierten und ausgewerteten Modells

An diesem Punkt haben Sie ein Modell vom Typ <xref:Microsoft.ML.Data.TransformerChain%601>, das in eine der vorhandenen oder neuen .NET-Anwendungen integriert werden kann. Fügen Sie zum Speichern Ihres trainierten Modells in einer ZIP-Datei den folgenden Code als nächste Zeile in `BuildAndTrainModel` hinzu, um die `SaveModelAsFile`-Methode aufzurufen:

[!code-csharp[CallSaveModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallSaveModel)]

## <a name="save-the-model-as-a-zip-file"></a>Speichern des Modells als ZIP-Datei

Erstellen Sie die `SaveModelAsFile`-Methode mit dem folgenden Code direkt nach der `Evaluate`-Methode:

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

Die `SaveModelAsFile`-Methode führt die folgenden Aufgaben aus:

* Speichern Sie das Modells als ZIP-Datei.

Erstellen Sie anschließend eine Methode zum Speichern des Modells, damit es wiederverwendet und in anderen Anwendungen integriert werden kann. Der `ITransformer` enthält eine <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)>-Methode mit dem globalen Feld `_modelPath` und einem <xref:System.IO.Stream>. Erstellen Sie `FileStream` unmittelbar vor dem Aufruf der `SaveTo`-Methode, um das Modell als ZIP-Datei zu speichern. Fügen Sie der `SaveModelAsFile`-Methode folgenden Code als nächste Zeile hinzu:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#SaveModel)]

Sie können auch anzeigen, wo die Datei geschrieben wurde, indem Sie mit dem folgenden Code eine Konsolenmeldung mit dem `_modelPath` schreiben:

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="deploy-and-predict-with-a-loaded-model"></a>Bereitstellen eines geladenen Modells und Vorhersagen mit diesem treffen

Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `Evaluate`-Methodenaufruf hinzu:

[!code-csharp[CallPredictIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallPredictIssue)]

Erstellen Sie die `PredictIssue`-Methode unmittelbar nach der `Evaluate`-Methode (und direkt vor der `SaveModelAsFile`-Methode) mithilfe des folgenden Codes:

```csharp
private static void PredictIssue()
{

}
```

Die `PredictIssue`-Methode führt die folgenden Aufgaben aus:

* Erstellen eines einzelnen Issues aus Testdaten
* Vorhersagen des Bereichs basierend auf Testdaten
* Kombinieren von Testdaten und Vorhersagen für die Berichterstattung.
* Anzeigen der vorhergesagten Ergebnisse.

Laden Sie zunächst mit dem folgenden Code das Modell, das Sie zuvor gespeichert haben:

[!code-csharp[LoadModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadModel)]

Fügen Sie ein GitHub-Issue hinzu, um die Vorhersage des trainierten Modells in der `Predict`-Methode zu testen, indem Sie eine `GitHubIssue`-Instanz erstellen:

[!code-csharp[AddTestIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTestIssue)]

[!code-csharp[CreatePredictionEngine](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]
  
Mit diesem Modell können Sie nun die GitHub-Bezeichnung des Bereichs einer einzelnen Instanz der Daten des GitHub-Issues vorhersagen. Verwenden Sie zum Abrufen einer Vorhersage <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> für die Daten. Die Eingabedaten sind eine Zeichenfolge, und das Modell enthält die Featurebereitstellung. Die Pipeline ist während Training und Vorhersage synchronisiert. Sie mussten keinen Vorverarbeitungs-/Featurebereitstellungscode speziell für Vorhersagen schreiben, und die gleiche API wird sowohl für Batch- als auch einmalige Vorhersagen eingesetzt. Fügen Sie für die Vorhersage den folgenden Code zur `PredictIssue`-Methode hinzu:

[!code-csharp[PredictIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#PredictIssue)]

### <a name="using-the-loaded-model-for-prediction"></a>Verwenden des geladenen Modells für Vorhersagen

Zeigen Sie `Area` an, um das Issue zu kategorisieren und eine entsprechende Aktion auszuführen. Erstellen Sie mit dem folgenden <xref:System.Console.WriteLine?displayProperty=nameWithType>-Code eine Anzeige für die Ergebnisse:

[!code-csharp[DisplayResults](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayResults)]

## <a name="results"></a>Ergebnisse

Die Ergebnisse sollten den unten dargestellten ähneln. Während der Pipelineverarbeitung werden Meldungen angezeigt. Sie können Warnungen oder Verarbeitungsmeldungen sehen. Diese Nachrichten wurden der Übersichtlichkeit halber aus den folgenden Ergebnissen entfernt.

```console
=============== Single Prediction just-trained-model - Result: area-System.Net ===============
The model is saved to C:\Users\johalex\dotnet-samples\samples\machine-learning\tutorials\GitHubIssueClassification\bin\Debug\netcoreapp2.0\..\..\..\Models\model.zip
*************************************************************************************************************
*       Metrics for Multi-class Classification model - Test Data
*------------------------------------------------------------------------------------------------------------
*       MicroAccuracy:    0.74
*       MacroAccuracy:    0.687
*       LogLoss:          .932
*       LogLossReduction: 63.852
*************************************************************************************************************
=============== Single Prediction - Result: area-System.Data ===============
```

Herzlichen Glückwunsch! Sie haben jetzt erfolgreich ein Machine Learning-Modell zur Klassifizierung und Vorhersage der Bereichsbezeichnung für ein GitHub-Issue erstellt. Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).

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
> [Vorhersage des Taxifahrtpreises](taxi-fare.md)
