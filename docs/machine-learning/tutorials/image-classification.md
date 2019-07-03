---
title: 'Tutorial: Erneutes Trainieren der TensorFlow-Bildklassifizierung: Übertragungslernen'
description: Erfahren Sie, wie ein TensorFlow-Modell für die Bildklassifizierung mit Übertragungslernen und ML.NET neu trainieren. Das ursprüngliche Modell war so trainiert, dass es einzelne Bilder klassifizieren konnte. Nach dem erneuten Training ordnet das neue Modell die Bilder in allgemeine Kategorien ein.
ms.date: 06/12/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: 62a926795ce34a8c1639f1d42ebbb34b53dc67ad
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2019
ms.locfileid: "67401738"
---
# <a name="tutorial-retrain-a-tensorflow-image-classifier-with-transfer-learning-and-mlnet"></a><span data-ttu-id="99706-105">Tutorial: Erneutes Trainieren einer TensorFlow-Bildklassifizierung mit Übertragungslernen und ML.NET</span><span class="sxs-lookup"><span data-stu-id="99706-105">Tutorial: Retrain a TensorFlow image classifier with transfer learning and ML.NET</span></span>

<span data-ttu-id="99706-106">Erfahren Sie, wie ein TensorFlow-Modell für die Bildklassifizierung mit Übertragungslernen und ML.NET neu trainieren.</span><span class="sxs-lookup"><span data-stu-id="99706-106">Learn how to retrain an image classification TensorFlow model with transfer learning and ML.NET.</span></span> <span data-ttu-id="99706-107">Das ursprüngliche Modell war so trainiert, dass es einzelne Bilder klassifizieren konnte.</span><span class="sxs-lookup"><span data-stu-id="99706-107">The original model was trained to classify individual images.</span></span> <span data-ttu-id="99706-108">Nach dem erneuten Training ordnet das neue Modell die Bilder in allgemeine Kategorien ein.</span><span class="sxs-lookup"><span data-stu-id="99706-108">After retraining, the new model organizes the images into broad categories.</span></span> 

<span data-ttu-id="99706-109">Das von Grund auf neue Trainieren eines Modells zur [Bildklassifizierung](https://en.wikipedia.org/wiki/Outline_of_object_recognition) erfordert das Einstellen von Millionen von Parametern, zahlreiche bezeichnete Trainingsdaten und eine große Menge an Computeressourcen (Hunderte von GPU-Stunden).</span><span class="sxs-lookup"><span data-stu-id="99706-109">Training an [Image Classification](https://en.wikipedia.org/wiki/Outline_of_object_recognition) model from scratch requires setting millions of parameters, a ton of labeled training data and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="99706-110">Transfer Learning ist zwar nicht so effektiv wie das von Grund auf neue Trainieren eines benutzerdefinierten Modells, doch damit können Sie diesen Prozess durch die Arbeit mit Tausenden von Bildern im Vergleich zur Arbeit mit Millionen bezeichneter Bilder abkürzen und relativ schnell ein benutzerdefiniertes Modell erstellen (innerhalb einer Stunde auf einem Computer ohne eine GPU).</span><span class="sxs-lookup"><span data-stu-id="99706-110">While not as effective as training a custom model from scratch, transfer learning allows you to shortcut this process by working with thousands of images vs. millions of labeled images and build a customized model fairly quickly (within an hour on a machine without a GPU).</span></span>

<span data-ttu-id="99706-111">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="99706-111">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="99706-112">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="99706-112">Understand the problem</span></span>
> * <span data-ttu-id="99706-113">Wiederverwenden und Optimieren des vortrainierten Modells</span><span class="sxs-lookup"><span data-stu-id="99706-113">Reuse and tune the pre-trained model</span></span>
> * <span data-ttu-id="99706-114">Klassifizieren von Bildern</span><span class="sxs-lookup"><span data-stu-id="99706-114">Classify Images</span></span>

## <a name="what-is-transfer-learning"></a><span data-ttu-id="99706-115">Was ist Übertragungslernen?</span><span class="sxs-lookup"><span data-stu-id="99706-115">What is transfer learning?</span></span>

<span data-ttu-id="99706-116">Was wäre, wenn Sie ein zum Lösen eines ähnlichen Problems bereits vortrainiertes Modell wiederverwenden und entweder alle oder einige Ebenen dieses Modells neu trainieren könnten, damit es Ihr Problem löst?</span><span class="sxs-lookup"><span data-stu-id="99706-116">What if you could reuse a model that's already been pre trained to solve a similar problem and retrain either all or some of the layers of that model to make it solve your problem?</span></span> <span data-ttu-id="99706-117">Dieses Verfahren der erneuten Nutzung eines Teils eines bereits trainierten Modells zum Erstellen eines neuen Modells wird als [Transfer Learning](https://en.wikipedia.org/wiki/Transfer_learning) (Übertragungslernen) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="99706-117">This technique of reusing part of an already trained model to build a new model is known as [transfer learning](https://en.wikipedia.org/wiki/Transfer_learning).</span></span>

## <a name="image-classification-sample-overview"></a><span data-ttu-id="99706-118">Übersicht über das Bildklassifizierungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="99706-118">Image classification sample overview</span></span>

<span data-ttu-id="99706-119">Das Beispiel ist eine Konsolenanwendung, die ML.NET verwendet, um eine Bildklassifizierung mittels Wiederverwendung eines vortrainierten Modells zum Klassifizieren von Bildern mit einer kleinen Menge von Trainingsdaten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="99706-119">The sample is a console application that uses ML.NET to build an image classifier by reusing a pre-trained model to classify images with a small amount of training data.</span></span>

<span data-ttu-id="99706-120">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).</span><span class="sxs-lookup"><span data-stu-id="99706-120">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="99706-121">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="99706-121">Prerequisites</span></span>

* <span data-ttu-id="99706-122">[Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="99706-122">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="99706-123">Microsoft.ML 1.0.0 NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="99706-123">Microsoft.ML 1.0.0 Nuget package</span></span>
* <span data-ttu-id="99706-124">Microsoft.ML.ImageAnalytics 1.0.0 NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="99706-124">Microsoft.ML.ImageAnalytics 1.0.0 Nuget package</span></span>
* <span data-ttu-id="99706-125">Microsoft.ML.TensorFlow 0.12.0 NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="99706-125">Microsoft.ML.TensorFlow 0.12.0 Nuget package</span></span>

* [<span data-ttu-id="99706-126">Die ZIP-Datei mit dem Tutorialassetsverzeichnis </span><span class="sxs-lookup"><span data-stu-id="99706-126">The tutorial assets directory .ZIP file</span></span>](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip)

* [<span data-ttu-id="99706-127">Die Machine Learning-Modelle von InceptionV3</span><span class="sxs-lookup"><span data-stu-id="99706-127">The InceptionV3 machine learning model</span></span>](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="99706-128">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="99706-128">Select the appropriate machine learning task</span></span>

<span data-ttu-id="99706-129">[Deep Learning](https://en.wikipedia.org/wiki/Deep_learning) ist eine Teilmenge von Machine Learning, die Bereiche wie maschinelles Sehen und Spracherkennung revolutioniert.</span><span class="sxs-lookup"><span data-stu-id="99706-129">[Deep learning](https://en.wikipedia.org/wiki/Deep_learning) is a subset of Machine Learning, which is revolutionizing areas like Computer Vision and Speech Recognition.</span></span>

<span data-ttu-id="99706-130">Deep Learning-Modelle werden mithilfe großer Mengen [bezeichneter Daten](https://en.wikipedia.org/wiki/Labeled_data) und [neuronaler Netze](https://en.wikipedia.org/wiki/Artificial_neural_network) trainiert, die mehrere Lernebenen enthalten.</span><span class="sxs-lookup"><span data-stu-id="99706-130">Deep learning models are trained by using large sets of [labeled data](https://en.wikipedia.org/wiki/Labeled_data) and [neural networks](https://en.wikipedia.org/wiki/Artificial_neural_network) that contain multiple learning layers.</span></span> <span data-ttu-id="99706-131">Deep Learning:</span><span class="sxs-lookup"><span data-stu-id="99706-131">Deep learning:</span></span>

* <span data-ttu-id="99706-132">Bietet bei einigen Aufgaben eine bessere Leistung als maschinelles Sehen.</span><span class="sxs-lookup"><span data-stu-id="99706-132">Performs better on some tasks like Computer Vision.</span></span>

* <span data-ttu-id="99706-133">Bietet gute Leistungen bei großen Datenmengen.</span><span class="sxs-lookup"><span data-stu-id="99706-133">Performs well on huge data amounts.</span></span>

<span data-ttu-id="99706-134">Bildklassifizierung ist eine gängige Machine Learning-Aufgabe, mit der automatisch Bilder in mehrere Kategorien klassifiziert werden können, z.B.:</span><span class="sxs-lookup"><span data-stu-id="99706-134">Image Classification is a common Machine Learning task that allows us to automatically classify images into multiple categories such as:</span></span>

* <span data-ttu-id="99706-135">Erkennen, ob ein Bild ein menschliches Gesicht enthält oder nicht.</span><span class="sxs-lookup"><span data-stu-id="99706-135">Detecting a human face in an image or not.</span></span>
* <span data-ttu-id="99706-136">Unterscheiden zwischen Katzen und Hunden.</span><span class="sxs-lookup"><span data-stu-id="99706-136">Detecting Cats vs. dogs.</span></span>

 <span data-ttu-id="99706-137">Es lässt sich auch wie in den folgenden Bildern bestimmen, ob ein Bild ein Lebensmittel, ein Spielzeug oder ein Gerät zeigt:</span><span class="sxs-lookup"><span data-stu-id="99706-137">Or as in the following images determining if an image is a(n)  food, toy, or appliance:</span></span>

<span data-ttu-id="99706-138">![Pizzabild](./media/image-classification/220px-Pepperoni_pizza.jpg)
![Teddybärbild](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![Toasterbild](./media/image-classification/193px-Broodrooster.jpg)</span><span class="sxs-lookup"><span data-stu-id="99706-138">![pizza image](./media/image-classification/220px-Pepperoni_pizza.jpg)
![teddy bear image](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![toaster image](./media/image-classification/193px-Broodrooster.jpg)</span></span>

>[!Note]
> <span data-ttu-id="99706-139">Die vorherigen Abbildungen stammen aus Wikimedia-Commons und unterliegen folgendem Urheberrecht:</span><span class="sxs-lookup"><span data-stu-id="99706-139">The preceding images belong to Wikimedia Commons and are attributed as follows:</span></span>
>
> * <span data-ttu-id="99706-140">„220px-Pepperoni_pizza.jpg“ Public Domain https://commons.wikimedia.org/w/index.php?curid=79505,</span><span class="sxs-lookup"><span data-stu-id="99706-140">"220px-Pepperoni_pizza.jpg" Public Domain, https://commons.wikimedia.org/w/index.php?curid=79505,</span></span>
> * <span data-ttu-id="99706-141">„119px-Nalle_-_a_small_brown_teddy_bear.jpg“ von [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) – selbst fotografiert, CC-BY-SA-2.0, https://commons.wikimedia.org/w/index.php?curid=48166.</span><span class="sxs-lookup"><span data-stu-id="99706-141">"119px-Nalle_-_a_small_brown_teddy_bear.jpg" By [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - Self-photographed, CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166.</span></span>
> * <span data-ttu-id="99706-142">„193px-Broodrooster.jpg“ von [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) – eigenes Werk, CC-BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403</span><span class="sxs-lookup"><span data-stu-id="99706-142">"193px-Broodrooster.jpg" By [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - Own work, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403</span></span>

<span data-ttu-id="99706-143">Transfer Learning umfasst einige Strategien wie z.B. *erneutes Trainieren aller Ebenen* und die *vorletzte Ebene*.</span><span class="sxs-lookup"><span data-stu-id="99706-143">Transfer learning includes a few strategies, such as *retrain all layers* and *penultimate layer*.</span></span> <span data-ttu-id="99706-144">In diesem Tutorial wird die Verwendung der *Strategie der vorletzten Ebene* erläutert und veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="99706-144">This tutorial will explain and show how to use the *penultimate layer strategy*.</span></span> <span data-ttu-id="99706-145">Die *Strategie der vorletzten Ebene* verwendet ein Modell erneut, das bereits vortrainiert wurde, um ein bestimmtes Problem zu lösen.</span><span class="sxs-lookup"><span data-stu-id="99706-145">The *penultimate layer strategy* reuses a model that's already been pre-trained to solve a specific problem.</span></span> <span data-ttu-id="99706-146">Die Strategie trainiert dann die letzte Ebene dieses Modells erneut, um ein neues Problem zu lösen.</span><span class="sxs-lookup"><span data-stu-id="99706-146">The strategy then retrains the final layer of that model to make it solve a new problem.</span></span> <span data-ttu-id="99706-147">Aus dem Wiederverwenden des vortrainierten Modells als Teil des neuen Modells resultiert eine erhebliche Zeit- und Ressourcenersparnis.</span><span class="sxs-lookup"><span data-stu-id="99706-147">Reusing the pre-trained model as part of your new model will save significant time and resources.</span></span>

<span data-ttu-id="99706-148">Ihr Bildklassifizierungsmodell verwendet das [Inception-Modell](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) erneut, ein gängiges, am `ImageNet`-Dataset trainiertes Bilderkennungsmodell, in dem das TensorFlow-Modell versucht, ganze Bilder in Tausenden von Klassen wie „Regenschirm“, „Jersey“ und „Spülmaschine“ zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="99706-148">Your image classification model reuses the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), a popular image recognition model trained on the `ImageNet` dataset where the TensorFlow model tries to classify entire images into a thousand classes, like “Umbrella”, “Jersey”, and “Dishwasher”.</span></span>

<span data-ttu-id="99706-149">Das `Inception v3 model` kann als [Deep Convolutional Neural Network](https://en.wikipedia.org/wiki/Convolutional_neural_network) (tiefes faltendes neuronales Netzwerk) klassifiziert werden und kann eine angemessene Leistung bei schwierigen visuellen Erkennungsaufgaben erzielen, die in einigen Bereichen dem menschlichen Leistungsvermögen ebenbürtig ist oder es überschreitet.</span><span class="sxs-lookup"><span data-stu-id="99706-149">The `Inception v3 model` can be classified as a [deep convolutional neural network](https://en.wikipedia.org/wiki/Convolutional_neural_network) and can achieve reasonable performance on hard visual recognition tasks, matching or exceeding human performance in some domains.</span></span> <span data-ttu-id="99706-150">Das Modell / der Algorithmus wurde von mehreren Forschern entwickelt und basiert auf der ursprünglichen Arbeit: [„Rethinking the Inception Architecture for Computer Vision“ von Szegedy, et al.](https://arxiv.org/abs/1512.00567) (Neuer Ansatz der Inception-Architektur für maschinelles Sehen)</span><span class="sxs-lookup"><span data-stu-id="99706-150">The model/algorithm was developed by multiple researchers and based on the original paper: ["Rethinking the Inception Architecture for Computer Vision” by Szegedy, et. al.](https://arxiv.org/abs/1512.00567)</span></span>

<span data-ttu-id="99706-151">Da das `Inception model` bereits anhand von Tausenden anderer Bilder vortrainiert wurde, enthält es die zur Bildidentifizierung erforderlichen [Bildfeatures](https://en.wikipedia.org/wiki/Feature_(computer_vision)).</span><span class="sxs-lookup"><span data-stu-id="99706-151">Because the `Inception model` has already been pre trained on thousands of different images, it contains the [image features](https://en.wikipedia.org/wiki/Feature_(computer_vision)) needed for image identification.</span></span> <span data-ttu-id="99706-152">Die unteren Bildfeatureebenen erkennen einfache Features (z.B. Kanten), und die höheren Ebenen erkennen komplexere Features (z.B. Formen).</span><span class="sxs-lookup"><span data-stu-id="99706-152">The lower image feature layers recognize simple features (such as edges) and the higher layers recognize more complex features (such as shapes).</span></span> <span data-ttu-id="99706-153">Die letzte Ebene wird anhand einer viel kleinerer Menge von Daten trainiert, da Sie mit einem vortrainierten Modell beginnen, das bereits weiß, wie Bilder klassifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="99706-153">The final layer is trained against a much smaller set of data because you're starting with a pre trained model that already understands how to classify images.</span></span> <span data-ttu-id="99706-154">Da Sie mit Ihrem Modell mehr als zwei Kategorien klassifizieren können, ist dies ein Beispiel für eine [Multiklassenklassifizierung](../resources/tasks.md#multiclass-classification).</span><span class="sxs-lookup"><span data-stu-id="99706-154">As your model allows you to classify more than two categories, this is an example of a [multi-class classifier](../resources/tasks.md#multiclass-classification).</span></span> 

<span data-ttu-id="99706-155">`TensorFlow` ist ein gängiges Deep Learning- und Machine Learning-Toolkit, das das Trainieren von Deep Neural Networks (und allgemeine numerische Berechnungen) ermöglicht, und wird als `transformer` in ML.NET implementiert.</span><span class="sxs-lookup"><span data-stu-id="99706-155">`TensorFlow` is a popular deep learning and machine learning toolkit that enables training deep neural networks (and general numeric computations), and is implemented as a `transformer` in ML.NET.</span></span> <span data-ttu-id="99706-156">Für dieses Tutorial dient es zum Wiederverwenden des `Inception model`.</span><span class="sxs-lookup"><span data-stu-id="99706-156">For this tutorial, it's used to reuse the `Inception model`.</span></span>

<span data-ttu-id="99706-157">Wie im folgenden Diagramm dargestellt, fügen Sie einen Verweis auf die ML.NET-NuGet-Pakete in Ihrer .NET Core- oder .NET Framework-Anwendung hinzu.</span><span class="sxs-lookup"><span data-stu-id="99706-157">As shown in the following diagram, you add a reference to the ML.NET NuGet packages in your .NET Core or .NET Framework applications.</span></span> <span data-ttu-id="99706-158">Im Hintergrund enthält ML.NET die native `TensorFlow`-Bibliothek, mit der Sie Code schreiben können, der eine vorhandene trainierte `TensorFlow`-Modelldatei für die Bewertung lädt, und verweist darauf.</span><span class="sxs-lookup"><span data-stu-id="99706-158">Under the covers, ML.NET includes and references the native `TensorFlow` library that allows you to write code that loads an existing trained `TensorFlow` model file for scoring.</span></span>  

![TensorFlow-Transformation – ML.NET Arch-Diagramm](./media/image-classification/tensorflow-mlnet.png)

<span data-ttu-id="99706-160">Das `Inception model` ist darauf trainiert, Bilder in tausend Kategorien zu klassifizieren, jedoch müssen Sie Bilder in eine kleinere Kategoriegruppe und nur in diese Kategorien klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="99706-160">The `Inception model` is trained to classify images into a thousand categories, but you need to classify images in a smaller category set, and only those categories.</span></span> <span data-ttu-id="99706-161">Geben Sie den `transfer`-Teil von `transfer learning` ein.</span><span class="sxs-lookup"><span data-stu-id="99706-161">Enter the `transfer` part of `transfer learning`.</span></span> <span data-ttu-id="99706-162">Sie können die Fähigkeit des `Inception model` zum Erkennen und Klassifizieren von Bildern auf die neuen begrenzten Kategorien Ihrer benutzerdefinierten Bildklassifizierung übertragen.</span><span class="sxs-lookup"><span data-stu-id="99706-162">You can transfer the `Inception model`'s ability to recognize and classify images to the new limited categories of your custom image classifier.</span></span>  

 <span data-ttu-id="99706-163">Sie werden die letzte Ebene dieses Modells mit einem Satz von drei Kategorien neu trainieren:</span><span class="sxs-lookup"><span data-stu-id="99706-163">You're going to retrain the final layer of that model using a set of three categories:</span></span>

* <span data-ttu-id="99706-164">Lebensmittel</span><span class="sxs-lookup"><span data-stu-id="99706-164">Food</span></span>
* <span data-ttu-id="99706-165">Spielzeug</span><span class="sxs-lookup"><span data-stu-id="99706-165">Toy</span></span>
* <span data-ttu-id="99706-166">Gerät</span><span class="sxs-lookup"><span data-stu-id="99706-166">Appliance</span></span>

<span data-ttu-id="99706-167">Ihre Ebene verwendet einen [Algorithmus für multinomiale logistische Regression](https://en.wikipedia.org/wiki/Multinomial_logistic_regression), um so schnell wie möglich die richtige Kategorie zu finden.</span><span class="sxs-lookup"><span data-stu-id="99706-167">Your layer uses a [multinomial logistic regression algorithm](https://en.wikipedia.org/wiki/Multinomial_logistic_regression) to find the correct category as quickly as possible.</span></span> <span data-ttu-id="99706-168">Dieser Algorithmus verwendet zur Klassifizierung Wahrscheinlichkeiten, um die Antwort zu bestimmen, wobei der richtigen Kategorie der Wert 1 und den anderen der Wert 0 zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="99706-168">This algorithm classifies using probabilities to determine the answer, giving a one value to the correct category and a zero value to the others.</span></span>  

### <a name="dataset"></a><span data-ttu-id="99706-169">Dataset</span><span class="sxs-lookup"><span data-stu-id="99706-169">DataSet</span></span>

<span data-ttu-id="99706-170">Es gibt zwei Datenquellen: die `.tsv`-Datei und die Bilddateien.</span><span class="sxs-lookup"><span data-stu-id="99706-170">There are two data sources: the `.tsv` file, and the image files.</span></span>  <span data-ttu-id="99706-171">Die `tags.tsv`-Datei enthält zwei Spalten: die erste ist als `ImagePath` definiert und die zweite das `Label` für das Bild.</span><span class="sxs-lookup"><span data-stu-id="99706-171">The `tags.tsv` file contains two columns: the first one is defined as `ImagePath` and the second one is the `Label` corresponding to the image.</span></span> <span data-ttu-id="99706-172">Die folgende Beispieldatei verfügt nicht über eine Kopfzeile und sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="99706-172">The following example file doesn't have a header row, and looks like this:</span></span>

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

<span data-ttu-id="99706-173">Die Trainings- und Testbilder befinden sich in dem Assetsordner, den Sie in einer ZIP-Datei herunterladen.</span><span class="sxs-lookup"><span data-stu-id="99706-173">The training and testing images are located in the assets folders that you'll download in a zip file.</span></span> <span data-ttu-id="99706-174">Diese Bilder gehören zu Wikimedia Commons.</span><span class="sxs-lookup"><span data-stu-id="99706-174">These images belong to Wikimedia Commons.</span></span>
> <span data-ttu-id="99706-175">*[Wikimedia-Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), das Repository für kostenlose Medien.*</span><span class="sxs-lookup"><span data-stu-id="99706-175">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), the free media repository.*</span></span> <span data-ttu-id="99706-176">Abgerufen am 17. Oktober 2018 um 10:48 Uhr aus:</span><span class="sxs-lookup"><span data-stu-id="99706-176">Retrieved 10:48, October 17, 2018 from:</span></span>  
> https://commons.wikimedia.org/wiki/Pizza  
> https://commons.wikimedia.org/wiki/Toaster  
> https://commons.wikimedia.org/wiki/Teddy_bear  

## <a name="create-a-console-application"></a><span data-ttu-id="99706-177">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="99706-177">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="99706-178">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="99706-178">Create a project</span></span>

1. <span data-ttu-id="99706-179">Erstellen Sie eine **.NET Core-Konsolenanwendung** mit dem Namen „TransferLearningTF“.</span><span class="sxs-lookup"><span data-stu-id="99706-179">Create a **.NET Core Console Application** called "TransferLearningTF".</span></span>

2. <span data-ttu-id="99706-180">Installieren des **Microsoft.ML NuGet-Pakets**:</span><span class="sxs-lookup"><span data-stu-id="99706-180">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="99706-181">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="99706-181">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="99706-182">Wählen Sie „nuget.org“ als Paketquelle aus, wählen Sie die Registerkarte „Durchsuchen“ aus, und suchen Sie nach **Microsoft.ML**.</span><span class="sxs-lookup"><span data-stu-id="99706-182">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**.</span></span> <span data-ttu-id="99706-183">Klicken Sie auf die **Version**-Dropdownliste, wählen Sie das **1.0.0**-Paket in der Liste und dann die Schaltfläche **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="99706-183">Click on the **Version** drop-down, select the **1.0.0** package in the list, and select the **Install** button.</span></span> <span data-ttu-id="99706-184">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="99706-184">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="99706-185">Wiederholen Sie diese Schritte für **Microsoft.ML.ImageAnalytics v1.0.0** und **Microsoft.ML.TensorFlow v0.12.0**.</span><span class="sxs-lookup"><span data-stu-id="99706-185">Repeat these steps for **Microsoft.ML.ImageAnalytics v1.0.0** and **Microsoft.ML.TensorFlow v0.12.0**.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="99706-186">Vorbereiten Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="99706-186">Prepare your data</span></span>

1. <span data-ttu-id="99706-187">Laden Sie [die ZIP-Datei des Projektassetverzeichnisses](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip) herunter, und entzippen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="99706-187">Download [The project assets directory zip file](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip), and unzip.</span></span>

2. <span data-ttu-id="99706-188">Kopieren Sie das `assets`-Verzeichnis in Ihr *TransferLearningTF*-Projektverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="99706-188">Copy the `assets` directory into your *TransferLearningTF* project directory.</span></span> <span data-ttu-id="99706-189">Dieses Verzeichnis und seine Unterverzeichnisse enthalten die für dieses Tutorial erforderlichen Daten und Unterstützungsdateien (mit Ausnahme des Inception-Modells, das Sie im nächsten Schritt herunterladen und hinzufügen).</span><span class="sxs-lookup"><span data-stu-id="99706-189">This directory and its subdirectories contain the data and support files (except for the Inception model, which you'll download and add in the next step) needed for this tutorial.</span></span>

3. <span data-ttu-id="99706-190">Laden Sie das [Inception-Modell](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) herunter, und entzippen Sie es.</span><span class="sxs-lookup"><span data-stu-id="99706-190">Download the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), and unzip.</span></span>

4. <span data-ttu-id="99706-191">Kopieren Sie den Inhalt des gerade entzippten `inception5h`-Verzeichnisses in Ihr *TransferLearningTF*-Projektverzeichnis `assets\inputs-train\inception`.</span><span class="sxs-lookup"><span data-stu-id="99706-191">Copy the contents of the `inception5h` directory just unzipped into your *TransferLearningTF* project `assets\inputs-train\inception` directory.</span></span> <span data-ttu-id="99706-192">Dieses Verzeichnis enthält das Modell und die zusätzlich für dieses Tutorial erforderlichen Unterstützungsdateien wie in der folgenden Abbildung gezeigt:</span><span class="sxs-lookup"><span data-stu-id="99706-192">This directory contains the model and additional support files needed for this tutorial, as shown in the following image:</span></span>

   ![Inhalt des Inception-Verzeichnisses](./media/image-classification/inception-files.png)

5. <span data-ttu-id="99706-194">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf alle Dateien im Assetverzeichnis und den Unterverzeichnissen, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="99706-194">In Solution Explorer, right-click each of the files in the asset directory and subdirectories and select **Properties**.</span></span> <span data-ttu-id="99706-195">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="99706-195">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="99706-196">Erstellen von Klassen und Definieren von Pfaden</span><span class="sxs-lookup"><span data-stu-id="99706-196">Create classes and define paths</span></span>

<span data-ttu-id="99706-197">Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="99706-197">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddUsings)]

<span data-ttu-id="99706-198">Erstellen Sie globale Felder, die die Pfade zu den verschiedenen Assets enthalten, und globale Variablen für `LabelTokey`, `ImageReal` und `PredictedLabelValue`:</span><span class="sxs-lookup"><span data-stu-id="99706-198">Create global fields to hold the paths to the various assets, and global variables for the `LabelTokey`,`ImageReal`, and  `PredictedLabelValue`:</span></span>

* <span data-ttu-id="99706-199">`_assetsPath` enthält den Pfad zu den Assets.</span><span class="sxs-lookup"><span data-stu-id="99706-199">`_assetsPath` has the path to the assets.</span></span>
* <span data-ttu-id="99706-200">`_trainTagsTsv` enthält den Pfad zur TSV-Datei mit den Trainingsbilddaten-Tags.</span><span class="sxs-lookup"><span data-stu-id="99706-200">`_trainTagsTsv` has the path to the training image data tags tsv file.</span></span>
* <span data-ttu-id="99706-201">`_predictTagsTsv` enthält den Pfad zur TSV-Datei mit den Vorhersagebilddaten-Tags.</span><span class="sxs-lookup"><span data-stu-id="99706-201">`_predictTagsTsv` has the path to the prediction image data tags tsv file.</span></span>
* <span data-ttu-id="99706-202">`_trainImagesFolder` enthält den Pfad zu den Bildern, die zum Trainieren des Modells verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="99706-202">`_trainImagesFolder` has the path to the images used to train the model.</span></span>
* <span data-ttu-id="99706-203">`_predictImagesFolder` enthält den Pfad zu den Bildern, die vom trainierten Modell klassifiziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="99706-203">`_predictImagesFolder` has the path to the images to be classified by the trained model.</span></span>
* <span data-ttu-id="99706-204">`_inceptionPb` enthält den Pfad zu dem vortrainierten Inception-Modell, das zum erneuten Trainieren Ihres Modells wiederverwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="99706-204">`_inceptionPb` has the path to the pre-trained Inception model to be reused to retrain your model.</span></span>
* <span data-ttu-id="99706-205">`_inputImageClassifierZip` enthält den Pfad, über den das trainierte Modell geladen wird.</span><span class="sxs-lookup"><span data-stu-id="99706-205">`_inputImageClassifierZip` has the path where the trained model is loaded from.</span></span>
* <span data-ttu-id="99706-206">`_outputImageClassifierZip` enthält den Pfad zu dem Speicherort, in dem das trainierte Modell gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="99706-206">`_outputImageClassifierZip` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="99706-207">`LabelTokey` ist der einem Schlüssel zugeordnete `Label`-Wert.</span><span class="sxs-lookup"><span data-stu-id="99706-207">`LabelTokey` is the `Label` value mapped to a key.</span></span>
* <span data-ttu-id="99706-208">`ImageReal` ist die Spalte, die den vorhergesagten Bildwert enthält.</span><span class="sxs-lookup"><span data-stu-id="99706-208">`ImageReal`  is the column containing the predicted image value.</span></span>
* <span data-ttu-id="99706-209">`PredictedLabelValue` ist die Spalte, die den vorhergesagten Bezeichnungswert enthält.</span><span class="sxs-lookup"><span data-stu-id="99706-209">`PredictedLabelValue` is the column containing the predicted label value.</span></span>

<span data-ttu-id="99706-210">Fügen Sie den folgenden Code der Zeile direkt über der `Main`-Methode hinzu, um diese Pfade und die anderen Variablen anzugeben:</span><span class="sxs-lookup"><span data-stu-id="99706-210">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="99706-211">Erstellen Sie einige Klassen für Ihre Eingabedaten und Vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="99706-211">Create some classes for your input data, and predictions.</span></span> <span data-ttu-id="99706-212">Fügen Sie dem Projekt eine neue Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="99706-212">Add a new class to your project:</span></span>

1. <span data-ttu-id="99706-213">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="99706-213">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="99706-214">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *ImageData.cs*.</span><span class="sxs-lookup"><span data-stu-id="99706-214">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImageData.cs*.</span></span> <span data-ttu-id="99706-215">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="99706-215">Then, select the **Add** button.</span></span>

    <span data-ttu-id="99706-216">Die Datei *ImageData.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="99706-216">The *ImageData.cs* file opens in the code editor.</span></span> <span data-ttu-id="99706-217">Fügen Sie die folgende `using`-Anweisung am Anfang der *ImageData.cs*-Datei hinzu:</span><span class="sxs-lookup"><span data-stu-id="99706-217">Add the following `using` statement to the top of *ImageData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#AddUsings)]

<span data-ttu-id="99706-218">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code für die `ImageData`-Klasse der *ImageData.cs*-Datei hinzu:</span><span class="sxs-lookup"><span data-stu-id="99706-218">Remove the existing class definition and add the following code for the `ImageData` class to the *ImageData.cs* file:</span></span>

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#DeclareTypes)]

<span data-ttu-id="99706-219">`ImageData` ist die Eingabebilddaten-Klasse mit den folgenden <xref:System.String>-Feldern:</span><span class="sxs-lookup"><span data-stu-id="99706-219">`ImageData` is the input image data class and has the following <xref:System.String> fields:</span></span>

* <span data-ttu-id="99706-220">`ImagePath` enthält den Bilddateinamen.</span><span class="sxs-lookup"><span data-stu-id="99706-220">`ImagePath` contains the image file name.</span></span>
* <span data-ttu-id="99706-221">`Label` enthält einen Wert für die Bildbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="99706-221">`Label` contains a value for the image label.</span></span>

<span data-ttu-id="99706-222">Fügen Sie dem Projekt eine neue Klasse für `ImagePrediction` hinzu:</span><span class="sxs-lookup"><span data-stu-id="99706-222">Add a new class to your project for `ImagePrediction`:</span></span>

1. <span data-ttu-id="99706-223">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="99706-223">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="99706-224">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *ImagePrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="99706-224">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImagePrediction.cs*.</span></span> <span data-ttu-id="99706-225">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="99706-225">Then, select the **Add** button.</span></span>

    <span data-ttu-id="99706-226">Die Datei *ImagePrediction.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="99706-226">The *ImagePrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="99706-227">Entfernen Sie sowohl die `System.Collections.Generic`- als auch die `System.Text` `using`-Anweisung am Anfang von *ImagePrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="99706-227">Remove both the `System.Collections.Generic` and the `System.Text` `using` statements at the top of *ImagePrediction.cs*:</span></span>

<span data-ttu-id="99706-228">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code mit der Klasse `ImagePrediction` der Datei *ImagePrediction.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="99706-228">Remove the existing class definition and add the following code, which has the `ImagePrediction` class, to the *ImagePrediction.cs* file:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/ImagePrediction.cs#DeclareTypes)]

<span data-ttu-id="99706-229">`ImagePrediction` ist die Bildvorhersageklasse und hat die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="99706-229">`ImagePrediction` is the image prediction class and has the following fields:</span></span>

* <span data-ttu-id="99706-230">`Score` enthält den Zuverlässigkeitsprozentsatz für eine bestimmte Bildklassifizierung.</span><span class="sxs-lookup"><span data-stu-id="99706-230">`Score` contains the confidence percentage for a given image classification.</span></span>
* <span data-ttu-id="99706-231">`PredictedLabelValue` enthält einen Wert für die vorhergesagte Bildklassifizierungsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="99706-231">`PredictedLabelValue` contains a value for the predicted image classification label.</span></span>

<span data-ttu-id="99706-232">Die `ImagePrediction`-Klasse wird für die Vorhersage verwendet, nachdem das Modell trainiert wurde.</span><span class="sxs-lookup"><span data-stu-id="99706-232">`ImagePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="99706-233">Sie besitzt einen `string` (`ImagePath`) für den Bildpfad.</span><span class="sxs-lookup"><span data-stu-id="99706-233">It has a `string` (`ImagePath`) for the image path.</span></span> <span data-ttu-id="99706-234">Mit `Label` wird das Modell wiederverwendet und neu trainiert.</span><span class="sxs-lookup"><span data-stu-id="99706-234">The `Label` is used to reuse and retrain the model.</span></span> <span data-ttu-id="99706-235">Das `PredictedLabelValue` wird während der Vorhersage und Evaluierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="99706-235">The `PredictedLabelValue` is used during prediction and evaluation.</span></span> <span data-ttu-id="99706-236">Für die Evaluierung werden eine Eingabe mit Trainingsdaten, die vorhergesagten Werte und das Modell verwendet.</span><span class="sxs-lookup"><span data-stu-id="99706-236">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="99706-237">Die [MLContext-Klasse](xref:Microsoft.ML.MLContext) ist der Startpunkt für alle ML.NET-Vorgänge. Durch das Initialisieren von `mlContext` wird eine neue ML.NET-Umgebung erstellt, die für mehrere Objekte des Modellerstellungsworkflows verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="99706-237">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="99706-238">Die Klasse ähnelt dem Konzept von `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="99706-238">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="99706-239">Initialisieren von Variablen in Main</span><span class="sxs-lookup"><span data-stu-id="99706-239">Initialize variables in Main</span></span>

<span data-ttu-id="99706-240">Initialisieren Sie die `mlContext`-Variable mit einer neuen Instanz von `MLContext`.</span><span class="sxs-lookup"><span data-stu-id="99706-240">Initialize the `mlContext` variable with a new instance of `MLContext`.</span></span>  <span data-ttu-id="99706-241">Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` mit dem folgenden Code in der `Main`-Methode:</span><span class="sxs-lookup"><span data-stu-id="99706-241">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CreateMLContext)]

### <a name="create-a-struct-for-default-parameters"></a><span data-ttu-id="99706-242">Erstellen einer Struktur für Standardparameter</span><span class="sxs-lookup"><span data-stu-id="99706-242">Create a struct for default parameters</span></span>

<span data-ttu-id="99706-243">Das Inception-Modell verfügt über mehrere Standardparameter, die Sie übergeben müssen.</span><span class="sxs-lookup"><span data-stu-id="99706-243">The Inception model has several default parameters you need to pass in.</span></span> <span data-ttu-id="99706-244">Erstellen Sie unmittelbar nach der `Main()`-Methode eine Struktur, um Anzeigenamen mit dem folgenden Code die Standardparameterwerte zuzuordnen:</span><span class="sxs-lookup"><span data-stu-id="99706-244">Create a struct to map the default parameter values to friendly names with the following code, just after the `Main()` method:</span></span>

[!code-csharp[InceptionSettings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a><span data-ttu-id="99706-245">Erstellen einer Anzeigehilfsprogramm-Methode</span><span class="sxs-lookup"><span data-stu-id="99706-245">Create a display utility method</span></span>

<span data-ttu-id="99706-246">Da Sie die Bilddaten und die zugehörigen Vorhersagen mehr als einmal anzeigen werden, erstellen Sie eine Anzeigehilfsmethode, um die Anzeige der Bild- und Vorhersageergebnisse zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="99706-246">Since you'll display the image data and the related predictions more than once, create a display utility method to handle displaying the image and prediction results.</span></span>

<span data-ttu-id="99706-247">Die `DisplayResults()`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="99706-247">The `DisplayResults()` method executes the following tasks:</span></span>

* <span data-ttu-id="99706-248">Anzeigen der vorhergesagten Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="99706-248">Displays the predicted results.</span></span>

<span data-ttu-id="99706-249">Erstellen Sie die `DisplayResults()`-Methode mit dem folgenden Code direkt nach der `InceptionSettings`-Struktur:</span><span class="sxs-lookup"><span data-stu-id="99706-249">Create the `DisplayResults()` method, just after the `InceptionSettings` struct, using the following code:</span></span>

```csharp
private static void DisplayResults(IEnumerable<ImagePrediction> imagePredictionData)
{

}
```

<span data-ttu-id="99706-250">Der in `ImagePrediction` eingegebene `ImagePath` der `Transform()`-Methode mit den vorhergesagten Feldern.</span><span class="sxs-lookup"><span data-stu-id="99706-250">The `Transform()` method populated `ImagePath` in `ImagePrediction` along with the predicted fields.</span></span> <span data-ttu-id="99706-251">Im Laufe des ML.NET-Prozesses fügt jede Komponente Spalten hinzu, sodass die Ergebnisse leicht angezeigt werden können:</span><span class="sxs-lookup"><span data-stu-id="99706-251">As the ML.NET process progresses, each component adds columns, and this makes it easy to display the results:</span></span>

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPredictions)]

<span data-ttu-id="99706-252">Sie rufen die `DisplayResults()` -Methode in den zwei Bildklassifizierungsmethoden auf.</span><span class="sxs-lookup"><span data-stu-id="99706-252">You'll call the `DisplayResults()` method in the two image classification methods.</span></span>

### <a name="create-a-tsv-file-utility-method"></a><span data-ttu-id="99706-253">Erstellen einer Hilfsprogrammmethode für die TSV-Datei</span><span class="sxs-lookup"><span data-stu-id="99706-253">Create a .tsv file utility method</span></span>

<span data-ttu-id="99706-254">Die `ReadFromTsv()`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="99706-254">The `ReadFromTsv()` method executes the following tasks:</span></span>

* <span data-ttu-id="99706-255">Lesen der Bilddatendatei `tags.tsv`.</span><span class="sxs-lookup"><span data-stu-id="99706-255">Reads the image data `tags.tsv` file.</span></span>
* <span data-ttu-id="99706-256">Hinzufügen des Bildpfads zum Bilddateinamen.</span><span class="sxs-lookup"><span data-stu-id="99706-256">Adds the file path to the image file name.</span></span>
* <span data-ttu-id="99706-257">Laden der Dateidaten in ein IEnumerable`ImageData`-Objekt.</span><span class="sxs-lookup"><span data-stu-id="99706-257">Loads the file data into an IEnumerable`ImageData` object.</span></span>

<span data-ttu-id="99706-258">Erstellen Sie die `ReadFromTsv()`-Methode mit dem folgenden Code direkt nach der `PairAndDisplayResults()`-Methode:</span><span class="sxs-lookup"><span data-stu-id="99706-258">Create the `ReadFromTsv()` method, just after the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
{

}
```

<span data-ttu-id="99706-259">Der folgende Code analysiert die `tags.tsv`-Datei, um den Dateipfad für die `ImagePath`-Eigenschaft dem Namen der Bilddatei hinzuzufügen und ihn und das `Label` in ein `ImageData`-Objekt zu laden.</span><span class="sxs-lookup"><span data-stu-id="99706-259">The following code parses through the `tags.tsv` file to add the file path to the image file name for the `ImagePath` property and load it and the `Label` into an `ImageData` object.</span></span> <span data-ttu-id="99706-260">Fügen Sie ihn als erste Zeile der `ReadFromTsv()`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="99706-260">Add it as the first line of the `ReadFromTsv()` method.</span></span>  <span data-ttu-id="99706-261">Zum Anzeigen der Vorhersageergebnisse benötigen Sie den vollqualifizierten Dateipfad.</span><span class="sxs-lookup"><span data-stu-id="99706-261">You need the fully qualified file path to display the prediction results.</span></span>

[!code-csharp[ReadFromTsv](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReadFromTsv)]
<span data-ttu-id="99706-262">In ML.NET werden die folgenden drei Hauptkonzepte genutzt: [Daten](../resources/glossary.md#data), [Transformatoren](../resources/glossary.md#transformer) (Transformers) und [Schätzer](../resources/glossary.md#estimator) (Estimators).</span><span class="sxs-lookup"><span data-stu-id="99706-262">There are three major concepts in ML.NET: [Data](../resources/glossary.md#data), [Transformers](../resources/glossary.md#transformer), and [Estimators](../resources/glossary.md#estimator).</span></span>

## <a name="reuse-and-tune-pre-trained-model"></a><span data-ttu-id="99706-263">Wiederverwenden und Optimieren des vortrainierten Modells</span><span class="sxs-lookup"><span data-stu-id="99706-263">Reuse and tune pre-trained model</span></span>

<span data-ttu-id="99706-264">Fügen Sie der `ReuseAndTuneInceptionModel()`-Methode den folgenden Aufruf als nächste Codezeile der `Main()`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="99706-264">Add the following call to the `ReuseAndTuneInceptionModel()`method as the next line of code in the `Main()` method:</span></span>

[!code-csharp[CallReuseAndTuneInceptionModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReuseAndTuneInceptionModel)]

<span data-ttu-id="99706-265">Die `ReuseAndTuneInceptionModel()`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="99706-265">The `ReuseAndTuneInceptionModel()` method executes the following tasks:</span></span>

* <span data-ttu-id="99706-266">Laden der Daten.</span><span class="sxs-lookup"><span data-stu-id="99706-266">Loads the data</span></span>
* <span data-ttu-id="99706-267">Extrahieren und Transformieren der Daten.</span><span class="sxs-lookup"><span data-stu-id="99706-267">Extracts and transforms the data.</span></span>
* <span data-ttu-id="99706-268">Bewerten des TensorFlow-Modells.</span><span class="sxs-lookup"><span data-stu-id="99706-268">Scores the TensorFlow model.</span></span>
* <span data-ttu-id="99706-269">Optimieren (erneutes Trainieren) des Modells.</span><span class="sxs-lookup"><span data-stu-id="99706-269">Tunes (retrains) the model.</span></span>
* <span data-ttu-id="99706-270">Anzeigen von Modellergebnissen.</span><span class="sxs-lookup"><span data-stu-id="99706-270">Displays model results.</span></span>
* <span data-ttu-id="99706-271">Auswerten des Modells.</span><span class="sxs-lookup"><span data-stu-id="99706-271">Evaluates the model.</span></span>
* <span data-ttu-id="99706-272">Zurückgeben des Modells.</span><span class="sxs-lookup"><span data-stu-id="99706-272">Returns the model.</span></span>

<span data-ttu-id="99706-273">Erstellen Sie die `ReuseAndTuneInceptionModel()`-Methode mithilfe des folgenden Codes unmittelbar nach der `InceptionSettings`-Struktur und direkt vor der `DisplayResults()`-Methode:</span><span class="sxs-lookup"><span data-stu-id="99706-273">Create the `ReuseAndTuneInceptionModel()` method, just after the `InceptionSettings` struct and just before the `DisplayResults()` method, using the following code:</span></span>

```csharp
public static ITransformer ReuseAndTuneInceptionModel(MLContext mlContext, string dataLocation, string imagesFolder, string inputModelLocation, string outputModelLocation)
{

}
```

### <a name="load-the-data"></a><span data-ttu-id="99706-274">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="99706-274">Load the data</span></span>

<span data-ttu-id="99706-275">Daten werden in ML.NET als [IDataView-Klasse](xref:Microsoft.ML.IDataView) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="99706-275">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="99706-276">Mit `IDataView` können Tabellendaten (Zahlen und Text) flexibel und effizient beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="99706-276">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="99706-277">Daten können aus einer Textdatei oder in Echtzeit (z. B. aus einer SQL-Datenbank oder aus Protokolldateien) in ein `IDataView`-Objekt geladen werden.</span><span class="sxs-lookup"><span data-stu-id="99706-277">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="99706-278">Laden der Daten mithilfe des `MLContext.Data.LoadFromTextFile`-Wrappers.</span><span class="sxs-lookup"><span data-stu-id="99706-278">Load the data using the `MLContext.Data.LoadFromTextFile` wrapper.</span></span> <span data-ttu-id="99706-279">Fügen Sie der `ReuseAndTuneInceptionModel()`-Methode folgenden Code als nächste Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="99706-279">Add the following code as the next line in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[LoadData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadData "Load the data")]

### <a name="extract-features-and-transform-the-data"></a><span data-ttu-id="99706-280">Extrahieren von Features und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="99706-280">Extract Features and transform the data</span></span>

<span data-ttu-id="99706-281">Vorverarbeitung und Bereinigung von Daten sind wichtige Aufgaben, die durchgeführt werden, bevor ein Dataset effektiv für Machine Learning verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="99706-281">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span>  <span data-ttu-id="99706-282">Die Verwendung von Daten ohne diese Modellierungsaufgaben kann irreführende Ergebnisse erzeugen.</span><span class="sxs-lookup"><span data-stu-id="99706-282">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="99706-283">Machine Learning-Algorithmen verstehen [mit Features ausgestattete](../resources/glossary.md#feature) Daten, und beim Umgang mit Deep Neural Networks müssen Sie die Bilder dem Format anpassen, das vom Netzwerk erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="99706-283">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, and when dealing with deep neural networks you must adapt the images to the format expected by the network.</span></span> <span data-ttu-id="99706-284">Dieses Format ist ein [numerischer Vektor](../resources/glossary.md#numerical-feature-vector).</span><span class="sxs-lookup"><span data-stu-id="99706-284">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="99706-285">Führen Sie nach Training und Auswertung eine Vorhersage mit den Werten der **Label**-Spalte durch.</span><span class="sxs-lookup"><span data-stu-id="99706-285">After training and evaluation, predict with the **Label** column values.</span></span> <span data-ttu-id="99706-286">Da Sie ein vortrainiertes Modell verwenden, ordnen Sie dem neuen Modell Felder mit der [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A)-Methode zu.</span><span class="sxs-lookup"><span data-stu-id="99706-286">As you're using a pre-trained model, map fields to the new model with the [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) method.</span></span> <span data-ttu-id="99706-287">Diese Methode wandelt das `Label` in einen numerischen Schlüsseltyp (`LabelTokey`) um und fügt es als neue Datasetspalte hinzu:  Benennen Sie diese mit `estimator`, da Sie ihr auch den Trainer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="99706-287">This method transforms the `Label` into a numeric key type (`LabelTokey`) column and add it as new dataset column:  Name this `estimator` as you'll also add the trainer to it.</span></span> <span data-ttu-id="99706-288">Fügen Sie die nächste Codezeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="99706-288">Add the next line of code:</span></span>

[!code-csharp[MapValueToKey1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey1)]

<span data-ttu-id="99706-289">Ihr Bildverarbeitungsschätzer verwendet vortrainierte [Deep Neural Network (DNN)](https://en.wikipedia.org/wiki/Deep_learning#Deep_neural_networks)-Featurebereitsteller für die Featureextraktion.</span><span class="sxs-lookup"><span data-stu-id="99706-289">Your image processing estimator uses pre-trained [Deep Neural Network(DNN)](https://en.wikipedia.org/wiki/Deep_learning#Deep_neural_networks) featurizers for feature extraction.</span></span> <span data-ttu-id="99706-290">Beim Umgang mit Deep Neural Networks passen Sie die Bilder dem vom Netzwerk erwarteten Format an.</span><span class="sxs-lookup"><span data-stu-id="99706-290">When dealing with deep neural networks, you  adapt the images to the expected network format.</span></span> <span data-ttu-id="99706-291">Aus diesem Grund verwenden Sie mehrere Bildtransformationen, um die Bilddaten in die vom Modell erwartete Form zu bringen:</span><span class="sxs-lookup"><span data-stu-id="99706-291">This is the reason you use several image transforms to get the image data into the model's expected form:</span></span>

1. <span data-ttu-id="99706-292">Die `LoadImages`-Transformationsbilder werden als Bitmaptyp in den Arbeitsspeicher geladen.</span><span class="sxs-lookup"><span data-stu-id="99706-292">The `LoadImages`transform images are loaded in memory as a Bitmap type.</span></span>
2. <span data-ttu-id="99706-293">Die `ResizeImages`-Transformation ändert die Größe der Bilder, da Breite und Höhe des Eingabebilds beim vortrainierten Modell definiert sind.</span><span class="sxs-lookup"><span data-stu-id="99706-293">The `ResizeImages` transform resizes the images as the pre-trained model has a defined input image width and height.</span></span>
3. <span data-ttu-id="99706-294">Die `ExtractPixels`-Transformation extrahiert die Pixel aus den Eingabebildern und wandelt sie in einen numerischen Vektor um.</span><span class="sxs-lookup"><span data-stu-id="99706-294">The `ExtractPixels` transform extracts the pixels from the input images and converts them into a numeric vector.</span></span>

<span data-ttu-id="99706-295">Fügen Sie diese Bildtransformationen als nächste Codezeilen hinzu:</span><span class="sxs-lookup"><span data-stu-id="99706-295">Add these image transforms as the next lines of code:</span></span>

[!code-csharp[ImageTransforms](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ImageTransforms)]

<span data-ttu-id="99706-296">Das `LoadTensorFlowModel` ist eine praktische Methode, die es ermöglicht, das `TensorFlow`-Modell einmal zu laden und dann den `TensorFlowEstimator` mit dem `ScoreTensorFlowModel` zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="99706-296">The `LoadTensorFlowModel` is a convenience method that allows the `TensorFlow` model to be loaded once and then creates the `TensorFlowEstimator` using `ScoreTensorFlowModel`.</span></span> <span data-ttu-id="99706-297">Die `ScoreTensorFlowModel` extrahiert angegebene Ausgaben (die `softmax2_pre_activation` der Bildfeatures des `Inception model`) und bewertet ein Dataset mithilfe des vorab trainierten `TensorFlow`-Modells.</span><span class="sxs-lookup"><span data-stu-id="99706-297">The `ScoreTensorFlowModel` extracts specified outputs (the `Inception model`'s image features `softmax2_pre_activation`), and scores a dataset using the pre-trained `TensorFlow` model.</span></span>

<span data-ttu-id="99706-298">`softmax2_pre_activation` unterstützt das Modell mit der Bestimmung, zu welcher Klasse die Bilder gehören.</span><span class="sxs-lookup"><span data-stu-id="99706-298">`softmax2_pre_activation` assists the model with determining which class the images belongs to.</span></span> <span data-ttu-id="99706-299">`softmax2_pre_activation` gibt für jede Kategorie eine Wahrscheinlichkeit für ein Bild zurück, und alle diese Wahrscheinlichkeiten müssen 1 ergeben.</span><span class="sxs-lookup"><span data-stu-id="99706-299">`softmax2_pre_activation` returns a probability for each of the categories for an image, and all of those probabilities must add up to 1.</span></span> <span data-ttu-id="99706-300">Es wird davon ausgegangen, dass ein Bild nur zu einer einzigen Kategorie gehört, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="99706-300">It assumes that an image will belong to only one category, as shown in the following example:</span></span>

| <span data-ttu-id="99706-301">Klasse</span><span class="sxs-lookup"><span data-stu-id="99706-301">Class</span></span>         | <span data-ttu-id="99706-302">Wahrscheinlichkeit</span><span class="sxs-lookup"><span data-stu-id="99706-302">Probability</span></span>   |
| ------------- | ------------- |
| `Food`        |  <span data-ttu-id="99706-303">0,001</span><span class="sxs-lookup"><span data-stu-id="99706-303">0.001</span></span>        |
| `Toy`         |  <span data-ttu-id="99706-304">0,95</span><span class="sxs-lookup"><span data-stu-id="99706-304">0.95</span></span>         |
| `Appliance`   |  <span data-ttu-id="99706-305">0,06</span><span class="sxs-lookup"><span data-stu-id="99706-305">0.06</span></span>         |

<span data-ttu-id="99706-306">Fügen Sie die `TensorFlowTransform` mit den folgenden Codezeilen dem `estimator` an:</span><span class="sxs-lookup"><span data-stu-id="99706-306">Append the `TensorFlowTransform` to the `estimator` with the following line of code:</span></span>

[!code-csharp[ScoreTensorFlowModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ScoreTensorFlowModel)]

### <a name="choose-a-training-algorithm"></a><span data-ttu-id="99706-307">Auswählen eines Trainingsalgorithmus</span><span class="sxs-lookup"><span data-stu-id="99706-307">Choose a training algorithm</span></span>

<span data-ttu-id="99706-308">Um den Trainingsalgorithmus hinzuzufügen, rufen Sie die `mlContext.MulticlassClassification.Trainers.LbfgsMaximumEntropy()`-Wrappermethode auf.</span><span class="sxs-lookup"><span data-stu-id="99706-308">To add the training algorithm, call the `mlContext.MulticlassClassification.Trainers.LbfgsMaximumEntropy()` wrapper method.</span></span>  <span data-ttu-id="99706-309">[LbfgsMaximumEntropy](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer) wird dem `estimator` angefügt und akzeptiert die Inception-Bildfeatures (`softmax2_pre_activation`) und die `Label`-Eingabeparameter, um aus den historischen Daten zu lernen.</span><span class="sxs-lookup"><span data-stu-id="99706-309">The [LbfgsMaximumEntropy](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer) is appended to the `estimator` and accepts the Inception image features (`softmax2_pre_activation`) and the `Label` input parameters to learn from the historic data.</span></span>  <span data-ttu-id="99706-310">Fügen Sie den Trainer mit dem folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="99706-310">Add the trainer with the following code:</span></span>

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddTrainer)]

<span data-ttu-id="99706-311">Sie müssen auch das `predictedlabel` dem `predictedlabelvalue` zuordnen:</span><span class="sxs-lookup"><span data-stu-id="99706-311">You also need to map the `predictedlabel` to the `predictedlabelvalue`:</span></span>

[!code-csharp[MapValueToKey2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey2)]

<span data-ttu-id="99706-312">Mit der `Fit()`-Methode wird Ihr Modell trainiert, indem das Dataset transformiert und das Training angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="99706-312">The `Fit()` method trains your model by transforming the dataset and applying the training.</span></span> <span data-ttu-id="99706-313">Fügen Sie den unten aufgeführten Code als nächste Codezeilen in die `ReuseAndTuneInceptionModel()`-Methode ein, um das Modell an das Trainingsdataset anzupassen und das trainierte Modell zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="99706-313">Fit the model to the training dataset and return the trained model by adding the following as the next line of code in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TrainModel)]

<span data-ttu-id="99706-314">Die [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A)-Methode trifft Vorhersagen für mehrere bereitgestellte Eingabezeilen eines Testdatasets.</span><span class="sxs-lookup"><span data-stu-id="99706-314">The [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method makes predictions for multiple provided input rows of a test dataset.</span></span>  <span data-ttu-id="99706-315">Fügen Sie `ReuseAndTuneInceptionModel()` den folgenden Code hinzu, um die `Training`-Daten zu transformieren:</span><span class="sxs-lookup"><span data-stu-id="99706-315">Transform the `Training` data by adding the following code to `ReuseAndTuneInceptionModel()`:</span></span>

[!code-csharp[TransformData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TransformData)]

<span data-ttu-id="99706-316">Konvertieren Sie Ihre Bilddaten und die Vorhersage-`DataViews` zur Kopplung für eine einfachere Anzeige in stark typisierte `IEnumerables`.</span><span class="sxs-lookup"><span data-stu-id="99706-316">Convert your image data and prediction `DataViews` into strongly-typed `IEnumerables` to pair for easier display.</span></span> <span data-ttu-id="99706-317">Verwenden Sie hierzu die `MLContext.CreateEnumerable()`-Methode mit dem folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="99706-317">Use the `MLContext.CreateEnumerable()` method to do that, using the following code:</span></span>

[!code-csharp[EnumerateDataViews](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#EnumerateDataViews)]

<span data-ttu-id="99706-318">Rufen Sie die `DisplayResults()`-Methode zum Anzeigen Ihrer Daten und Vorhersagen als nächste Zeile in der `ReuseAndTuneInceptionModel()`-Methode auf:</span><span class="sxs-lookup"><span data-stu-id="99706-318">Call the `DisplayResults()` method to display your data and predictions as the next line in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[CallDisplayResults1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults1)]

<span data-ttu-id="99706-319">Nachdem Sie die Vorhersage festgelegt haben, führt die [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A)-Methode Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="99706-319">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) method:</span></span>

* <span data-ttu-id="99706-320">Bewerten des Modells (Vergleich der vorhergesagten Werte mit dem tatsächlichen Dataset `Labels`).</span><span class="sxs-lookup"><span data-stu-id="99706-320">Assesses the model (compares the predicted values with the actual dataset `Labels`).</span></span>

* <span data-ttu-id="99706-321">Rückgabe der Modellleistungsmetriken.</span><span class="sxs-lookup"><span data-stu-id="99706-321">Returns the model performance metrics.</span></span>

<span data-ttu-id="99706-322">Fügen Sie der `ReuseAndTuneInceptionModel()`-Methode folgenden Code als nächste Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="99706-322">Add the following code to the `ReuseAndTuneInceptionModel()` method as the next line:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Evaluate)]

<span data-ttu-id="99706-323">Für die Bildklassifizierung werden die folgenden Metriken ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="99706-323">The following metrics are evaluated for image classification:</span></span>

* <span data-ttu-id="99706-324">`Log-loss` – siehe [Protokollverlust](../resources/glossary.md#log-loss).</span><span class="sxs-lookup"><span data-stu-id="99706-324">`Log-loss` - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="99706-325">Der Protokollverlust sollte so nahe wie möglich bei 0 liegen.</span><span class="sxs-lookup"><span data-stu-id="99706-325">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="99706-326">`Per class Log-loss`.</span><span class="sxs-lookup"><span data-stu-id="99706-326">`Per class Log-loss`.</span></span> <span data-ttu-id="99706-327">Der Protokollverlust pro Klasse sollte so nahe wie möglich bei 0 liegen.</span><span class="sxs-lookup"><span data-stu-id="99706-327">You want per class Log-loss to be as close to zero as possible.</span></span>

<span data-ttu-id="99706-328">Verwenden Sie den folgenden Code, um die Metriken anzuzeigen, die Ergebnisse freizugeben und dann mit ihnen zu arbeiten:</span><span class="sxs-lookup"><span data-stu-id="99706-328">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayMetrics)]

 <span data-ttu-id="99706-329">Fügen Sie den folgenden Code hinzu, um das trainierte Modell als nächste Zeile zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="99706-329">Add the following code to return the trained model as the next line:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReturnModel)]

## <a name="classify-images-with-a-loaded-model"></a><span data-ttu-id="99706-330">Klassifizieren von Bildern mit einem geladenen Modell</span><span class="sxs-lookup"><span data-stu-id="99706-330">Classify images with a loaded model</span></span>

<span data-ttu-id="99706-331">Fügen Sie den folgenden Aufruf der `ClassifyImages()`-Methode als nächste Codezeile der `Main`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="99706-331">Add the following call to the `ClassifyImages()` method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallClassifyImages](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifyImages)]

<span data-ttu-id="99706-332">Die `ClassifyImages()`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="99706-332">The `ClassifyImages()` method executes the following tasks:</span></span>

* <span data-ttu-id="99706-333">Einlesen der TSV-Datei in `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="99706-333">Reads .TSV file into `IEnumerable`.</span></span>
* <span data-ttu-id="99706-334">Vorhersage der Bildklassifizierungen anhand von Testdaten.</span><span class="sxs-lookup"><span data-stu-id="99706-334">Predicts image classifications based on test data.</span></span>

<span data-ttu-id="99706-335">Erstellen Sie die `ClassifyImages()`-Methode mithilfe des folgenden Codes unmittelbar nach der `ReuseAndTuneInceptionModel()`-Methode und direkt vor der `PairAndDisplayResults()`-Methode:</span><span class="sxs-lookup"><span data-stu-id="99706-335">Create the `ClassifyImages()` method, just after the `ReuseAndTuneInceptionModel()` method and just before the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static void ClassifyImages(MLContext mlContext, string dataLocation, string imagesFolder, string outputModelLocation, ITransformer model)
{

}
```

<span data-ttu-id="99706-336">Rufen Sie zunächst die `ReadFromTsv()`-Methode zum Erstellen einer `IEnumerable<ImageData>`-Klasse auf, die den vollqualifizierten Pfad für jeden `ImagePath` enthält.</span><span class="sxs-lookup"><span data-stu-id="99706-336">First, call the `ReadFromTsv()` method to create an `IEnumerable<ImageData>` class that contains the fully qualified path for each `ImagePath`.</span></span> <span data-ttu-id="99706-337">Sie benötigen diesen Dateipfad, um Ihre Daten und Vorhersageergebnisse zu koppeln.</span><span class="sxs-lookup"><span data-stu-id="99706-337">You need that file path to pair your data and prediction results.</span></span> <span data-ttu-id="99706-338">Sie müssen außerdem die `IEnumerable<ImageData>`-Klasse in eine `IDataView` konvertieren, die Sie zur Vorhersage verwenden.</span><span class="sxs-lookup"><span data-stu-id="99706-338">You also need to convert the `IEnumerable<ImageData>` class to an `IDataView` that you will use to predict.</span></span> <span data-ttu-id="99706-339">Fügen Sie der `ClassifyImages()`-Methode den folgenden Code in den nächsten beiden Zeilen hinzu:</span><span class="sxs-lookup"><span data-stu-id="99706-339">Add the following code as the next two lines in the `ClassifyImages()` method:</span></span>

[!code-csharp[CallReadFromTSV](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReadFromTSV)]

<span data-ttu-id="99706-340">Sagen Sie wie zuvor bei den Trainingsbilddaten die Kategorie der Testbilddaten mit der [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A)-Methode des übergebenen Modells vorher.</span><span class="sxs-lookup"><span data-stu-id="99706-340">As you did previously with the training image data, predict the category of the test image data using the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method of the model passed in.</span></span> <span data-ttu-id="99706-341">Fügen Sie der `ClassifyImages()`-Methode den folgenden Code für die Vorhersagen und zum Konvertieren der `predictions` `IDataView` in ein `IEnumerable` für Kopplung und Anzeige hinzu:</span><span class="sxs-lookup"><span data-stu-id="99706-341">Add the following code to the `ClassifyImages()` method for the predictions and to convert the `predictions` `IDataView` into an `IEnumerable` for pairing and display:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Predict)]

<span data-ttu-id="99706-342">Fügen Sie zum Koppeln und Anzeigen Ihrer Testbilddaten und Vorhersagen den folgenden Code zum Aufrufen der zuvor erstellten `DisplayResults()`-Methode als nächste Zeile der `ClassifyImages()`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="99706-342">To pair and display your test image data and predictions, add the following code to call the `DisplayResults()` method previously created as the next line in the `ClassifyImages()` method:</span></span>

[!code-csharp[CallDisplayResults2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults2)]

## <a name="classify-a-single-image-with-a-loaded-model"></a><span data-ttu-id="99706-343">Klassifizieren eines einzelnen Bilds mit einem geladenen Modell</span><span class="sxs-lookup"><span data-stu-id="99706-343">Classify a single image with a loaded model</span></span>

<span data-ttu-id="99706-344">Fügen Sie den folgenden Aufruf der `ClassifySingleImage()`-Methode der `Main`-Methode als nächste Codezeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="99706-344">Add the following call to the `ClassifySingleImage()` method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallClassifySingleImage](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifySingleImage)]

<span data-ttu-id="99706-345">Die `ClassifySingleImage()`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="99706-345">The `ClassifySingleImage()` method executes the following tasks:</span></span>

* <span data-ttu-id="99706-346">Laden einer `ImageData`-Instanz.</span><span class="sxs-lookup"><span data-stu-id="99706-346">Loads an `ImageData` instance.</span></span>
* <span data-ttu-id="99706-347">Vorhersagen der Bildklassifizierung anhand von Testdaten.</span><span class="sxs-lookup"><span data-stu-id="99706-347">Predicts image classification based on test data.</span></span>

<span data-ttu-id="99706-348">Erstellen Sie die `ClassifySingleImage()`-Methode mithilfe des folgenden Codes unmittelbar nach der `ClassifyImages()`-Methode und direkt vor der `PairAndDisplayResults()`-Methode:</span><span class="sxs-lookup"><span data-stu-id="99706-348">Create the `ClassifySingleImage()` method, just after the `ClassifyImages()` method and just before the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static void ClassifySingleImage(MLContext mlContext, string imagePath, string outputModelLocation, ITransformer model)
{

}
```

<span data-ttu-id="99706-349">Erstellen Sie zunächst eine `ImageData`-Klasse, die den vollqualifizierten Pfad und Bilddateinamen für den einzelnen `ImagePath` enthält.</span><span class="sxs-lookup"><span data-stu-id="99706-349">First, create an `ImageData` class that contains the fully qualified path and image file name for the single `ImagePath`.</span></span> <span data-ttu-id="99706-350">Fügen Sie der `ClassifySingleImage()`-Methode folgenden Code als nächste Zeilen hinzu:</span><span class="sxs-lookup"><span data-stu-id="99706-350">Add the following code as the next  lines in the `ClassifySingleImage()` method:</span></span>

[!code-csharp[LoadImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadImageData)]

<span data-ttu-id="99706-351">Die [PredictionEngine-Klasse](xref:Microsoft.ML.PredictionEngine%602) ist eine komfortable API, die eine Vorhersage für eine einzelne Dateninstanz ausführt.</span><span class="sxs-lookup"><span data-stu-id="99706-351">The [PredictionEngine class](xref:Microsoft.ML.PredictionEngine%602) is a convenience API that performs a prediction on a single instance of data.</span></span> <span data-ttu-id="99706-352">Die [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A)-Funktion trifft eine Vorhersage für eine einzelne Datenspalte.</span><span class="sxs-lookup"><span data-stu-id="99706-352">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single column of data.</span></span> <span data-ttu-id="99706-353">Übergeben Sie `imageData` an die `PredictionEngine`, um die Bildkategorie vorherzusagen, indem Sie `ClassifySingleImage()` den folgenden Code hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="99706-353">Pass `imageData` to the `PredictionEngine` to predict the image category by adding the following code to `ClassifySingleImage()`:</span></span>

[!code-csharp[PredictSingle](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#PredictSingle)]

<span data-ttu-id="99706-354">Zeigen Sie das Vorhersageergebnis als nächste Codezeile in der `ClassifySingleImage()`-Methode an:</span><span class="sxs-lookup"><span data-stu-id="99706-354">Display the prediction result as the next line of code in the `ClassifySingleImage()` method:</span></span>

[!code-csharp[DisplayPrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPrediction)]

## <a name="results"></a><span data-ttu-id="99706-355">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="99706-355">Results</span></span>

<span data-ttu-id="99706-356">Nachdem Sie die vorherigen Schritte durchgeführt haben, führen Sie die Konsolen-App aus (STRG+F5).</span><span class="sxs-lookup"><span data-stu-id="99706-356">After following the previous steps, run your console app (Ctrl + F5).</span></span> <span data-ttu-id="99706-357">Ihre Ergebnisse sollten der folgenden Ausgabe ähneln.</span><span class="sxs-lookup"><span data-stu-id="99706-357">Your results should be similar to the following output.</span></span>  <span data-ttu-id="99706-358">Möglicherweise werden Warnungen oder Verarbeitungsnachrichten angezeigt. Diese wurden jedoch aus Gründen der Übersichtlichkeit aus den folgenden Ergebnissen entfernt.</span><span class="sxs-lookup"><span data-stu-id="99706-358">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

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
=============== Making classifications ===============
Image: broccoli.png predicted as: food with score: 0.905548
Image: pizza3.jpg predicted as: food with score: 0.9709008
Image: teddy6.jpg predicted as: toy with score: 0.9750155
=============== Making single image classification ===============
Image: toaster3.jpg predicted as: appliance with score: 0.9625379

C:\Program Files\dotnet\dotnet.exe (process 4304) exited with code 0.
Press any key to close this window . . .
```

<span data-ttu-id="99706-359">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="99706-359">Congratulations!</span></span> <span data-ttu-id="99706-360">Sie haben nun durch Wiederverwenden eines vortrainierten `TensorFlow`-Modells in ML.NET erfolgreich ein Machine Learning-Modell für die Bildklassifizierung erstellt.</span><span class="sxs-lookup"><span data-stu-id="99706-360">You've now successfully built a machine learning model for image classification by reusing a pre-trained `TensorFlow` model in ML.NET.</span></span>

<span data-ttu-id="99706-361">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).</span><span class="sxs-lookup"><span data-stu-id="99706-361">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span>

<span data-ttu-id="99706-362">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="99706-362">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="99706-363">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="99706-363">Understand the problem</span></span>
> * <span data-ttu-id="99706-364">Wiederverwenden und Optimieren des vortrainierten Modells</span><span class="sxs-lookup"><span data-stu-id="99706-364">Reuse and tune the pre-trained model</span></span>
> * <span data-ttu-id="99706-365">Klassifizieren von Bildern mit einem geladenen Modell</span><span class="sxs-lookup"><span data-stu-id="99706-365">Classify images with a loaded model</span></span>

<span data-ttu-id="99706-366">Sehen Sie sich im GitHub-Repository für Machine Learning-Beispiele nach einem Beispiel für erweiterte Bildklassifizierung um, damit Sie es untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="99706-366">Check out the Machine Learning samples GitHub repository to explore an expanded image classification sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="99706-367">dotnet/machinelearning-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="99706-367">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/)
