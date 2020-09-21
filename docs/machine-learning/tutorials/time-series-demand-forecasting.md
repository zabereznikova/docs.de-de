---
title: 'Tutorial: Vorhersage des Bedarfs für Fahrradvermietungen – Zeitreihe'
description: Dieses Tutorial zeigt Ihnen, wie Sie den Bedarf für einen Fahrradverleih mithilfe einer univariaten Zeitreihenanalyse und ML.NET prognostizieren können.
ms.date: 06/30/2020
ms.topic: tutorial
ms.custom: mvc
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: 51041f5a9076ad360a84cc39704aedb50b77d40a
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679389"
---
# <a name="tutorial-forecast-bike-rental-service-demand-with-time-series-analysis-and-mlnet"></a>Tutorial: Prognose des Bedarfs eines Fahrradverleihs mit Zeitreihenanalyse und ML.NET

Erfahren Sie, wie Sie den Bedarf für einen Fahrradverleih mithilfe einer univariaten Zeitreihenanalyse für in einer SQL Server-Datenbank gespeicherte Daten mit ML.NET prognostizieren können.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> * Das Problem verstehen
> * Laden von Daten aus einer Datenbank
> * Erstellen eines Vorhersagemodells
> * Auswerten eines Vorhersagemodells
> * Speichern eines Vorhersagemodells
> * Verwenden eines Vorhersagemodells

## <a name="prerequisites"></a>Voraussetzungen

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) oder höher oder Visual Studio 2017 Version 15.6 oder höher mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.

## <a name="time-series-forecasting-sample-overview"></a>Übersicht über das Beispiel zur Zeitreihenvorhersage

Bei diesem Beispiel handelt es sich um eine **C#.NET Core-Konsolenanwendung**, die den Bedarf für einen Fahrradverleih mithilfe eines univariaten Zeitreihenanalyse-Algorithmus prognostiziert, der unter dem Namen „singuläre Spektralanalyse“ bekannt ist. Den Code für dieses Beispiel finden Sie im Repository [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand) auf GitHub.

## <a name="understand-the-problem"></a>Das Problem verstehen

Um einen effizienten Betrieb zu gewährleisten, spielt die Inventarverwaltung eine wichtige Rolle. Zu viel von einem Produkt auf Lager zu haben, bedeutet, dass unverkaufte Produkte in den Regalen stehen und keine Umsätze generieren. Zu wenig Produktvorrat führt zu Umsatzeinbußen und Kunden, die von Wettbewerbern kaufen. Daher stellt sich immer wieder die folgende Frage: Wie hoch ist die optimale Menge an Lagerbestand, die vorgehalten werden sollte? Die Zeitreihenanalyse hilft, eine Antwort auf diese Fragen zu geben, indem sie historische Daten untersucht, Muster identifiziert und diese Informationen verwendet, um Werte irgendwann in der Zukunft vorherzusagen.

Das Verfahren zum Analysieren von Daten, das in diesem Tutorial verwendet wird, ist die univariate Zeitreihenanalyse. Die univariate Zeitreihenanalyse untersucht eine einzelne numerische Beobachtung über einen bestimmten Zeitraum in bestimmten Intervallen, z.B. die monatlichen Umsätze.

Der in diesem Tutorial verwendete Algorithmus ist [singuläre Spektralanalyse (Singular Spectrum Analysis, SSA)](http://ssa.cf.ac.uk/zhigljavsky/pdfs/SSA/SSA_encyclopedia.pdf). SSA zerlegt eine Zeitreihe in ihre Hauptkomponenten. Diese Komponenten können als Teile eines Signals interpretiert werden, das Trends, Rauschen, Saisonalität und vielen anderen Faktoren entspricht. Anschließend werden diese Komponenten rekonstruiert und verwendet, um Werte in der Zukunft vorherzusagen.

## <a name="create-console-application"></a>Erstellen einer Konsolenanwendung

1. Erstellen Sie eine neue **C# .NET Core-Konsolenanwendung** mit dem Namen „BikeDemandForecasting“.
1. Installieren des NuGet-Pakets **Microsoft.ML**

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.
    1. Wählen Sie „nuget.org“ als Paketquelle aus, wählen Sie die Registerkarte **Durchsuchen** aus, und suchen Sie nach **Microsoft.ML**.
    1. Aktivieren Sie das Kontrollkästchen **Vorabversion einbeziehen**.
    1. Wählen Sie die Schaltfläche **Installieren** aus.
    1. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld „Zustimmung zur Lizenz“ aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.
    1. Wiederholen Sie diese Schritte für **System.Data.SqlClient** und **Microsoft.ML.TimeSeries**.

### <a name="prepare-and-understand-the-data"></a>Vorbereiten und Verstehen der Daten

1. Erstellen Sie ein Verzeichnis namens *Data*.
1. Laden Sie die [Datenbankdatei *DailyDemand.mdf*](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Data/DailyDemand.mdf) herunter, und speichern Sie sie im Verzeichnis *Data*.

> [!NOTE]
> Die in diesem Tutorial verwendeten Daten stammen aus dem [UCI Bike Sharing-Dataset](http://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset). Fanaee-T, Hadi und Gama, Joao, „Event labeling combining ensemble detectors and background knowledge“, Progress in Artificial Intelligence (2013): S. 1-15, Springer Berlin Heidelberg, [Weblink](https://link.springer.com/article/10.1007%2Fs13748-013-0040-3).

Das ursprüngliche Dataset enthält mehrere Spalten, die der Saisonalität und dem Wetter entsprechen. Aus Gründen der Kürze und weil der in diesem Tutorial verwendete Algorithmus nur die Werte einer einzigen numerischen Spalte benötigt, wurde das ursprüngliche Dataset so zusammengefasst, dass es nur die folgenden Spalten enthält:

- **dteday**: Das Datum der Beobachtung.
- **year**: Das codierte Jahr der Beobachtung (0 = 2011, 1 = 2012).
- **cnt**: Die Gesamtzahl der Fahrradvermietungen für diesen Tag.

Das ursprüngliche Dataset wird einer Datenbanktabelle mit dem folgenden Schema in einer SQL Server Datenbank zugeordnet.

```sql
CREATE TABLE [Rentals] (
    [RentalDate] DATE NOT NULL,
    [Year] INT NOT NULL,
    [TotalRentals] INT NOT NULL
);
```

Im Folgenden finden Sie ein Beispiel für die Daten:

| RentalDate | Jahr | TotalRentals |
| --- | --- | --- |
|1/1/2011|0|985|
|1/2/2011|0|801|
|1/3/2011|0|1349|

### <a name="create-input-and-output-classes"></a>Erstellen von Eingabe- und Ausgabeklassen

1. Ersetzen Sie in *Program.cs* die vorhandenen `using`-Anweisungen durch Folgendes:

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L1-L8)]

1. Erstellen Sie die `ModelInput`-Klasse. Fügen Sie unter der `Program`-Klasse den folgenden Code hinzu.

    [!code-csharp [ModelInputClass](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L120-L127)]

    Die `ModelInput`-Klasse enthält die folgenden Spalten:

    - **RentalDate**: Das Datum der Beobachtung.
    - **Year**: Das codierte Jahr der Beobachtung (0 = 2011, 1 = 2012).
    - **TotalRentals**: Die Gesamtzahl der Fahrradvermietungen für diesen Tag.

1. Erstellen Sie die `ModelOutput`-Klasse unterhalb der neu erstellten `ModelInput`-Klasse.

    [!code-csharp [ModelOutputClass](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L129-L136)]

    Die `ModelOutput`-Klasse enthält die folgenden Spalten:

    - **ForecastedRentals**: Die vorhergesagten Werte für den Vorhersagezeitraum.
    - **LowerBoundRentals**: Die vorhergesagten Mindestwerte für den Vorhersagezeitraum.
    - **UpperBoundRentals**: Die vorhergesagten Maximalwerte für den Vorhersagezeitraum.

### <a name="define-paths-and-initialize-variables"></a>Definieren von Pfaden und Initialisieren von Variablen

1. Definieren Sie innerhalb der `Main`-Methode Variablen, um den Speicherort der Daten, die Verbindungszeichenfolge und den Speicherort für das trainierte Modell zu speichern.

    [!code-csharp [DefinePaths](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L16-L19)]

1. Initialisieren Sie die `mlContext`-Variable mit einer neuen Instanz von [`MLContext`](xref:Microsoft.ML.MLContext), indem Sie der `Main`-Methode die folgende Zeile hinzufügen.

    [!code-csharp [MLContext](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L21)]

    Die [`MLContext`](xref:Microsoft.ML.MLContext)-Klasse ist der Ausgangspunkt für alle ML.NET-Vorgänge. Durch das Initialisieren von mlContext wird eine neue ML.NET-Umgebung erstellt, die für mehrere Objekte des Modellerstellungsworkflows verwendet werden kann. Die Klasse ähnelt dem Konzept von `DBContext` in Entity Framework.

## <a name="load-the-data"></a>Laden der Daten

1. Erstellen Sie das `DatabaseLoader`-Element, mit dem Datensätze des Typs `ModelInput` geladen werden.

    [!code-csharp [CreateDBLoader](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L23)]

1. Definieren Sie die Abfrage, um die Daten aus der Datenbank zu laden.

    [!code-csharp [DefineSQLQuery](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L25)]

    ML.NET-Algorithmen erwarten, dass Daten vom Typ [`Single`](xref:System.Single) sind. Daher müssen numerische Werte aus der Datenbank, die nicht vom Typ [`Real`](xref:System.Data.SqlDbType) (ein Gleitkommawert mit einfacher Genauigkeit) sind, in [`Real`](xref:System.Data.SqlDbType) konvertiert werden.

    Die Spalten `Year` und `TotalRental` sind Integertypen in der Datenbank. Mithilfe der integrierten Funktion `CAST` werden beide Werte in `Real` umgewandelt.

1. Erstellen Sie eine `DatabaseSource`, um eine Verbindung mit der Datenbank herzustellen und die Abfrage auszuführen.

    [!code-csharp [CreateDBSource](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L27-L29)]

1. Laden Sie die Daten in eine `IDataView`.

    [!code-csharp [LoadData](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L31)]

1. Das Dataset enthält Daten aus zwei Jahren. Nur Daten aus dem ersten Jahr werden für das Training verwendet, das zweite Jahr wird zum Vergleichen der tatsächlichen Werte mit der vom Modell generierten Vorhersage verwendet. Filtern Sie die Daten mithilfe der [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn%2A)-Transformation.

    [!code-csharp [SplitData](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L33-L34)]

    Für das erste Jahr werden nur die Werte in der Spalte `Year`, die kleiner als 1 ist, durch Festlegen des `upperBound`-Parameters auf 1 ausgewählt. Umgekehrt werden für das zweite Jahr Werte größer oder gleich 1 ausgewählt, indem der `lowerBound`-Parameter auf 1 festgelegt wird.

## <a name="define-time-series-analysis-pipeline"></a>Definieren einer Zeitreihenanalyse-Pipeline

1. Definieren Sie eine Pipeline, die [SsaForecastingEstimator](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator) verwendet, um Werte in einem Zeitreihendataset vorherzusagen.

    [!code-csharp [DefinePipeline](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L36-L45)]

    Die `forecastingPipeline` nimmt für das erste Jahr 365 Datenpunkte an und teilt ein Zeitreihendataset in Stichproben von jeweils 30 Tagen (monatlich) auf, wie vom `seriesLength`-Parameter angegeben. Jede dieser Stichproben wird anhand eines wöchentlichen oder ein 7-tägigen Fensters analysiert. Bei der Ermittlung des prognostizierten Werts für die nächste(n) Zeitspanne(n) werden die Werte der letzten sieben Tage verwendet, um eine Prognose zu erstellen. Das Modell wird so festgelegt, dass sieben Zeitspannen in der Zukunft vorhergesagt werden, wie durch den `horizon`-Parameter definiert. Da eine Vorhersage eine fundierte Vermutung ist, ist sie nicht immer zu 100 % genau. Daher ist es gut, den Wertebereich in den besten und schlechtesten Szenarien zu kennen, wie durch die oberen und unteren Grenzen definiert. In diesem Fall wird der Vertrauensgrad für die untere und obere Grenze auf 95 % festgelegt. Der Vertrauensgrad kann entsprechend angehoben oder gesenkt werden. Je höher der Wert, desto größer ist der Bereich zwischen der oberen und unteren Grenze, um das gewünschte Maß an Vertrauen zu erreichen.

1. Verwenden Sie die [`Fit`](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator.Fit%2A)-Methode, um das Modell zu trainieren und die Daten an die zuvor definierte `forecastingPipeline` anzupassen.

    [!code-csharp [TrainModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L47)]

## <a name="evaluate-the-model"></a>Evaluieren des Modells

Bewerten Sie die Leistungsfähigkeit des Modells, indem Sie die Daten des nächsten Jahrs prognostizieren und mit den tatsächlichen Werten vergleichen.

1. Erstellen Sie unter der `Main`-Methode eine neue Hilfsmethode namens `Evaluate`.

    ```csharp
    static void Evaluate(IDataView testData, ITransformer model, MLContext mlContext)
    {

    }
    ```

1. Prognostizieren Sie in der `Evaluate`-Methode die Daten des zweiten Jahrs mithilfe der [`Transform`](xref:Microsoft.ML.ITransformer.Transform%2A)-Methode mit dem trainierten Modell.

    [!code-csharp [EvaluateForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L62)]

1. Verwenden Sie die [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A)-Methode, um die tatsächlichen Werte aus den Daten abzurufen.

    [!code-csharp [GetActualRentals](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L65-L67)]

1. Verwenden Sie die [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A)-Methode, um die Vorhersagewerte abzurufen.

    [!code-csharp [GetForecastRentals](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L70-L72)]

1. Berechnen Sie die Differenz zwischen den tatsächlichen Werten und den Vorhersagewerten, die im Allgemeinen als „Fehler“ bezeichnet wird.

    [!code-csharp [CalculateError](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L75)]

1. Messen Sie die Leistung, indem Sie die Werte Mean Absolute Error (Mittlerer absoluter Fehler) und Root Mean Squared Error (Mittlerer quadratischer Fehler) berechnen.

    [!code-csharp [CalculateMetrics](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L78-L79)]

    Die folgenden Metriken werden verwendet, um die Leistung auszuwerten:

    - **Mean Absolute Error** (Mittlerer absoluter Fehler): Misst, wie nahe Vorhersagen am tatsächlichen Wert liegen. Dieser Wert liegt zwischen 0 und unendlich. Je näher der Wert an 0 ist, desto besser ist die Qualität des Modells.
    - **Root Mean Squared Error** (Mittlerer quadratischer Fehler): Fasst den Fehler im Modell zusammen. Dieser Wert liegt zwischen 0 und unendlich. Je näher der Wert an 0 ist, desto besser ist die Qualität des Modells.

1. Geben Sie die Metriken an die Konsole aus.

    [!code-csharp [OutputMetrics](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L82-L85)]

1. Verwenden Sie die `Evaluate`-Methode in der `Main`-Methode.

    [!code-csharp [EvaluateModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L49)]

## <a name="save-the-model"></a>Speichern des Modells

Wenn Sie mit Ihrem Modell zufrieden sind, speichern Sie es zur späteren Verwendung in anderen Anwendungen.

1. Erstellen Sie in der `Main`-Methode eine [`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602). [`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602) ist eine bequeme Methode, um einzelne Vorhersagen zu treffen.

    [!code-csharp [CreateTimeSeriesEngine](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L51)]

1. Speichern Sie das Modell in einer Datei namens `MLModel.zip`, wie durch die zuvor definierten `modelPath`-Variable angegeben. Verwenden Sie die [`Checkpoint`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.CheckPoint%2A)-Methode, um das Modell zu speichern.

    [!code-csharp [SaveModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L52)]

## <a name="use-the-model-to-forecast-demand"></a>Verwenden des Modells zum Vorhersagen des Bedarfs

1. Erstellen Sie unter der `Evaluate`-Methode eine neue Hilfsmethode namens `Forecast`.

    ```csharp
    static void Forecast(IDataView testData, int horizon, TimeSeriesPredictionEngine<ModelInput, ModelOutput> forecaster, MLContext mlContext)
    {

    }
    ```

1. Verwenden Sie innerhalb der `Forecast`-Methode die [`Predict`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.Predict%2A)-Methode, um die Vermietungen der nächsten sieben Tage vorherzusagen.

    [!code-csharp [SingleForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L91)]

1. Bringen Sie die tatsächlichen und die vorhergesagten Werte für sieben Zeiträume in Einklang.

    [!code-csharp [GetForecastOutput](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L93-L108)]

1. Iterieren Sie durch die Vorhersageausgabe, und zeigen Sie diese in der Konsole an.

    [!code-csharp [DisplayForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L111-L116)]

## <a name="run-the-application"></a>Ausführen der Anwendung

1. Rufen Sie in der `Main`-Methode die `Forecast`-Methode auf.

    [!code-csharp [BuildForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L54)]

1. Führen Sie die Anwendung aus. Eine ähnliche Ausgabe wie die folgende sollte in der Konsole angezeigt werden. Aus Gründen der Kürze wurde die Ausgabe komprimiert.

    ```text
    Evaluation Metrics
    ---------------------
    Mean Absolute Error: 726.416
    Root Mean Squared Error: 987.658

    Rental Forecast
    ---------------------
    Date: 1/1/2012
    Actual Rentals: 2294
    Lower Estimate: 1197.842
    Forecast: 2334.443
    Upper Estimate: 3471.044

    Date: 1/2/2012
    Actual Rentals: 1951
    Lower Estimate: 1148.412
    Forecast: 2360.861
    Upper Estimate: 3573.309
    ```

Bei der Untersuchung der tatsächlichen und der vorhergesagten Werte werden die folgenden Beziehungen angezeigt:

![Vergleich der tatsächlichen und der vorhergesagten Werte](./media/time-series-demand-forecasting/forecast.png)

Obwohl die vorhergesagten Werte nicht die genaue Anzahl von Vermietungen vorhersagen, stellen sie einen engeren Bereich von Werten bereit, der es im Betrieb ermöglicht, die Verwendung von Ressourcen zu optimieren.

Herzlichen Glückwunsch! Sie haben nun erfolgreich ein Machine Learning-Zeitreihenmodell erstellt, um den Bedarf für die Fahrradvermietung zu prognostizieren.

Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand).

## <a name="next-steps"></a>Nächste Schritte

- [Machine Learning-Aufgaben in ML.NET](../resources/tasks.md)
- [Verbessern der Modellgenauigkeit](../resources/improve-machine-learning-model-ml-net.md)
