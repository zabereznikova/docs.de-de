---
title: 'Tutorial: Vorhersagen von Preisen per Regression'
description: In diesem Tutorial wird veranschaulicht, wie mit ML.NET ein Regressionsmodell für die Vorhersage von Preisen für Taxifahrten in New York City erstellt wird.
ms.date: 06/30/2020
ms.topic: tutorial
ms.custom: mvc, title-hack-0516
ms.openlocfilehash: 0a8ab9ca07d2d83f41b40a3f5782e8e7e201976f
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803234"
---
# <a name="tutorial-predict-prices-using-regression-with-mlnet"></a>Tutorial: Vorhersagen von Preisen per Regression mit ML.NET

In diesem Tutorial wird veranschaulicht, wie mit ML.NET ein [Regressionsmodell](../resources/glossary.md#regression) für die Vorhersage von Preisen für Taxifahrten in New York City erstellt wird.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> * Vorbereiten und Verstehen der Daten
> * Laden und Transformieren der Daten
> * Auswählen eines Lernalgorithmus
> * Trainieren des Modells
> * Evaluieren des Modells
> * Verwenden des Modells für Vorhersagen

## <a name="prerequisites"></a>Voraussetzungen

* [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) oder höher oder Visual Studio 2017 Version 15.6 oder höher mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.

## <a name="create-a-console-application"></a>Erstellen einer Konsolenanwendung

1. Erstellen Sie eine **.NET Core-Konsolenanwendung** mit dem Namen „TaxiFarePrediction“.

1. Erstellen Sie in Ihrem Projekt ein Verzeichnis mit dem Namen *Data*, um das Dataset und die Modelldateien zu speichern.

1. Installieren Sie das NuGet-Paket **Microsoft.ML**:

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach **Microsoft.ML**, und wählen Sie das Paket in der Liste und anschließend die Schaltfläche **Installieren** aus. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen. Gehen Sie für das NuGet-Paket **Microsoft.ML.FastTreee** genauso vor.

## <a name="prepare-and-understand-the-data"></a>Vorbereiten und Verstehen der Daten

1. Laden Sie die Datasets [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) und [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) herunter, und speichern Sie sie im zuvor erstellten Ordner *Data*. Diese Datasets werden zum Trainieren des Machine Learning-Modells und zum anschließenden Auswerten der Genauigkeit des Modells verwendet. Diese Datasets stammen ursprünglich aus dem [Dataset „NYC TLC Taxi Trip“](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page).

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die „\*.csv“-Dateien, und wählen Sie **Eigenschaften** aus. Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.

1. Öffnen Sie das Dataset **taxi-fare-train.csv**, und sehen Sie sich die Spaltenheader in der ersten Zeile an. Sehen Sie sich jede der Spalten an. Machen Sie sich mit den Daten vertraut, und entscheiden Sie, welche Spalten **Features** sind, und welche Spalte die **Bezeichnung** ist.

`label` ist die Spalte, die vorhergesagt werden soll. Die identifizierten `Features` sind die Eingaben, die Sie für das Modell zum Vorhersagen von `Label` bereitstellen.

Das angegebene Dataset enthält die folgenden Spalten:

* **vendor_id:** Die ID des Taxiunternehmers ist ein Feature.
* **rate_code:** Der Tariftyp der Taxifahrt ist ein Feature.
* **passenger_count:** Die Anzahl der Fahrgäste bei einer Fahrt ist ein Feature.
* **trip_time_in_secs:** Die Dauer der Fahrt. Der Fahrpreis soll vorhergesagt werden, bevor die Fahrt abgeschlossen ist. Zu diesem Zeitpunkt wissen Sie noch nicht, wie lange die Fahrt dauert. Deshalb ist die Fahrtzeit kein Feature, und Sie müssen diese Spalte aus dem Modell ausschließen.
* **trip_distance:** Die Fahrtstrecke ist ein Feature.
* **payment_type:** Die Zahlungsmethode (Bargeld oder Kreditkarte) ist ein Feature.
* **fare_amount:** Der gesamte gezahlte Taxifahrtpreis ist die Bezeichnung.

## <a name="create-data-classes"></a>Erstellen von Datenklassen

Erstellen Sie Klassen für die Eingabedaten und die Vorhersagen:

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.
1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *TaxiTrip.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.
1. Fügen Sie der Formularklasse die folgenden `using`-Anweisungen hinzu:

   [!code-csharp[AddUsings](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/TaxiTrip.cs#1 "Add necessary usings")]

Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code mit den beiden Klassen `TaxiTrip` und `TaxiTripFarePrediction` der Datei *TaxiTrip.cs* hinzu:

[!code-csharp[DefineTaxiTrip](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

`TaxiTrip` ist die Eingabedatenklasse und verfügt über Definitionen für jede der Datasetspalten. Verwenden Sie das <xref:Microsoft.ML.Data.LoadColumnAttribute>-Attribut, um die Indizes der Quellspalten im Dataset festzulegen.

Die Klasse `TaxiTripFarePrediction` stellt die vorhergesagten Ergebnisse dar. Sie verfügt über ein einzelnes Feld für einen Gleitkommawert (`FareAmount`) mit einem angewendeten `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute>-Attribut. Für die Regressionsaufgabe enthält die Spalte **Score** die vorhergesagten Bezeichnungswerte.

> [!NOTE]
> Verwenden Sie den Typ `float`, um Gleitkommawerte in den Eingabe- und Vorhersagedatenklassen darzustellen.

### <a name="define-data-and-model-paths"></a>Definieren von Daten und Modellpfaden

Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:

[!code-csharp[AddUsings](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#1 "Add necessary usings")]

Sie müssen drei Felder erstellen, die die Pfade zu den Dateien mit Datasets und der Datei zum Speichern des Modells enthalten:

* `_trainDataPath` enthält den Pfad zur Datei mit dem Dataset, das zum Trainieren des Modells verwendet wird.
* `_testDataPath` enthält den Pfad zur Datei mit dem Dataset, das zum Evaluieren des Modells verwendet wird.
* `_modelPath` enthält den Pfad zur Datei, in der das trainierte Modell gespeichert ist.

Fügen Sie den folgenden Code direkt über der `Main`-Methode hinzu, um diese Pfade anzugeben, und für die `_textLoader`-Variable:

[!code-csharp[InitializePaths](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#2 "Define variables to store the data file paths")]

Alle ML.NET-Operationen beginnen in der [MLContext-Klasse](xref:Microsoft.ML.MLContext). Beim Initialisieren von `mlContext` wird eine neue ML.NET-Umgebung erstellt, die für alle Objekte des Workflows für die Modellerstellung gemeinsam genutzt werden kann. Die Klasse ähnelt dem Konzept von `DBContext` in Entity Framework.

### <a name="initialize-variables-in-main"></a>Initialisieren von Variablen in Main

Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` in der `Main`-Methode durch den folgenden Code, um die Variable `mlContext` zu deklarieren und zu initialisieren:

[!code-csharp[CreateMLContext](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#3 "Create the ML Context")]

Fügen Sie den folgenden Text als nächste Codezeile in die `Main`-Methode zum Aufruf der `Train`-Methode ein:

[!code-csharp[Train](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#5 "Train your model")]

Die `Train()`-Methode führt die folgenden Aufgaben aus:

* Laden der Daten.
* Extrahieren und Transformieren der Daten.
* Trainieren des Modells.
* Zurückgeben des Modells.

Die `Train`-Methode trainiert das Modell. Erstellen Sie die Methode direkt unter `Main` mit folgendem Code:

```csharp
public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

## <a name="load-and-transform-data"></a>Laden und Transformieren der Daten

Für ML.NET wird die [IDataView-Klasse](xref:Microsoft.ML.IDataView) als flexible, effiziente Möglichkeit zum Beschreiben von Tabellendaten in Zahlen- oder Textform verwendet. Mit `IDataView` können entweder Textdateien geladen werden, oder es kann ein Echtzeitladevorgang durchgeführt werden (z. B. SQL-Datenbank- oder Protokolldateien). Fügen Sie den folgenden Code am Ende der ersten Zeile der `Train()`-Methode hinzu.

[!code-csharp[LoadTrainData](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#6 "loading training dataset")]

Da Sie den Preis der Taxifahrt vorhersagen möchten, ist die Spalte `FareAmount` das `Label`-Element für die Vorhersage (Ausgabe des Modells). Verwenden Sie die `CopyColumnsEstimator`-Transformationsklasse, um `FareAmount` zu kopieren, und fügen Sie den folgenden Code hinzu:

[!code-csharp[CopyColumnsEstimator](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#7 "Use the CopyColumnsEstimator")]

Da der Algorithmus, der das Modell trainiert, **numerische** Features erfordert, müssen Sie die kategorischen Datenwerte (`VendorId`, `RateCode` und `PaymentType`) in Zahlen transformieren (`VendorIdEncoded`, `RateCodeEncoded` und `PaymentTypeEncoded`). Verwenden Sie hierzu die [OneHotEncodingTransformer](xref:Microsoft.ML.Transforms.OneHotEncodingTransformer)-Transformationsklasse, mit der verschiedenen Werten in den Spalten verschiedene numerische Schlüsselwerte zugeordnet werden, und fügen Sie den folgenden Code hinzu:

[!code-csharp[OneHotEncodingEstimator](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#8 "Use the OneHotEncodingEstimator")]

Im letzten Schritt der Vorbereitung der Daten werden alle Feature-Spalten mithilfe der Transformationsklasse `mlContext.Transforms.Concatenate` in die Spalte **Features** kombiniert. Standardmäßig verarbeitet ein Lernalgorithmus nur Merkmale aus der Spalte **Features**. Fügen Sie den folgenden Code hinzu:

[!code-csharp[ColumnConcatenatingEstimator](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#9 "Use the ColumnConcatenatingEstimator")]

## <a name="choose-a-learning-algorithm"></a>Auswählen eines Lernalgorithmus

Bei diesem Problem geht es darum, den Preis einer Taxifahrt in New York City vorherzusagen. Dies mag auf den ersten Blick einfach von der zurückgelegten Stecke abhängen. Taxiunternehmer in New York berechnen jedoch abhängig von anderen Faktoren wie zusätzlichen Fahrgästen oder Kreditkartenzahlung anstelle von Barzahlung unterschiedliche Beträge. Ihr Ziel ist es, den Preiswert vorherzusagen. Dies ist ein realer Wert, der auf anderen Faktoren im Dataset basiert. Wählen Sie hierzu eine Machine Learning-Aufgabe für die [Regression](../resources/glossary.md#regression) aus.

Fügen Sie die Machine Learning-Aufgabe [FastTreeRegressionTrainer](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer) an die Definitionen für die Datentransformation an, indem Sie in `Train()` Folgendes als nächste Codezeile hinzufügen:

[!code-csharp[FastTreeRegressionTrainer](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#10 "Add the FastTreeRegressionTrainer")]

## <a name="train-the-model"></a>Trainieren des Modells

Fügen Sie die folgende Codezeile in der `Train()`-Methode hinzu, um das Modell an die `dataview`-Daten für das Trainieren anzupassen und das trainierte Modell zurückzugeben:

[!code-csharp[TrainModel](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#11 "Train the model")]

Mit der [Fit()](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29)-Methode wird Ihr Modell trainiert, indem das Dataset transformiert und das Training angewendet wird.

Geben Sie das trainierte Modell mit der folgenden Codezeile in der Methode `Train()` zurück:

[!code-csharp[ReturnModel](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#12 "Return the model")]

## <a name="evaluate-the-model"></a>Evaluieren des Modells

Evaluieren Sie als Nächstes die Leistung Ihres Modells mit Ihren Testdaten zur Qualitätssicherung und Validierung. Erstellen Sie mit dem folgenden Code die `Evaluate()`-Methode direkt nach `Train()`:

```csharp
private static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```

Die `Evaluate`-Methode führt die folgenden Aufgaben aus:

* Laden des Testdatasets.
* Erstellen des Regressionsauswerters.
* Evaluieren des Modells und Erstellen von Metriken.
* Anzeigen der Metriken.

Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `Train`-Methodenaufruf hinzu:

[!code-csharp[CallEvaluate](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#14 "Call the Evaluate method")]

Laden Sie das Testdataset, indem Sie die [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A)-Methode verwenden. Evaluieren Sie das Modell, indem Sie dieses Dataset als Qualitätsprüfung verwenden. Fügen Sie hierzu in der `Evaluate`-Methode den folgenden Code hinzu:

[!code-csharp[LoadTestDataset](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#15 "Load the test dataset")]

Fügen Sie als Nächstes `Evaluate()` den folgenden Code hinzu, um die `Test`-Daten zu transformieren:

[!code-csharp[PredictWithTransformer](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#16 "Predict using the Transformer")]

Mit der [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A)-Methode werden Vorhersagen für die Eingabezeilen des Testdatasets getroffen.

Die `RegressionContext.Evaluate`-Methode berechnet die Qualitätsmetriken für das `PredictionModel` mit dem angegebenen Dataset. Das zurückgegebene <xref:Microsoft.ML.Data.RegressionMetrics>-Objekt enthält alle von Regressionsauswertern berechneten Metriken.

Um diese zur Bestimmung der Qualität des Modells anzuzeigen, müssen Sie die Metriken zuerst abzurufen. Fügen Sie der `Evaluate`-Methode folgenden Code als nächste Zeile hinzu:

[!code-csharp[ComputeMetrics](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#17 "Compute Metrics")]

Nach der Vorhersagekonfiguration wertet die [Evaluate()](xref:Microsoft.ML.RegressionCatalog.Evaluate%2A)-Methode das Modell aus. Dabei werden die Vorhersagewerte mit den tatsächlichen `Labels` im Testdataset verglichen und die Leistungsmetriken für das Modell zurückgegeben.

Fügen Sie den folgenden Code hinzu, um das Modell zu evaluieren und die Auswertungsmetriken zu erzeugen:

```csharp
Console.WriteLine();
Console.WriteLine($"*************************************************");
Console.WriteLine($"*       Model quality metrics evaluation         ");
Console.WriteLine($"*------------------------------------------------");
```

[RSquared](../resources/glossary.md#coefficient-of-determination) ist eine weitere Auswertungsmetrik der Regressionsmodelle. RSquared akzeptiert Werte zwischen 0 (null) und 1. Je näher der Wert an 1 liegt, desto besser ist das Modell. Fügen Sie der `Evaluate`-Methode den folgenden Code hinzu, um den RSquared-Wert anzuzeigen:

[!code-csharp[DisplayRSquared](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#18 "Display the RSquared metric.")]

[RMS](../resources/glossary.md#root-of-mean-squared-error-rmse) ist eine der Auswertungsmetriken aus dem Regressionsmodell. Je niedriger sie ausfällt, desto besser ist das Modell. Fügen Sie der `Evaluate`-Methode den folgenden Code hinzu, um den RMS-Wert anzuzeigen:

[!code-csharp[DisplayRMS](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#19 "Display the RMS metric.")]

## <a name="use-the-model-for-predictions"></a>Verwenden des Modells für Vorhersagen

Erstellen Sie die `TestSinglePrediction`-Methode mit dem folgenden Code direkt nach der `Evaluate`-Methode:

```csharp
private static void TestSinglePrediction(MLContext mlContext, ITransformer model)
{

}
```

Die `TestSinglePrediction`-Methode führt die folgenden Aufgaben aus:

* Erstellen eines einzelnen Kommentars aus Testdaten.
* Vorhersagen des Fahrpreisbetrags anhand der Testdaten.
* Kombinieren von Testdaten und Vorhersagen für die Berichterstattung.
* Anzeigen der vorhergesagten Ergebnisse.

Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `Evaluate`-Methodenaufruf hinzu:

[!code-csharp[CallTestSinglePrediction](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#20 "Call the TestSinglePrediction method")]

Fügen Sie `TestSinglePrediction()` den folgenden Code hinzu, um mit `PredictionEngine` den Preis für die Fahrt vorherzusagen:

[!code-csharp[MakePredictionEngine](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#22 "Create the PredictionFunction")]

Die [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) ist eine Hilfs-API, mit der Sie eine Vorhersage für eine einzelne Instanz der Daten treffen können. [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) ist nicht threadsicher. Die Verwendung in Singlethread-oder Prototypumgebungen ist zulässig. Zur Verbesserung der Leistung und Threadsicherheit in Produktionsumgebungen verwenden Sie den `PredictionEnginePool`-Dienst, der einen [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) aus [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)-Objekten für die Verwendung in Ihrer gesamten Anwendung erstellt. Informationen zur [Verwendung von `PredictionEnginePool` in einer ASP.NET Core-Web-API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application) finden Sie in dieser Anleitung.

> [!NOTE]
> Die `PredictionEnginePool`-Diensterweiterung ist derzeit als Vorschauversion verfügbar.

Dieses Tutorial verwendet eine Testfahrt innerhalb dieser Klasse. Sie können später weitere Szenarios zum Experimentieren mit dem Beispiel hinzufügen. Fügen Sie eine Fahrt hinzu, um die Kostenvorhersage des trainierten Modells in der `TestSinglePrediction()`-Methode zu testen, indem Sie eine `TaxiTrip`-Instanz erstellen:

[!code-csharp[PredictionData](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#23 "Create test data for single prediction")]

Als Nächstes wird der Preis für die Fahrt basierend auf einer einzelnen Instanz der Taxifahrtdaten vorhergesagt und an `PredictionEngine` übergeben, indem als nächste Codezeilen der `TestSinglePrediction()`-Methode Folgendes hinzugefügt wird:

[!code-csharp[Predict](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#24 "Create a prediction of taxi fare")]

Die [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A)-Funktion trifft eine Vorhersage für eine einzelne Dateninstanz.

Um den vorhergesagten Preis der angegebenen Fahrt anzuzeigen, fügen Sie den folgenden Code der `TestSinglePrediction`-Methode hinzu:

[!code-csharp[Predict](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#25 "Display the prediction.")]

Führen Sie das Programm aus, um den vorhergesagten Taxifahrtpreis für den Testfall anzuzeigen.

Herzlichen Glückwunsch! Hiermit haben Sie ein Machine Learning-Modell erfolgreich zum Vorhersagen von Taxifahrtpreisen erstellt, die Genauigkeit ausgewertet und es zum Vorhersagen der Preise verwendet. Sie finden den Quellcode für dieses Tutorial im GitHub-Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction).

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
>
> * Vorbereiten und Verstehen der Daten
> * Erstellen einer Lernpipeline
> * Laden und Transformieren der Daten
> * Auswählen eines Lernalgorithmus
> * Trainieren des Modells
> * Evaluieren des Modells
> * Verwenden des Modells für Vorhersagen

Fahren Sie mit dem nächsten Tutorial fort, um mehr zu erfahren.

> [!div class="nextstepaction"]
> [Iris-Clustering](iris-clustering.md)
