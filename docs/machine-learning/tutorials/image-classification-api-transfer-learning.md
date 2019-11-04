---
title: 'Tutorial: Automatisierte visuelle Überprüfung mithilfe von Transferlernen'
description: In diesem Tutorial wird gezeigt, wie Sie anhand von Transferlernen ein TensorFlow-Modell mit Deep Learning in ML.NET mit der Bilderkennungs-API trainieren, um Bilder von Betonoberflächen als gerissen oder nicht gerissen zu klassifizieren.
author: luisquintanilla
ms.author: luquinta
ms.date: 10/25/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: b8aec80134188811eb80ad1394e5a64d65a3c6f0
ms.sourcegitcommit: 9b2ef64c4fc10a4a10f28a223d60d17d7d249ee8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/26/2019
ms.locfileid: "72961953"
---
# <a name="tutorial-automated-visual-inspection-using-transfer-learning-with-the-mlnet-image-classification-api"></a><span data-ttu-id="ab769-103">Tutorial: Automatisierte visuelle Überprüfung mithilfe von Transferlernen mit der ML.NET-Bildklassifizierungs-API</span><span class="sxs-lookup"><span data-stu-id="ab769-103">Tutorial: Automated visual inspection using transfer learning with the ML.NET Image Classification API</span></span>

<span data-ttu-id="ab769-104">Erfahren Sie, wie Sie ein benutzerdefiniertes Deep-Learning-Modell mithilfe von Transferlernen, einem vorab trainierten TensorFlow-Modell und der ML.NET-Bildklassifizierungs-API trainieren, um Bilder von Betonoberflächen als gerissen oder nicht gerissen zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="ab769-104">Learn how to train a custom deep learning model using transfer learning, a pretrained TensorFlow model and the ML.NET Image Classification API to classify images of concrete surfaces as cracked or uncracked.</span></span>

> [!NOTE]
> <span data-ttu-id="ab769-105">In diesem Tutorial wird eine Vorschauversion der ML.NET-Bildklassifizierungs-API verwendet.</span><span class="sxs-lookup"><span data-stu-id="ab769-105">This tutorial uses a preview version of the ML.NET Image Classification API.</span></span>

<span data-ttu-id="ab769-106">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="ab769-106">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="ab769-107">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="ab769-107">Understand the problem</span></span>
> - <span data-ttu-id="ab769-108">Informationen zur ML.NET-Bildklassifizierungs-API</span><span class="sxs-lookup"><span data-stu-id="ab769-108">Learn about ML.NET Image Classification API</span></span>
> - <span data-ttu-id="ab769-109">Grundlegendes zum vorab trainierten Modell</span><span class="sxs-lookup"><span data-stu-id="ab769-109">Understand the pretrained model</span></span>
> - <span data-ttu-id="ab769-110">Trainieren eines benutzerdefinierten TensorFlow-Bildklassifizierungsmodells mithilfe von Transferlernen</span><span class="sxs-lookup"><span data-stu-id="ab769-110">Use transfer learning to train a custom TensorFlow image classification model</span></span>
> - <span data-ttu-id="ab769-111">Klassifizieren von Bildern mit dem benutzerdefinierten Modell</span><span class="sxs-lookup"><span data-stu-id="ab769-111">Classify images with the custom model</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ab769-112">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="ab769-112">Prerequisites</span></span>

- <span data-ttu-id="ab769-113">[Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="ab769-113">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="image-classification-transfer-learning-sample-overview"></a><span data-ttu-id="ab769-114">Beispielübersicht zur Bildklassifizierung mit Transferlernen</span><span class="sxs-lookup"><span data-stu-id="ab769-114">Image classification transfer learning sample overview</span></span>

<span data-ttu-id="ab769-115">Bei diesem Beispiel handelt es sich um eine C#.NET Core-Konsolenanwendung, die Bilder mit einem vorab mit Deep Learning trainierten TensorFlow-Modell klassifiziert.</span><span class="sxs-lookup"><span data-stu-id="ab769-115">This sample is a C# .NET Core console application that classifies images using a pretrained deep learning TensorFlow model.</span></span> <span data-ttu-id="ab769-116">Den Code für dieses Beispiel finden Sie im [dotnet/machinelearning-Beispielrepository](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="ab769-116">The code for this sample can be found on the [dotnet/machinelearning-samples repository](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary) on GitHub.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="ab769-117">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="ab769-117">Understand the problem</span></span>

<span data-ttu-id="ab769-118">Bildklassifizierung ist ein Problem des maschinellen Sehens.</span><span class="sxs-lookup"><span data-stu-id="ab769-118">Image classification is a computer vision problem.</span></span> <span data-ttu-id="ab769-119">Bei der Bildklassifizierung wird ein Bild eingegeben, das dann in eine bestimmte Klasse eingeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="ab769-119">Image classification takes an image as input and categorizes it into a prescribed class.</span></span> <span data-ttu-id="ab769-120">Die Bildklassifizierung kann zum Beispiel in diesen Szenarios hilfreich sein:</span><span class="sxs-lookup"><span data-stu-id="ab769-120">Some scenarios where image classification is useful include:</span></span>

- <span data-ttu-id="ab769-121">Gesichtserkennung</span><span class="sxs-lookup"><span data-stu-id="ab769-121">Facial recognition</span></span>
- <span data-ttu-id="ab769-122">Emotionserkennung</span><span class="sxs-lookup"><span data-stu-id="ab769-122">Emotion detection</span></span>
- <span data-ttu-id="ab769-123">Medizinische Diagnose</span><span class="sxs-lookup"><span data-stu-id="ab769-123">Medical diagnosis</span></span>
- <span data-ttu-id="ab769-124">Orientierungspunkterkennung</span><span class="sxs-lookup"><span data-stu-id="ab769-124">Landmark detection</span></span>

<span data-ttu-id="ab769-125">In diesem Tutorial wird ein benutzerdefiniertes Bildklassifizierungsmodell trainiert, um eine automatisierte visuelle Überprüfung von Brückenbelägen durchzuführen, bei der durch Risse unterbrochene Strukturen identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="ab769-125">This tutorial trains a custom image classification model to perform automated visual inspection of bridge decks to identify structures that are damaged by cracks.</span></span>

## <a name="mlnet-image-classification-api"></a><span data-ttu-id="ab769-126">ML.NET-Bildklassifizierungs-API</span><span class="sxs-lookup"><span data-stu-id="ab769-126">ML.NET Image Classification API</span></span>

<span data-ttu-id="ab769-127">ML.NET bietet verschiedene Methoden zum Durchführen einer Bildklassifizierung.</span><span class="sxs-lookup"><span data-stu-id="ab769-127">ML.NET provides various ways of performing image classification.</span></span> <span data-ttu-id="ab769-128">In diesem Tutorial wird die Methode des Transferlernens unter Verwendung der Bildklassifizierungs-API angewendet.</span><span class="sxs-lookup"><span data-stu-id="ab769-128">This tutorial applies transfer learning using the Image Classification API.</span></span> <span data-ttu-id="ab769-129">Die Bildklassifizierungs-API nutzt [TensorFlow.NET](https://github.com/SciSharp/TensorFlow.NET), eine Low-Level-Bibliothek, die C#-Bindungen für die TensorFlow-C++-API bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ab769-129">The Image Classification API makes use of [TensorFlow.NET](https://github.com/SciSharp/TensorFlow.NET), a low-level library that provides C# bindings for the TensorFlow C++ API.</span></span>

## <a name="what-is-transfer-learning"></a><span data-ttu-id="ab769-130">Was ist Übertragungslernen?</span><span class="sxs-lookup"><span data-stu-id="ab769-130">What is transfer learning?</span></span>

<span data-ttu-id="ab769-131">Beim Transferlernen werden Erkenntnisse aus der Lösung eines Problems für ein anderes verwandtes Problem genutzt.</span><span class="sxs-lookup"><span data-stu-id="ab769-131">Transfer learning applies knowledge gained from solving one problem to another related problem.</span></span>

<span data-ttu-id="ab769-132">Das von Grund auf neue Trainieren eines Deep-Learning-Modells erfordert das Festlegen mehrerer Parameter, zahlreiche bezeichnete Trainingsdaten und eine große Menge an Computeressourcen (Hunderte von GPU-Stunden).</span><span class="sxs-lookup"><span data-stu-id="ab769-132">Training a deep learning model from scratch requires setting several parameters, a large amount of labeled training data, and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="ab769-133">Die Verwendung eines vorab trainierten Modells zusammen mit dem Transferlernen ermöglicht es Ihnen, den Trainingsprozess zu verkürzen.</span><span class="sxs-lookup"><span data-stu-id="ab769-133">Using a pretrained model along with transfer learning allows you to shortcut the training process.</span></span> 

## <a name="training-process"></a><span data-ttu-id="ab769-134">Trainingsprozess</span><span class="sxs-lookup"><span data-stu-id="ab769-134">Training process</span></span>

<span data-ttu-id="ab769-135">Die Bildklassifizierungs-API startet den Trainingsprozess, indem das vorab trainierte TensorFlow-Modell geladen wird.</span><span class="sxs-lookup"><span data-stu-id="ab769-135">The Image Classification API starts the training process by loading a pretrained TensorFlow model.</span></span> <span data-ttu-id="ab769-136">Der Trainingsprozess setzt sich aus zwei Schritten zusammen:</span><span class="sxs-lookup"><span data-stu-id="ab769-136">The training process consists of two steps:</span></span>

1. <span data-ttu-id="ab769-137">Engpassphase</span><span class="sxs-lookup"><span data-stu-id="ab769-137">Bottleneck phase</span></span>
2. <span data-ttu-id="ab769-138">Trainingsphase</span><span class="sxs-lookup"><span data-stu-id="ab769-138">Training phase</span></span>

![Trainingsschritte](./media/image-classification-api-transfer-learning/training.png)

### <a name="bottleneck-phase"></a><span data-ttu-id="ab769-140">Engpassphase</span><span class="sxs-lookup"><span data-stu-id="ab769-140">Bottleneck phase</span></span>

<span data-ttu-id="ab769-141">Während der Engpassphase werden die Trainingsbilder geladen, wobei die Pixelwerte als Eingabe dienen, oder aber Features für die fixierten Ebenen des vorab trainierten Modells.</span><span class="sxs-lookup"><span data-stu-id="ab769-141">During the bottleneck phase, the set of training images is loaded and the pixel values are used as input, or features, for the frozen layers of the pretrained model.</span></span> <span data-ttu-id="ab769-142">Die fixierten Ebenen umfassen sämtliche Ebenen im neuronalen Netz bis hin zur vorletzte Ebene, die inoffiziell auch als Engpassebene bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="ab769-142">The frozen layers include all of the layers in the neural network up to the penultimate layer, informally known as the bottleneck layer.</span></span> <span data-ttu-id="ab769-143">Diese Ebenen werden „fixiert“ genannt, da für diese kein Training stattfindet und Vorgänge lediglich weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ab769-143">These layers are referred to as frozen because no training will occur on these layers and operations are pass-through.</span></span> <span data-ttu-id="ab769-144">In diesen fixierten Ebenen werden die zugrunde liegenden Muster berechnet, anhand derer ein Modell zwischen den verschiedenen Klassen unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="ab769-144">It's at these frozen layers where the lower-level patterns that help a model differentiate between the different classes are computed.</span></span> <span data-ttu-id="ab769-145">Je mehr Ebenen es gibt, desto rechenintensiver ist dieser Schritt.</span><span class="sxs-lookup"><span data-stu-id="ab769-145">The larger the number of layers, the more computationally intensive this step is.</span></span> <span data-ttu-id="ab769-146">Da es sich hierbei um eine einmalige Berechnung handelt, können die Ergebnisse zwischengespeichert und in späteren Durchläufen verwendet werden, wenn mit verschiedenen Parametern experimentiert wird.</span><span class="sxs-lookup"><span data-stu-id="ab769-146">Fortunately, since this is a one-time calculation, the results can be cached and used in later runs when experimenting with different parameters.</span></span>

### <a name="training-phase"></a><span data-ttu-id="ab769-147">Trainingsphase</span><span class="sxs-lookup"><span data-stu-id="ab769-147">Training phase</span></span>

<span data-ttu-id="ab769-148">Sobald die Ausgabewerte aus der Engpassphase berechnet sind, dienen sie als Eingabe für das nochmalige Training der letzten Ebene des Modells.</span><span class="sxs-lookup"><span data-stu-id="ab769-148">Once the output values from the bottleneck phase are computed, they are used as input to retrain the final layer of the model.</span></span> <span data-ttu-id="ab769-149">Dieser Prozess ist iterativ und wird so oft ausgeführt, wie durch Modellparameter angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="ab769-149">This process is iterative and runs for the number of times specified by model parameters.</span></span> <span data-ttu-id="ab769-150">Bei jeder Ausführung werden Verlust und Genauigkeit ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="ab769-150">During each run, the loss and accuracy are evaluated.</span></span> <span data-ttu-id="ab769-151">Anschließend werden die entsprechenden Anpassungen zur Verbesserung des Modells vorgenommen, um so den Verlust zu minimieren und die Genauigkeit zu maximieren.</span><span class="sxs-lookup"><span data-stu-id="ab769-151">Then, the appropriate adjustments are made to improve the model with the goal of minimizing the loss and maximizing the accuracy.</span></span> <span data-ttu-id="ab769-152">Nach Abschluss des Trainings verfügen Sie über zwei Modellformate.</span><span class="sxs-lookup"><span data-stu-id="ab769-152">Once training is finished, two model formats are output.</span></span> <span data-ttu-id="ab769-153">Eines wird als `.pb`-Version des Modells und das andere als für ML.NET serialisierte `.zip`-Version des Modells bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ab769-153">One of them is the `.pb` version of the model and the other is the `.zip` ML.NET serialized version of the model.</span></span> <span data-ttu-id="ab769-154">Für die Arbeit in von ML.NET unterstützten Umgebungen wird die `.zip`-Version des Modells empfohlen.</span><span class="sxs-lookup"><span data-stu-id="ab769-154">When working in environments supported by ML.NET, it is recommended to use the `.zip` version of the model.</span></span> <span data-ttu-id="ab769-155">In Umgebungen, in denen ML.NET nicht unterstützt wird, haben Sie jedoch die Möglichkeit, die `.pb`-Version zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ab769-155">However, in environments where ML.NET is not supported, you have the option of using the `.pb` version.</span></span>

## <a name="understand-the-pretrained-model"></a><span data-ttu-id="ab769-156">Grundlegendes zum vorab trainierten Modell</span><span class="sxs-lookup"><span data-stu-id="ab769-156">Understand the pretrained model</span></span>

<span data-ttu-id="ab769-157">Das in diesem Tutorial verwendete vorab trainierte Modell ist die 101-Ebenen-Variante des Modells „Residual Network (ResNet) v2“.</span><span class="sxs-lookup"><span data-stu-id="ab769-157">The pretrained model used in this tutorial is the 101-layer variant of the Residual Network (ResNet) v2 model.</span></span> <span data-ttu-id="ab769-158">Das Originalmodell ist darauf trainiert, Bilder in tausend Kategorien einzuteilen.</span><span class="sxs-lookup"><span data-stu-id="ab769-158">The original model is trained to classify images into a thousand categories.</span></span> <span data-ttu-id="ab769-159">Das Modell verwendet ein Bild der Größe 224 × 224 als Eingabe und gibt die Klassenwahrscheinlichkeiten für jede der Klassen aus, für die es trainiert ist.</span><span class="sxs-lookup"><span data-stu-id="ab769-159">The model takes as input an image of size 224 x 224 and outputs the class probabilities for each of the classes it's trained on.</span></span> <span data-ttu-id="ab769-160">Ein Teil dieses Modells wird verwendet, um ein neues Modell mit benutzerdefinierten Bildern zu trainieren, damit dieses Vorhersagen für zwei Klassen treffen kann.</span><span class="sxs-lookup"><span data-stu-id="ab769-160">Part of this model is used to train a new model using custom images to make predictions between two classes.</span></span> 

## <a name="create-console-application"></a><span data-ttu-id="ab769-161">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="ab769-161">Create console application</span></span>

<span data-ttu-id="ab769-162">Nachdem Sie nun grundlegende Kenntnisse über das Transferlernen und die Bildklassifizierungs-API haben, ist es an der Zeit, die Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ab769-162">Now that you have a general understanding of transfer learning and the Image Classification API, it's time to build the application.</span></span>

1. <span data-ttu-id="ab769-163">Erstellen Sie eine **.NET Core-Konsolenanwendung in C#** namens „DeepLearning_ImageClassification_Binary“.</span><span class="sxs-lookup"><span data-stu-id="ab769-163">Create a **C# .NET Core Console Application** called "DeepLearning_ImageClassification_Binary".</span></span>
1. <span data-ttu-id="ab769-164">Installieren Sie das NuGet-Paket **Microsoft.ML 1.4.0-preview2**:</span><span class="sxs-lookup"><span data-stu-id="ab769-164">Install the **Microsoft.ML 1.4.0-preview2** NuGet Package:</span></span>
    1. <span data-ttu-id="ab769-165">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="ab769-165">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span>
    1. <span data-ttu-id="ab769-166">Wählen Sie als Paketquelle „nuget.org“ aus.</span><span class="sxs-lookup"><span data-stu-id="ab769-166">Choose "nuget.org" as the Package source.</span></span>
    1. <span data-ttu-id="ab769-167">Wählen Sie die Registerkarte **Durchsuchen** aus.</span><span class="sxs-lookup"><span data-stu-id="ab769-167">Select the **Browse** tab.</span></span>
    1. <span data-ttu-id="ab769-168">Aktivieren Sie das Kontrollkästchen **Vorabversion einbeziehen**.</span><span class="sxs-lookup"><span data-stu-id="ab769-168">Check the **Include prerelease** checkbox.</span></span>
    1. <span data-ttu-id="ab769-169">Suchen Sie nach **Microsoft.ML**.</span><span class="sxs-lookup"><span data-stu-id="ab769-169">Search for **Microsoft.ML**.</span></span>
    1. <span data-ttu-id="ab769-170">Wählen Sie die Schaltfläche **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="ab769-170">Select the **Install** button.</span></span>
    1. <span data-ttu-id="ab769-171">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="ab769-171">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>
    1. <span data-ttu-id="ab769-172">Wiederholen Sie die Schritte für **Microsoft.ML.Dnn 0.16.0-preview2** und **Microsoft.ML.ImageAnalytics 1.4.0-preview2**.</span><span class="sxs-lookup"><span data-stu-id="ab769-172">Repeat these steps for **Microsoft.ML.Dnn 0.16.0-preview2** and **Microsoft.ML.ImageAnalytics 1.4.0-preview2**.</span></span>

### <a name="prepare-and-understand-the-data"></a><span data-ttu-id="ab769-173">Vorbereiten und Verstehen der Daten</span><span class="sxs-lookup"><span data-stu-id="ab769-173">Prepare and understand the data</span></span>

> [!NOTE]
> <span data-ttu-id="ab769-174">Die Datasets für dieses Tutorial stammen von Marc Maguire, Sattar Dorafshan und Robert J. Thomas, „SDNET2018: A concrete crack image dataset for machine learning applications“ (2018).</span><span class="sxs-lookup"><span data-stu-id="ab769-174">The datasets for this tutorial are from Maguire, Marc; Dorafshan, Sattar; and Thomas, Robert J., "SDNET2018: A concrete crack image dataset for machine learning applications" (2018).</span></span> <span data-ttu-id="ab769-175">Durchsuchen Sie alle Datasets.</span><span class="sxs-lookup"><span data-stu-id="ab769-175">Browse all Datasets.</span></span> <span data-ttu-id="ab769-176">Dokument 48.</span><span class="sxs-lookup"><span data-stu-id="ab769-176">Paper 48.</span></span> <span data-ttu-id="ab769-177">https://digitalcommons.usu.edu/all_datasets/48</span><span class="sxs-lookup"><span data-stu-id="ab769-177">https://digitalcommons.usu.edu/all_datasets/48</span></span>

<span data-ttu-id="ab769-178">SDNET2018 ist ein Bilddataset, das Anmerkungen für gerissene und nicht gerissene Betonstrukturen (Brückenbeläge, Mauern und Gehwege) enthält.</span><span class="sxs-lookup"><span data-stu-id="ab769-178">SDNET2018 is an image dataset that contains annotations for cracked and non-cracked concrete structures (bridge decks, walls, and pavement).</span></span> 

![Beispiele für Brückenbeläge des SDNET2018-Datasets](./media/image-classification-api-transfer-learning/sdnet2018decksamples.png)

<span data-ttu-id="ab769-180">Die Daten sind in drei Unterverzeichnissen organisiert:</span><span class="sxs-lookup"><span data-stu-id="ab769-180">The data is organized in three subdirectories:</span></span>

- <span data-ttu-id="ab769-181">D enthält Bilder von Brückenbelägen</span><span class="sxs-lookup"><span data-stu-id="ab769-181">D contains bridge deck images</span></span>
- <span data-ttu-id="ab769-182">P enthält Bilder von Gehwegen</span><span class="sxs-lookup"><span data-stu-id="ab769-182">P contains pavement images</span></span>
- <span data-ttu-id="ab769-183">W enthält Bilder von Mauern</span><span class="sxs-lookup"><span data-stu-id="ab769-183">W contains wall images</span></span>

<span data-ttu-id="ab769-184">Jedes dieser Unterverzeichnisse enthält zwei zusätzliche Unterverzeichnisse mit Präfixen:</span><span class="sxs-lookup"><span data-stu-id="ab769-184">Each of these subdirectories contains two additional prefixed subdirectories:</span></span>

- <span data-ttu-id="ab769-185">C ist das Präfix für gerissene Oberflächen</span><span class="sxs-lookup"><span data-stu-id="ab769-185">C is the prefix used for cracked surfaces</span></span>
- <span data-ttu-id="ab769-186">U ist das Präfix für nicht gerissene Oberflächen</span><span class="sxs-lookup"><span data-stu-id="ab769-186">U is the prefix used for uncracked surfaces</span></span>

<span data-ttu-id="ab769-187">In diesem Tutorial werden ausschließlich Bilder von Brückenbelägen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ab769-187">In this tutorial, only bridge deck images are used.</span></span>

1. <span data-ttu-id="ab769-188">Laden Sie das [Dataset](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/assets.zip) herunter, und entpacken Sie es.</span><span class="sxs-lookup"><span data-stu-id="ab769-188">Download the [dataset](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/assets.zip) and unzip.</span></span>
1. <span data-ttu-id="ab769-189">Erstellen Sie in Ihrem Projekt ein Verzeichnis mit dem Namen „assets“, um darin die Datasetdateien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ab769-189">Create a directory named "assets" in your project to save your dataset files.</span></span>
1. <span data-ttu-id="ab769-190">Kopieren Sie die Unterverzeichnisse *CD* und *UD* aus dem zuletzt entpackten Verzeichnis in das Verzeichnis *assets*.</span><span class="sxs-lookup"><span data-stu-id="ab769-190">Copy the *CD* and *UD* subdirectories from the recently unzipped directory to the *assets* directory.</span></span>

### <a name="create-input-and-output-classes"></a><span data-ttu-id="ab769-191">Erstellen von Eingabe- und Ausgabeklassen</span><span class="sxs-lookup"><span data-stu-id="ab769-191">Create input and output classes</span></span>

1. <span data-ttu-id="ab769-192">Öffnen Sie die Datei *Program.cs*, und ersetzen Sie die vorhandenen `using`-Anweisungen am Anfang der Datei durch die folgenden Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="ab769-192">Open the *Program.cs* file and replace the existing `using` statements at the top of the file with the following:</span></span>

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L1-L7)]

1. <span data-ttu-id="ab769-193">Erstellen Sie in der Datei *Program.cs* unter der `Program`-Klasse eine Klasse mit dem Namen `ImageData`.</span><span class="sxs-lookup"><span data-stu-id="ab769-193">Below the `Program` class in *Program.cs*, create a class called `ImageData`.</span></span> <span data-ttu-id="ab769-194">Diese Klasse wird verwendet, um die ursprünglich geladenen Daten darzustellen.</span><span class="sxs-lookup"><span data-stu-id="ab769-194">This class is used to represent the initially loaded data.</span></span> 

    [!code-csharp [ImageDataClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L135-L140)]

    <span data-ttu-id="ab769-195">`ImageData` enthält die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="ab769-195">`ImageData` contains the following properties:</span></span>

    - <span data-ttu-id="ab769-196">`ImagePath` ist der vollqualifizierte Pfad, in dem das Bild gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="ab769-196">`ImagePath` is the fully qualified path where the image is stored.</span></span>
    - <span data-ttu-id="ab769-197">`Label` ist die Kategorie, zu der das Bild gehört.</span><span class="sxs-lookup"><span data-stu-id="ab769-197">`Label` is the category the image belongs to.</span></span> <span data-ttu-id="ab769-198">Dies ist der vorherzusagende Wert.</span><span class="sxs-lookup"><span data-stu-id="ab769-198">This is the value to predict.</span></span>

1. <span data-ttu-id="ab769-199">Erstellen Sie Klassen für Ihre Eingabe- und Ausgabedaten.</span><span class="sxs-lookup"><span data-stu-id="ab769-199">Create classes for your input and output data</span></span>

    1. <span data-ttu-id="ab769-200">Definieren Sie unter der `ImageData`-Klasse das Schema Ihrer Eingabedaten in einer neuen Klasse namens `ModelInput`.</span><span class="sxs-lookup"><span data-stu-id="ab769-200">Below the `ImageData` class, define the schema of your input data in a new class called `ModelInput`.</span></span>

        [!code-csharp [ModelInputClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L142-L151)]

        <span data-ttu-id="ab769-201">`ModelInput` enthält die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="ab769-201">`ModelInput` contains the following properties:</span></span>

        - <span data-ttu-id="ab769-202">`ImagePath` ist der vollqualifizierte Pfad, in dem das Bild gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="ab769-202">`ImagePath` is the fully qualified path where the image is stored.</span></span> 
        - <span data-ttu-id="ab769-203">`Label` ist die Kategorie, zu der das Bild gehört.</span><span class="sxs-lookup"><span data-stu-id="ab769-203">`Label` is the category the image belongs to.</span></span> <span data-ttu-id="ab769-204">Dies ist der vorherzusagende Wert.</span><span class="sxs-lookup"><span data-stu-id="ab769-204">This is the value to predict.</span></span>
        - <span data-ttu-id="ab769-205">`Image` ist die `byte[]`-Darstellung des Bilds.</span><span class="sxs-lookup"><span data-stu-id="ab769-205">`Image` is the `byte[]` representation of the image.</span></span> <span data-ttu-id="ab769-206">Bei dem Modell wird erwartet, dass Bilddaten diesen Typ für das Training aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ab769-206">The model expects image data to be of this type for training.</span></span>
        - <span data-ttu-id="ab769-207">`LabelAsKey` ist die numerische Darstellung von `Label`.</span><span class="sxs-lookup"><span data-stu-id="ab769-207">`LabelAsKey` is the numerical representation of the `Label`.</span></span> 

        <span data-ttu-id="ab769-208">Nur `Image` und `LabelAsKey` werden verwendet, um das Modell zu trainieren und Vorhersagen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="ab769-208">Only `Image` and `LabelAsKey` are used to train the model and make predictions.</span></span> <span data-ttu-id="ab769-209">Die Eigenschaften `ImagePath` und `Label` werden beibehalten, damit einfacher auf den Namen und die Kategorie der ursprünglichen Bilddatei zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="ab769-209">The `ImagePath` and `Label` properties are kept for convenience to access the original image file name and category.</span></span>

    1. <span data-ttu-id="ab769-210">Anschließend definieren Sie unter der `ModelInput`-Klasse das Schema Ihrer Ausgabedaten in einer neuen Klasse namens `ModelOutput`.</span><span class="sxs-lookup"><span data-stu-id="ab769-210">Then, below the `ModelInput` class, define the schema of your output data in a new class called `ModelOutput`.</span></span> 

        [!code-csharp [ModelOutputClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L153-L160)]

        <span data-ttu-id="ab769-211">`ModelOutput` enthält die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="ab769-211">`ModelOutput` contains the following properties:</span></span>

        - <span data-ttu-id="ab769-212">`ImagePath` ist der vollqualifizierte Pfad, in dem das Bild gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="ab769-212">`ImagePath` is the fully qualified path where the image is stored.</span></span>
        - <span data-ttu-id="ab769-213">`Label` ist die ursprüngliche Kategorie, zu der das Bild gehört.</span><span class="sxs-lookup"><span data-stu-id="ab769-213">`Label` is the original category the image belongs to.</span></span> <span data-ttu-id="ab769-214">Dies ist der vorherzusagende Wert.</span><span class="sxs-lookup"><span data-stu-id="ab769-214">This is the value to predict.</span></span> 
        - <span data-ttu-id="ab769-215">`PredictedLabel` ist der vom Modell vorhergesagte Wert.</span><span class="sxs-lookup"><span data-stu-id="ab769-215">`PredictedLabel` is the value predicted by the model.</span></span>

        <span data-ttu-id="ab769-216">Ähnlich wie bei `ModelInput` ist nur `PredictedLabel` für Vorhersagen erforderlich, da dies die vom Modell getroffene Vorhersage enthält.</span><span class="sxs-lookup"><span data-stu-id="ab769-216">Similar to `ModelInput`, only the `PredictedLabel` is required to make predictions since it contains the prediction made by the model.</span></span> <span data-ttu-id="ab769-217">Die Eigenschaften `ImagePath` und `Label` werden beibehalten, damit einfacher auf den Namen und die Kategorie der ursprünglichen Bilddatei zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="ab769-217">The `ImagePath` and `Label` properties are retained for convenience to access the original image file name and category.</span></span>

### <a name="define-paths-and-initialize-variables"></a><span data-ttu-id="ab769-218">Definieren von Pfaden und Initialisieren von Variablen</span><span class="sxs-lookup"><span data-stu-id="ab769-218">Define paths and initialize variables</span></span>

1. <span data-ttu-id="ab769-219">Definieren Sie innerhalb der `Main`-Methode den Speicherort Ihrer Objekte.</span><span class="sxs-lookup"><span data-stu-id="ab769-219">Inside the `Main` method, define the location of your assets.</span></span>

    [!code-csharp [DefinePaths](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L15-L16)]

1. <span data-ttu-id="ab769-220">Initialisieren Sie dann die `mlContext`-Variable mit einer neuen Instanz von [MLContext](xref:Microsoft.ML.MLContext).</span><span class="sxs-lookup"><span data-stu-id="ab769-220">Then, initialize the `mlContext` variable with a new instance of [MLContext](xref:Microsoft.ML.MLContext).</span></span>

    [!code-csharp [MLContext](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L18)]

<span data-ttu-id="ab769-221">Die [MLContext](xref:Microsoft.ML.MLContext)-Klasse ist der Startpunkt für alle ML.NET-Vorgänge. Durch das Initialisieren von MLContext wird eine neue ML.NET-Umgebung erstellt, die für mehrere Objekte des Modellerstellungsworkflows verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ab769-221">The [MLContext](xref:Microsoft.ML.MLContext) class is a starting point for all ML.NET operations, and initializing mlContext creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="ab769-222">Die Klasse ähnelt dem Konzept von `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="ab769-222">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="ab769-223">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="ab769-223">Load the data</span></span>

### <a name="create-data-loading-utility-method"></a><span data-ttu-id="ab769-224">Erstellen einer Hilfsmethode zum Laden von Daten</span><span class="sxs-lookup"><span data-stu-id="ab769-224">Create data loading utility method</span></span>

<span data-ttu-id="ab769-225">Die Bilder werden in zwei Unterverzeichnissen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ab769-225">The images are stored in two subdirectories.</span></span> <span data-ttu-id="ab769-226">Vor dem Laden der Daten müssen diese in eine Liste mit `ImageData`-Objekten formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="ab769-226">Before loading the data, it needs to be formatted into a list of `ImageData` objects.</span></span> <span data-ttu-id="ab769-227">Erstellen Sie hierzu die `LoadImagesFromDirectory`-Methode unter der `Main`-Methode.</span><span class="sxs-lookup"><span data-stu-id="ab769-227">To do so, create the `LoadImagesFromDirectory` method below the `Main` method.</span></span>

```csharp
public static IEnumerable<ImageData> LoadImagesFromDirectory(string folder, bool useFolderNameAsLabel = true)
{

}
```

1. <span data-ttu-id="ab769-228">Fügen Sie in `LoadImagesDirectory` den folgenden Code hinzu, um alle Dateipfade aus den Unterverzeichnissen abzurufen:</span><span class="sxs-lookup"><span data-stu-id="ab769-228">Inside the `LoadImagesDirectory` add the following code to get all of the file paths from the subdirectories:</span></span>

    [!code-csharp [GetFiles](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L102-L103)]

1. <span data-ttu-id="ab769-229">Durchlaufen Sie dann die einzelnen Dateien mithilfe einer `foreach`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ab769-229">Then, iterate through each of the files using a `foreach` statement.</span></span>

    ```csharp
    foreach (var file in files)
    {

    }
    ```

1. <span data-ttu-id="ab769-230">Überprüfen Sie, ob in der `foreach`-Anweisung die Dateierweiterungen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="ab769-230">Inside the `foreach` statement, check that the file extensions are supported.</span></span> <span data-ttu-id="ab769-231">Die Bildklassifizierungs-API unterstützt JPEG- und PNG-Formate.</span><span class="sxs-lookup"><span data-stu-id="ab769-231">The Image Classification API supports JPEG and PNG formats.</span></span>

    [!code-csharp [CheckExtension](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L107-L108)]

1. <span data-ttu-id="ab769-232">Rufen Sie anschließend die Bezeichnung für die Datei ab.</span><span class="sxs-lookup"><span data-stu-id="ab769-232">Then, get the label for the file.</span></span> <span data-ttu-id="ab769-233">Wenn der `useFolderNameAsLabel`-Parameter auf `true` festgelegt ist, wird das übergeordnete Verzeichnis, in dem die Datei gespeichert wird, als Bezeichnung verwendet.</span><span class="sxs-lookup"><span data-stu-id="ab769-233">If the `useFolderNameAsLabel` parameter is set to `true`, then the parent directory where the file is saved is used as the label.</span></span> <span data-ttu-id="ab769-234">Andernfalls wird erwartet, dass die Bezeichnung ein Präfix des Dateinamens oder der Dateiname selbst ist.</span><span class="sxs-lookup"><span data-stu-id="ab769-234">Otherwise, it expects the label to be a prefix of the file name or the file name itself.</span></span>

    [!code-csharp [GetLabel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L110-L124)]

1. <span data-ttu-id="ab769-235">Abschließend erstellen Sie eine neue Instanz von `ModelInput`.</span><span class="sxs-lookup"><span data-stu-id="ab769-235">Finally, create a new instance of `ModelInput`.</span></span>

    [!code-csharp [CreateImageData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L126-L130)]

### <a name="prepare-the-data"></a><span data-ttu-id="ab769-236">Vorbereiten der Daten</span><span class="sxs-lookup"><span data-stu-id="ab769-236">Prepare the data</span></span>

1. <span data-ttu-id="ab769-237">Verwenden Sie in der `Main`-Methode die `LoadFromDirectory`-Hilfsmethode, um die Liste der Bilder abzurufen, die für das Training verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ab769-237">Back in the `Main` method, use the `LoadFromDirectory` utility method to get the list of images used for training.</span></span>

    [!code-csharp [LoadImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L20)]

1. <span data-ttu-id="ab769-238">Laden Sie dann die Bilder mithilfe der [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*)-Methode in eine [`IDataView`](xref:Microsoft.ML.IDataView)-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ab769-238">Then, load the images into an [`IDataView`](xref:Microsoft.ML.IDataView) using the [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) method.</span></span>

    [!code-csharp [CreateIDataView](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L22)]    

1. <span data-ttu-id="ab769-239">Die Daten werden in der Reihenfolge geladen, in der sie aus den Verzeichnissen gelesen wurden.</span><span class="sxs-lookup"><span data-stu-id="ab769-239">The data is loaded in the order it was read from the directories.</span></span> <span data-ttu-id="ab769-240">Um die Daten auszugleichen, mischen Sie sie zufällig mithilfe der [`ShuffleRows`](xref:Microsoft.ML.DataOperationsCatalog.ShuffleRows*)-Methode.</span><span class="sxs-lookup"><span data-stu-id="ab769-240">To balance the data, shuffle it using the [`ShuffleRows`](xref:Microsoft.ML.DataOperationsCatalog.ShuffleRows*) method.</span></span>

    [!code-csharp [ShuffleRows](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L24)]

1. <span data-ttu-id="ab769-241">Bei Modellen für maschinelles Lernen wird eine Eingabe im numerischen Format erwartet.</span><span class="sxs-lookup"><span data-stu-id="ab769-241">Machine learning models expect input to be in numerical format.</span></span> <span data-ttu-id="ab769-242">Daher muss vor dem Training eine Vorverarbeitung der Daten durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ab769-242">Therefore, some preprocessing needs to be done on the data prior to training.</span></span> <span data-ttu-id="ab769-243">Erstellen Sie eine [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601)-Klasse aus den Transformationen [`MapValueToKey`](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey*) und [`LoadImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages*).</span><span class="sxs-lookup"><span data-stu-id="ab769-243">Create an [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) made up of the [`MapValueToKey`](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey*) and [`LoadImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages*) transforms.</span></span> <span data-ttu-id="ab769-244">Die `MapValueToKey`-Transformation übernimmt den kategorischen Wert aus der Spalte `Label`, konvertiert diesen in einen numerischen `KeyType`-Wert und speichert ihn in einer neuen Spalte namens `LabelAsKey`.</span><span class="sxs-lookup"><span data-stu-id="ab769-244">The `MapValueToKey` transform takes the categorical value in the `Label` column, converts it to a numerical `KeyType` value and stores it in a new column called `LabelAsKey`.</span></span> <span data-ttu-id="ab769-245">`LoadImages` greift auf Werte aus der Spalte `ImagePath` zusammen mit dem Parameter `imageFolder` zu, um Bilder für das Training zu laden.</span><span class="sxs-lookup"><span data-stu-id="ab769-245">The `LoadImages` takes the values from the `ImagePath` column along with the `imageFolder` parameter to load images for training.</span></span> <span data-ttu-id="ab769-246">Durch Festlegen von `useImageType` auf `false` wird das Bild in ein `byte[]`-Array konvertiert.</span><span class="sxs-lookup"><span data-stu-id="ab769-246">Setting the `useImageType` to `false` converts the images into a `byte[]`.</span></span> 

    [!code-csharp [DefinePreprocessingPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L26-L33)]

1. <span data-ttu-id="ab769-247">Verwenden Sie die [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*)-Methode, um die Daten auf die [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601)-Klasse `preprocessingPipeline` gefolgt von der [`Transform`](xref:Microsoft.ML.Data.TransformerChain`1.Transform*)-Methode anzuwenden, wodurch eine [`IDataView`](xref:Microsoft.ML.IDataView)-Schnittstelle zurückgegeben wird, die die vorverarbeiteten Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="ab769-247">Use the [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*) method to apply the data to the `preprocessingPipeline` [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) followed by the [`Transform`](xref:Microsoft.ML.Data.TransformerChain`1.Transform*) method, which returns an [`IDataView`](xref:Microsoft.ML.IDataView) containing the pre-processed data.</span></span>

    [!code-csharp [PreprocessData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L35-L37)]

1. <span data-ttu-id="ab769-248">Beim Trainieren eines Modells ist es wichtig, sowohl über ein Trainingsdataset als auch ein Validierungsdataset zu verfügen.</span><span class="sxs-lookup"><span data-stu-id="ab769-248">To train a model, it's important to have a training dataset as well as a validation dataset.</span></span> <span data-ttu-id="ab769-249">Das Modell wird mit dem Trainingsset trainiert.</span><span class="sxs-lookup"><span data-stu-id="ab769-249">The model is trained on the training set.</span></span> <span data-ttu-id="ab769-250">Wie gut es Vorhersagen über unbekannte Daten erstellt, wird an der Leistung im Vergleich zum Validierungsset gemessen.</span><span class="sxs-lookup"><span data-stu-id="ab769-250">How well it makes predictions on unseen data is measured by the performance against the validation set.</span></span> <span data-ttu-id="ab769-251">Basierend auf den Ergebnissen dieser Leistung nimmt das Modell Anpassungen an dem Gelernten vor, um die Ergebnisse zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="ab769-251">Based on the results of that performance, the model makes adjustments to what it has learned in an effort to improve.</span></span> <span data-ttu-id="ab769-252">Das Validierungsset kann entweder aus der Aufteilung des ursprünglichen Datasets oder aus einer anderen Quelle stammen, die bereits für diesen Zweck vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="ab769-252">The validation set can come from either splitting your original dataset or from another source that has already been set aside for this purpose.</span></span> <span data-ttu-id="ab769-253">In diesem Fall wird das vorverarbeitete Datenset in Trainings-, Validierungs- und Testsets unterteilt.</span><span class="sxs-lookup"><span data-stu-id="ab769-253">In this case, the pre-processed dataset is split into training, validation and test sets.</span></span>

    [!code-csharp [CreateDataSplits](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L39-L40)]

    <span data-ttu-id="ab769-254">Im obigen Codebeispiel werden zwei Aufteilungen vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="ab769-254">The code sample above performs two splits.</span></span> <span data-ttu-id="ab769-255">Zunächst werden die vorverarbeiteten Daten aufgeteilt, wobei 70% für das Training und die restlichen 30% für die Validierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ab769-255">First, the pre-processed data is split and 70% is used for training while the remaining 30% is used for validation.</span></span> <span data-ttu-id="ab769-256">Anschließend werden die 30% des Validierungssets weiter in Validierungs- und Testsets unterteilt, wobei 90% für die Validierung und 10% für Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ab769-256">Then, the 30% validation set is further split into validation and test sets where 90% is used for validation and 10% is used for testing.</span></span> 

    <span data-ttu-id="ab769-257">Ein gutes Beispiel, um den Sinn und Zweck dieser Datenaufteilungen zu verstehen, ist eine Prüfungsituation.</span><span class="sxs-lookup"><span data-stu-id="ab769-257">A way to think about the purpose of these data partitions is taking an exam.</span></span> <span data-ttu-id="ab769-258">Wenn Sie für eine Prüfung lernen, lesen Sie Ihre Notizen, Bücher oder andere Unterlagen, um die in der Prüfung enthaltenen Themen zu lernen und zu vertiefen.</span><span class="sxs-lookup"><span data-stu-id="ab769-258">When studying for an exam, you review your notes, books, or other resources to get a grasp on the concepts that are on the exam.</span></span> <span data-ttu-id="ab769-259">Dafür ist das Trainingsset da.</span><span class="sxs-lookup"><span data-stu-id="ab769-259">This is what the train set is for.</span></span> <span data-ttu-id="ab769-260">Dann können Sie eine Probeklausur ablegen, um Ihren Wissensstand zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ab769-260">Then, you might take a mock exam to validate your knowledge.</span></span> <span data-ttu-id="ab769-261">Hier bietet sich das Validierungsset an.</span><span class="sxs-lookup"><span data-stu-id="ab769-261">This is where the validation set comes in handy.</span></span> <span data-ttu-id="ab769-262">Sie möchten vor der eigentlichen Prüfung feststellen, ob Sie die Inhalte richtig verstanden haben.</span><span class="sxs-lookup"><span data-stu-id="ab769-262">You want to check whether you have a good grasp of the concepts before taking the actual exam.</span></span> <span data-ttu-id="ab769-263">Ausgehend von den Ergebnissen können Sie herausfinden, was Sie falsch gemacht bzw. nicht richtig verstanden haben, und so die Ergebnisse in den Lernprozess für die eigentliche Prüfung einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="ab769-263">Based on those results, you take note of what you got wrong or didn't understand well and incorporate your changes as you review for the real exam.</span></span> <span data-ttu-id="ab769-264">Zum Schluss legen Sie die Prüfung ab.</span><span class="sxs-lookup"><span data-stu-id="ab769-264">Finally, you take the exam.</span></span> <span data-ttu-id="ab769-265">Dafür wird das Testset verwendet.</span><span class="sxs-lookup"><span data-stu-id="ab769-265">This is what the test set is used for.</span></span> <span data-ttu-id="ab769-266">Sie haben die Fragen in der Prüfung noch nie gesehen und nutzen zur Bearbeitung der vorliegenden Aufgabe nun das, was Sie sich durch den Lernprozess (Training) und die Überprüfung des Gelernten (Validierung) angeeignet haben.</span><span class="sxs-lookup"><span data-stu-id="ab769-266">You've never seen the questions that are on the exam and now use what you learned from training and validation to apply your knowledge to the task at hand.</span></span> 

1. <span data-ttu-id="ab769-267">Ordnen Sie den Teilbereichen die jeweiligen Werte für die Trainings-, Validierungs- und Testdaten zu.</span><span class="sxs-lookup"><span data-stu-id="ab769-267">Assign the partitions their respective values for the train, validation and test data.</span></span>

    [!code-csharp [CreateDatasets](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L42-L44)]

## <a name="define-the-training-pipeline"></a><span data-ttu-id="ab769-268">Definieren der Trainingspipeline</span><span class="sxs-lookup"><span data-stu-id="ab769-268">Define the training pipeline</span></span>

<span data-ttu-id="ab769-269">Das Modelltraining umfasst mehrere Schritte.</span><span class="sxs-lookup"><span data-stu-id="ab769-269">Model training consists of a couple of steps.</span></span> <span data-ttu-id="ab769-270">Zunächst wird die Bildklassifizierungs-API verwendet, um das Modell zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="ab769-270">First, Image Classification API is used to train the model.</span></span> <span data-ttu-id="ab769-271">Anschließend werden die verschlüsselten Bezeichnungen in der Spalte `PredictedLabel` mithilfe der `MapKeyToValue`-Transformation wieder in ihren ursprünglichen kategorischen Wert konvertiert.</span><span class="sxs-lookup"><span data-stu-id="ab769-271">Then, the encoded labels in the `PredictedLabel` column are converted back to their original categorical value using the `MapKeyToValue` transform.</span></span> 

1. <span data-ttu-id="ab769-272">Definieren Sie die Trainingspipeline [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601), die sowohl aus der `mapLabelEstimator`- als auch aus der `ImageClassification`-Transformation besteht.</span><span class="sxs-lookup"><span data-stu-id="ab769-272">Define the training [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) pipeline that consists of both the `mapLabelEstimator` and the `ImageClassification` transforms.</span></span>

    [!code-csharp [DefineTrainingPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L46-L58)]    

    <span data-ttu-id="ab769-273">Der `ImageClassification`-Estimator berücksichtigt mehrere Parameter:</span><span class="sxs-lookup"><span data-stu-id="ab769-273">The `ImageClassification` estimator takes in several parameters:</span></span>

    - <span data-ttu-id="ab769-274">`featuresColumnName` ist die Spalte, die als Eingabe für das Modell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ab769-274">`featuresColumnName` is the column that is used as input for the model.</span></span>
    - <span data-ttu-id="ab769-275">`labelColumnName` ist die Spalte für den vorherzusagenden Wert.</span><span class="sxs-lookup"><span data-stu-id="ab769-275">`labelColumnName` is the column for the value to predict.</span></span>
    - <span data-ttu-id="ab769-276">`arch` definiert, welche der vorab trainierten Modellarchitekturen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ab769-276">`arch` defines which of the pretrained model architectures to use.</span></span> <span data-ttu-id="ab769-277">In diesem Tutorial wird die 101-Ebenen-Variante des Modells „ResNetv2“ verwendet.</span><span class="sxs-lookup"><span data-stu-id="ab769-277">This tutorial uses the 101-layer variant of the ResNetv2 model.</span></span>
    - <span data-ttu-id="ab769-278">`epoch` gibt die Höchstzahl von Iterationen über das gesamte Dataset während des Trainingsprozesses an.</span><span class="sxs-lookup"><span data-stu-id="ab769-278">`epoch` specifies the maximum number of iterations over the entire dataset throughout the training process.</span></span> <span data-ttu-id="ab769-279">Je höher die Anzahl, desto länger trainiert das Modell und desto besser ist das dabei erzeugte Modell.</span><span class="sxs-lookup"><span data-stu-id="ab769-279">The higher the number, the longer the model trains for and potentially the better model that is produced.</span></span>
    - <span data-ttu-id="ab769-280">`batchSize` ist die Anzahl der Beispiele, die gleichzeitig für das Training verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ab769-280">`batchSize` is the number of samples to use at a time for training.</span></span> <span data-ttu-id="ab769-281">Während einer Epoche werden mehrere Batches entsprechend dem batchSize-Wert verwendet, um das Modell zu trainieren und zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ab769-281">During one epoch, multiple batches equal to the batchSize are used to train and update the model.</span></span> <span data-ttu-id="ab769-282">Je niedriger der Wert, desto weniger Speicherplatz wird bei der Verarbeitung jedes Batches benötigt.</span><span class="sxs-lookup"><span data-stu-id="ab769-282">The lower the number, the less memory required when each batch is processed.</span></span>
    - <span data-ttu-id="ab769-283">`testOnTrainSet` weist das Modell an, die Leistung anhand des Trainingssets zu messen, wenn kein Validierungsset vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ab769-283">`testOnTrainSet` tells the model to measure performance against the training set when no validation set is present.</span></span>
    - <span data-ttu-id="ab769-284">`metricsCallback` verknüpft eine Funktion, um den Fortschritt während des Trainings zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="ab769-284">`metricsCallback` binds a function to track the progress during training.</span></span>
    - <span data-ttu-id="ab769-285">`validationSet` ist die [`IDataView`](xref:Microsoft.ML.IDataView)-Schnittstelle, die die Validierungsdaten enthält.</span><span class="sxs-lookup"><span data-stu-id="ab769-285">`validationSet` is the [`IDataView`](xref:Microsoft.ML.IDataView) containing the validation data.</span></span>
    - <span data-ttu-id="ab769-286">`reuseTrainSetBottleneckCachedValues` informiert das Modell, ob die zwischengespeicherten Werte aus der Engpassphase in nachfolgenden Durchläufen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ab769-286">`reuseTrainSetBottleneckCachedValues` tells the model whether to use the cached values from the bottleneck phase in subsequent runs.</span></span> <span data-ttu-id="ab769-287">Die Engpassphase ist eine einmalige Pass-Through-Berechnung, die bei der ersten Durchführung sehr rechenintensiv ist.</span><span class="sxs-lookup"><span data-stu-id="ab769-287">The bottleneck phase is a one-time pass-through computation that is computationally intensive the first time it is performed.</span></span> <span data-ttu-id="ab769-288">Wenn sich die Trainingsdaten nicht ändern, und Sie mit einer anderen Anzahl von Epochen oder anderen Batchgrößen experimentieren möchten, können Sie mit den zwischengespeicherten Werten den Zeitaufwand für das Training eines Modells erheblich verringern.</span><span class="sxs-lookup"><span data-stu-id="ab769-288">If the training data does not change and you want to experiment using a different number of epochs or batch size, using the cached values significantly reduces the amount of time required to train a model.</span></span>
    - <span data-ttu-id="ab769-289">`reuseValidationSetBottleneckCachedValues` ist vergleichbar mit `reuseTrainSetBottleneckCachedValues`, allerdings handelt es sich in diesem Fall um das Validierungsdataset.</span><span class="sxs-lookup"><span data-stu-id="ab769-289">`reuseValidationSetBottleneckCachedValues` is similar to `reuseTrainSetBottleneckCachedValues` only that in this case it's for the validation dataset.</span></span>
    - <span data-ttu-id="ab769-290">`disableEarlyStopping` informiert den ImageClassification-Estimator darüber, ob er eine Strategie zum frühzeitigen Abbrechen anwenden soll.</span><span class="sxs-lookup"><span data-stu-id="ab769-290">`disableEarlyStopping` tells the ImageClassification estimator whether to employ an early stopping strategy.</span></span> <span data-ttu-id="ab769-291">Wenn das Modell nach den optimalen Werten sucht, mit denen es während des Trainings genaue Vorhersagen treffen kann, ist es möglich, dass die Leistung steigt oder sinkt.</span><span class="sxs-lookup"><span data-stu-id="ab769-291">As the model searches for the optimal values that will help it make accurate predictions during training, performance may increase or decrease.</span></span> <span data-ttu-id="ab769-292">Erreicht das Modell schließlich die letzte Epoche, kann es vorkommen, dass die im Training erlernten Muster nicht optimal sind.</span><span class="sxs-lookup"><span data-stu-id="ab769-292">Ultimately, if the model reaches the last epoch, it may be the case that the patterns it learned from training are suboptimal.</span></span> <span data-ttu-id="ab769-293">Die Funktion zum frühzeitigen Abbrechen überwacht, ob es beim Training zu Leistungseinbrüchen kommt. Sollte dies der Fall sein, wird der Trainingsprozess abgebrochen, damit eine optimale Version des Modells erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ab769-293">Early stopping monitors training for these drops in performance and stops the training process in an effort to preserve an optimal version of the model.</span></span>

1. <span data-ttu-id="ab769-294">Verwenden Sie die Methode [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*), um Ihr Modell zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="ab769-294">Use the [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*) method to train your model.</span></span>

    [!code-csharp [TrainModel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L60)]

## <a name="use-the-model"></a><span data-ttu-id="ab769-295">Verwenden des Modells</span><span class="sxs-lookup"><span data-stu-id="ab769-295">Use the model</span></span>

<span data-ttu-id="ab769-296">Nachdem Sie Ihr Modell trainiert haben, ist es an der Zeit, es zur Klassifizierung von Bildern zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ab769-296">Now that you have trained your model, it's time to use it to classify images.</span></span>

<span data-ttu-id="ab769-297">Erstellen Sie unter der `Main`-Methode eine neue Hilfsmethode namens `OutputPrediction`, um Vorhersageinformationen in der Konsole anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ab769-297">Below the `Main` method, create a new utility method called `OutputPrediction` to display prediction information in the console.</span></span>

[!code-csharp [OuputPredictionMethod](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L94-L98)]

### <a name="classify-a-single-image"></a><span data-ttu-id="ab769-298">Klassifizieren eines einzelnen Bilds</span><span class="sxs-lookup"><span data-stu-id="ab769-298">Classify a single image</span></span>

1. <span data-ttu-id="ab769-299">Fügen Sie eine neue Methode namens `ClassifySingleImage` unter der `Main`-Methode hinzu, um eine Einzelbildvorhersage zu erstellen und auszugeben.</span><span class="sxs-lookup"><span data-stu-id="ab769-299">Add a new method called `ClassifySingleImage` below the `Main` method to make and output a single image prediction.</span></span>

    ```csharp
    public static void ClassifySingleImage(MLContext mlContext, IDataView data, ITransformer trainedModel)
    {

    }
    ```

1. <span data-ttu-id="ab769-300">Erstellen Sie eine [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)-Klasse innerhalb der `ClassifySingleImage`-Methode.</span><span class="sxs-lookup"><span data-stu-id="ab769-300">Create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) inside the `ClassifySingleImage` method.</span></span> <span data-ttu-id="ab769-301">Die [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)-Klasse ist eine praktische API, mit der Sie eine Vorhersage für eine einzelne Dateninstanz übergeben und dann ausführen können.</span><span class="sxs-lookup"><span data-stu-id="ab769-301">The [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to pass in and then perform a prediction on a single instance of data.</span></span>

    [!code-csharp [CreatePredictionEngine](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L71)]    

1. <span data-ttu-id="ab769-302">Um auf eine einzelne `ModelInput`-Instanz zuzugreifen, konvertieren Sie die [`IDataView`](xref:Microsoft.ML.IDataView)-Schnittstelle `data` in eine [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601)-Schnittstelle mit der [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*)-Methode und erhalten Sie dann das erste Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="ab769-302">To access a single `ModelInput` instance, convert the `data` [`IDataView`](xref:Microsoft.ML.IDataView) into an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) using the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method and then get the first observation.</span></span> 

    [!code-csharp [GetTestInputData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L73)]

1. <span data-ttu-id="ab769-303">Verwenden Sie die [`Predict`](xref:Microsoft.ML.PredictionEngine%602.Predict*)-Methode, um das Bild zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="ab769-303">Use the [`Predict`](xref:Microsoft.ML.PredictionEngine%602.Predict*) method to classify the image.</span></span>

    [!code-csharp [MakeSinglePrediction](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L75)]

1. <span data-ttu-id="ab769-304">Geben Sie die Vorhersage mit der `OutputPrediction`-Methode in der Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="ab769-304">Output the prediction to the console with the `OutputPrediction` method.</span></span>

    [!code-csharp [OuputSinglePrediction](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L77-L78)]

1. <span data-ttu-id="ab769-305">Rufen Sie innerhalb der `Main`-Methode `ClassifySingleImage` mit dem Testset der Bilder auf.</span><span class="sxs-lookup"><span data-stu-id="ab769-305">Inside the `Main` method, call `ClassifySingleImage` using the test set of images.</span></span>

    [!code-csharp [ClassifySingleImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L62)]

### <a name="classify-multiple-images"></a><span data-ttu-id="ab769-306">Klassifizieren mehrerer Bilder</span><span class="sxs-lookup"><span data-stu-id="ab769-306">Classify multiple images</span></span>

1. <span data-ttu-id="ab769-307">Fügen Sie eine neue Methode namens `ClassifyImages` unter der `ClassifySingleImage`-Methode hinzu, um mehrere Bildvorhersagen zu erstellen und auszugeben.</span><span class="sxs-lookup"><span data-stu-id="ab769-307">Add a new method called `ClassifyImages` below the `ClassifySingleImage` method to make and output multiple image predictions.</span></span>

    ```csharp
    public static void ClassifyImages(MLContext mlContext, IDataView data, ITransformer trainedModel)
    {

    }
    ```

1. <span data-ttu-id="ab769-308">Erstellen Sie mithilfe der [`Transform`](xref:Microsoft.ML.ITransformer.Transform*)-Methode eine [`IDataView`](xref:Microsoft.ML.IDataView)-Schnittstelle, die die Vorhersagen enthält.</span><span class="sxs-lookup"><span data-stu-id="ab769-308">Create an [`IDataView`](xref:Microsoft.ML.IDataView) containing the predictions by using the [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) method.</span></span> <span data-ttu-id="ab769-309">Fügen Sie der `ClassifyImages`-Methode den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="ab769-309">Add the following code inside the `ClassifyImages` method.</span></span>

    [!code-csharp [MakeMultiplePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L83)]

1. <span data-ttu-id="ab769-310">Zur Iteration über die Vorhersagen konvertieren Sie die [`IDataView`](xref:Microsoft.ML.IDataView)-Schnittstelle `predictionData` in eine [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601)-Schnittstelle mithilfe der [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*)-Methode und erhalten Sie dann die ersten zehn Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="ab769-310">In order to iterate over the predictions, convert the `predictionData` [`IDataView`](xref:Microsoft.ML.IDataView) into an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) using the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method and then get the first 10 observations.</span></span>

    [!code-csharp [IEnumerablePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L85)]

1. <span data-ttu-id="ab769-311">Iterieren Sie die ursprünglichen und vorhergesagten Bezeichnungen für die Vorhersagen, und geben Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="ab769-311">Iterate and output the original and predicted labels for the predictions.</span></span>

    [!code-csharp [OutputMultiplePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L87-L91)]

1. <span data-ttu-id="ab769-312">Abschließend rufen Sie innerhalb der `Main`-Methode `ClassifyImages` mit dem Testset der Bilder auf.</span><span class="sxs-lookup"><span data-stu-id="ab769-312">Finally, inside the `Main` method, call `ClassifyImages` using the test set of images.</span></span>

    [!code-csharp [ClassifyImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L64)]

## <a name="run-the-application"></a><span data-ttu-id="ab769-313">Ausführen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="ab769-313">Run the application</span></span>

<span data-ttu-id="ab769-314">Führen Sie die Konsolenanwendung aus.</span><span class="sxs-lookup"><span data-stu-id="ab769-314">Run your console app.</span></span> <span data-ttu-id="ab769-315">Die Ausgabe sollte in etwa wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="ab769-315">The output should be similar to that below.</span></span> <span data-ttu-id="ab769-316">Möglicherweise werden Warnungen oder Verarbeitungsnachrichten angezeigt. Diese wurden jedoch aus Gründen der Übersichtlichkeit aus den folgenden Ergebnissen entfernt.</span><span class="sxs-lookup"><span data-stu-id="ab769-316">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span> <span data-ttu-id="ab769-317">Aus Gründen der Kürze wurde die Ausgabe komprimiert.</span><span class="sxs-lookup"><span data-stu-id="ab769-317">For brevity, the output has been condensed.</span></span>

<span data-ttu-id="ab769-318">**Engpassphase**</span><span class="sxs-lookup"><span data-stu-id="ab769-318">**Bottleneck phase**</span></span>

<span data-ttu-id="ab769-319">Für den Bildnamen wird kein Wert ausgegeben, da die Bilder als `byte[]` geladen werden, sodass kein Bildname angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ab769-319">No value is printed for the image name because the images are loaded as a `byte[]` therefore there is no image name to display.</span></span>

```test
Phase: Bottleneck Computation, Dataset used:      Train, Image Index: 279, Image Name:
Phase: Bottleneck Computation, Dataset used:      Train, Image Index: 280, Image Name:
Phase: Bottleneck Computation, Dataset used: Validation, Image Index:   1, Image Name:
Phase: Bottleneck Computation, Dataset used: Validation, Image Index:   2, Image Name:
```

<span data-ttu-id="ab769-320">**Trainingsphase**</span><span class="sxs-lookup"><span data-stu-id="ab769-320">**Training phase**</span></span>

```text
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  21, Accuracy:  0.6797619
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  22, Accuracy:  0.7642857
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  23, Accuracy:  0.7916667
```

<span data-ttu-id="ab769-321">**Klassifizieren der Ausgabe von Bildern**</span><span class="sxs-lookup"><span data-stu-id="ab769-321">**Classify images output**</span></span>

```text
Classifying single image
Image: 7001-220.jpg | Actual Value: UD | Predicted Value: UD

Classifying multiple images
Image: 7001-220.jpg | Actual Value: UD | Predicted Value: UD
Image: 7001-163.jpg | Actual Value: UD | Predicted Value: UD
Image: 7001-210.jpg | Actual Value: UD | Predicted Value: UD
```

<span data-ttu-id="ab769-322">Bei der Überprüfung des Bilds *7001-220.jpg* können Sie feststellen, dass tatsächlich kein Riss zu sehen ist.</span><span class="sxs-lookup"><span data-stu-id="ab769-322">Upon inspection of the *7001-220.jpg* image, you can see that it in fact is not cracked.</span></span> 

![Für die Vorhersage verwendetes SDNET2018-Datasetbild](./media/image-classification-api-transfer-learning/predictedimage.jpg)

<span data-ttu-id="ab769-324">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="ab769-324">Congratulations!</span></span> <span data-ttu-id="ab769-325">Sie haben ein Deep-Learning-Modell zur Klassifizierung von Bildern erstellt.</span><span class="sxs-lookup"><span data-stu-id="ab769-325">You've now successfully built a deep learning model for classifying images.</span></span>

### <a name="improve-the-model"></a><span data-ttu-id="ab769-326">Verbessern des Modells</span><span class="sxs-lookup"><span data-stu-id="ab769-326">Improve the model</span></span>

<span data-ttu-id="ab769-327">Wenn Sie mit den Ergebnissen des Modells nicht zufrieden sind, können Sie versuchen, seine Leistung zu verbessern, indem Sie einige der folgenden Ansätze ausprobieren:</span><span class="sxs-lookup"><span data-stu-id="ab769-327">If you're not satisfied with the results of your model, you can try to improve its performance by trying some of the following approaches:</span></span>

- <span data-ttu-id="ab769-328">**Mehr Daten**: Je mehr Beispiele vorhanden sind, von denen ein Modell lernt, desto besser ist dessen Leistung.</span><span class="sxs-lookup"><span data-stu-id="ab769-328">**More Data**: The more examples a model learns from, the better it performs.</span></span> <span data-ttu-id="ab769-329">Laden Sie das vollständige [SDNET2018-Dataset](https://digitalcommons.usu.edu/cgi/viewcontent.cgi?filename=2&article=1047&context=all_datasets&type=additional) herunter, und verwenden Sie es für das Training.</span><span class="sxs-lookup"><span data-stu-id="ab769-329">Download the full [SDNET2018 dataset](https://digitalcommons.usu.edu/cgi/viewcontent.cgi?filename=2&article=1047&context=all_datasets&type=additional) and use it to train.</span></span> 
- <span data-ttu-id="ab769-330">**Erweitern der Daten**: Eine gängige Technik, um eine größere Datenvielfalt zu erreichen, ist die Erweiterung der Daten durch Aufnahme eines Bilds und Anwendung verschiedener Transformationen (Drehen, Spiegeln, Verschieben, Zuschneiden).</span><span class="sxs-lookup"><span data-stu-id="ab769-330">**Augment the data**: A common technique to add variety to the data is to augment the data by taking an image and applying different transforms (rotate, flip, shift, crop).</span></span> <span data-ttu-id="ab769-331">Auf diese Weise erhalten Sie verschiedene Beispiele, von denen das Modell lernen kann.</span><span class="sxs-lookup"><span data-stu-id="ab769-331">This adds more varied examples for the model to learn from.</span></span> 
- <span data-ttu-id="ab769-332">**Längere Trainingsdauer**: Umso länger die Trainingsdauer, desto genauer werden die Ergebnisse des Modells sein.</span><span class="sxs-lookup"><span data-stu-id="ab769-332">**Train for a longer time**: The longer you train, the more tuned the model will be.</span></span> <span data-ttu-id="ab769-333">Durch die Erhöhung der Anzahl von Epochen kann sich die Leistung des Modell erheblich verbessern.</span><span class="sxs-lookup"><span data-stu-id="ab769-333">Increasing the number of epochs may improve the performance of your model.</span></span>
- <span data-ttu-id="ab769-334">**Experimentieren mit Hyperparametern**: Zusätzlich zu den in diesem Tutorial verwendeten Parametern können weitere Parameter angepasst werden, um die Leistung zu steigern.</span><span class="sxs-lookup"><span data-stu-id="ab769-334">**Experiment with the hyper-parameters**: In addition to the parameters used in this tutorial, other parameters can be tuned to potentially improve performance.</span></span> <span data-ttu-id="ab769-335">Die Änderung des Lerntempos, das den Umfang der Aktualisierungen am Modell nach jeder Epoche bestimmt, kann zu einer höheren Leistung führen.</span><span class="sxs-lookup"><span data-stu-id="ab769-335">Changing the learning rate, which determines the magnitude of updates made to the model after each epoch may improve performance.</span></span>
- <span data-ttu-id="ab769-336">**Verwenden einer anderen Modellarchitektur**: Abhängig von der Beschaffenheit Ihrer Daten kann sich das Modell, das am besten deren Merkmale erlernen kann, unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="ab769-336">**Use a different model architecture**: Depending on what your data looks like, the model that can best learn its features may differ.</span></span> <span data-ttu-id="ab769-337">Wenn Sie mit der Leistung Ihres Modells unzufrieden sind, sollten Sie versuchen, die Architektur zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ab769-337">If you're not satisfied with the performance of your model, try changing the architecture.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ab769-338">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="ab769-338">Additional Resources</span></span>

- <span data-ttu-id="ab769-339">[Deep Learning im Vergleich zu maschinellem Lernen](/azure/machine-learning/service/concept-deep-learning-vs-machine-learning)</span><span class="sxs-lookup"><span data-stu-id="ab769-339">[Deep Learning vs Machine Learning](/azure/machine-learning/service/concept-deep-learning-vs-machine-learning).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ab769-340">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ab769-340">Next steps</span></span>

<span data-ttu-id="ab769-341">In diesem Tutorial haben Sie erfahren, wie Sie ein benutzerdefiniertes Deep-Learning-Modell mithilfe von Transferlernen, einem vorab trainierten TensorFlow-Modell und der ML.NET-Bildklassifizierungs-API erstellen, um Bilder von Betonoberflächen als gerissen oder nicht gerissen zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="ab769-341">In this tutorial, you learned how to build a custom deep learning model using transfer learning, a pretrained image classification TensorFlow model and the ML.NET Image Classification API to classify images of concrete surfaces as cracked or uncracked.</span></span>

<span data-ttu-id="ab769-342">Fahren Sie mit dem nächsten Tutorial fort, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="ab769-342">Advance to the next tutorial to learn more.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ab769-343">Objekterkennung</span><span class="sxs-lookup"><span data-stu-id="ab769-343">Object Detection</span></span>](object-detection-onnx.md)
