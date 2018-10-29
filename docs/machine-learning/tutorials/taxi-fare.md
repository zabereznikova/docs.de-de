---
title: Verwenden von ML.NET, um Taxifahrtpreise in New York vorherzusagen (Regression)
description: Erfahren Sie, wie Sie ML.NET in einem Regressionsszenario verwenden.
author: aditidugar
ms.author: johalex
ms.date: 07/02/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: bfae97d65ec192e9289841c82d84807b4937b09a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50183814"
---
# <a name="tutorial-use-mlnet-to-predict-new-york-taxi-fares-regression"></a>Tutorial: Verwenden von ML.NET, um Taxifahrtpreise in New York vorherzusagen (Regression)

> [!NOTE]
> Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden. Weitere Informationen finden Sie in der [ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

In diesem Tutorial wird veranschaulicht, wie ML.NET zum Erstellen eines [Regressionsmodells](../resources/glossary.md#regression) für die Vorhersage von Taxifahrtpreisen in New York City verwendet wird.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> * Das Problem verstehen
> * Auswählen der entsprechenden Machine Learning-Aufgabe
> * Vorbereiten und Verstehen der Daten
> * Erstellen einer Lernpipeline
> * Laden und Transformieren der Daten
> * Auswählen eines Lernalgorithmus
> * Trainieren des Modells
> * Evaluieren des Modells
> * Verwenden des Modells für Vorhersagen

## <a name="prerequisites"></a>Erforderliche Komponenten

* [Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.

## <a name="understand-the-problem"></a>Das Problem verstehen

Bei diesem Problem geht es darum, den Fahrtpreis einer Taxifahrt in New York City vorherzusagen. Dies mag auf den ersten Blick einfach von der zurückgelegten Stecke abhängen. Taxiunternehmer in New York berechnen jedoch abhängig von anderen Faktoren wie zusätzlichen Fahrgästen oder Kreditkartenzahlung anstelle von Barzahlung unterschiedliche Beträge.

## <a name="select-the-appropriate-machine-learning-task"></a>Auswählen der entsprechenden Machine Learning-Aufgabe

Ihr Ziel ist es, den Preiswert vorherzusagen, was einem echten Wert entspricht, der auf anderen Faktoren im Dataset basiert. Wählen Sie hierzu eine Machine Learning-[Regressionsaufgabe](../resources/glossary.md#regression) aus.

## <a name="create-a-console-application"></a>Erstellen einer Konsolenanwendung

1. Öffnen Sie Visual Studio 2017. Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus. Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **.NET Core** aus. Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)**. Geben Sie „TaxiFarePrediction“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.

1. Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um das Dataset und die Modelldateien zu speichern:

    Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus. Geben Sie „Data“ ein, und drücken Sie die EINGABETASTE.

1. Installieren Sie das NuGet-Paket **Microsoft.ML**:

    Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach **Microsoft.ML**, wählen Sie das Paket in der Liste aus, und klicken Sie anschließend auf die Schaltfläche **Installieren**. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.

## <a name="prepare-and-understand-the-data"></a>Vorbereiten und Verstehen der Daten

1. Laden Sie die Datasets [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) und [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) herunter, und speichern Sie sie im zuvor erstellten Ordner *Data*. Diese Datasets werden zum Trainieren des Machine Learning-Modells und zum anschließenden Auswerten der Genauigkeit des Modells verwendet. Diese Datasets stammen ursprünglich aus dem [Dataset „NYC TLC Taxi Trip“](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die „\*.csv“-Dateien, und wählen Sie **Eigenschaften** aus. Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.

1. Öffnen Sie das Dataset **taxi-fare-train.csv**, und sehen Sie sich die Spaltenheader in der ersten Zeile an. Sehen Sie sich jede der Spalten an. Machen Sie sich mit den Daten vertraut, und entscheiden Sie, welche Spalten **Features** sind, und welche Spalte die **Bezeichnung** ist.

Die **Bezeichnung** ist der Bezeichner der Spalte, die Sie vorhersagen möchten. Die angegebenen **Features** werden verwendet, um die Bezeichnung vorherzusagen.

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

   [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code mit den beiden Klassen `TaxiTrip` und `TaxiTripFarePrediction` der Datei *TaxiTrip.cs* hinzu:

[!code-csharp[DefineTaxiTrip](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

`TaxiTrip` ist die Eingabedatenklasse und verfügt über Definitionen für jede der Datasetspalten. Verwenden Sie das [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute)-Attribut, um die Indizes der Quellspalten im Dataset festzulegen.

Die Klasse `TaxiTripFarePrediction` stellt die vorhergesagten Ergebnisse dar. Sie verfügt über ein einzelnes Feld für einen Gleitkommawert (`FareAmount`) mit einem angewendeten `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute)-Attribut. Für die Regressionsaufgabe enthält die Spalte **Score** die vorhergesagten Bezeichnungswerte.

> [!NOTE]
> Verwenden Sie den Typ `float`, um Gleitkommawerte in den Eingabe- und Vorhersagedatenklassen darzustellen.

## <a name="define-data-and-model-paths"></a>Definieren von Daten und Modellpfaden

Wechseln Sie zurück zur Datei *Program.cs*, und fügen Sie drei Felder hinzu, die die Pfade zu den Dateien mit Datasets und zur Datei zum Speichern des Modells enthalten:

* `_datapath` enthält den Pfad zur Datei mit dem Dataset, das zum Trainieren des Modells verwendet wird.
* `_testdatapath` enthält den Pfad zur Datei mit dem Dataset, das zum Evaluieren des Modells verwendet wird.
* `_modelpath` enthält den Pfad zur Datei, in der das trainierte Modell gespeichert ist.

Fügen Sie den folgenden Code direkt über der `Main`-Methode hinzu, um diese Pfade anzugeben:

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

Fügen Sie die folgende `using`-Anweisung am Anfang der Datei *Program.cs* hinzu, um den obenstehenden Code zu kompilieren:

[!code-csharp[AddUsingsForPaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#17 "Using statements for path definitions")]

## <a name="create-a-learning-pipeline"></a>Erstellen einer Lernpipeline

Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

Ersetzen Sie in der `Main`-Methode `Console.WriteLine("Hello World!")` durch den folgenden Code:

```csharp
PredictionModel<TaxiTrip, TaxiTripFarePrediction> model = Train();
```

Die `Train`-Methode trainiert das Modell. Erstellen Sie die Methode direkt unter `Main` mit folgendem Code:

```csharp
public static PredictionModel<TaxiTrip, TaxiTripFarePrediction> Train()
{

}
```

Die Lernpipeline lädt alle Daten und Algorithmen, die zum Trainieren des Modells erforderlich sind. Fügen Sie den folgenden Code der `Train`-Methode hinzu:

```csharp
var pipeline = new LearningPipeline();
```

## <a name="load-and-transform-data"></a>Laden und Transformieren der Daten

Der erste Schritt besteht im Laden der Daten aus dem Trainingsdataset. In diesem Fall wird das Trainingsdataset in der Textdatei mit einem Pfad gespeichert, der vom Feld `_datapath` definiert wird. Die Datei enthält den Header mit den Spaltennamen, weshalb die erste Zeile beim Laden der Daten ignoriert werden sollte. Die Spalten in der Datei werden durch Kommas („,“) getrennt. Fügen Sie den folgenden Code der `Train`-Methode hinzu:

```csharp
pipeline.Add(new TextLoader(_datapath).CreateFrom<TaxiTrip>(useHeader: true, separator: ','));
```

In den nächsten Schritten werden die Spalten mit den jeweiligen in der `TaxiTrip`-Klasse definierten Namen bezeichnet.

Wenn das Modell trainiert und ausgewertet wurde, gelten die Werte in der Spalte **Label** standardmäßig als richtige Werte, die vorhergesagt werden. Da der Fahrpreis der Taxifahrt vorhergesagt werden soll, kopieren Sie die Spalte `FareAmount` in die Spalte **Label**. Verwenden Sie hierzu <xref:Microsoft.ML.Legacy.Transforms.ColumnCopier>, und fügen Sie den folgenden Code hinzu:

```csharp
pipeline.Add(new ColumnCopier(("FareAmount", "Label")));
```

Da der Algorithmus, der das Modell trainiert, **numerische** Features erfordert, müssen Sie die kategorischen Datenwerte (`VendorId`, `RateCode` und `PaymentType`) in Zahlen transformieren. Verwenden Sie hierzu die Klasse <xref:Microsoft.ML.Legacy.Transforms.CategoricalOneHotVectorizer>, die verschiedenen Werten in den Spalten verschiedene numerische Schlüsselwerte zuordnet, und fügen Sie den folgenden Code hinzu:

```csharp
pipeline.Add(new CategoricalOneHotVectorizer("VendorId",
                                             "RateCode",
                                             "PaymentType"));
```

Im letzten Schritt der Vorbereitung der Daten werden alle Feature-Spalten mithilfe der Transformationsklasse <xref:Microsoft.ML.Legacy.Transforms.ColumnConcatenator> in die Spalte **Features** kombiniert. Standardmäßig verarbeitet ein Lernalgorithmus nur Merkmale aus der Spalte **Features**. Fügen Sie den folgenden Code hinzu:

```csharp
pipeline.Add(new ColumnConcatenator("Features",
                                    "VendorId",
                                    "RateCode",
                                    "PassengerCount",
                                    "TripDistance",
                                    "PaymentType"));
```

Beachten Sie, dass die `TripTime`-Spalte, die der `trip_time_in_secs`-Spalte in der Dataset-Datei entspricht, nicht enthalten ist. Sie haben bereits bestimmt, dass sie kein nützliches Feature für die Vorhersage ist.

> [!NOTE]
> Diese Schritte müssen der Pipeline zur erfolgreichen Ausführung in der oben angegebenen Reihenfolge hinzugefügt werden.

## <a name="choose-a-learning-algorithm"></a>Auswählen eines Lernalgorithmus

Nach dem Hinzufügen von Daten zur Pipeline und dem Transformieren in das richtige Eingabeformat wählen Sie einen Lernalgorithmus (**Lernmodul**) aus. Das Lernmodul trainiert das Modell. Da Sie für dieses Problem eine **Regressionsaufgabe** ausgewählt haben, verwenden Sie ein <xref:Microsoft.ML.Legacy.Trainers.FastTreeRegressor>-Lernmodul. Dies ist ein von ML.NET bereitgestelltes Regressionslernmodul.

Das Lernmodul <xref:Microsoft.ML.Legacy.Trainers.FastTreeRegressor> verwendet Gradient Boosting. Gradient Boosting ist eine Machine Learning-Technik für Regressionsprobleme. Sie erstellt jede Regressionsstruktur schrittweise. Sie verwendet eine vordefinierte Verlustfunktion, um den Fehler in jedem Schritt zu messen und im nächsten zu beheben. Das Ergebnis ist ein Vorhersagemodell, das sich im Grunde aus schwächeren Vorhersagemodellen zusammensetzt. Weitere Informationen zu Gradient Boosting finden Sie unter [Boosted-Entscheidungsstrukturregression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression).

Fügen Sie den folgenden Code nach dem im vorherigen Schritt hinzugefügten Datenverarbeitungscode in die `Train`-Methode ein:

```csharp
pipeline.Add(new FastTreeRegressor());
```

Sie haben alle vorherigen Schritte als einzelne Anweisungen der Pipeline hinzugefügt, aber C# verfügt über eine praktische Initialisierungssyntaxsammlung, die das Erstellen und Initialisieren der Pipeline vereinfacht. Ersetzen Sie den Code, den Sie bislang der `Train`-Methode hinzugefügt haben, durch den folgenden Code:

[!code-csharp[CreatePipeline](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create and initialize the learning pipeline")]

## <a name="train-the-model"></a>Trainieren des Modells

Der letzte Schritt ist das Trainieren des Modells. Bis zu diesem Punkt wurde nichts in der Pipeline ausgeführt. Die Methode `pipeline.Train<TInput, TOutput>` erzeugt das Modell, das eine Instanz vom Typ `TInput` annimmt und eine Instanz vom Typ `TOutput` ausgibt. Fügen Sie den folgenden Code der `Train`-Methode hinzu:

[!code-csharp[TrainMOdel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#4 "Train your model")]

Und das ist schon alles! Sie haben erfolgreich ein Machine Learning-Modell trainiert, das Taxifahrtpreise in NYC vorhersagen kann. Anschließend erfahren Sie, wie genau das Modell ist, und wie Sie es verwenden, um die Fahrpreiswerte vorherzusagen.

### <a name="save-the-model"></a>Speichern des Modells

An diesem Punkt haben Sie ein Modell, das in eine der vorhandenen oder neuen .NET-Anwendungen integriert werden kann. Fügen Sie folgenden Code am Ende der `Train`-Methode hinzu, um das Modell in einer ZIP-Datei zu speichern:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Save the model asynchronously and return the model")]

Wenn die `await`-Anweisung dem `model.WriteAsync`-Aufruf hinzugefügt wird, bedeutet dies, dass die `Train`-Methode in eine asynchrone Methode geändert werden muss, die eine Aufgabe zurückgibt. Ändern Sie die Signatur von `Train` wie im folgenden Code gezeigt:

[!code-csharp[AsyncTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "Make the Train method async and return a task.")]

Eine Änderung des Rückgabetyps der `Train`-Methode bedeutet, dass Sie wie im folgenden Code dargestellt ein `await` dem Code hinzufügen müssen, der `Train` in der `Main`-Methode aufruft:

[!code-csharp[AwaitTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Await the Train method")]

Wenn Sie `await` in der Methode `Main` verwenden, bedeutet dies, dass die `Main`-Methode den Modifizierer `async` erfordert und eine Aufgabe `Task` zurückgeben muss:

[!code-csharp[AsyncMain](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Make the Main method async and return a task.")]

Außerdem müssen Sie die folgende `using`-Anweisung am Anfang der Datei hinzufügen:

[!code-csharp[UsingTasks](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Add System.Threading.Tasks. to your usings.")]

Da die `async Main`-Methode ein neues Feature in C# 7.1 und die Standardsprachversion des Projekts C# 7.0 ist, müssen Sie die Sprachversion auf C# 7.1 oder höher ändern. Klicken Sie hierzu im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektknoten, und wählen Sie **Eigenschaften** aus. Wählen Sie die Registerkarte **Build** aus, und klicken Sie auf **Erweitert**. Wählen Sie in der Dropdownliste **C# 7.1** (oder eine höhere Version) aus. Klicken Sie auf die Schaltfläche **OK**.

## <a name="evaluate-the-model"></a>Evaluieren des Modells

Mit der Auswertung wird überprüft, wie gut das Modell Bezeichnungswerte vorhersagt. Es ist wichtig, dass das Modell gute Vorhersagen zu Daten trifft, die nicht zum Trainieren des Modells verwendet wurden. Eine Möglichkeit hierfür ist es, die Daten wie in diesem Tutorial in Trainings- und Testdatasets aufzuteilen. Da Sie nun das Modell anhand der Trainingsdaten trainiert haben, können Sie prüfen, wie gut es mit den Testdaten arbeitet.

Wechseln Sie zurück zu der `Main`-Methode, und fügen Sie den folgenden Code unter dem Aufruf der `Train`-Methode ein:

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Evaluate the model.")]

Die Methode `Evaluate` wertet das Modell aus. Fügen Sie den folgenden Code unter der `Train`-Methode hinzu, um die Methode zu erstellen:

```csharp
private static void Evaluate(PredictionModel<TaxiTrip, TaxiTripFarePrediction> model)
{

}
```

Fügen Sie den folgenden Code der `Evaluate`-Methode hinzu, um das Laden der Testdaten einzurichten:

[!code-csharp[LoadTestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Load the test data.")]

Fügen Sie den folgenden Code hinzu, um das Modell zu evaluieren und die Auswertungsmetriken zu erzeugen:

[!code-csharp[EvaluateAndMeasure](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Evaluate the model and its predictions.")]

[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) ist eine der Auswertungsmetriken aus dem Regressionsmodell. Je niedriger sie ausfällt, desto besser ist das Modell. Fügen Sie der `Evaluate`-Methode den folgenden Code hinzu, um den RMS-Wert anzuzeigen:

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Display the RMS metric.")]

[RSquared](../resources/glossary.md#coefficient-of-determination) ist eine weitere Auswertungsmetrik der Regressionsmodelle. RSquared akzeptiert Werte zwischen 0 (null) und 1. Je näher der Wert an 1 liegt, desto besser ist das Modell. Fügen Sie der `Evaluate`-Methode den folgenden Code hinzu, um den RSquared-Wert anzuzeigen:

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Display the RSquared metric.")]

## <a name="use-the-model-for-predictions"></a>Verwenden des Modells für Vorhersagen

Erstellen Sie eine Klasse, um Testdateninstanzen unterzubringen:

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.
1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *TestTrips.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.
1. Ändern Sie die Klasse wie im folgenden Beispiel in „statisch“:

   [!code-csharp[StaticClass](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#1 "Change class to be a static class.")]

Dieses Tutorial verwendet eine Testfahrt innerhalb dieser Klasse. Sie können später weitere Szenarios zum Experimentieren mit dem Beispiel hinzufügen. Fügen Sie den folgenden Code der `TestTrips`-Klasse hinzu:

[!code-csharp[TestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#2 "Create aq trip to predict its cost.")]

Der tatsächliche Fahrpreis beträgt $ 29,5. Verwenden Sie 0 (null) als Platzhalter, da das Modell den Fahrpreis vorhersagt.

Wechseln Sie zurück zur Datei *Program.cs*, und fügen Sie der `Main`-Methode den folgenden Code hinzu, um den Fahrpreis für die angegebene Fahrt vorherzusagen:

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Try a prediction.")]

Führen Sie das Programm aus, um den vorhergesagten Taxifahrtpreis für den Testfall anzuzeigen.

Herzlichen Glückwunsch! Hiermit haben Sie ein Machine Learning-Modell erfolgreich zum Vorhersagen von Taxifahrtpreisen erstellt, die Genauigkeit ausgewertet und es zum Vorhersagen der Preise verwendet. Sie finden den Quellcode für dieses Tutorial im GitHub-Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction).

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> * Das Problem verstehen
> * Auswählen der entsprechenden Machine Learning-Aufgabe
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
