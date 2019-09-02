---
title: Vorhersagen von Preisen per Regression mit dem Modell-Generator
description: In diesem Tutorial wird veranschaulicht, wie mit dem ML.NET-Modell-Generator ein Regressionsmodell für die Vorhersage von Preisen für Taxifahrten in New York City erstellt wird.
author: luisquintanilla
ms.author: luquinta
ms.date: 07/15/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 1bdbe31e16408da2d7dfe17941c90a022f3d8c32
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "70107143"
---
# <a name="predict-prices-using-regression-with-model-builder"></a>Vorhersagen von Preisen per Regression mit dem Modell-Generator

Hier erfahren Sie, wie Sie mit dem ML.NET-Modellgenerator ein Regressionsmodells für Preisvorhersagen erstellen.  Die .NET Konsolenanwendung, die Sie in diesem Tutorial entwickeln, sagt Taxipreise basierend auf historischen Taxipreisdaten aus New York vorher.

Die Preisvorhersagevorlage des Modell-Generators kann für jedes Szenario verwendet werden, das einen numerischen Vorhersagewert erfordert. Beispielszenarien sind: Vorhersagen des Hauspreises oder der Nachfrage und Umsatzprognosen.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> - Vorbereiten und Verstehen der Daten
> - Auswählen eines Szenarios
> - Laden der Daten
> - Trainieren des Modells
> - Evaluieren des Modells
> - Verwenden des Modells für Vorhersagen

> [!NOTE]
> Der Modell-Generator befindet sich derzeit in der Vorschauphase.

## <a name="pre-requisites"></a>Voraussetzungen

Eine Liste der Voraussetzungen und Installationsanweisungen finden Sie in der [Installationsanleitung für den Modell-Generator](../how-to-guides/install-model-builder.md).

## <a name="create-a-console-application"></a>Erstellen einer Konsolenanwendung

1. Erstellen Sie eine **.NET Core-Konsolenanwendung** mit dem Namen „TaxiFarePrediction“.

## <a name="prepare-and-understand-the-data"></a>Vorbereiten und Verstehen der Daten

1. Erstellen Sie ein Verzeichnis mit dem Namen *Daten* in Ihrem Projekt, um die Datasetdateien zu speichern.

1. Das Dataset zum Trainieren und Bewerten des Machine Learning-Modells stammt ursprünglich aus dem Dataset „NYC TLC Taxi Trip“.

    Navigieren Sie zum Herunterladen des Datasets zum [Downloadlink für „taxi-fare-train.csv“](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv).

    Klicken Sie mit der rechten Maustaste auf die geladene Seite, und wählen Sie **Speichern unter** aus.

    Speichern Sie die Datei über das Dialogfeld **Speichern unter** im Ordner *Daten*, den Sie im vorherigen Schritt erstellt haben.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei *taxi-fare-train.csv*, und wählen Sie **Eigenschaften** aus. Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.

Jede Zeile im Dataset `taxi-fare-train.csv` enthält Details zu den Fahrten eines Taxis.

1. Öffnen Sie das Dataset **taxi-fare-train.csv**.

    Das angegebene Dataset enthält die folgenden Spalten:

    - **vendor_id:** Die ID des Taxiunternehmers ist ein Feature.
    - **rate_code:** Der Tariftyp der Taxifahrt ist ein Feature.
    - **passenger_count:** Die Anzahl der Fahrgäste bei einer Fahrt ist ein Feature.
    - **trip_time_in_secs:** Die Dauer der Fahrt.
    - **trip_distance:** Die Fahrtstrecke ist ein Feature.
    - **payment_type:** Die Zahlungsmethode (Bargeld oder Kreditkarte) ist ein Feature.
    - **fare_amount:** Der gesamte gezahlte Taxifahrtpreis ist die Bezeichnung.

`label` ist die Spalte, die vorhergesagt werden soll. Das Ziel bei der Durchführung einer Regressionsaufgabe ist die Vorhersage eines numerischen Werts. In diesem Preisvorhersageszenario werden die Kosten für eine Taxifahrt vorhergesagt. Daher lautet die Bezeichnung **fare_amount**. Die identifizierten `features` sind die Eingaben, die Sie für das Modell zum Vorhersagen von `label` bereitstellen. In diesem Fall werden die restlichen Spalten als Features oder Eingaben verwendet, um den Fahrpreis vorherzusagen.

## <a name="choose-a-scenario"></a>Auswählen eines Szenarios

Um Ihr Modell zu trainieren, wählen Sie ein Szenario aus der Liste der vom Modell-Generator bereitgestellten verfügbaren Machine Learning-Szenarien aus. In diesem Fall handelt es sich um das Szenario `Price Prediction`.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt *TaxiFarePrediction*, und wählen Sie **Hinzufügen** > **Machine Learning** aus.
1. Wählen Sie im Schritt „Szenario“ des Modell-Generator-Tools das Szenario *Price Prediction* aus.

## <a name="load-the-data"></a>Laden der Daten

Der Modellgenerator akzeptiert Daten aus zwei Quellen: aus einer SQL Server-Datenbank oder aus einer lokalen Datei im CSV- oder TSV-Format.

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

Das Ergebnis des Schritts „Trainieren“ ist ein Modell mit der besten Leistung. Der Schritt „Evaluieren“ des Modell-Generator-Tools, der Ausgabebereich, enthält den Algorithmus, der vom leistungsfähigsten Modell im Eintrag *Bestes Modell* verwendet wird, sowie Metriken in *Beste Modellqualität (RSquared)* . Außerdem finden Sie hier eine Übersichtstabelle mit den fünf besten Modellen und deren Metriken.

Wenn Sie mit Ihren Genauigkeitsmetriken nicht zufrieden sind, gibt es einige einfache Möglichkeiten, die Modellgenauigkeit zu verbessern. Dazu müssen Sie die Zeit für das Training des Modells erhöhen oder mehr Daten verwenden. Navigieren Sie andernfalls zum Codeschritt.

## <a name="add-the-code-to-make-predictions"></a>Hinzufügen des Codes für Vorhersagen

Das Ergebnis des Trainings sind zwei Projekte.

- TaxiFarePredictionML.ConsoleApp: Eine .NET Core-Konsolenanwendung, die den Modelltrainings- und Verbrauchscode enthält.
- TaxiFarePredictionML.Model: Eine .NET-Standardklassenbibliothek, die die Datenmodelle enthält, die das Schema der Eingabe- und Ausgabemodelldaten sowie die persistente Version des leistungsfähigsten Modells während des Trainings definieren.

1. Wählen Sie im Codeschritt des Modellgenerators die Option **Projekte hinzufügen** aus, um der Projektmappe die automatisch generierten Projekte hinzuzufügen.
1. Klicken Sie mit der rechten Maustaste auf das Projekt *TaxiFarePrediction*. Klicken Sie dann auf **Hinzufügen > Verweis**. Wählen Sie den Knoten **Projekte > Projektmappe** aus der Liste, aktivieren Sie das Kontrollkästchen für das Projekt *TaxiFarePredictionML.Model*, und wählen Sie „OK“ aus.
1. Öffnen Sie die Datei *Program.cs* im Projekt *TaxiFarePrediction*.
1. Fügen Sie die folgenden using-Anweisungen hinzu, um auf das NuGet-Paket *Microsoft.ML* und auf das Projekt *TaxiFarePredictionML.Model* zu verweisen:

    ```csharp
    using System;
    using Microsoft.ML;
    using TaxiFarePredictionML.Model.DataModels;
    ```

1. Fügen Sie der Klasse `Program` zur Klasse `ConsumeModel` hinzu.

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

    `ConsumeModel` lädt das trainierte Modell, erstellt eine Vorhersageengine ([`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)) für das Modell und verwendet sie, um Vorhersagen für neue Daten zu generieren.

1. Erstellen Sie eine neue Instanz der Klasse `ModelInput`, und verwenden Sie die Methode `ConsumeModel`, um unter Verwendung des Modells eine Vorhersage für neue Daten zu generieren. Beachten Sie, dass der Fahrpreis nicht Teil der Eingabe ist. Das liegt daran, dass das Modell die Vorhersage dafür generiert. Fügen Sie der Methode `Main` den folgenden Code hinzu, und führen Sie die Anwendung aus:

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
> - Vorbereiten und Verstehen der Daten
> - Auswählen eines Szenarios
> - Laden der Daten
> - Trainieren des Modells
> - Evaluieren des Modells
> - Verwenden des Modells für Vorhersagen

### <a name="additional-resources"></a>Zusätzliche Ressourcen

Weitere Informationen zu den in diesem Tutorial erwähnten Themen finden Sie in den folgenden Ressourcen:

- [Szenarien für den Modellgenerator](../automate-training-with-model-builder.md#scenarios)
- [Regression](../resources/glossary.md#regression)
- [Metriken für Regression](../resources/metrics.md#metrics-for-regression)
- [Dataset „NYC TLC Taxi Trip“](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml)
