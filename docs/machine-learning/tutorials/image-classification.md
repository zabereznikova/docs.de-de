---
title: 'Tutorial: Generieren eines ML.NET-Bildklassifizierungsmodells aus einem vortrainierten TensorFlow-Modell'
description: Erfahren Sie, wie Sie das erworbene Wissen aus einem vorhandenen TensorFlow-Modell in ein neues ML.NET-Bildklassifizierungsmodell übertragen können. Das TensorFlow-Modell wurde trainiert, um Bilder in tausend Kategorien zu klassifizieren. Das ML.NET-Modell nutzt Übertragungslernen, um Bilder in weniger umfassendere Kategorien zu klassifizieren.
ms.date: 09/30/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
author: natke
ms.author: nakersha
ms.openlocfilehash: 399e9ce3288d53049e968688736f5b953d7e5b80
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799073"
---
# <a name="tutorial-generate-an-mlnet-image-classification-model-from-a-pre-trained-tensorflow-model"></a>Tutorial: Generieren eines ML.NET-Bildklassifizierungsmodells aus einem vortrainierten TensorFlow-Modell

Erfahren Sie, wie Sie das erworbene Wissen aus einem vorhandenen TensorFlow-Modell in ein neues ML.NET-Bildklassifizierungsmodell übertragen können.

Das TensorFlow-Modell wurde trainiert, um Bilder in tausend Kategorien zu klassifizieren. Das ML.NET-Modell nutzt einen Teil des TensorFlow-Modells in seiner Pipeline, um ein Modell zur Klassifizierung von Bildern in 3 Kategorien zu trainieren.

Das von Grund auf neue Trainieren eines Modells zur [Bildklassifizierung](https://en.wikipedia.org/wiki/Outline_of_object_recognition) erfordert das Einstellen von Millionen von Parametern, zahlreiche bezeichnete Trainingsdaten und eine große Menge an Computeressourcen (Hunderte von GPU-Stunden). Transfer Learning ist zwar nicht so effektiv wie das von Grund auf neue Trainieren eines benutzerdefinierten Modells, doch damit können Sie diesen Prozess durch die Arbeit mit Tausenden von Bildern im Vergleich zur Arbeit mit Millionen bezeichneter Bilder abkürzen und relativ schnell ein benutzerdefiniertes Modell erstellen (innerhalb einer Stunde auf einem Computer ohne eine GPU). In diesem Tutorial wird dieser Prozess noch weiter herunterskaliert, indem nur ein Dutzend Trainingsbilder verwendet werden.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> * Das Problem verstehen
> * Integrieren des vortrainierten TensorFlow-Modells in die ML.NET-Pipeline
> * Trainieren und Auswerten des ML.NET-Modells
> * Klassifizieren eines Testbilds

Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF). Hinweis: Die .NET-Projektkonfiguration, die für dieses Tutorial verwendet wird, ist standardmäßig auf .NET Core 2.2 ausgerichtet.

## <a name="what-is-transfer-learning"></a>Was ist Übertragungslernen?

Übertragungslernen ist der Prozess der Verwendung von Wissen, das bei der Lösung eines Problems erworben wurde, und der Anwendung dieses Wissens auf ein anderes, aber verwandtes Problem.

Für dieses Tutorial verwenden Sie einen Teil eines TensorFlow-Modells – trainiert, um Bilder in tausend Kategorien zu klassifizieren – in einem ML.NET-Modell, das Bilder in drei Kategorien klassifiziert.

## <a name="prerequisites"></a>Erforderliche Komponenten

* [Visual Studio 2017 Version 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.

* NuGet-Paket Microsoft.ML 1.3.1
* NuGet-Paket Microsoft.ML.ImageAnalytics 1.3.1
* NuGet-Paket Microsoft.ML.TensorFlow 1.3.1

* [Die ZIP-Datei mit dem Tutorialassetsverzeichnis ](https://github.com/dotnet/samples/blob/master/machine-learning/tutorials/TransferLearningTF/image-classifier-assets.zip)

* [Das Machine Learning-Modell von InceptionV1](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-right-machine-learning-task"></a>Auswählen der richtigen Machine Learning-Aufgabe

### <a name="deep-learning"></a>Deep Learning

[Deep Learning](https://en.wikipedia.org/wiki/Deep_learning) ist eine Teilmenge von Machine Learning, die Bereiche wie maschinelles Sehen und Spracherkennung revolutioniert.

Deep Learning-Modelle werden mithilfe großer Mengen [bezeichneter Daten](https://en.wikipedia.org/wiki/Labeled_data) und [neuronaler Netze](https://en.wikipedia.org/wiki/Artificial_neural_network) trainiert, die mehrere Lernebenen enthalten. Deep Learning:

* Bietet bei einigen Aufgaben eine bessere Leistung als maschinelles Sehen.
* Erfordert große Mengen an Trainingsdaten.

Bildklassifizierung ist eine gängige Machine Learning-Aufgabe, mit der automatisch Bilder in mehrere Kategorien klassifiziert werden können, beispielsweise:

* Erkennen, ob ein Bild ein menschliches Gesicht enthält oder nicht.
* Unterscheiden zwischen Katzen und Hunden.

 Es lässt sich auch wie in den folgenden Bildern bestimmen, ob ein Bild ein Lebensmittel, ein Spielzeug oder ein Gerät zeigt:

![Pizzabild](./media/image-classification/220px-Pepperoni_pizza.jpg)
![Teddybärbild](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![Toasterbild](./media/image-classification/193px-Broodrooster.jpg)

>[!Note]
> Die vorherigen Abbildungen stammen aus Wikimedia-Commons und unterliegen folgendem Urheberrecht:
>
> * „220px-Pepperoni_pizza.jpg“ Public Domain https://commons.wikimedia.org/w/index.php?curid=79505,
> * „119px-Nalle_-_a_small_brown_teddy_bear.jpg“ von [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) – selbst fotografiert, CC-BY-SA-2.0, https://commons.wikimedia.org/w/index.php?curid=48166.
> * „193px-Broodrooster.jpg“ von [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) – eigenes Werk, CC-BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403

Das `Inception model` ist darauf trainiert, Bilder in tausend Kategorien zu klassifizieren, jedoch müssen Sie für dieses Tutorial Bilder in eine kleinere Kategoriegruppe und nur in diese Kategorien klassifizieren. Geben Sie den `transfer`-Teil von `transfer learning` ein. Sie können die Fähigkeit des `Inception model` zum Erkennen und Klassifizieren von Bildern auf die neuen begrenzten Kategorien Ihrer benutzerdefinierten Bildklassifizierung übertragen.

* Lebensmittel
* Spielzeug
* Gerät

Dieses Tutorial verwendet das TensorFlow-Deep Learning-Modell [Inception](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), ein beliebtes Bilderkennungsmodell, das mit dem Dataset `ImageNet` trainiert wurde. Das TensorFlow-Modell klassifiziert ganze Bilder in tausend Klassen wie „Regenschirm“, „Trikot“ und „Geschirrspüler“.

Da das `Inception model` bereits anhand von Tausenden anderer Bilder vortrainiert wurde, enthält es intern die zur Bildidentifizierung erforderlichen [Bildmerkmale](https://en.wikipedia.org/wiki/Feature_(computer_vision)). Wir können diese internen Bildmerkmale im Modell verwenden, um ein neues Modell mit weitaus weniger Klassen zu trainieren.

Wie im folgenden Diagramm dargestellt, fügen Sie einen Verweis auf die ML.NET-NuGet-Pakete in Ihrer .NET Core- oder .NET Framework-Anwendung hinzu. Im Hintergrund beinhaltet und verweist ML.NET auf die native `TensorFlow`-Bibliothek, mit der Sie Code schreiben können, der eine vorhandene trainierte `TensorFlow`-Modelldatei lädt.

![TensorFlow-Transformation – ML.NET Arch-Diagramm](./media/image-classification/tensorflow-mlnet.png)

### <a name="multiclass-classification"></a>Multiklassenklassifizierung

Nachdem wir das TensorFlow-Inception-Modell verwendet haben, um Merkmale zu extrahieren, die als Eingabe für einen klassischen Machine Learning-Algorithmus geeignet sind, fügen wir einen ML.NET-[Multiklassenklassifizierer](../resources/tasks.md#multiclass-classification) hinzu.

Der in diesem Fall verwendete Trainingsmechanismus ist der [multinomiale logistische Regressionsalgorithmus](https://en.wikipedia.org/wiki/Multinomial_logistic_regression).

Der von diesem Trainingsmechanismus implementierte Algorithmus eignet sich gut für Probleme mit einer Vielzahl von Merkmalen, was bei einem Deep Learning-Modell der Fall ist, das mit Bilddaten arbeitet.

### <a name="data"></a>Daten

Es gibt zwei Datenquellen: die `.tsv`-Datei und die Bilddateien.  Die `tags.tsv`-Datei enthält zwei Spalten: die erste ist als `ImagePath` definiert und die zweite das `Label` für das Bild. Die folgende Beispieldatei verfügt nicht über eine Kopfzeile und sieht wie folgt aus:

<!-- markdownlint-disable MD010 -->
```tsv
broccoli.jpg    food
pizza.jpg   food
pizza2.jpg  food
teddy2.jpg  toy
teddy3.jpg  toy
teddy4.jpg  toy
toaster.jpg appliance
toaster2.png    appliance
```
<!-- markdownlint-enable MD010 -->

Die Trainings- und Testbilder befinden sich in dem Assetsordner, den Sie in einer ZIP-Datei herunterladen. Diese Bilder gehören zu Wikimedia Commons.
> *[Wikimedia-Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), das Repository für kostenlose Medien.* Abgerufen am 17. Oktober 2018 um 10:48 Uhr aus: https://commons.wikimedia.org/wiki/Pizza https://commons.wikimedia.org/wiki/Toaster https://commons.wikimedia.org/wiki/Teddy_bear

## <a name="setup"></a>Setup

### <a name="create-a-project"></a>Erstellen eines Projekts

1. Erstellen Sie eine **.NET Core-Konsolenanwendung** mit dem Namen „TransferLearningTF“.

1. Installieren des **Microsoft.ML NuGet-Pakets**:

    * Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.
    * Wählen Sie „nuget.org“ als Paketquelle aus, wählen Sie die Registerkarte „Durchsuchen“ aus, und suchen Sie nach **Microsoft.ML**.
    * Klicken Sie auf die Dropdownliste **Version**, und wählen Sie das Paket mit der Version **1.3.1** in der Liste aus. Klicken Sie dann auf die Schaltfläche **Installieren**.
    * Klicken Sie im Dialogfeld **Vorschau der Änderungen** auf die Schaltfläche **OK**.
    * Wählen Sie die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz**, wenn Sie mit den Lizenzbedingungen für die aufgeführten Pakete einverstanden sind.
    * Wiederholen Sie diese Schritte für **Microsoft.ML.ImageAnalytics v1.3.1** und **Microsoft.ML.TensorFlow v1.3.1**.

### <a name="download-assets"></a>Herunterladen von Ressourcen

1. Laden Sie [die ZIP-Datei des Projektassetverzeichnisses](https://github.com/dotnet/samples/blob/master/machine-learning/tutorials/TransferLearningTF/image-classifier-assets.zip) herunter, und entzippen Sie sie.

1. Kopieren Sie das `assets`-Verzeichnis in Ihr *TransferLearningTF*-Projektverzeichnis. Dieses Verzeichnis und seine Unterverzeichnisse enthalten die für dieses Tutorial erforderlichen Daten und Unterstützungsdateien (mit Ausnahme des Inception-Modells, das Sie im nächsten Schritt herunterladen und hinzufügen).

1. Laden Sie das [Inception-Modell](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) herunter, und entzippen Sie es.

1. Kopieren Sie den Inhalt des gerade entzippten `inception5h`-Verzeichnisses in Ihr *TransferLearningTF*-Projektverzeichnis `assets/inputs-train/inception`. Dieses Verzeichnis enthält das Modell und die zusätzlich für dieses Tutorial erforderlichen Unterstützungsdateien wie in der folgenden Abbildung gezeigt:

   ![Inhalt des Inception-Verzeichnisses](./media/image-classification/inception-files.png)

1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf alle Dateien im Assetverzeichnis und den Unterverzeichnissen, und wählen Sie **Eigenschaften** aus. Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.

### <a name="create-classes-and-define-paths"></a>Erstellen von Klassen und Definieren von Pfaden

1. Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:

    [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddUsings)]

1. Fügen Sie den folgenden Code der Zeile direkt über der `Main`-Methode hinzu, um die Ressourcenpfade anzugeben:

    [!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareGlobalVariables)]

1. Erstellen Sie anschließend Klassen für Ihre Eingabedaten und Vorhersagen.

    [!code-csharp[DeclareImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareImageData)]

    `ImageData` ist die Eingabebilddaten-Klasse mit den folgenden <xref:System.String>-Feldern:

    * `ImagePath` enthält den Bilddateinamen.
    * `Label` enthält einen Wert für die Bildbezeichnung.

1. Fügen Sie dem Projekt eine neue Klasse für `ImagePrediction` hinzu:

    [!code-csharp[DeclareImagePrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareImagePrediction)]

    `ImagePrediction` ist die Bildvorhersageklasse und hat die folgenden Felder:

    * `Score` enthält den Zuverlässigkeitsprozentsatz für eine bestimmte Bildklassifizierung.
    * `PredictedLabelValue` enthält einen Wert für die vorhergesagte Bildklassifizierungsbezeichnung.

    Die `ImagePrediction`-Klasse wird für die Vorhersage verwendet, nachdem das Modell trainiert wurde. Sie besitzt einen `string` (`ImagePath`) für den Bildpfad. Mit `Label` wird das Modell wiederverwendet und trainiert. Das `PredictedLabelValue` wird während der Vorhersage und Evaluierung verwendet. Für die Evaluierung werden eine Eingabe mit Trainingsdaten, die vorhergesagten Werte und das Modell verwendet.

### <a name="initialize-variables-in-main"></a>Initialisieren von Variablen in Main

1. Initialisieren Sie die `mlContext`-Variable mit einer neuen Instanz von `MLContext`.  Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` mit dem folgenden Code in der `Main`-Methode:

    [!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CreateMLContext)]

    Die [MLContext-Klasse](xref:Microsoft.ML.MLContext) ist der Startpunkt für alle ML.NET-Vorgänge. Durch das Initialisieren von `mlContext` wird eine neue ML.NET-Umgebung erstellt, die für mehrere Objekte des Modellerstellungsworkflows verwendet werden kann. Die Klasse ähnelt dem Konzept von `DBContext` in Entity Framework.

### <a name="create-a-struct-for-inception-model-parameters"></a>Erstellen einer Struktur für Inception-Modellparameter

1. Das Inception-Modell verfügt über mehrere Parameter, die Sie übergeben müssen. Erstellen Sie unmittelbar nach der `Main()`-Methode eine Struktur, um Anzeigenamen mit dem folgenden Code die Parameterwerte zuzuordnen:

    [!code-csharp[InceptionSettings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a>Erstellen einer Anzeigehilfsprogramm-Methode

Da Sie die Bilddaten und die zugehörigen Vorhersagen mehr als einmal anzeigen werden, erstellen Sie eine Anzeigehilfsmethode, um die Anzeige der Bild- und Vorhersageergebnisse zu verarbeiten.

1. Erstellen Sie die `DisplayResults()`-Methode mit dem folgenden Code direkt nach der `InceptionSettings`-Struktur:

    ```csharp
    private static void DisplayResults(IEnumerable<ImagePrediction> imagePredictionData)
    {

    }
    ```

1. Geben Sie den Text der `DisplayResults`-Methode ein:

    [!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPredictions)]

### <a name="create-a-tsv-file-utility-method"></a>Erstellen einer Hilfsprogrammmethode für die TSV-Datei

1. Erstellen Sie die `ReadFromTsv()`-Methode mit dem folgenden Code direkt nach der `DisplayResults()`-Methode:

    ```csharp
    public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
    {

    }
    ```

1. Geben Sie den Text der `ReadFromTsv`-Methode ein:

    [!code-csharp[ReadFromTsv](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReadFromTsv)]

    Der Code analysiert die `tags.tsv`-Datei, um den Dateipfad für die `ImagePath`-Eigenschaft dem Namen der Bilddatei hinzuzufügen und ihn und das `Label` in ein `ImageData`-Objekt zu laden.

### <a name="create-a-method-to-make-a-prediction"></a>Erstellen einer Methode zum Treffen einer Vorhersage

1. Erstellen Sie die `ClassifySingleImage()`-Methode mit dem folgenden Code direkt vor der `DisplayResults()`-Methode:

    ```csharp
    public static void ClassifySingleImage(MLContext mlContext, ITransformer model)
    {

    }
    ```

1. Erstellen Sie ein `ImageData`-Objekt, das den vollqualifizierten Pfad und Bilddateinamen für den einzelnen `ImagePath` enthält. Fügen Sie der `ClassifySingleImage()`-Methode folgenden Code als nächste Zeilen hinzu:

    [!code-csharp[LoadImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadImageData)]

1. Treffen Sie eine einzelne Vorhersage, indem Sie den folgenden Code als nächste Zeile in der `ClassifySingleImage`-Methode hinzufügen:

    [!code-csharp[PredictSingle](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#PredictSingle)]

    Um die Vorhersage zu erhalten, verwenden Sie die [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A)-Methode. Die [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) ist eine Hilfs-API, mit der Sie eine Vorhersage für eine einzelne Instanz der Daten treffen können. [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) ist nicht threadsicher. Die Verwendung in Singlethread-oder Prototypumgebungen ist zulässig. Zur Verbesserung der Leistung und Threadsicherheit in Produktionsumgebungen verwenden Sie den `PredictionEnginePool`-Dienst, der einen [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) aus [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)-Objekten für die Verwendung in Ihrer gesamten Anwendung erstellt. Informationen zur [Verwendung von `PredictionEnginePool` in einer ASP.NET Core-Web-API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application) finden Sie in dieser Anleitung.

    > [!NOTE]
    > Die `PredictionEnginePool`-Diensterweiterung ist derzeit als Vorschauversion verfügbar.

1. Zeigen Sie das Vorhersageergebnis als nächste Codezeile in der `ClassifySingleImage()`-Methode an:

   [!code-csharp[DisplayPrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPrediction)]

## <a name="construct-the-mlnet-model-pipeline"></a>Erstellen der ML.NET-Modellpipeline

Eine ML.NET-Modellpipeline ist eine Kette von Kalkulatoren. Beachten Sie, dass während der Pipelineerstellung keine Ausführung erfolgt. Die Kalkulatorobjekte werden erstellt, aber nicht ausgeführt.

1. Hinzufügen einer Methode zum Generieren des Modells

    Diese Methode ist das Herzstück des Tutorials. Sie erstellt eine Pipeline für das Modell und trainiert die Pipeline, um das ML.NET-Modell zu generieren. Außerdem wertet sie das Modell anhand einiger zuvor unbekannter Testdaten aus.

    Erstellen Sie die `GenerateModel()`-Methode mithilfe des folgenden Codes unmittelbar nach der `InceptionSettings`-Struktur und direkt vor der `DisplayResults()`-Methode:

    ```csharp
    public static ITransformer GenerateModel(MLContext mlContext)
    {

    }
    ```

1. Fügen Sie die Kalkulatoren zum Laden, Ändern der Größe und Extrahieren der Pixel aus den Bilddaten hinzu:

    [!code-csharp[ImageTransforms](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ImageTransforms)]

    Die Bilddaten müssen in das Format verarbeitet werden, das vom TensorFlow-Modell erwartet wird. In diesem Fall werden die Bilder in den Arbeitsspeicher geladen, die Größe in eine konsistente Größe geändert, und die Pixel werden in einen numerischen Vektor extrahiert.

1. Fügen Sie den Kalkulator zum Laden des TensorFlow-Modells hinzu, und versehen Sie es mit einem Score:

    [!code-csharp[ScoreTensorFlowModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ScoreTensorFlowModel)]

    Diese Phase in der Pipeline lädt das TensorFlow-Modell in den Arbeitsspeicher und verarbeitet dann den Vektor der Pixelwerte über das TensorFlow-Modellnetzwerk. Das Anwenden von Eingaben auf ein Deep Learning-Modell und das Generieren einer Ausgabe mithilfe des Modells wird als **Scoring** bezeichnet. Wenn Sie das Modell in seiner Gesamtheit verwenden, führt das Scoring zu einem Rückschluss oder einer Vorhersage.

    In diesem Fall verwenden Sie das gesamte TensorFlow-Modell mit Ausnahme der letzten Schicht, bei der es sich um die Schicht handelt, die den Rückschluss ausführt. Die Ausgabe der vorletzten Schicht wird als `softmax_2_preactivation` bezeichnet. Die Ausgabe dieser Schicht ist praktisch ein Vektor von Merkmalen, die die ursprünglichen Eingabebilder charakterisieren.

    Dieser vom TensorFlow-Modell generierte Merkmalsvektor wird als Eingabe in einen ML.NET-Trainingsalgorithmus verwendet.

1. Fügen Sie den Kalkulator hinzu, um die Zeichenfolgenbezeichnungen in den Trainingsdaten ganzzahligen Schlüsselwerten zuzuordnen:

    [!code-csharp[MapValueToKey](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey)]

    Der ML.NET-Trainingsmechanismus, der als nächstes angefügt wird, erfordert, dass seine Bezeichnungen im `key`-Format und nicht in beliebigen Zeichenfolgen vorliegen. Ein Schlüssel ist eine Zahl, die eine 1:1-Zuordnung zu einem Zeichenfolgenwert aufweist.

1. Fügen Sie den ML.NET-Trainingsalgorithmus hinzu:

    [!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddTrainer)]

1. Fügen Sie den Kalkulator hinzu, um den vorhergesagten Schlüsselwert erneut einer Zeichenfolge zuzuordnen:

    [!code-csharp[MapKeyToValue](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapKeyToValue)]

## <a name="train-the-model"></a>Trainieren des Modells

1. Laden Sie die Trainingsdaten mithilfe des [LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile(Microsoft.ML.DataOperationsCatalog,System.String,Microsoft.ML.Data.TextLoader.Options))-Wrappers. Fügen Sie der `GenerateModel()`-Methode folgenden Code als nächste Zeile hinzu:

    [!code-csharp[LoadData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadData "Load the data")]

    Daten werden in ML.NET als [IDataView-Klasse](xref:Microsoft.ML.IDataView) dargestellt. Mit `IDataView` können Tabellendaten (Zahlen und Text) flexibel und effizient beschrieben werden. Daten können aus einer Textdatei oder in Echtzeit (z. B. aus einer SQL-Datenbank oder aus Protokolldateien) in ein `IDataView`-Objekt geladen werden.

1. Trainieren Sie das Modell mit den zuvor geladenen Daten:

    [!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TrainModel)]

    Die `Fit()`-Methode trainiert Ihr Modell, indem das Trainingsdataset auf die Pipeline angewendet wird.

## <a name="evaluate-the-accuracy-of-the-model"></a>Auswerten der Genauigkeit des Modells

1. Laden und transformieren Sie die Testdaten, indem Sie der nächsten Zeile der `GenerateModel`-Methode den folgenden Code hinzufügen:

    [!code-csharp[LoadAndTransformTestData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadAndTransformTestData "Load and transform test data")]

    Es gibt einige Beispielbilder, die Sie zum Auswerten des Modells verwenden können. Wie die Trainingsdaten müssen diese in eine `IDataView` geladen werden, damit Sie vom Modell transformiert werden können.

1. Fügen Sie der `GenerateModel()`-Methode den folgenden Code hinzu, um das Modell auszuwerten:

    [!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Evaluate)]

    Nachdem Sie die Vorhersage festgelegt haben, führt die [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A)-Methode Folgendes aus:

    * Bewerten des Modells (Vergleichen der vorhergesagten Werte mit dem Testdataset `labels`).
    * Rückgabe der Modellleistungsmetriken.

1. Anzeigen der Modellgenauigkeitsmetriken

    Verwenden Sie den folgenden Code, um die Metriken anzuzeigen, die Ergebnisse freizugeben und dann mit ihnen zu arbeiten:

    [!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayMetrics)]

    Für die Bildklassifizierung werden die folgenden Metriken ausgewertet:

    * `Log-loss` – siehe [Protokollverlust](../resources/glossary.md#log-loss). Der Protokollverlust sollte so nahe wie möglich bei 0 liegen.
    * `Per class Log-loss`. Der Protokollverlust pro Klasse sollte so nahe wie möglich bei 0 liegen.

1. Fügen Sie den folgenden Code hinzu, um das trainierte Modell als nächste Zeile zurückzugeben:

    [!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReturnModel)]

## <a name="run-the-application"></a>Führen Sie die Anwendung aus!

1. Fügen Sie in der `Main`-Methode nach der Erstellung der MLContext-Klasse den Aufruf von `GenerateModel` hinzu:

    [!code-csharp[CallGenerateModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallGenerateModel)]

1. Fügen Sie den Aufruf der `ClassifySingleImage()`-Methode der `Main`-Methode als nächste Codezeile hinzu:

    [!code-csharp[CallClassifySingleImage](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifySingleImage)]

1. Führen Sie die Konsolen-App aus (STRG+F5). Ihre Ergebnisse sollten der folgenden Ausgabe ähneln.  Möglicherweise werden Warnungen oder Verarbeitungsnachrichten angezeigt. Diese wurden jedoch aus Gründen der Übersichtlichkeit aus den folgenden Ergebnissen entfernt.

    ```console
    =============== Training classification model ===============
    Image: broccoli.jpg predicted as: food with score: 0.976743
    Image: pizza.jpg predicted as: food with score: 0.9751652
    Image: pizza2.jpg predicted as: food with score: 0.9660203
    Image: teddy2.jpg predicted as: toy with score: 0.9748783
    Image: teddy3.jpg predicted as: toy with score: 0.9829691
    Image: teddy4.jpg predicted as: toy with score: 0.9868168
    Image: toaster.jpg predicted as: appliance with score: 0.9769174
    Image: toaster2.png predicted as: appliance with score: 0.9800823
    =============== Classification metrics ===============
    LogLoss is: 0.0228266745633507
    PerClassLogLoss is: 0.0277501705149937 , 0.0186303530571291 , 0.0217359128952187
    =============== Making single image classification ===============
    Image: toaster3.jpg predicted as: appliance with score: 0.9625379

    C:\Program Files\dotnet\dotnet.exe (process 4304) exited with code 0.
    Press any key to close this window . . .
    ```

Herzlichen Glückwunsch! Sie haben durch Anwenden von Übertragungslernen auf ein `TensorFlow`-Modell in ML.NET erfolgreich ein Machine Learning-Modell für die Bildklassifizierung erstellt.

Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> * Das Problem verstehen
> * Integrieren des vortrainierten TensorFlow-Modells in die ML.NET-Pipeline
> * Trainieren und Auswerten des ML.NET-Modells
> * Klassifizieren eines Testbilds

Sehen Sie sich im GitHub-Repository für Machine Learning-Beispiele nach einem Beispiel für erweiterte Bildklassifizierung um, damit Sie es untersuchen können.
> [!div class="nextstepaction"]
> [dotnet/machinelearning-samples-GitHub-Repository](https://github.com/dotnet/machinelearning-samples/)
