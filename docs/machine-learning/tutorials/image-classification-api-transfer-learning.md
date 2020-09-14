---
title: 'Tutorial: Automatisierte visuelle Überprüfung mithilfe von Transferlernen'
description: In diesem Tutorial wird gezeigt, wie Sie anhand von Transferlernen ein TensorFlow-Modell mit Deep Learning in ML.NET mit der Bilderkennungs-API trainieren, um Bilder von Betonoberflächen als gerissen oder nicht gerissen zu klassifizieren.
author: luisquintanilla
ms.author: luquinta
ms.date: 06/30/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: a2ebad329f583d35f110c5db053eebfa80ace6e2
ms.sourcegitcommit: ae2e8a61a93c5cf3f0035c59e6b064fa2f812d14
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "89359323"
---
# <a name="tutorial-automated-visual-inspection-using-transfer-learning-with-the-mlnet-image-classification-api"></a><span data-ttu-id="7c3fd-103">Tutorial: Automatisierte visuelle Überprüfung mithilfe von Transferlernen mit der ML.NET-Bildklassifizierungs-API</span><span class="sxs-lookup"><span data-stu-id="7c3fd-103">Tutorial: Automated visual inspection using transfer learning with the ML.NET Image Classification API</span></span>

<span data-ttu-id="7c3fd-104">Erfahren Sie, wie Sie ein benutzerdefiniertes Deep-Learning-Modell mithilfe von Transferlernen, einem vorab trainierten TensorFlow-Modell und der ML.NET-Bildklassifizierungs-API trainieren, um Bilder von Betonoberflächen als gerissen oder nicht gerissen zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-104">Learn how to train a custom deep learning model using transfer learning, a pretrained TensorFlow model and the ML.NET Image Classification API to classify images of concrete surfaces as cracked or uncracked.</span></span>

<span data-ttu-id="7c3fd-105">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="7c3fd-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="7c3fd-106">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="7c3fd-106">Understand the problem</span></span>
> - <span data-ttu-id="7c3fd-107">Informationen zur ML.NET-Bildklassifizierungs-API</span><span class="sxs-lookup"><span data-stu-id="7c3fd-107">Learn about ML.NET Image Classification API</span></span>
> - <span data-ttu-id="7c3fd-108">Grundlegendes zum vorab trainierten Modell</span><span class="sxs-lookup"><span data-stu-id="7c3fd-108">Understand the pretrained model</span></span>
> - <span data-ttu-id="7c3fd-109">Trainieren eines benutzerdefinierten TensorFlow-Bildklassifizierungsmodells mithilfe von Transferlernen</span><span class="sxs-lookup"><span data-stu-id="7c3fd-109">Use transfer learning to train a custom TensorFlow image classification model</span></span>
> - <span data-ttu-id="7c3fd-110">Klassifizieren von Bildern mit dem benutzerdefinierten Modell</span><span class="sxs-lookup"><span data-stu-id="7c3fd-110">Classify images with the custom model</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7c3fd-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="7c3fd-111">Prerequisites</span></span>

- <span data-ttu-id="7c3fd-112">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) oder höher oder Visual Studio 2017 Version 15.6 oder höher mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-112">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or later or Visual Studio 2017 version 15.6 or later with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="image-classification-transfer-learning-sample-overview"></a><span data-ttu-id="7c3fd-113">Beispielübersicht zur Bildklassifizierung mit Transferlernen</span><span class="sxs-lookup"><span data-stu-id="7c3fd-113">Image classification transfer learning sample overview</span></span>

<span data-ttu-id="7c3fd-114">Bei diesem Beispiel handelt es sich um eine C#.NET Core-Konsolenanwendung, die Bilder mit einem vorab mit Deep Learning trainierten TensorFlow-Modell klassifiziert.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-114">This sample is a C# .NET Core console application that classifies images using a pretrained deep learning TensorFlow model.</span></span> <span data-ttu-id="7c3fd-115">Den Code für dieses Beispiel finden Sie im [Beispielbrowser](/samples/dotnet/machinelearning-samples/mlnet-image-classification-transfer-learning/).</span><span class="sxs-lookup"><span data-stu-id="7c3fd-115">The code for this sample can be found on the [samples browser](/samples/dotnet/machinelearning-samples/mlnet-image-classification-transfer-learning/).</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="7c3fd-116">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="7c3fd-116">Understand the problem</span></span>

<span data-ttu-id="7c3fd-117">Bildklassifizierung ist ein Problem des maschinellen Sehens.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-117">Image classification is a computer vision problem.</span></span> <span data-ttu-id="7c3fd-118">Bei der Bildklassifizierung wird ein Bild eingegeben, das dann in eine bestimmte Klasse eingeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-118">Image classification takes an image as input and categorizes it into a prescribed class.</span></span> <span data-ttu-id="7c3fd-119">Die Bildklassifizierung kann zum Beispiel in diesen Szenarios hilfreich sein:</span><span class="sxs-lookup"><span data-stu-id="7c3fd-119">Some scenarios where image classification is useful include:</span></span>

- <span data-ttu-id="7c3fd-120">Gesichtserkennung</span><span class="sxs-lookup"><span data-stu-id="7c3fd-120">Facial recognition</span></span>
- <span data-ttu-id="7c3fd-121">Emotionserkennung</span><span class="sxs-lookup"><span data-stu-id="7c3fd-121">Emotion detection</span></span>
- <span data-ttu-id="7c3fd-122">Medizinische Diagnose</span><span class="sxs-lookup"><span data-stu-id="7c3fd-122">Medical diagnosis</span></span>
- <span data-ttu-id="7c3fd-123">Orientierungspunkterkennung</span><span class="sxs-lookup"><span data-stu-id="7c3fd-123">Landmark detection</span></span>

<span data-ttu-id="7c3fd-124">In diesem Tutorial wird ein benutzerdefiniertes Bildklassifizierungsmodell trainiert, um eine automatisierte visuelle Überprüfung von Brückenbelägen durchzuführen, bei der durch Risse unterbrochene Strukturen identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-124">This tutorial trains a custom image classification model to perform automated visual inspection of bridge decks to identify structures that are damaged by cracks.</span></span>

## <a name="mlnet-image-classification-api"></a><span data-ttu-id="7c3fd-125">ML.NET-Bildklassifizierungs-API</span><span class="sxs-lookup"><span data-stu-id="7c3fd-125">ML.NET Image Classification API</span></span>

<span data-ttu-id="7c3fd-126">ML.NET bietet verschiedene Methoden zum Durchführen einer Bildklassifizierung.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-126">ML.NET provides various ways of performing image classification.</span></span> <span data-ttu-id="7c3fd-127">In diesem Tutorial wird die Methode des Transferlernens unter Verwendung der Bildklassifizierungs-API angewendet.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-127">This tutorial applies transfer learning using the Image Classification API.</span></span> <span data-ttu-id="7c3fd-128">Die Bildklassifizierungs-API nutzt [TensorFlow.NET](https://github.com/SciSharp/TensorFlow.NET), eine Low-Level-Bibliothek, die C#-Bindungen für die TensorFlow-C++-API bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-128">The Image Classification API makes use of [TensorFlow.NET](https://github.com/SciSharp/TensorFlow.NET), a low-level library that provides C# bindings for the TensorFlow C++ API.</span></span>

## <a name="what-is-transfer-learning"></a><span data-ttu-id="7c3fd-129">Was ist Übertragungslernen?</span><span class="sxs-lookup"><span data-stu-id="7c3fd-129">What is transfer learning?</span></span>

<span data-ttu-id="7c3fd-130">Beim Transferlernen werden Erkenntnisse aus der Lösung eines Problems für ein anderes verwandtes Problem genutzt.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-130">Transfer learning applies knowledge gained from solving one problem to another related problem.</span></span>

<span data-ttu-id="7c3fd-131">Das von Grund auf neue Trainieren eines Deep-Learning-Modells erfordert das Festlegen mehrerer Parameter, zahlreiche bezeichnete Trainingsdaten und eine große Menge an Computeressourcen (Hunderte von GPU-Stunden).</span><span class="sxs-lookup"><span data-stu-id="7c3fd-131">Training a deep learning model from scratch requires setting several parameters, a large amount of labeled training data, and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="7c3fd-132">Die Verwendung eines vorab trainierten Modells zusammen mit dem Transferlernen ermöglicht es Ihnen, den Trainingsprozess zu verkürzen.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-132">Using a pretrained model along with transfer learning allows you to shortcut the training process.</span></span>

## <a name="training-process"></a><span data-ttu-id="7c3fd-133">Trainingsprozess</span><span class="sxs-lookup"><span data-stu-id="7c3fd-133">Training process</span></span>

<span data-ttu-id="7c3fd-134">Die Bildklassifizierungs-API startet den Trainingsprozess, indem das vorab trainierte TensorFlow-Modell geladen wird.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-134">The Image Classification API starts the training process by loading a pretrained TensorFlow model.</span></span> <span data-ttu-id="7c3fd-135">Der Trainingsprozess setzt sich aus zwei Schritten zusammen:</span><span class="sxs-lookup"><span data-stu-id="7c3fd-135">The training process consists of two steps:</span></span>

1. <span data-ttu-id="7c3fd-136">Engpassphase</span><span class="sxs-lookup"><span data-stu-id="7c3fd-136">Bottleneck phase</span></span>
2. <span data-ttu-id="7c3fd-137">Trainingsphase</span><span class="sxs-lookup"><span data-stu-id="7c3fd-137">Training phase</span></span>

![Trainingsschritte](./media/image-classification-api-transfer-learning/training.png)

### <a name="bottleneck-phase"></a><span data-ttu-id="7c3fd-139">Engpassphase</span><span class="sxs-lookup"><span data-stu-id="7c3fd-139">Bottleneck phase</span></span>

<span data-ttu-id="7c3fd-140">Während der Engpassphase werden die Trainingsbilder geladen, wobei die Pixelwerte als Eingabe dienen, oder aber Features für die fixierten Ebenen des vorab trainierten Modells.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-140">During the bottleneck phase, the set of training images is loaded and the pixel values are used as input, or features, for the frozen layers of the pretrained model.</span></span> <span data-ttu-id="7c3fd-141">Die fixierten Ebenen umfassen sämtliche Ebenen im neuronalen Netz bis hin zur vorletzte Ebene, die inoffiziell auch als Engpassebene bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-141">The frozen layers include all of the layers in the neural network up to the penultimate layer, informally known as the bottleneck layer.</span></span> <span data-ttu-id="7c3fd-142">Diese Ebenen werden „fixiert“ genannt, da für diese kein Training stattfindet und Vorgänge lediglich weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-142">These layers are referred to as frozen because no training will occur on these layers and operations are pass-through.</span></span> <span data-ttu-id="7c3fd-143">In diesen fixierten Ebenen werden die zugrunde liegenden Muster berechnet, anhand derer ein Modell zwischen den verschiedenen Klassen unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-143">It's at these frozen layers where the lower-level patterns that help a model differentiate between the different classes are computed.</span></span> <span data-ttu-id="7c3fd-144">Je mehr Ebenen es gibt, desto rechenintensiver ist dieser Schritt.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-144">The larger the number of layers, the more computationally intensive this step is.</span></span> <span data-ttu-id="7c3fd-145">Da es sich hierbei um eine einmalige Berechnung handelt, können die Ergebnisse zwischengespeichert und in späteren Durchläufen verwendet werden, wenn mit verschiedenen Parametern experimentiert wird.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-145">Fortunately, since this is a one-time calculation, the results can be cached and used in later runs when experimenting with different parameters.</span></span>

### <a name="training-phase"></a><span data-ttu-id="7c3fd-146">Trainingsphase</span><span class="sxs-lookup"><span data-stu-id="7c3fd-146">Training phase</span></span>

<span data-ttu-id="7c3fd-147">Sobald die Ausgabewerte aus der Engpassphase berechnet sind, dienen sie als Eingabe für das nochmalige Training der letzten Ebene des Modells.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-147">Once the output values from the bottleneck phase are computed, they are used as input to retrain the final layer of the model.</span></span> <span data-ttu-id="7c3fd-148">Dieser Prozess ist iterativ und wird so oft ausgeführt, wie durch Modellparameter angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-148">This process is iterative and runs for the number of times specified by model parameters.</span></span> <span data-ttu-id="7c3fd-149">Bei jeder Ausführung werden Verlust und Genauigkeit ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-149">During each run, the loss and accuracy are evaluated.</span></span> <span data-ttu-id="7c3fd-150">Anschließend werden die entsprechenden Anpassungen zur Verbesserung des Modells vorgenommen, um so den Verlust zu minimieren und die Genauigkeit zu maximieren.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-150">Then, the appropriate adjustments are made to improve the model with the goal of minimizing the loss and maximizing the accuracy.</span></span> <span data-ttu-id="7c3fd-151">Nach Abschluss des Trainings verfügen Sie über zwei Modellformate.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-151">Once training is finished, two model formats are output.</span></span> <span data-ttu-id="7c3fd-152">Eines wird als `.pb`-Version des Modells und das andere als für ML.NET serialisierte `.zip`-Version des Modells bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-152">One of them is the `.pb` version of the model and the other is the `.zip` ML.NET serialized version of the model.</span></span> <span data-ttu-id="7c3fd-153">Für die Arbeit in von ML.NET unterstützten Umgebungen wird die `.zip`-Version des Modells empfohlen.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-153">When working in environments supported by ML.NET, it is recommended to use the `.zip` version of the model.</span></span> <span data-ttu-id="7c3fd-154">In Umgebungen, in denen ML.NET nicht unterstützt wird, haben Sie jedoch die Möglichkeit, die `.pb`-Version zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-154">However, in environments where ML.NET is not supported, you have the option of using the `.pb` version.</span></span>

## <a name="understand-the-pretrained-model"></a><span data-ttu-id="7c3fd-155">Grundlegendes zum vorab trainierten Modell</span><span class="sxs-lookup"><span data-stu-id="7c3fd-155">Understand the pretrained model</span></span>

<span data-ttu-id="7c3fd-156">Das in diesem Tutorial verwendete vorab trainierte Modell ist die 101-Ebenen-Variante des Modells „Residual Network (ResNet) v2“.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-156">The pretrained model used in this tutorial is the 101-layer variant of the Residual Network (ResNet) v2 model.</span></span> <span data-ttu-id="7c3fd-157">Das Originalmodell ist darauf trainiert, Bilder in tausend Kategorien einzuteilen.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-157">The original model is trained to classify images into a thousand categories.</span></span> <span data-ttu-id="7c3fd-158">Das Modell verwendet ein Bild der Größe 224 × 224 als Eingabe und gibt die Klassenwahrscheinlichkeiten für jede der Klassen aus, für die es trainiert ist.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-158">The model takes as input an image of size 224 x 224 and outputs the class probabilities for each of the classes it's trained on.</span></span> <span data-ttu-id="7c3fd-159">Ein Teil dieses Modells wird verwendet, um ein neues Modell mit benutzerdefinierten Bildern zu trainieren, damit dieses Vorhersagen für zwei Klassen treffen kann.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-159">Part of this model is used to train a new model using custom images to make predictions between two classes.</span></span>

## <a name="create-console-application"></a><span data-ttu-id="7c3fd-160">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="7c3fd-160">Create console application</span></span>

<span data-ttu-id="7c3fd-161">Nachdem Sie nun grundlegende Kenntnisse über das Transferlernen und die Bildklassifizierungs-API haben, ist es an der Zeit, die Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-161">Now that you have a general understanding of transfer learning and the Image Classification API, it's time to build the application.</span></span>

1. <span data-ttu-id="7c3fd-162">Erstellen Sie eine **.NET Core-Konsolenanwendung in C#** namens „DeepLearning_ImageClassification_Binary“.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-162">Create a **C# .NET Core Console Application** called "DeepLearning_ImageClassification_Binary".</span></span>
1. <span data-ttu-id="7c3fd-163">Installieren Sie das NuGet-Paket **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="7c3fd-163">Install the **Microsoft.ML** NuGet Package:</span></span>

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    1. <span data-ttu-id="7c3fd-164">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-164">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span>
    1. <span data-ttu-id="7c3fd-165">Wählen Sie als Paketquelle „nuget.org“ aus.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-165">Choose "nuget.org" as the Package source.</span></span>
    1. <span data-ttu-id="7c3fd-166">Wählen Sie die Registerkarte **Durchsuchen** aus.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-166">Select the **Browse** tab.</span></span>
    1. <span data-ttu-id="7c3fd-167">Aktivieren Sie das Kontrollkästchen **Vorabversion einbeziehen**.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-167">Check the **Include prerelease** checkbox.</span></span>
    1. <span data-ttu-id="7c3fd-168">Suchen Sie nach **Microsoft.ML**.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-168">Search for **Microsoft.ML**.</span></span>
    1. <span data-ttu-id="7c3fd-169">Wählen Sie die Schaltfläche **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-169">Select the **Install** button.</span></span>
    1. <span data-ttu-id="7c3fd-170">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-170">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>
    1. <span data-ttu-id="7c3fd-171">Wiederholen Sie diese Schritte für die NuGet-Pakete **Microsoft.ML.Vision**, **SciSharp.TensorFlow.Redist** und **Microsoft.ML.ImageAnalytics**.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-171">Repeat these steps for the **Microsoft.ML.Vision**, **SciSharp.TensorFlow.Redist**, and **Microsoft.ML.ImageAnalytics** NuGet packages.</span></span>

### <a name="prepare-and-understand-the-data"></a><span data-ttu-id="7c3fd-172">Vorbereiten und Verstehen der Daten</span><span class="sxs-lookup"><span data-stu-id="7c3fd-172">Prepare and understand the data</span></span>

> [!NOTE]
> <span data-ttu-id="7c3fd-173">Die Datasets für dieses Tutorial stammen von Marc Maguire, Sattar Dorafshan und Robert J. Thomas, „SDNET2018: A concrete crack image dataset for machine learning applications“ (2018).</span><span class="sxs-lookup"><span data-stu-id="7c3fd-173">The datasets for this tutorial are from Maguire, Marc; Dorafshan, Sattar; and Thomas, Robert J., "SDNET2018: A concrete crack image dataset for machine learning applications" (2018).</span></span> <span data-ttu-id="7c3fd-174">Durchsuchen Sie alle Datasets.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-174">Browse all Datasets.</span></span> <span data-ttu-id="7c3fd-175">Dokument 48.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-175">Paper 48.</span></span> <https://digitalcommons.usu.edu/all_datasets/48>

<span data-ttu-id="7c3fd-176">SDNET2018 ist ein Bilddataset, das Anmerkungen für gerissene und nicht gerissene Betonstrukturen (Brückenbeläge, Mauern und Gehwege) enthält.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-176">SDNET2018 is an image dataset that contains annotations for cracked and non-cracked concrete structures (bridge decks, walls, and pavement).</span></span>

![Beispiele für Brückenbeläge des SDNET2018-Datasets](./media/image-classification-api-transfer-learning/sdnet2018decksamples.png)

<span data-ttu-id="7c3fd-178">Die Daten sind in drei Unterverzeichnissen organisiert:</span><span class="sxs-lookup"><span data-stu-id="7c3fd-178">The data is organized in three subdirectories:</span></span>

- <span data-ttu-id="7c3fd-179">D enthält Bilder von Brückenbelägen</span><span class="sxs-lookup"><span data-stu-id="7c3fd-179">D contains bridge deck images</span></span>
- <span data-ttu-id="7c3fd-180">P enthält Bilder von Gehwegen</span><span class="sxs-lookup"><span data-stu-id="7c3fd-180">P contains pavement images</span></span>
- <span data-ttu-id="7c3fd-181">W enthält Bilder von Mauern</span><span class="sxs-lookup"><span data-stu-id="7c3fd-181">W contains wall images</span></span>

<span data-ttu-id="7c3fd-182">Jedes dieser Unterverzeichnisse enthält zwei zusätzliche Unterverzeichnisse mit Präfixen:</span><span class="sxs-lookup"><span data-stu-id="7c3fd-182">Each of these subdirectories contains two additional prefixed subdirectories:</span></span>

- <span data-ttu-id="7c3fd-183">C ist das Präfix für gerissene Oberflächen</span><span class="sxs-lookup"><span data-stu-id="7c3fd-183">C is the prefix used for cracked surfaces</span></span>
- <span data-ttu-id="7c3fd-184">U ist das Präfix für nicht gerissene Oberflächen</span><span class="sxs-lookup"><span data-stu-id="7c3fd-184">U is the prefix used for uncracked surfaces</span></span>

<span data-ttu-id="7c3fd-185">In diesem Tutorial werden ausschließlich Bilder von Brückenbelägen verwendet.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-185">In this tutorial, only bridge deck images are used.</span></span>

1. <span data-ttu-id="7c3fd-186">Laden Sie das [Dataset](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/assets.zip) herunter, und entpacken Sie es.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-186">Download the [dataset](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/assets.zip) and unzip.</span></span>
1. <span data-ttu-id="7c3fd-187">Erstellen Sie in Ihrem Projekt ein Verzeichnis mit dem Namen „assets“, um darin die Datasetdateien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-187">Create a directory named "assets" in your project to save your dataset files.</span></span>
1. <span data-ttu-id="7c3fd-188">Kopieren Sie die Unterverzeichnisse *CD* und *UD* aus dem zuletzt entpackten Verzeichnis in das Verzeichnis *assets*.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-188">Copy the *CD* and *UD* subdirectories from the recently unzipped directory to the *assets* directory.</span></span>

### <a name="create-input-and-output-classes"></a><span data-ttu-id="7c3fd-189">Erstellen von Eingabe- und Ausgabeklassen</span><span class="sxs-lookup"><span data-stu-id="7c3fd-189">Create input and output classes</span></span>

1. <span data-ttu-id="7c3fd-190">Öffnen Sie die Datei *Program.cs*, und ersetzen Sie die vorhandenen `using`-Anweisungen am Anfang der Datei durch die folgenden Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="7c3fd-190">Open the *Program.cs* file and replace the existing `using` statements at the top of the file with the following:</span></span>

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L1-L7)]

1. <span data-ttu-id="7c3fd-191">Erstellen Sie in der Datei *Program.cs* unter der `Program`-Klasse eine Klasse mit dem Namen `ImageData`.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-191">Below the `Program` class in *Program.cs*, create a class called `ImageData`.</span></span> <span data-ttu-id="7c3fd-192">Diese Klasse wird verwendet, um die ursprünglich geladenen Daten darzustellen.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-192">This class is used to represent the initially loaded data.</span></span>

    [!code-csharp [ImageDataClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L138-L143)]

    <span data-ttu-id="7c3fd-193">`ImageData` enthält die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="7c3fd-193">`ImageData` contains the following properties:</span></span>

    - <span data-ttu-id="7c3fd-194">`ImagePath` ist der vollqualifizierte Pfad, in dem das Bild gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-194">`ImagePath` is the fully qualified path where the image is stored.</span></span>
    - <span data-ttu-id="7c3fd-195">`Label` ist die Kategorie, zu der das Bild gehört.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-195">`Label` is the category the image belongs to.</span></span> <span data-ttu-id="7c3fd-196">Dies ist der vorherzusagende Wert.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-196">This is the value to predict.</span></span>

1. <span data-ttu-id="7c3fd-197">Erstellen Sie Klassen für Ihre Eingabe- und Ausgabedaten.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-197">Create classes for your input and output data</span></span>

    1. <span data-ttu-id="7c3fd-198">Definieren Sie unter der `ImageData`-Klasse das Schema Ihrer Eingabedaten in einer neuen Klasse namens `ModelInput`.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-198">Below the `ImageData` class, define the schema of your input data in a new class called `ModelInput`.</span></span>

        [!code-csharp [ModelInputClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L145-L154)]

        <span data-ttu-id="7c3fd-199">`ModelInput` enthält die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="7c3fd-199">`ModelInput` contains the following properties:</span></span>

        - <span data-ttu-id="7c3fd-200">`Image` ist die `byte[]`-Darstellung des Bilds.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-200">`Image` is the `byte[]` representation of the image.</span></span> <span data-ttu-id="7c3fd-201">Bei dem Modell wird erwartet, dass Bilddaten diesen Typ für das Training aufweisen.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-201">The model expects image data to be of this type for training.</span></span>
        - <span data-ttu-id="7c3fd-202">`LabelAsKey` ist die numerische Darstellung von `Label`.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-202">`LabelAsKey` is the numerical representation of the `Label`.</span></span>
        - <span data-ttu-id="7c3fd-203">`ImagePath` ist der vollqualifizierte Pfad, in dem das Bild gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-203">`ImagePath` is the fully qualified path where the image is stored.</span></span>
        - <span data-ttu-id="7c3fd-204">`Label` ist die Kategorie, zu der das Bild gehört.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-204">`Label` is the category the image belongs to.</span></span> <span data-ttu-id="7c3fd-205">Dies ist der vorherzusagende Wert.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-205">This is the value to predict.</span></span>

        <span data-ttu-id="7c3fd-206">Nur `Image` und `LabelAsKey` werden verwendet, um das Modell zu trainieren und Vorhersagen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-206">Only `Image` and `LabelAsKey` are used to train the model and make predictions.</span></span> <span data-ttu-id="7c3fd-207">Die Eigenschaften `ImagePath` und `Label` werden beibehalten, damit einfacher auf den Namen und die Kategorie der ursprünglichen Bilddatei zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-207">The `ImagePath` and `Label` properties are kept for convenience to access the original image file name and category.</span></span>

    1. <span data-ttu-id="7c3fd-208">Anschließend definieren Sie unter der `ModelInput`-Klasse das Schema Ihrer Ausgabedaten in einer neuen Klasse namens `ModelOutput`.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-208">Then, below the `ModelInput` class, define the schema of your output data in a new class called `ModelOutput`.</span></span>

        [!code-csharp [ModelOutputClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L156-L163)]

        <span data-ttu-id="7c3fd-209">`ModelOutput` enthält die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="7c3fd-209">`ModelOutput` contains the following properties:</span></span>

        - <span data-ttu-id="7c3fd-210">`ImagePath` ist der vollqualifizierte Pfad, in dem das Bild gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-210">`ImagePath` is the fully qualified path where the image is stored.</span></span>
        - <span data-ttu-id="7c3fd-211">`Label` ist die ursprüngliche Kategorie, zu der das Bild gehört.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-211">`Label` is the original category the image belongs to.</span></span> <span data-ttu-id="7c3fd-212">Dies ist der vorherzusagende Wert.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-212">This is the value to predict.</span></span>
        - <span data-ttu-id="7c3fd-213">`PredictedLabel` ist der vom Modell vorhergesagte Wert.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-213">`PredictedLabel` is the value predicted by the model.</span></span>

        <span data-ttu-id="7c3fd-214">Ähnlich wie bei `ModelInput` ist nur `PredictedLabel` für Vorhersagen erforderlich, da dies die vom Modell getroffene Vorhersage enthält.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-214">Similar to `ModelInput`, only the `PredictedLabel` is required to make predictions since it contains the prediction made by the model.</span></span> <span data-ttu-id="7c3fd-215">Die Eigenschaften `ImagePath` und `Label` werden beibehalten, damit einfacher auf den Namen und die Kategorie der ursprünglichen Bilddatei zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-215">The `ImagePath` and `Label` properties are retained for convenience to access the original image file name and category.</span></span>

### <a name="create-workspace-directory"></a><span data-ttu-id="7c3fd-216">Erstellen eines Arbeitsbereichsverzeichnisses</span><span class="sxs-lookup"><span data-stu-id="7c3fd-216">Create workspace directory</span></span>

<span data-ttu-id="7c3fd-217">Wenn sich Trainings-und Validierungsdaten nicht häufig ändern, empfiehlt es sich, die berechneten Engpasswerte für weitere Ausführungen zwischenzuspeichern.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-217">When training and validation data do not change often, it is good practice to cache the computed bottleneck values for further runs.</span></span>

1. <span data-ttu-id="7c3fd-218">Erstellen Sie in Ihrem Projekt ein neues Verzeichnis namens *workspace*, um die berechneten Engpasswerte und die `.pb`-Version des Modells zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-218">In your project, create a new directory called *workspace* to store the computed bottleneck values and `.pb` version of the model.</span></span>

### <a name="define-paths-and-initialize-variables"></a><span data-ttu-id="7c3fd-219">Definieren von Pfaden und Initialisieren von Variablen</span><span class="sxs-lookup"><span data-stu-id="7c3fd-219">Define paths and initialize variables</span></span>

1. <span data-ttu-id="7c3fd-220">Definieren Sie innerhalb der `Main`-Methode den Speicherort Ihrer Ressourcen, der berechneten Engpasswerte und der `.pb`-Version des Modells.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-220">Inside the `Main` method, define the location of your assets, computed bottleneck values and `.pb` version of the model.</span></span>

    [!code-csharp [DefinePaths](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L15-L17)]

1. <span data-ttu-id="7c3fd-221">Initialisieren Sie die `mlContext`-Variable mit einer neuen Instanz von [MLContext](xref:Microsoft.ML.MLContext).</span><span class="sxs-lookup"><span data-stu-id="7c3fd-221">Initialize the `mlContext` variable with a new instance of [MLContext](xref:Microsoft.ML.MLContext).</span></span>

    [!code-csharp [MLContext](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L19)]

    <span data-ttu-id="7c3fd-222">Die [MLContext](xref:Microsoft.ML.MLContext)-Klasse ist der Startpunkt für alle ML.NET-Vorgänge. Durch das Initialisieren von MLContext wird eine neue ML.NET-Umgebung erstellt, die für mehrere Objekte des Modellerstellungsworkflows verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-222">The [MLContext](xref:Microsoft.ML.MLContext) class is a starting point for all ML.NET operations, and initializing mlContext creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="7c3fd-223">Die Klasse ähnelt dem Konzept von `DbContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-223">It's similar, conceptually, to `DbContext` in Entity Framework.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="7c3fd-224">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="7c3fd-224">Load the data</span></span>

### <a name="create-data-loading-utility-method"></a><span data-ttu-id="7c3fd-225">Erstellen einer Hilfsmethode zum Laden von Daten</span><span class="sxs-lookup"><span data-stu-id="7c3fd-225">Create data loading utility method</span></span>

<span data-ttu-id="7c3fd-226">Die Bilder werden in zwei Unterverzeichnissen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-226">The images are stored in two subdirectories.</span></span> <span data-ttu-id="7c3fd-227">Vor dem Laden der Daten müssen diese in eine Liste mit `ImageData`-Objekten formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-227">Before loading the data, it needs to be formatted into a list of `ImageData` objects.</span></span> <span data-ttu-id="7c3fd-228">Erstellen Sie hierzu die `LoadImagesFromDirectory`-Methode unter der `Main`-Methode.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-228">To do so, create the `LoadImagesFromDirectory` method below the `Main` method.</span></span>

```csharp
public static IEnumerable<ImageData> LoadImagesFromDirectory(string folder, bool useFolderNameAsLabel = true)
{

}
```

1. <span data-ttu-id="7c3fd-229">Fügen Sie in `LoadImagesFromDirectory` den folgenden Code hinzu, um alle Dateipfade aus den Unterverzeichnissen abzurufen:</span><span class="sxs-lookup"><span data-stu-id="7c3fd-229">Inside the `LoadImagesFromDirectory`, add the following code to get all of the file paths from the subdirectories:</span></span>

    [!code-csharp [GetFiles](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L105-L106)]

1. <span data-ttu-id="7c3fd-230">Durchlaufen Sie dann die einzelnen Dateien mithilfe einer `foreach`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-230">Then, iterate through each of the files using a `foreach` statement.</span></span>

    ```csharp
    foreach (var file in files)
    {

    }
    ```

1. <span data-ttu-id="7c3fd-231">Überprüfen Sie, ob in der `foreach`-Anweisung die Dateierweiterungen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-231">Inside the `foreach` statement, check that the file extensions are supported.</span></span> <span data-ttu-id="7c3fd-232">Die Bildklassifizierungs-API unterstützt JPEG- und PNG-Formate.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-232">The Image Classification API supports JPEG and PNG formats.</span></span>

    [!code-csharp [CheckExtension](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L110-L111)]

1. <span data-ttu-id="7c3fd-233">Rufen Sie anschließend die Bezeichnung für die Datei ab.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-233">Then, get the label for the file.</span></span> <span data-ttu-id="7c3fd-234">Wenn der `useFolderNameAsLabel`-Parameter auf `true` festgelegt ist, wird das übergeordnete Verzeichnis, in dem die Datei gespeichert wird, als Bezeichnung verwendet.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-234">If the `useFolderNameAsLabel` parameter is set to `true`, then the parent directory where the file is saved is used as the label.</span></span> <span data-ttu-id="7c3fd-235">Andernfalls wird erwartet, dass die Bezeichnung ein Präfix des Dateinamens oder der Dateiname selbst ist.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-235">Otherwise, it expects the label to be a prefix of the file name or the file name itself.</span></span>

    [!code-csharp [GetLabel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L113-L127)]

1. <span data-ttu-id="7c3fd-236">Abschließend erstellen Sie eine neue Instanz von `ModelInput`.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-236">Finally, create a new instance of `ModelInput`.</span></span>

    [!code-csharp [CreateImageData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L129-L133)]

### <a name="prepare-the-data"></a><span data-ttu-id="7c3fd-237">Vorbereiten der Daten</span><span class="sxs-lookup"><span data-stu-id="7c3fd-237">Prepare the data</span></span>

1. <span data-ttu-id="7c3fd-238">Verwenden Sie in der `Main`-Methode die `LoadImagesFromDirectory`-Hilfsmethode, um die Liste der Bilder abzurufen, die für das Training verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-238">Back in the `Main` method, use the `LoadImagesFromDirectory` utility method to get the list of images used for training.</span></span>

    [!code-csharp [LoadImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L22)]

1. <span data-ttu-id="7c3fd-239">Laden Sie dann die Bilder mithilfe der [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*)-Methode in eine [`IDataView`](xref:Microsoft.ML.IDataView)-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-239">Then, load the images into an [`IDataView`](xref:Microsoft.ML.IDataView) using the [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) method.</span></span>

    [!code-csharp [CreateIDataView](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L24)]

1. <span data-ttu-id="7c3fd-240">Die Daten werden in der Reihenfolge geladen, in der sie aus den Verzeichnissen gelesen wurden.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-240">The data is loaded in the order it was read from the directories.</span></span> <span data-ttu-id="7c3fd-241">Um die Daten auszugleichen, mischen Sie sie zufällig mithilfe der [`ShuffleRows`](xref:Microsoft.ML.DataOperationsCatalog.ShuffleRows*)-Methode.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-241">To balance the data, shuffle it using the [`ShuffleRows`](xref:Microsoft.ML.DataOperationsCatalog.ShuffleRows*) method.</span></span>

    [!code-csharp [ShuffleRows](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L26)]

1. <span data-ttu-id="7c3fd-242">Bei Modellen für maschinelles Lernen wird eine Eingabe im numerischen Format erwartet.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-242">Machine learning models expect input to be in numerical format.</span></span> <span data-ttu-id="7c3fd-243">Daher muss vor dem Training eine Vorverarbeitung der Daten durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-243">Therefore, some preprocessing needs to be done on the data prior to training.</span></span> <span data-ttu-id="7c3fd-244">Erstellen Sie eine [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601), die aus [`MapValueToKey`](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey*) und `LoadRawImageBytes`-Transformationen besteht.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-244">Create an [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) made up of the [`MapValueToKey`](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey*) and `LoadRawImageBytes` transforms.</span></span> <span data-ttu-id="7c3fd-245">Die `MapValueToKey`-Transformation übernimmt den kategorischen Wert aus der Spalte `Label`, konvertiert diesen in einen numerischen `KeyType`-Wert und speichert ihn in einer neuen Spalte namens `LabelAsKey`.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-245">The `MapValueToKey` transform takes the categorical value in the `Label` column, converts it to a numerical `KeyType` value and stores it in a new column called `LabelAsKey`.</span></span> <span data-ttu-id="7c3fd-246">`LoadImages` greift auf Werte aus der Spalte `ImagePath` zusammen mit dem Parameter `imageFolder` zu, um Bilder für das Training zu laden.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-246">The `LoadImages` takes the values from the `ImagePath` column along with the `imageFolder` parameter to load images for training.</span></span>

    [!code-csharp [PreprocessingPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L28-L34)]

1. <span data-ttu-id="7c3fd-247">Verwenden Sie die [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*)-Methode, um die Daten auf die [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601)-Klasse `preprocessingPipeline` gefolgt von der [`Transform`](xref:Microsoft.ML.Data.TransformerChain`1.Transform*)-Methode anzuwenden, wodurch eine [`IDataView`](xref:Microsoft.ML.IDataView)-Schnittstelle zurückgegeben wird, die die vorverarbeiteten Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-247">Use the [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*) method to apply the data to the `preprocessingPipeline` [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) followed by the [`Transform`](xref:Microsoft.ML.Data.TransformerChain`1.Transform*) method, which returns an [`IDataView`](xref:Microsoft.ML.IDataView) containing the pre-processed data.</span></span>

    [!code-csharp [PreprocessData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L36-L38)]

1. <span data-ttu-id="7c3fd-248">Beim Trainieren eines Modells ist es wichtig, sowohl über ein Trainingsdataset als auch ein Validierungsdataset zu verfügen.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-248">To train a model, it's important to have a training dataset as well as a validation dataset.</span></span> <span data-ttu-id="7c3fd-249">Das Modell wird mit dem Trainingsset trainiert.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-249">The model is trained on the training set.</span></span> <span data-ttu-id="7c3fd-250">Wie gut es Vorhersagen über unbekannte Daten erstellt, wird an der Leistung im Vergleich zum Validierungsset gemessen.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-250">How well it makes predictions on unseen data is measured by the performance against the validation set.</span></span> <span data-ttu-id="7c3fd-251">Basierend auf den Ergebnissen dieser Leistung nimmt das Modell Anpassungen an dem Gelernten vor, um die Ergebnisse zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-251">Based on the results of that performance, the model makes adjustments to what it has learned in an effort to improve.</span></span> <span data-ttu-id="7c3fd-252">Das Validierungsset kann entweder aus der Aufteilung des ursprünglichen Datasets oder aus einer anderen Quelle stammen, die bereits für diesen Zweck vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-252">The validation set can come from either splitting your original dataset or from another source that has already been set aside for this purpose.</span></span> <span data-ttu-id="7c3fd-253">In diesem Fall wird das vorverarbeitete Datenset in Trainings-, Validierungs- und Testsets unterteilt.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-253">In this case, the pre-processed dataset is split into training, validation and test sets.</span></span>

    [!code-csharp [CreateDataSplits](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L40-L41)]

    <span data-ttu-id="7c3fd-254">Im obigen Codebeispiel werden zwei Aufteilungen vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-254">The code sample above performs two splits.</span></span> <span data-ttu-id="7c3fd-255">Zunächst werden die vorverarbeiteten Daten aufgeteilt, wobei 70% für das Training und die restlichen 30% für die Validierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-255">First, the pre-processed data is split and 70% is used for training while the remaining 30% is used for validation.</span></span> <span data-ttu-id="7c3fd-256">Anschließend werden die 30% des Validierungssets weiter in Validierungs- und Testsets unterteilt, wobei 90% für die Validierung und 10% für Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-256">Then, the 30% validation set is further split into validation and test sets where 90% is used for validation and 10% is used for testing.</span></span>

    <span data-ttu-id="7c3fd-257">Ein gutes Beispiel, um den Sinn und Zweck dieser Datenaufteilungen zu verstehen, ist eine Prüfungsituation.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-257">A way to think about the purpose of these data partitions is taking an exam.</span></span> <span data-ttu-id="7c3fd-258">Wenn Sie für eine Prüfung lernen, lesen Sie Ihre Notizen, Bücher oder andere Unterlagen, um die in der Prüfung enthaltenen Themen zu lernen und zu vertiefen.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-258">When studying for an exam, you review your notes, books, or other resources to get a grasp on the concepts that are on the exam.</span></span> <span data-ttu-id="7c3fd-259">Dafür ist das Trainingsset da.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-259">This is what the train set is for.</span></span> <span data-ttu-id="7c3fd-260">Dann können Sie eine Probeklausur ablegen, um Ihren Wissensstand zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-260">Then, you might take a mock exam to validate your knowledge.</span></span> <span data-ttu-id="7c3fd-261">Hier bietet sich das Validierungsset an.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-261">This is where the validation set comes in handy.</span></span> <span data-ttu-id="7c3fd-262">Sie möchten vor der eigentlichen Prüfung feststellen, ob Sie die Inhalte richtig verstanden haben.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-262">You want to check whether you have a good grasp of the concepts before taking the actual exam.</span></span> <span data-ttu-id="7c3fd-263">Ausgehend von den Ergebnissen können Sie herausfinden, was Sie falsch gemacht bzw. nicht richtig verstanden haben, und so die Ergebnisse in den Lernprozess für die eigentliche Prüfung einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-263">Based on those results, you take note of what you got wrong or didn't understand well and incorporate your changes as you review for the real exam.</span></span> <span data-ttu-id="7c3fd-264">Zum Schluss legen Sie die Prüfung ab.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-264">Finally, you take the exam.</span></span> <span data-ttu-id="7c3fd-265">Dafür wird das Testset verwendet.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-265">This is what the test set is used for.</span></span> <span data-ttu-id="7c3fd-266">Sie haben die Fragen in der Prüfung noch nie gesehen und nutzen zur Bearbeitung der vorliegenden Aufgabe nun das, was Sie sich durch den Lernprozess (Training) und die Überprüfung des Gelernten (Validierung) angeeignet haben.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-266">You've never seen the questions that are on the exam and now use what you learned from training and validation to apply your knowledge to the task at hand.</span></span>

1. <span data-ttu-id="7c3fd-267">Ordnen Sie den Teilbereichen die jeweiligen Werte für die Trainings-, Validierungs- und Testdaten zu.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-267">Assign the partitions their respective values for the train, validation and test data.</span></span>

    [!code-csharp [CreateDatasets](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L43-L45)]

## <a name="define-the-training-pipeline"></a><span data-ttu-id="7c3fd-268">Definieren der Trainingspipeline</span><span class="sxs-lookup"><span data-stu-id="7c3fd-268">Define the training pipeline</span></span>

<span data-ttu-id="7c3fd-269">Das Modelltraining umfasst mehrere Schritte.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-269">Model training consists of a couple of steps.</span></span> <span data-ttu-id="7c3fd-270">Zunächst wird die Bildklassifizierungs-API verwendet, um das Modell zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-270">First, Image Classification API is used to train the model.</span></span> <span data-ttu-id="7c3fd-271">Anschließend werden die verschlüsselten Bezeichnungen in der Spalte `PredictedLabel` mithilfe der `MapKeyToValue`-Transformation wieder in ihren ursprünglichen kategorischen Wert konvertiert.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-271">Then, the encoded labels in the `PredictedLabel` column are converted back to their original categorical value using the `MapKeyToValue` transform.</span></span>

1. <span data-ttu-id="7c3fd-272">Erstellen Sie eine neue Variable, um einen Satz erforderlicher und optionaler Parameter für ein `ImageClassificationTrainer`-Element zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-272">Create a new variable to store a set of required and optional parameters for an `ImageClassificationTrainer`.</span></span>

    [!code-csharp [ClassifierOptions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L47-L58)]

    <span data-ttu-id="7c3fd-273">Ein `ImageClassificationTrainer`-Element nimmt mehrere optionale Parameter an:</span><span class="sxs-lookup"><span data-stu-id="7c3fd-273">An `ImageClassificationTrainer` takes several optional parameters:</span></span>

    - <span data-ttu-id="7c3fd-274">`FeatureColumnName` ist die Spalte, die als Eingabe für das Modell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-274">`FeatureColumnName` is the column that is used as input for the model.</span></span>
    - <span data-ttu-id="7c3fd-275">`LabelColumnName` ist die Spalte für den vorherzusagenden Wert.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-275">`LabelColumnName` is the column for the value to predict.</span></span>
    - <span data-ttu-id="7c3fd-276">`ValidationSet` ist die [`IDataView`](xref:Microsoft.ML.IDataView)-Schnittstelle, die die Validierungsdaten enthält.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-276">`ValidationSet` is the [`IDataView`](xref:Microsoft.ML.IDataView) containing the validation data.</span></span>
    - <span data-ttu-id="7c3fd-277">`Arch` definiert, welche der vorab trainierten Modellarchitekturen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-277">`Arch` defines which of the pretrained model architectures to use.</span></span> <span data-ttu-id="7c3fd-278">In diesem Tutorial wird die 101-Ebenen-Variante des Modells „ResNetv2“ verwendet.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-278">This tutorial uses the 101-layer variant of the ResNetv2 model.</span></span>
    - <span data-ttu-id="7c3fd-279">`MetricsCallback` verknüpft eine Funktion, um den Fortschritt während des Trainings zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-279">`MetricsCallback` binds a function to track the progress during training.</span></span>
    - <span data-ttu-id="7c3fd-280">`TestOnTrainSet` weist das Modell an, die Leistung anhand des Trainingssets zu messen, wenn kein Validierungsset vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-280">`TestOnTrainSet` tells the model to measure performance against the training set when no validation set is present.</span></span>
    - <span data-ttu-id="7c3fd-281">`ReuseTrainSetBottleneckCachedValues` informiert das Modell, ob die zwischengespeicherten Werte aus der Engpassphase in nachfolgenden Durchläufen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-281">`ReuseTrainSetBottleneckCachedValues` tells the model whether to use the cached values from the bottleneck phase in subsequent runs.</span></span> <span data-ttu-id="7c3fd-282">Die Engpassphase ist eine einmalige Pass-Through-Berechnung, die bei der ersten Durchführung sehr rechenintensiv ist.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-282">The bottleneck phase is a one-time pass-through computation that is computationally intensive the first time it is performed.</span></span> <span data-ttu-id="7c3fd-283">Wenn sich die Trainingsdaten nicht ändern, und Sie mit einer anderen Anzahl von Epochen oder anderen Batchgrößen experimentieren möchten, können Sie mit den zwischengespeicherten Werten den Zeitaufwand für das Training eines Modells erheblich verringern.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-283">If the training data does not change and you want to experiment using a different number of epochs or batch size, using the cached values significantly reduces the amount of time required to train a model.</span></span>
    - <span data-ttu-id="7c3fd-284">`ReuseValidationSetBottleneckCachedValues` ist vergleichbar mit `ReuseTrainSetBottleneckCachedValues`, allerdings handelt es sich in diesem Fall um das Validierungsdataset.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-284">`ReuseValidationSetBottleneckCachedValues` is similar to `ReuseTrainSetBottleneckCachedValues` only that in this case it's for the validation dataset.</span></span>
    - <span data-ttu-id="7c3fd-285">`WorkspacePath` definiert das Verzeichnis, in dem die berechneten Engpasswerte und die `.pb`-Version des Modells gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-285">`WorkspacePath` defines the directory where to store the computed bottleneck values and `.pb` version of the model.</span></span>

1. <span data-ttu-id="7c3fd-286">Definieren Sie die [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601)-Trainingspipeline, die aus `mapLabelEstimator` und `ImageClassificationTrainer` besteht.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-286">Define the [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) training pipeline that consists of both the `mapLabelEstimator` and the `ImageClassificationTrainer`.</span></span>

    [!code-csharp [TrainingPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L60-L61)]

1. <span data-ttu-id="7c3fd-287">Verwenden Sie die Methode [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*), um Ihr Modell zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-287">Use the [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*) method to train your model.</span></span>

    [!code-csharp [TrainModel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L63)]

## <a name="use-the-model"></a><span data-ttu-id="7c3fd-288">Verwenden des Modells</span><span class="sxs-lookup"><span data-stu-id="7c3fd-288">Use the model</span></span>

<span data-ttu-id="7c3fd-289">Nachdem Sie Ihr Modell trainiert haben, ist es an der Zeit, es zur Klassifizierung von Bildern zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-289">Now that you have trained your model, it's time to use it to classify images.</span></span>

<span data-ttu-id="7c3fd-290">Erstellen Sie unter der `Main`-Methode eine neue Hilfsmethode namens `OutputPrediction`, um Vorhersageinformationen in der Konsole anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-290">Below the `Main` method, create a new utility method called `OutputPrediction` to display prediction information in the console.</span></span>

[!code-csharp [OuputPredictionMethod](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L97-L101)]

### <a name="classify-a-single-image"></a><span data-ttu-id="7c3fd-291">Klassifizieren eines einzelnen Bilds</span><span class="sxs-lookup"><span data-stu-id="7c3fd-291">Classify a single image</span></span>

1. <span data-ttu-id="7c3fd-292">Fügen Sie eine neue Methode namens `ClassifySingleImage` unter der `Main`-Methode hinzu, um eine Einzelbildvorhersage zu erstellen und auszugeben.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-292">Add a new method called `ClassifySingleImage` below the `Main` method to make and output a single image prediction.</span></span>

    ```csharp
    public static void ClassifySingleImage(MLContext mlContext, IDataView data, ITransformer trainedModel)
    {

    }
    ```

1. <span data-ttu-id="7c3fd-293">Erstellen Sie eine [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)-Klasse innerhalb der `ClassifySingleImage`-Methode.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-293">Create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) inside the `ClassifySingleImage` method.</span></span> <span data-ttu-id="7c3fd-294">Die [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)-Klasse ist eine praktische API, mit der Sie eine Vorhersage für eine einzelne Dateninstanz übergeben und dann ausführen können.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-294">The [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to pass in and then perform a prediction on a single instance of data.</span></span>

    [!code-csharp [CreatePredictionEngine](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L74)]

1. <span data-ttu-id="7c3fd-295">Um auf eine einzelne `ModelInput`-Instanz zuzugreifen, konvertieren Sie die [`IDataView`](xref:Microsoft.ML.IDataView)-Schnittstelle `data` in eine [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601)-Schnittstelle mit der [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*)-Methode und erhalten Sie dann das erste Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-295">To access a single `ModelInput` instance, convert the `data` [`IDataView`](xref:Microsoft.ML.IDataView) into an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) using the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method and then get the first observation.</span></span>

    [!code-csharp [GetTestInputData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L76)]

1. <span data-ttu-id="7c3fd-296">Verwenden Sie die [`Predict`](xref:Microsoft.ML.PredictionEngine%602.Predict*)-Methode, um das Bild zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-296">Use the [`Predict`](xref:Microsoft.ML.PredictionEngine%602.Predict*) method to classify the image.</span></span>

    [!code-csharp [MakeSinglePrediction](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L78)]

1. <span data-ttu-id="7c3fd-297">Geben Sie die Vorhersage mit der `OutputPrediction`-Methode in der Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-297">Output the prediction to the console with the `OutputPrediction` method.</span></span>

    [!code-csharp [OuputSinglePrediction](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L80-L81)]

1. <span data-ttu-id="7c3fd-298">Rufen Sie innerhalb der `Main`-Methode `ClassifySingleImage` mit dem Testset der Bilder auf.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-298">Inside the `Main` method, call `ClassifySingleImage` using the test set of images.</span></span>

    [!code-csharp [ClassifySingleImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L65)]

### <a name="classify-multiple-images"></a><span data-ttu-id="7c3fd-299">Klassifizieren mehrerer Bilder</span><span class="sxs-lookup"><span data-stu-id="7c3fd-299">Classify multiple images</span></span>

1. <span data-ttu-id="7c3fd-300">Fügen Sie eine neue Methode namens `ClassifyImages` unter der `ClassifySingleImage`-Methode hinzu, um mehrere Bildvorhersagen zu erstellen und auszugeben.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-300">Add a new method called `ClassifyImages` below the `ClassifySingleImage` method to make and output multiple image predictions.</span></span>

    ```csharp
    public static void ClassifyImages(MLContext mlContext, IDataView data, ITransformer trainedModel)
    {

    }
    ```

1. <span data-ttu-id="7c3fd-301">Erstellen Sie mithilfe der [`Transform`](xref:Microsoft.ML.ITransformer.Transform*)-Methode eine [`IDataView`](xref:Microsoft.ML.IDataView)-Schnittstelle, die die Vorhersagen enthält.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-301">Create an [`IDataView`](xref:Microsoft.ML.IDataView) containing the predictions by using the [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) method.</span></span> <span data-ttu-id="7c3fd-302">Fügen Sie der `ClassifyImages`-Methode den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-302">Add the following code inside the `ClassifyImages` method.</span></span>

    [!code-csharp [MakeMultiplePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L86)]

1. <span data-ttu-id="7c3fd-303">Zur Iteration über die Vorhersagen konvertieren Sie die [`IDataView`](xref:Microsoft.ML.IDataView)-Schnittstelle `predictionData` in eine [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601)-Schnittstelle mithilfe der [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*)-Methode und erhalten Sie dann die ersten zehn Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-303">In order to iterate over the predictions, convert the `predictionData` [`IDataView`](xref:Microsoft.ML.IDataView) into an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) using the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method and then get the first 10 observations.</span></span>

    [!code-csharp [IEnumerablePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L88)]

1. <span data-ttu-id="7c3fd-304">Iterieren Sie die ursprünglichen und vorhergesagten Bezeichnungen für die Vorhersagen, und geben Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-304">Iterate and output the original and predicted labels for the predictions.</span></span>

    [!code-csharp [OutputMultiplePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L90-L94)]

1. <span data-ttu-id="7c3fd-305">Abschließend rufen Sie innerhalb der `Main`-Methode `ClassifyImages` mit dem Testset der Bilder auf.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-305">Finally, inside the `Main` method, call `ClassifyImages` using the test set of images.</span></span>

    [!code-csharp [ClassifyImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L67)]

## <a name="run-the-application"></a><span data-ttu-id="7c3fd-306">Ausführen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="7c3fd-306">Run the application</span></span>

<span data-ttu-id="7c3fd-307">Führen Sie die Konsolenanwendung aus.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-307">Run your console app.</span></span> <span data-ttu-id="7c3fd-308">Die Ausgabe sollte in etwa wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-308">The output should be similar to that below.</span></span> <span data-ttu-id="7c3fd-309">Möglicherweise werden Warnungen oder Verarbeitungsnachrichten angezeigt. Diese wurden jedoch aus Gründen der Übersichtlichkeit aus den folgenden Ergebnissen entfernt.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-309">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span> <span data-ttu-id="7c3fd-310">Aus Gründen der Kürze wurde die Ausgabe komprimiert.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-310">For brevity, the output has been condensed.</span></span>

<span data-ttu-id="7c3fd-311">**Engpassphase**</span><span class="sxs-lookup"><span data-stu-id="7c3fd-311">**Bottleneck phase**</span></span>

<span data-ttu-id="7c3fd-312">Für den Bildnamen wird kein Wert ausgegeben, da die Bilder als `byte[]` geladen werden, sodass kein Bildname angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-312">No value is printed for the image name because the images are loaded as a `byte[]` therefore there is no image name to display.</span></span>

```test
Phase: Bottleneck Computation, Dataset used:      Train, Image Index: 279
Phase: Bottleneck Computation, Dataset used:      Train, Image Index: 280
Phase: Bottleneck Computation, Dataset used: Validation, Image Index:   1
Phase: Bottleneck Computation, Dataset used: Validation, Image Index:   2
```

<span data-ttu-id="7c3fd-313">**Trainingsphase**</span><span class="sxs-lookup"><span data-stu-id="7c3fd-313">**Training phase**</span></span>

```text
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  21, Accuracy:  0.6797619
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  22, Accuracy:  0.7642857
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  23, Accuracy:  0.7916667
```

<span data-ttu-id="7c3fd-314">**Klassifizieren der Ausgabe von Bildern**</span><span class="sxs-lookup"><span data-stu-id="7c3fd-314">**Classify images output**</span></span>

```text
Classifying single image
Image: 7001-220.jpg | Actual Value: UD | Predicted Value: UD

Classifying multiple images
Image: 7001-220.jpg | Actual Value: UD | Predicted Value: UD
Image: 7001-163.jpg | Actual Value: UD | Predicted Value: UD
Image: 7001-210.jpg | Actual Value: UD | Predicted Value: UD
```

<span data-ttu-id="7c3fd-315">Bei der Überprüfung des Bilds *7001-220.jpg* können Sie feststellen, dass tatsächlich kein Riss zu sehen ist.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-315">Upon inspection of the *7001-220.jpg* image, you can see that it in fact is not cracked.</span></span>

![Für die Vorhersage verwendetes SDNET2018-Datasetbild](./media/image-classification-api-transfer-learning/predictedimage.jpg)

<span data-ttu-id="7c3fd-317">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="7c3fd-317">Congratulations!</span></span> <span data-ttu-id="7c3fd-318">Sie haben ein Deep-Learning-Modell zur Klassifizierung von Bildern erstellt.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-318">You've now successfully built a deep learning model for classifying images.</span></span>

### <a name="improve-the-model"></a><span data-ttu-id="7c3fd-319">Verbessern des Modells</span><span class="sxs-lookup"><span data-stu-id="7c3fd-319">Improve the model</span></span>

<span data-ttu-id="7c3fd-320">Wenn Sie mit den Ergebnissen des Modells nicht zufrieden sind, können Sie versuchen, seine Leistung zu verbessern, indem Sie einige der folgenden Ansätze ausprobieren:</span><span class="sxs-lookup"><span data-stu-id="7c3fd-320">If you're not satisfied with the results of your model, you can try to improve its performance by trying some of the following approaches:</span></span>

- <span data-ttu-id="7c3fd-321">**Mehr Daten**: Je mehr Beispiele vorhanden sind, von denen ein Modell lernt, desto besser ist dessen Leistung.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-321">**More Data**: The more examples a model learns from, the better it performs.</span></span> <span data-ttu-id="7c3fd-322">Laden Sie das vollständige [SDNET2018-Dataset](https://digitalcommons.usu.edu/cgi/viewcontent.cgi?filename=2&article=1047&context=all_datasets&type=additional) herunter, und verwenden Sie es für das Training.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-322">Download the full [SDNET2018 dataset](https://digitalcommons.usu.edu/cgi/viewcontent.cgi?filename=2&article=1047&context=all_datasets&type=additional) and use it to train.</span></span>
- <span data-ttu-id="7c3fd-323">**Erweitern der Daten**: Eine gängige Technik, um eine größere Datenvielfalt zu erreichen, ist die Erweiterung der Daten durch Aufnahme eines Bilds und Anwendung verschiedener Transformationen (Drehen, Spiegeln, Verschieben, Zuschneiden).</span><span class="sxs-lookup"><span data-stu-id="7c3fd-323">**Augment the data**: A common technique to add variety to the data is to augment the data by taking an image and applying different transforms (rotate, flip, shift, crop).</span></span> <span data-ttu-id="7c3fd-324">Auf diese Weise erhalten Sie verschiedene Beispiele, von denen das Modell lernen kann.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-324">This adds more varied examples for the model to learn from.</span></span>
- <span data-ttu-id="7c3fd-325">**Längere Trainingsdauer**: Umso länger die Trainingsdauer, desto genauer werden die Ergebnisse des Modells sein.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-325">**Train for a longer time**: The longer you train, the more tuned the model will be.</span></span> <span data-ttu-id="7c3fd-326">Durch die Erhöhung der Anzahl von Epochen kann sich die Leistung des Modell erheblich verbessern.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-326">Increasing the number of epochs may improve the performance of your model.</span></span>
- <span data-ttu-id="7c3fd-327">**Experimentieren mit Hyperparametern**: Zusätzlich zu den in diesem Tutorial verwendeten Parametern können weitere Parameter angepasst werden, um die Leistung zu steigern.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-327">**Experiment with the hyper-parameters**: In addition to the parameters used in this tutorial, other parameters can be tuned to potentially improve performance.</span></span> <span data-ttu-id="7c3fd-328">Die Änderung des Lerntempos, das den Umfang der Aktualisierungen am Modell nach jeder Epoche bestimmt, kann zu einer höheren Leistung führen.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-328">Changing the learning rate, which determines the magnitude of updates made to the model after each epoch may improve performance.</span></span>
- <span data-ttu-id="7c3fd-329">**Verwenden einer anderen Modellarchitektur**: Abhängig von der Beschaffenheit Ihrer Daten kann sich das Modell, das am besten deren Merkmale erlernen kann, unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-329">**Use a different model architecture**: Depending on what your data looks like, the model that can best learn its features may differ.</span></span> <span data-ttu-id="7c3fd-330">Wenn Sie mit der Leistung Ihres Modells unzufrieden sind, sollten Sie versuchen, die Architektur zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-330">If you're not satisfied with the performance of your model, try changing the architecture.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="7c3fd-331">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="7c3fd-331">Additional Resources</span></span>

- <span data-ttu-id="7c3fd-332">[Deep Learning im Vergleich zu maschinellem Lernen](/azure/machine-learning/service/concept-deep-learning-vs-machine-learning)</span><span class="sxs-lookup"><span data-stu-id="7c3fd-332">[Deep Learning vs Machine Learning](/azure/machine-learning/service/concept-deep-learning-vs-machine-learning).</span></span>

## <a name="next-steps"></a><span data-ttu-id="7c3fd-333">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7c3fd-333">Next steps</span></span>

<span data-ttu-id="7c3fd-334">In diesem Tutorial haben Sie erfahren, wie Sie ein benutzerdefiniertes Deep-Learning-Modell mithilfe von Transferlernen, einem vorab trainierten TensorFlow-Modell und der ML.NET-Bildklassifizierungs-API erstellen, um Bilder von Betonoberflächen als gerissen oder nicht gerissen zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-334">In this tutorial, you learned how to build a custom deep learning model using transfer learning, a pretrained image classification TensorFlow model and the ML.NET Image Classification API to classify images of concrete surfaces as cracked or uncracked.</span></span>

<span data-ttu-id="7c3fd-335">Fahren Sie mit dem nächsten Tutorial fort, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="7c3fd-335">Advance to the next tutorial to learn more.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="7c3fd-336">Objekterkennung</span><span class="sxs-lookup"><span data-stu-id="7c3fd-336">Object Detection</span></span>](object-detection-onnx.md)
