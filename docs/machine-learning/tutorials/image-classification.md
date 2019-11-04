---
title: 'Tutorial: Generieren eines ML.NET-Bildklassifizierungsmodells aus einem vortrainierten TensorFlow-Modell'
description: Erfahren Sie, wie Sie das erworbene Wissen aus einem vorhandenen TensorFlow-Modell in ein neues ML.NET-Bildklassifizierungsmodell übertragen können. Das TensorFlow-Modell wurde trainiert, um Bilder in tausend Kategorien zu klassifizieren. Das ML.NET-Modell nutzt Übertragungslernen, um Bilder in weniger umfassendere Kategorien zu klassifizieren.
ms.date: 10/30/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
author: natke
ms.author: nakersha
ms.openlocfilehash: bd25a24e467148c46958b6e7ce7b18e181dab5fd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129603"
---
# <a name="tutorial-generate-an-mlnet-image-classification-model-from-a-pre-trained-tensorflow-model"></a><span data-ttu-id="15362-105">Tutorial: Generieren eines ML.NET-Bildklassifizierungsmodells aus einem vortrainierten TensorFlow-Modell</span><span class="sxs-lookup"><span data-stu-id="15362-105">Tutorial: Generate an ML.NET image classification model from a pre-trained TensorFlow model</span></span>

<span data-ttu-id="15362-106">Erfahren Sie, wie Sie das erworbene Wissen aus einem vorhandenen TensorFlow-Modell in ein neues ML.NET-Bildklassifizierungsmodell übertragen können.</span><span class="sxs-lookup"><span data-stu-id="15362-106">Learn how to transfer the knowledge from an existing TensorFlow model into a new ML.NET image classification model.</span></span>

<span data-ttu-id="15362-107">Das TensorFlow-Modell wurde trainiert, um Bilder in tausend Kategorien zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="15362-107">The TensorFlow model was trained to classify images into a thousand categories.</span></span> <span data-ttu-id="15362-108">Das ML.NET-Modell nutzt einen Teil des TensorFlow-Modells in seiner Pipeline, um ein Modell zur Klassifizierung von Bildern in 3 Kategorien zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="15362-108">The ML.NET model makes use of part of the TensorFlow model in its pipeline to train a model to classify images into 3 categories.</span></span>

<span data-ttu-id="15362-109">Das von Grund auf neue Trainieren eines Modells zur [Bildklassifizierung](https://en.wikipedia.org/wiki/Outline_of_object_recognition) erfordert das Einstellen von Millionen von Parametern, zahlreiche bezeichnete Trainingsdaten und eine große Menge an Computeressourcen (Hunderte von GPU-Stunden).</span><span class="sxs-lookup"><span data-stu-id="15362-109">Training an [Image Classification](https://en.wikipedia.org/wiki/Outline_of_object_recognition) model from scratch requires setting millions of parameters, a ton of labeled training data and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="15362-110">Transfer Learning ist zwar nicht so effektiv wie das von Grund auf neue Trainieren eines benutzerdefinierten Modells, doch damit können Sie diesen Prozess durch die Arbeit mit Tausenden von Bildern im Vergleich zur Arbeit mit Millionen bezeichneter Bilder abkürzen und relativ schnell ein benutzerdefiniertes Modell erstellen (innerhalb einer Stunde auf einem Computer ohne eine GPU).</span><span class="sxs-lookup"><span data-stu-id="15362-110">While not as effective as training a custom model from scratch, transfer learning allows you to shortcut this process by working with thousands of images vs. millions of labeled images and build a customized model fairly quickly (within an hour on a machine without a GPU).</span></span> <span data-ttu-id="15362-111">In diesem Tutorial wird dieser Prozess noch weiter herunterskaliert, indem nur ein Dutzend Trainingsbilder verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="15362-111">This tutorial scales that process down even further, using only a dozen training images.</span></span>

<span data-ttu-id="15362-112">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="15362-112">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="15362-113">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="15362-113">Understand the problem</span></span>
> * <span data-ttu-id="15362-114">Integrieren des vortrainierten TensorFlow-Modells in die ML.NET-Pipeline</span><span class="sxs-lookup"><span data-stu-id="15362-114">Incorporate the pre-trained TensorFlow model into the ML.NET pipeline</span></span>
> * <span data-ttu-id="15362-115">Trainieren und Auswerten des ML.NET-Modells</span><span class="sxs-lookup"><span data-stu-id="15362-115">Train and evaluate the ML.NET model</span></span>
> * <span data-ttu-id="15362-116">Klassifizieren eines Testbilds</span><span class="sxs-lookup"><span data-stu-id="15362-116">Classify a test image</span></span>

<span data-ttu-id="15362-117">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).</span><span class="sxs-lookup"><span data-stu-id="15362-117">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span> <span data-ttu-id="15362-118">Hinweis: Die .NET-Projektkonfiguration, die für dieses Tutorial verwendet wird, ist standardmäßig auf .NET Core 2.2 ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="15362-118">Note that by default, the .NET project configuration for this tutorial targets .NET core 2.2.</span></span>

## <a name="what-is-transfer-learning"></a><span data-ttu-id="15362-119">Was ist Übertragungslernen?</span><span class="sxs-lookup"><span data-stu-id="15362-119">What is transfer learning?</span></span>

<span data-ttu-id="15362-120">Übertragungslernen ist der Prozess der Verwendung von Wissen, das bei der Lösung eines Problems erworben wurde, und der Anwendung dieses Wissens auf ein anderes, aber verwandtes Problem.</span><span class="sxs-lookup"><span data-stu-id="15362-120">Transfer learning is the process of using knowledge gained while solving one problem and applying it to a different but related problem.</span></span>

<span data-ttu-id="15362-121">Für dieses Tutorial verwenden Sie einen Teil eines TensorFlow-Modells – trainiert, um Bilder in tausend Kategorien zu klassifizieren – in einem ML.NET-Modell, das Bilder in drei Kategorien klassifiziert.</span><span class="sxs-lookup"><span data-stu-id="15362-121">For this tutorial, you use part of a TensorFlow model - trained to classify images into a thousand categories - in an ML.NET model that classifies images into 3 categories.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="15362-122">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="15362-122">Prerequisites</span></span>

* <span data-ttu-id="15362-123">[Visual Studio 2017 Version 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="15362-123">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="15362-124">NuGet-Paket Microsoft.ML 1.3.1</span><span class="sxs-lookup"><span data-stu-id="15362-124">Microsoft.ML 1.3.1 Nuget package</span></span>
* <span data-ttu-id="15362-125">NuGet-Paket Microsoft.ML.ImageAnalytics 1.3.1</span><span class="sxs-lookup"><span data-stu-id="15362-125">Microsoft.ML.ImageAnalytics 1.3.1 Nuget package</span></span>
* <span data-ttu-id="15362-126">NuGet-Paket Microsoft.ML.TensorFlow 1.3.1</span><span class="sxs-lookup"><span data-stu-id="15362-126">Microsoft.ML.TensorFlow 1.3.1 Nuget package</span></span>

* [<span data-ttu-id="15362-127">Die ZIP-Datei mit dem Tutorialassetsverzeichnis </span><span class="sxs-lookup"><span data-stu-id="15362-127">The tutorial assets directory .ZIP file</span></span>](https://github.com/dotnet/samples/blob/master/machine-learning/tutorials/TransferLearningTF/image-classifier-assets.zip)

* [<span data-ttu-id="15362-128">Das Machine Learning-Modell von InceptionV1</span><span class="sxs-lookup"><span data-stu-id="15362-128">The InceptionV1 machine learning model</span></span>](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-right-machine-learning-task"></a><span data-ttu-id="15362-129">Auswählen der richtigen Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="15362-129">Select the right machine learning task</span></span>

### <a name="deep-learning"></a><span data-ttu-id="15362-130">Deep Learning</span><span class="sxs-lookup"><span data-stu-id="15362-130">Deep learning</span></span>

<span data-ttu-id="15362-131">[Deep Learning](https://en.wikipedia.org/wiki/Deep_learning) ist eine Teilmenge von Machine Learning, die Bereiche wie maschinelles Sehen und Spracherkennung revolutioniert.</span><span class="sxs-lookup"><span data-stu-id="15362-131">[Deep learning](https://en.wikipedia.org/wiki/Deep_learning) is a subset of Machine Learning, which is revolutionizing areas like Computer Vision and Speech Recognition.</span></span>

<span data-ttu-id="15362-132">Deep Learning-Modelle werden mithilfe großer Mengen [bezeichneter Daten](https://en.wikipedia.org/wiki/Labeled_data) und [neuronaler Netze](https://en.wikipedia.org/wiki/Artificial_neural_network) trainiert, die mehrere Lernebenen enthalten.</span><span class="sxs-lookup"><span data-stu-id="15362-132">Deep learning models are trained by using large sets of [labeled data](https://en.wikipedia.org/wiki/Labeled_data) and [neural networks](https://en.wikipedia.org/wiki/Artificial_neural_network) that contain multiple learning layers.</span></span> <span data-ttu-id="15362-133">Deep Learning:</span><span class="sxs-lookup"><span data-stu-id="15362-133">Deep learning:</span></span>

* <span data-ttu-id="15362-134">Bietet bei einigen Aufgaben eine bessere Leistung als maschinelles Sehen.</span><span class="sxs-lookup"><span data-stu-id="15362-134">Performs better on some tasks like Computer Vision.</span></span>
* <span data-ttu-id="15362-135">Erfordert große Mengen an Trainingsdaten.</span><span class="sxs-lookup"><span data-stu-id="15362-135">Requires huge amounts of training data.</span></span>

<span data-ttu-id="15362-136">Bildklassifizierung ist eine gängige Machine Learning-Aufgabe, mit der automatisch Bilder in mehrere Kategorien klassifiziert werden können, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="15362-136">Image Classification is a common Machine Learning task that allows us to automatically classify images into categories such as:</span></span>

* <span data-ttu-id="15362-137">Erkennen, ob ein Bild ein menschliches Gesicht enthält oder nicht.</span><span class="sxs-lookup"><span data-stu-id="15362-137">Detecting a human face in an image or not.</span></span>
* <span data-ttu-id="15362-138">Unterscheiden zwischen Katzen und Hunden.</span><span class="sxs-lookup"><span data-stu-id="15362-138">Detecting cats vs. dogs.</span></span>

 <span data-ttu-id="15362-139">Es lässt sich auch wie in den folgenden Bildern bestimmen, ob ein Bild ein Lebensmittel, ein Spielzeug oder ein Gerät zeigt:</span><span class="sxs-lookup"><span data-stu-id="15362-139">Or as in the following images, determining if an image is a(n)  food, toy, or appliance:</span></span>

<span data-ttu-id="15362-140">![Pizzabild](./media/image-classification/220px-Pepperoni_pizza.jpg)
![Teddybärbild](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![Toasterbild](./media/image-classification/193px-Broodrooster.jpg)</span><span class="sxs-lookup"><span data-stu-id="15362-140">![pizza image](./media/image-classification/220px-Pepperoni_pizza.jpg)
![teddy bear image](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![toaster image](./media/image-classification/193px-Broodrooster.jpg)</span></span>

>[!Note]
> <span data-ttu-id="15362-141">Die vorherigen Abbildungen stammen aus Wikimedia-Commons und unterliegen folgendem Urheberrecht:</span><span class="sxs-lookup"><span data-stu-id="15362-141">The preceding images belong to Wikimedia Commons and are attributed as follows:</span></span>
>
> * <span data-ttu-id="15362-142">„220px-Pepperoni_pizza.jpg“ Public Domain https://commons.wikimedia.org/w/index.php?curid=79505,</span><span class="sxs-lookup"><span data-stu-id="15362-142">"220px-Pepperoni_pizza.jpg" Public Domain, https://commons.wikimedia.org/w/index.php?curid=79505,</span></span>
> * <span data-ttu-id="15362-143">„119px-Nalle_-_a_small_brown_teddy_bear.jpg“ von [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) – selbst fotografiert, CC-BY-SA-2.0, https://commons.wikimedia.org/w/index.php?curid=48166.</span><span class="sxs-lookup"><span data-stu-id="15362-143">"119px-Nalle_-_a_small_brown_teddy_bear.jpg" By [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - Self-photographed, CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166.</span></span>
> * <span data-ttu-id="15362-144">„193px-Broodrooster.jpg“ von [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) – eigenes Werk, CC-BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403</span><span class="sxs-lookup"><span data-stu-id="15362-144">"193px-Broodrooster.jpg" By [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - Own work, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403</span></span>

<span data-ttu-id="15362-145">Das `Inception model` ist darauf trainiert, Bilder in tausend Kategorien zu klassifizieren, jedoch müssen Sie für dieses Tutorial Bilder in eine kleinere Kategoriegruppe und nur in diese Kategorien klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="15362-145">The `Inception model` is trained to classify images into a thousand categories, but for this tutorial, you need to classify images in a smaller category set, and only those categories.</span></span> <span data-ttu-id="15362-146">Geben Sie den `transfer`-Teil von `transfer learning` ein.</span><span class="sxs-lookup"><span data-stu-id="15362-146">Enter the `transfer` part of `transfer learning`.</span></span> <span data-ttu-id="15362-147">Sie können die Fähigkeit des `Inception model` zum Erkennen und Klassifizieren von Bildern auf die neuen begrenzten Kategorien Ihrer benutzerdefinierten Bildklassifizierung übertragen.</span><span class="sxs-lookup"><span data-stu-id="15362-147">You can transfer the `Inception model`'s ability to recognize and classify images to the new limited categories of your custom image classifier.</span></span>

* <span data-ttu-id="15362-148">Lebensmittel</span><span class="sxs-lookup"><span data-stu-id="15362-148">Food</span></span>
* <span data-ttu-id="15362-149">Spielzeug</span><span class="sxs-lookup"><span data-stu-id="15362-149">Toy</span></span>
* <span data-ttu-id="15362-150">Gerät</span><span class="sxs-lookup"><span data-stu-id="15362-150">Appliance</span></span>

<span data-ttu-id="15362-151">Dieses Tutorial verwendet das TensorFlow-Deep Learning-Modell [Inception](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), ein beliebtes Bilderkennungsmodell, das mit dem Dataset `ImageNet` trainiert wurde.</span><span class="sxs-lookup"><span data-stu-id="15362-151">This tutorial uses the TensorFlow [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) deep learning model, a popular image recognition model trained on the `ImageNet` dataset.</span></span> <span data-ttu-id="15362-152">Das TensorFlow-Modell klassifiziert ganze Bilder in tausend Klassen wie „Regenschirm“, „Trikot“ und „Geschirrspüler“.</span><span class="sxs-lookup"><span data-stu-id="15362-152">The TensorFlow model classifies entire images into a thousand classes, such as “Umbrella”, “Jersey”, and “Dishwasher”.</span></span>

<span data-ttu-id="15362-153">Da das `Inception model` bereits anhand von Tausenden anderer Bilder vortrainiert wurde, enthält es intern die zur Bildidentifizierung erforderlichen [Bildmerkmale](https://en.wikipedia.org/wiki/Feature_(computer_vision)).</span><span class="sxs-lookup"><span data-stu-id="15362-153">Because the `Inception model` has already been pre trained on thousands of different images, internally it contains the [image features](https://en.wikipedia.org/wiki/Feature_(computer_vision)) needed for image identification.</span></span> <span data-ttu-id="15362-154">Wir können diese internen Bildmerkmale im Modell verwenden, um ein neues Modell mit weitaus weniger Klassen zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="15362-154">We can make use of these internal image features in the model to train a new model with far fewer classes.</span></span>

<span data-ttu-id="15362-155">Wie im folgenden Diagramm dargestellt, fügen Sie einen Verweis auf die ML.NET-NuGet-Pakete in Ihrer .NET Core- oder .NET Framework-Anwendung hinzu.</span><span class="sxs-lookup"><span data-stu-id="15362-155">As shown in the following diagram, you add a reference to the ML.NET NuGet packages in your .NET Core or .NET Framework applications.</span></span> <span data-ttu-id="15362-156">Im Hintergrund beinhaltet und verweist ML.NET auf die native `TensorFlow`-Bibliothek, mit der Sie Code schreiben können, der eine vorhandene trainierte `TensorFlow`-Modelldatei lädt.</span><span class="sxs-lookup"><span data-stu-id="15362-156">Under the covers, ML.NET includes and references the native `TensorFlow` library that allows you to write code that loads an existing trained `TensorFlow` model file.</span></span>

![TensorFlow-Transformation – ML.NET Arch-Diagramm](./media/image-classification/tensorflow-mlnet.png)

### <a name="multiclass-classification"></a><span data-ttu-id="15362-158">Multiklassenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="15362-158">Multiclass classification</span></span>

<span data-ttu-id="15362-159">Nachdem wir das TensorFlow-Inception-Modell verwendet haben, um Merkmale zu extrahieren, die als Eingabe für einen klassischen Machine Learning-Algorithmus geeignet sind, fügen wir einen ML.NET-[Multiklassenklassifizierer](../resources/tasks.md#multiclass-classification) hinzu.</span><span class="sxs-lookup"><span data-stu-id="15362-159">After using the TensorFlow inception model to extract features suitable as input for a classical machine learning algorithm, we add an ML.NET [multi-class classifier](../resources/tasks.md#multiclass-classification).</span></span>

<span data-ttu-id="15362-160">Der in diesem Fall verwendete Trainingsmechanismus ist der [multinomiale logistische Regressionsalgorithmus](https://en.wikipedia.org/wiki/Multinomial_logistic_regression).</span><span class="sxs-lookup"><span data-stu-id="15362-160">The specific trainer used in this case is the [multinomial logistic regression algorithm](https://en.wikipedia.org/wiki/Multinomial_logistic_regression).</span></span>

<span data-ttu-id="15362-161">Der von diesem Trainingsmechanismus implementierte Algorithmus eignet sich gut für Probleme mit einer Vielzahl von Merkmalen, was bei einem Deep Learning-Modell der Fall ist, das mit Bilddaten arbeitet.</span><span class="sxs-lookup"><span data-stu-id="15362-161">The algorithm implemented by this trainer performs well on problems with a large number of features, which is the case for a deep learning model operating on image data.</span></span>

### <a name="data"></a><span data-ttu-id="15362-162">Daten</span><span class="sxs-lookup"><span data-stu-id="15362-162">Data</span></span>

<span data-ttu-id="15362-163">Es gibt zwei Datenquellen: die `.tsv`-Datei und die Bilddateien.</span><span class="sxs-lookup"><span data-stu-id="15362-163">There are two data sources: the `.tsv` file, and the image files.</span></span>  <span data-ttu-id="15362-164">Die `tags.tsv`-Datei enthält zwei Spalten: die erste ist als `ImagePath` definiert und die zweite das `Label` für das Bild.</span><span class="sxs-lookup"><span data-stu-id="15362-164">The `tags.tsv` file contains two columns: the first one is defined as `ImagePath` and the second one is the `Label` corresponding to the image.</span></span> <span data-ttu-id="15362-165">Die folgende Beispieldatei verfügt nicht über eine Kopfzeile und sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="15362-165">The following example file doesn't have a header row, and looks like this:</span></span>

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

<span data-ttu-id="15362-166">Die Trainings- und Testbilder befinden sich in dem Assetsordner, den Sie in einer ZIP-Datei herunterladen.</span><span class="sxs-lookup"><span data-stu-id="15362-166">The training and testing images are located in the assets folders that you'll download in a zip file.</span></span> <span data-ttu-id="15362-167">Diese Bilder gehören zu Wikimedia Commons.</span><span class="sxs-lookup"><span data-stu-id="15362-167">These images belong to Wikimedia Commons.</span></span>
> <span data-ttu-id="15362-168">*[Wikimedia-Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), das Repository für kostenlose Medien.*</span><span class="sxs-lookup"><span data-stu-id="15362-168">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), the free media repository.*</span></span> <span data-ttu-id="15362-169">Abgerufen am 17. Oktober 2018 um 10:48 Uhr aus: https://commons.wikimedia.org/wiki/Pizza https://commons.wikimedia.org/wiki/Toaster https://commons.wikimedia.org/wiki/Teddy_bear</span><span class="sxs-lookup"><span data-stu-id="15362-169">Retrieved 10:48, October 17, 2018 from: https://commons.wikimedia.org/wiki/Pizza https://commons.wikimedia.org/wiki/Toaster https://commons.wikimedia.org/wiki/Teddy_bear</span></span>

## <a name="setup"></a><span data-ttu-id="15362-170">Setup</span><span class="sxs-lookup"><span data-stu-id="15362-170">Setup</span></span>

### <a name="create-a-project"></a><span data-ttu-id="15362-171">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="15362-171">Create a project</span></span>

1. <span data-ttu-id="15362-172">Erstellen Sie eine **.NET Core-Konsolenanwendung** mit dem Namen „TransferLearningTF“.</span><span class="sxs-lookup"><span data-stu-id="15362-172">Create a **.NET Core Console Application** called "TransferLearningTF".</span></span>

1. <span data-ttu-id="15362-173">Installieren des **Microsoft.ML NuGet-Pakets**:</span><span class="sxs-lookup"><span data-stu-id="15362-173">Install the **Microsoft.ML NuGet Package**:</span></span>

    * <span data-ttu-id="15362-174">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="15362-174">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span>
    * <span data-ttu-id="15362-175">Wählen Sie „nuget.org“ als Paketquelle aus, wählen Sie die Registerkarte „Durchsuchen“ aus, und suchen Sie nach **Microsoft.ML**.</span><span class="sxs-lookup"><span data-stu-id="15362-175">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**.</span></span>
    * <span data-ttu-id="15362-176">Klicken Sie auf die Dropdownliste **Version**, und wählen Sie das Paket mit der Version **1.3.1** in der Liste aus. Klicken Sie dann auf die Schaltfläche **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="15362-176">Click on the **Version** drop-down, select the **1.3.1** package in the list, and select the **Install** button.</span></span>
    * <span data-ttu-id="15362-177">Klicken Sie im Dialogfeld **Vorschau der Änderungen** auf die Schaltfläche **OK**.</span><span class="sxs-lookup"><span data-stu-id="15362-177">Select the **OK** button on the **Preview Changes** dialog.</span></span>
    * <span data-ttu-id="15362-178">Wählen Sie die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz**, wenn Sie mit den Lizenzbedingungen für die aufgeführten Pakete einverstanden sind.</span><span class="sxs-lookup"><span data-stu-id="15362-178">Select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>
    * <span data-ttu-id="15362-179">Wiederholen Sie diese Schritte für **Microsoft.ML.ImageAnalytics v1.3.1** und **Microsoft.ML.TensorFlow v1.3.1**.</span><span class="sxs-lookup"><span data-stu-id="15362-179">Repeat these steps for **Microsoft.ML.ImageAnalytics v1.3.1** and **Microsoft.ML.TensorFlow v1.3.1**.</span></span>

### <a name="download-assets"></a><span data-ttu-id="15362-180">Herunterladen von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="15362-180">Download assets</span></span>

1. <span data-ttu-id="15362-181">Laden Sie [die ZIP-Datei des Projektassetverzeichnisses](https://github.com/dotnet/samples/blob/master/machine-learning/tutorials/TransferLearningTF/image-classifier-assets.zip) herunter, und entzippen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="15362-181">Download [The project assets directory zip file](https://github.com/dotnet/samples/blob/master/machine-learning/tutorials/TransferLearningTF/image-classifier-assets.zip), and unzip.</span></span>

1. <span data-ttu-id="15362-182">Kopieren Sie das `assets`-Verzeichnis in Ihr *TransferLearningTF*-Projektverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="15362-182">Copy the `assets` directory into your *TransferLearningTF* project directory.</span></span> <span data-ttu-id="15362-183">Dieses Verzeichnis und seine Unterverzeichnisse enthalten die für dieses Tutorial erforderlichen Daten und Unterstützungsdateien (mit Ausnahme des Inception-Modells, das Sie im nächsten Schritt herunterladen und hinzufügen).</span><span class="sxs-lookup"><span data-stu-id="15362-183">This directory and its subdirectories contain the data and support files (except for the Inception model, which you'll download and add in the next step) needed for this tutorial.</span></span>

1. <span data-ttu-id="15362-184">Laden Sie das [Inception-Modell](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) herunter, und entzippen Sie es.</span><span class="sxs-lookup"><span data-stu-id="15362-184">Download the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), and unzip.</span></span>

1. <span data-ttu-id="15362-185">Kopieren Sie den Inhalt des gerade entzippten `inception5h`-Verzeichnisses in Ihr *TransferLearningTF*-Projektverzeichnis `assets/inception`.</span><span class="sxs-lookup"><span data-stu-id="15362-185">Copy the contents of the `inception5h` directory just unzipped into your *TransferLearningTF* project `assets/inception` directory.</span></span> <span data-ttu-id="15362-186">Dieses Verzeichnis enthält das Modell und die zusätzlich für dieses Tutorial erforderlichen Unterstützungsdateien wie in der folgenden Abbildung gezeigt:</span><span class="sxs-lookup"><span data-stu-id="15362-186">This directory contains the model and additional support files needed for this tutorial, as shown in the following image:</span></span>

   ![Inhalt des Inception-Verzeichnisses](./media/image-classification/inception-files.png)

1. <span data-ttu-id="15362-188">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf alle Dateien im Assetverzeichnis und den Unterverzeichnissen, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="15362-188">In Solution Explorer, right-click each of the files in the asset directory and subdirectories and select **Properties**.</span></span> <span data-ttu-id="15362-189">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="15362-189">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="15362-190">Erstellen von Klassen und Definieren von Pfaden</span><span class="sxs-lookup"><span data-stu-id="15362-190">Create classes and define paths</span></span>

1. <span data-ttu-id="15362-191">Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="15362-191">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddUsings)]

1. <span data-ttu-id="15362-192">Fügen Sie den folgenden Code der Zeile direkt über der `Main`-Methode hinzu, um die Ressourcenpfade anzugeben:</span><span class="sxs-lookup"><span data-stu-id="15362-192">Add the following code to the line right above the `Main` method to specify the asset paths:</span></span>

    [!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareGlobalVariables)]

1. <span data-ttu-id="15362-193">Erstellen Sie anschließend Klassen für Ihre Eingabedaten und Vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="15362-193">Create classes for your input data, and predictions.</span></span>

    [!code-csharp[DeclareImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareImageData)]

    <span data-ttu-id="15362-194">`ImageData` ist die Eingabebilddaten-Klasse mit den folgenden <xref:System.String>-Feldern:</span><span class="sxs-lookup"><span data-stu-id="15362-194">`ImageData` is the input image data class and has the following <xref:System.String> fields:</span></span>

    * <span data-ttu-id="15362-195">`ImagePath` enthält den Bilddateinamen.</span><span class="sxs-lookup"><span data-stu-id="15362-195">`ImagePath` contains the image file name.</span></span>
    * <span data-ttu-id="15362-196">`Label` enthält einen Wert für die Bildbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="15362-196">`Label` contains a value for the image label.</span></span>

1. <span data-ttu-id="15362-197">Fügen Sie dem Projekt eine neue Klasse für `ImagePrediction` hinzu:</span><span class="sxs-lookup"><span data-stu-id="15362-197">Add a new class to your project for `ImagePrediction`:</span></span>

    [!code-csharp[DeclareImagePrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareImagePrediction)]

    <span data-ttu-id="15362-198">`ImagePrediction` ist die Bildvorhersageklasse und hat die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="15362-198">`ImagePrediction` is the image prediction class and has the following fields:</span></span>

    * <span data-ttu-id="15362-199">`Score` enthält den Zuverlässigkeitsprozentsatz für eine bestimmte Bildklassifizierung.</span><span class="sxs-lookup"><span data-stu-id="15362-199">`Score` contains the confidence percentage for a given image classification.</span></span>
    * <span data-ttu-id="15362-200">`PredictedLabelValue` enthält einen Wert für die vorhergesagte Bildklassifizierungsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="15362-200">`PredictedLabelValue` contains a value for the predicted image classification label.</span></span>

    <span data-ttu-id="15362-201">Die `ImagePrediction`-Klasse wird für die Vorhersage verwendet, nachdem das Modell trainiert wurde.</span><span class="sxs-lookup"><span data-stu-id="15362-201">`ImagePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="15362-202">Sie besitzt einen `string` (`ImagePath`) für den Bildpfad.</span><span class="sxs-lookup"><span data-stu-id="15362-202">It has a `string` (`ImagePath`) for the image path.</span></span> <span data-ttu-id="15362-203">Mit `Label` wird das Modell wiederverwendet und trainiert.</span><span class="sxs-lookup"><span data-stu-id="15362-203">The `Label` is used to reuse and train the model.</span></span> <span data-ttu-id="15362-204">Das `PredictedLabelValue` wird während der Vorhersage und Evaluierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="15362-204">The `PredictedLabelValue` is used during prediction and evaluation.</span></span> <span data-ttu-id="15362-205">Für die Evaluierung werden eine Eingabe mit Trainingsdaten, die vorhergesagten Werte und das Modell verwendet.</span><span class="sxs-lookup"><span data-stu-id="15362-205">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="15362-206">Initialisieren von Variablen in Main</span><span class="sxs-lookup"><span data-stu-id="15362-206">Initialize variables in Main</span></span>

1. <span data-ttu-id="15362-207">Initialisieren Sie die `mlContext`-Variable mit einer neuen Instanz von `MLContext`.</span><span class="sxs-lookup"><span data-stu-id="15362-207">Initialize the `mlContext` variable with a new instance of `MLContext`.</span></span>  <span data-ttu-id="15362-208">Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` mit dem folgenden Code in der `Main`-Methode:</span><span class="sxs-lookup"><span data-stu-id="15362-208">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

    [!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CreateMLContext)]

    <span data-ttu-id="15362-209">Die [MLContext-Klasse](xref:Microsoft.ML.MLContext) ist der Startpunkt für alle ML.NET-Vorgänge. Durch das Initialisieren von `mlContext` wird eine neue ML.NET-Umgebung erstellt, die für mehrere Objekte des Modellerstellungsworkflows verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="15362-209">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="15362-210">Die Klasse ähnelt dem Konzept von `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="15362-210">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="create-a-struct-for-inception-model-parameters"></a><span data-ttu-id="15362-211">Erstellen einer Struktur für Inception-Modellparameter</span><span class="sxs-lookup"><span data-stu-id="15362-211">Create a struct for Inception model parameters</span></span>

1. <span data-ttu-id="15362-212">Das Inception-Modell verfügt über mehrere Parameter, die Sie übergeben müssen.</span><span class="sxs-lookup"><span data-stu-id="15362-212">The Inception model has several parameters you need to pass in.</span></span> <span data-ttu-id="15362-213">Erstellen Sie unmittelbar nach der `Main()`-Methode eine Struktur, um Anzeigenamen mit dem folgenden Code die Parameterwerte zuzuordnen:</span><span class="sxs-lookup"><span data-stu-id="15362-213">Create a struct to map the parameter values to friendly names with the following code, just after the `Main()` method:</span></span>

    [!code-csharp[InceptionSettings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a><span data-ttu-id="15362-214">Erstellen einer Anzeigehilfsprogramm-Methode</span><span class="sxs-lookup"><span data-stu-id="15362-214">Create a display utility method</span></span>

<span data-ttu-id="15362-215">Da Sie die Bilddaten und die zugehörigen Vorhersagen mehr als einmal anzeigen werden, erstellen Sie eine Anzeigehilfsmethode, um die Anzeige der Bild- und Vorhersageergebnisse zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="15362-215">Since you'll display the image data and the related predictions more than once, create a display utility method to handle displaying the image and prediction results.</span></span>

1. <span data-ttu-id="15362-216">Erstellen Sie die `DisplayResults()`-Methode mit dem folgenden Code direkt nach der `InceptionSettings`-Struktur:</span><span class="sxs-lookup"><span data-stu-id="15362-216">Create the `DisplayResults()` method, just after the `InceptionSettings` struct, using the following code:</span></span>

    ```csharp
    private static void DisplayResults(IEnumerable<ImagePrediction> imagePredictionData)
    {

    }
    ```

1. <span data-ttu-id="15362-217">Geben Sie den Text der `DisplayResults`-Methode ein:</span><span class="sxs-lookup"><span data-stu-id="15362-217">Fill in the body of the `DisplayResults` method:</span></span>

    [!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPredictions)]

### <a name="create-a-tsv-file-utility-method"></a><span data-ttu-id="15362-218">Erstellen einer Hilfsprogrammmethode für die TSV-Datei</span><span class="sxs-lookup"><span data-stu-id="15362-218">Create a .tsv file utility method</span></span>

1. <span data-ttu-id="15362-219">Erstellen Sie die `ReadFromTsv()`-Methode mit dem folgenden Code direkt nach der `DisplayResults()`-Methode:</span><span class="sxs-lookup"><span data-stu-id="15362-219">Create the `ReadFromTsv()` method, just after the `DisplayResults()` method, using the following code:</span></span>

    ```csharp
    public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
    {

    }
    ```

1. <span data-ttu-id="15362-220">Geben Sie den Text der `ReadFromTsv`-Methode ein:</span><span class="sxs-lookup"><span data-stu-id="15362-220">Fill in the body of the `ReadFromTsv` method:</span></span>

    [!code-csharp[ReadFromTsv](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReadFromTsv)]

    <span data-ttu-id="15362-221">Der Code analysiert die `tags.tsv`-Datei, um den Dateipfad für die `ImagePath`-Eigenschaft dem Namen der Bilddatei hinzuzufügen und ihn und das `Label` in ein `ImageData`-Objekt zu laden.</span><span class="sxs-lookup"><span data-stu-id="15362-221">The code parses through the `tags.tsv` file to add the file path to the image file name for the `ImagePath` property and load it and the `Label` into an `ImageData` object.</span></span>

### <a name="create-a-method-to-make-a-prediction"></a><span data-ttu-id="15362-222">Erstellen einer Methode zum Treffen einer Vorhersage</span><span class="sxs-lookup"><span data-stu-id="15362-222">Create a method to make a prediction</span></span>

1. <span data-ttu-id="15362-223">Erstellen Sie die `ClassifySingleImage()`-Methode mit dem folgenden Code direkt vor der `DisplayResults()`-Methode:</span><span class="sxs-lookup"><span data-stu-id="15362-223">Create the `ClassifySingleImage()` method, just before the `DisplayResults()` method, using the following code:</span></span>

    ```csharp
    public static void ClassifySingleImage(MLContext mlContext, ITransformer model)
    {

    }
    ```

1. <span data-ttu-id="15362-224">Erstellen Sie ein `ImageData`-Objekt, das den vollqualifizierten Pfad und Bilddateinamen für den einzelnen `ImagePath` enthält.</span><span class="sxs-lookup"><span data-stu-id="15362-224">Create an `ImageData` object that contains the fully qualified path and image file name for the single `ImagePath`.</span></span> <span data-ttu-id="15362-225">Fügen Sie der `ClassifySingleImage()`-Methode folgenden Code als nächste Zeilen hinzu:</span><span class="sxs-lookup"><span data-stu-id="15362-225">Add the following code as the next  lines in the `ClassifySingleImage()` method:</span></span>

    [!code-csharp[LoadImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadImageData)]

1. <span data-ttu-id="15362-226">Treffen Sie eine einzelne Vorhersage, indem Sie den folgenden Code als nächste Zeile in der `ClassifySingleImage`-Methode hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="15362-226">Make a single prediction, by adding the following code as the next line in the `ClassifySingleImage` method:</span></span>

    [!code-csharp[PredictSingle](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#PredictSingle)]

    <span data-ttu-id="15362-227">Um die Vorhersage zu erhalten, verwenden Sie die [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A)-Methode.</span><span class="sxs-lookup"><span data-stu-id="15362-227">To get the prediction, use the [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) method.</span></span> <span data-ttu-id="15362-228">Die [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) ist eine Hilfs-API, mit der Sie eine Vorhersage für eine einzelne Instanz der Daten treffen können.</span><span class="sxs-lookup"><span data-stu-id="15362-228">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="15362-229">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) ist nicht threadsicher.</span><span class="sxs-lookup"><span data-stu-id="15362-229">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="15362-230">Die Verwendung in Singlethread-oder Prototypumgebungen ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="15362-230">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="15362-231">Zur Verbesserung der Leistung und Threadsicherheit in Produktionsumgebungen verwenden Sie den `PredictionEnginePool`-Dienst, der einen [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) aus [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)-Objekten für die Verwendung in Ihrer gesamten Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="15362-231">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="15362-232">Informationen zur [Verwendung von `PredictionEnginePool` in einer ASP.NET Core-Web-API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application) finden Sie in dieser Anleitung.</span><span class="sxs-lookup"><span data-stu-id="15362-232">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

    > [!NOTE]
    > <span data-ttu-id="15362-233">Die `PredictionEnginePool`-Diensterweiterung ist derzeit als Vorschauversion verfügbar.</span><span class="sxs-lookup"><span data-stu-id="15362-233">`PredictionEnginePool` service extension is currently in preview.</span></span>

1. <span data-ttu-id="15362-234">Zeigen Sie das Vorhersageergebnis als nächste Codezeile in der `ClassifySingleImage()`-Methode an:</span><span class="sxs-lookup"><span data-stu-id="15362-234">Display the prediction result as the next line of code in the `ClassifySingleImage()` method:</span></span>

   [!code-csharp[DisplayPrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPrediction)]

## <a name="construct-the-mlnet-model-pipeline"></a><span data-ttu-id="15362-235">Erstellen der ML.NET-Modellpipeline</span><span class="sxs-lookup"><span data-stu-id="15362-235">Construct the ML.NET model pipeline</span></span>

<span data-ttu-id="15362-236">Eine ML.NET-Modellpipeline ist eine Kette von Kalkulatoren.</span><span class="sxs-lookup"><span data-stu-id="15362-236">An ML.NET model pipeline is a chain of estimators.</span></span> <span data-ttu-id="15362-237">Beachten Sie, dass während der Pipelineerstellung keine Ausführung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="15362-237">Note that no execution happens during pipeline construction.</span></span> <span data-ttu-id="15362-238">Die Kalkulatorobjekte werden erstellt, aber nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="15362-238">The estimator objects are created but not executed.</span></span>

1. <span data-ttu-id="15362-239">Hinzufügen einer Methode zum Generieren des Modells</span><span class="sxs-lookup"><span data-stu-id="15362-239">Add a method to generate the model</span></span>

    <span data-ttu-id="15362-240">Diese Methode ist das Herzstück des Tutorials.</span><span class="sxs-lookup"><span data-stu-id="15362-240">This method is the heart of the tutorial.</span></span> <span data-ttu-id="15362-241">Sie erstellt eine Pipeline für das Modell und trainiert die Pipeline, um das ML.NET-Modell zu generieren.</span><span class="sxs-lookup"><span data-stu-id="15362-241">It creates a pipeline for the model, and trains the pipeline to produce the ML.NET model.</span></span> <span data-ttu-id="15362-242">Außerdem wertet sie das Modell anhand einiger zuvor unbekannter Testdaten aus.</span><span class="sxs-lookup"><span data-stu-id="15362-242">It also evaluates the model against some previously unseen test data.</span></span>

    <span data-ttu-id="15362-243">Erstellen Sie die `GenerateModel()`-Methode mithilfe des folgenden Codes unmittelbar nach der `InceptionSettings`-Struktur und direkt vor der `DisplayResults()`-Methode:</span><span class="sxs-lookup"><span data-stu-id="15362-243">Create the `GenerateModel()` method, just after the `InceptionSettings` struct and just before the `DisplayResults()` method, using the following code:</span></span>

    ```csharp
    public static ITransformer GenerateModel(MLContext mlContext)
    {

    }
    ```

1. <span data-ttu-id="15362-244">Fügen Sie die Kalkulatoren zum Laden, Ändern der Größe und Extrahieren der Pixel aus den Bilddaten hinzu:</span><span class="sxs-lookup"><span data-stu-id="15362-244">Add the estimators to load, resize and extract the pixels from the image data:</span></span>

    [!code-csharp[ImageTransforms](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ImageTransforms)]

    <span data-ttu-id="15362-245">Die Bilddaten müssen in das Format verarbeitet werden, das vom TensorFlow-Modell erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="15362-245">The image data needs to be processed into the format that the TensorFlow model expects.</span></span> <span data-ttu-id="15362-246">In diesem Fall werden die Bilder in den Arbeitsspeicher geladen, die Größe in eine konsistente Größe geändert, und die Pixel werden in einen numerischen Vektor extrahiert.</span><span class="sxs-lookup"><span data-stu-id="15362-246">In this case, the images are loaded into memory, resized to a consistent size, and the pixels are extracted into a numeric vector.</span></span>

1. <span data-ttu-id="15362-247">Fügen Sie den Kalkulator zum Laden des TensorFlow-Modells hinzu, und versehen Sie es mit einem Score:</span><span class="sxs-lookup"><span data-stu-id="15362-247">Add the estimator to load the TensorFlow model, and score it:</span></span>

    [!code-csharp[ScoreTensorFlowModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ScoreTensorFlowModel)]

    <span data-ttu-id="15362-248">Diese Phase in der Pipeline lädt das TensorFlow-Modell in den Arbeitsspeicher und verarbeitet dann den Vektor der Pixelwerte über das TensorFlow-Modellnetzwerk.</span><span class="sxs-lookup"><span data-stu-id="15362-248">This stage in the pipeline loads the TensorFlow model into memory, then processes the vector of pixel values through the TensorFlow model network.</span></span> <span data-ttu-id="15362-249">Das Anwenden von Eingaben auf ein Deep Learning-Modell und das Generieren einer Ausgabe mithilfe des Modells wird als **Scoring** bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="15362-249">Applying inputs to a deep learning model, and generating an output using the model, is referred to as **Scoring**.</span></span> <span data-ttu-id="15362-250">Wenn Sie das Modell in seiner Gesamtheit verwenden, führt das Scoring zu einem Rückschluss oder einer Vorhersage.</span><span class="sxs-lookup"><span data-stu-id="15362-250">When using the model in its entirety, scoring makes an inference, or prediction.</span></span>

    <span data-ttu-id="15362-251">In diesem Fall verwenden Sie das gesamte TensorFlow-Modell mit Ausnahme der letzten Schicht, bei der es sich um die Schicht handelt, die den Rückschluss ausführt.</span><span class="sxs-lookup"><span data-stu-id="15362-251">In this case, you use all of the TensorFlow model except the last layer, which is the layer that makes the inference.</span></span> <span data-ttu-id="15362-252">Die Ausgabe der vorletzten Schicht wird als `softmax_2_preactivation` bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="15362-252">The output of the penultimate layer is labeled `softmax_2_preactivation`.</span></span> <span data-ttu-id="15362-253">Die Ausgabe dieser Schicht ist praktisch ein Vektor von Merkmalen, die die ursprünglichen Eingabebilder charakterisieren.</span><span class="sxs-lookup"><span data-stu-id="15362-253">The output of this layer is effectively a vector of features that characterize the original input images.</span></span>

    <span data-ttu-id="15362-254">Dieser vom TensorFlow-Modell generierte Merkmalsvektor wird als Eingabe in einen ML.NET-Trainingsalgorithmus verwendet.</span><span class="sxs-lookup"><span data-stu-id="15362-254">This feature vector generated by the TensorFlow model will be used as input to an ML.NET training algorithm.</span></span>

1. <span data-ttu-id="15362-255">Fügen Sie den Kalkulator hinzu, um die Zeichenfolgenbezeichnungen in den Trainingsdaten ganzzahligen Schlüsselwerten zuzuordnen:</span><span class="sxs-lookup"><span data-stu-id="15362-255">Add the estimator to map the string labels in the training data to integer key values:</span></span>

    [!code-csharp[MapValueToKey](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey)]

    <span data-ttu-id="15362-256">Der ML.NET-Trainingsmechanismus, der als nächstes angefügt wird, erfordert, dass seine Bezeichnungen im `key`-Format und nicht in beliebigen Zeichenfolgen vorliegen.</span><span class="sxs-lookup"><span data-stu-id="15362-256">The ML.NET trainer that is appended next requires its labels to be in `key` format rather than arbitrary strings.</span></span> <span data-ttu-id="15362-257">Ein Schlüssel ist eine Zahl, die eine 1:1-Zuordnung zu einem Zeichenfolgenwert aufweist.</span><span class="sxs-lookup"><span data-stu-id="15362-257">A key is a number that has a one to one mapping to a string value.</span></span>

1. <span data-ttu-id="15362-258">Fügen Sie den ML.NET-Trainingsalgorithmus hinzu:</span><span class="sxs-lookup"><span data-stu-id="15362-258">Add the ML.NET training algorithm:</span></span>

    [!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddTrainer)]

1. <span data-ttu-id="15362-259">Fügen Sie den Kalkulator hinzu, um den vorhergesagten Schlüsselwert erneut einer Zeichenfolge zuzuordnen:</span><span class="sxs-lookup"><span data-stu-id="15362-259">Add the estimator to map the predicted key value back into a string:</span></span>

    [!code-csharp[MapKeyToValue](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapKeyToValue)]

## <a name="train-the-model"></a><span data-ttu-id="15362-260">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="15362-260">Train the model</span></span>

1. <span data-ttu-id="15362-261">Laden Sie die Trainingsdaten mithilfe des [LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile(Microsoft.ML.DataOperationsCatalog,System.String,Microsoft.ML.Data.TextLoader.Options))-Wrappers.</span><span class="sxs-lookup"><span data-stu-id="15362-261">Load the training data using the [LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile(Microsoft.ML.DataOperationsCatalog,System.String,Microsoft.ML.Data.TextLoader.Options)) wrapper.</span></span> <span data-ttu-id="15362-262">Fügen Sie der `GenerateModel()`-Methode folgenden Code als nächste Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="15362-262">Add the following code as the next line in the `GenerateModel()` method:</span></span>

    [!code-csharp[LoadData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadData "Load the data")]

    <span data-ttu-id="15362-263">Daten werden in ML.NET als [IDataView-Klasse](xref:Microsoft.ML.IDataView) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="15362-263">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="15362-264">Mit `IDataView` können Tabellendaten (Zahlen und Text) flexibel und effizient beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="15362-264">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="15362-265">Daten können aus einer Textdatei oder in Echtzeit (z. B. aus einer SQL-Datenbank oder aus Protokolldateien) in ein `IDataView`-Objekt geladen werden.</span><span class="sxs-lookup"><span data-stu-id="15362-265">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

1. <span data-ttu-id="15362-266">Trainieren Sie das Modell mit den zuvor geladenen Daten:</span><span class="sxs-lookup"><span data-stu-id="15362-266">Train the model with the data loaded above:</span></span>

    [!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TrainModel)]

    <span data-ttu-id="15362-267">Die `Fit()`-Methode trainiert Ihr Modell, indem das Trainingsdataset auf die Pipeline angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="15362-267">The `Fit()` method trains your model by applying the training dataset to the pipeline.</span></span>

## <a name="evaluate-the-accuracy-of-the-model"></a><span data-ttu-id="15362-268">Auswerten der Genauigkeit des Modells</span><span class="sxs-lookup"><span data-stu-id="15362-268">Evaluate the accuracy of the model</span></span>

1. <span data-ttu-id="15362-269">Laden und transformieren Sie die Testdaten, indem Sie der nächsten Zeile der `GenerateModel`-Methode den folgenden Code hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="15362-269">Load and transform the test data, by adding the following code to the next line of the `GenerateModel` method:</span></span>

    [!code-csharp[LoadAndTransformTestData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadAndTransformTestData "Load and transform test data")]

    <span data-ttu-id="15362-270">Es gibt einige Beispielbilder, die Sie zum Auswerten des Modells verwenden können.</span><span class="sxs-lookup"><span data-stu-id="15362-270">There are a few sample images that you can use to evaluate the model.</span></span> <span data-ttu-id="15362-271">Wie die Trainingsdaten müssen diese in eine `IDataView` geladen werden, damit Sie vom Modell transformiert werden können.</span><span class="sxs-lookup"><span data-stu-id="15362-271">Like the training data, these need to be loaded into an `IDataView`, so that they can be transformed by the model.</span></span>

1. <span data-ttu-id="15362-272">Fügen Sie der `GenerateModel()`-Methode den folgenden Code hinzu, um das Modell auszuwerten:</span><span class="sxs-lookup"><span data-stu-id="15362-272">Add the following code to the `GenerateModel()` method to evaluate the model:</span></span>

    [!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Evaluate)]

    <span data-ttu-id="15362-273">Nachdem Sie die Vorhersage festgelegt haben, führt die [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A)-Methode Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="15362-273">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) method:</span></span>

    * <span data-ttu-id="15362-274">Bewerten des Modells (Vergleichen der vorhergesagten Werte mit dem Testdataset `labels`).</span><span class="sxs-lookup"><span data-stu-id="15362-274">Assesses the model (compares the predicted values with the test dataset `labels`).</span></span>
    * <span data-ttu-id="15362-275">Rückgabe der Modellleistungsmetriken.</span><span class="sxs-lookup"><span data-stu-id="15362-275">Returns the model performance metrics.</span></span>

1. <span data-ttu-id="15362-276">Anzeigen der Modellgenauigkeitsmetriken</span><span class="sxs-lookup"><span data-stu-id="15362-276">Display the model accuracy metrics</span></span>

    <span data-ttu-id="15362-277">Verwenden Sie den folgenden Code, um die Metriken anzuzeigen, die Ergebnisse freizugeben und dann mit ihnen zu arbeiten:</span><span class="sxs-lookup"><span data-stu-id="15362-277">Use the following code to display the metrics, share the results, and then act on them:</span></span>

    [!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayMetrics)]

    <span data-ttu-id="15362-278">Für die Bildklassifizierung werden die folgenden Metriken ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="15362-278">The following metrics are evaluated for image classification:</span></span>

    * <span data-ttu-id="15362-279">`Log-loss` – siehe [Protokollverlust](../resources/glossary.md#log-loss).</span><span class="sxs-lookup"><span data-stu-id="15362-279">`Log-loss` - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="15362-280">Der Protokollverlust sollte so nahe wie möglich bei 0 liegen.</span><span class="sxs-lookup"><span data-stu-id="15362-280">You want Log-loss to be as close to zero as possible.</span></span>
    * <span data-ttu-id="15362-281">`Per class Log-loss`.</span><span class="sxs-lookup"><span data-stu-id="15362-281">`Per class Log-loss`.</span></span> <span data-ttu-id="15362-282">Der Protokollverlust pro Klasse sollte so nahe wie möglich bei 0 liegen.</span><span class="sxs-lookup"><span data-stu-id="15362-282">You want per class Log-loss to be as close to zero as possible.</span></span>

1. <span data-ttu-id="15362-283">Fügen Sie den folgenden Code hinzu, um das trainierte Modell als nächste Zeile zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="15362-283">Add the following code to return the trained model as the next line:</span></span>

    [!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReturnModel)]

## <a name="run-the-application"></a><span data-ttu-id="15362-284">Führen Sie die Anwendung aus!</span><span class="sxs-lookup"><span data-stu-id="15362-284">Run the application!</span></span>

1. <span data-ttu-id="15362-285">Fügen Sie in der `Main`-Methode nach der Erstellung der MLContext-Klasse den Aufruf von `GenerateModel` hinzu:</span><span class="sxs-lookup"><span data-stu-id="15362-285">Add the call to `GenerateModel` in the `Main` method after the creation of the MLContext class:</span></span>

    [!code-csharp[CallGenerateModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallGenerateModel)]

1. <span data-ttu-id="15362-286">Fügen Sie den Aufruf der `ClassifySingleImage()`-Methode der `Main`-Methode als nächste Codezeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="15362-286">Add the call to the `ClassifySingleImage()` method as the next line of code in the `Main` method:</span></span>

    [!code-csharp[CallClassifySingleImage](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifySingleImage)]

1. <span data-ttu-id="15362-287">Führen Sie die Konsolen-App aus (STRG+F5).</span><span class="sxs-lookup"><span data-stu-id="15362-287">Run your console app (Ctrl + F5).</span></span> <span data-ttu-id="15362-288">Ihre Ergebnisse sollten der folgenden Ausgabe ähneln.</span><span class="sxs-lookup"><span data-stu-id="15362-288">Your results should be similar to the following output.</span></span>  <span data-ttu-id="15362-289">Möglicherweise werden Warnungen oder Verarbeitungsnachrichten angezeigt. Diese wurden jedoch aus Gründen der Übersichtlichkeit aus den folgenden Ergebnissen entfernt.</span><span class="sxs-lookup"><span data-stu-id="15362-289">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

    ```console
    =============== Training classification model ===============
    Image: broccoli2.jpg predicted as: food with score: 0.8955513
    Image: pizza3.jpg predicted as: food with score: 0.9667718
    Image: teddy6.jpg predicted as: toy with score: 0.9797683
    =============== Classification metrics ===============
    LogLoss is: 0.0653774699265059
    PerClassLogLoss is: 0.110315812569315 , 0.0204391272836966 , 0
    =============== Making single image classification ===============
    Image: toaster3.jpg predicted as: appliance with score: 0.9646884
    ```

<span data-ttu-id="15362-290">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="15362-290">Congratulations!</span></span> <span data-ttu-id="15362-291">Sie haben durch Anwenden von Übertragungslernen auf ein `TensorFlow`-Modell in ML.NET erfolgreich ein Machine Learning-Modell für die Bildklassifizierung erstellt.</span><span class="sxs-lookup"><span data-stu-id="15362-291">You've now successfully built a machine learning model for image classification by applying transfer learning to a `TensorFlow` model in ML.NET.</span></span>

<span data-ttu-id="15362-292">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).</span><span class="sxs-lookup"><span data-stu-id="15362-292">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span>

<span data-ttu-id="15362-293">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="15362-293">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="15362-294">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="15362-294">Understand the problem</span></span>
> * <span data-ttu-id="15362-295">Integrieren des vortrainierten TensorFlow-Modells in die ML.NET-Pipeline</span><span class="sxs-lookup"><span data-stu-id="15362-295">Incorporate the pre-trained TensorFlow model into the ML.NET pipeline</span></span>
> * <span data-ttu-id="15362-296">Trainieren und Auswerten des ML.NET-Modells</span><span class="sxs-lookup"><span data-stu-id="15362-296">Train and evaluate the ML.NET model</span></span>
> * <span data-ttu-id="15362-297">Klassifizieren eines Testbilds</span><span class="sxs-lookup"><span data-stu-id="15362-297">Classify a test image</span></span>

<span data-ttu-id="15362-298">Sehen Sie sich im GitHub-Repository für Machine Learning-Beispiele nach einem Beispiel für erweiterte Bildklassifizierung um, damit Sie es untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="15362-298">Check out the Machine Learning samples GitHub repository to explore an expanded image classification sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="15362-299">dotnet/machinelearning-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="15362-299">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/)
