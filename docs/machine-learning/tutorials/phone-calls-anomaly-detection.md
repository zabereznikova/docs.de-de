---
title: 'Tutorial: Erkennen von Anomalien bei Telefonanrufen'
description: Hier erfahren Sie, wie Sie eine Anwendung zur Erkennung von Anomalien bei Zeitreihendaten erstellen. Dieses Tutorial erstellt mithilfe von C# in Visual Studio 2019 eine .NET Core-Konsolenanwendung.
ms.date: 12/04/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 3451a44f8fa7ae85625687b7d52f120c411df1b6
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "97634052"
---
# <a name="tutorial-detect-anomalies-in-time-series-with-mlnet"></a>Tutorial: Erkennen von Anomalien bei Zeitreihen mit ML.NET

Hier erfahren Sie, wie Sie eine Anwendung zur Erkennung von Anomalien bei Zeitreihendaten erstellen. Dieses Tutorial erstellt mithilfe von C# in Visual Studio 2019 eine .NET Core-Konsolenanwendung.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> * Laden der Daten
> * Erkennen eines Zeitraums für eine Zeitreihe
> * Erkennen von Anomalien bei einer periodischen Zeitreihe

Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/PhoneCallsAnomalyDetection).

## <a name="prerequisites"></a>Voraussetzungen

* [Visual Studio 2019 Version 16.7.8 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.

* [Dataset „phone-calls.csv“](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_PhoneCalls/SrCnnDetection/Data/phone-calls.csv)

## <a name="create-a-console-application"></a>Erstellen einer Konsolenanwendung

1. Erstellen Sie eine **.NET Core-Konsolenanwendung in C#** mit dem Namen „ProductSalesAnomalyDetection“.

2. Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um die Datasetdateien zu speichern.

3. Installieren des **Microsoft.ML NuGet-Pakets**:

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie als Paketquelle „nuget.org“ aus. Klicken Sie dann auf die Registerkarte „Durchsuchen“ aus, suchen Sie nach **Microsoft.ML**, und klicken Sie anschließend auf **Installieren**. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen. Wiederholen Sie diese Schritte für **Microsoft.ML.TimeSeries**.

4. Fügen Sie am Anfang der Datei *Program.cs* die folgenden `using`-Anweisungen hinzu:

    [!code-csharp[AddUsings](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#AddUsings "Add necessary usings")]

### <a name="download-your-data"></a>Herunterladen der Daten

1. Laden Sie die das Dataset herunter, und speichern Sie es im Ordner *Data*, den Sie vorher erstellt haben:

    Klicken Sie mit der rechten Maustaste auf [*phone-calls.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_PhoneCalls/SrCnnDetection/Data/phone-calls.csv) und anschließend auf „Link speichern unter“ oder „Ziel speichern unter“.

     Achten Sie darauf, die \*CSV-Datei entweder im Ordner *Data* zu speichern oder sie in den Ordner *Data* zu verschieben, nachdem Sie die \*CSV-Datei an anderer Stelle gespeichert haben.

2. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die \*CSV Datei, und wählen Sie **Eigenschaften** aus. Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.

Die folgende Tabelle enthält eine Datenvorschau aus Ihrem \*CSV-Datei:

| timestamp  | value |
|--------|--------------|
| 2018/9/3  | 36.69670857  |
| 2018/9/4  | 35.74160571  |
| .....  | .....  |
| 2018/10/3  | 34.49893429  |
| ...    | ....   |

Diese Datei stellt eine Zeitreihe dar. Jede Zeile in der Datei entspricht einem Datenpunkt. Jeder Datenpunkt verfügt über die beiden Attribute `timestamp` und `value`, mit denen die Anzahl der Telefonanrufe für jeden Tag dargestellt werden. Die Anzahl der Telefonanrufe wird zur Desensitivität transformiert.

### <a name="create-classes-and-define-paths"></a>Erstellen von Klassen und Definieren von Pfaden

Als Nächstes definieren Sie Ihre Datenstruktur der Eingabe- und Vorhersageklasse.

Fügen Sie dem Projekt eine neue Klasse hinzu:

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und klicken Sie auf **Hinzufügen > Neues Element**.

2. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *PhoneCallsData.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.

   Die Datei *PhoneCallsData.cs* wird im Code-Editor geöffnet.

3. Fügen Sie die folgende `using`-Anweisung am Anfang der Datei *PhoneCallsData.cs* hinzu:

   ```csharp
   using Microsoft.ML.Data;
   ```

4. Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code mit den beiden Klassen `PhoneCallsData` und `PhoneCallsPrediction` der Datei *PhoneCallsData.cs* hinzu:

    [!code-csharp[DeclareTypes](./snippets/phone-calls-anomaly-detection/csharp/PhoneCallsData.cs#DeclareTypes "Declare data record types")]

    `PhoneCallsData` ist eine Klasse für Eingabedaten. Das [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29)-Attribut legt fest, welche Spalten (durch Angabe des Spaltenindex) im Dataset geladen werden sollen. Es verfügt über die beiden Attribute `timestamp` und `value`, die den jeweiligen Attributen in der Datendatei entsprechen.

    `PhoneCallsPrediction` gibt die Vorhersagedatenklasse an. Bei der SR-CNN-Erkennung hängt die Vorhersage vom angegebenen [Erkennungsmodus](xref:Microsoft.ML.TimeSeries.SrCnnDetectMode) ab. In diesem Beispiel wählen wir den Modus `AnomalyAndMargin` aus. Die Ausgabe enthält sieben Spalten. In der Regel sind `IsAnomaly`, `ExpectedValue`, `UpperBoundary` und `LowerBoundary` ausreichend informativ. Anhand dieser Vektoren können Sie erkennen, ob es sich bei einem Punkt um eine Anomalie handelt. Zudem enthalten diese Vektoren Informationen zum erwarteten Wert des Punkts sowie zum unteren/oberen Grenzbereich des Punkts.

5. Fügen Sie den folgenden Code der Zeile direkt über der `Main`-Methode hinzu, um den Pfad zu Ihrer Datendatei anzugeben:

    [!code-csharp[Declare global variables](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

### <a name="initialize-variables-in-main"></a>Initialisieren von Variablen in Main

1. Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` in der `Main`-Methode durch den folgenden Code, um die Variable `mlContext` zu deklarieren und zu initialisieren:

    [!code-csharp[CreateMLContext](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#CreateMLContext "Create the ML Context")]

    Die [MLContext-Klasse](xref:Microsoft.ML.MLContext) ist der Startpunkt für alle ML.NET-Vorgänge. Durch das Initialisieren von `mlContext` wird eine neue ML.NET-Umgebung erstellt, die für mehrere Objekte des Modellerstellungsworkflows verwendet werden kann. Die Klasse ähnelt dem Konzept von `DBContext` in Entity Framework.

### <a name="load-the-data"></a>Laden der Daten

Daten werden in ML.NET als [IDataView-Klasse](xref:Microsoft.ML.IDataView) dargestellt. Mit `IDataView` können Tabellendaten (Zahlen und Text) flexibel und effizient beschrieben werden. Daten können aus einer Textdatei oder aus anderen Ressourcen (z. B. aus einer SQL-Datenbank oder aus Protokolldateien) in ein `IDataView`-Objekt geladen werden.

1. Fügen Sie der `Main`-Methode folgenden Code als nächste Zeile hinzu:

    [!code-csharp[LoadData](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#LoadData "loading dataset")]

    Die [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)-Methode definiert das Datenschema und liest die Datei ein. Diese Methode akzeptiert Datenpfadvariablen und gibt ein `IDataView`-Objekt zurück.

## <a name="time-series-anomaly-detection"></a>Anomalieerkennung in Zeitreihen

Bei der Erkennung von Anomalien bei Zeitreihen handelt es sich um einen Prozess, bei dem Ausreißer in Zeitreihendaten ermittelt werden. Damit wird auf Eingabezeitreihen hingewiesen, bei denen nicht das erwartete oder ein ungewöhnliches Verhalten aufgetreten ist. Diese Anomalien sind in der Regel Hinweise auf einige relevante Ereignisse in der Problemdomäne: ein Cyberangriff auf Benutzerkonten, Stromausfälle, ein sprunghafter Anstieg von Anforderungen pro Sekunde auf einem Server, Arbeitsspeicherverlust usw.

Zum Auffinden von Anomalien in Zeitreihen sollten Sie zunächst den Zeitraum der Reihe bestimmen. Anschließend kann die Zeitreihe in Form von `Y = T + S + R` in verschiedene Komponenten zerlegt werden, wobei `Y` der ursprünglichen Reihe, `T` der Trendkomponente, `S` der saisonalen Komponente und `R` der Restkomponente der Reihe entspricht. Dieser Schritt wird als [Zerlegung](https://en.wikipedia.org/wiki/Decomposition_of_time_series) bezeichnet. Abschließend wird zum Auffinden der Anomalien für die Restkomponente eine Erkennung ausgeführt. In ML.NET ist der SR-CNN-Algorithmus ein intelligenter und neuartiger Algorithmus, mit dem Anomalien bei Zeitreihen mittels SR-Methode (Spectral Residual) und Convolutional Neural Network (CNN) erkannt werden. Weitere Informationen zu diesem Algorithmus finden Sie unter [Time-Series Anomaly Detection Service at Microsoft](https://arxiv.org/pdf/1906.03821.pdf) (Dienst bei Microsoft zur Erkennung von Anomalien bei Zeitreihen).

In diesem Tutorial werden Sie sehen, dass diese Verfahren mit zwei Funktionen durchgeführt werden können.

## <a name="detect-period"></a>Erkennen eines Zeitraums

Im ersten Schritt wird die Funktion `DetectSeasonality` aufgerufen, um den Zeitraum der Reihe zu bestimmen.

### <a name="create-the-detectperiod-method"></a>Erstellen der DetectPeriod-Methode

1. Erstellen Sie mit dem folgenden Code die `DetectPeriod`-Methode direkt unterhalb der `Main`-Methode:

    ```csharp
    static void DetectPeriod(MLContext mlContext, IDataView phoneCalls)
    {

    }
    ```

2. Verwenden Sie die Funktion <xref:Microsoft.ML.TimeSeriesCatalog.DetectSeasonality%2A> zum Erkennen des Zeitraums. Fügen Sie ihn mit dem folgenden Code zur `DetectPeriod`-Methode hinzu:

    [!code-csharp[DetectSeasonality](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DetectSeasonality)]

3. Zeigen Sie den Wert für den Zeitraum an, indem Sie den unten aufgeführten Code als nächste Codezeile in der `DetectPeriod`-Methode hinzufügen:

    [!code-csharp[DisplayPeriod](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DisplayPeriod)]

4. Fügen Sie der `DetectPeriod`-Methode in der `Main`-Methode den folgenden Aufruf hinzu:

    [!code-csharp[CallDetectPeriod](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#CallDetectPeriod)]

### <a name="period-detection-results"></a>Ergebnisse der Zeitraumerkennung

Führen Sie die Anwendung aus. Die Ergebnisse sollten den unten dargestellten ähneln.

```console
Period of the series is: 7.
```

## <a name="detect-anomaly"></a>Erkennen von Anomalien

In diesem Schritt werden Anomalien mithilfe der <xref:Microsoft.ML.TimeSeriesCatalog.DetectEntireAnomalyBySrCnn%2A>-Methode erkannt.

### <a name="create-the-detectanomaly-method"></a>Erstellen der DetectAnomaly-Methode

1. Erstellen Sie mit dem folgenden Code die `DetectAnomaly`-Methode direkt unterhalb der `DetectPeriod`-Methode:

    ```csharp
    static void DetectAnomaly(MLContext mlContext, IDataView phoneCalls, int period)
    {

    }
    ```

2. Richten Sie <xref:Microsoft.ML.TimeSeries.SrCnnEntireAnomalyDetectorOptions> mit dem folgenden Code in der `DetectAnomaly`-Methode ein:

    [!code-csharp[SetupSrCnnParameters](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#SetupSrCnnParameters)]

3. Erkennen Sie Anomalien mithilfe des SR-CNN-Algorithmus, indem Sie in der `DetectAnomaly`-Methode die folgende Codezeile hinzufügen:

    [!code-csharp[DetectAnomaly](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DetectAnomaly)]

4. Konvertieren Sie die Ansicht der Ausgabedaten zur einfacheren Anzeige mit der [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A)-Methode mit dem folgenden Code in ein stark typisiertes `IEnumerable`-Element:

    [!code-csharp[CreateEnumerableForResult](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#CreateEnumerableForResult)]

5. Erstellen Sie mit dem folgenden Code als nächste Zeile in der `DetectAnomaly`-Methode einen Anzeigeheader:

    [!code-csharp[DisplayHeader](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DisplayHeader)]

    In den Ergebnissen der Änderungspunkterkennung werden folgende Informationen angezeigt:

    * `Index` entspricht dem Index des jeweiligen Datenpunkts.
    * `Anomaly` entspricht dem Indikator, der angibt, ob der jeweilige Punkt als Anomalie erkannt wird.
    * `ExpectedValue` entspricht dem Schätzwert des jeweiligen Punkts.
    * `LowerBoundary` entspricht dem niedrigsten Wert, den ein Punkt annehmen kann, ohne als Anomalie zu gelten.
    * `UpperBoundary` entspricht dem höchsten Wert, den ein Punkt annehmen kann, ohne als Anomalie zu gelten.

6. Mit dem folgenden Code können Sie `predictions` `IEnumerable` durchlaufen und die Ergebnisse anzeigen:

    [!code-csharp[DisplayAnomalyDetectionResults](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DisplayAnomalyDetectionResults)]

7. Fügen Sie der `DetectAnomaly`-Methode in der `Main`-Methode den folgenden Aufruf hinzu:

    [!code-csharp[CallDetectAnomaly](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#CallDetectAnomaly)]

## <a name="anomaly-detection-results"></a>Ergebnisse der Anomalieerkennung

Führen Sie die Anwendung aus. Die Ergebnisse sollten den unten dargestellten ähneln. Während der Verarbeitung werden Meldungen angezeigt. Möglicherweise werden Warnungen oder Verarbeitungsmeldungen angezeigt. Einige der Nachrichten wurden der Übersichtlichkeit halber aus den folgenden Ergebnissen entfernt.

```console
Detect period of the series
Period of the series is: 7.
Detect anomaly points in the series
Index   Data    Anomaly AnomalyScore    Mag     ExpectedValue   BoundaryUnit    UpperBoundary   LowerBoundary
0,0,36.841787256739266,41.14206982401966,32.541504689458876
1,0,35.67303618137362,39.97331874865401,31.372753614093227
2,0,34.710132999891826,39.029491313022824,30.390774686760828
3,0,33.44765248883495,37.786086547816545,29.10921842985335
4,0,28.937110922276364,33.25646923540736,24.61775260914537
5,0,5.143895892785781,9.444178460066171,0.843613325505391
6,0,5.163325228419392,9.463607795699783,0.8630426611390014
7,0,36.76414836240396,41.06443092968435,32.46386579512357
8,0,35.77908590657007,40.07936847385046,31.478803339289676
9,0,34.547259536635245,38.847542103915636,30.246976969354854
10,0,33.55193524820608,37.871293561337076,29.23257693507508
11,0,29.091800129624648,33.392082696905035,24.79151756234426
12,0,5.154836630338823,9.455119197619213,0.8545540630584334
13,0,5.234332502492464,9.534615069772855,0.934049935212073
14,0,36.54992549471526,40.85020806199565,32.24964292743487
15,0,35.79526470980883,40.095547277089224,31.494982142528443
16,0,34.34099013096804,38.64127269824843,30.040707563687647
17,0,33.61201516582131,37.9122977331017,29.31173259854092
18,0,29.223563320561812,33.5238458878422,24.923280753281425
19,0,5.170512168851533,9.470794736131923,0.8702296015711433
20,0,5.2614938889462834,9.561776456226674,0.9612113216658926
21,0,36.37103858487317,40.67132115215356,32.07075601759278
22,0,35.813544599026855,40.113827166307246,31.513262031746464
23,0,34.05600492733225,38.356287494612644,29.755722360051863
24,0,33.65828319077884,37.95856575805923,29.358000623498448
25,0,29.381125690882463,33.681408258162854,25.080843123602072
26,0,5.261543539820418,9.561826107100808,0.9612609725400283
27,0,5.4873712582971805,9.787653825577571,1.1870886910167897
28,1,36.504694001629254,40.804976568909645,32.20441143434886  <-- alert is on, detected anomaly
...
```

Herzlichen Glückwunsch! Sie haben Machine Learning-Modelle zur Erkennung von Zeiträumen und Anomalien in einer periodischen Zeitreihe erstellt.

Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/PhoneCallsAnomalyDetection).

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> * Laden der Daten
> * Erkennen eines Zeitraums bei Zeitreihendaten
> * Erkennen einer Anomalie bei Zeitreihendaten

## <a name="next-steps"></a>Nächste Schritte

Durchsuchen Sie das GitHub-Repository für Machine Learning-Beispiele nach einem Beispiel für die Erkennung von Stromverbrauchsanomalien, damit Sie es untersuchen können.
> [!div class="nextstepaction"]
> [dotnet/machinelearning-samples-GitHub-Repository](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/AnomalyDetection_PowerMeterReadings)
