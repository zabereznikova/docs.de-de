---
title: Vorhersagen von Preisen per Regression mit dem Modell-Generator
description: In diesem Tutorial wird veranschaulicht, wie mit dem ML.NET-Modell-Generator ein Regressionsmodell für die Vorhersage von Preisen für Taxifahrten in New York City erstellt wird.
author: luisquintanilla
ms.author: luquinta
ms.date: 06/26/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: d9a6f193d877fc1a679b7a3cafd7491e021cb2ad
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539622"
---
# <a name="predict-prices-using-regression-with-model-builder"></a>Vorhersagen von Preisen per Regression mit dem Modell-Generator

Erfahren Sie, wie Sie mit dem ML.NET-Modell-Generator ein [Regressionsmodells](../resources/glossary.md#regression) für Preisvorhersagen erstellen können.  Die .NET Konsolenanwendung, die Sie in diesem Tutorial entwickeln, sagt Taxipreise basierend auf historischen Taxipreisdaten aus New York vorher.

Die Preisvorhersagevorlage des Modell-Generators kann für jedes Szenario verwendet werden, das einen numerischen Vorhersagewert erfordert. Beispielszenarien sind: Vorhersagen des Hauspreises oder der Nachfrage und Umsatzprognosen.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> * Vorbereiten und Verstehen der Daten
> * Auswählen eines Szenarios
> * Laden der Daten
> * Trainieren des Modells
> * Evaluieren des Modells
> * Verwenden des Modells für Vorhersagen

> [!NOTE]
> Der Modell-Generator befindet sich derzeit in der Vorschauphase.

## <a name="pre-requisites"></a>Voraussetzungen

Eine Liste der Voraussetzungen und Installationsanweisungen finden Sie in der [Installationsanleitung für den Modell-Generator](../how-to-guides/install-model-builder.md).

## <a name="create-a-console-application"></a>Erstellen einer Konsolenanwendung

1. Erstellen Sie eine **.NET Core-Konsolenanwendung** mit dem Namen „TaxiFarePrediction“.

1. Installieren Sie das NuGet-Paket **Microsoft.ML**:

    Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf *TaxiFarePrediction*, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach **Microsoft.ML**, und wählen Sie das Paket in der Liste und anschließend die Schaltfläche **Installieren** aus. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.

## <a name="prepare-and-understand-the-data"></a>Vorbereiten und Verstehen der Daten

1. Erstellen Sie ein Verzeichnis mit dem Namen *Daten* in Ihrem Projekt, um die Datasetdateien zu speichern.

1. Laden Sie das Dataset [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) herunter und speichern Sie es im Ordner *Daten*, den Sie im vorherigen Schritt erstellt haben. Dieses Dataset wird zum Trainieren und Evaluieren des Machine Learning-Modells verwendet. Dieses Dataset stammt ursprünglich aus dem [Dataset „NYC TLC Taxi Trip“](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei *taxi-fare-train.csv*, und wählen Sie **Eigenschaften** aus. Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.

Jede Zeile im Dataset `taxi-fare-train.csv` enthält Details zu den Fahrten eines Taxis.

1. Öffnen Sie das Dataset **taxi-fare-train.csv**.

    Das angegebene Dataset enthält die folgenden Spalten:

    * **vendor_id:** Die ID des Taxiunternehmers ist ein Feature.
    * **rate_code:** Der Tariftyp der Taxifahrt ist ein Feature.
    * **passenger_count:** Die Anzahl der Fahrgäste bei einer Fahrt ist ein Feature.
    * **trip_time_in_secs:** Die Dauer der Fahrt. Der Fahrpreis soll vorhergesagt werden, bevor die Fahrt abgeschlossen ist. Zu diesem Zeitpunkt wissen Sie noch nicht, wie lange die Fahrt dauert. Deshalb ist die Fahrtzeit kein Feature, und Sie müssen diese Spalte aus dem Modell ausschließen.
    * **trip_distance:** Die Fahrtstrecke ist ein Feature.
    * **payment_type:** Die Zahlungsmethode (Bargeld oder Kreditkarte) ist ein Feature.
    * **fare_amount:** Der gesamte gezahlte Taxifahrtpreis ist die Bezeichnung.

`label` ist die Spalte, die vorhergesagt werden soll. Das Ziel bei der Durchführung einer Regressionsaufgabe ist die Vorhersage eines numerischen Werts. In diesem Preisvorhersageszenario werden die Kosten für eine Taxifahrt vorhergesagt. Daher lautet die Bezeichnung **fare_amount**. Die identifizierten `features` sind die Eingaben, die Sie für das Modell zum Vorhersagen von `label` bereitstellen. In diesem Fall werden die restlichen Spalten als Features oder Eingaben verwendet, um den Fahrpreis vorherzusagen.

## <a name="choose-a-scenario"></a>Auswählen eines Szenarios

Um Ihr Modell zu trainieren, wählen Sie ein Szenario aus der Liste der vom Modell-Generator bereitgestellten verfügbaren Machine Learning-Szenarien aus. In diesem Fall handelt es sich um das Szenario `Price Prediction`. Eine ausführlichere Liste finden Sie im [Übersichtsartikel zum Modell-Generator](../automate-training-with-model-builder.md#scenarios).

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt *TaxiFarePrediction*, und wählen Sie **Hinzufügen** > **Machine Learning** aus.
1. Wählen Sie im Schritt „Szenario“ des Modell-Generator-Tools das Szenario *Price Prediction* aus.

## <a name="load-the-data"></a>Laden der Daten

Der Modell-Generator akzeptiert Daten aus zwei Quellen: eine SQL Server-Datenbank oder eine lokalen csv- oder tsv-Datei. Weitere Informationen zu Anforderungen an das Datenformat finden Sie auf über den folgenden [Link](../how-to-guides/install-model-builder.md#limitations).

1. Wählen Sie im Schritt „Daten“ des Modell-Generator-Tools die Option *Datei* aus der Dropdownliste „Datenquelle“ aus.
1. Wählen Sie die Schaltfläche neben dem Textfeld *Datei auswählen*, und verwenden Sie den Datei-Explorer, um die Datei *taxi-fare-test.csv* im Verzeichnis *Daten* zu suchen und auszuwählen.
1. Wählen Sie *fare_amount* in der Dropdownliste *Bezeichnung oder Spalte für die Vorhersage* aus, und navigieren Sie zum Schritt „Trainieren“ des Modell-Generator-Tools.

## <a name="train-the-model"></a>Trainieren des Modells

Die in diesem Tutorial zum Trainieren des Preisvorhersagemodells verwendete Machine Learning-Aufgabe ist die Regression. Während des Modelltrainings trainiert der Modell-Generator einzelne Modelle mit verschiedenen Regressionsalgorithmen und Einstellungen, um das leistungsfähigste Modell für Ihr Dataset zu finden.

Die Zeit, die für das Trainieren des Modells benötigt wird, ist proportional zur Datenmenge. Verwenden Sie diese Tabelle als Orientierungshilfe, um einen geeigneten Wert für das Feld `Time to train (seconds)` auszuwählen:

*Datasetgröße  | Datasettyp       | Durchschn. Trainingszeit*
------------- | ------------------ | --------------
0 bis 10 MB     | Numerisch und Text   | 10 Sek.
10 bis 100 MB   | Numerisch und Text   | 10 Min.
100 bis 500 MB  | Numerisch und Text   | 30 Min.
500 MB bis 1 GB    | Numerisch und Text   | 60 Min.
1 GB+         | Numerisch und Text   | 3 Stunden +

1. Da die Trainingsdatendatei mehr als 10 MB umfasst, verwenden Sie 600 Sekunden (10 Minuten) als Wert für *Trainingszeit (Sekunden)* .
2. Wählen Sie *Training starten* aus.

Während des gesamten Trainingsprozesses werden die Fortschrittsdaten im Abschnitt `Progress` des Schritts „Trainieren“ angezeigt.

- „Status“ zeigt den Abschlussstatus des Trainingsprozesses an.
- „Beste Genauigkeit“ zeigt die Genauigkeit des leistungsfähigsten Modells, das bisher vom Modell-Generator gefunden wurde. Eine höhere Genauigkeit bedeutet, dass die Vorhersage des Modells anhand der Testdaten präziser ist.
- „Bester Algorithmus“ zeigt den Namen des leistungsfähigsten Algorithmus an, der bisher vom Modell-Generator gefunden wurde.
- „Letzter Algorithmus“ zeigt den Namen des Algorithmus an, der zuletzt vom Modell-Generator zum Trainieren des Modells verwendet wurde.

Navigieren Sie nach Abschluss des Trainings zum Schritt „Evaluieren“.

## <a name="evaluate-the-model"></a>Evaluieren des Modells

Das Ergebnis des Schritts „Trainieren“ ist ein Modell mit der besten Leistung. Der Schritt „Evaluieren“ des Modell-Generator-Tools, der Ausgabebereich, enthält den Algorithmus, der vom leistungsfähigsten Modell im Eintrag *Bestes Modell* verwendet wird, sowie Metriken in *Beste Modellqualität (RSquared)* . Außerdem finden Sie hier eine Übersichtstabelle mit den fünf besten Modellen und deren Metriken. Klicken Sie auf den folgenden Link, um mehr über das [Evaluieren von Modellmetriken](https://docs.microsoft.com/dotnet/machine-learning/resources/metrics) zu erfahren.

Wenn Sie mit Ihren Genauigkeitsmetriken nicht zufrieden sind, gibt es einige einfache Möglichkeiten, die Modellgenauigkeit zu verbessern. Dazu müssen Sie die Zeit für das Training des Modells erhöhen oder mehr Daten verwenden.

## <a name="use-the-model-for-predictions"></a>Verwenden des Modells für Vorhersagen

Das Ergebnis des Trainings sind zwei Projekte.

- TaxiFarePredictionML.ConsoleApp: Eine .NET-Konsolenanwendung, die den Modelltrainings- und Verbrauchscode enthält.
- TaxiFarePredictionML.Model: Eine .NET-Standardklassenbibliothek, die die Datenmodelle enthält, die das Schema der Eingabe- und Ausgabemodelldaten sowie die persistente Version des leistungsfähigsten Modells während des Trainings definieren.

1. Wählen Sie im Abschnitt „Code“ des Modell-Generator-Tools die Option **Hinzugefügte Projekte**, um die Projekte zur Projektmappe hinzuzufügen.
2. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt *TaxiFarePrediction*. Wählen Sie dann **Hinzufügen > Vorhandenes Element** aus. Wählen Sie dann in der Dropdownliste „Dateityp“ `All Files` aus, navigieren Sie zum Projektverzeichnis *TaxiFarePredictionML.Model*, und wählen Sie die Datei `MLModel.zip` aus. Klicken Sie dann mit der rechten Maustaste auf die zuletzt hinzugefügte Datei `MLModel.zip`, und wählen Sie *Eigenschaften* aus. Wählen Sie für die Option „In Ausgabeverzeichnis kopieren“ in der Dropdownliste *Kopieren, wenn neuer* aus.
3. Klicken Sie mit der rechten Maustaste auf das Projekt *TaxiFarePrediction*. Klicken Sie dann auf **Hinzufügen > Verweis**. Wählen Sie den Knoten **Projekte > Projektmappe** aus der Liste, aktivieren Sie das Kontrollkästchen für das Projekt *TaxiFarePredictionML.Model*, und wählen Sie „OK“ aus.

4. Öffnen Sie die Datei *Program.cs* im Projekt *TaxiFarePrediction*.
5. Fügen Sie die folgenden using-Anweisungen hinzu:

    ```csharp
    using System;
    using Microsoft.ML;
    using TaxiFarePredictionML.Model.DataModels;
    ```

6. Fügen Sie der Klasse `Program` zur Klasse `ConsumeModel` hinzu. Das `ConsumeModel` erstellt eine `PredictionEngine` basierend auf dem vom Modell-Generator generierten Modell, um Vorhersagen für neue Daten zu treffen und diese an die Konsole auszugeben.

    ```csharp
    static ModelOutput ConsumeModel(ModelInput input)
    {
        // 1. Load the model
        MLContext mlContext = new MLContext();
        ITransformer mlModel = mlContext.Model.Load("MLModel.zip", out var modelInputSchema);

        // 2. Create PredictionEngine
        var predictionEngine = mlContext.Model.CreatePredictionEngine<ModelInput, ModelOutput>(mlModel);

        // 3. Use PredictionEngine to use model on input data
        ModelOutput result = predictionEngine.Predict(input);

        // 4. Return prediction result
        return result;
    }
    ```

7. Fügen Sie den folgenden Code zur Methode `Main` hinzu, und führen Sie die Anwendung aus.

    ```csharp
    // Create sample data
    ModelInput input = new ModelInput()
    {
        Vendor_id = "CMT",
        Rate_code = 1,
        Passenger_count = 1,
        Trip_time_in_secs = 1271,
        Trip_distance = 3.8f,
        Payment_type = "CRD"
    };

    // Make prediction
    ModelOutput prediction = ConsumeModel(input);

    // Print Prediction
    Console.WriteLine($"Predicted Fare: {prediction.Score}");
    Console.ReadKey();
    ```

    Die vom Programm generierte Ausgabe sollte wie der folgende Ausschnitt aussehen:

    ```bash
    Predicted Fare: 16.82245
    ```

Wenn Sie zu einem späteren Zeitpunkt innerhalb einer anderen Projektmappe auf die generierten Projekte verweisen müssen, finden Sie diese im Verzeichnis `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> * Vorbereiten und Verstehen der Daten
> * Auswählen eines Szenarios
> * Laden der Daten
> * Trainieren des Modells
> * Evaluieren des Modells
> * Verwenden des Modells für Vorhersagen

Lesen Sie einen der folgenden Anleitungsartikel, um zu erfahren, wie Sie Ihr Modell bereitstellen können.

> [!div class="nextstepaction"]
> [Bereitstellen des Modells für Azure Functions](../how-to-guides/serve-model-serverless-azure-functions-ml-net.md)
> [!div class="nextstepaction"]
> [Bereitstellen eines Modells für eine Web-API](../how-to-guides/serve-model-web-api-ml-net.md)
