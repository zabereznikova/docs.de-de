---
title: 'Tutorial: Erkennen von Objekten mithilfe eines ONNX-Deep-Learning-Modells'
description: In diesem Tutorial wird veranschaulicht, wie Sie ein vortrainiertes ONNX Deep Learning-Modell in ML.NET verwenden, um Objekte in Bildern zu erkennen.
author: luisquintanilla
ms.author: luquinta
ms.date: 01/30/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: d9677c6c9da542123146fc9eef9c311ef30c174e
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2020
ms.locfileid: "81608009"
---
# <a name="tutorial-detect-objects-using-onnx-in-mlnet"></a>Tutorial: Erkennen von Objekten mithilfe von ONNX in ML.NET

Erfahren Sie, wie Sie ein vortrainiertes ONNX-Modell in ML.NET verwenden, um Objekte in Bildern zu erkennen.

Das von Grund auf neue Trainieren eines Objekterkennungsmodells erfordert das Festlegen von Millionen von Parametern, zahlreiche bezeichnete Trainingsdaten und eine große Menge an Computeressourcen (Hunderte von GPU-Stunden). Die Verwendung eines vortrainierten Modells ermöglicht es Ihnen, den Trainingsprozess zu verkürzen.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> - Das Problem verstehen
> - Erfahren Sie, was ONNX ist und wie ONNX mit ML.NET funktioniert.
> - Verstehen des Modells
> - Wiederverwenden des vortrainierten Modells
> - Erkennen von Objekten mit einem geladenen Modell

## <a name="pre-requisites"></a>Voraussetzungen

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) oder höher oder Visual Studio 2017 Version 15.6 oder höher mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.
- [Microsoft.ML NuGet-Paket](https://www.nuget.org/packages/Microsoft.ML/)
- [Microsoft.ML.ImageAnalytics NuGet-Paket](https://www.nuget.org/packages/Microsoft.ML.ImageAnalytics/)
- [Microsoft.ML.OnnxTransformer NuGet-Paket](https://www.nuget.org/packages/Microsoft.ML.OnnxTransformer/)
- [Vortrainiertes Tiny YOLOv2-Modell](https://github.com/onnx/models/tree/master/vision/object_detection_segmentation/tiny_yolov2)
- [Netron](https://github.com/lutzroeder/netron) (optional)

## <a name="onnx-object-detection-sample-overview"></a>ONNX-Objekterkennungsbeispiel: Übersicht

Dieses Beispiel erstellt eine .NET Core-Konsolenanwendung, die Objekte in einem Bild mithilfe eines vortrainierten Deep Learning ONNX-Modells erkennt. Den Code für dieses Beispiel finden Sie im [dotnet/machinelearning-Beispielrepository](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx) auf GitHub.

## <a name="what-is-object-detection"></a>Was ist Objekterkennung?

Objekterkennung ist ein Problem des maschinellen Sehens. Obwohl die Objekterkennung eng mit der Bildklassifizierung verwandt ist, führt sie die Bildklassifizierung auf einer detaillierteren Ebene durch. Die Objekterkennung ermittelt _und_ kategorisiert Entitäten in Bildern. Verwenden Sie die Objekterkennung, wenn Bilder mehrere Objekte verschiedener Typen enthalten.

![Screenshots zum Vergleich der Bildklassifizierung mit der Objektklassifizierung](./media/object-detection-onnx/img-classification-obj-detection.png)

Einige Anwendungsfälle für die Objekterkennung sind:

- Autonomes Fahren
- Robotik
- Gesichtserkennung
- Arbeitsplatzsicherheit
- Objektzählung
- Aktivitätserkennung

## <a name="select-a-deep-learning-model"></a>Auswählen eines Deep Learning-Modells

Deep Learning ist eine Teilmenge von Machine Learning. Zum Trainieren von Deep Learning-Modellen sind große Mengen von Daten erforderlich. Muster in den Daten werden durch eine Reihe von Schichten dargestellt. Die Beziehungen in den Daten werden als Verbindungen zwischen den Schichten mit Gewichtungen codiert. Je höher die Gewichtung, desto stärker die Beziehung. Zusammen werden diese Schichten und Verbindungen als künstliche neuronale Netze bezeichnet. Je mehr Schichten in einem Netzwerk vorhanden sind, desto „tiefer“ ist es, was es zu einem Deep Neural Network macht.

Es gibt verschiedene Arten von neuronalen Netzen, wobei die häufigsten MLP (Multi-Layered Perceptron), CNN (Convolutional Neural Network) und RNN (Recurrent Neural Network) sind. Das einfachste neuronale Netz ist MLP, das eine Reihe von Eingaben einem Satz von Ausgaben zuordnet. Dieses neuronale Netz eignet sich gut, wenn die Daten nicht über eine räumliche oder zeitliche Komponente verfügen. Das CNN nutzt Faltungsschichten, um die in den Daten enthaltenen räumlichen Informationen zu verarbeiten. Ein guter Anwendungsfall für CNNs ist die Bildverarbeitung, um das Vorhandensein eines Merkmals in einer Region eines Bilds zu erkennen (Beispiel: befindet sich eine Nase in der Mitte eines Bilds?). RNNs schließlich ermöglichen die Verwendung von Persistenz von Zustand oder Speicher als Eingabe. RNNs werden für die Zeitreihenanalyse verwendet, bei der die sequenzielle Reihenfolge und der Kontext der Ereignisse wichtig sind.

### <a name="understand-the-model"></a>Verstehen des Modells

Objekterkennung ist eine Bildverarbeitungsaufgabe. Daher sind die meisten Deep Learning-Modelle, die zur Lösung dieses Problems trainiert werden, CNNs. Das in diesem Tutorial verwendete Modell ist das Tiny YOLOv2-Modell, eine kompaktere Version des YOLOv2-Modells, das im folgenden Dokument beschrieben wird: [„YOLO9000: Better, Faster, Stronger“ von Redmon und Fadhari](https://arxiv.org/pdf/1612.08242.pdf). Tiny YOLOv2 wird mit dem Pascal VOC-Dataset trainiert und besteht aus 15 Schichten, die 20 verschiedene Klassen von Objekten vorhersagen können. Da Tiny YOLOv2 eine komprimierte Version des ursprünglichen YOLOv2-Modells ist, wird ein Kompromiss zwischen Geschwindigkeit und Genauigkeit erzielt. Die verschiedenen Schichten, die das Modell bilden, können mithilfe von Tools wie etwa Netron visualisiert werden. Die Untersuchung des Modells würde eine Zuordnung der Verbindungen zwischen allen Schichten ergeben, aus denen sich das neuronale Netz zusammensetzt, wobei jede Schicht den Namen der Schicht zusammen mit den Dimensionen der jeweiligen Ein- bzw. Ausgabe enthalten würde. Die Datenstrukturen, die zum Beschreiben der Eingaben und Ausgaben des Modells verwendet werden, werden als Tensoren bezeichnet. Tensoren können als Container betrachtet werden, in denen Daten in N Dimensionen gespeichert werden. Im Fall von Tiny YOLOv2 ist der Name der Eingabeschicht `image`, und es wird ein Tensor mit den Dimensionen `3 x 416 x 416` erwartet. Der Name der Ausgabeschicht ist `grid`, und es wird ein Tensor mit den Dimensionen `125 x 13 x 13` generiert.

![Die Eingabeschicht wird in verborgene Schichten aufgeteilt und führt zur Ausgabeschicht.](./media/object-detection-onnx/netron-model-map-layers.png)

Das Yolo-Modell verwendet ein Bild mit `3(RGB) x 416px x 416px`. Das Modell nimmt diese Eingabe an und übergibt sie durch die verschiedenen Schichten, um eine Ausgabe zu generieren. Die Ausgabe teilt das Eingabebild in ein `13 x 13`-Raster auf, wobei jede Zelle im Raster aus `125` Werten besteht.

### <a name="what-is-an-onnx-model"></a>Was ist ein ONNX-Modell?

ONNX (Open Neural Network Exchange) ist ein Open-Source-Format für KI-Modelle. ONNX unterstützt die Interoperabilität zwischen Frameworks. Das bedeutet, dass Sie ein Modell in einem der vielen gängigen Machine Learning-Frameworks wie PyTorch trainieren, es in das ONNX-Format konvertieren und das ONNX-Modell in einem anderen Framework wie ML.NET verwenden können. Weitere Informationen finden Sie auf der [ONNX-Website](https://onnx.ai/).

![Diagramm der verwendeten unterstützten ONNX-Formate](./media/object-detection-onnx/onnx-supported-formats.png)

Das vortrainierte Tiny YOLOv2-Modell wird im ONNX-Format gespeichert, einer serialisierten Darstellung der Schichten und erlernten Muster dieser Schichten. In ML.NET wird die Interoperabilität mit ONNX mit den NuGet-Paketen [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) und [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer) erreicht. Das Paket [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) enthält eine Reihe von Transformationen, die ein Bild annehmen und in numerische Werte codieren, die als Eingabe in eine Vorhersage- oder Trainingspipeline verwendet werden können. Das Paket [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer) nutzt die ONNX Runtime, um ein ONNX-Modell zu laden und damit Vorhersagen basierend auf bereitgestellten Eingaben zu treffen.

![Datenfluss der ONNX-Datei in die ONNX-Runtime](./media/object-detection-onnx/onnx-ml-net-integration.png)

## <a name="set-up-the-net-core-project"></a>Einrichten des .NET Core-Projekts

Da Sie nun ein allgemeines Verständnis davon haben, was ONNX ist und wie Tiny YOLOv2 funktioniert, ist es an der Zeit, die Anwendung zu erstellen.

### <a name="create-a-console-application"></a>Erstellen einer Konsolenanwendung

1. Erstellen Sie eine **.NET Core-Konsolenanwendung** mit dem Namen „ObjectDetection“.

1. Installieren des **Microsoft.ML NuGet-Pakets**:

    - Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.
    - Wählen Sie „nuget.org“ als Paketquelle aus, wählen Sie die Registerkarte „Durchsuchen“ aus, und suchen Sie nach **Microsoft.ML**.
    - Wählen Sie die Schaltfläche **Installieren** aus.
    - Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.
    - Wiederholen Sie diese Schritte für **Microsoft.ML.ImageAnalytics** und **Microsoft.ML.OnnxTransformer**.

### <a name="prepare-your-data-and-pre-trained-model"></a>Vorbereiten der Daten und des vortrainierten Modells

1. Laden Sie die [ZIP-Datei aus dem Projektressourcenverzeichnis](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/assets.zip) herunter, und entzippen Sie sie.

1. Kopieren Sie das Verzeichnis `assets` in Ihr *ObjectDetection*-Projektverzeichnis. Dieses Verzeichnis und seine Unterverzeichnisse enthalten die für dieses Tutorial erforderlichen Bilddateien (mit Ausnahme des Tiny YOLOv2-Modells, das Sie im nächsten Schritt herunterladen und hinzufügen).

1. Laden Sie das [Tiny YOLOv2-Modell](https://onnxzoo.blob.core.windows.net/models/opset_8/tiny_yolov2/tiny_yolov2.tar.gz) aus dem [ONNX Model Zoo](https://github.com/onnx/models/tree/master/vision/object_detection_segmentation/tiny_yolov2) herunter, und entzippen Sie es.

    Öffnen Sie die Eingabeaufforderung, und geben Sie den folgenden Befehl ein:

    ```shell
    tar -xvzf tiny_yolov2.tar.gz
    ```

1. Kopieren Sie die extrahierte Datei `model.onnx` aus dem soeben entzippten Verzeichnis in das Verzeichnis `assets\Model` Ihres *ObjectDetection*-Projekts, und benennen Sie sie in `TinyYolo2_model.onnx` um. Dieses Verzeichnis enthält das für dieses Tutorial erforderliche Modell.

1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf alle Dateien im Assetverzeichnis und den Unterverzeichnissen, und wählen Sie **Eigenschaften** aus. Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.

### <a name="create-classes-and-define-paths"></a>Erstellen von Klassen und Definieren von Pfaden

Öffnen Sie die Datei *Program.cs*, und fügen Sie am Anfang der Datei folgende zusätzliche `using`-Anweisungen hinzu:

[!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L1-L7)]

Definieren Sie als nächstes die Pfade der verschiedenen Ressourcen.

1. Fügen Sie zunächst die `GetAbsolutePath`-Methode unter der `Main`-Methode in der `Program`-Klasse hinzu.

    [!code-csharp [GetAbsolutePath](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L66-L74)]

1. Erstellen Sie dann in der Methode `Main` Felder, um den Speicherort Ihrer Ressourcen zu speichern.

    [!code-csharp [AssetDefinition](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L17-L21)]

Fügen Sie Ihrem Projekt ein neues Verzeichnis hinzu, um die Eingabedaten und Vorhersageklassen zu speichern.

Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neuer Ordner** aus. Wenn der neue Ordner im Projektmappen-Explorer angezeigt wird, nennen Sie ihn „DataStructures“.

Erstellen Sie die Eingabedatenklasse im neu erstellten Verzeichnis *DataStructures*.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Verzeichnis *DataStructures*, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.
1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *ImageNetData.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.

    Die Datei *ImageNetData.cs* wird im Code-Editor geöffnet. Fügen Sie die folgende `using`-Anweisung am Anfang der Datei *ImageNetData.cs* hinzu:

    [!code-csharp [ImageNetDataUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetData.cs#L1-L4)]

    Entfernen Sie die vorhandene Klassendefinition, und fügen Sie der Datei *ImageNetData.cs* den folgenden Code für die `ImageNetData`-Klasse hinzu:

    [!code-csharp [ImageNetDataClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetData.cs#L8-L23)]

    `ImageNetData` ist die Eingabebilddaten-Klasse mit den folgenden <xref:System.String>-Feldern:

    - `ImagePath` enthält den Pfad, in dem das Bild gespeichert ist.
    - `Label` enthält den Namen der Datei.

    Darüber hinaus enthält `ImageNetData` eine Methode `ReadFromFile`, die mehrere Bilddateien lädt, die im angegebenen Pfad `imageFolder` gespeichert sind, und sie als eine Sammlung von `ImageNetData`-Objekten zurückgibt.

Erstellen Sie die Vorhersageklasse im Verzeichnis *DataStructures*.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Verzeichnis *DataStructures*, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.
1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *ImageNetPrediction.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.

    Die Datei *ImageNetPrediction.cs* wird im Code-Editor geöffnet. Fügen Sie die folgende `using`-Anweisung am Anfang der Datei *ImageNetPrediction.cs* hinzu:

    [!code-csharp [ImageNetPredictionUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetPrediction.cs#L1)]

    Entfernen Sie die vorhandene Klassendefinition, und fügen Sie der Datei *ImageNetPrediction.cs* den folgenden Code für die `ImageNetPrediction`-Klasse hinzu:

    [!code-csharp [ImageNetPredictionClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetPrediction.cs#L5-L9)]

    `ImageNetPrediction` ist die Vorhersagedatenklasse und weist das folgende `float[]`-Feld auf:

    - `PredictedLabel` enthält die Dimensionen, die Objektbewertung und die Klassenwahrscheinlichkeiten für jeden der Begrenzungsrahmen, der in einem Bild erkannt wird.

### <a name="initialize-variables-in-main"></a>Initialisieren von Variablen in Main

Die [MLContext-Klasse](xref:Microsoft.ML.MLContext) ist der Startpunkt für alle ML.NET-Vorgänge. Durch das Initialisieren von `mlContext` wird eine neue ML.NET-Umgebung erstellt, die für mehrere Objekte des Modellerstellungsworkflows verwendet werden kann. Die Klasse ähnelt dem Konzept von `DBContext` in Entity Framework.

Initialisieren Sie die `mlContext`-Variable mit einer neuen Instanz von `MLContext`, indem Sie der `Main`-Methode von *Program.cs* unterhalb des Felds `outputFolder` die folgende Zeile hinzufügen.

[!code-csharp [InitMLContext](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L24)]

## <a name="create-a-parser-to-post-process-model-outputs"></a>Erstellen eines Parsers für die Nachverarbeitung von Modellausgaben

Das Modell segmentiert ein Bild in ein `13 x 13`-Raster, in dem jede Rasterzelle `32px x 32px` groß ist. Jede Rasterzelle enthält fünf potenzielle Objektbegrenzungsrahmen. Ein Begrenzungsrahmen enthält 25 Elemente:

![Rasterbeispiel auf der linken Seite und Begrenzungsfeldbeispiel auf der rechten Seite](./media/object-detection-onnx/model-output-description.png)

- `x`: die x-Position der Mitte des Begrenzungsrahmens relativ zu der Rasterzelle, der er zugeordnet ist.
- `y`: die y-Position der Mitte des Begrenzungsrahmens relativ zu der Rasterzelle, der er zugeordnet ist.
- `w`: Die Breite des Begrenzungsrahmens.
- `h`: Die Höhe des Begrenzungsrahmens.
- `o`: Der Konfidenzwert, mit dem ein Objekt im Begrenzungsrahmen vorhanden ist (auch als Objectness Score bezeichnet).
- `p1-p20`: Klassenwahrscheinlichkeiten für jede der 20 vom Modell vorhergesagten Klassen.

Insgesamt bilden die 25 Elemente, die jeden der 5 Begrenzungsrahmen beschreiben, die 125 Elemente, die in jeder Rasterzelle enthalten sind.

Die Ausgabe, die vom vortrainierten ONNX-Modell generiert wird, ist ein float-Array der Länge `21125`, das die Elemente eines Tensors mit Dimensionen `125 x 13 x 13` darstellt. Um die vom Modell generierten Vorhersagen in einen Tensor zu transformieren, sind einige Nachverarbeitungsaufgaben erforderlich. Erstellen Sie zu diesem Zweck eine Reihe von Klassen, um die Analyse der Ausgabe zu unterstützen.

Fügen Sie Ihrem Projekt ein neues Verzeichnis hinzu, um den Satz von Parserklassen zu organisieren.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neuer Ordner** aus. Wenn der neue Ordner im Projektmappen-Explorer angezeigt wird, nennen Sie ihn „YoloParser“.

### <a name="create-bounding-boxes-and-dimensions"></a>Erstellen von Begrenzungsrahmen und Dimensionen

Die Daten, die vom Modell ausgegeben werden, enthalten Koordinaten und Dimensionen der Begrenzungsrahmen von Objekten im Bild. Erstellen Sie eine Basisklasse für Dimensionen.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Verzeichnis *YoloParser*, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.
1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *DimensionsBase.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.

    Die Datei *DimensionsBase.cs* wird im Code-Editor geöffnet. Entfernen Sie alle `using`-Anweisungen und die vorhandene Klassendefinition.

    Fügen Sie der Datei *DimensionsBase.cs* den folgenden Code für die `DimensionsBase`-Klasse hinzu:

    [!code-csharp [DimensionsBaseClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/DimensionsBase.cs#L3-L9)]

    `DimensionsBase` weist die folgenden `float`-Eigenschaften auf:

    - `X` enthält die Position des Objekts auf der X-Achse.
    - `Y` enthält die Position des Objekts auf der Y-Achse.
    - `Height` enthält die Höhe des Objekts.
    - `Width` enthält die Breite des Objekts.

Erstellen Sie nun eine Klasse für Ihre Begrenzungsrahmen.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Verzeichnis *YoloParser*, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.
1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *YoloBoundingBox.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.

    Die Datei *YoloBoundingBox.cs* wird im Code-Editor geöffnet. Fügen Sie die folgende `using`-Anweisung am Anfang der Datei *YoloBoundingBox.cs* hinzu:

    [!code-csharp [YoloBoundingBoxUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloBoundingBox.cs#L1)]

    Fügen Sie direkt oberhalb der vorhandenen Klassendefinition eine neue Klassendefinition namens `BoundingBoxDimensions` hinzu, die von der `DimensionsBase`-Klasse erbt, um die Dimensionen des entsprechenden Begrenzungsrahmens zu enthalten.

    [!code-csharp [BoundingBoxDimClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloBoundingBox.cs#L5)]

    Entfernen Sie die vorhandene `YoloBoundingBox`-Klassendefinition, und fügen Sie der Datei *YoloBoundingBox.cs* den folgenden Code für die `YoloBoundingBox`-Klasse hinzu:

    [!code-csharp [YoloBoundingBoxClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloBoundingBox.cs#L7-L21)]

    `YoloBoundingBox` weist die folgenden Eigenschaften auf:

    - `Dimensions` enthält Dimensionen des Begrenzungsrahmens.
    - `Label` enthält die Klasse des Objekts, das innerhalb des Begrenzungsrahmens erkannt wurde.
    - `Confidence` enthält die Konfidenz der Klasse.
    - `Rect` enthält die Rechteckdarstellung der Abmessungen des Begrenzungsrahmens.
    - `BoxColor` enthält die Farbe, die der jeweiligen Klasse zugeordnet ist, die zum Zeichnen des Bilds verwendet wird.

### <a name="create-the-parser"></a>Erstellen des Parsers

Da nun die Klassen für Dimensionen und Begrenzungsrahmen erstellt wurden, ist es an der Zeit, den Parser zu erstellen.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Verzeichnis *YoloParser*, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.
1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *YoloOutputParser.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.

    Die Datei *YoloOutputParser.cs* wird im Code-Editor geöffnet. Fügen Sie die folgende `using`-Anweisung am Anfang der Datei *YoloOutputParser.cs* hinzu:

    [!code-csharp [YoloParserUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L1-L4)]

    Fügen Sie innerhalb der vorhandenen `YoloOutputParser`-Klassendefinition eine geschachtelte Klasse hinzu, die die Dimensionen der einzelnen Zellen im Bild enthält. Fügen Sie den folgenden Code am Anfang der `YoloOutputParser`-Klassendefinition für die `CellDimensions`-Klasse hinzu, die von der `DimensionsBase`-Klasse erbt.

    [!code-csharp [YoloParserUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L10)]

1. Fügen Sie in der `YoloOutputParser`-Klassendefinition die folgenden Konstanten und Felder hinzu.

    [!code-csharp [ParserVarDefinitions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L12-L21)]

    - `ROW_COUNT` ist die Anzahl der Zeilen im Raster, in die das Bild aufgeteilt wird.
    - `COL_COUNT` ist die Anzahl der Spalten im Raster, in die das Bild aufgeteilt wird.
    - `CHANNEL_COUNT` ist die Gesamtzahl der Werte, die in einer Zelle des Rasters enthalten sind.
    - `BOXES_PER_CELL` ist die Anzahl der Begrenzungsrahmen in einer Zelle.
    - `BOX_INFO_FEATURE_COUNT` ist die Anzahl der in einem Feld enthaltenen Merkmale (x, y, Höhe, Breite, Konfidenz).
    - `CLASS_COUNT` ist die Anzahl der Klassenvorhersagen, die in jedem Begrenzungsrahmen enthalten sind.
    - `CELL_WIDTH` ist die Breite einer Zelle im Bildraster.
    - `CELL_HEIGHT` ist die Höhe einer Zelle im Bildraster.
    - `channelStride` ist die Anfangsposition der aktuellen Zelle im Raster.

    Wenn das Modell eine Vorhersage erstellt (auch als Bewertung bezeichnet), unterteilt es das Eingabebild `416px x 416px` in ein Raster von Zellen mit einer Größe von `13 x 13`. Jede enthaltene Zelle ist `32px x 32px` groß. In jeder Zelle sind fünf Begrenzungsrahmen enthalten, die jeweils fünf Merkmale enthalten (x, y, Breite, Höhe, Konfidenz). Außerdem enthält jeder Begrenzungsrahmen die Wahrscheinlichkeit der einzelnen Klassen (in diesem Fall ist sie 20). Daher enthält jede Zelle 125 Informationen (5 Merkmale und 20 Klassenwahrscheinlichkeiten).

Erstellen Sie eine Liste der Anker unter `channelStride` für alle 5 Begrenzungsrahmen:

[!code-csharp [ParserAnchors](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L23-L26)]

Anker sind vordefinierte Höhen- und Breitenverhältnisse für Begrenzungsrahmen. Die meisten von einem Modell erkannten Objekte oder Klassen weisen ähnliche Verhältnisse auf. Dies ist nützlich, wenn es um das Erstellen von Begrenzungsrahmen geht. Anstatt die Begrenzungsrahmen vorherzusagen, wird der Offset zu den vordefinierten Abmessungen berechnet, wodurch die für die Vorhersage des Begrenzungsrahmens erforderliche Berechnung verringert wird. Normalerweise werden diese Ankerverhältnisse basierend auf dem verwendeten Dataset berechnet. In diesem Fall können die Anker hartcodiert werden, da das Dataset bekannt ist und die Werte vorberechnet wurden.

Definieren Sie nun die Bezeichnungen oder Klassen, die vom Modell vorhergesagt werden. Dieses Modell sagt 20 Klassen voraus, was eine Teilmenge der Gesamtzahl der vom ursprünglichen YOLOv2-Modell vorhergesagten Klassen ist.

Fügen Sie die Liste der Bezeichnungen unterhalb von `anchors` hinzu.

[!code-csharp [ParserLabels](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L28-L34)]

Jeder der Klassen sind Farben zugeordnet. Weisen Sie Ihre Klassenfarben unter `labels` zu:

[!code-csharp [ParserColors](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L36-L59)]

### <a name="create-helper-functions"></a>Erstellen von Hilfsfunktionen

In der Nachverarbeitungsphase sind mehrere Schritte erforderlich. Zur Unterstützung können mehrere Hilfsmethoden eingesetzt werden.

Die folgenden Hilfsmethoden werden vom Parser verwendet:

- `Sigmoid` wendet die Sigmoidfunktion an, die eine Zahl zwischen 0 und 1 ausgibt.
- `Softmax` normalisiert einen Eingabevektor in eine Wahrscheinlichkeitsverteilung.
- `GetOffset` ordnet Elemente in der eindimensionalen Modellausgabe der entsprechenden Position in einem `125 x 13 x 13`-Tensor zu.
- `ExtractBoundingBoxes` extrahiert die Abmessungen des Begrenzungsrahmens mithilfe der `GetOffset`-Methode aus der Modellausgabe.
- `GetConfidence` extrahiert den Konfidenzwert, der angibt, wie sicher sich das Modell ist, dass ein Objekt erkannt wurde, und verwendet die `Sigmoid`-Funktion, um diesen Wert in eine Prozentangabe umzuwandeln.
- `MapBoundingBoxToCell` verwendet die Abmessungen des Begrenzungsrahmens und ordnet diese der entsprechenden Zelle im Bild zu.
- `ExtractClasses` extrahiert die Klassenvorhersagen für den Begrenzungsrahmen aus der Modellausgabe unter Verwendung der `GetOffset`-Methode und wandelt sie mithilfe der `Softmax`-Methode in eine Wahrscheinlichkeitsverteilung um.
- `GetTopResult` wählt die Klasse aus der Liste der vorhergesagten Klassen mit der höchsten Wahrscheinlichkeit aus.
- `IntersectionOverUnion` filtert sich überlappende Begrenzungsrahmen mit geringeren Wahrscheinlichkeiten.

Fügen Sie den Code für alle Hilfsmethoden unterhalb der Liste der `classColors` hinzu.

[!code-csharp [ParserHelperMethods](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L61-L151)]

Nachdem Sie alle Hilfsmethoden definiert haben, ist es an der Zeit, Sie zum Verarbeiten der Modellausgabe zu verwenden.

Erstellen Sie unter der `IntersectionOverUnion`-Methode die `ParseOutputs`-Methode, um die vom Modell generierte Ausgabe zu verarbeiten.

```csharp
public IList<YoloBoundingBox> ParseOutputs(float[] yoloModelOutputs, float threshold = .3F)
{

}
```

Erstellen Sie eine Liste, um die Begrenzungsrahmen zu speichern, und definieren Sie Variablen in der `ParseOutputs`-Methode.

[!code-csharp [BBoxList](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L155)]

Jedes Bild wird in ein Raster von `13 x 13`-Zellen aufgeteilt. Jede Zelle enthält fünf Begrenzungsrahmen. Fügen Sie unterhalb der Variablen `boxes` Code hinzu, um alle Rahmen jeder Zelle zu verarbeiten.

```csharp
for (int row = 0; row < ROW_COUNT; row++)
{
    for (int column = 0; column < COL_COUNT; column++)
    {
        for (int box = 0; box < BOXES_PER_CELL; box++)
        {

        }
    }
}
```

Berechnen Sie in der innersten Schleife die Anfangsposition des aktuellen Rahmens innerhalb der eindimensionalen Modellausgabe.

[!code-csharp [ChannelDef](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L163)]

Verwenden Sie direkt darunter die `ExtractBoundingBoxDimensions`-Methode, um die Abmessungen des aktuellen Begrenzungsrahmens abzurufen.

[!code-csharp [GetBBoxDims](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L165)]

Verwenden Sie dann die `GetConfidence`-Methode, um die Konfidenz für den aktuellen Begrenzungsrahmen abzurufen.

[!code-csharp [GetConfidence](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L167)]

Verwenden Sie anschließend die `MapBoundingBoxToCell`-Methode, um der aktuellen Zelle, die verarbeitet wird, den aktuellen Begrenzungsrahmen zuzuordnen.

[!code-csharp [MapBoundingBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L169)]

Überprüfen Sie vor der weiteren Verarbeitung, ob Ihr Konfidenzwert größer als der angegebene Schwellenwert ist. Wenn dies nicht der Fall ist, verarbeiten Sie den nächsten Begrenzungsrahmen.

[!code-csharp [CheckThreshold1](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L171-L172)]

Setzen Sie andernfalls die Verarbeitung der Ausgabe fort. Der nächste Schritt besteht darin, die Wahrscheinlichkeitsverteilung der vorhergesagten Klassen für den aktuellen Begrenzungsrahmen mithilfe der `ExtractClasses`-Methode abzurufen.

[!code-csharp [ExtractClasses](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L174)]

Verwenden Sie dann die `GetTopResult`-Methode, um den Wert und den Index der Klasse mit der höchsten Wahrscheinlichkeit für den aktuellen Rahmen abzurufen, und berechnen Sie die Bewertung.

[!code-csharp [GetTopResult](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L176-L177)]

Verwenden Sie `topScore`, um erneut nur die Begrenzungsrahmen beizubehalten, die über dem angegebenen Schwellenwert liegen.

[!code-csharp [CheckThreshold2](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L179-L180)]

Wenn der aktuelle Begrenzungsrahmen den Schwellenwert überschreitet, erstellen Sie ein neues `BoundingBox`-Objekt, und fügen Sie es der `boxes`-Liste hinzu.

[!code-csharp [AddBBoxToList](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L182-L194)]

Nachdem alle Zellen im Bild verarbeitet wurden, geben Sie die `boxes`-Liste zurück. Fügen Sie die folgende Rückgabeanweisung unterhalb der äußersten for-Schleife in der `ParseOutputs`-Methode hinzu.

[!code-csharp [ReturnBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L198)]

### <a name="filter-overlapping-boxes"></a>Filtern sich überlappender Rahmen

Nachdem nun alle Begrenzungsrahmen mit einem hohen Konfidenzwert aus der Modellausgabe extrahiert wurden, muss eine zusätzliche Filterung durchgeführt werden, um sich überlappende Bilder zu entfernen. Fügen Sie unter der `ParseOutputs`-Methode eine Methode namens `FilterBoundingBoxes` hinzu:

```csharp
public IList<YoloBoundingBox> FilterBoundingBoxes(IList<YoloBoundingBox> boxes, int limit, float threshold)
{

}
```

Erstellen Sie innerhalb der `FilterBoundingBoxes`-Methode zunächst ein Array in der Größe der erkannten Rahmen, und markieren Sie alle Slots als aktiv oder bereit zur Verarbeitung.

[!code-csharp [InitActiveSlots](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L203-L207)]

Sortieren Sie die Liste mit den Begrenzungsrahmen dann in absteigender Reihenfolge basierend auf dem Konfidenzwert.

[!code-csharp [SortBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L209-L211)]

Erstellen Sie anschließend eine Liste, in der die gefilterten Ergebnisse gespeichert werden.

[!code-csharp [InitFilterResult](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L213)]

Beginnen Sie mit der Verarbeitung der einzelnen Begrenzungsrahmen, indem Sie die einzelnen Begrenzungsrahmen durchlaufen.

```csharp
for (int i = 0; i < boxes.Count; i++)
{

}
```

Überprüfen Sie in dieser for-Schleife, ob der aktuelle Begrenzungsrahmen verarbeitet werden kann.

```csharp
if (isActiveBoxes[i])
{

}
```

Wenn dies der Fall ist, fügen Sie den Begrenzungsrahmen der Ergebnisliste hinzu. Wenn die Ergebnisse den angegebenen Grenzwert für die zu extrahierenden Rahmen überschreiten, unterbrechen Sie die Schleife. Fügen Sie den folgenden Code in der if-Anweisung hinzu.

[!code-csharp [AddFirstBBoxToResults](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L219-L223)]

Untersuchen Sie andernfalls die angrenzenden Begrenzungsrahmen. Fügen Sie unter der Überprüfung der Rahmengrenze den folgenden Code hinzu.

```csharp
for (var j = i + 1; j < boxes.Count; j++)
{

}
```

Wenn der benachbarte Rahmen aktiv oder bereit zur Verarbeitung ist, verwenden Sie wie beim ersten Rahmen die `IntersectionOverUnion`-Methode, um zu überprüfen, ob der erste Rahmen und der zweite Rahmen den angegebenen Schwellenwert überschreiten. Fügen Sie der innersten for-Schleife den folgenden Code hinzu.

[!code-csharp [IOUBBox](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L227-L239)]

Überprüfen Sie außerhalb der inneren for-Schleife, die angrenzende Begrenzungsrahmen überprüft, ob noch verbleibende Begrenzungsrahmen verarbeitet werden müssen. Wenn dies nicht der Fall ist, unterbrechen Sie die äußere for-Schleife.

[!code-csharp [CheckActiveSlots](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L242-L243)]

Geben Sie schließlich außerhalb der anfänglichen for-Schleife der `FilterBoundingBoxes`-Methode die Ergebnisse zurück:

[!code-csharp [ReturnFilteredBBox](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L246)]

Großartig! Nun ist es an der Zeit, diesen Code zusammen mit dem Modell für die Bewertung zu verwenden.

## <a name="use-the-model-for-scoring"></a>Verwenden des Modells für die Bewertung

Genau wie bei der Nachverarbeitung gibt sind einige Bewertungsschritte erforderlich. Fügen Sie dem Projekt zur Unterstützung dieser Aufgaben eine Klasse hinzu, die die Bewertungslogik enthält.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.
1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *OnnxModelScorer.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.

    Die Datei *OnnxModelScorer.cs* wird im Code-Editor geöffnet. Fügen Sie die folgende `using`-Anweisung am Anfang der Datei *OnnxModelScorer.cs* hinzu:

    [!code-csharp [ScorerUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L1-L7)]

    Fügen Sie innerhalb der `OnnxModelScorer`-Klassendefinition die folgenden Variablen hinzu.

    [!code-csharp [InitScorerVars](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L13-L17)]

    Erstellen Sie direkt darunter einen Konstruktor für die `OnnxModelScorer`-Klasse, die die zuvor definierten Variablen initialisiert.

    [!code-csharp [ScorerCtor](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L19-L24)]

    Nachdem Sie den Konstruktor erstellt haben, definieren Sie einige Strukturen, die Variablen enthalten, die sich auf das Bild und die Modelleinstellungen beziehen. Erstellen Sie eine Struktur namens `ImageNetSettings`, die die Höhe und Breite enthält, die als Eingabe für das Modell erwartet wird.

    [!code-csharp [ImageNetSettingStruct](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L26-L30)]

    Erstellen Sie anschließend eine weitere Struktur namens `TinyYoloModelSettings`, die die Namen der Eingabe- und Ausgabeschichten des Modells enthält. Um den Namen der Eingabe- und Ausgabeschichten des Modells zu visualisieren, können Sie ein Tool wie [Netron](https://github.com/lutzroeder/netron) verwenden.

    [!code-csharp [YoloSettingsStruct](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L32-L43)]

    Erstellen Sie nun den ersten Satz von Methoden, die für die Bewertung verwendet werden. Erstellen Sie die `LoadModel`-Methode in der `OnnxModelScorer`-Klasse.

    ```csharp
    private ITransformer LoadModel(string modelLocation)
    {

    }
    ```

    Fügen Sie in der `LoadModel`-Methode den folgenden Code für die Protokollierung hinzu.

    [!code-csharp [LoadModelLog](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L47-L49)]

    ML.NET-Pipelines müssen das Datenschema kennen, das verwendet werden soll, wenn die Methode [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit*) aufgerufen wird. In diesem Fall wird ein Prozess ähnlich dem Training verwendet. Da jedoch kein tatsächliches Training stattfindet, ist es akzeptabel, eine leere [`IDataView`](xref:Microsoft.ML.IDataView) zu verwenden. Erstellen Sie eine neue [`IDataView`](xref:Microsoft.ML.IDataView) für die Pipeline aus einer leeren Liste.

    [!code-csharp [LoadEmptyIDV](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L52)]

    Definieren Sie darunter die Pipeline. Die Pipeline besteht aus vier Transformationen.

    - [`LoadImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages*) lädt das Bild als Bitmap.
    - [`ResizeImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.ResizeImages*) wandelt das Bild um die angegebene Größe um (in diesem Fall `416 x 416`).
    - [`ExtractPixels`](xref:Microsoft.ML.ImageEstimatorsCatalog.ExtractPixels*) ändert die Pixeldarstellung des Bilds aus einer Bitmap in einen numerischen Vektor.
    - [`ApplyOnnxModel`](xref:Microsoft.ML.OnnxCatalog.ApplyOnnxModel*) lädt das ONNX-Modell und verwendet es, um die bereitgestellten Daten zu bewerten.

    Definieren Sie die Pipeline in der `LoadModel`-Methode unter der `data`-Variablen.

    [!code-csharp [ScoringPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L55-L58)]

    Jetzt ist es an der Zeit, das Modell für die Bewertung zu instanziieren. Rufen Sie die [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit*)-Methode für die Pipeline auf, und geben Sie sie zur weiteren Verarbeitung zurück.

    [!code-csharp [FitReturnModel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L61-L63)]

Nachdem das Modell geladen wurde, kann es verwendet werden, um Vorhersagen zu treffen. Um diesen Prozess zu ermöglichen, erstellen Sie eine Methode namens `PredictDataUsingModel` unter der `LoadModel`-Methode.

```csharp
private IEnumerable<float[]> PredictDataUsingModel(IDataView testData, ITransformer model)
{

}
```

Fügen Sie in `PredictDataUsingModel` den folgenden Code für die Protokollierung hinzu.

[!code-csharp [PredictDataLog](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L68-L71)]

Verwenden Sie dann die [`Transform`](xref:Microsoft.ML.ITransformer.Transform*)-Methode, um die Daten zu bewerten.

[!code-csharp [ScoreImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L73)]

Extrahieren Sie die vorhergesagten Wahrscheinlichkeiten, und geben Sie sie zur weiteren Verarbeitung zurück.

[!code-csharp [ReturnModelOutput](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L75-L77)]

Nachdem Sie nun beide Schritte eingerichtet haben, kombinieren Sie sie in einer einzigen Methode. Fügen Sie unter der `PredictDataUsingModel`-Methode eine Methode namens `Score` hinzu.

[!code-csharp [ScoreMethod](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L80-L85)]

Fast geschafft! Jetzt ist es an der Zeit, alles zusammen einzusetzen.

## <a name="detect-objects"></a>Erkennen von Objekten

Nachdem das gesamte Setup nun vollständig ist, ist es an der Zeit, einige Objekte zu erkennen. Fügen Sie zu Beginn Verweise auf den Scorer und den Parser zur Klasse *Program.cs* hinzu.

[!code-csharp [ReferenceScorerParser](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L8-L9)]

### <a name="score-and-parse-model-outputs"></a>Bewerten und Analysieren von Modellausgaben

Fügen Sie innerhalb der `Main`-Methode der Klasse *Program.cs* eine try-catch-Anweisung hinzu.

```csharp
try
{

}
catch (Exception ex)
{
    Console.WriteLine(ex.ToString());
}
```

Beginnen Sie innerhalb des `try`-Blocks mit der Implementierung der Objekterkennungslogik. Laden Sie die Daten zunächst in eine [`IDataView`](xref:Microsoft.ML.IDataView).

[!code-csharp [LoadData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L29-L30)]

Erstellen Sie dann eine Instanz von `OnnxModelScorer`, und verwenden Sie diese zum Bewerten der geladenen Daten.

[!code-csharp [ScoreData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L33-L36)]

Jetzt muss der Nachverarbeitungsschritt erfolgen. Erstellen Sie eine Instanz von `YoloOutputParser`, und verwenden Sie diese, um die Modellausgabe zu verarbeiten.

[!code-csharp [ParsePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L39-L44)]

Nachdem die Modellausgabe verarbeitet wurde, können die Begrenzungsrahmen auf den Bildern gezeichnet werden.

### <a name="visualize-predictions"></a>Visualisieren von Vorhersagen

Nachdem das Modell die Bilder bewertet hat und die Ausgaben verarbeitet wurden, müssen die Begrenzungsrahmen auf das Bild gezeichnet werden. Fügen Sie zu diesem Zweck eine Methode namens `DrawBoundingBox` unter der Methode `GetAbsolutePath` der Datei *Program.cs* hinzu.

```csharp
private static void DrawBoundingBox(string inputImageLocation, string outputImageLocation, string imageName, IList<YoloBoundingBox> filteredBoundingBoxes)
{

}
```

Laden Sie zuerst das Bild, und rufen Sie die Abmessungen für die Höhe und Breite in der `DrawBoundingBox`-Methode ab.

[!code-csharp [LoadImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L78-L81)]

Erstellen Sie dann eine for-each-Schleife, um über jeden der vom Modell erfassten Begrenzungsrahmen zu iterieren.

```csharp
foreach (var box in filteredBoundingBoxes)
{

}
```

In der for-each-Schleife rufen Sie die Abmessungen des Begrenzungsrahmens ab.

[!code-csharp [GetBBoxDimensions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L86-L89)]

Da die Abmessungen des Begrenzungsrahmens der Modelleingabe von `416 x 416` entsprechen, skalieren Sie die Abmessungen des Begrenzungsrahmens so, dass sie der tatsächlichen Größe des Bilds entsprechen.

[!code-csharp [ScaleImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L92-L95)]

Definieren Sie dann eine Vorlage für Text, der oberhalb jedes Begrenzungsrahmens angezeigt wird. Der Text enthält die Klasse des Objekts innerhalb des entsprechenden Begrenzungsrahmens sowie die Konfidenz.

[!code-csharp [DefineBBoxText](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L98)]

Um auf dem Bild zu zeichnen, konvertieren Sie es in ein [`Graphics`](xref:System.Drawing.Graphics)-Objekt.

```csharp
using (Graphics thumbnailGraphic = Graphics.FromImage(image))
{

}
```

Optimieren Sie innerhalb des `using`-Codeblocks die [`Graphics`](xref:System.Drawing.Graphics)-Objekteinstellungen der Grafik.

[!code-csharp [TuneGraphicSettings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L102-L104)]

Legen Sie darunter die Schriftart- und Farboptionen für den Text und den Begrenzungsrahmen fest.

[!code-csharp [SetColorOptions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L106-L114)]

Erstellen und füllen Sie ein Rechteck oberhalb des Begrenzungsrahmens mithilfe der [`FillRectangle`](xref:System.Drawing.Graphics.FillRectangle*)-Methode, damit es den Text enthält. Dies hilft dabei, den Text vom Hintergrund abzuheben und die Lesbarkeit zu verbessern.

[!code-csharp [DrawTextBackground](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L117)]

Zeichnen Sie dann den Text und den Begrenzungsrahmen auf dem Bild mithilfe der Methoden [`DrawString`](xref:System.Drawing.Graphics.DrawString*) und [`DrawRectangle`](xref:System.Drawing.Graphics.DrawRectangle*).

[!code-csharp [DrawClassAndBBox](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L118-L121)]

Fügen Sie außerhalb der for-each-Schleife Code hinzu, um die Bilder im `outputDirectory` zu speichern.

[!code-csharp [SaveImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L125-L130)]

Wenn Sie zusätzliches Feedback dazu erhalten möchten, ob die Anwendung Vorhersagen wie erwartet zur Laufzeit trifft, fügen Sie eine Methode namens `LogDetectedObjects` unterhalb der Methode `DrawBoundingBox` zu der Datei *Program.cs* hinzu, um die erkannten Objekte an die Konsole auszugeben.

[!code-csharp [LogOutputs](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L133-L143)]

Nun, da Sie über Hilfsmethoden zum Erstellen von visuellem Feedback aus den Vorhersagen verfügen, sollten Sie eine For-Schleife hinzufügen, um die einzelnen bewerteten Bilder zu durchlaufen.

```csharp
for (var i = 0; i < images.Count(); i++)
{

}
```

Rufen Sie in der for-Schleife den Namen der Bilddatei und die Begrenzungsrahmen ab, die ihr zugeordnet sind.

[!code-csharp [GetImageFileName](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L49-L50)]

Verwenden Sie darunter die `DrawBoundingBox`-Methode, um die Begrenzungsrahmen auf dem Bild zu zeichnen.

[!code-csharp [DrawBBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L52)]

Verwenden Sie schließlich die Methode `LogDetectedObjects`, um Vorhersagen an die Konsole auszugeben.

[!code-csharp [LogPredictionsOutput](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L54)]

Fügen Sie nach der try-catch-Anweisung zusätzliche Logik hinzu, um anzugeben, dass die Ausführung des Prozesses abgeschlossen wurde.

[!code-csharp [EndProcessLog](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L62-L63)]

Das ist alles!

## <a name="results"></a>Ergebnisse

Nachdem Sie die vorherigen Schritte durchgeführt haben, führen Sie die Konsolen-App aus (STRG+F5). Ihre Ergebnisse sollten der folgenden Ausgabe ähneln. Möglicherweise werden Warnungen oder Verarbeitungsnachrichten angezeigt. Diese wurden jedoch aus Gründen der Übersichtlichkeit aus den folgenden Ergebnissen entfernt.

```console
=====Identify the objects in the images=====

.....The objects in the image image1.jpg are detected as below....
car and its Confidence score: 0.9697262
car and its Confidence score: 0.6674225
person and its Confidence score: 0.5226039
car and its Confidence score: 0.5224892
car and its Confidence score: 0.4675332

.....The objects in the image image2.jpg are detected as below....
cat and its Confidence score: 0.6461141
cat and its Confidence score: 0.6400049

.....The objects in the image image3.jpg are detected as below....
chair and its Confidence score: 0.840578
chair and its Confidence score: 0.796363
diningtable and its Confidence score: 0.6056048
diningtable and its Confidence score: 0.3737402

.....The objects in the image image4.jpg are detected as below....
dog and its Confidence score: 0.7608147
person and its Confidence score: 0.6321323
dog and its Confidence score: 0.5967442
person and its Confidence score: 0.5730394
person and its Confidence score: 0.5551759

========= End of Process..Hit any Key ========
```

Navigieren Sie zum Verzeichnis `assets/images/output/`, um die Bilder mit Begrenzungsrahmen anzuzeigen. Unten sehen Sie ein Beispiel aus einem der verarbeiteten Bilder.

![Beispiel für ein verarbeitetes Bild eines Esszimmers](./media/object-detection-onnx/dinning-room-table-chairs.png)

Herzlichen Glückwunsch! Sie haben nun durch Wiederverwenden eines vortrainierten `ONNX`-Modells in ML.NET erfolgreich ein Machine Learning-Modell für die Objekterkennung erstellt.

Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx).

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> - Das Problem verstehen
> - Erfahren Sie, was ONNX ist und wie ONNX mit ML.NET funktioniert.
> - Verstehen des Modells
> - Wiederverwenden des vortrainierten Modells
> - Erkennen von Objekten mit einem geladenen Modell

Sehen Sie sich im GitHub-Repository für Machine Learning-Beispiele nach einem Beispiel für erweiterte Objekterkennung um, damit Sie es untersuchen können.
> [!div class="nextstepaction"]
> [dotnet/machinelearning-samples-GitHub-Repository](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx)
