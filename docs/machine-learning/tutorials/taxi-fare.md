---
title: Verwenden von ML.NET, um Taxifahrtpreise in New York vorherzusagen (Regression)
description: Erfahren Sie, wie Sie ML.NET in einem Regressionsszenario verwenden.
author: aditidugar
ms.author: johalex
ms.date: 06/05/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 048ed1d38408c1ba4901c554cae33d5552c9e303
ms.sourcegitcommit: 5b0802832fb9ad684d34e69b8644a16a5b7c4810
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2018
ms.locfileid: "34860672"
---
# <a name="tutorial-use-mlnet-to-predict-new-york-taxi-fares-regression"></a>Tutorial: Verwenden von ML.NET, um Taxifahrtpreise in New York vorherzusagen (Regression)

> [!NOTE]
> Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden. Weitere Informationen finden Sie in [der ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

In diesem Tutorial wird veranschaulicht, wie ML.NET zum Erstellen eines [Regressionsmodells](../resources/glossary.md#regression) für die Vorhersage von Taxifahrtpreisen in New York City verwendet wird.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> * Das Problem verstehen
> * Auswählen der entsprechenden Machine Learning-Aufgabe
> * Vorbereiten und Verstehen Ihrer Daten
> * Erstellen einer Lernpipeline
> * Laden und Transformieren Ihrer Daten
> * Auswählen eines Lernalgorithmus
> * Trainieren des Modells
> * Evaluieren des Modells
> * Verwenden des Modells für Vorhersagen

## <a name="prerequisites"></a>Erforderliche Komponenten

* [Visual Studio 2017 15.6 oder höher](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) mit installierter Workload für die „plattformübergreifende .NET Core-Entwicklung“.

## <a name="understand-the-problem"></a>Das Problem verstehen

Im Zentrum des Problems steht die **Vorhersage des Fahrtpreises einer Taxifahrt in New York City**. Dies mag auf den ersten Blick einfach von der zurückgelegten Stecke abhängen. Taxiunternehmer in New York berechnen jedoch abhängig von anderen Faktoren wie zusätzlichen Fahrgästen oder Kreditkartenzahlung anstelle von Barzahlung unterschiedliche Beträge.

## <a name="select-the-appropriate-machine-learning-task"></a>Auswählen der entsprechenden Machine Learning-Aufgabe

Um den Taxifahrtpreis vorhersagen zu können, wählen Sie zunächst die entsprechende Machine Learning-Aufgabe aus. Sie möchten einen realen Wert (einen Double-Datentypwert, der den Preis darstellt) auf Basis der anderen Faktoren im Dataset vorhersagen. Wählen Sie eine [**Regression**](../resources/glossary.md#regression)saufgabe aus.

Der Prozess zum Trainieren des Modells identifiziert, welche Faktoren im Dataset bei der endgültigen Fahrtpreisvorhersage am einflussreichsten sind.

## <a name="create-a-console-application"></a>Erstellen einer Konsolenanwendung

1. Öffnen Sie Visual Studio 2017. Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus. Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **.NET Core** aus. Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)**. Geben Sie „TaxiFarePrediction“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.

2. Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um die Datasetdateien zu speichern:

    Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus. Geben Sie „Data“ ein, und drücken Sie die EINGABETASTE.

3. Installieren des **Microsoft.ML NuGet-Pakets**:

    Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte „Durchsuchen“ aus, suchen Sie nach **Microsoft.ML**, und wählen Sie das Paket in der Liste sowie anschließend die Schaltfläche **Installieren** aus. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.

### <a name="prepare-and-understand-your-data"></a>Vorbereiten und Verstehen Ihrer Daten

1. Laden Sie die Datasets [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) und [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) herunter, und speichern Sie sie im zuvor erstellten Ordner *Data*. Das Taxi Trip-Dataset trainiert das Machine Learning-Modell und kann verwendet werden, um zu evaluieren, wie genau das Modell ist. Diese Datasets stammen ursprünglich aus dem [Dataset „NYC TLC Taxi Trip“](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).

2. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die \*.csv-Dateien, und wählen Sie **Eigenschaften** aus. Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Immer**.

3. Öffnen Sie das Dataset **taxi-fare-train.csv** im Code-Editor, und sehen Sie sich die Spaltenüberschriften in der ersten Zeile an. Sehen Sie sich jede der Spalten an. Machen Sie sich mit den Daten vertraut, und entscheiden Sie, welche Spalten **Features** sind, und was die **Bezeichnung** ist.

Die **Bezeichnung** ist der Bezeichner der Spalte, die Sie vorhersagen möchten. Die angegebenen **Features** werden verwendet, um die Bezeichnung vorherzusagen.

* **vendor_id:** Die ID des Taxiunternehmers ist ein Feature.
* **rate_code:** Der Tariftyp der Taxifahrt ist ein Feature.
* **passenger_count:** Die Anzahl der Fahrgäste bei einer Fahrt ist ein Feature.
* **trip_time_in_secs:** Die Dauer der Fahrt. Die Dauer der Fahrt ist erst nach ihrem Ende bekannt. Sie können diese Spalte aus dem Modell ausschließen.
* **trip_distance:** Die Fahrtstrecke ist ein Feature.
* **payment_type:** Die Zahlungsmethode (Bargeld oder Kreditkarte) ist ein Feature.
* **fare_amount:** Der gesamte gezahlte Taxifahrtpreis ist die Bezeichnung.

### <a name="create-classes-and-define-paths"></a>Erstellen von Klassen und Definieren von Pfaden

Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

Sie müssen drei globale Variablen erstellen, die die Pfade zu den zuletzt heruntergeladenen Dateien enthalten und das Modell speichern:

* `_datapath` enthält den Pfad zu dem Dataset, das zum Trainieren des Modells verwendet wird.
* `_testdatapath` enthält den Pfad zu dem Dataset, das zum Evaluieren des Modells verwendet wird.
* `_modelpath` enthält den Pfad zu dem Speicherort, in dem das trainierte Modell gespeichert ist.

Fügen Sie den folgenden Code der Zeile direkt oberhalb von `Main` hinzu, um die zuletzt heruntergeladenen Dateien anzugeben:

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

Erstellen Sie als Nächstes Klassen für die Eingabedaten und die Vorhersagen:

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.
1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *TaxiTrip.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.
1. Fügen Sie folgenden `using`-Anweisungen der neuen Datei hinzu:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code mit den beiden Klassen `TaxiTrip` und `TaxiTripFarePrediction` der Datei *TaxiTrip.cs* hinzu:

[!code-csharp[DefineTaxiTrip](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

`TaxiTrip` ist die Eingabedatasetklasse und verfügt über Definitionen für jede der Datasetspalten. Die `TaxiTripFarePrediction`-Klasse wird für die Vorhersage verwendet, nachdem das Modell trainiert wurde. Sie verfügt über einen einzelnen Gleitkommawert (`FareAmount`) und das [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute)-Attribut `Score`.

Wechseln Sie nun zurück zur **Program.cs**-Datei. Ersetzen Sie in `Main` `Console.WriteLine("Hello World!")` durch folgenden Code:

```csharp
PredictionModel<TaxiTrip, TaxiTripFarePrediction> model = Train();
```

Die `Train`-Methode trainiert das Modell. Erstellen Sie die Funktion direkt unter `Main` mit folgendem Code:

```csharp
public static PredictionModel<TaxiTrip, TaxiTripFarePrediction> Train()
{

}
```

## <a name="create-a-learning-pipeline"></a>Erstellen einer Lernpipeline

Die Lernpipeline lädt alle Daten und Algorithmen, die zum Trainieren des Modells erforderlich sind. Fügen Sie der `Train()`-Methode den folgenden Code hinzu:

```csharp
var pipeline = new LearningPipeline();
```

## <a name="load-and-transform-your-data"></a>Laden und Transformieren Ihrer Daten

Als Nächstes laden Sie die Daten in die Pipeline. Zeigen Sie auf die anfänglich erstellte Variable `_datapath`, und geben Sie das Trennzeichen der CSV-Datei („,“) an. Fügen Sie den folgenden Code in die `Train()`-Methode unterhalb des letzten Schritts ein:

```csharp
pipeline.Add(new TextLoader(_datapath).CreateFrom<TaxiTrip>(separator:','));
```

Sie müssen in dem Code, den Sie erstellen, ohne Unterstriche auf die Spalten verweisen. Kopieren Sie die `FareAmount`-Spalte mit der `ColumnCopier()`-Funktion in eine neue Spalte namens „Label“. Diese Spalte ist die **Bezeichnung**.

```csharp
pipeline.Add(new ColumnCopier(("FareAmount", "Label")));
```

Transformieren Sie die Daten mittels **Feature Engineering**, sodass sie effektiv für das Machine Learning verwendet werden können. Da der Algorithmus, der das Modell trainiert, **numerische** Features erfordert, transformieren Sie die kategorischen Daten (`VendorId`, `RateCode` und `PaymentType`) in Zahlen. Die `CategoricalOneHotVectorizer()`-Funktion weist den Werten in diesen Spalten einen numerischen Schlüssel zu. Transformieren Sie die Daten, indem Sie diesen Code hinzufügen:

```csharp
pipeline.Add(new CategoricalOneHotVectorizer("VendorId",
                                             "RateCode",
                                             "PaymentType"));
```

Im letzten Schritt der Datenvorbereitung werden alle Ihre **Features** mit der `ColumnConcatenator()`-Funktion in einem Vektor kombiniert. Dank dieses erforderlichen Schritts kann der Algorithmus Ihre Features problemlos verarbeiten. Fügen Sie den folgenden Code hinzu:

```csharp
pipeline.Add(new ColumnConcatenator("Features",
                                    "VendorId",
                                    "RateCode",
                                    "PassengerCount",
                                    "TripDistance",
                                    "PaymentType"));
```

Beachten Sie, dass die `trip_time_in_secs`-Spalte nicht enthalten ist. Sie haben bereits bestimmt, dass sie kein nützliches Feature für die Vorhersage ist.

> [!NOTE]
> Diese Schritte müssen der Pipeline zur erfolgreichen Ausführung in der oben angegebenen Reihenfolge hinzugefügt werden.

## <a name="choose-a-learning-algorithm"></a>Auswählen eines Lernalgorithmus

Nach dem Hinzufügen von Daten zur Pipeline und dem Transformieren in das richtige Eingabeformat wählen Sie einen Lernalgorithmus (**Lernmodul**) aus. Der Lernalgorithmus trainiert das Modell. Da Sie eine **Regressionsaufgabe** für dieses Problem ausgewählt haben, fügen Sie der Pipeline ein Lernmodul namens `FastTreeRegressor()` hinzu, das **Gradient Boosting** einsetzt.

Gradient Boosting ist eine Machine Learning-Technik für Regressionsprobleme. Sie erstellt jede Regressionsstruktur schrittweise. Sie verwendet eine vordefinierte Verlustfunktion, um den Fehler in jedem Schritt zu messen und im nächsten zu beheben. Das Ergebnis ist ein Vorhersagemodell, das sich im Grunde aus schwächeren Vorhersagemodellen zusammensetzt. Weitere Informationen zu Gradient Boosting finden Sie unter [Boosted-Entscheidungsstrukturregression](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression).

Fügen Sie den folgenden Code nach dem im letzten Schritt hinzugefügten Datenverarbeitungscode in die `Train()`-Methode ein:

```csharp
pipeline.Add(new FastTreeRegressor());
```

Sie haben alle vorherigen Schritte als einzelne Anweisungen der Pipeline hinzugefügt, aber C# verfügt über eine praktische Initialisierungssyntaxsammlung, die das Erstellen und Initialisieren der Pipeline vereinfacht. Ersetzen Sie den Code, den Sie bislang der `Train()`-Methode hinzugefügt haben, durch den folgenden Code:

[!code-csharp[CreatePipeline](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create and initialize the learning pipeline")]

## <a name="train-the-model"></a>Trainieren des Modells

Der letzte Schritt ist das Trainieren des Modells. Bis zu diesem Punkt wurde nichts in der Pipeline ausgeführt. Die `pipeline.Train<T_Input, T_Output>()`-Funktion nimmt den vordefinierten `TaxiTrip`-Klassentyp entgegen und gibt einen `TaxiTripFarePrediction`-Typ aus. Fügen Sie diesen letzten Codeabschnitt der `Train()`-Funktion hinzu:

[!code-csharp[TrainMOdel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#4 "Train your model")]

Und das ist schon alles! Sie haben erfolgreich ein Machine Learning-Modell trainiert, das Taxifahrtpreise in NYC vorhersagen kann. Untersuchen Sie nun, wie genau Ihr Modell funktioniert, und wie Sie es verwenden können.

## <a name="save-the-model"></a>Speichern des Modells

Bevor Sie mit dem nächsten Schritt fortfahren, speichern Sie Ihr Modell in einer ZIP-Datei, indem Sie den folgenden Code am Ende Ihrer `Train()`-Funktion hinzufügen:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Save the model asynchronously and return the model")]

Wenn die `await`-Anweisung dem `model.WriteAsync()`-Aufruf hinzugefügt wird, bedeutet dies, dass die `Train()`-Methode in eine asynchrone Methode geändert werden muss, die eine `Task` zurückgibt. Ändern Sie die Signatur von `Train` wie im folgenden Code gezeigt:

[!code-csharp[AsyncTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "Make the Train method async and return a task.")]

Eine Änderung des Rückgabetyps der `Train`-Methode bedeutet, dass Sie wie im folgenden Code dargestellt ein `await` dem Code hinzufügen müssen, der `Train` in der `Main`-Methode aufruft:

[!code-csharp[AwaitTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Await the Train method")]

Das Hinzufügen eines `await` zu Ihrer `Main`-Methode bedeutet, dass die `Main`-Methode den `async`-Modifizierer benötigt und eine `Task` zurückgeben muss:

[!code-csharp[AsyncMain](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Make the Main method async and return a task.")]

Sie müssen auch am Anfang der Datei die folgende Using-Anweisung hinzufügen:

[!code-csharp[UsingTasks](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Add System.Threading.Tasks. to your usings.")]

Da die `async Main`-Methode ein neues Feature in C# 7.1 und die Standardsprachversion des Projekts C# 7.0 ist, müssen Sie die Sprachversion auf C# 7.1 oder höher ändern.
Klicken Sie hierzu im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektknoten, und wählen Sie **Eigenschaften** aus. Wählen Sie die Registerkarte **Build** aus, und klicken Sie auf **Erweitert**. Wählen Sie in der Dropdownliste **C# 7.1** (oder eine höhere Version) aus. Klicken Sie auf die Schaltfläche **OK**.

## <a name="evaluate-the-model"></a>Evaluieren des Modells

Mit der Auswertung wird überprüft, wie gut das Modell funktioniert. Es ist wichtig, dass Ihr Modell gute Vorhersagen mithilfe von Daten trifft, die es nicht verwendet hat, als es trainiert wurde. Eine Möglichkeit hierfür ist das Aufteilen der Daten in Trainings- und Testdatasets, was Sie in diesem Tutorial praktiziert haben. Da Sie nun das Modell anhand der Trainingsdaten trainiert haben, können Sie prüfen, wie gut es mit den Testdaten arbeitet.

Wechseln Sie zurück zu Ihrer `Main`-Funktion, und fügen Sie den folgenden Code unterhalb des Aufrufs der `Train()`-Methode ein:

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Evaluate the model.")]

Die `Evaluate()`-Funktion evaluiert das Modell. Erstellen Sie diese Funktion unter `Train()`. Fügen Sie den folgenden Code hinzu:

```csharp
private static void Evaluate(PredictionModel<TaxiTrip, TaxiTripFarePrediction> model)
{

}
```

Laden Sie die Testdaten mit der `TextLoader()`-Funktion. Fügen Sie den folgenden Code der `Evaluate()`-Methode hinzu:

[!code-csharp[LoadTestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Load the test data.")]

Fügen Sie den folgenden Code hinzu, um das Modell zu evaluieren und die Metriken dafür zu erzeugen:

[!code-csharp[EvaluateAndMeasure](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Evaluate the model and its predictions.")]

RMS ist eine Metrik zur Auswertung von Regressionsproblemen. Je niedriger sie ausfällt, desto besser das Modell. Fügen Sie den folgenden Code der `Evaluate()`-Funktion hinzu, um den RMS-Wert für Ihr Modell zu drucken.

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Display the RMS metric.")]

RSquared ist eine weitere Metrik zur Auswertung von Regressionsproblemen. RSquared wird einen Wert zwischen 0 und 1 besitzen. Je näher Sie an 1 sind, umso besser das Modell. Fügen Sie den folgenden Code der `Evaluate()`-Funktion hinzu, um den RSquared-Wert für Ihr Modell zu drucken.

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Display the RSquared metric.")]

## <a name="use-the-model-for-predictions"></a>Verwenden des Modells für Vorhersagen

Als Nächstes erstellen Sie eine Klasse, um Testszenarien unterzubringen, die Sie verwenden können, um sicherzustellen, dass Ihr Modell ordnungsgemäß arbeitet:

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.
1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *TestTrips.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.
1. Ändern Sie die Klasse wie im folgenden Beispiel in „statisch“:

[!code-csharp[StaticClass](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#1 "Change class to be a static class.")]

Dieses Tutorial verwendet eine Testfahrt innerhalb dieser Klasse. Sie können später weitere Szenarien zum Experimentieren mit diesem Beispiel hinzufügen. Fügen Sie den folgenden Code der `TestTrips`-Klasse hinzu:

[!code-csharp[TestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#2 "Create aq trip to predict its cost.")]

Der tatsächliche Preis dieser Fahrt beträgt 29,5, aber verwenden Sie 0 als Platzhalter. Der Machine Learning-Algorithmus wird den Fahrpreis vorhersagen.

Fügen Sie den folgenden Code Ihrer `Main`-Funktion hinzu. Sie testet unser Modell mithilfe der `TestTrip`-Daten:

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Try a prediction.")]

Führen Sie das Programm aus, um den vorhergesagten Taxifahrtpreis für den Testfall anzuzeigen.

Herzlichen Glückwunsch! Sie haben jetzt erfolgreich ein Machine Learning-Modell für die Vorhersage von Taxifahrtpreisen erstellt, seine Genauigkeit ausgewertet und es getestet. Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction).

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> * Das Problem verstehen
> * Auswählen der entsprechenden Machine Learning-Aufgabe
> * Vorbereiten und Verstehen Ihrer Daten
> * Erstellen einer Lernpipeline
> * Laden und Transformieren Ihrer Daten
> * Auswählen eines Lernalgorithmus
> * Trainieren des Modells
> * Evaluieren des Modells
> * Verwenden des Modells für Vorhersagen

In unserem GitHub-Repository können Sie mit dem Lernen fortfahren und weitere Beispiele finden.
> [!div class="nextstepaction"]
> [dotnet/machinelearning GitHub repository](https://github.com/dotnet/machinelearning/)
