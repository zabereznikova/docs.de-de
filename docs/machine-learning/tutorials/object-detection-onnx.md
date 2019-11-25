---
title: 'Tutorial: Erkennen von Objekten mithilfe von Deep Learning mit ONNX und ML.NET'
description: In diesem Tutorial wird veranschaulicht, wie Sie ein vortrainiertes ONNX Deep Learning-Modell in ML.NET verwenden, um Objekte in Bildern zu erkennen.
author: luisquintanilla
ms.author: luquinta
ms.date: 08/27/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 1364b6a1cf6d424975828185a50175b2763c6516
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73420033"
---
# <a name="tutorial-detect-objects-using-onnx-in-mlnet"></a><span data-ttu-id="154d8-103">Tutorial: Erkennen von Objekten mithilfe von ONNX in ML.NET</span><span class="sxs-lookup"><span data-stu-id="154d8-103">Tutorial: Detect objects using ONNX in ML.NET</span></span>

<span data-ttu-id="154d8-104">Erfahren Sie, wie Sie ein vortrainiertes ONNX-Modell in ML.NET verwenden, um Objekte in Bildern zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="154d8-104">Learn how to use a pre-trained ONNX model in ML.NET to detect objects in images.</span></span>

<span data-ttu-id="154d8-105">Das von Grund auf neue Trainieren eines Objekterkennungsmodells erfordert das Festlegen von Millionen von Parametern, zahlreiche bezeichnete Trainingsdaten und eine große Menge an Computeressourcen (Hunderte von GPU-Stunden).</span><span class="sxs-lookup"><span data-stu-id="154d8-105">Training an object detection model from scratch requires setting millions of parameters, a large amount of labeled training data and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="154d8-106">Die Verwendung eines vortrainierten Modells ermöglicht es Ihnen, den Trainingsprozess zu verkürzen.</span><span class="sxs-lookup"><span data-stu-id="154d8-106">Using a pre-trained model allows you to shortcut the training process.</span></span>

<span data-ttu-id="154d8-107">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="154d8-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="154d8-108">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="154d8-108">Understand the problem</span></span>
> - <span data-ttu-id="154d8-109">Erfahren Sie, was ONNX ist und wie ONNX mit ML.NET funktioniert.</span><span class="sxs-lookup"><span data-stu-id="154d8-109">Learn what ONNX is and how it works with ML.NET</span></span>
> - <span data-ttu-id="154d8-110">Verstehen des Modells</span><span class="sxs-lookup"><span data-stu-id="154d8-110">Understand the model</span></span>
> - <span data-ttu-id="154d8-111">Wiederverwenden des vortrainierten Modells</span><span class="sxs-lookup"><span data-stu-id="154d8-111">Reuse the pre-trained model</span></span>
> - <span data-ttu-id="154d8-112">Erkennen von Objekten mit einem geladenen Modell</span><span class="sxs-lookup"><span data-stu-id="154d8-112">Detect objects with a loaded model</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="154d8-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="154d8-113">Pre-requisites</span></span>

- <span data-ttu-id="154d8-114">[Visual Studio 2017 Version 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="154d8-114">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- [<span data-ttu-id="154d8-115">Microsoft.ML NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="154d8-115">Microsoft.ML NuGet Package</span></span>](https://www.nuget.org/packages/Microsoft.ML/)
- [<span data-ttu-id="154d8-116">Microsoft.ML.ImageAnalytics NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="154d8-116">Microsoft.ML.ImageAnalytics NuGet Package</span></span>](https://www.nuget.org/packages/Microsoft.ML.ImageAnalytics/)
- [<span data-ttu-id="154d8-117">Microsoft.ML.OnnxTransformer NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="154d8-117">Microsoft.ML.OnnxTransformer NuGet Package</span></span>](https://www.nuget.org/packages/Microsoft.ML.OnnxTransformer/)
- [<span data-ttu-id="154d8-118">Vortrainiertes Tiny YOLOv2-Modell</span><span class="sxs-lookup"><span data-stu-id="154d8-118">Tiny YOLOv2 pre-trained model</span></span>](https://github.com/onnx/models/tree/master/vision/object_detection_segmentation/tiny_yolov2)
- <span data-ttu-id="154d8-119">[Netron](https://github.com/lutzroeder/netron) (optional)</span><span class="sxs-lookup"><span data-stu-id="154d8-119">[Netron](https://github.com/lutzroeder/netron) (optional)</span></span>

## <a name="onnx-object-detection-sample-overview"></a><span data-ttu-id="154d8-120">ONNX-Objekterkennungsbeispiel: Übersicht</span><span class="sxs-lookup"><span data-stu-id="154d8-120">ONNX object detection sample overview</span></span>

<span data-ttu-id="154d8-121">Dieses Beispiel erstellt eine .NET Core-Konsolenanwendung, die Objekte in einem Bild mithilfe eines vortrainierten Deep Learning ONNX-Modells erkennt.</span><span class="sxs-lookup"><span data-stu-id="154d8-121">This sample creates a .NET core console application that detects objects within an image using a pre-trained deep learning ONNX model.</span></span> <span data-ttu-id="154d8-122">Den Code für dieses Beispiel finden Sie im [dotnet/machinelearning-Beispielrepository](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="154d8-122">The code for this sample can be found on the [dotnet/machinelearning-samples repository](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx) on GitHub.</span></span>

## <a name="what-is-object-detection"></a><span data-ttu-id="154d8-123">Was ist Objekterkennung?</span><span class="sxs-lookup"><span data-stu-id="154d8-123">What is object detection?</span></span>

<span data-ttu-id="154d8-124">Objekterkennung ist ein Problem des maschinellen Sehens.</span><span class="sxs-lookup"><span data-stu-id="154d8-124">Object detection is a computer vision problem.</span></span> <span data-ttu-id="154d8-125">Obwohl die Objekterkennung eng mit der Bildklassifizierung verwandt ist, führt sie die Bildklassifizierung auf einer detaillierteren Ebene durch.</span><span class="sxs-lookup"><span data-stu-id="154d8-125">While closely related to image classification, object detection performs image classification at a more granular scale.</span></span> <span data-ttu-id="154d8-126">Die Objekterkennung ermittelt _und_ kategorisiert Entitäten in Bildern.</span><span class="sxs-lookup"><span data-stu-id="154d8-126">Object detection both locates _and_ categorizes entities within images.</span></span> <span data-ttu-id="154d8-127">Verwenden Sie die Objekterkennung, wenn Bilder mehrere Objekte verschiedener Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="154d8-127">Use object detection when images contain multiple objects of different types.</span></span>

![Screenshots zum Vergleich der Bildklassifizierung mit der Objektklassifizierung](./media/object-detection-onnx/img-classification-obj-detection.png)

<span data-ttu-id="154d8-129">Einige Anwendungsfälle für die Objekterkennung sind:</span><span class="sxs-lookup"><span data-stu-id="154d8-129">Some use cases for object detection include:</span></span>

- <span data-ttu-id="154d8-130">Autonomes Fahren</span><span class="sxs-lookup"><span data-stu-id="154d8-130">Self-Driving Cars</span></span>
- <span data-ttu-id="154d8-131">Robotik</span><span class="sxs-lookup"><span data-stu-id="154d8-131">Robotics</span></span>
- <span data-ttu-id="154d8-132">Gesichtserfassung</span><span class="sxs-lookup"><span data-stu-id="154d8-132">Face Detection</span></span>
- <span data-ttu-id="154d8-133">Arbeitsplatzsicherheit</span><span class="sxs-lookup"><span data-stu-id="154d8-133">Workplace Safety</span></span>
- <span data-ttu-id="154d8-134">Objektzählung</span><span class="sxs-lookup"><span data-stu-id="154d8-134">Object Counting</span></span>
- <span data-ttu-id="154d8-135">Aktivitätserkennung</span><span class="sxs-lookup"><span data-stu-id="154d8-135">Activity Recognition</span></span>

## <a name="select-a-deep-learning-model"></a><span data-ttu-id="154d8-136">Auswählen eines Deep Learning-Modells</span><span class="sxs-lookup"><span data-stu-id="154d8-136">Select a deep learning model</span></span>

<span data-ttu-id="154d8-137">Deep Learning ist eine Teilmenge von Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="154d8-137">Deep learning is a subset of machine learning.</span></span> <span data-ttu-id="154d8-138">Zum Trainieren von Deep Learning-Modellen sind große Mengen von Daten erforderlich.</span><span class="sxs-lookup"><span data-stu-id="154d8-138">To train deep learning models, large quantities of data are required.</span></span> <span data-ttu-id="154d8-139">Muster in den Daten werden durch eine Reihe von Schichten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="154d8-139">Patterns in the data are represented by a series of layers.</span></span> <span data-ttu-id="154d8-140">Die Beziehungen in den Daten werden als Verbindungen zwischen den Schichten mit Gewichtungen codiert.</span><span class="sxs-lookup"><span data-stu-id="154d8-140">The relationships in the data are encoded as connections between the layers containing weights.</span></span> <span data-ttu-id="154d8-141">Je höher die Gewichtung, desto stärker die Beziehung.</span><span class="sxs-lookup"><span data-stu-id="154d8-141">The higher the weight, the stronger the relationship.</span></span> <span data-ttu-id="154d8-142">Zusammen werden diese Schichten und Verbindungen als künstliche neuronale Netze bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="154d8-142">Collectively, this series of layers and connections are known as artificial neural networks.</span></span> <span data-ttu-id="154d8-143">Je mehr Schichten in einem Netzwerk vorhanden sind, desto „tiefer“ ist es, was es zu einem Deep Neural Network macht.</span><span class="sxs-lookup"><span data-stu-id="154d8-143">The more layers in a network, the "deeper" it is, making it a deep neural network.</span></span>

<span data-ttu-id="154d8-144">Es gibt verschiedene Arten von neuronalen Netzen, wobei die häufigsten MLP (Multi-Layered Perceptron), CNN (Convolutional Neural Network) und RNN (Recurrent Neural Network) sind.</span><span class="sxs-lookup"><span data-stu-id="154d8-144">There are different types of neural networks, the most common being Multi-Layered Perceptron (MLP), Convolutional Neural Network (CNN) and Recurrent Neural Network (RNN).</span></span> <span data-ttu-id="154d8-145">Das einfachste neuronale Netz ist MLP, das eine Reihe von Eingaben einem Satz von Ausgaben zuordnet.</span><span class="sxs-lookup"><span data-stu-id="154d8-145">The most basic is the MLP, which maps a set of inputs to a set of outputs.</span></span> <span data-ttu-id="154d8-146">Dieses neuronale Netz eignet sich gut, wenn die Daten nicht über eine räumliche oder zeitliche Komponente verfügen.</span><span class="sxs-lookup"><span data-stu-id="154d8-146">This neural network is good when the data does not have a spatial or time component.</span></span> <span data-ttu-id="154d8-147">Das CNN nutzt Faltungsschichten, um die in den Daten enthaltenen räumlichen Informationen zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="154d8-147">The CNN makes use of convolutional layers to process spatial information contained in the data.</span></span> <span data-ttu-id="154d8-148">Ein guter Anwendungsfall für CNNs ist die Bildverarbeitung, um das Vorhandensein eines Merkmals in einer Region eines Bilds zu erkennen (Beispiel: befindet sich eine Nase in der Mitte eines Bilds?).</span><span class="sxs-lookup"><span data-stu-id="154d8-148">A good use case for CNNs is image processing to detect the presence of a feature in a region of an image (for example, is there a nose in the center of an image?).</span></span> <span data-ttu-id="154d8-149">RNNs schließlich ermöglichen die Verwendung von Persistenz von Zustand oder Speicher als Eingabe.</span><span class="sxs-lookup"><span data-stu-id="154d8-149">Finally, RNNs allow for the persistence of state or memory to be used as input.</span></span> <span data-ttu-id="154d8-150">RNNs werden für die Zeitreihenanalyse verwendet, bei der die sequenzielle Reihenfolge und der Kontext der Ereignisse wichtig sind.</span><span class="sxs-lookup"><span data-stu-id="154d8-150">RNNs are used for time-series analysis, where the sequential ordering and context of events is important.</span></span>

### <a name="understand-the-model"></a><span data-ttu-id="154d8-151">Verstehen des Modells</span><span class="sxs-lookup"><span data-stu-id="154d8-151">Understand the model</span></span>

<span data-ttu-id="154d8-152">Objekterkennung ist eine Bildverarbeitungsaufgabe.</span><span class="sxs-lookup"><span data-stu-id="154d8-152">Object detection is an image processing task.</span></span> <span data-ttu-id="154d8-153">Daher sind die meisten Deep Learning-Modelle, die zur Lösung dieses Problems trainiert werden, CNNs.</span><span class="sxs-lookup"><span data-stu-id="154d8-153">Therefore, most deep learning models trained to solve this problem are CNNs.</span></span> <span data-ttu-id="154d8-154">Das in diesem Tutorial verwendete Modell ist das Tiny YOLOv2-Modell, eine kompaktere Version des YOLOv2-Modells, das im folgenden Dokument beschrieben wird: [„YOLO9000: Better, Faster, Stronger“ von Redmon und Fadhari](https://arxiv.org/pdf/1612.08242.pdf).</span><span class="sxs-lookup"><span data-stu-id="154d8-154">The model used in this tutorial is the Tiny YOLOv2 model, a more compact version of the YOLOv2 model described in the paper: ["YOLO9000: Better, Faster, Stronger" by Redmon and Fadhari](https://arxiv.org/pdf/1612.08242.pdf).</span></span> <span data-ttu-id="154d8-155">Tiny YOLOv2 wird mit dem Pascal VOC-Dataset trainiert und besteht aus 15 Schichten, die 20 verschiedene Klassen von Objekten vorhersagen können.</span><span class="sxs-lookup"><span data-stu-id="154d8-155">Tiny YOLOv2 is trained on the Pascal VOC dataset and is made up of 15 layers that can predict 20 different classes of objects.</span></span> <span data-ttu-id="154d8-156">Da Tiny YOLOv2 eine komprimierte Version des ursprünglichen YOLOv2-Modells ist, wird ein Kompromiss zwischen Geschwindigkeit und Genauigkeit erzielt.</span><span class="sxs-lookup"><span data-stu-id="154d8-156">Because Tiny YOLOv2 is a condensed version of the original YOLOv2 model, a tradeoff is made between speed and accuracy.</span></span> <span data-ttu-id="154d8-157">Die verschiedenen Schichten, die das Modell bilden, können mithilfe von Tools wie etwa Netron visualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="154d8-157">The different layers that make up the model can be visualized using tools like Netron.</span></span> <span data-ttu-id="154d8-158">Die Untersuchung des Modells würde eine Zuordnung der Verbindungen zwischen allen Schichten ergeben, aus denen sich das neuronale Netz zusammensetzt, wobei jede Schicht den Namen der Schicht zusammen mit den Dimensionen der jeweiligen Ein- bzw. Ausgabe enthalten würde.</span><span class="sxs-lookup"><span data-stu-id="154d8-158">Inspecting the model would yield a mapping of the connections between all the layers that make up the neural network, where each layer would contain the name of the layer along with the dimensions of the respective input / output.</span></span> <span data-ttu-id="154d8-159">Die Datenstrukturen, die zum Beschreiben der Eingaben und Ausgaben des Modells verwendet werden, werden als Tensoren bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="154d8-159">The data structures used to describe the inputs and outputs of the model are known as tensors.</span></span> <span data-ttu-id="154d8-160">Tensoren können als Container betrachtet werden, in denen Daten in N Dimensionen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="154d8-160">Tensors can be thought of as containers that store data in N-dimensions.</span></span> <span data-ttu-id="154d8-161">Im Fall von Tiny YOLOv2 ist der Name der Eingabeschicht `image`, und es wird ein Tensor mit den Dimensionen `3 x 416 x 416` erwartet.</span><span class="sxs-lookup"><span data-stu-id="154d8-161">In the case of Tiny YOLOv2, the name of the input layer is `image` and it expects a tensor of dimensions `3 x 416 x 416`.</span></span> <span data-ttu-id="154d8-162">Der Name der Ausgabeschicht ist `grid`, und es wird ein Tensor mit den Dimensionen `125 x 13 x 13` generiert.</span><span class="sxs-lookup"><span data-stu-id="154d8-162">The name of the output layer is `grid` and generates an output tensor of dimensions `125 x 13 x 13`.</span></span>

![Die Eingabeschicht wird in verborgene Schichten aufgeteilt und führt zur Ausgabeschicht.](./media/object-detection-onnx/netron-model-map-layers.png)

<span data-ttu-id="154d8-164">Das Yolo-Modell verwendet ein Bild mit `3(RGB) x 416px x 416px`.</span><span class="sxs-lookup"><span data-stu-id="154d8-164">The YOLO model takes an image `3(RGB) x 416px x 416px`.</span></span> <span data-ttu-id="154d8-165">Das Modell nimmt diese Eingabe an und übergibt sie durch die verschiedenen Schichten, um eine Ausgabe zu generieren.</span><span class="sxs-lookup"><span data-stu-id="154d8-165">The model takes this input and passes it through the different layers to produce an output.</span></span> <span data-ttu-id="154d8-166">Die Ausgabe teilt das Eingabebild in ein `13 x 13`-Raster auf, wobei jede Zelle im Raster aus `125` Werten besteht.</span><span class="sxs-lookup"><span data-stu-id="154d8-166">The output divides the input image into a `13 x 13` grid, with each cell in the grid consisting of `125` values.</span></span>

### <a name="what-is-an-onnx-model"></a><span data-ttu-id="154d8-167">Was ist ein ONNX-Modell?</span><span class="sxs-lookup"><span data-stu-id="154d8-167">What is an ONNX model?</span></span>

<span data-ttu-id="154d8-168">ONNX (Open Neural Network Exchange) ist ein Open-Source-Format für KI-Modelle.</span><span class="sxs-lookup"><span data-stu-id="154d8-168">The Open Neural Network Exchange (ONNX) is an open source format for AI models.</span></span> <span data-ttu-id="154d8-169">ONNX unterstützt die Interoperabilität zwischen Frameworks.</span><span class="sxs-lookup"><span data-stu-id="154d8-169">ONNX supports interoperability between frameworks.</span></span> <span data-ttu-id="154d8-170">Das bedeutet, dass Sie ein Modell in einem der vielen gängigen Machine Learning-Frameworks wie PyTorch trainieren, es in das ONNX-Format konvertieren und das ONNX-Modell in einem anderen Framework wie ML.NET verwenden können.</span><span class="sxs-lookup"><span data-stu-id="154d8-170">This means you can train a model in one of the many popular machine learning frameworks like PyTorch, convert it into ONNX format and consume the ONNX model in a different framework like ML.NET.</span></span> <span data-ttu-id="154d8-171">Weitere Informationen finden Sie auf der [ONNX-Website](https://onnx.ai/).</span><span class="sxs-lookup"><span data-stu-id="154d8-171">To learn more, visit the [ONNX website](https://onnx.ai/).</span></span>

![Diagramm der verwendeten unterstützten ONNX-Formate](./media/object-detection-onnx/onyx-supported-formats.png)

<span data-ttu-id="154d8-173">Das vortrainierte Tiny YOLOv2-Modell wird im ONNX-Format gespeichert, einer serialisierten Darstellung der Schichten und erlernten Muster dieser Schichten.</span><span class="sxs-lookup"><span data-stu-id="154d8-173">The pre-trained Tiny YOLOv2 model is stored in ONNX format, a serialized representation of the layers and learned patterns of those layers.</span></span> <span data-ttu-id="154d8-174">In ML.NET wird die Interoperabilität mit ONNX mit den NuGet-Paketen [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) und [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer) erreicht.</span><span class="sxs-lookup"><span data-stu-id="154d8-174">In ML.NET, interoperability with ONNX is achieved with the [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) and [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer) NuGet packages.</span></span> <span data-ttu-id="154d8-175">Das Paket [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) enthält eine Reihe von Transformationen, die ein Bild annehmen und in numerische Werte codieren, die als Eingabe in eine Vorhersage- oder Trainingspipeline verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="154d8-175">The [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) package contains a series of transforms that take an image and encode it into numerical values that can be used as input into a prediction or training pipeline.</span></span> <span data-ttu-id="154d8-176">Das Paket [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer) nutzt die ONNX Runtime, um ein ONNX-Modell zu laden und damit Vorhersagen basierend auf bereitgestellten Eingaben zu treffen.</span><span class="sxs-lookup"><span data-stu-id="154d8-176">The [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer) package leverages the ONNX Runtime to load an ONNX model and use it to make predictions based on input provided.</span></span>

![Datenfluss der ONNX-Datei in die ONNX-Runtime](./media/object-detection-onnx/onnx-ml-net-integration.png)

## <a name="set-up-the-net-core-project"></a><span data-ttu-id="154d8-178">Einrichten des .NET Core-Projekts</span><span class="sxs-lookup"><span data-stu-id="154d8-178">Set up the .NET Core project</span></span>

<span data-ttu-id="154d8-179">Da Sie nun ein allgemeines Verständnis davon haben, was ONNX ist und wie Tiny YOLOv2 funktioniert, ist es an der Zeit, die Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="154d8-179">Now that you have a general understanding of what ONNX is and how Tiny YOLOv2 works, it's time to build the application.</span></span>

### <a name="create-a-console-application"></a><span data-ttu-id="154d8-180">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="154d8-180">Create a console application</span></span>

1. <span data-ttu-id="154d8-181">Erstellen Sie eine **.NET Core-Konsolenanwendung** mit dem Namen „ObjectDetection“.</span><span class="sxs-lookup"><span data-stu-id="154d8-181">Create a **.NET Core Console Application** called "ObjectDetection".</span></span>

1. <span data-ttu-id="154d8-182">Installieren des **Microsoft.ML NuGet-Pakets**:</span><span class="sxs-lookup"><span data-stu-id="154d8-182">Install the **Microsoft.ML NuGet Package**:</span></span>

    - <span data-ttu-id="154d8-183">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="154d8-183">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span>
    - <span data-ttu-id="154d8-184">Wählen Sie „nuget.org“ als Paketquelle aus, wählen Sie die Registerkarte „Durchsuchen“ aus, und suchen Sie nach **Microsoft.ML**.</span><span class="sxs-lookup"><span data-stu-id="154d8-184">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**.</span></span>
    - <span data-ttu-id="154d8-185">Wählen Sie die Schaltfläche **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="154d8-185">Select the **Install** button.</span></span>
    - <span data-ttu-id="154d8-186">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="154d8-186">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>
    - <span data-ttu-id="154d8-187">Wiederholen Sie diese Schritte für **Microsoft.ML.ImageAnalytics** und **Microsoft.ML.OnnxTransformer**.</span><span class="sxs-lookup"><span data-stu-id="154d8-187">Repeat these steps for **Microsoft.ML.ImageAnalytics** and **Microsoft.ML.OnnxTransformer**.</span></span>

### <a name="prepare-your-data-and-pre-trained-model"></a><span data-ttu-id="154d8-188">Vorbereiten der Daten und des vortrainierten Modells</span><span class="sxs-lookup"><span data-stu-id="154d8-188">Prepare your data and pre-trained model</span></span>

1. <span data-ttu-id="154d8-189">Laden Sie die [ZIP-Datei aus dem Projektressourcenverzeichnis](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/assets.zip) herunter, und entzippen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="154d8-189">Download [The project assets directory zip file](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/assets.zip) and unzip.</span></span>

1. <span data-ttu-id="154d8-190">Kopieren Sie das Verzeichnis `assets` in Ihr *ObjectDetection*-Projektverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="154d8-190">Copy the `assets` directory into your *ObjectDetection* project directory.</span></span> <span data-ttu-id="154d8-191">Dieses Verzeichnis und seine Unterverzeichnisse enthalten die für dieses Tutorial erforderlichen Bilddateien (mit Ausnahme des Tiny YOLOv2-Modells, das Sie im nächsten Schritt herunterladen und hinzufügen).</span><span class="sxs-lookup"><span data-stu-id="154d8-191">This directory and its subdirectories contain the image files (except for the Tiny YOLOv2 model, which you'll download and add in the next step) needed for this tutorial.</span></span>

1. <span data-ttu-id="154d8-192">Laden Sie das [Tiny YOLOv2-Modell](https://onnxzoo.blob.core.windows.net/models/opset_8/tiny_yolov2/tiny_yolov2.tar.gz) aus dem [ONNX Model Zoo](https://github.com/onnx/models/tree/master/vision/object_detection_segmentation/tiny_yolov2) herunter, und entzippen Sie es.</span><span class="sxs-lookup"><span data-stu-id="154d8-192">Download the [Tiny YOLOv2 model](https://onnxzoo.blob.core.windows.net/models/opset_8/tiny_yolov2/tiny_yolov2.tar.gz) from the [ONNX Model Zoo](https://github.com/onnx/models/tree/master/vision/object_detection_segmentation/tiny_yolov2), and unzip.</span></span>

    <span data-ttu-id="154d8-193">Öffnen Sie die Eingabeaufforderung, und geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="154d8-193">Open the command prompt and enter the following command:</span></span>

    ```shell
    tar -xvzf tiny_yolov2.tar.gz
    ```

1. <span data-ttu-id="154d8-194">Kopieren Sie die extrahierte Datei `model.onnx` aus dem soeben entzippten Verzeichnis in das Verzeichnis `assets\Model` Ihres *ObjectDetection*-Projekts, und benennen Sie sie in `TinyYolo2_model.onnx` um.</span><span class="sxs-lookup"><span data-stu-id="154d8-194">Copy the extracted `model.onnx` file from the directory just unzipped into your *ObjectDetection* project `assets\Model` directory and rename it to `TinyYolo2_model.onnx`.</span></span> <span data-ttu-id="154d8-195">Dieses Verzeichnis enthält das für dieses Tutorial erforderliche Modell.</span><span class="sxs-lookup"><span data-stu-id="154d8-195">This directory contains the model needed for this tutorial.</span></span>

1. <span data-ttu-id="154d8-196">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf alle Dateien im Assetverzeichnis und den Unterverzeichnissen, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="154d8-196">In Solution Explorer, right-click each of the files in the asset directory and subdirectories and select **Properties**.</span></span> <span data-ttu-id="154d8-197">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="154d8-197">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="154d8-198">Erstellen von Klassen und Definieren von Pfaden</span><span class="sxs-lookup"><span data-stu-id="154d8-198">Create classes and define paths</span></span>

<span data-ttu-id="154d8-199">Öffnen Sie die Datei *Program.cs*, und fügen Sie am Anfang der Datei folgende zusätzliche `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="154d8-199">Open the *Program.cs* file and add the following additional `using` statements to the top of the file:</span></span>

[!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L1-L7)]

<span data-ttu-id="154d8-200">Definieren Sie als nächstes die Pfade der verschiedenen Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="154d8-200">Next, define the paths of the various assets.</span></span>

1. <span data-ttu-id="154d8-201">Fügen Sie zunächst die `GetAbsolutePath`-Methode unter der `Main`-Methode in der `Program`-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="154d8-201">First, add the `GetAbsolutePath` method below the `Main` method in the `Program` class.</span></span>

    [!code-csharp [GetAbsolutePath](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L66-L74)]

1. <span data-ttu-id="154d8-202">Erstellen Sie dann in der Methode `Main` Felder, um den Speicherort Ihrer Ressourcen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="154d8-202">Then, inside the `Main` method, create fields to store the location of your assets.</span></span>

    [!code-csharp [AssetDefinition](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L17-L21)]

<span data-ttu-id="154d8-203">Fügen Sie Ihrem Projekt ein neues Verzeichnis hinzu, um die Eingabedaten und Vorhersageklassen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="154d8-203">Add a new directory to your project to store your input data and prediction classes.</span></span>

<span data-ttu-id="154d8-204">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neuer Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="154d8-204">In **Solution Explorer**, right-click the project, and then select **Add** > **New Folder**.</span></span> <span data-ttu-id="154d8-205">Wenn der neue Ordner im Projektmappen-Explorer angezeigt wird, nennen Sie ihn „DataStructures“.</span><span class="sxs-lookup"><span data-stu-id="154d8-205">When the new folder appears in the Solution Explorer, name it "DataStructures".</span></span>

<span data-ttu-id="154d8-206">Erstellen Sie die Eingabedatenklasse im neu erstellten Verzeichnis *DataStructures*.</span><span class="sxs-lookup"><span data-stu-id="154d8-206">Create your input data class in the newly created *DataStructures* directory.</span></span>

1. <span data-ttu-id="154d8-207">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Verzeichnis *DataStructures*, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="154d8-207">In **Solution Explorer**, right-click the *DataStructures* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="154d8-208">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *ImageNetData.cs*.</span><span class="sxs-lookup"><span data-stu-id="154d8-208">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImageNetData.cs*.</span></span> <span data-ttu-id="154d8-209">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="154d8-209">Then, select the **Add** button.</span></span>

    <span data-ttu-id="154d8-210">Die Datei *ImageNetData.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="154d8-210">The *ImageNetData.cs* file opens in the code editor.</span></span> <span data-ttu-id="154d8-211">Fügen Sie die folgende `using`-Anweisung am Anfang der Datei *ImageNetData.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="154d8-211">Add the following `using` statement to the top of *ImageNetData.cs*:</span></span>

    [!code-csharp [ImageNetDataUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetData.cs#L1-L4)]

    <span data-ttu-id="154d8-212">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie der Datei *ImageNetData.cs* den folgenden Code für die `ImageNetData`-Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="154d8-212">Remove the existing class definition and add the following code for the `ImageNetData` class to the *ImageNetData.cs* file:</span></span>

    [!code-csharp [ImageNetDataClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetData.cs#L8-L23)]

    <span data-ttu-id="154d8-213">`ImageNetData` ist die Eingabebilddaten-Klasse mit den folgenden <xref:System.String>-Feldern:</span><span class="sxs-lookup"><span data-stu-id="154d8-213">`ImageNetData` is the input image data class and has the following <xref:System.String> fields:</span></span>

    - <span data-ttu-id="154d8-214">`ImagePath` enthält den Pfad, in dem das Bild gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="154d8-214">`ImagePath` contains the path where the image is stored.</span></span>
    - <span data-ttu-id="154d8-215">`Label` enthält den Namen der Datei.</span><span class="sxs-lookup"><span data-stu-id="154d8-215">`Label` contains the name of the file.</span></span>

    <span data-ttu-id="154d8-216">Darüber hinaus enthält `ImageNetData` eine Methode `ReadFromFile`, die mehrere Bilddateien lädt, die im angegebenen Pfad `imageFolder` gespeichert sind, und sie als eine Sammlung von `ImageNetData`-Objekten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="154d8-216">Additionally, `ImageNetData` contains a method `ReadFromFile` which loads multiple image files stored in the `imageFolder` path specified and returns them as a collection of `ImageNetData` objects.</span></span>

<span data-ttu-id="154d8-217">Erstellen Sie die Vorhersageklasse im Verzeichnis *DataStructures*.</span><span class="sxs-lookup"><span data-stu-id="154d8-217">Create your prediction class in the *DataStructures* directory.</span></span>

1. <span data-ttu-id="154d8-218">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Verzeichnis *DataStructures*, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="154d8-218">In **Solution Explorer**, right-click the *DataStructures* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="154d8-219">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *ImageNetPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="154d8-219">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImageNetPrediction.cs*.</span></span> <span data-ttu-id="154d8-220">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="154d8-220">Then, select the **Add** button.</span></span>

    <span data-ttu-id="154d8-221">Die Datei *ImageNetPrediction.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="154d8-221">The *ImageNetPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="154d8-222">Fügen Sie die folgende `using`-Anweisung am Anfang der Datei *ImageNetPrediction.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="154d8-222">Add the following `using` statement to the top of *ImageNetPrediction.cs*:</span></span>

    [!code-csharp [ImageNetPredictionUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetPrediction.cs#L1)]

    <span data-ttu-id="154d8-223">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie der Datei *ImageNetPrediction.cs* den folgenden Code für die `ImageNetPrediction`-Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="154d8-223">Remove the existing class definition and add the following code for the `ImageNetPrediction` class to the *ImageNetPrediction.cs* file:</span></span>

    [!code-csharp [ImageNetPredictionClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetPrediction.cs#L5-L9)]

    <span data-ttu-id="154d8-224">`ImageNetPrediction` ist die Vorhersagedatenklasse und weist das folgende `float[]`-Feld auf:</span><span class="sxs-lookup"><span data-stu-id="154d8-224">`ImageNetPrediction` is the prediction data class and has the following `float[]` field:</span></span>

    - <span data-ttu-id="154d8-225">`PredictedLabel` enthält die Dimensionen, die Objektbewertung und die Klassenwahrscheinlichkeiten für jeden der Begrenzungsrahmen, der in einem Bild erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="154d8-225">`PredictedLabel` contains the dimensions, objectness score and class probabilities for each of the bounding boxes detected in an image.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="154d8-226">Initialisieren von Variablen in Main</span><span class="sxs-lookup"><span data-stu-id="154d8-226">Initialize variables in Main</span></span>

<span data-ttu-id="154d8-227">Die [MLContext-Klasse](xref:Microsoft.ML.MLContext) ist der Startpunkt für alle ML.NET-Vorgänge. Durch das Initialisieren von `mlContext` wird eine neue ML.NET-Umgebung erstellt, die für mehrere Objekte des Modellerstellungsworkflows verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="154d8-227">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="154d8-228">Die Klasse ähnelt dem Konzept von `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="154d8-228">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

<span data-ttu-id="154d8-229">Initialisieren Sie die `mlContext`-Variable mit einer neuen Instanz von `MLContext`, indem Sie der `Main`-Methode von *Program.cs* unterhalb des Felds `outputFolder` die folgende Zeile hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="154d8-229">Initialize the `mlContext` variable with a new instance of `MLContext` by adding the following line to the `Main` method of *Program.cs* below the `outputFolder` field.</span></span>

[!code-csharp [InitMLContext](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L24)]

## <a name="create-a-parser-to-post-process-model-outputs"></a><span data-ttu-id="154d8-230">Erstellen eines Parsers für die Nachverarbeitung von Modellausgaben</span><span class="sxs-lookup"><span data-stu-id="154d8-230">Create a parser to post-process model outputs</span></span>

<span data-ttu-id="154d8-231">Das Modell segmentiert ein Bild in ein `13 x 13`-Raster, in dem jede Rasterzelle `32px x 32px` groß ist.</span><span class="sxs-lookup"><span data-stu-id="154d8-231">The model segments an image into a `13 x 13` grid, where each grid cell is `32px x 32px`.</span></span> <span data-ttu-id="154d8-232">Jede Rasterzelle enthält fünf potenzielle Objektbegrenzungsrahmen.</span><span class="sxs-lookup"><span data-stu-id="154d8-232">Each grid cell contains 5 potential object bounding boxes.</span></span> <span data-ttu-id="154d8-233">Ein Begrenzungsrahmen enthält 25 Elemente:</span><span class="sxs-lookup"><span data-stu-id="154d8-233">A bounding box has  25 elements:</span></span>

![Rasterbeispiel auf der linken Seite und Begrenzungsfeldbeispiel auf der rechten Seite](./media/object-detection-onnx/model-output-description.png)

- <span data-ttu-id="154d8-235">`x`: die x-Position der Mitte des Begrenzungsrahmens relativ zu der Rasterzelle, der er zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="154d8-235">`x` the x position of the bounding box center relative to the grid cell it's associated with.</span></span>
- <span data-ttu-id="154d8-236">`y`: die y-Position der Mitte des Begrenzungsrahmens relativ zu der Rasterzelle, der er zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="154d8-236">`y` the y position of the bounding box center relative to the grid cell it's associated with.</span></span>
- <span data-ttu-id="154d8-237">`w`: Die Breite des Begrenzungsrahmens.</span><span class="sxs-lookup"><span data-stu-id="154d8-237">`w` the width of the bounding box.</span></span>
- <span data-ttu-id="154d8-238">`h`: Die Höhe des Begrenzungsrahmens.</span><span class="sxs-lookup"><span data-stu-id="154d8-238">`h` the height of the bounding box.</span></span>
- <span data-ttu-id="154d8-239">`o`: Der Konfidenzwert, mit dem ein Objekt im Begrenzungsrahmen vorhanden ist (auch als Objectness Score bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="154d8-239">`o` the confidence value that an object exists within the bounding box, also known as objectness score.</span></span>
- <span data-ttu-id="154d8-240">`p1-p20`: Klassenwahrscheinlichkeiten für jede der 20 vom Modell vorhergesagten Klassen.</span><span class="sxs-lookup"><span data-stu-id="154d8-240">`p1-p20` class probabilities for each of the 20 classes predicted by the model.</span></span>

<span data-ttu-id="154d8-241">Insgesamt bilden die 25 Elemente, die jeden der 5 Begrenzungsrahmen beschreiben, die 125 Elemente, die in jeder Rasterzelle enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="154d8-241">In total, the 25 elements describing each of the 5 bounding boxes make up the 125 elements contained in each grid cell.</span></span>

<span data-ttu-id="154d8-242">Die Ausgabe, die vom vortrainierten ONNX-Modell generiert wird, ist ein float-Array der Länge `21125`, das die Elemente eines Tensors mit Dimensionen `125 x 13 x 13` darstellt.</span><span class="sxs-lookup"><span data-stu-id="154d8-242">The output generated by the pre-trained ONNX model is a float array of length `21125`, representing the elements of a tensor with dimensions `125 x 13 x 13`.</span></span> <span data-ttu-id="154d8-243">Um die vom Modell generierten Vorhersagen in einen Tensor zu transformieren, sind einige Nachverarbeitungsaufgaben erforderlich.</span><span class="sxs-lookup"><span data-stu-id="154d8-243">In order to transform the predictions generated by the model into a tensor, some post-processing work is required.</span></span> <span data-ttu-id="154d8-244">Erstellen Sie zu diesem Zweck eine Reihe von Klassen, um die Analyse der Ausgabe zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="154d8-244">To do so, create a set of classes to help parse the output.</span></span>

<span data-ttu-id="154d8-245">Fügen Sie Ihrem Projekt ein neues Verzeichnis hinzu, um den Satz von Parserklassen zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="154d8-245">Add a new directory to your project to organize the set of parser classes.</span></span>

1. <span data-ttu-id="154d8-246">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neuer Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="154d8-246">In **Solution Explorer**, right-click the project, and then select **Add** > **New Folder**.</span></span> <span data-ttu-id="154d8-247">Wenn der neue Ordner im Projektmappen-Explorer angezeigt wird, nennen Sie ihn „YoloParser“.</span><span class="sxs-lookup"><span data-stu-id="154d8-247">When the new folder appears in the Solution Explorer, name it "YoloParser".</span></span>

### <a name="create-bounding-boxes-and-dimensions"></a><span data-ttu-id="154d8-248">Erstellen von Begrenzungsrahmen und Dimensionen</span><span class="sxs-lookup"><span data-stu-id="154d8-248">Create bounding boxes and dimensions</span></span>

<span data-ttu-id="154d8-249">Die Daten, die vom Modell ausgegeben werden, enthalten Koordinaten und Dimensionen der Begrenzungsrahmen von Objekten im Bild.</span><span class="sxs-lookup"><span data-stu-id="154d8-249">The data output by the model contains coordinates and dimensions of the bounding boxes of objects within the image.</span></span> <span data-ttu-id="154d8-250">Erstellen Sie eine Basisklasse für Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="154d8-250">Create a base class for dimensions.</span></span>

1. <span data-ttu-id="154d8-251">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Verzeichnis *YoloParser*, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="154d8-251">In **Solution Explorer**, right-click the *YoloParser* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="154d8-252">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *DimensionsBase.cs*.</span><span class="sxs-lookup"><span data-stu-id="154d8-252">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *DimensionsBase.cs*.</span></span> <span data-ttu-id="154d8-253">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="154d8-253">Then, select the **Add** button.</span></span>

    <span data-ttu-id="154d8-254">Die Datei *DimensionsBase.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="154d8-254">The *DimensionsBase.cs* file opens in the code editor.</span></span> <span data-ttu-id="154d8-255">Entfernen Sie alle `using`-Anweisungen und die vorhandene Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="154d8-255">Remove all `using` statements and existing class definition.</span></span>

    <span data-ttu-id="154d8-256">Fügen Sie der Datei *DimensionsBase.cs* den folgenden Code für die `DimensionsBase`-Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="154d8-256">Add the following code for the `DimensionsBase` class to the *DimensionsBase.cs* file:</span></span>

    [!code-csharp [DimensionsBaseClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/DimensionsBase.cs#L3-L9)]

    <span data-ttu-id="154d8-257">`DimensionsBase` verfügt über die folgenden `float`-Felder:</span><span class="sxs-lookup"><span data-stu-id="154d8-257">`DimensionsBase` has the following `float` fields:</span></span>

    - <span data-ttu-id="154d8-258">`X` enthält die Position des Objekts auf der X-Achse.</span><span class="sxs-lookup"><span data-stu-id="154d8-258">`X` contains the position of the object along the x-axis.</span></span>
    - <span data-ttu-id="154d8-259">`Y` enthält die Position des Objekts auf der Y-Achse.</span><span class="sxs-lookup"><span data-stu-id="154d8-259">`Y` contains the position of the object along the y-axis.</span></span>
    - <span data-ttu-id="154d8-260">`Height` enthält die Höhe des Objekts.</span><span class="sxs-lookup"><span data-stu-id="154d8-260">`Height` contains the height of the object.</span></span>
    - <span data-ttu-id="154d8-261">`Width` enthält die Breite des Objekts.</span><span class="sxs-lookup"><span data-stu-id="154d8-261">`Width` contains the width of the object.</span></span>

<span data-ttu-id="154d8-262">Erstellen Sie nun eine Klasse für Ihre Begrenzungsrahmen.</span><span class="sxs-lookup"><span data-stu-id="154d8-262">Next, create a class for your bounding boxes.</span></span>

1. <span data-ttu-id="154d8-263">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Verzeichnis *YoloParser*, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="154d8-263">In **Solution Explorer**, right-click the *YoloParser* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="154d8-264">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *YoloBoundingBox.cs*.</span><span class="sxs-lookup"><span data-stu-id="154d8-264">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *YoloBoundingBox.cs*.</span></span> <span data-ttu-id="154d8-265">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="154d8-265">Then, select the **Add** button.</span></span>

    <span data-ttu-id="154d8-266">Die Datei *YoloBoundingBox.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="154d8-266">The *YoloBoundingBox.cs* file opens in the code editor.</span></span> <span data-ttu-id="154d8-267">Fügen Sie die folgende `using`-Anweisung am Anfang der Datei *YoloBoundingBox.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="154d8-267">Add the following `using` statement to the top of *YoloBoundingBox.cs*:</span></span>

    [!code-csharp [YoloBoundingBoxUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloBoundingBox.cs#L1)]

    <span data-ttu-id="154d8-268">Fügen Sie direkt oberhalb der vorhandenen Klassendefinition eine neue Klassendefinition namens `BoundingBoxDimensions` hinzu, die von der `DimensionsBase`-Klasse erbt, um die Dimensionen des entsprechenden Begrenzungsrahmens zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="154d8-268">Just above the existing class definition, add a new class definition called `BoundingBoxDimensions` which inherits from the `DimensionsBase` class to contain the dimensions of the respective bounding box.</span></span>

    [!code-csharp [BoundingBoxDimClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloBoundingBox.cs#L5)]

    <span data-ttu-id="154d8-269">Entfernen Sie die vorhandene `YoloBoundingBox`-Klassendefinition, und fügen Sie der Datei *YoloBoundingBox.cs* den folgenden Code für die `YoloBoundingBox`-Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="154d8-269">Remove the existing `YoloBoundingBox` class definition and add the following code for the `YoloBoundingBox` class to the *YoloBoundingBox.cs* file:</span></span>

    [!code-csharp [YoloBoundingBoxClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloBoundingBox.cs#L7-L21)]

    <span data-ttu-id="154d8-270">`YoloBoundingBox` verfügt über die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="154d8-270">`YoloBoundingBox` has the following fields:</span></span>

    - <span data-ttu-id="154d8-271">`Dimensions` enthält Dimensionen des Begrenzungsrahmens.</span><span class="sxs-lookup"><span data-stu-id="154d8-271">`Dimensions` contains dimensions of the bounding box.</span></span>
    - <span data-ttu-id="154d8-272">`Label` enthält die Klasse des Objekts, das innerhalb des Begrenzungsrahmens erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="154d8-272">`Label` contains the class of object detected within the bounding box.</span></span>
    - <span data-ttu-id="154d8-273">`Confidence` enthält die Konfidenz der Klasse.</span><span class="sxs-lookup"><span data-stu-id="154d8-273">`Confidence` contains the confidence of the class.</span></span>
    - <span data-ttu-id="154d8-274">`Rect` enthält die Rechteckdarstellung der Abmessungen des Begrenzungsrahmens.</span><span class="sxs-lookup"><span data-stu-id="154d8-274">`Rect` contains the rectangle representation of the bounding box's dimensions.</span></span>
    - <span data-ttu-id="154d8-275">`BoxColor` enthält die Farbe, die der jeweiligen Klasse zugeordnet ist, die zum Zeichnen des Bilds verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="154d8-275">`BoxColor` contains the color associated with the respective class used to draw on the image.</span></span>

### <a name="create-the-parser"></a><span data-ttu-id="154d8-276">Erstellen des Parsers</span><span class="sxs-lookup"><span data-stu-id="154d8-276">Create the parser</span></span>

<span data-ttu-id="154d8-277">Da nun die Klassen für Dimensionen und Begrenzungsrahmen erstellt wurden, ist es an der Zeit, den Parser zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="154d8-277">Now that the classes for dimensions and bounding boxes are created, it's time to create the parser.</span></span>

1. <span data-ttu-id="154d8-278">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Verzeichnis *YoloParser*, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="154d8-278">In **Solution Explorer**, right-click the *YoloParser* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="154d8-279">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *YoloOutputParser.cs*.</span><span class="sxs-lookup"><span data-stu-id="154d8-279">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *YoloOutputParser.cs*.</span></span> <span data-ttu-id="154d8-280">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="154d8-280">Then, select the **Add** button.</span></span>

    <span data-ttu-id="154d8-281">Die Datei *YoloOutputParser.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="154d8-281">The *YoloOutputParser.cs* file opens in the code editor.</span></span> <span data-ttu-id="154d8-282">Fügen Sie die folgende `using`-Anweisung am Anfang der Datei *YoloOutputParser.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="154d8-282">Add the following `using` statement to the top of *YoloOutputParser.cs*:</span></span>

    [!code-csharp [YoloParserUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L1-L4)]

    <span data-ttu-id="154d8-283">Fügen Sie innerhalb der vorhandenen `YoloOutputParser`-Klassendefinition eine geschachtelte Klasse hinzu, die die Dimensionen der einzelnen Zellen im Bild enthält.</span><span class="sxs-lookup"><span data-stu-id="154d8-283">Inside the existing `YoloOutputParser` class definition, add a nested class that contains the dimensions of each of the cells in the image.</span></span> <span data-ttu-id="154d8-284">Fügen Sie den folgenden Code am Anfang der `YoloOutputParser`-Klassendefinition für die `CellDimensions`-Klasse hinzu, die von der `DimensionsBase`-Klasse erbt.</span><span class="sxs-lookup"><span data-stu-id="154d8-284">Add the following code for the `CellDimensions` class which inherits from the `DimensionsBase` class at the top of the `YoloOutputParser` class definition.</span></span>

    [!code-csharp [YoloParserUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L10)]

1. <span data-ttu-id="154d8-285">Fügen Sie in der `YoloOutputParser`-Klassendefinition die folgende Konstante und die folgenden Felder hinzu.</span><span class="sxs-lookup"><span data-stu-id="154d8-285">Inside the `YoloOutputParser` class definition, add the following constant and fields.</span></span>

    [!code-csharp [ParserVarDefinitions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L12-L21)]

    - <span data-ttu-id="154d8-286">`ROW_COUNT` ist die Anzahl der Zeilen im Raster, in die das Bild aufgeteilt wird.</span><span class="sxs-lookup"><span data-stu-id="154d8-286">`ROW_COUNT` is the number of rows in the grid the image is divided into.</span></span>
    - <span data-ttu-id="154d8-287">`COL_COUNT` ist die Anzahl der Spalten im Raster, in die das Bild aufgeteilt wird.</span><span class="sxs-lookup"><span data-stu-id="154d8-287">`COL_COUNT` is the number of columns in the grid the image is divided into.</span></span>
    - <span data-ttu-id="154d8-288">`CHANNEL_COUNT` ist die Gesamtzahl der Werte, die in einer Zelle des Rasters enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="154d8-288">`CHANNEL_COUNT` is the total number of values contained in one cell of the grid.</span></span>
    - <span data-ttu-id="154d8-289">`BOXES_PER_CELL` ist die Anzahl der Begrenzungsrahmen in einer Zelle.</span><span class="sxs-lookup"><span data-stu-id="154d8-289">`BOXES_PER_CELL` is the number of bounding boxes in a cell,</span></span>
    - <span data-ttu-id="154d8-290">`BOX_INFO_FEATURE_COUNT` ist die Anzahl der in einem Feld enthaltenen Merkmale (x, y, Höhe, Breite, Konfidenz).</span><span class="sxs-lookup"><span data-stu-id="154d8-290">`BOX_INFO_FEATURE_COUNT` is the number of features contained within a box (x,y,height,width,confidence).</span></span>
    - <span data-ttu-id="154d8-291">`CLASS_COUNT` ist die Anzahl der Klassenvorhersagen, die in jedem Begrenzungsrahmen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="154d8-291">`CLASS_COUNT` is the number of class predictions contained in each bounding box.</span></span>
    - <span data-ttu-id="154d8-292">`CELL_WIDTH` ist die Breite einer Zelle im Bildraster.</span><span class="sxs-lookup"><span data-stu-id="154d8-292">`CELL_WIDTH` is the width of one cell in the image grid.</span></span>
    - <span data-ttu-id="154d8-293">`CELL_HEIGHT` ist die Höhe einer Zelle im Bildraster.</span><span class="sxs-lookup"><span data-stu-id="154d8-293">`CELL_HEIGHT` is the height of one cell in the image grid.</span></span>
    - <span data-ttu-id="154d8-294">`channelStride` ist die Anfangsposition der aktuellen Zelle im Raster.</span><span class="sxs-lookup"><span data-stu-id="154d8-294">`channelStride` is the starting position of the current cell in the grid.</span></span>

    <span data-ttu-id="154d8-295">Wenn das Modell eine Vorhersage erstellt (auch als Bewertung bezeichnet), unterteilt es das Eingabebild `416px x 416px` in ein Raster von Zellen mit einer Größe von `13 x 13`.</span><span class="sxs-lookup"><span data-stu-id="154d8-295">When the model makes a prediction, also known as scoring, it divides the `416px x 416px` input image into a grid of cells the size of `13 x 13`.</span></span> <span data-ttu-id="154d8-296">Jede enthaltene Zelle ist `32px x 32px` groß.</span><span class="sxs-lookup"><span data-stu-id="154d8-296">Each cell contains is `32px x 32px`.</span></span> <span data-ttu-id="154d8-297">In jeder Zelle sind fünf Begrenzungsrahmen enthalten, die jeweils fünf Merkmale enthalten (x, y, Breite, Höhe, Konfidenz).</span><span class="sxs-lookup"><span data-stu-id="154d8-297">Within each cell, there are 5 bounding boxes each containing 5 features (x, y, width, height, confidence).</span></span> <span data-ttu-id="154d8-298">Außerdem enthält jeder Begrenzungsrahmen die Wahrscheinlichkeit der einzelnen Klassen (in diesem Fall ist sie 20).</span><span class="sxs-lookup"><span data-stu-id="154d8-298">In addition, each bounding box contains the probability of each of the classes which in this case is 20.</span></span> <span data-ttu-id="154d8-299">Daher enthält jede Zelle 125 Informationen (5 Merkmale und 20 Klassenwahrscheinlichkeiten).</span><span class="sxs-lookup"><span data-stu-id="154d8-299">Therefore, each cell contains 125 pieces of information (5 features + 20 class probabilities).</span></span>

<span data-ttu-id="154d8-300">Erstellen Sie eine Liste der Anker unter `channelStride` für alle 5 Begrenzungsrahmen:</span><span class="sxs-lookup"><span data-stu-id="154d8-300">Create a list of anchors below `channelStride` for all 5 bounding boxes:</span></span>

[!code-csharp [ParserAnchors](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L23-L26)]

<span data-ttu-id="154d8-301">Anker sind vordefinierte Höhen- und Breitenverhältnisse für Begrenzungsrahmen.</span><span class="sxs-lookup"><span data-stu-id="154d8-301">Anchors are pre-defined height and width ratios of bounding boxes.</span></span> <span data-ttu-id="154d8-302">Die meisten von einem Modell erkannten Objekte oder Klassen weisen ähnliche Verhältnisse auf.</span><span class="sxs-lookup"><span data-stu-id="154d8-302">Most object or classes detected by a model have similar ratios.</span></span> <span data-ttu-id="154d8-303">Dies ist nützlich, wenn es um das Erstellen von Begrenzungsrahmen geht.</span><span class="sxs-lookup"><span data-stu-id="154d8-303">This is valuable when it comes to creating bounding boxes.</span></span> <span data-ttu-id="154d8-304">Anstatt die Begrenzungsrahmen vorherzusagen, wird der Offset zu den vordefinierten Abmessungen berechnet, wodurch die für die Vorhersage des Begrenzungsrahmens erforderliche Berechnung verringert wird.</span><span class="sxs-lookup"><span data-stu-id="154d8-304">Instead of predicting the bounding boxes, the offset from the pre-defined dimensions is calculated therefore reducing the computation required to predict the bounding box.</span></span> <span data-ttu-id="154d8-305">Normalerweise werden diese Ankerverhältnisse basierend auf dem verwendeten Dataset berechnet.</span><span class="sxs-lookup"><span data-stu-id="154d8-305">Typically these anchor ratios are calculated based on the dataset used.</span></span> <span data-ttu-id="154d8-306">In diesem Fall können die Anker hartcodiert werden, da das Dataset bekannt ist und die Werte vorberechnet wurden.</span><span class="sxs-lookup"><span data-stu-id="154d8-306">In this case because the dataset is known and the values have been pre-computed, the anchors can be hard-coded.</span></span>

<span data-ttu-id="154d8-307">Definieren Sie nun die Bezeichnungen oder Klassen, die vom Modell vorhergesagt werden.</span><span class="sxs-lookup"><span data-stu-id="154d8-307">Next, define the labels or classes that the model will predict.</span></span> <span data-ttu-id="154d8-308">Dieses Modell sagt 20 Klassen voraus, was eine Teilmenge der Gesamtzahl der vom ursprünglichen YOLOv2-Modell vorhergesagten Klassen ist.</span><span class="sxs-lookup"><span data-stu-id="154d8-308">This model predicts 20 classes which is a subset of the total number of classes predicted by the original YOLOv2 model.</span></span>

<span data-ttu-id="154d8-309">Fügen Sie die Liste der Bezeichnungen unterhalb von `anchors` hinzu.</span><span class="sxs-lookup"><span data-stu-id="154d8-309">Add your list of labels below the `anchors`.</span></span>

[!code-csharp [ParserLabels](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L28-L34)]

<span data-ttu-id="154d8-310">Jeder der Klassen sind Farben zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="154d8-310">There are colors associated with each of the classes.</span></span> <span data-ttu-id="154d8-311">Weisen Sie Ihre Klassenfarben unter `labels` zu:</span><span class="sxs-lookup"><span data-stu-id="154d8-311">Assign your class colors below your `labels`:</span></span>

[!code-csharp [ParserColors](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L36-L59)]

### <a name="create-helper-functions"></a><span data-ttu-id="154d8-312">Erstellen von Hilfsfunktionen</span><span class="sxs-lookup"><span data-stu-id="154d8-312">Create helper functions</span></span>

<span data-ttu-id="154d8-313">In der Nachverarbeitungsphase sind mehrere Schritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="154d8-313">There are a series of steps involved in the post-processing phase.</span></span> <span data-ttu-id="154d8-314">Zur Unterstützung können mehrere Hilfsmethoden eingesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="154d8-314">To help with that, several helper methods can be employed.</span></span>

<span data-ttu-id="154d8-315">Die folgenden Hilfsmethoden werden vom Parser verwendet:</span><span class="sxs-lookup"><span data-stu-id="154d8-315">The helper methods used in by the parser are:</span></span>

- <span data-ttu-id="154d8-316">`Sigmoid` wendet die Sigmoidfunktion an, die eine Zahl zwischen 0 und 1 ausgibt.</span><span class="sxs-lookup"><span data-stu-id="154d8-316">`Sigmoid` applies the sigmoid function that outputs a number between 0 and 1.</span></span>
- <span data-ttu-id="154d8-317">`Softmax` normalisiert einen Eingabevektor in eine Wahrscheinlichkeitsverteilung.</span><span class="sxs-lookup"><span data-stu-id="154d8-317">`Softmax` normalizes an input vector into a probability distribution.</span></span>
- <span data-ttu-id="154d8-318">`GetOffset` ordnet Elemente in der eindimensionalen Modellausgabe der entsprechenden Position in einem `125 x 13 x 13`-Tensor zu.</span><span class="sxs-lookup"><span data-stu-id="154d8-318">`GetOffset` maps elements in the one-dimensional model output to the corresponding position in a `125 x 13 x 13` tensor.</span></span>
- <span data-ttu-id="154d8-319">`ExtractBoundingBoxes` extrahiert die Abmessungen des Begrenzungsrahmens mithilfe der `GetOffset`-Methode aus der Modellausgabe.</span><span class="sxs-lookup"><span data-stu-id="154d8-319">`ExtractBoundingBoxes` extracts the bounding box dimensions using the `GetOffset` method from the model output.</span></span>
- <span data-ttu-id="154d8-320">`GetConfidence` extrahiert den Konfidenzwert, der angibt, wie sicher sich das Modell ist, dass ein Objekt erkannt wurde, und verwendet die `Sigmoid`-Funktion, um diesen Wert in eine Prozentangabe umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="154d8-320">`GetConfidence` extracts the confidence value which states how sure the model is that it has detected an object and uses the `Sigmoid` function to turn it into a percentage.</span></span>
- <span data-ttu-id="154d8-321">`MapBoundingBoxToCell` verwendet die Abmessungen des Begrenzungsrahmens und ordnet diese der entsprechenden Zelle im Bild zu.</span><span class="sxs-lookup"><span data-stu-id="154d8-321">`MapBoundingBoxToCell` uses the bounding box dimensions and maps them onto its respective cell within the image.</span></span>
- <span data-ttu-id="154d8-322">`ExtractClasses` extrahiert die Klassenvorhersagen für den Begrenzungsrahmen aus der Modellausgabe unter Verwendung der `GetOffset`-Methode und wandelt sie mithilfe der `Softmax`-Methode in eine Wahrscheinlichkeitsverteilung um.</span><span class="sxs-lookup"><span data-stu-id="154d8-322">`ExtractClasses` extracts the class predictions for the bounding box from the model output using the `GetOffset` method and turns them into a probability distribution using the `Softmax` method.</span></span>
- <span data-ttu-id="154d8-323">`GetTopResult` wählt die Klasse aus der Liste der vorhergesagten Klassen mit der höchsten Wahrscheinlichkeit aus.</span><span class="sxs-lookup"><span data-stu-id="154d8-323">`GetTopResult` selects the class from the list of predicted classes with the highest probability.</span></span>
- <span data-ttu-id="154d8-324">`IntersectionOverUnion` filtert sich überlappende Begrenzungsrahmen mit geringeren Wahrscheinlichkeiten.</span><span class="sxs-lookup"><span data-stu-id="154d8-324">`IntersectionOverUnion` filters overlapping bounding boxes with lower probabilities.</span></span>

<span data-ttu-id="154d8-325">Fügen Sie den Code für alle Hilfsmethoden unterhalb der Liste der `classColors` hinzu.</span><span class="sxs-lookup"><span data-stu-id="154d8-325">Add the code for all the helper methods below your list of `classColors`.</span></span>

[!code-csharp [ParserHelperMethods](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L61-L151)]

<span data-ttu-id="154d8-326">Nachdem Sie alle Hilfsmethoden definiert haben, ist es an der Zeit, Sie zum Verarbeiten der Modellausgabe zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="154d8-326">Once you have defined all of the helper methods, it's time to use them to process the model output.</span></span>

<span data-ttu-id="154d8-327">Erstellen Sie unter der `IntersectionOverUnion`-Methode die `ParseOutputs`-Methode, um die vom Modell generierte Ausgabe zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="154d8-327">Below the `IntersectionOverUnion` method, create the `ParseOutputs` method to process the output generated by the model.</span></span>

```csharp
public IList<YoloBoundingBox> ParseOutputs(float[] yoloModelOutputs, float threshold = .3F)
{

}
```

<span data-ttu-id="154d8-328">Erstellen Sie eine Liste, um die Begrenzungsrahmen zu speichern, und definieren Sie Variablen in der `ParseOutputs`-Methode.</span><span class="sxs-lookup"><span data-stu-id="154d8-328">Create a list to store your bounding boxes and define variables inside the `ParseOutputs` method.</span></span>

[!code-csharp [BBoxList](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L155)]

<span data-ttu-id="154d8-329">Jedes Bild wird in ein Raster von `13 x 13`-Zellen aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="154d8-329">Each image is divided into a grid of `13 x 13` cells.</span></span> <span data-ttu-id="154d8-330">Jede Zelle enthält fünf Begrenzungsrahmen.</span><span class="sxs-lookup"><span data-stu-id="154d8-330">Each cell contains five bounding boxes.</span></span> <span data-ttu-id="154d8-331">Fügen Sie unterhalb der Variablen `boxes` Code hinzu, um alle Rahmen jeder Zelle zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="154d8-331">Below the `boxes` variable, add code to process all of the boxes in each of the cells.</span></span>

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

<span data-ttu-id="154d8-332">Berechnen Sie in der innersten Schleife die Anfangsposition des aktuellen Rahmens innerhalb der eindimensionalen Modellausgabe.</span><span class="sxs-lookup"><span data-stu-id="154d8-332">Inside the inner-most loop, calculate the starting position of the current box within the one-dimensional model output.</span></span>

[!code-csharp [ChannelDef](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L163)]

<span data-ttu-id="154d8-333">Verwenden Sie direkt darunter die `ExtractBoundingBoxDimensions`-Methode, um die Abmessungen des aktuellen Begrenzungsrahmens abzurufen.</span><span class="sxs-lookup"><span data-stu-id="154d8-333">Directly below that, use the `ExtractBoundingBoxDimensions` method to get the dimensions of the current bounding box.</span></span>

[!code-csharp [GetBBoxDims](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L165)]

<span data-ttu-id="154d8-334">Verwenden Sie dann die `GetConfidence`-Methode, um die Konfidenz für den aktuellen Begrenzungsrahmen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="154d8-334">Then, use the `GetConfidence` method to get the confidence for the current bounding box.</span></span>

[!code-csharp [GetConfidence](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L167)]

<span data-ttu-id="154d8-335">Verwenden Sie anschließend die `MapBoundingBoxToCell`-Methode, um der aktuellen Zelle, die verarbeitet wird, den aktuellen Begrenzungsrahmen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="154d8-335">After that, use the `MapBoundingBoxToCell` method to map the current bounding box to the current cell being processed.</span></span>

[!code-csharp [MapBoundingBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L169)]

<span data-ttu-id="154d8-336">Überprüfen Sie vor der weiteren Verarbeitung, ob Ihr Konfidenzwert größer als der angegebene Schwellenwert ist.</span><span class="sxs-lookup"><span data-stu-id="154d8-336">Before doing any further processing, check whether your confidence value is greater than the threshold provided.</span></span> <span data-ttu-id="154d8-337">Wenn dies nicht der Fall ist, verarbeiten Sie den nächsten Begrenzungsrahmen.</span><span class="sxs-lookup"><span data-stu-id="154d8-337">If not, process the next bounding box.</span></span>

[!code-csharp [CheckThreshold1](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L171-L172)]

<span data-ttu-id="154d8-338">Setzen Sie andernfalls die Verarbeitung der Ausgabe fort.</span><span class="sxs-lookup"><span data-stu-id="154d8-338">Otherwise, continue processing the output.</span></span> <span data-ttu-id="154d8-339">Der nächste Schritt besteht darin, die Wahrscheinlichkeitsverteilung der vorhergesagten Klassen für den aktuellen Begrenzungsrahmen mithilfe der `ExtractClasses`-Methode abzurufen.</span><span class="sxs-lookup"><span data-stu-id="154d8-339">The next step is to get the probability distribution of the predicted classes for the current bounding box using the `ExtractClasses` method.</span></span>

[!code-csharp [ExtractClasses](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L174)]

<span data-ttu-id="154d8-340">Verwenden Sie dann die `GetTopResult`-Methode, um den Wert und den Index der Klasse mit der höchsten Wahrscheinlichkeit für den aktuellen Rahmen abzurufen, und berechnen Sie die Bewertung.</span><span class="sxs-lookup"><span data-stu-id="154d8-340">Then, use the `GetTopResult` method to get the value and index of the class with the highest probability for the current box and compute its score.</span></span>

[!code-csharp [GetTopResult](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L176-L177)]

<span data-ttu-id="154d8-341">Verwenden Sie `topScore`, um erneut nur die Begrenzungsrahmen beizubehalten, die über dem angegebenen Schwellenwert liegen.</span><span class="sxs-lookup"><span data-stu-id="154d8-341">Use the `topScore` to once again keep only those bounding boxes that are above the specified threshold.</span></span>

[!code-csharp [CheckThreshold2](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L179-L180)]

<span data-ttu-id="154d8-342">Wenn der aktuelle Begrenzungsrahmen den Schwellenwert überschreitet, erstellen Sie ein neues `BoundingBox`-Objekt, und fügen Sie es der `boxes`-Liste hinzu.</span><span class="sxs-lookup"><span data-stu-id="154d8-342">Finally, if the current bounding box exceeds the threshold, create a new `BoundingBox` object and add it to the `boxes` list.</span></span>

[!code-csharp [AddBBoxToList](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L182-L194)]

<span data-ttu-id="154d8-343">Nachdem alle Zellen im Bild verarbeitet wurden, geben Sie die `boxes`-Liste zurück.</span><span class="sxs-lookup"><span data-stu-id="154d8-343">Once all cells in the image have been processed, return the `boxes` list.</span></span> <span data-ttu-id="154d8-344">Fügen Sie die folgende Rückgabeanweisung unterhalb der äußersten for-Schleife in der `ParseOutputs`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="154d8-344">Add the following return statement below the outer-most for-loop in the `ParseOutputs` method.</span></span>

[!code-csharp [ReturnBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L198)]

### <a name="filter-overlapping-boxes"></a><span data-ttu-id="154d8-345">Filtern sich überlappender Rahmen</span><span class="sxs-lookup"><span data-stu-id="154d8-345">Filter overlapping boxes</span></span>

<span data-ttu-id="154d8-346">Nachdem nun alle Begrenzungsrahmen mit einem hohen Konfidenzwert aus der Modellausgabe extrahiert wurden, muss eine zusätzliche Filterung durchgeführt werden, um sich überlappende Bilder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="154d8-346">Now that all of the highly confident bounding boxes have been extracted from the model output, additional filtering needs to be done to remove overlapping images.</span></span> <span data-ttu-id="154d8-347">Fügen Sie unter der `ParseOutputs`-Methode eine Methode namens `FilterBoundingBoxes` hinzu:</span><span class="sxs-lookup"><span data-stu-id="154d8-347">Add a method called `FilterBoundingBoxes` below the `ParseOutputs` method:</span></span>

```csharp
public IList<YoloBoundingBox> FilterBoundingBoxes(IList<YoloBoundingBox> boxes, int limit, float threshold)
{

}
```

<span data-ttu-id="154d8-348">Erstellen Sie innerhalb der `FilterBoundingBoxes`-Methode zunächst ein Array in der Größe der erkannten Rahmen, und markieren Sie alle Slots als aktiv oder bereit zur Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="154d8-348">Inside the `FilterBoundingBoxes` method, start off by creating an array equal to the size of detected boxes and marking all slots as active or ready for processing.</span></span>

[!code-csharp [InitActiveSlots](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L203-L207)]

<span data-ttu-id="154d8-349">Sortieren Sie die Liste mit den Begrenzungsrahmen dann in absteigender Reihenfolge basierend auf dem Konfidenzwert.</span><span class="sxs-lookup"><span data-stu-id="154d8-349">Then, sort the list containing your bounding boxes in descending order based on confidence.</span></span>

[!code-csharp [SortBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L209-L211)]

<span data-ttu-id="154d8-350">Erstellen Sie anschließend eine Liste, in der die gefilterten Ergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="154d8-350">After that, create a list to hold the filtered results.</span></span>

[!code-csharp [InitFilterResult](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L213)]

<span data-ttu-id="154d8-351">Beginnen Sie mit der Verarbeitung der einzelnen Begrenzungsrahmen, indem Sie die einzelnen Begrenzungsrahmen durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="154d8-351">Begin processing each bounding box by iterating over each of the bounding boxes.</span></span>

```csharp
for (int i = 0; i < boxes.Count; i++)
{

}
```

<span data-ttu-id="154d8-352">Überprüfen Sie in dieser for-Schleife, ob der aktuelle Begrenzungsrahmen verarbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="154d8-352">Inside of this for-loop, check whether the current bounding box can be processed.</span></span>

```csharp
if (isActiveBoxes[i])
{

}
```

<span data-ttu-id="154d8-353">Wenn dies der Fall ist, fügen Sie den Begrenzungsrahmen der Ergebnisliste hinzu.</span><span class="sxs-lookup"><span data-stu-id="154d8-353">If so, add the bounding box to the list of results.</span></span> <span data-ttu-id="154d8-354">Wenn die Ergebnisse den angegebenen Grenzwert für die zu extrahierenden Rahmen überschreiten, unterbrechen Sie die Schleife.</span><span class="sxs-lookup"><span data-stu-id="154d8-354">If the results exceeds the specified limit of boxes to be extracted, break out of the loop.</span></span> <span data-ttu-id="154d8-355">Fügen Sie den folgenden Code in der if-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="154d8-355">Add the following code inside the if-statement.</span></span>

[!code-csharp [AddFirstBBoxToResults](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L219-L223)]

<span data-ttu-id="154d8-356">Untersuchen Sie andernfalls die angrenzenden Begrenzungsrahmen.</span><span class="sxs-lookup"><span data-stu-id="154d8-356">Otherwise, look at the adjacent bounding boxes.</span></span> <span data-ttu-id="154d8-357">Fügen Sie unter der Überprüfung der Rahmengrenze den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="154d8-357">Add the following code below the box limit check.</span></span>

```csharp
for (var j = i + 1; j < boxes.Count; j++)
{

}
```

<span data-ttu-id="154d8-358">Wenn der benachbarte Rahmen aktiv oder bereit zur Verarbeitung ist, verwenden Sie wie beim ersten Rahmen die `IntersectionOverUnion`-Methode, um zu überprüfen, ob der erste Rahmen und der zweite Rahmen den angegebenen Schwellenwert überschreiten.</span><span class="sxs-lookup"><span data-stu-id="154d8-358">Like the first box, if the adjacent box is active or ready to be processed, use the `IntersectionOverUnion` method to check whether the first box and the second box exceed the specified threshold.</span></span> <span data-ttu-id="154d8-359">Fügen Sie der innersten for-Schleife den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="154d8-359">Add the following code to your inner-most for-loop.</span></span>

[!code-csharp [IOUBBox](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L227-L239)]

<span data-ttu-id="154d8-360">Überprüfen Sie außerhalb der inneren for-Schleife, die angrenzende Begrenzungsrahmen überprüft, ob noch verbleibende Begrenzungsrahmen verarbeitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="154d8-360">Outside of the inner-most for-loop that checks adjacent bounding boxes, see whether there are any remaining bounding boxes to be processed.</span></span> <span data-ttu-id="154d8-361">Wenn dies nicht der Fall ist, unterbrechen Sie die äußere for-Schleife.</span><span class="sxs-lookup"><span data-stu-id="154d8-361">If not, break out of the outer for-loop.</span></span>

[!code-csharp [CheckActiveSlots](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L242-L243)]

<span data-ttu-id="154d8-362">Geben Sie schließlich außerhalb der anfänglichen for-Schleife der `FilterBoundingBoxes`-Methode die Ergebnisse zurück:</span><span class="sxs-lookup"><span data-stu-id="154d8-362">Finally, outside of the initial for-loop of the `FilterBoundingBoxes` method, return the results:</span></span>

[!code-csharp [ReturnFilteredBBox](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L246)]

<span data-ttu-id="154d8-363">Prima.</span><span class="sxs-lookup"><span data-stu-id="154d8-363">Great!</span></span> <span data-ttu-id="154d8-364">Nun ist es an der Zeit, diesen Code zusammen mit dem Modell für die Bewertung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="154d8-364">Now it's time to use this code along with the model for scoring.</span></span>

## <a name="use-the-model-for-scoring"></a><span data-ttu-id="154d8-365">Verwenden des Modells für die Bewertung</span><span class="sxs-lookup"><span data-stu-id="154d8-365">Use the model for scoring</span></span>

<span data-ttu-id="154d8-366">Genau wie bei der Nachverarbeitung gibt sind einige Bewertungsschritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="154d8-366">Just like with post-processing, there are a few steps in the scoring steps.</span></span> <span data-ttu-id="154d8-367">Fügen Sie dem Projekt zur Unterstützung dieser Aufgaben eine Klasse hinzu, die die Bewertungslogik enthält.</span><span class="sxs-lookup"><span data-stu-id="154d8-367">To help with this, add a class that will contain the scoring logic to your project.</span></span>

1. <span data-ttu-id="154d8-368">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="154d8-368">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="154d8-369">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *OnnxModelScorer.cs*.</span><span class="sxs-lookup"><span data-stu-id="154d8-369">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *OnnxModelScorer.cs*.</span></span> <span data-ttu-id="154d8-370">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="154d8-370">Then, select the **Add** button.</span></span>

    <span data-ttu-id="154d8-371">Die Datei *OnnxModelScorer.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="154d8-371">The *OnnxModelScorer.cs* file opens in the code editor.</span></span> <span data-ttu-id="154d8-372">Fügen Sie die folgende `using`-Anweisung am Anfang der Datei *OnnxModelScorer.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="154d8-372">Add the following `using` statement to the top of *OnnxModelScorer.cs*:</span></span>

    [!code-csharp [ScorerUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L1-L7)]

    <span data-ttu-id="154d8-373">Fügen Sie innerhalb der `OnnxModelScorer`-Klassendefinition die folgenden Variablen hinzu.</span><span class="sxs-lookup"><span data-stu-id="154d8-373">Inside the `OnnxModelScorer` class definition, add the following variables.</span></span>

    [!code-csharp [InitScorerVars](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L13-L17)]

    <span data-ttu-id="154d8-374">Erstellen Sie direkt darunter einen Konstruktor für die `OnnxModelScorer`-Klasse, die die zuvor definierten Variablen initialisiert.</span><span class="sxs-lookup"><span data-stu-id="154d8-374">Directly below that, create a constructor for the `OnnxModelScorer` class that will initialize the previously defined variables.</span></span>

    [!code-csharp [ScorerCtor](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L19-L24)]

    <span data-ttu-id="154d8-375">Nachdem Sie den Konstruktor erstellt haben, definieren Sie einige Strukturen, die Variablen enthalten, die sich auf das Bild und die Modelleinstellungen beziehen.</span><span class="sxs-lookup"><span data-stu-id="154d8-375">Once you have created the constructor, define a couple of structs that contain variables related to the image and model settings.</span></span> <span data-ttu-id="154d8-376">Erstellen Sie eine Struktur namens `ImageNetSettings`, die die Höhe und Breite enthält, die als Eingabe für das Modell erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="154d8-376">Create a struct called `ImageNetSettings` to contain the height and width expected as input for the model.</span></span>

    [!code-csharp [ImageNetSettingStruct](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L26-L30)]

    <span data-ttu-id="154d8-377">Erstellen Sie anschließend eine weitere Struktur namens `TinyYoloModelSettings`, die die Namen der Eingabe- und Ausgabeschichten des Modells enthält.</span><span class="sxs-lookup"><span data-stu-id="154d8-377">After that, create another struct called `TinyYoloModelSettings` which contains the names of the input and output layers of the model.</span></span> <span data-ttu-id="154d8-378">Um den Namen der Eingabe- und Ausgabeschichten des Modells zu visualisieren, können Sie ein Tool wie [Netron](https://github.com/lutzroeder/netron) verwenden.</span><span class="sxs-lookup"><span data-stu-id="154d8-378">To visualize the name of the input and output layers of the model, you can use a tool like [Netron](https://github.com/lutzroeder/netron).</span></span>

    [!code-csharp [YoloSettingsStruct](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L32-L43)]

    <span data-ttu-id="154d8-379">Erstellen Sie nun den ersten Satz von Methoden, die für die Bewertung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="154d8-379">Next, create the first set of methods use for scoring.</span></span> <span data-ttu-id="154d8-380">Erstellen Sie die `LoadModel`-Methode in der `OnnxModelScorer`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="154d8-380">Create the `LoadModel` method inside of your `OnnxModelScorer` class.</span></span>

    ```csharp
    private ITransformer LoadModel(string modelLocation)
    {

    }
    ```

    <span data-ttu-id="154d8-381">Fügen Sie in der `LoadModel`-Methode den folgenden Code für die Protokollierung hinzu.</span><span class="sxs-lookup"><span data-stu-id="154d8-381">Inside the `LoadModel` method, add the following code for logging.</span></span>

    [!code-csharp [LoadModelLog](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L47-L49)]

    <span data-ttu-id="154d8-382">ML.NET-Pipelines müssen das Datenschema kennen, das verwendet werden soll, wenn die Methode [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit*) aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="154d8-382">ML.NET pipelines need to know the data schema to operate on when the [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit*) method is called.</span></span> <span data-ttu-id="154d8-383">In diesem Fall wird ein Prozess ähnlich dem Training verwendet.</span><span class="sxs-lookup"><span data-stu-id="154d8-383">In this case, a process similar to training will be used.</span></span> <span data-ttu-id="154d8-384">Da jedoch kein tatsächliches Training stattfindet, ist es akzeptabel, eine leere [`IDataView`](xref:Microsoft.ML.IDataView) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="154d8-384">However, because no actual training is happening, it is acceptable to use an empty [`IDataView`](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="154d8-385">Erstellen Sie eine neue [`IDataView`](xref:Microsoft.ML.IDataView) für die Pipeline aus einer leeren Liste.</span><span class="sxs-lookup"><span data-stu-id="154d8-385">Create a new [`IDataView`](xref:Microsoft.ML.IDataView) for the pipeline from an empty list.</span></span>

    [!code-csharp [LoadEmptyIDV](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L52)]

    <span data-ttu-id="154d8-386">Definieren Sie darunter die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="154d8-386">Below that, define the pipeline.</span></span> <span data-ttu-id="154d8-387">Die Pipeline besteht aus vier Transformationen.</span><span class="sxs-lookup"><span data-stu-id="154d8-387">The pipeline will consist of four transforms.</span></span>

    - <span data-ttu-id="154d8-388">[`LoadImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages*) lädt das Bild als Bitmap.</span><span class="sxs-lookup"><span data-stu-id="154d8-388">[`LoadImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages*) loads the image as a Bitmap.</span></span>
    - <span data-ttu-id="154d8-389">[`ResizeImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.ResizeImages*) wandelt das Bild um die angegebene Größe um (in diesem Fall `416 x 416`).</span><span class="sxs-lookup"><span data-stu-id="154d8-389">[`ResizeImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.ResizeImages*) rescales the image to the size specified (in this case, `416 x 416`).</span></span>
    - <span data-ttu-id="154d8-390">[`ExtractPixels`](xref:Microsoft.ML.ImageEstimatorsCatalog.ExtractPixels*) ändert die Pixeldarstellung des Bilds aus einer Bitmap in einen numerischen Vektor.</span><span class="sxs-lookup"><span data-stu-id="154d8-390">[`ExtractPixels`](xref:Microsoft.ML.ImageEstimatorsCatalog.ExtractPixels*) changes the pixel representation of the image from a Bitmap to a numerical vector.</span></span>
    - <span data-ttu-id="154d8-391">[`ApplyOnnxModel`](xref:Microsoft.ML.OnnxCatalog.ApplyOnnxModel*) lädt das ONNX-Modell und verwendet es, um die bereitgestellten Daten zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="154d8-391">[`ApplyOnnxModel`](xref:Microsoft.ML.OnnxCatalog.ApplyOnnxModel*) loads the ONNX model and uses it to score on the data provided.</span></span>

    <span data-ttu-id="154d8-392">Definieren Sie die Pipeline in der `LoadModel`-Methode unter der `data`-Variablen.</span><span class="sxs-lookup"><span data-stu-id="154d8-392">Define your pipeline in the `LoadModel` method below the `data` variable.</span></span>

    [!code-csharp [ScoringPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L55-L58)]

    <span data-ttu-id="154d8-393">Jetzt ist es an der Zeit, das Modell für die Bewertung zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="154d8-393">Now it's time to instantiate the model for scoring.</span></span> <span data-ttu-id="154d8-394">Rufen Sie die [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit*)-Methode für die Pipeline auf, und geben Sie sie zur weiteren Verarbeitung zurück.</span><span class="sxs-lookup"><span data-stu-id="154d8-394">Call the [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit*) method on the pipeline and return it for further processing.</span></span>

    [!code-csharp [FitReturnModel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L61-L63)]

<span data-ttu-id="154d8-395">Nachdem das Modell geladen wurde, kann es verwendet werden, um Vorhersagen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="154d8-395">Once the model is loaded, it can then be used to make predictions.</span></span> <span data-ttu-id="154d8-396">Um diesen Prozess zu ermöglichen, erstellen Sie eine Methode namens `PredictDataUsingModel` unter der `LoadModel`-Methode.</span><span class="sxs-lookup"><span data-stu-id="154d8-396">To facilitate that process, create a method called `PredictDataUsingModel` below the `LoadModel` method.</span></span>

```csharp
private IEnumerable<float[]> PredictDataUsingModel(IDataView testData, ITransformer model)
{

}
```

<span data-ttu-id="154d8-397">Fügen Sie in `PredictDataUsingModel` den folgenden Code für die Protokollierung hinzu.</span><span class="sxs-lookup"><span data-stu-id="154d8-397">Inside the `PredictDataUsingModel`, add the following code for logging.</span></span>

[!code-csharp [PredictDataLog](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L68-L71)]

<span data-ttu-id="154d8-398">Verwenden Sie dann die [`Transform`](xref:Microsoft.ML.ITransformer.Transform*)-Methode, um die Daten zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="154d8-398">Then, use the [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) method to score the data.</span></span>

[!code-csharp [ScoreImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L73)]

<span data-ttu-id="154d8-399">Extrahieren Sie die vorhergesagten Wahrscheinlichkeiten, und geben Sie sie zur weiteren Verarbeitung zurück.</span><span class="sxs-lookup"><span data-stu-id="154d8-399">Extract the predicted probabilities and return them for additional processing.</span></span>

[!code-csharp [ReturnModelOutput](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L75-L77)]

<span data-ttu-id="154d8-400">Nachdem Sie nun beide Schritte eingerichtet haben, kombinieren Sie sie in einer einzigen Methode.</span><span class="sxs-lookup"><span data-stu-id="154d8-400">Now that both steps are set up, combine them into a single method.</span></span> <span data-ttu-id="154d8-401">Fügen Sie unter der `PredictDataUsingModel`-Methode eine Methode namens `Score` hinzu.</span><span class="sxs-lookup"><span data-stu-id="154d8-401">Below the `PredictDataUsingModel` method, add a new method called `Score`.</span></span>

[!code-csharp [ScoreMethod](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L80-L85)]

<span data-ttu-id="154d8-402">Fast geschafft!</span><span class="sxs-lookup"><span data-stu-id="154d8-402">Almost there!</span></span> <span data-ttu-id="154d8-403">Jetzt ist es an der Zeit, alles zusammen einzusetzen.</span><span class="sxs-lookup"><span data-stu-id="154d8-403">Now it's time to put it all to use.</span></span>

## <a name="detect-objects"></a><span data-ttu-id="154d8-404">Erkennen von Objekten</span><span class="sxs-lookup"><span data-stu-id="154d8-404">Detect objects</span></span>

<span data-ttu-id="154d8-405">Nachdem das gesamte Setup nun vollständig ist, ist es an der Zeit, einige Objekte zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="154d8-405">Now that all of the setup is complete, it's time to detect some objects.</span></span> <span data-ttu-id="154d8-406">Fügen Sie zu Beginn Verweise auf den Scorer und den Parser zur Klasse *Program.cs* hinzu.</span><span class="sxs-lookup"><span data-stu-id="154d8-406">Start off by adding references to the scorer and parser in your *Program.cs* class.</span></span>

[!code-csharp [ReferenceScorerParser](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L8-L9)]

### <a name="score-and-parse-model-outputs"></a><span data-ttu-id="154d8-407">Bewerten und Analysieren von Modellausgaben</span><span class="sxs-lookup"><span data-stu-id="154d8-407">Score and parse model outputs</span></span>

<span data-ttu-id="154d8-408">Fügen Sie innerhalb der `Main`-Methode der Klasse *Program.cs* eine try-catch-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="154d8-408">Inside the `Main` method of your *Program.cs* class, add a try-catch statement.</span></span>

```csharp
try
{

}
catch (Exception ex)
{
    Console.WriteLine(ex.ToString());
}
```

<span data-ttu-id="154d8-409">Beginnen Sie innerhalb des `try`-Blocks mit der Implementierung der Objekterkennungslogik.</span><span class="sxs-lookup"><span data-stu-id="154d8-409">Inside of the `try` block, start implementing the object detection logic.</span></span> <span data-ttu-id="154d8-410">Laden Sie die Daten zunächst in eine [`IDataView`](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="154d8-410">First, load the data into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

[!code-csharp [LoadData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L29-L30)]

<span data-ttu-id="154d8-411">Erstellen Sie dann eine Instanz von `OnnxModelScorer`, und verwenden Sie diese zum Bewerten der geladenen Daten.</span><span class="sxs-lookup"><span data-stu-id="154d8-411">Then, create an instance of `OnnxModelScorer` and use it to score the loaded data.</span></span>

[!code-csharp [ScoreData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L33-L36)]

<span data-ttu-id="154d8-412">Jetzt muss der Nachverarbeitungsschritt erfolgen.</span><span class="sxs-lookup"><span data-stu-id="154d8-412">Now it's time for the post-processing step.</span></span> <span data-ttu-id="154d8-413">Erstellen Sie eine Instanz von `YoloOutputParser`, und verwenden Sie diese, um die Modellausgabe zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="154d8-413">Create an instance of `YoloOutputParser` and use it to process the model output.</span></span>

[!code-csharp [ParsePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L39-L44)]

<span data-ttu-id="154d8-414">Nachdem die Modellausgabe verarbeitet wurde, können die Begrenzungsrahmen auf den Bildern gezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="154d8-414">Once the model output has been processed, it's time to draw the bounding boxes on the images.</span></span>

### <a name="visualize-predictions"></a><span data-ttu-id="154d8-415">Visualisieren von Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="154d8-415">Visualize predictions</span></span>

<span data-ttu-id="154d8-416">Nachdem das Modell die Bilder bewertet hat und die Ausgaben verarbeitet wurden, müssen die Begrenzungsrahmen auf das Bild gezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="154d8-416">After the model has scored the images and the outputs have been processed, the bounding boxes have to be drawn on the image.</span></span> <span data-ttu-id="154d8-417">Fügen Sie zu diesem Zweck eine Methode namens `DrawBoundingBox` unter der Methode `GetAbsolutePath` der Datei *Program.cs* hinzu.</span><span class="sxs-lookup"><span data-stu-id="154d8-417">To do so, add a method called `DrawBoundingBox` below the `GetAbsolutePath` method inside of *Program.cs*.</span></span>

```csharp
private static void DrawBoundingBox(string inputImageLocation, string outputImageLocation, string imageName, IList<YoloBoundingBox> filteredBoundingBoxes)
{

}
```

<span data-ttu-id="154d8-418">Laden Sie zuerst das Bild, und rufen Sie die Abmessungen für die Höhe und Breite in der `DrawBoundingBox`-Methode ab.</span><span class="sxs-lookup"><span data-stu-id="154d8-418">First, load the image and get the height and width dimensions in the `DrawBoundingBox` method.</span></span>

[!code-csharp [LoadImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L78-L81)]

<span data-ttu-id="154d8-419">Erstellen Sie dann eine for-each-Schleife, um über jeden der vom Modell erfassten Begrenzungsrahmen zu iterieren.</span><span class="sxs-lookup"><span data-stu-id="154d8-419">Then, create a for-each loop to iterate over each of the bounding boxes detected by the model.</span></span>

```csharp
foreach (var box in filteredBoundingBoxes)
{

}
```

<span data-ttu-id="154d8-420">In der for-each-Schleife rufen Sie die Abmessungen des Begrenzungsrahmens ab.</span><span class="sxs-lookup"><span data-stu-id="154d8-420">Inside of the for-each loop, get the dimensions of the bounding box.</span></span>

[!code-csharp [GetBBoxDimensions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L86-L89)]

<span data-ttu-id="154d8-421">Da die Abmessungen des Begrenzungsrahmens der Modelleingabe von `416 x 416` entsprechen, skalieren Sie die Abmessungen des Begrenzungsrahmens so, dass sie der tatsächlichen Größe des Bilds entsprechen.</span><span class="sxs-lookup"><span data-stu-id="154d8-421">Because the dimensions of the bounding box correspond to the model input of `416 x 416`, scale the bounding box dimensions to match the actual size of the image.</span></span>

[!code-csharp [ScaleImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L92-L95)]

<span data-ttu-id="154d8-422">Definieren Sie dann eine Vorlage für Text, der oberhalb jedes Begrenzungsrahmens angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="154d8-422">Then, define a template for text that will appear above each bounding box.</span></span> <span data-ttu-id="154d8-423">Der Text enthält die Klasse des Objekts innerhalb des entsprechenden Begrenzungsrahmens sowie die Konfidenz.</span><span class="sxs-lookup"><span data-stu-id="154d8-423">The text will contain the class of the object inside of the respective bounding box as well as the confidence.</span></span>

[!code-csharp [DefineBBoxText](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L98)]

<span data-ttu-id="154d8-424">Um auf dem Bild zu zeichnen, konvertieren Sie es in ein [`Graphics`](xref:System.Drawing.Graphics)-Objekt.</span><span class="sxs-lookup"><span data-stu-id="154d8-424">In order to draw on the image, convert it to a [`Graphics`](xref:System.Drawing.Graphics) object.</span></span>

```csharp
using (Graphics thumbnailGraphic = Graphics.FromImage(image))
{

}
```

<span data-ttu-id="154d8-425">Optimieren Sie innerhalb des `using`-Codeblocks die [`Graphics`](xref:System.Drawing.Graphics)-Objekteinstellungen der Grafik.</span><span class="sxs-lookup"><span data-stu-id="154d8-425">Inside the `using` code block, tune the graphic's [`Graphics`](xref:System.Drawing.Graphics) object settings.</span></span>

[!code-csharp [TuneGraphicSettings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L102-L104)]

<span data-ttu-id="154d8-426">Legen Sie darunter die Schriftart- und Farboptionen für den Text und den Begrenzungsrahmen fest.</span><span class="sxs-lookup"><span data-stu-id="154d8-426">Below that, set the font and color options for the text and bounding box.</span></span>

[!code-csharp [SetColorOptions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L106-L114)]

<span data-ttu-id="154d8-427">Erstellen und füllen Sie ein Rechteck oberhalb des Begrenzungsrahmens mithilfe der [`FillRectangle`](xref:System.Drawing.Graphics.FillRectangle*)-Methode, damit es den Text enthält.</span><span class="sxs-lookup"><span data-stu-id="154d8-427">Create and fill a rectangle above the bounding box to contain the text using the [`FillRectangle`](xref:System.Drawing.Graphics.FillRectangle*) method.</span></span> <span data-ttu-id="154d8-428">Dies hilft dabei, den Text vom Hintergrund abzuheben und die Lesbarkeit zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="154d8-428">This will help contrast the text and improve readability.</span></span>

[!code-csharp [DrawTextBackground](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L117)]

<span data-ttu-id="154d8-429">Zeichnen Sie dann den Text und den Begrenzungsrahmen auf dem Bild mithilfe der Methoden [`DrawString`](xref:System.Drawing.Graphics.DrawString*) und [`DrawRectangle`](xref:System.Drawing.Graphics.DrawRectangle*).</span><span class="sxs-lookup"><span data-stu-id="154d8-429">Then, Draw the text and bounding box on the image using the [`DrawString`](xref:System.Drawing.Graphics.DrawString*) and [`DrawRectangle`](xref:System.Drawing.Graphics.DrawRectangle*) methods.</span></span>

[!code-csharp [DrawClassAndBBox](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L118-L121)]

<span data-ttu-id="154d8-430">Fügen Sie außerhalb der for-each-Schleife Code hinzu, um die Bilder im `outputDirectory` zu speichern.</span><span class="sxs-lookup"><span data-stu-id="154d8-430">Outside of the for-each loop, add code to save the images in the `outputDirectory`.</span></span>

[!code-csharp [SaveImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L125-L130)]

<span data-ttu-id="154d8-431">Wenn Sie zusätzliches Feedback dazu erhalten möchten, ob die Anwendung Vorhersagen wie erwartet zur Laufzeit trifft, fügen Sie eine Methode namens `LogDetectedObjects` unterhalb der Methode `DrawBoundingBox` zu der Datei *Program.cs* hinzu, um die erkannten Objekte an die Konsole auszugeben.</span><span class="sxs-lookup"><span data-stu-id="154d8-431">For additional feedback that the application is making predictions as expected at runtime, add a method called `LogDetectedObjects` below the `DrawBoundingBox` method in the *Program.cs* file to output the detected objects to the console.</span></span>

[!code-csharp [LogOutputs](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L133-L143)]

<span data-ttu-id="154d8-432">Nun, da Sie über Hilfsmethoden zum Erstellen von visuellem Feedback aus den Vorhersagen verfügen, sollten Sie eine For-Schleife hinzufügen, um die einzelnen bewerteten Bilder zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="154d8-432">Now that you have helper methods to create visual feedback from the predictions, add a for-loop to iterate over each of the scored images.</span></span>

```csharp
for (var i = 0; i < images.Count(); i++)
{

}
```

<span data-ttu-id="154d8-433">Rufen Sie in der for-Schleife den Namen der Bilddatei und die Begrenzungsrahmen ab, die ihr zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="154d8-433">Inside of the for-loop, get the name of the image file and the bounding boxes associated with it.</span></span>

[!code-csharp [GetImageFileName](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L49-L50)]

<span data-ttu-id="154d8-434">Verwenden Sie darunter die `DrawBoundingBox`-Methode, um die Begrenzungsrahmen auf dem Bild zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="154d8-434">Below that, use the `DrawBoundingBox` method to draw the bounding boxes on the image.</span></span>

[!code-csharp [DrawBBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L52)]

<span data-ttu-id="154d8-435">Verwenden Sie schließlich die Methode `LogDetectedObjects`, um Vorhersagen an die Konsole auszugeben.</span><span class="sxs-lookup"><span data-stu-id="154d8-435">Lastly, use the `LogDetectedObjects` method to output predictions to the console.</span></span>

[!code-csharp [LogPredictionsOutput](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L54)]

<span data-ttu-id="154d8-436">Fügen Sie nach der try-catch-Anweisung zusätzliche Logik hinzu, um anzugeben, dass die Ausführung des Prozesses abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="154d8-436">After the try-catch statement, add additional logic to indicate the process is done running.</span></span>

[!code-csharp [EndProcessLog](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L62-L63)]

<span data-ttu-id="154d8-437">Das ist alles!</span><span class="sxs-lookup"><span data-stu-id="154d8-437">That's it!</span></span>

## <a name="results"></a><span data-ttu-id="154d8-438">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="154d8-438">Results</span></span>

<span data-ttu-id="154d8-439">Nachdem Sie die vorherigen Schritte durchgeführt haben, führen Sie die Konsolen-App aus (STRG+F5).</span><span class="sxs-lookup"><span data-stu-id="154d8-439">After following the previous steps, run your console app (Ctrl + F5).</span></span> <span data-ttu-id="154d8-440">Ihre Ergebnisse sollten der folgenden Ausgabe ähneln.</span><span class="sxs-lookup"><span data-stu-id="154d8-440">Your results should be similar to the following output.</span></span> <span data-ttu-id="154d8-441">Möglicherweise werden Warnungen oder Verarbeitungsnachrichten angezeigt. Diese wurden jedoch aus Gründen der Übersichtlichkeit aus den folgenden Ergebnissen entfernt.</span><span class="sxs-lookup"><span data-stu-id="154d8-441">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

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

<span data-ttu-id="154d8-442">Navigieren Sie zum Verzeichnis `assets/images/output/`, um die Bilder mit Begrenzungsrahmen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="154d8-442">To see the images with bounding boxes, navigate to the `assets/images/output/` directory.</span></span> <span data-ttu-id="154d8-443">Unten sehen Sie ein Beispiel aus einem der verarbeiteten Bilder.</span><span class="sxs-lookup"><span data-stu-id="154d8-443">Below is a sample from one of the processed images.</span></span>

![Beispiel für ein verarbeitetes Bild eines Esszimmers](./media/object-detection-onnx/dinning-room-table-chairs.png)

<span data-ttu-id="154d8-445">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="154d8-445">Congratulations!</span></span> <span data-ttu-id="154d8-446">Sie haben nun durch Wiederverwenden eines vortrainierten `ONNX`-Modells in ML.NET erfolgreich ein Machine Learning-Modell für die Objekterkennung erstellt.</span><span class="sxs-lookup"><span data-stu-id="154d8-446">You've now successfully built a machine learning model for object detection by reusing a pre-trained `ONNX` model in ML.NET.</span></span>

<span data-ttu-id="154d8-447">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx).</span><span class="sxs-lookup"><span data-stu-id="154d8-447">You can find the source code for this tutorial at the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx) repository.</span></span>

<span data-ttu-id="154d8-448">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="154d8-448">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="154d8-449">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="154d8-449">Understand the problem</span></span>
> - <span data-ttu-id="154d8-450">Erfahren Sie, was ONNX ist und wie ONNX mit ML.NET funktioniert.</span><span class="sxs-lookup"><span data-stu-id="154d8-450">Learn what ONNX is and how it works with ML.NET</span></span>
> - <span data-ttu-id="154d8-451">Verstehen des Modells</span><span class="sxs-lookup"><span data-stu-id="154d8-451">Understand the model</span></span>
> - <span data-ttu-id="154d8-452">Wiederverwenden des vortrainierten Modells</span><span class="sxs-lookup"><span data-stu-id="154d8-452">Reuse the pre-trained model</span></span>
> - <span data-ttu-id="154d8-453">Erkennen von Objekten mit einem geladenen Modell</span><span class="sxs-lookup"><span data-stu-id="154d8-453">Detect objects with a loaded model</span></span>

<span data-ttu-id="154d8-454">Sehen Sie sich im GitHub-Repository für Machine Learning-Beispiele nach einem Beispiel für erweiterte Objekterkennung um, damit Sie es untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="154d8-454">Check out the Machine Learning samples GitHub repository to explore an expanded object detection sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="154d8-455">dotnet/machinelearning-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="154d8-455">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx)
