---
title: 'Tutorial: Erstellen eines Programms zur Filmempfehlung (Matrixfaktorisierung)'
description: Dieses Tutorial zeigt Ihnen, wie Sie mithilfe von ML.NET in einer .NET Core-Konsolenanwendung ein Filmempfehlungssystem erstellen. Für die Schritte verwenden Sie C# und Visual Studio 2019.
author: briacht
ms.date: 09/30/2019
ms.custom: mvc, title-hack-0516
ms.topic: tutorial
ms.openlocfilehash: 5b4541b527559ee05c9b97d84324e9e70599a014
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977381"
---
# <a name="tutorial-build-a-movie-recommender-using-matrix-factorizaton-with-mlnet"></a>Tutorial: Erstellen eines Programms zur Filmempfehlung mithilfe der Matrixfaktorisierung mit ML.NET

Dieses Tutorial zeigt Ihnen, wie Sie mithilfe von ML.NET in einer .NET Core-Konsolenanwendung ein Filmempfehlungssystem erstellen. Für die Schritte verwenden Sie C# und Visual Studio 2019.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> * Auswählen eines Machine Learning-Algorithmus
> * Vorbereiten und Laden von Daten
> * Erstellen und Trainieren eines Modells
> * Auswerten eines Modells
> * Bereitstellen und Nutzen eines Modells

Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation).

## <a name="machine-learning-workflow"></a>Machine Learning-Workflow

Die folgenden Schritten eignen sich für diese und alle anderen ML.NET-Aufgaben:

1. [Laden von Daten](#load-your-data)
2. [Erstellen und Trainieren des Modells](#build-and-train-your-model)
3. [Auswerten des Modells](#evaluate-your-model)
4. [Verwenden des Modells](#use-your-model)

## <a name="prerequisites"></a>Erforderliche Komponenten

* [Visual Studio 2017 Version 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.

## <a name="select-the-appropriate-machine-learning-task"></a>Auswählen der entsprechenden Machine Learning-Aufgabe

Es gibt mehrere Möglichkeiten, ein Empfehlungssystem umzusetzen. Beispielsweise könnten Sie eine Liste mit empfohlenen Filmen oder mit ähnlichen Produkten erstellen. In diesem Szenario sagt Ihr Modell jedoch vorher, wie ein Benutzer einen bestimmten Film auf einer Skala von eins bis fünf bewertet. Falls dieser Wert höher als ein festgelegter Schwellenwert ist, wird der Film empfohlen. Dabei entsprechen höhere Bewertungen auch einer höheren Wahrscheinlichkeit dafür, dass ein Benutzer einen bestimmten Film mag.

## <a name="create-a-console-application"></a>Erstellen einer Konsolenanwendung

### <a name="create-a-project"></a>Erstellen eines Projekts

1. Öffnen Sie Visual Studio 2017. Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus. Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **.NET Core** aus. Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)**. Geben Sie im Textfeld **Name** „MovieRecommender“ ein, und klicken Sie anschließend auf die Schaltfläche **OK**.

2. Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um das Dataset zu speichern:

    Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus. Geben Sie „Data“ ein, und drücken Sie die EINGABETASTE.

3. Installieren Sie die NuGet-Pakete **Microsoft.ML** und **Microsoft.ML.Recommender**:

    Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach **Microsoft.ML**, und wählen Sie das Paket in der Liste und anschließend die Schaltfläche **Installieren** aus. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen. Wiederholen Sie diese Schritte für **Microsoft.ML.Recommender**.

4. Fügen Sie am Anfang der Datei *Program.cs* die folgenden `using`-Anweisungen hinzu:

    [!code-csharp[UsingStatements](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#UsingStatements "Add necessary usings")]

### <a name="download-your-data"></a>Herunterladen der Daten

1. Laden Sie die beiden Datasets herunter, und speichern Sie sie im Ordner *Data*, den Sie vorher erstellt haben:

   * Klicken Sie mit der rechten Maustaste auf [*recommendation-ratings-train.csv* ](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-train.csv) und anschließend auf „Save Link As...“ (Link speichern unter...) oder „Save Target As...“ (Ziel speichern unter...).
   * Klicken Sie mit der rechten Maustaste auf [*recommendation-ratings-test.csv* ](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-test.csv) und anschließend auf „Save Link As“ (Link speichern unter) oder „Save Target As“ (Ziel speichern unter).

     Achten Sie darauf, \* die CSV-Dateien entweder im Ordner *Data* zu speichern oder sie in den Ordner *Data* zu verschieben, nachdem Sie \* die Dateien an anderer Stelle gespeichert haben.

2. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die \*.csv-Dateien, und wählen Sie **Eigenschaften** aus. Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.

   ![GIF der Auswahl der Option „Kopieren, wenn neuer“](./media/movie-recommendation/copy-to-output-if-newer.gif)

## <a name="load-your-data"></a>Laden von Daten

Der erste Schritt im ML.NET-Prozess besteht darin, die Modelltrainings- und Testdaten vorzubereiten und zu laden.

Die Empfehlungsbewertungsdaten werden in die Datasets `Train` und `Test` unterteilt. Die `Train`-Daten werden verwendet, um das Modell anzupassen. Die `Test`-Daten werden verwendet, um mit dem trainierten Modell Vorhersagen zu treffen und die Modellleistung auszuwerten. `Train`- und `Test`-Daten werden üblicherweise im Verhältnis 80 zu 20 aufgeteilt.

Unten sehen Sie eine Vorschau der Daten aus den CSV-Dateien:

![Screenshot: Vorschau des CVS-Datasets](./media/movie-recommendation/csv-file-dataset-preview.png)

In den CSV-Dateien befinden sich vier Spalten:

* `userId`
* `movieId`
* `rating`
* `timestamp`

Im Machine Learning-Kontext heißen Spalten, mit denen eine Vorhersage getroffen wird, [Features](../resources/glossary.md#feature). Die Spalte mit der zurückgegebenen Vorhersage wird als [Label](../resources/glossary.md#label) bezeichnet.

Da Sie Filmbewertungen vorhersagen möchten, ist `Label` die Bewertungsspalte. Die anderen drei Spalten `userId`, `movieId` und `timestamp` sind alle `Features`, mit denen das `Label` vorhergesagt wird.

| Features      | Bezeichnung         |
| ------------- |:-------------:|
| `userId`        |    `rating`     |
| `movieId`      |               |
| `timestamp`     |               |

Sie müssen selbst entscheiden, welche `Features` Sie verwenden möchten, um das `Label` vorherzusagen. Sie können auch Methoden wie [Permutation Feature Importance](../how-to-guides/explain-machine-learning-model-permutation-feature-importance-ml-net.md) verwenden, um die Auswahl der besten `Features` zu unterstützen.

In diesem Tutorial sollten Sie die `timestamp`-Spalte nicht als `Feature` festlegen, da der Zeitstempel nicht beeinflusst, wie ein Benutzer einen Film bewertet, und daher nicht zu einer genaueren Vorhersage beitragen würde.

| Features      | Bezeichnung         |
| ------------- |:-------------:|
| `userId`        |    `rating`     |
| `movieId`      |               |

Als Nächstes müssen Sie die Datenstruktur für die Eingabeklasse definieren.

Fügen Sie dem Projekt eine neue Klasse hinzu:

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und klicken Sie auf **Hinzufügen > Neues Element**.

2. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *MovieRatingData.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.

Die Datei *MovieRatingData.cs* wird im Code-Editor geöffnet. Fügen Sie am Anfang der Datei *MovieRatingData.cs* die folgende `using`-Anweisung hinzu:

```csharp
using Microsoft.ML.Data;
```

Erstellen Sie eine Klasse mit dem Namen `MovieRating`, indem Sie die vorhandene Klassendefinition entfernen und *MovieRatingData.cs* den folgenden Code hinzufügen:

[!code-csharp[MovieRatingClass](~/samples/machine-learning/tutorials/MovieRecommendation/MovieRatingData.cs#MovieRatingClass "Add the Movie Rating class")]

`MovieRating` ist eine Klasse für Eingabedaten. Das [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29)-Attribut legt fest, welche Spalten (durch Angabe des Spaltenindex) im Dataset geladen werden sollen. Die Spalten `userId` und `movieId` sind `Features`, also die Eingaben, die dem Modell übergeben werden, um das `Label` vorherzusagen. Die Bewertungsspalte ist das vorhergesagte `Label`, also die Ausgabe des Modells.

Erstellen Sie eine weitere Klasse mit dem Namen `MovieRatingPrediction`, um die vorhergesagten Ergebnisse darzustellen, indem Sie nach der Klasse `MovieRating` den folgenden Code in *MovieRatingData.cs* hinzufügen:

[!code-csharp[PredictionClass](~/samples/machine-learning/tutorials/MovieRecommendation/MovieRatingData.cs#PredictionClass "Add the Movie Prediction Class")]

Ersetzen Sie in *Program.cs* innerhalb von `Main()` die Zeile `Console.WriteLine("Hello World!")` durch den folgenden Code:

[!code-csharp[MLContext](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#MLContext "Add MLContext")]

Die [MLContext-Klasse](xref:Microsoft.ML.MLContext) ist der Startpunkt für alle ML.NET-Vorgänge. Durch das Initialisieren von `mlContext` wird eine neue ML.NET-Umgebung erstellt, die für mehrere Objekte des Modellerstellungsworkflows verwendet werden kann. Die Klasse ähnelt dem Konzept von `DBContext` in Entity Framework.

Erstellen Sie nach `Main()` die Methode `LoadData()`:

```csharp
public static (IDataView training, IDataView test) LoadData(MLContext mlContext)
{

}
```

> [!NOTE]
> Diese Methode löst zunächst eine Fehlermeldung aus. Dies ändert sich erst, wenn Sie in den folgenden Schritten eine Rückgabeanweisung hinzufügen.

Fügen Sie den unten aufgeführten Code als nächste Codezeilen in `LoadData()` ein, um die Datenpfadvariablen zu initialisieren, die Daten aus den CSV-Dateien zu laden und die `Train`- und`Test` -Daten als `IDataView`-Objekte zurückzugeben:

[!code-csharp[LoadData](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#LoadData "Load data from data paths")]

Daten werden in ML.NET als [IDataView-Klasse](xref:Microsoft.ML.IDataView) dargestellt. Mit `IDataView` können Tabellendaten (Zahlen und Text) flexibel und effizient beschrieben werden. Daten können aus einer Textdatei oder in Echtzeit (z. B. aus einer SQL-Datenbank oder aus Protokolldateien) in ein `IDataView`-Objekt geladen werden.

Die [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)-Methode definiert das Datenschema und liest die Datei ein. Diese Methode akzeptiert Datenpfadvariablen und gibt ein `IDataView`-Objekt zurück. In diesem Tutorial geben Sie den Pfad für die `Test`- und `Train`-Dateien, den Textdateiheader (zur korrekten Verwendung der Spaltennamen) und das Komma als Zeichendatentrennzeichen an (das Standardtrennzeichen ist ein Tabstopp).

Fügen Sie den folgenden Code zur Methode `Main()` hinzu, um die Methode `LoadData()` aufzurufen und die Daten `Train` und `Test` zurückzugeben:

[!code-csharp[LoadDataMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#LoadDataMain "Add LoadData method to Main")]

## <a name="build-and-train-your-model"></a>Erstellen und Trainieren des Modells

In ML.NET werden die folgenden drei Hauptkonzepte genutzt: [Daten](../resources/glossary.md#data), [Transformatoren](../resources/glossary.md#transformer) (Transformers) und [Schätzer](../resources/glossary.md#estimator) (Estimators).

Für Machine Learning-Trainingsalgorithmen sind Daten in einem bestimmten Format erforderlich. `Transformers` werden verwendet, um Tabellendaten in ein kompatibles Format zu transformieren.

![Diagramm des Transformationsdatenflusses](./media/movie-recommendation/data-transformer-transformed.png)

`Transformers` werden in ML.NET mithilfe von `Estimators` erstellt. `Estimators` akzeptieren Daten und geben `Transformers` zurück.

![Diagramm des Schätzungsdatenflusses](./media/movie-recommendation/data-estimator-transformer.png)

Der Trainingsalgorithmus für Empfehlungen, den Sie für das Training des Modells einsetzen, ist ein Beispiel für einen `Estimator`.

Erstellen Sie mit den folgenden Schritten einen `Estimator`:

Erstellen Sie die `BuildAndTrainModel()`-Methode mit dem folgenden Code direkt nach der `LoadData()`-Methode:

```csharp
public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView trainingDataView)
{

}
```

> [!NOTE]
> Diese Methode löst zunächst eine Fehlermeldung aus. Dies ändert sich erst, wenn Sie in den folgenden Schritten eine Rückgabeanweisung hinzufügen.

Fügen Sie `BuildAndTrainModel()` folgenden Code hinzu, um die Datentransformationen zu definieren:

[!code-csharp[DataTransformations](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#DataTransformations "Define data transformations")]

Da `userId` und `movieId` keine reellen Zahlen, sondern Benutzer und Filmtitel darstellen, verwenden Sie die [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A)-Methode, um jede `userId` und `movieId` in eine `Feature`-Spalte mit einem numerischen Schlüsseltyp (also in ein Format, das von Empfehlungsalgorithmen akzeptiert wird) zu transformieren. Anschließend fügen Sie die Werte als neue Datasetspalten ein:

| userId | movieId | Bezeichnung | userIdEncoded | movieIdEncoded |
| ------------- |:-------------:| -----:|-----:|-----:|
| 1 | 1 | 4 | userKey1 | movieKey1 |
| 1 | 3 | 4 | userKey1 | movieKey2 |
| 1 | 6 | 4 | userKey1 | movieKey3 |

Fügen Sie den unten aufgeführten Code als nächste Codezeilen in `BuildAndTrainModel()` ein, um den Machine Learning-Algorithmus festzulegen und ihn an die Datentransformationsdefinitionen anzufügen:

[!code-csharp[AddAlgorithm](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#AddAlgorithm "Add the training algorithm with options")]

Als Trainingsalgorithmus für Empfehlungen wird der [MatrixFactorizationTrainer](xref:Microsoft.ML.RecommendationCatalog.RecommendationTrainers.MatrixFactorization%28Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options%29) verwendet.  Die [Matrixfaktorisierung](https://en.wikipedia.org/wiki/Matrix_factorization_(recommender_systems)) wird häufig für Empfehlungen eingesetzt, wenn Daten dazu vorliegen, wie Benutzer Produkte in der Vergangenheit bewertet haben. Dies trifft auf die Datasets dieses Tutorials zu. Falls andere Daten verfügbar sind, können noch mehr Empfehlungsalgorithmen eingesetzt werden. Weitere Informationen dazu finden Sie im Abschnitt [Weitere Empfehlungsalgorithmen](#other-recommendation-algorithms) weiter unten.

In diesem Tutorial verwendet der `Matrix Factorization`-Algorithmus kollaborative Filter. Dabei wird Folgendes angenommen: Wenn Benutzer 1 zu einem bestimmten Thema die gleiche Meinung wie Benutzer 2 hat, vertritt Benutzer 1 zu einem anderen Thema mit höherer Wahrscheinlichkeit die gleiche Meinung wie Benutzer 2.

Wenn beispielsweise Benutzer 1 und Benutzer 2 Filme ähnlich bewerten, gefällt Benutzer 2 mit höherer Wahrscheinlichkeit ein Film, den Benutzer 1 angesehen und hoch bewertet hat:

| | `Incredibles 2 (2018)` | `The Avengers (2012)` | `Guardians of the Galaxy (2014)` |
| -------------:|-------------:| -----:|-----:|
| Benutzer 1 | Hat den Film gesehen und ihn gemocht | Hat den Film gesehen und ihn gemocht | Hat den Film gesehen und ihn gemocht |
| Benutzer 2 | Hat den Film gesehen und ihn gemocht | Hat den Film gesehen und ihn gemocht | Hat den Film nicht gesehen; Film wird empfohlen |

Der `Matrix Factorization`-Trainer kann durch mehrere [Optionen](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options) angepasst werden. Weitere Informationen zu diesen finden Sie im Abschnitt [Hyperparameter für Algorithmen](#algorithm-hyperparameters) weiter unten.

Fügen Sie den unten aufgeführten Code als nächste Codezeilen in die `BuildAndTrainModel()`-Methode ein, um das Modell an die `Train`-Daten anzupassen und das trainierte Modell zurückzugeben:

[!code-csharp[FitModel](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#FitModel "Call the Fit method and return back the trained model")]

Die [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29)-Methode trainiert das Modell mit dem bereitgestellten Trainingsdataset. Sie führt die `Estimator`-Definitionen aus, indem sie die Daten transformiert und das Training durchführt. Anschließend gibt sie das trainierte Modell als `Transformer` zurück.

Fügen Sie den unten aufgeführten Code als nächste Codezeile in der Methode `Main()` hinzu, um die `BuildAndTrainModel()`-Methode aufzurufen und das trainierte Modell zurückzugeben:

[!code-csharp[BuildTrainModelMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#BuildTrainModelMain "Add BuildAndTrainModel method in Main")]

## <a name="evaluate-your-model"></a>Auswerten des Modells

Nachdem Sie Ihr Modell trainiert haben, werten Sie mit den Testdaten die Modellleistung aus.

Erstellen Sie die `EvaluateModel()`-Methode mit dem folgenden Code direkt nach der `BuildAndTrainModel()`-Methode:

```csharp
public static void EvaluateModel(MLContext mlContext, IDataView testDataView, ITransformer model)
{

}
```

Fügen Sie `EvaluateModel()` den folgenden Code hinzu, um die `Test`-Daten zu transformieren:

[!code-csharp[Transform](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#Transform "Transform the test data")]

Die [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A)-Methode trifft Vorhersagen für mehrere bereitgestellte Eingabezeilen eines Testdatasets.

Fügen Sie den unten aufgeführten Code als nächste Codezeile in die `EvaluateModel()`-Methode ein, um das Modell auszuwerten:

[!code-csharp[Evaluate](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#Evaluate "Evaluate the model using predictions from the test data")]

Nach der Vorhersagekonfiguration wertet die [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A)-Methode das Modell aus. Dabei werden die Vorhersagewerte mit den tatsächlichen `Labels` im Testdataset verglichen und die Leistungsmetriken für das Modell zurückgegeben.

Fügen Sie den unten aufgeführten Code als nächste Codezeilen in die `EvaluateModel()`-Methode ein, um die Auswertungsmetriken auf der Konsole auszugeben:

[!code-csharp[PrintMetrics](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#PrintMetrics "Print the evaluation metrics")]

Fügen Sie den unten aufgeführten Code als nächste Codezeile in die `Main()`-Methode ein, um die `EvaluateModel()`-Methode aufzurufen:

[!code-csharp[EvaluateModelMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#EvaluateModelMain "Add EvaluateModel method in Main")]

Bis hierhin sollte die Ausgabe in etwa wie folgt aussehen:

```console
=============== Training the model ===============
iter      tr_rmse          obj
   0       1.5403   3.1262e+05
   1       0.9221   1.6030e+05
   2       0.8687   1.5046e+05
   3       0.8416   1.4584e+05
   4       0.8142   1.4209e+05
   5       0.7849   1.3907e+05
   6       0.7544   1.3594e+05
   7       0.7266   1.3361e+05
   8       0.6987   1.3110e+05
   9       0.6751   1.2948e+05
  10       0.6530   1.2766e+05
  11       0.6350   1.2644e+05
  12       0.6197   1.2541e+05
  13       0.6067   1.2470e+05
  14       0.5953   1.2382e+05
  15       0.5871   1.2342e+05
  16       0.5781   1.2279e+05
  17       0.5713   1.2240e+05
  18       0.5660   1.2230e+05
  19       0.5592   1.2179e+05
=============== Evaluating the model ===============
Rms: 0.994051469730769
RSquared: 0.412556298844873
```

Diese Ausgabe enthält 20 Iterationen. Bei jeder Iteration verringert sich der Fehlermesswert und nähert sich immer mehr 0 an.

Die Wurzel der mittleren Fehlerquadratsumme (`root of mean squared error`; auch als RMS oder RMSE bezeichnet) wird verwendet, um die Unterschiede zwischen den vom Modell vorhergesagten Werten und den Beobachtungswerten des Testdatasets zu messen. Es handelt sich dabei um die Quadratwurzel der durchschnittlichen Fehlerquadrate. Je niedriger sie ausfällt, desto besser ist das Modell.

`R Squared` gibt an, wie gut Daten zu einem Modell passen. Die Werte liegen zwischen 0 und 1. Der Wert 0 bedeutet, dass die Daten zufällig sind oder nicht an das Modell angepasst werden können. Ein Wert von 1 bedeutet, dass das Modell exakt mit den Daten übereinstimmt. Der Wert von `R Squared` sollte möglichst nahe bei 1 liegen.

Erfolgreiche Modelle zu erstellen ist ein iterativer Prozess. Dieses Modell hat erst geringere Qualität, da das Tutorial kleine Datasets verwendet, um schnelles Modelltraining zu ermöglichen. Wenn Sie nicht mit der Modellqualität zufrieden sind, können Sie versuchen, sie durch die Bereitstellung größerer Trainingsdatasets oder die Auswahl anderer Trainingsalgorithmen mit anderen Hyperparametern für jeden Algorithmus zu verbessern. Weitere Informationen finden Sie im Abschnitt [Verbessern des Modells](#improve-your-model) weiter unten.

## <a name="use-your-model"></a>Verwenden Ihres Modells

Nun können Sie mit dem trainierten Modell Vorhersagen für neue Daten treffen.

Erstellen Sie die `UseModelForSinglePrediction()`-Methode mit dem folgenden Code direkt nach der `EvaluateModel()`-Methode:

```csharp
public static void UseModelForSinglePrediction(MLContext mlContext, ITransformer model)
{

}
```

Fügen Sie `UseModelForSinglePrediction()` den folgenden Code hinzu, um mit `PredictionEngine` die Bewertung vorherzusagen:

[!code-csharp[PredictionEngine](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#PredictionEngine "Create Prediction Engine")]

Die [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) ist eine Hilfs-API, mit der Sie eine Vorhersage für eine einzelne Instanz der Daten treffen können. [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) ist nicht threadsicher. Die Verwendung in Singlethread-oder Prototypumgebungen ist zulässig. Zur Verbesserung der Leistung und Threadsicherheit in Produktionsumgebungen verwenden Sie den `PredictionEnginePool`-Dienst, der einen [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) aus [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)-Objekten für die Verwendung in Ihrer gesamten Anwendung erstellt. Informationen zur [Verwendung von `PredictionEnginePool` in einer ASP.NET Core-Web-API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application) finden Sie in dieser Anleitung.

> [!NOTE]
> Die `PredictionEnginePool`-Diensterweiterung ist derzeit als Vorschauversion verfügbar.

Fügen Sie den unten aufgeführten Code als nächste Codezeilen in die `UseModelForSinglePrediction()`-Methode ein, um eine Instanz von `MovieRating` mit dem Namen `testInput` zu erstellen und diese der PredictionEngine-Klasse zu übergeben:

[!code-csharp[MakeSinglePrediction](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#MakeSinglePrediction "Make a single prediction with the Prediction Engine")]

Die [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A)-Funktion trifft eine Vorhersage für eine einzelne Datenspalte.

Anschließend können Sie mit dem `Score` (der vorhergesagten Bewertung) bestimmen, ob der Film mit der movieId 10 Benutzer 6 empfohlen werden soll. Je höher der `Score`, desto höher ist die Wahrscheinlichkeit, dass einem Benutzer ein bestimmter Film gefällt. In diesem Tutorial wird festgelegt, dass Filme mit einer höheren Bewertung als 3,5 empfohlen werden.

Fügen Sie den unten aufgeführten Code als nächste Codezeilen in die `UseModelForSinglePrediction()`-Methode ein, um die Ergebnisse auszugeben:

[!code-csharp[PrintResults](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#PrintResults "Print the recommendation prediction results")]

Fügen Sie den unten aufgeführten Code als nächste Codezeile in die `Main()`-Methode ein, um die `UseModelForSinglePrediction()`-Methode aufzurufen:

[!code-csharp[UseModelMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#UseModelMain "Add UseModelForSinglePrediction method in Main")]

Die Ausgabe dieser Methode sollte in etwa wie folgt aussehen:

```console
=============== Making a prediction ===============
Movie 10 is recommended for user 6
```

### <a name="save-your-model"></a>Speichern des Modells

Sie müssen das Modell zuerst speichern, um damit Vorhersagen in Endbenutzeranwendungen treffen zu können.

Erstellen Sie die `SaveModel()`-Methode mit dem folgenden Code direkt nach der `UseModelForSinglePrediction()`-Methode:

```csharp
public static void SaveModel(MLContext mlContext, DataViewSchema trainingDataViewSchema, ITransformer model)
{

}
```

Fügen Sie der `SaveModel()`-Methode folgenden Code hinzu, um das trainierte Modell zu speichern:

[!code-csharp[SaveModel](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#SaveModel "Save the model to a zip file")]

Diese Methode speichert das trainierte Modell in einer ZIP-Datei (im Ordner „Data“), die anschließend in anderen .NET-Anwendungen für Vorhersagen verwendet werden kann.

Fügen Sie den unten aufgeführten Code als nächste Codezeile in die `Main()`-Methode ein, um die `SaveModel()`-Methode aufzurufen:

[!code-csharp[SaveModelMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#SaveModelMain "Create SaveModel method in Main")]

### <a name="use-your-saved-model"></a>Verwenden des gespeicherten Modells

Nachdem Sie Ihr trainiertes Modell gespeichert haben, können Sie das Modell in verschiedenen Umgebungen nutzen. Weitere Informationen zum Nutzbarmachen eines trainierten Machine Learning-Modells in Apps finden Sie unter [Speichern und Laden trainierter Modelle](../how-to-guides/save-load-machine-learning-models-ml-net.md).

## <a name="results"></a>Ergebnisse

Nachdem Sie die obigen Schritte durchgeführt haben, können Sie nun die Konsolen-App ausführen (STRG+F5). Die Ergebnisse der obigen Vorhersage sollten in etwa wie folgt aussehen. Möglicherweise werden Warnungen oder Verarbeitungsnachrichten angezeigt. Diese wurden jedoch aus Gründen der Übersichtlichkeit aus den folgenden Ergebnissen entfernt.

```console
=============== Training the model ===============
iter      tr_rmse          obj
   0       1.5382   3.1213e+05
   1       0.9223   1.6051e+05
   2       0.8691   1.5050e+05
   3       0.8413   1.4576e+05
   4       0.8145   1.4208e+05
   5       0.7848   1.3895e+05
   6       0.7552   1.3613e+05
   7       0.7259   1.3357e+05
   8       0.6987   1.3121e+05
   9       0.6747   1.2949e+05
  10       0.6533   1.2766e+05
  11       0.6353   1.2636e+05
  12       0.6209   1.2561e+05
  13       0.6072   1.2462e+05
  14       0.5965   1.2394e+05
  15       0.5868   1.2352e+05
  16       0.5782   1.2279e+05
  17       0.5713   1.2227e+05
  18       0.5637   1.2190e+05
  19       0.5604   1.2178e+05
=============== Evaluating the model ===============
Rms: 0.977175077487166
RSquared: 0.43233349213192
=============== Making a prediction ===============
Movie 10 is recommended for user 6
=============== Saving the model to a file ===============
```

Herzlichen Glückwunsch! Sie haben ein Machine Learning-Modell zur Empfehlung von Filmen erstellt. Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation).

## <a name="improve-your-model"></a>Verbessern des Modells

Es gibt mehrere Möglichkeiten, die Leistung des Modells zu verbessern, um so genauere Vorhersagen treffen zu können.

### <a name="data"></a>Daten

Wenn Sie mehr Trainingsdaten mit ausreichend Beispielen für jeden Benutzer und für jede movieId hinzufügen, kann die Qualität des Empfehlungsmodells gesteigert werden.

Die [Kreuzvalidierung](../how-to-guides/train-machine-learning-model-cross-validation-ml-net.md) ist eine Methode zur Auswertung von Modellen, bei der nicht –wie in diesem Tutorial – Testdaten aus dem Dataset extrahiert, sondern stattdessen nach dem Zufallsprinzip Daten in Teilmengen aufgeteilt werden. Anschließend werden einige Gruppen als Trainingsdaten und einige als Testdaten verwendet. Diese Methode führt im Vergleich zur Aufteilung von Daten in Trainings- und Testdatasets zu einer höheren Modellqualität.

### <a name="features"></a>Features

In diesem Tutorial verwenden Sie nur die drei `Features` (`user id`, `movie id` und `rating`), die vom Dataset bereitgestellt werden.

Dies ist für den Anfang ausreichend. In einem echten Szenario sollten Sie jedoch weitere Attribute oder `Features` (beispielsweise Alter, Geschlecht, Standort usw.) hinzufügen, falls diese im Dataset enthalten sind. Durch das Hinzufügen relevanter `Features` können Sie die Leistung des Empfehlungsmodells verbessern.

Wenn Sie nicht genau wissen, welche `Features` für Ihre Machine Learning-Aufgabe am relevantesten sind, können Sie auch die Methoden Feature Contribution Calculation (FCC) und [Permutation Feature Importance](../how-to-guides/explain-machine-learning-model-permutation-feature-importance-ml-net.md) verwenden, die ML.NET zur Ermittlung der wichtigsten `Features` bereitstellt.

### <a name="algorithm-hyperparameters"></a>Hyperparameter für Algorithmen

ML.NET stellt viele effiziente Trainingsalgorithmen bereit. Sie können die Leistung allerdings noch weiter optimieren, indem Sie die [Hyperparameter](../resources/glossary.md#hyperparameter) des Algorithmus anpassen.

Bei `Matrix Factorization` können Sie mit Hyperparametern wie [NumberOfIterations](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.NumberOfIterations) und [ApproximationRank](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.ApproximationRank) experimentieren, um möglicherweise bessere Ergebnisse zu erzielen.

In diesem Tutorial werden beispielsweise folgende Algorithmusoptionen verwendet:

```csharp
var options = new MatrixFactorizationTrainer.Options
{
    MatrixColumnIndexColumnName = "userIdEncoded",
    MatrixRowIndexColumnName = "movieIdEncoded",
    LabelColumnName = "Label",
    NumberOfIterations = 20,
    ApproximationRank = 100
};
```

### <a name="other-recommendation-algorithms"></a>Weitere Empfehlungsalgorithmen

Der Algorithmus zur Matrixfaktorisierung mit kollaborativen Filtern ist nur eine Möglichkeit für Filmempfehlungen. In vielen Fällen verfügen Sie möglicherweise nicht über die Bewertungsdaten, sondern nur über den Filmverlauf der Benutzer. In anderen Fällen sind eventuell zusätzlich zu den Bewertungsdaten der Benutzer noch weitere Daten verfügbar.

| Algorithmus       | Szenario           | Beispiel  |
| ------------- |:-------------:| -----:|
| One Class Matrix Factorization (Matrixfaktorisierung mit einer Klasse) | Verwenden Sie diesen Algorithmus, wenn nur userId und movieId zur Verfügung stehen. Diese Empfehlungsstrategie wird für Szenarios eingesetzt, in denen Produkte oft zusammen gekauft werden. Kunden werden auf diese Weise empfohlene Produkte auf Grundlage des eigenen Bestellverlaufs angezeigt. | [> Ausprobieren](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/MatrixFactorization_ProductRecommendation) |
| Field Aware Factorization Machines (Faktorisierungsverfahren mit Berücksichtigung von Feldern) | Verwenden Sie diesen Algorithmus für Empfehlungen, wenn zusätzlich zur userId, productId und Bewertung noch weitere Features wie eine Produktbeschreibung oder ein Produktpreis vorhanden sind. Auch bei dieser Methode kommen kollaborative Filter zum Einsatz. | [> Ausprobieren](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/end-to-end-apps/Recommendation-MovieRecommender) |

### <a name="new-user-scenario"></a>Szenario mit neuen Benutzern

Bei kollaborativen Filtern tritt häufig das sogenannte Kaltstartproblem auf. Hierbei müssen für neue Benutzer Rückschlüsse gezogen werden, obwohl noch keine Datengrundlage vorhanden ist. Das Problem wird oft dadurch gelöst, dass neue Benutzer aufgefordert werden, ein Profil zu erstellen und z. B. bereits gesehene Filme zu bewerten. Diese Methode stellt zwar für Benutzer einen gewissen Aufwand dar, liefert jedoch zumindest einige Startdaten für neue Benutzer ohne Bewertungsverlauf.

## <a name="resources"></a>Ressourcen

Die Daten aus diesem Tutorial stammen aus dem [MovieLens-Dataset](http://files.grouplens.org/datasets/movielens/).

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
>
> * Auswählen eines Machine Learning-Algorithmus
> * Vorbereiten und Laden von Daten
> * Erstellen und Trainieren eines Modells
> * Auswerten eines Modells
> * Bereitstellen und Nutzen eines Modells

Wechseln Sie zum nächsten Tutorial, um mehr zu erfahren.
> [!div class="nextstepaction"]
> [Standpunktanalyse](sentiment-analysis.md)
