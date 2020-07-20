---
title: 'Tutorial: Erkennen von Anomalien bei Produktverkäufen'
description: Erfahren Sie, wie Sie eine Anwendung zur Anomalieerkennung bei Produktvertriebsdaten erstellen. Dieses Tutorial erstellt mithilfe von C# in Visual Studio 2019 eine .NET Core-Konsolenanwendung.
ms.date: 06/30/2020
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: cf61f197e4befebdbb1fbf2ca4cbcdc61c48780a
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281666"
---
# <a name="tutorial-detect-anomalies-in-product-sales-with-mlnet"></a>Tutorial: Erkennen von Anomalien in Produktverkäufen mit ML.NET

Erfahren Sie, wie Sie eine Anwendung zur Anomalieerkennung bei Produktvertriebsdaten erstellen. Dieses Tutorial erstellt mithilfe von C# in Visual Studio eine .NET Core-Konsolenanwendung.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> * Laden der Daten
> * Erstellen einer Transformation zur Erkennung von Anomaliespitzen
> * Erkennen von Anomaliespitzen mit der Transformation
> * Erstellen einer Transformation für die Anomalieerkennung bei Änderungspunkten
> * Erkennen von Änderungspunktanomalien mit der Transformation

Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).

## <a name="prerequisites"></a>Voraussetzungen

* [Visual Studio 2017 Version 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.

* [Das Dataset „product-sales.csv“](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)

>[!NOTE]
> Das Datenformat in `product-sales.csv` basiert auf dem Dataset „Shampoo Sales Over a Three Year Period“ von Rob Hyndman, ursprünglich aus dem DataMarket und von der Time Series Data Library (TSDL) bereitgestellt.
> Das Dataset „Shampoo Sales Over a Three Year Period“ ist im Rahmen der DataMarket Default Open License lizenziert.

## <a name="create-a-console-application"></a>Erstellen einer Konsolenanwendung

1. Erstellen Sie eine **.NET Core-Konsolenanwendung** mit dem Namen „ProductSalesAnomalyDetection“.

2. Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um die Datasetdateien zu speichern.

3. Installieren des **Microsoft.ML NuGet-Pakets**:

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie als Paketquelle „nuget.org“ aus. Klicken Sie dann auf die Registerkarte „Durchsuchen“ aus, suchen Sie nach **Microsoft.ML**, und klicken Sie anschließend auf **Installieren**. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen. Wiederholen Sie diese Schritte für **Microsoft.ML.TimeSeries**.

4. Fügen Sie am Anfang der Datei *Program.cs* die folgenden `using`-Anweisungen hinzu:

    [!code-csharp[AddUsings](./snippets/sales-anomaly-detection/csharp/Program.cs#AddUsings "Add necessary usings")]

### <a name="download-your-data"></a>Herunterladen der Daten

1. Laden Sie die das Dataset herunter, und speichern Sie es im Ordner *Data*, den Sie vorher erstellt haben:

   * Klicken Sie mit der rechten Maustaste auf [*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv) und anschließend auf „Link speichern unter“ oder „Ziel speichern unter“.

     Achten Sie darauf, die \*CSV-Datei entweder im Ordner *Data* zu speichern oder sie in den Ordner *Data* zu verschieben, nachdem Sie die \*CSV-Datei an anderer Stelle gespeichert haben.

2. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die \*CSV Datei, und wählen Sie **Eigenschaften** aus. Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.

Die folgende Tabelle enthält eine Datenvorschau aus Ihrem \*CSV-Datei:

|Monat  |ProductSales |
|-------|-------------|
|1-Jan  |    271      |
|2-Jan  |    150,9    |
|.....  |    .....    |
|1-Feb  |    199,3    |
|.....  |    .....    |

### <a name="create-classes-and-define-paths"></a>Erstellen von Klassen und Definieren von Pfaden

Als Nächstes definieren Sie Ihre Datenstruktur der Eingabe- und Vorhersageklasse.

Fügen Sie dem Projekt eine neue Klasse hinzu:

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und klicken Sie auf **Hinzufügen > Neues Element**.

2. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in*ProductSalesData.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.

   Die Datei *ProductSalesData.cs* wird im Code-Editor geöffnet.

3. Fügen Sie die folgende `using`-Anweisung am Anfang der *ProductSalesData.cs*-Datei hinzu:

   ```csharp
   using Microsoft.ML.Data;
   ```

4. Entfernen Sie die vorhandene Klassendefinition, und fügen Sie der Datei *ProductSalesData.cs* den folgenden Code mit den beiden Klassen `ProductSalesData` und `ProductSalesPrediction` hinzu:

    [!code-csharp[DeclareTypes](./snippets/sales-anomaly-detection/csharp/ProductSalesData.cs#DeclareTypes "Declare data record types")]

    `ProductSalesData` ist eine Klasse für Eingabedaten. Das [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29)-Attribut legt fest, welche Spalten (durch Angabe des Spaltenindex) im Dataset geladen werden sollen.

    `ProductSalesPrediction` gibt die Vorhersagedatenklasse an. Zur Anomalieerkennung besteht die Vorhersage aus einer Warnung, die angibt, ob eine Anomalie, eine Rohbewertung und ein Signifikanzwert (p-value; P-Wert) vorhanden sind. Je näher der Signifikanzwert an 0 ist, desto größer ist die Wahrscheinlichkeit einer Anomalie.

5. Erstellen Sie zwei globale Felder zum Speichern des gerade heruntergeladenen Datasetdateipfads und des gespeicherten Modelldateipfads:

    * `_dataPath` enthält den Pfad zu dem Dataset, das zum Trainieren des Modells verwendet wird.
    * `_docsize` enthält die Anzahl der Datensätze in der Datendatei. Sie verwenden `_docSize` zum Berechnen von `pvalueHistoryLength`.

6. Fügen Sie den folgenden Code der Zeile direkt über der `Main`-Methode hinzu, um diese Pfade anzugeben:

    [!code-csharp[Declare global variables](./snippets/sales-anomaly-detection/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

### <a name="initialize-variables-in-main"></a>Initialisieren von Variablen in Main

1. Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` in der `Main`-Methode durch den folgenden Code, um die Variable `mlContext` zu deklarieren und zu initialisieren:

    [!code-csharp[CreateMLContext](./snippets/sales-anomaly-detection/csharp/Program.cs#CreateMLContext "Create the ML Context")]

    Die [MLContext-Klasse](xref:Microsoft.ML.MLContext) ist der Startpunkt für alle ML.NET-Vorgänge. Durch das Initialisieren von `mlContext` wird eine neue ML.NET-Umgebung erstellt, die für mehrere Objekte des Modellerstellungsworkflows verwendet werden kann. Die Klasse ähnelt dem Konzept von `DBContext` in Entity Framework.

### <a name="load-the-data"></a>Laden der Daten

Daten werden in ML.NET als [IDataView-Klasse](xref:Microsoft.ML.IDataView) dargestellt. Mit `IDataView` können Tabellendaten (Zahlen und Text) flexibel und effizient beschrieben werden. Daten können aus einer Textdatei oder aus anderen Ressourcen (z. B. aus einer SQL-Datenbank oder aus Protokolldateien) in ein `IDataView`-Objekt geladen werden.

1. Fügen Sie der `Main()`-Methode folgenden Code als nächste Zeile hinzu:

    [!code-csharp[LoadData](./snippets/sales-anomaly-detection/csharp/Program.cs#LoadData "loading dataset")]

    Die [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)-Methode definiert das Datenschema und liest die Datei ein. Diese Methode akzeptiert Datenpfadvariablen und gibt ein `IDataView`-Objekt zurück.

## <a name="time-series-anomaly-detection"></a>Anomalieerkennung in Zeitreihen

Die Anomalieerkennung zeigt unerwartete oder ungewöhnliche Ereignisse oder Verhaltensweisen an. Sie erhalten Hinweise darauf, wo Sie nach Problemen schauen müssen, und können die Frage beantworten, ob das Ereignis oder Verhalten ungewöhnlich ist.

![Beispiel der Anomalieerkennung „Ist das ungewöhnlich“](./media/sales-anomaly-detection/time-series-anomaly-detection.png)

Die Anomalieerkennung ist ein Prozess, bei dem Ausreißer in Zeitreihendaten ermittelt. Damit wird auf Eingabezeitreihen hingewiesen, bei denen nicht das erwartete oder ein ungewöhnliches Verhalten aufgetreten ist.

Die Anomalieerkennung kann auf viele Weisen nützlich sein. Zum Beispiel:

Wenn Sie ein Auto besitzen, möchten Sie vielleicht wissen: Ist diese Ölstandsanzeige normal oder habe ich ein Leck?
Wenn Sie den Energieverbrauch überwachen, möchten Sie vielleicht wissen: Gibt es einen Stromausfall?

Es können zwei Arten von Zeitreihenanomalien erkannt werden:

* **Spitzen** zeigen temporäre Häufungen von anomalem Verhalten im System an.

* **Änderungspunkte** zeigen den Beginn anhaltender Änderungen im Zeitverlauf im System an.

In ML.NET eignen sich die Algorithmen „IID Spike Detection“ oder „IID Change point Detection“ für [unabhängige und identisch verteilte Datasets](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables).

Im Gegensatz zu den Modellen in den anderen Tutorials werden die Transformationen für die Zeitreihenanomalieerkennung direkt auf Eingabedaten angewendet. Die `IEstimator.Fit()`-Methode benötigt keine Trainingsdaten, um die Transformation zu entwickeln. Sie benötigt jedoch das Datenschema, das aus einer Datenansicht bereitgestellt wird, die aus einer leeren Liste von `ProductSalesData` generiert wird.

Sie analysieren die gleichen Produktvertriebsdaten, um Spitzen und Änderungspunkte zu erkennen. Der Prozess zum Erstellen und Trainieren eines Modells ist für die Erkennung von Spitzen und Änderungspunkten gleich; der Hauptunterschied besteht in dem verwendeten spezifischen Erkennungsalgorithmus.

## <a name="spike-detection"></a>Spitzenerkennung

Das Ziel der Spitzenerkennung ist es, plötzliche, aber temporäre Häufungen zu identifizieren, die sich signifikant von der Mehrzahl der Zeitreihen-Datenwerte unterscheiden. Es ist wichtig, diese verdächtigen seltenen Elemente, Ereignisse oder Beobachtungen rechtzeitig zu erkennen, um sie zu minimieren. Der folgende Ansatz kann zur Erkennung einer Vielzahl von Anomalien verwendet werden: z.B. Ausfälle, Cyberangriffe oder virale Webinhalte. Das folgende Bild zeigt ein Beispiel für Spitzen in einem Zeitreihen-Dataset:

![Screenshot: zwei ermittelte Spitzen](./media/sales-anomaly-detection/two-spike-detections.png)

### <a name="add-the-createemptydataview-method"></a>Hinzufügen der CreateEmptyDataView()-Methode

Fügen Sie `Program.cs` zur folgenden Methode hinzu:

[!code-csharp[CreateEmptyDataView](./snippets/sales-anomaly-detection/csharp/Program.cs#CreateEmptyDataView)]

Die Methode `CreateEmptyDataView()` erzeugt ein leeres Datenansichtsobjekt mit dem korrekten Schema, das für die Methode `IEstimator.Fit()` als Eingabe verwendet werden soll.

### <a name="create-the-detectspike-method"></a>Erstellen der DetectSpike()-Methode

Die `DetectSpike()`-Methode:

* erstellt die Transformation aus der Schätzung
* Erkennen von Spitzen basierend auf historischen Vertriebsdaten.
* Anzeigen der Ergebnisse.

1. Erstellen Sie die `DetectSpike()`-Methode mit dem folgenden Code direkt nach der `Main()`-Methode:

    ```csharp
    static void DetectSpike(MLContext mlContext, int docSize, IDataView productSales)
    {

    }
    ```

1. Verwenden Sie [IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator), um das Modell zum Erkennen von Spitzen zu trainieren. Fügen Sie ihn mit dem folgenden Code zur `DetectSpike()`-Methode hinzu:

    [!code-csharp[AddSpikeTrainer](./snippets/sales-anomaly-detection/csharp/Program.cs#AddSpikeTrainer)]

1. Fügen Sie den unten aufgeführten Code als nächste Codezeile in die `DetectSpike()`-Methode ein, um die Spitzenerkennungstransformation zu erstellen.

    [!code-csharp[TrainModel1](./snippets/sales-anomaly-detection/csharp/Program.cs#TrainModel1)]

1. Fügen Sie die folgende Codezeile hinzu, um die `productSales`-Daten als nächste Zeile in der `DetectSpike()`-Methode zu transformieren:

    [!code-csharp[TransformData1](./snippets/sales-anomaly-detection/csharp/Program.cs#TransformData1)]

    Der vorherige Code verwendet die [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A)-Methode trifft Vorhersagen für mehrere Eingabezeilen eines Datasets.

1. Konvertieren Sie Ihre `transformedData` mit der [CreateEnumerable()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A)-Methode mit dem folgenden Code in ein stark typisiertes `IEnumerable`-Element zur einfacheren Anzeige:

    [!code-csharp[CreateEnumerable1](./snippets/sales-anomaly-detection/csharp/Program.cs#CreateEnumerable1)]

1. Erstellen Sie mit dem folgenden <xref:System.Console.WriteLine?displayProperty=nameWithType>-Code eine Anzeige für die Kopfzeile:

    [!code-csharp[DisplayHeader1](./snippets/sales-anomaly-detection/csharp/Program.cs#DisplayHeader1)]

    In den Ergebnissen der Spitzenerkennung werden folgende Informationen angezeigt:

    * `Alert` gibt eine Spitzenwarnung für einen bestimmten Datenpunkt an.
    * `Score` ist der `ProductSales`-Wert für einen bestimmten Datenpunkt im Dataset.
    * `P-Value` Das „P“ steht für „Probability“ (Wahrscheinlichkeit). Je näher der Signifikanzwert an 0 ist, desto größer ist die Wahrscheinlichkeit, dass der Datenpunkt eine Anomalie darstellt.

1. Verwenden Sie den folgenden Code, um `predictions` `IEnumerable` zu durchlaufen und die Ergebnisse anzuzeigen:

    [!code-csharp[DisplayResults1](./snippets/sales-anomaly-detection/csharp/Program.cs#DisplayResults1)]

1. Fügen Sie den Aufruf der `DetectSpike()`-Methode in der `Main()`-Methode hinzu:

    [!code-csharp[CallDetectSpike](./snippets/sales-anomaly-detection/csharp/Program.cs#CallDetectSpike)]

## <a name="spike-detection-results"></a>Ergebnisse der Spitzenerkennung

Die Ergebnisse sollten den unten dargestellten ähneln. Während der Verarbeitung werden Meldungen angezeigt. Sie können Warnungen oder Verarbeitungsmeldungen sehen. Einige dieser Nachrichten wurden der Übersichtlichkeit halber aus den folgenden Ergebnissen entfernt.

```console
Detect temporary changes in pattern
=============== Training the model ===============
=============== End of training process ===============
Alert   Score   P-Value
0       271.00  0.50
0       150.90  0.00
0       188.10  0.41
0       124.30  0.13
0       185.30  0.47
0       173.50  0.47
0       236.80  0.19
0       229.50  0.27
0       197.80  0.48
0       127.90  0.13
1       341.50  0.00 <-- Spike detected
0       190.90  0.48
0       199.30  0.48
0       154.50  0.24
0       215.10  0.42
0       278.30  0.19
0       196.40  0.43
0       292.00  0.17
0       231.00  0.45
0       308.60  0.18
0       294.90  0.19
1       426.60  0.00 <-- Spike detected
0       269.50  0.47
0       347.30  0.21
0       344.70  0.27
0       445.40  0.06
0       320.90  0.49
0       444.30  0.12
0       406.30  0.29
0       442.40  0.21
1       580.50  0.00 <-- Spike detected
0       412.60  0.45
1       687.00  0.01 <-- Spike detected
0       480.30  0.40
0       586.30  0.20
0       651.90  0.14
```

## <a name="change-point-detection"></a>Erkennen von Änderungspunkten

`Change points` sind anhaltende Änderungen in der Verteilung der Werte in einem Zeitreihen-Ereignisstrom, wie Niveauänderungen und Trends. Diese anhaltenden Änderungen dauern wesentlich länger als `spikes` und könnten auf katastrophale Ereignisse hinweisen. `Change points` sind in der Regel nicht mit bloßem Auge erkennbar, können aber mit Ansätzen wie beispielsweise der folgenden Methode in Ihren Daten festgestellt werden.  Das folgende Bild ist ein Beispiel für eine Änderungspunkterkennung:

![Screenshot: Änderungspunkterkennung](./media/sales-anomaly-detection/change-point-detection.png)

### <a name="create-the-detectchangepoint-method"></a>Erstellen der DetectChangepoint()-Methode

Die `DetectChangepoint()`-Methode führt die folgenden Aufgaben aus:

* erstellt die Transformation aus der Schätzung
* Erkennen von Änderungspunkten basierend auf historischen Vertriebsdaten.
* Anzeigen der Ergebnisse.

1. Erstellen Sie die `DetectChangepoint()`-Methode mit dem folgenden Code direkt nach der `Main()`-Methode:

    ```csharp
    static void DetectChangepoint(MLContext mlContext, int docSize, IDataView productSales)
    {

    }
    ```

1. Erstellen Sie den [iidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator) in der `DetectChangepoint()`-Methode mit folgendem Code:

    [!code-csharp[AddChangepointTrainer](./snippets/sales-anomaly-detection/csharp/Program.cs#AddChangepointTrainer)]

1. Erstellen Sie wie zuvor die Transformation aus der Schätzung, indem Sie die folgende Codezeile in der `DetectChangePoint()`-Methode hinzufügen.

    [!code-csharp[TrainModel2](./snippets/sales-anomaly-detection/csharp/Program.cs#TrainModel2)]

1. Verwenden Sie die `Transform()`-Methode, um die Daten zu transformieren, indem Sie den folgenden Code zu `DetectChangePoint()` hinzufügen:

    [!code-csharp[TransformData2](./snippets/sales-anomaly-detection/csharp/Program.cs#TransformData2)]

1. Konvertieren Sie wie bereits zuvor Ihre `transformedData` mit der `CreateEnumerable()`-Methode mit dem folgenden Code in ein stark typisiertes `IEnumerable`-Element zur einfacheren Anzeige:

    [!code-csharp[CreateEnumerable2](./snippets/sales-anomaly-detection/csharp/Program.cs#CreateEnumerable2)]

1. Erstellen Sie mit dem folgenden Code als nächste Zeile in der `DetectChangePoint()`-Methode einen Anzeigeheader:

    [!code-csharp[DisplayHeader2](./snippets/sales-anomaly-detection/csharp/Program.cs#DisplayHeader2)]

    In den Ergebnissen der Änderungspunkterkennung werden folgende Informationen angezeigt:

    * `Alert` gibt eine Änderungspunktwarnung für einen bestimmten Datenpunkt an.
    * `Score` ist der `ProductSales`-Wert für einen bestimmten Datenpunkt im Dataset.
    * `P-Value` Das „P“ steht für „Probability“ (Wahrscheinlichkeit). Je näher der Signifikanzwert an 0 ist, desto größer ist die Wahrscheinlichkeit, dass der Datenpunkt eine Anomalie darstellt.
    * `Martingale value` wird verwendet, um basierend auf der Reihenfolge der P-Werte zu bestimmen, wie „ungewöhnlich ein Datenpunkt ist.

1. Mit dem folgenden Code können Sie `predictions` `IEnumerable` durchlaufen und die Ergebnisse anzeigen:

    [!code-csharp[DisplayResults2](./snippets/sales-anomaly-detection/csharp/Program.cs#DisplayResults2)]

1. Fügen Sie den folgenden Aufruf der `DetectChangepoint()`-Methode in der `Main()`-Methode hinzu:

    [!code-csharp[CallDetectChangepoint](./snippets/sales-anomaly-detection/csharp/Program.cs#CallDetectChangepoint)]

## <a name="change-point-detection-results"></a>Ergebnisse der Änderungspunkterkennung

Die Ergebnisse sollten den unten dargestellten ähneln. Während der Verarbeitung werden Meldungen angezeigt. Sie können Warnungen oder Verarbeitungsmeldungen sehen. Einige der Nachrichten wurden der Übersichtlichkeit halber aus den folgenden Ergebnissen entfernt.

```console
Detect Persistent changes in pattern
=============== Training the model Using Change Point Detection Algorithm===============
=============== End of training process ===============
Alert   Score   P-Value Martingale value
0       271.00  0.50    0.00
0       150.90  0.00    2.33
0       188.10  0.41    2.80
0       124.30  0.13    9.16
0       185.30  0.47    9.77
0       173.50  0.47    10.41
0       236.80  0.19    24.46
0       229.50  0.27    42.38
1       197.80  0.48    44.23 <-- alert is on, predicted changepoint
0       127.90  0.13    145.25
0       341.50  0.00    0.01
0       190.90  0.48    0.01
0       199.30  0.48    0.00
0       154.50  0.24    0.00
0       215.10  0.42    0.00
0       278.30  0.19    0.00
0       196.40  0.43    0.00
0       292.00  0.17    0.01
0       231.00  0.45    0.00
0       308.60  0.18    0.00
0       294.90  0.19    0.00
0       426.60  0.00    0.00
0       269.50  0.47    0.00
0       347.30  0.21    0.00
0       344.70  0.27    0.00
0       445.40  0.06    0.02
0       320.90  0.49    0.01
0       444.30  0.12    0.02
0       406.30  0.29    0.01
0       442.40  0.21    0.01
0       580.50  0.00    0.01
0       412.60  0.45    0.01
0       687.00  0.01    0.12
0       480.30  0.40    0.08
0       586.30  0.20    0.03
0       651.90  0.14    0.09
```

Herzlichen Glückwunsch! Sie haben jetzt erfolgreich Machine Learning-Modelle zur Erkennung von Spitzen und Änderungspunktanomalien in Vertriebsdaten erstellt.

Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> * Laden der Daten
> * Trainieren des Modells zur Erkennung von Anomaliespitzen
> * Erkennen von Anomaliespitzen mit dem trainierten Modell
> * Trainieren des Modells zur Erkennung einer Änderungspunktanomalie
> * Erkennen von Änderungspunktanomalien mit dem trainierten Modell

## <a name="next-steps"></a>Nächste Schritte

Durchsuchen Sie das GitHub-Repository für Machine Learning-Beispiele nach einem Beispiel für die Erkennung von Stromverbrauchsanomalien, damit Sie es untersuchen können.
> [!div class="nextstepaction"]
> [dotnet/machinelearning-samples-GitHub-Repository](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/AnomalyDetection_PowerMeterReadings)
