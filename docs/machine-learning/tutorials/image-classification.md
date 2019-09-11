---
title: 'Tutorial: Erneutes Trainieren der TensorFlow-Bildklassifizierung: Übertragungslernen'
description: Erfahren Sie, wie ein TensorFlow-Modell für die Bildklassifizierung mit Übertragungslernen und ML.NET neu trainieren. Das ursprüngliche Modell war so trainiert, dass es einzelne Bilder klassifizieren konnte. Nach dem erneuten Training ordnet das neue Modell die Bilder in allgemeine Kategorien ein.
ms.date: 07/09/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: 65f94fa5e725703d79d0dddae761cbfbc3f89e0e
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804761"
---
# <a name="tutorial-retrain-a-tensorflow-image-classifier-with-transfer-learning-and-mlnet"></a><span data-ttu-id="b37db-105">Tutorial: Erneutes Trainieren einer TensorFlow-Bildklassifizierung mit Übertragungslernen und ML.NET</span><span class="sxs-lookup"><span data-stu-id="b37db-105">Tutorial: Retrain a TensorFlow image classifier with transfer learning and ML.NET</span></span>

<span data-ttu-id="b37db-106">Erfahren Sie, wie ein TensorFlow-Modell für die Bildklassifizierung mit Übertragungslernen und ML.NET neu trainieren.</span><span class="sxs-lookup"><span data-stu-id="b37db-106">Learn how to retrain an image classification TensorFlow model with transfer learning and ML.NET.</span></span> <span data-ttu-id="b37db-107">Das ursprüngliche Modell war so trainiert, dass es einzelne Bilder klassifizieren konnte.</span><span class="sxs-lookup"><span data-stu-id="b37db-107">The original model was trained to classify individual images.</span></span> <span data-ttu-id="b37db-108">Nach dem erneuten Training ordnet das neue Modell die Bilder in allgemeine Kategorien ein.</span><span class="sxs-lookup"><span data-stu-id="b37db-108">After retraining, the new model organizes the images into broad categories.</span></span> 

<span data-ttu-id="b37db-109">Das von Grund auf neue Trainieren eines Modells zur [Bildklassifizierung](https://en.wikipedia.org/wiki/Outline_of_object_recognition) erfordert das Einstellen von Millionen von Parametern, zahlreiche bezeichnete Trainingsdaten und eine große Menge an Computeressourcen (Hunderte von GPU-Stunden).</span><span class="sxs-lookup"><span data-stu-id="b37db-109">Training an [Image Classification](https://en.wikipedia.org/wiki/Outline_of_object_recognition) model from scratch requires setting millions of parameters, a ton of labeled training data and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="b37db-110">Transfer Learning ist zwar nicht so effektiv wie das von Grund auf neue Trainieren eines benutzerdefinierten Modells, doch damit können Sie diesen Prozess durch die Arbeit mit Tausenden von Bildern im Vergleich zur Arbeit mit Millionen bezeichneter Bilder abkürzen und relativ schnell ein benutzerdefiniertes Modell erstellen (innerhalb einer Stunde auf einem Computer ohne eine GPU).</span><span class="sxs-lookup"><span data-stu-id="b37db-110">While not as effective as training a custom model from scratch, transfer learning allows you to shortcut this process by working with thousands of images vs. millions of labeled images and build a customized model fairly quickly (within an hour on a machine without a GPU).</span></span>

<span data-ttu-id="b37db-111">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="b37db-111">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="b37db-112">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="b37db-112">Understand the problem</span></span>
> * <span data-ttu-id="b37db-113">Wiederverwenden und Optimieren des vortrainierten Modells</span><span class="sxs-lookup"><span data-stu-id="b37db-113">Reuse and tune the pre-trained model</span></span>
> * <span data-ttu-id="b37db-114">Klassifizieren von Bildern</span><span class="sxs-lookup"><span data-stu-id="b37db-114">Classify Images</span></span>

## <a name="what-is-transfer-learning"></a><span data-ttu-id="b37db-115">Was ist Übertragungslernen?</span><span class="sxs-lookup"><span data-stu-id="b37db-115">What is transfer learning?</span></span>

<span data-ttu-id="b37db-116">Was wäre, wenn Sie ein zum Lösen eines ähnlichen Problems bereits vortrainiertes Modell wiederverwenden und entweder alle oder einige Ebenen dieses Modells neu trainieren könnten, damit es Ihr Problem löst?</span><span class="sxs-lookup"><span data-stu-id="b37db-116">What if you could reuse a model that's already been pre trained to solve a similar problem and retrain either all or some of the layers of that model to make it solve your problem?</span></span> <span data-ttu-id="b37db-117">Dieses Verfahren der erneuten Nutzung eines Teils eines bereits trainierten Modells zum Erstellen eines neuen Modells wird als [Transfer Learning](https://en.wikipedia.org/wiki/Transfer_learning) (Übertragungslernen) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b37db-117">This technique of reusing part of an already trained model to build a new model is known as [transfer learning](https://en.wikipedia.org/wiki/Transfer_learning).</span></span>

## <a name="image-classification-sample-overview"></a><span data-ttu-id="b37db-118">Übersicht über das Bildklassifizierungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="b37db-118">Image classification sample overview</span></span>

<span data-ttu-id="b37db-119">Das Beispiel ist eine Konsolenanwendung, die ML.NET verwendet, um eine Bildklassifizierung mittels Wiederverwendung eines vortrainierten Modells zum Klassifizieren von Bildern mit einer kleinen Menge von Trainingsdaten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b37db-119">The sample is a console application that uses ML.NET to build an image classifier by reusing a pre-trained model to classify images with a small amount of training data.</span></span>

<span data-ttu-id="b37db-120">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).</span><span class="sxs-lookup"><span data-stu-id="b37db-120">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span> <span data-ttu-id="b37db-121">Hinweis: Die .NET-Projektkonfiguration, die für dieses Tutorial verwendet wird, ist standardmäßig auf .NET Core 2.2 ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="b37db-121">Note that by default, the .NET project configuration for this tutorial targets .NET core 2.2.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b37db-122">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="b37db-122">Prerequisites</span></span>

* <span data-ttu-id="b37db-123">[Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="b37db-123">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span> 

* <span data-ttu-id="b37db-124">Microsoft.ML 1.0.0 NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="b37db-124">Microsoft.ML 1.0.0 Nuget package</span></span>
* <span data-ttu-id="b37db-125">Microsoft.ML.ImageAnalytics 1.0.0 NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="b37db-125">Microsoft.ML.ImageAnalytics 1.0.0 Nuget package</span></span>
* <span data-ttu-id="b37db-126">Microsoft.ML.TensorFlow 0.12.0 NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="b37db-126">Microsoft.ML.TensorFlow 0.12.0 Nuget package</span></span>

* [<span data-ttu-id="b37db-127">Die ZIP-Datei mit dem Tutorialassetsverzeichnis </span><span class="sxs-lookup"><span data-stu-id="b37db-127">The tutorial assets directory .ZIP file</span></span>](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip)

* [<span data-ttu-id="b37db-128">Das Machine Learning-Modell von InceptionV1</span><span class="sxs-lookup"><span data-stu-id="b37db-128">The InceptionV1 machine learning model</span></span>](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="b37db-129">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="b37db-129">Select the appropriate machine learning task</span></span>

<span data-ttu-id="b37db-130">[Deep Learning](https://en.wikipedia.org/wiki/Deep_learning) ist eine Teilmenge von Machine Learning, die Bereiche wie maschinelles Sehen und Spracherkennung revolutioniert.</span><span class="sxs-lookup"><span data-stu-id="b37db-130">[Deep learning](https://en.wikipedia.org/wiki/Deep_learning) is a subset of Machine Learning, which is revolutionizing areas like Computer Vision and Speech Recognition.</span></span>

<span data-ttu-id="b37db-131">Deep Learning-Modelle werden mithilfe großer Mengen [bezeichneter Daten](https://en.wikipedia.org/wiki/Labeled_data) und [neuronaler Netze](https://en.wikipedia.org/wiki/Artificial_neural_network) trainiert, die mehrere Lernebenen enthalten.</span><span class="sxs-lookup"><span data-stu-id="b37db-131">Deep learning models are trained by using large sets of [labeled data](https://en.wikipedia.org/wiki/Labeled_data) and [neural networks](https://en.wikipedia.org/wiki/Artificial_neural_network) that contain multiple learning layers.</span></span> <span data-ttu-id="b37db-132">Deep Learning:</span><span class="sxs-lookup"><span data-stu-id="b37db-132">Deep learning:</span></span>

* <span data-ttu-id="b37db-133">Bietet bei einigen Aufgaben eine bessere Leistung als maschinelles Sehen.</span><span class="sxs-lookup"><span data-stu-id="b37db-133">Performs better on some tasks like Computer Vision.</span></span>

* <span data-ttu-id="b37db-134">Bietet gute Leistungen bei großen Datenmengen.</span><span class="sxs-lookup"><span data-stu-id="b37db-134">Performs well on huge data amounts.</span></span>

<span data-ttu-id="b37db-135">Bildklassifizierung ist eine gängige Machine Learning-Aufgabe, mit der automatisch Bilder in mehrere Kategorien klassifiziert werden können, z.B.:</span><span class="sxs-lookup"><span data-stu-id="b37db-135">Image Classification is a common Machine Learning task that allows us to automatically classify images into multiple categories such as:</span></span>

* <span data-ttu-id="b37db-136">Erkennen, ob ein Bild ein menschliches Gesicht enthält oder nicht.</span><span class="sxs-lookup"><span data-stu-id="b37db-136">Detecting a human face in an image or not.</span></span>
* <span data-ttu-id="b37db-137">Unterscheiden zwischen Katzen und Hunden.</span><span class="sxs-lookup"><span data-stu-id="b37db-137">Detecting Cats vs. dogs.</span></span>

 <span data-ttu-id="b37db-138">Es lässt sich auch wie in den folgenden Bildern bestimmen, ob ein Bild ein Lebensmittel, ein Spielzeug oder ein Gerät zeigt:</span><span class="sxs-lookup"><span data-stu-id="b37db-138">Or as in the following images determining if an image is a(n)  food, toy, or appliance:</span></span>

<span data-ttu-id="b37db-139">![Pizzabild](./media/image-classification/220px-Pepperoni_pizza.jpg)
![Teddybärbild](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![Toasterbild](./media/image-classification/193px-Broodrooster.jpg)</span><span class="sxs-lookup"><span data-stu-id="b37db-139">![pizza image](./media/image-classification/220px-Pepperoni_pizza.jpg)
![teddy bear image](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![toaster image](./media/image-classification/193px-Broodrooster.jpg)</span></span>

>[!Note]
> <span data-ttu-id="b37db-140">Die vorherigen Abbildungen stammen aus Wikimedia-Commons und unterliegen folgendem Urheberrecht:</span><span class="sxs-lookup"><span data-stu-id="b37db-140">The preceding images belong to Wikimedia Commons and are attributed as follows:</span></span>
>
> * <span data-ttu-id="b37db-141">„220px-Pepperoni_pizza.jpg“ Public Domain https://commons.wikimedia.org/w/index.php?curid=79505,</span><span class="sxs-lookup"><span data-stu-id="b37db-141">"220px-Pepperoni_pizza.jpg" Public Domain, https://commons.wikimedia.org/w/index.php?curid=79505,</span></span>
> * <span data-ttu-id="b37db-142">„119px-Nalle_-_a_small_brown_teddy_bear.jpg“ von [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) – selbst fotografiert, CC-BY-SA-2.0, https://commons.wikimedia.org/w/index.php?curid=48166.</span><span class="sxs-lookup"><span data-stu-id="b37db-142">"119px-Nalle_-_a_small_brown_teddy_bear.jpg" By [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - Self-photographed, CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166.</span></span>
> * <span data-ttu-id="b37db-143">„193px-Broodrooster.jpg“ von [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) – eigenes Werk, CC-BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403</span><span class="sxs-lookup"><span data-stu-id="b37db-143">"193px-Broodrooster.jpg" By [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - Own work, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403</span></span>

<span data-ttu-id="b37db-144">Transfer Learning umfasst einige Strategien wie z.B. *erneutes Trainieren aller Ebenen* und die *vorletzte Ebene*.</span><span class="sxs-lookup"><span data-stu-id="b37db-144">Transfer learning includes a few strategies, such as *retrain all layers* and *penultimate layer*.</span></span> <span data-ttu-id="b37db-145">In diesem Tutorial wird die Verwendung der *Strategie der vorletzten Ebene* erläutert und veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b37db-145">This tutorial will explain and show how to use the *penultimate layer strategy*.</span></span> <span data-ttu-id="b37db-146">Die *Strategie der vorletzten Ebene* verwendet ein Modell erneut, das bereits vortrainiert wurde, um ein bestimmtes Problem zu lösen.</span><span class="sxs-lookup"><span data-stu-id="b37db-146">The *penultimate layer strategy* reuses a model that's already been pre-trained to solve a specific problem.</span></span> <span data-ttu-id="b37db-147">Die Strategie trainiert dann die letzte Ebene dieses Modells erneut, um ein neues Problem zu lösen.</span><span class="sxs-lookup"><span data-stu-id="b37db-147">The strategy then retrains the final layer of that model to make it solve a new problem.</span></span> <span data-ttu-id="b37db-148">Aus dem Wiederverwenden des vortrainierten Modells als Teil des neuen Modells resultiert eine erhebliche Zeit- und Ressourcenersparnis.</span><span class="sxs-lookup"><span data-stu-id="b37db-148">Reusing the pre-trained model as part of your new model will save significant time and resources.</span></span>

<span data-ttu-id="b37db-149">Ihr Bildklassifizierungsmodell verwendet das [Inception-Modell](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) erneut, ein gängiges, am `ImageNet`-Dataset trainiertes Bilderkennungsmodell, in dem das TensorFlow-Modell versucht, ganze Bilder in Tausenden von Klassen wie „Regenschirm“, „Jersey“ und „Spülmaschine“ zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="b37db-149">Your image classification model reuses the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), a popular image recognition model trained on the `ImageNet` dataset where the TensorFlow model tries to classify entire images into a thousand classes, like “Umbrella”, “Jersey”, and “Dishwasher”.</span></span>

<span data-ttu-id="b37db-150">Das `Inception v1 model` kann als [Deep Convolutional Neural Network](https://en.wikipedia.org/wiki/Convolutional_neural_network) (tiefes faltendes neuronales Netzwerk) klassifiziert werden und kann eine angemessene Leistung bei schwierigen visuellen Erkennungsaufgaben erzielen, die in einigen Bereichen dem menschlichen Leistungsvermögen ebenbürtig ist oder es überschreitet.</span><span class="sxs-lookup"><span data-stu-id="b37db-150">The `Inception v1 model` can be classified as a [deep convolutional neural network](https://en.wikipedia.org/wiki/Convolutional_neural_network) and can achieve reasonable performance on hard visual recognition tasks, matching or exceeding human performance in some domains.</span></span> <span data-ttu-id="b37db-151">Das Modell / der Algorithmus wurde von mehreren Forschern entwickelt und basiert auf der ursprünglichen Arbeit: [„Rethinking the Inception Architecture for Computer Vision“ von Szegedy, et al.](https://arxiv.org/abs/1512.00567) (Neuer Ansatz der Inception-Architektur für maschinelles Sehen)</span><span class="sxs-lookup"><span data-stu-id="b37db-151">The model/algorithm was developed by multiple researchers and based on the original paper: ["Rethinking the Inception Architecture for Computer Vision” by Szegedy, et. al.](https://arxiv.org/abs/1512.00567)</span></span>

<span data-ttu-id="b37db-152">Da das `Inception model` bereits anhand von Tausenden anderer Bilder vortrainiert wurde, enthält es die zur Bildidentifizierung erforderlichen [Bildfeatures](https://en.wikipedia.org/wiki/Feature_(computer_vision)).</span><span class="sxs-lookup"><span data-stu-id="b37db-152">Because the `Inception model` has already been pre trained on thousands of different images, it contains the [image features](https://en.wikipedia.org/wiki/Feature_(computer_vision)) needed for image identification.</span></span> <span data-ttu-id="b37db-153">Die unteren Bildfeatureebenen erkennen einfache Features (z.B. Kanten), und die höheren Ebenen erkennen komplexere Features (z.B. Formen).</span><span class="sxs-lookup"><span data-stu-id="b37db-153">The lower image feature layers recognize simple features (such as edges) and the higher layers recognize more complex features (such as shapes).</span></span> <span data-ttu-id="b37db-154">Die letzte Ebene wird anhand einer viel kleinerer Menge von Daten trainiert, da Sie mit einem vortrainierten Modell beginnen, das bereits weiß, wie Bilder klassifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="b37db-154">The final layer is trained against a much smaller set of data because you're starting with a pre trained model that already understands how to classify images.</span></span> <span data-ttu-id="b37db-155">Da Sie mit Ihrem Modell mehr als zwei Kategorien klassifizieren können, ist dies ein Beispiel für eine [Multiklassenklassifizierung](../resources/tasks.md#multiclass-classification).</span><span class="sxs-lookup"><span data-stu-id="b37db-155">As your model allows you to classify more than two categories, this is an example of a [multi-class classifier](../resources/tasks.md#multiclass-classification).</span></span> 

<span data-ttu-id="b37db-156">`TensorFlow` ist ein gängiges Deep Learning- und Machine Learning-Toolkit, das das Trainieren von Deep Neural Networks (und allgemeine numerische Berechnungen) ermöglicht, und wird als `transformer` in ML.NET implementiert.</span><span class="sxs-lookup"><span data-stu-id="b37db-156">`TensorFlow` is a popular deep learning and machine learning toolkit that enables training deep neural networks (and general numeric computations), and is implemented as a `transformer` in ML.NET.</span></span> <span data-ttu-id="b37db-157">Für dieses Tutorial dient es zum Wiederverwenden des `Inception model`.</span><span class="sxs-lookup"><span data-stu-id="b37db-157">For this tutorial, it's used to reuse the `Inception model`.</span></span>

<span data-ttu-id="b37db-158">Wie im folgenden Diagramm dargestellt, fügen Sie einen Verweis auf die ML.NET-NuGet-Pakete in Ihrer .NET Core- oder .NET Framework-Anwendung hinzu.</span><span class="sxs-lookup"><span data-stu-id="b37db-158">As shown in the following diagram, you add a reference to the ML.NET NuGet packages in your .NET Core or .NET Framework applications.</span></span> <span data-ttu-id="b37db-159">Im Hintergrund enthält ML.NET die native `TensorFlow`-Bibliothek, mit der Sie Code schreiben können, der eine vorhandene trainierte `TensorFlow`-Modelldatei für die Bewertung lädt, und verweist darauf.</span><span class="sxs-lookup"><span data-stu-id="b37db-159">Under the covers, ML.NET includes and references the native `TensorFlow` library that allows you to write code that loads an existing trained `TensorFlow` model file for scoring.</span></span>  

![TensorFlow-Transformation – ML.NET Arch-Diagramm](./media/image-classification/tensorflow-mlnet.png)

<span data-ttu-id="b37db-161">Das `Inception model` ist darauf trainiert, Bilder in tausend Kategorien zu klassifizieren, jedoch müssen Sie Bilder in eine kleinere Kategoriegruppe und nur in diese Kategorien klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="b37db-161">The `Inception model` is trained to classify images into a thousand categories, but you need to classify images in a smaller category set, and only those categories.</span></span> <span data-ttu-id="b37db-162">Geben Sie den `transfer`-Teil von `transfer learning` ein.</span><span class="sxs-lookup"><span data-stu-id="b37db-162">Enter the `transfer` part of `transfer learning`.</span></span> <span data-ttu-id="b37db-163">Sie können die Fähigkeit des `Inception model` zum Erkennen und Klassifizieren von Bildern auf die neuen begrenzten Kategorien Ihrer benutzerdefinierten Bildklassifizierung übertragen.</span><span class="sxs-lookup"><span data-stu-id="b37db-163">You can transfer the `Inception model`'s ability to recognize and classify images to the new limited categories of your custom image classifier.</span></span>  

 <span data-ttu-id="b37db-164">Sie werden die letzte Ebene dieses Modells mit einem Satz von drei Kategorien neu trainieren:</span><span class="sxs-lookup"><span data-stu-id="b37db-164">You're going to retrain the final layer of that model using a set of three categories:</span></span>

* <span data-ttu-id="b37db-165">Lebensmittel</span><span class="sxs-lookup"><span data-stu-id="b37db-165">Food</span></span>
* <span data-ttu-id="b37db-166">Spielzeug</span><span class="sxs-lookup"><span data-stu-id="b37db-166">Toy</span></span>
* <span data-ttu-id="b37db-167">Gerät</span><span class="sxs-lookup"><span data-stu-id="b37db-167">Appliance</span></span>

<span data-ttu-id="b37db-168">Ihre Ebene verwendet einen [Algorithmus für multinomiale logistische Regression](https://en.wikipedia.org/wiki/Multinomial_logistic_regression), um so schnell wie möglich die richtige Kategorie zu finden.</span><span class="sxs-lookup"><span data-stu-id="b37db-168">Your layer uses a [multinomial logistic regression algorithm](https://en.wikipedia.org/wiki/Multinomial_logistic_regression) to find the correct category as quickly as possible.</span></span> <span data-ttu-id="b37db-169">Dieser Algorithmus verwendet zur Klassifizierung Wahrscheinlichkeiten, um die Antwort zu bestimmen, wobei der richtigen Kategorie der Wert 1 und den anderen der Wert 0 zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b37db-169">This algorithm classifies using probabilities to determine the answer, giving a one value to the correct category and a zero value to the others.</span></span>  

### <a name="dataset"></a><span data-ttu-id="b37db-170">Dataset</span><span class="sxs-lookup"><span data-stu-id="b37db-170">DataSet</span></span>

<span data-ttu-id="b37db-171">Es gibt zwei Datenquellen: die `.tsv`-Datei und die Bilddateien.</span><span class="sxs-lookup"><span data-stu-id="b37db-171">There are two data sources: the `.tsv` file, and the image files.</span></span>  <span data-ttu-id="b37db-172">Die `tags.tsv`-Datei enthält zwei Spalten: die erste ist als `ImagePath` definiert und die zweite das `Label` für das Bild.</span><span class="sxs-lookup"><span data-stu-id="b37db-172">The `tags.tsv` file contains two columns: the first one is defined as `ImagePath` and the second one is the `Label` corresponding to the image.</span></span> <span data-ttu-id="b37db-173">Die folgende Beispieldatei verfügt nicht über eine Kopfzeile und sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="b37db-173">The following example file doesn't have a header row, and looks like this:</span></span>

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

<span data-ttu-id="b37db-174">Die Trainings- und Testbilder befinden sich in dem Assetsordner, den Sie in einer ZIP-Datei herunterladen.</span><span class="sxs-lookup"><span data-stu-id="b37db-174">The training and testing images are located in the assets folders that you'll download in a zip file.</span></span> <span data-ttu-id="b37db-175">Diese Bilder gehören zu Wikimedia Commons.</span><span class="sxs-lookup"><span data-stu-id="b37db-175">These images belong to Wikimedia Commons.</span></span>
> <span data-ttu-id="b37db-176">*[Wikimedia-Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), das Repository für kostenlose Medien.*</span><span class="sxs-lookup"><span data-stu-id="b37db-176">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), the free media repository.*</span></span> <span data-ttu-id="b37db-177">Abgerufen am 17. Oktober 2018 um 10:48 Uhr aus:</span><span class="sxs-lookup"><span data-stu-id="b37db-177">Retrieved 10:48, October 17, 2018 from:</span></span>  
> https://commons.wikimedia.org/wiki/Pizza  
> https://commons.wikimedia.org/wiki/Toaster  
> https://commons.wikimedia.org/wiki/Teddy_bear  

## <a name="create-a-console-application"></a><span data-ttu-id="b37db-178">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="b37db-178">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="b37db-179">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="b37db-179">Create a project</span></span>

1. <span data-ttu-id="b37db-180">Erstellen Sie eine **.NET Core-Konsolenanwendung** mit dem Namen „TransferLearningTF“.</span><span class="sxs-lookup"><span data-stu-id="b37db-180">Create a **.NET Core Console Application** called "TransferLearningTF".</span></span>

2. <span data-ttu-id="b37db-181">Installieren des **Microsoft.ML NuGet-Pakets**:</span><span class="sxs-lookup"><span data-stu-id="b37db-181">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="b37db-182">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="b37db-182">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="b37db-183">Wählen Sie „nuget.org“ als Paketquelle aus, wählen Sie die Registerkarte „Durchsuchen“ aus, und suchen Sie nach **Microsoft.ML**.</span><span class="sxs-lookup"><span data-stu-id="b37db-183">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**.</span></span> <span data-ttu-id="b37db-184">Klicken Sie auf die **Version**-Dropdownliste, wählen Sie das **1.0.0**-Paket in der Liste und dann die Schaltfläche **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="b37db-184">Click on the **Version** drop-down, select the **1.0.0** package in the list, and select the **Install** button.</span></span> <span data-ttu-id="b37db-185">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="b37db-185">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="b37db-186">Wiederholen Sie diese Schritte für **Microsoft.ML.ImageAnalytics v1.0.0** und **Microsoft.ML.TensorFlow v0.12.0**.</span><span class="sxs-lookup"><span data-stu-id="b37db-186">Repeat these steps for **Microsoft.ML.ImageAnalytics v1.0.0** and **Microsoft.ML.TensorFlow v0.12.0**.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="b37db-187">Vorbereiten Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="b37db-187">Prepare your data</span></span>

1. <span data-ttu-id="b37db-188">Laden Sie [die ZIP-Datei des Projektassetverzeichnisses](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip) herunter, und entzippen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="b37db-188">Download [The project assets directory zip file](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip), and unzip.</span></span>

2. <span data-ttu-id="b37db-189">Kopieren Sie das `assets`-Verzeichnis in Ihr *TransferLearningTF*-Projektverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="b37db-189">Copy the `assets` directory into your *TransferLearningTF* project directory.</span></span> <span data-ttu-id="b37db-190">Dieses Verzeichnis und seine Unterverzeichnisse enthalten die für dieses Tutorial erforderlichen Daten und Unterstützungsdateien (mit Ausnahme des Inception-Modells, das Sie im nächsten Schritt herunterladen und hinzufügen).</span><span class="sxs-lookup"><span data-stu-id="b37db-190">This directory and its subdirectories contain the data and support files (except for the Inception model, which you'll download and add in the next step) needed for this tutorial.</span></span>

3. <span data-ttu-id="b37db-191">Laden Sie das [Inception-Modell](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) herunter, und entzippen Sie es.</span><span class="sxs-lookup"><span data-stu-id="b37db-191">Download the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), and unzip.</span></span>

4. <span data-ttu-id="b37db-192">Kopieren Sie den Inhalt des gerade entzippten `inception5h`-Verzeichnisses in Ihr *TransferLearningTF*-Projektverzeichnis `assets\inputs-train\inception`.</span><span class="sxs-lookup"><span data-stu-id="b37db-192">Copy the contents of the `inception5h` directory just unzipped into your *TransferLearningTF* project `assets\inputs-train\inception` directory.</span></span> <span data-ttu-id="b37db-193">Dieses Verzeichnis enthält das Modell und die zusätzlich für dieses Tutorial erforderlichen Unterstützungsdateien wie in der folgenden Abbildung gezeigt:</span><span class="sxs-lookup"><span data-stu-id="b37db-193">This directory contains the model and additional support files needed for this tutorial, as shown in the following image:</span></span>

   ![Inhalt des Inception-Verzeichnisses](./media/image-classification/inception-files.png)

5. <span data-ttu-id="b37db-195">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf alle Dateien im Assetverzeichnis und den Unterverzeichnissen, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="b37db-195">In Solution Explorer, right-click each of the files in the asset directory and subdirectories and select **Properties**.</span></span> <span data-ttu-id="b37db-196">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="b37db-196">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="b37db-197">Erstellen von Klassen und Definieren von Pfaden</span><span class="sxs-lookup"><span data-stu-id="b37db-197">Create classes and define paths</span></span>

<span data-ttu-id="b37db-198">Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="b37db-198">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddUsings)]

<span data-ttu-id="b37db-199">Erstellen Sie globale Felder, die die Pfade zu den verschiedenen Assets enthalten, und globale Variablen für `LabelTokey`, `ImageReal` und `PredictedLabelValue`:</span><span class="sxs-lookup"><span data-stu-id="b37db-199">Create global fields to hold the paths to the various assets, and global variables for the `LabelTokey`,`ImageReal`, and  `PredictedLabelValue`:</span></span>

* <span data-ttu-id="b37db-200">`_assetsPath` enthält den Pfad zu den Assets.</span><span class="sxs-lookup"><span data-stu-id="b37db-200">`_assetsPath` has the path to the assets.</span></span>
* <span data-ttu-id="b37db-201">`_trainTagsTsv` enthält den Pfad zur TSV-Datei mit den Trainingsbilddaten-Tags.</span><span class="sxs-lookup"><span data-stu-id="b37db-201">`_trainTagsTsv` has the path to the training image data tags tsv file.</span></span>
* <span data-ttu-id="b37db-202">`_predictTagsTsv` enthält den Pfad zur TSV-Datei mit den Vorhersagebilddaten-Tags.</span><span class="sxs-lookup"><span data-stu-id="b37db-202">`_predictTagsTsv` has the path to the prediction image data tags tsv file.</span></span>
* <span data-ttu-id="b37db-203">`_trainImagesFolder` enthält den Pfad zu den Bildern, die zum Trainieren des Modells verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b37db-203">`_trainImagesFolder` has the path to the images used to train the model.</span></span>
* <span data-ttu-id="b37db-204">`_predictImagesFolder` enthält den Pfad zu den Bildern, die vom trainierten Modell klassifiziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b37db-204">`_predictImagesFolder` has the path to the images to be classified by the trained model.</span></span>
* <span data-ttu-id="b37db-205">`_inceptionPb` enthält den Pfad zu dem vortrainierten Inception-Modell, das zum erneuten Trainieren Ihres Modells wiederverwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b37db-205">`_inceptionPb` has the path to the pre-trained Inception model to be reused to retrain your model.</span></span>
* <span data-ttu-id="b37db-206">`_inputImageClassifierZip` enthält den Pfad, über den das trainierte Modell geladen wird.</span><span class="sxs-lookup"><span data-stu-id="b37db-206">`_inputImageClassifierZip` has the path where the trained model is loaded from.</span></span>
* <span data-ttu-id="b37db-207">`_outputImageClassifierZip` enthält den Pfad zu dem Speicherort, in dem das trainierte Modell gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="b37db-207">`_outputImageClassifierZip` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="b37db-208">`LabelTokey` ist der einem Schlüssel zugeordnete `Label`-Wert.</span><span class="sxs-lookup"><span data-stu-id="b37db-208">`LabelTokey` is the `Label` value mapped to a key.</span></span>
* <span data-ttu-id="b37db-209">`ImageReal` ist die Spalte, die den vorhergesagten Bildwert enthält.</span><span class="sxs-lookup"><span data-stu-id="b37db-209">`ImageReal`  is the column containing the predicted image value.</span></span>
* <span data-ttu-id="b37db-210">`PredictedLabelValue` ist die Spalte, die den vorhergesagten Bezeichnungswert enthält.</span><span class="sxs-lookup"><span data-stu-id="b37db-210">`PredictedLabelValue` is the column containing the predicted label value.</span></span>

<span data-ttu-id="b37db-211">Fügen Sie den folgenden Code der Zeile direkt über der `Main`-Methode hinzu, um diese Pfade und die anderen Variablen anzugeben:</span><span class="sxs-lookup"><span data-stu-id="b37db-211">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="b37db-212">Erstellen Sie einige Klassen für Ihre Eingabedaten und Vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="b37db-212">Create some classes for your input data, and predictions.</span></span> <span data-ttu-id="b37db-213">Fügen Sie dem Projekt eine neue Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="b37db-213">Add a new class to your project:</span></span>

1. <span data-ttu-id="b37db-214">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="b37db-214">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="b37db-215">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *ImageData.cs*.</span><span class="sxs-lookup"><span data-stu-id="b37db-215">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImageData.cs*.</span></span> <span data-ttu-id="b37db-216">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="b37db-216">Then, select the **Add** button.</span></span>

    <span data-ttu-id="b37db-217">Die Datei *ImageData.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="b37db-217">The *ImageData.cs* file opens in the code editor.</span></span> <span data-ttu-id="b37db-218">Fügen Sie die folgende `using`-Anweisung am Anfang der *ImageData.cs*-Datei hinzu:</span><span class="sxs-lookup"><span data-stu-id="b37db-218">Add the following `using` statement to the top of *ImageData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#AddUsings)]

<span data-ttu-id="b37db-219">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code für die `ImageData`-Klasse der *ImageData.cs*-Datei hinzu:</span><span class="sxs-lookup"><span data-stu-id="b37db-219">Remove the existing class definition and add the following code for the `ImageData` class to the *ImageData.cs* file:</span></span>

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#DeclareTypes)]

<span data-ttu-id="b37db-220">`ImageData` ist die Eingabebilddaten-Klasse mit den folgenden <xref:System.String>-Feldern:</span><span class="sxs-lookup"><span data-stu-id="b37db-220">`ImageData` is the input image data class and has the following <xref:System.String> fields:</span></span>

* <span data-ttu-id="b37db-221">`ImagePath` enthält den Bilddateinamen.</span><span class="sxs-lookup"><span data-stu-id="b37db-221">`ImagePath` contains the image file name.</span></span>
* <span data-ttu-id="b37db-222">`Label` enthält einen Wert für die Bildbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="b37db-222">`Label` contains a value for the image label.</span></span>

<span data-ttu-id="b37db-223">Fügen Sie dem Projekt eine neue Klasse für `ImagePrediction` hinzu:</span><span class="sxs-lookup"><span data-stu-id="b37db-223">Add a new class to your project for `ImagePrediction`:</span></span>

1. <span data-ttu-id="b37db-224">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="b37db-224">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="b37db-225">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *ImagePrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="b37db-225">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImagePrediction.cs*.</span></span> <span data-ttu-id="b37db-226">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="b37db-226">Then, select the **Add** button.</span></span>

    <span data-ttu-id="b37db-227">Die Datei *ImagePrediction.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="b37db-227">The *ImagePrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="b37db-228">Entfernen Sie sowohl die `System.Collections.Generic`- als auch die `System.Text` `using`-Anweisung am Anfang von *ImagePrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="b37db-228">Remove both the `System.Collections.Generic` and the `System.Text` `using` statements at the top of *ImagePrediction.cs*:</span></span>

<span data-ttu-id="b37db-229">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code mit der Klasse `ImagePrediction` der Datei *ImagePrediction.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="b37db-229">Remove the existing class definition and add the following code, which has the `ImagePrediction` class, to the *ImagePrediction.cs* file:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/ImagePrediction.cs#DeclareTypes)]

<span data-ttu-id="b37db-230">`ImagePrediction` ist die Bildvorhersageklasse und hat die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="b37db-230">`ImagePrediction` is the image prediction class and has the following fields:</span></span>

* <span data-ttu-id="b37db-231">`Score` enthält den Zuverlässigkeitsprozentsatz für eine bestimmte Bildklassifizierung.</span><span class="sxs-lookup"><span data-stu-id="b37db-231">`Score` contains the confidence percentage for a given image classification.</span></span>
* <span data-ttu-id="b37db-232">`PredictedLabelValue` enthält einen Wert für die vorhergesagte Bildklassifizierungsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="b37db-232">`PredictedLabelValue` contains a value for the predicted image classification label.</span></span>

<span data-ttu-id="b37db-233">Die `ImagePrediction`-Klasse wird für die Vorhersage verwendet, nachdem das Modell trainiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b37db-233">`ImagePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="b37db-234">Sie besitzt einen `string` (`ImagePath`) für den Bildpfad.</span><span class="sxs-lookup"><span data-stu-id="b37db-234">It has a `string` (`ImagePath`) for the image path.</span></span> <span data-ttu-id="b37db-235">Mit `Label` wird das Modell wiederverwendet und neu trainiert.</span><span class="sxs-lookup"><span data-stu-id="b37db-235">The `Label` is used to reuse and retrain the model.</span></span> <span data-ttu-id="b37db-236">Das `PredictedLabelValue` wird während der Vorhersage und Evaluierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="b37db-236">The `PredictedLabelValue` is used during prediction and evaluation.</span></span> <span data-ttu-id="b37db-237">Für die Evaluierung werden eine Eingabe mit Trainingsdaten, die vorhergesagten Werte und das Modell verwendet.</span><span class="sxs-lookup"><span data-stu-id="b37db-237">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="b37db-238">Die [MLContext-Klasse](xref:Microsoft.ML.MLContext) ist der Startpunkt für alle ML.NET-Vorgänge. Durch das Initialisieren von `mlContext` wird eine neue ML.NET-Umgebung erstellt, die für mehrere Objekte des Modellerstellungsworkflows verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b37db-238">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="b37db-239">Die Klasse ähnelt dem Konzept von `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="b37db-239">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="b37db-240">Initialisieren von Variablen in Main</span><span class="sxs-lookup"><span data-stu-id="b37db-240">Initialize variables in Main</span></span>

<span data-ttu-id="b37db-241">Initialisieren Sie die `mlContext`-Variable mit einer neuen Instanz von `MLContext`.</span><span class="sxs-lookup"><span data-stu-id="b37db-241">Initialize the `mlContext` variable with a new instance of `MLContext`.</span></span>  <span data-ttu-id="b37db-242">Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` mit dem folgenden Code in der `Main`-Methode:</span><span class="sxs-lookup"><span data-stu-id="b37db-242">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CreateMLContext)]

### <a name="create-a-struct-for-default-parameters"></a><span data-ttu-id="b37db-243">Erstellen einer Struktur für Standardparameter</span><span class="sxs-lookup"><span data-stu-id="b37db-243">Create a struct for default parameters</span></span>

<span data-ttu-id="b37db-244">Das Inception-Modell verfügt über mehrere Standardparameter, die Sie übergeben müssen.</span><span class="sxs-lookup"><span data-stu-id="b37db-244">The Inception model has several default parameters you need to pass in.</span></span> <span data-ttu-id="b37db-245">Erstellen Sie unmittelbar nach der `Main()`-Methode eine Struktur, um Anzeigenamen mit dem folgenden Code die Standardparameterwerte zuzuordnen:</span><span class="sxs-lookup"><span data-stu-id="b37db-245">Create a struct to map the default parameter values to friendly names with the following code, just after the `Main()` method:</span></span>

[!code-csharp[InceptionSettings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a><span data-ttu-id="b37db-246">Erstellen einer Anzeigehilfsprogramm-Methode</span><span class="sxs-lookup"><span data-stu-id="b37db-246">Create a display utility method</span></span>

<span data-ttu-id="b37db-247">Da Sie die Bilddaten und die zugehörigen Vorhersagen mehr als einmal anzeigen werden, erstellen Sie eine Anzeigehilfsmethode, um die Anzeige der Bild- und Vorhersageergebnisse zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="b37db-247">Since you'll display the image data and the related predictions more than once, create a display utility method to handle displaying the image and prediction results.</span></span>

<span data-ttu-id="b37db-248">Die `DisplayResults()`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="b37db-248">The `DisplayResults()` method executes the following tasks:</span></span>

* <span data-ttu-id="b37db-249">Anzeigen der vorhergesagten Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="b37db-249">Displays the predicted results.</span></span>

<span data-ttu-id="b37db-250">Erstellen Sie die `DisplayResults()`-Methode mit dem folgenden Code direkt nach der `InceptionSettings`-Struktur:</span><span class="sxs-lookup"><span data-stu-id="b37db-250">Create the `DisplayResults()` method, just after the `InceptionSettings` struct, using the following code:</span></span>

```csharp
private static void DisplayResults(IEnumerable<ImagePrediction> imagePredictionData)
{

}
```

<span data-ttu-id="b37db-251">Der in `ImagePrediction` eingegebene `ImagePath` der `Transform()`-Methode mit den vorhergesagten Feldern.</span><span class="sxs-lookup"><span data-stu-id="b37db-251">The `Transform()` method populated `ImagePath` in `ImagePrediction` along with the predicted fields.</span></span> <span data-ttu-id="b37db-252">Im Laufe des ML.NET-Prozesses fügt jede Komponente Spalten hinzu, sodass die Ergebnisse leicht angezeigt werden können:</span><span class="sxs-lookup"><span data-stu-id="b37db-252">As the ML.NET process progresses, each component adds columns, and this makes it easy to display the results:</span></span>

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPredictions)]

<span data-ttu-id="b37db-253">Sie rufen die `DisplayResults()` -Methode in den zwei Bildklassifizierungsmethoden auf.</span><span class="sxs-lookup"><span data-stu-id="b37db-253">You'll call the `DisplayResults()` method in the two image classification methods.</span></span>

### <a name="create-a-tsv-file-utility-method"></a><span data-ttu-id="b37db-254">Erstellen einer Hilfsprogrammmethode für die TSV-Datei</span><span class="sxs-lookup"><span data-stu-id="b37db-254">Create a .tsv file utility method</span></span>

<span data-ttu-id="b37db-255">Die `ReadFromTsv()`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="b37db-255">The `ReadFromTsv()` method executes the following tasks:</span></span>

* <span data-ttu-id="b37db-256">Lesen der Bilddatendatei `tags.tsv`.</span><span class="sxs-lookup"><span data-stu-id="b37db-256">Reads the image data `tags.tsv` file.</span></span>
* <span data-ttu-id="b37db-257">Hinzufügen des Bildpfads zum Bilddateinamen.</span><span class="sxs-lookup"><span data-stu-id="b37db-257">Adds the file path to the image file name.</span></span>
* <span data-ttu-id="b37db-258">Laden der Dateidaten in ein IEnumerable`ImageData`-Objekt.</span><span class="sxs-lookup"><span data-stu-id="b37db-258">Loads the file data into an IEnumerable`ImageData` object.</span></span>

<span data-ttu-id="b37db-259">Erstellen Sie die `ReadFromTsv()`-Methode mit dem folgenden Code direkt nach der `PairAndDisplayResults()`-Methode:</span><span class="sxs-lookup"><span data-stu-id="b37db-259">Create the `ReadFromTsv()` method, just after the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
{

}
```

<span data-ttu-id="b37db-260">Der folgende Code analysiert die `tags.tsv`-Datei, um den Dateipfad für die `ImagePath`-Eigenschaft dem Namen der Bilddatei hinzuzufügen und ihn und das `Label` in ein `ImageData`-Objekt zu laden.</span><span class="sxs-lookup"><span data-stu-id="b37db-260">The following code parses through the `tags.tsv` file to add the file path to the image file name for the `ImagePath` property and load it and the `Label` into an `ImageData` object.</span></span> <span data-ttu-id="b37db-261">Fügen Sie ihn als erste Zeile der `ReadFromTsv()`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="b37db-261">Add it as the first line of the `ReadFromTsv()` method.</span></span>  <span data-ttu-id="b37db-262">Zum Anzeigen der Vorhersageergebnisse benötigen Sie den vollqualifizierten Dateipfad.</span><span class="sxs-lookup"><span data-stu-id="b37db-262">You need the fully qualified file path to display the prediction results.</span></span>

[!code-csharp[ReadFromTsv](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReadFromTsv)]
<span data-ttu-id="b37db-263">In ML.NET werden die folgenden drei Hauptkonzepte genutzt: [Daten](../resources/glossary.md#data), [Transformatoren](../resources/glossary.md#transformer) und [Kalkulatoren](../resources/glossary.md#estimator).</span><span class="sxs-lookup"><span data-stu-id="b37db-263">There are three major concepts in ML.NET: [Data](../resources/glossary.md#data), [Transformers](../resources/glossary.md#transformer), and [Estimators](../resources/glossary.md#estimator).</span></span>

## <a name="reuse-and-tune-pre-trained-model"></a><span data-ttu-id="b37db-264">Wiederverwenden und Optimieren des vortrainierten Modells</span><span class="sxs-lookup"><span data-stu-id="b37db-264">Reuse and tune pre-trained model</span></span>

<span data-ttu-id="b37db-265">Fügen Sie der `ReuseAndTuneInceptionModel()`-Methode den folgenden Aufruf als nächste Codezeile der `Main()`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="b37db-265">Add the following call to the `ReuseAndTuneInceptionModel()`method as the next line of code in the `Main()` method:</span></span>

[!code-csharp[CallReuseAndTuneInceptionModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReuseAndTuneInceptionModel)]

<span data-ttu-id="b37db-266">Die `ReuseAndTuneInceptionModel()`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="b37db-266">The `ReuseAndTuneInceptionModel()` method executes the following tasks:</span></span>

* <span data-ttu-id="b37db-267">Laden der Daten.</span><span class="sxs-lookup"><span data-stu-id="b37db-267">Loads the data</span></span>
* <span data-ttu-id="b37db-268">Extrahieren und Transformieren der Daten.</span><span class="sxs-lookup"><span data-stu-id="b37db-268">Extracts and transforms the data.</span></span>
* <span data-ttu-id="b37db-269">Bewerten des TensorFlow-Modells.</span><span class="sxs-lookup"><span data-stu-id="b37db-269">Scores the TensorFlow model.</span></span>
* <span data-ttu-id="b37db-270">Optimieren (erneutes Trainieren) des Modells.</span><span class="sxs-lookup"><span data-stu-id="b37db-270">Tunes (retrains) the model.</span></span>
* <span data-ttu-id="b37db-271">Anzeigen von Modellergebnissen.</span><span class="sxs-lookup"><span data-stu-id="b37db-271">Displays model results.</span></span>
* <span data-ttu-id="b37db-272">Auswerten des Modells.</span><span class="sxs-lookup"><span data-stu-id="b37db-272">Evaluates the model.</span></span>
* <span data-ttu-id="b37db-273">Zurückgeben des Modells.</span><span class="sxs-lookup"><span data-stu-id="b37db-273">Returns the model.</span></span>

<span data-ttu-id="b37db-274">Erstellen Sie die `ReuseAndTuneInceptionModel()`-Methode mithilfe des folgenden Codes unmittelbar nach der `InceptionSettings`-Struktur und direkt vor der `DisplayResults()`-Methode:</span><span class="sxs-lookup"><span data-stu-id="b37db-274">Create the `ReuseAndTuneInceptionModel()` method, just after the `InceptionSettings` struct and just before the `DisplayResults()` method, using the following code:</span></span>

```csharp
public static ITransformer ReuseAndTuneInceptionModel(MLContext mlContext, string dataLocation, string imagesFolder, string inputModelLocation, string outputModelLocation)
{

}
```

### <a name="load-the-data"></a><span data-ttu-id="b37db-275">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="b37db-275">Load the data</span></span>

<span data-ttu-id="b37db-276">Daten werden in ML.NET als [IDataView-Klasse](xref:Microsoft.ML.IDataView) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b37db-276">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="b37db-277">Mit `IDataView` können Tabellendaten (Zahlen und Text) flexibel und effizient beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="b37db-277">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="b37db-278">Daten können aus einer Textdatei oder in Echtzeit (z. B. aus einer SQL-Datenbank oder aus Protokolldateien) in ein `IDataView`-Objekt geladen werden.</span><span class="sxs-lookup"><span data-stu-id="b37db-278">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="b37db-279">Laden der Daten mithilfe des `MLContext.Data.LoadFromTextFile`-Wrappers.</span><span class="sxs-lookup"><span data-stu-id="b37db-279">Load the data using the `MLContext.Data.LoadFromTextFile` wrapper.</span></span> <span data-ttu-id="b37db-280">Fügen Sie der `ReuseAndTuneInceptionModel()`-Methode folgenden Code als nächste Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="b37db-280">Add the following code as the next line in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[LoadData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadData "Load the data")]

### <a name="extract-features-and-transform-the-data"></a><span data-ttu-id="b37db-281">Extrahieren von Features und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="b37db-281">Extract Features and transform the data</span></span>

<span data-ttu-id="b37db-282">Vorverarbeitung und Bereinigung von Daten sind wichtige Aufgaben, die durchgeführt werden, bevor ein Dataset effektiv für Machine Learning verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b37db-282">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span>  <span data-ttu-id="b37db-283">Die Verwendung von Daten ohne diese Modellierungsaufgaben kann irreführende Ergebnisse erzeugen.</span><span class="sxs-lookup"><span data-stu-id="b37db-283">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="b37db-284">Machine Learning-Algorithmen verstehen [mit Features ausgestattete](../resources/glossary.md#feature) Daten, und beim Umgang mit Deep Neural Networks müssen Sie die Bilder dem Format anpassen, das vom Netzwerk erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="b37db-284">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, and when dealing with deep neural networks you must adapt the images to the format expected by the network.</span></span> <span data-ttu-id="b37db-285">Dieses Format ist ein [numerischer Vektor](../resources/glossary.md#numerical-feature-vector).</span><span class="sxs-lookup"><span data-stu-id="b37db-285">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="b37db-286">Führen Sie nach Training und Auswertung eine Vorhersage mit den Werten der **Label**-Spalte durch.</span><span class="sxs-lookup"><span data-stu-id="b37db-286">After training and evaluation, predict with the **Label** column values.</span></span> <span data-ttu-id="b37db-287">Da Sie ein vortrainiertes Modell verwenden, ordnen Sie dem neuen Modell Felder mit der [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A)-Methode zu.</span><span class="sxs-lookup"><span data-stu-id="b37db-287">As you're using a pre-trained model, map fields to the new model with the [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) method.</span></span> <span data-ttu-id="b37db-288">Diese Methode wandelt das `Label` in einen numerischen Schlüsseltyp (`LabelTokey`) um und fügt es als neue Datasetspalte hinzu:  Benennen Sie diese mit `estimator`, da Sie ihr auch den Trainer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b37db-288">This method transforms the `Label` into a numeric key type (`LabelTokey`) column and add it as new dataset column:  Name this `estimator` as you'll also add the trainer to it.</span></span> <span data-ttu-id="b37db-289">Fügen Sie die nächste Codezeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="b37db-289">Add the next line of code:</span></span>

[!code-csharp[MapValueToKey1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey1)]

<span data-ttu-id="b37db-290">Ihr Bildverarbeitungsschätzer verwendet vortrainierte [Deep Neural Network (DNN)](https://en.wikipedia.org/wiki/Deep_learning#Deep_neural_networks)-Featurebereitsteller für die Featureextraktion.</span><span class="sxs-lookup"><span data-stu-id="b37db-290">Your image processing estimator uses pre-trained [Deep Neural Network(DNN)](https://en.wikipedia.org/wiki/Deep_learning#Deep_neural_networks) featurizers for feature extraction.</span></span> <span data-ttu-id="b37db-291">Beim Umgang mit Deep Neural Networks passen Sie die Bilder dem vom Netzwerk erwarteten Format an.</span><span class="sxs-lookup"><span data-stu-id="b37db-291">When dealing with deep neural networks, you  adapt the images to the expected network format.</span></span> <span data-ttu-id="b37db-292">Aus diesem Grund verwenden Sie mehrere Bildtransformationen, um die Bilddaten in die vom Modell erwartete Form zu bringen:</span><span class="sxs-lookup"><span data-stu-id="b37db-292">This is the reason you use several image transforms to get the image data into the model's expected form:</span></span>

1. <span data-ttu-id="b37db-293">Die `LoadImages`-Transformationsbilder werden als Bitmaptyp in den Arbeitsspeicher geladen.</span><span class="sxs-lookup"><span data-stu-id="b37db-293">The `LoadImages`transform images are loaded in memory as a Bitmap type.</span></span>
2. <span data-ttu-id="b37db-294">Die `ResizeImages`-Transformation ändert die Größe der Bilder, da Breite und Höhe des Eingabebilds beim vortrainierten Modell definiert sind.</span><span class="sxs-lookup"><span data-stu-id="b37db-294">The `ResizeImages` transform resizes the images as the pre-trained model has a defined input image width and height.</span></span>
3. <span data-ttu-id="b37db-295">Die `ExtractPixels`-Transformation extrahiert die Pixel aus den Eingabebildern und wandelt sie in einen numerischen Vektor um.</span><span class="sxs-lookup"><span data-stu-id="b37db-295">The `ExtractPixels` transform extracts the pixels from the input images and converts them into a numeric vector.</span></span>

<span data-ttu-id="b37db-296">Fügen Sie diese Bildtransformationen als nächste Codezeilen hinzu:</span><span class="sxs-lookup"><span data-stu-id="b37db-296">Add these image transforms as the next lines of code:</span></span>

[!code-csharp[ImageTransforms](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ImageTransforms)]

<span data-ttu-id="b37db-297">Das `LoadTensorFlowModel` ist eine praktische Methode, die es ermöglicht, das `TensorFlow`-Modell einmal zu laden und dann den `TensorFlowEstimator` mit dem `ScoreTensorFlowModel` zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b37db-297">The `LoadTensorFlowModel` is a convenience method that allows the `TensorFlow` model to be loaded once and then creates the `TensorFlowEstimator` using `ScoreTensorFlowModel`.</span></span> <span data-ttu-id="b37db-298">Die `ScoreTensorFlowModel` extrahiert angegebene Ausgaben (die `softmax2_pre_activation` der Bildfeatures des `Inception model`) und bewertet ein Dataset mithilfe des vorab trainierten `TensorFlow`-Modells.</span><span class="sxs-lookup"><span data-stu-id="b37db-298">The `ScoreTensorFlowModel` extracts specified outputs (the `Inception model`'s image features `softmax2_pre_activation`), and scores a dataset using the pre-trained `TensorFlow` model.</span></span>

<span data-ttu-id="b37db-299">`softmax2_pre_activation` unterstützt das Modell mit der Bestimmung, zu welcher Klasse die Bilder gehören.</span><span class="sxs-lookup"><span data-stu-id="b37db-299">`softmax2_pre_activation` assists the model with determining which class the images belongs to.</span></span> <span data-ttu-id="b37db-300">`softmax2_pre_activation` gibt für jede Kategorie eine Wahrscheinlichkeit für ein Bild zurück, und alle diese Wahrscheinlichkeiten müssen 1 ergeben.</span><span class="sxs-lookup"><span data-stu-id="b37db-300">`softmax2_pre_activation` returns a probability for each of the categories for an image, and all of those probabilities must add up to 1.</span></span> <span data-ttu-id="b37db-301">Es wird davon ausgegangen, dass ein Bild nur zu einer einzigen Kategorie gehört, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="b37db-301">It assumes that an image will belong to only one category, as shown in the following example:</span></span>

| <span data-ttu-id="b37db-302">Klasse</span><span class="sxs-lookup"><span data-stu-id="b37db-302">Class</span></span>         | <span data-ttu-id="b37db-303">Wahrscheinlichkeit</span><span class="sxs-lookup"><span data-stu-id="b37db-303">Probability</span></span>   |
| ------------- | ------------- |
| `Food`        |  <span data-ttu-id="b37db-304">0,001</span><span class="sxs-lookup"><span data-stu-id="b37db-304">0.001</span></span>        |
| `Toy`         |  <span data-ttu-id="b37db-305">0,95</span><span class="sxs-lookup"><span data-stu-id="b37db-305">0.95</span></span>         |
| `Appliance`   |  <span data-ttu-id="b37db-306">0,06</span><span class="sxs-lookup"><span data-stu-id="b37db-306">0.06</span></span>         |

<span data-ttu-id="b37db-307">Fügen Sie die `TensorFlowTransform` mit den folgenden Codezeilen dem `estimator` an:</span><span class="sxs-lookup"><span data-stu-id="b37db-307">Append the `TensorFlowTransform` to the `estimator` with the following line of code:</span></span>

[!code-csharp[ScoreTensorFlowModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ScoreTensorFlowModel)]

### <a name="choose-a-training-algorithm"></a><span data-ttu-id="b37db-308">Auswählen eines Trainingsalgorithmus</span><span class="sxs-lookup"><span data-stu-id="b37db-308">Choose a training algorithm</span></span>

<span data-ttu-id="b37db-309">Um den Trainingsalgorithmus hinzuzufügen, rufen Sie die `mlContext.MulticlassClassification.Trainers.LbfgsMaximumEntropy()`-Wrappermethode auf.</span><span class="sxs-lookup"><span data-stu-id="b37db-309">To add the training algorithm, call the `mlContext.MulticlassClassification.Trainers.LbfgsMaximumEntropy()` wrapper method.</span></span>  <span data-ttu-id="b37db-310">[LbfgsMaximumEntropy](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer) wird dem `estimator` angefügt und akzeptiert die Inception-Bildfeatures (`softmax2_pre_activation`) und die `Label`-Eingabeparameter, um aus den historischen Daten zu lernen.</span><span class="sxs-lookup"><span data-stu-id="b37db-310">The [LbfgsMaximumEntropy](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer) is appended to the `estimator` and accepts the Inception image features (`softmax2_pre_activation`) and the `Label` input parameters to learn from the historic data.</span></span>  <span data-ttu-id="b37db-311">Fügen Sie den Trainer mit dem folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="b37db-311">Add the trainer with the following code:</span></span>

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddTrainer)]

<span data-ttu-id="b37db-312">Sie müssen auch das `predictedlabel` dem `predictedlabelvalue` zuordnen:</span><span class="sxs-lookup"><span data-stu-id="b37db-312">You also need to map the `predictedlabel` to the `predictedlabelvalue`:</span></span>

[!code-csharp[MapValueToKey2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey2)]

<span data-ttu-id="b37db-313">Mit der `Fit()`-Methode wird Ihr Modell trainiert, indem das Dataset transformiert und das Training angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="b37db-313">The `Fit()` method trains your model by transforming the dataset and applying the training.</span></span> <span data-ttu-id="b37db-314">Fügen Sie den unten aufgeführten Code als nächste Codezeilen in die `ReuseAndTuneInceptionModel()`-Methode ein, um das Modell an das Trainingsdataset anzupassen und das trainierte Modell zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="b37db-314">Fit the model to the training dataset and return the trained model by adding the following as the next line of code in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TrainModel)]

<span data-ttu-id="b37db-315">Die [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A)-Methode trifft Vorhersagen für mehrere bereitgestellte Eingabezeilen eines Testdatasets.</span><span class="sxs-lookup"><span data-stu-id="b37db-315">The [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method makes predictions for multiple provided input rows of a test dataset.</span></span>  <span data-ttu-id="b37db-316">Fügen Sie `ReuseAndTuneInceptionModel()` den folgenden Code hinzu, um die `Training`-Daten zu transformieren:</span><span class="sxs-lookup"><span data-stu-id="b37db-316">Transform the `Training` data by adding the following code to `ReuseAndTuneInceptionModel()`:</span></span>

[!code-csharp[TransformData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TransformData)]

<span data-ttu-id="b37db-317">Konvertieren Sie Ihre Bilddaten und die Vorhersage-`DataViews` zur Kopplung für eine einfachere Anzeige in stark typisierte `IEnumerables`.</span><span class="sxs-lookup"><span data-stu-id="b37db-317">Convert your image data and prediction `DataViews` into strongly-typed `IEnumerables` to pair for easier display.</span></span> <span data-ttu-id="b37db-318">Verwenden Sie hierzu die `MLContext.CreateEnumerable()`-Methode mit dem folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="b37db-318">Use the `MLContext.CreateEnumerable()` method to do that, using the following code:</span></span>

[!code-csharp[EnumerateDataViews](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#EnumerateDataViews)]

<span data-ttu-id="b37db-319">Rufen Sie die `DisplayResults()`-Methode zum Anzeigen Ihrer Daten und Vorhersagen als nächste Zeile in der `ReuseAndTuneInceptionModel()`-Methode auf:</span><span class="sxs-lookup"><span data-stu-id="b37db-319">Call the `DisplayResults()` method to display your data and predictions as the next line in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[CallDisplayResults1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults1)]

<span data-ttu-id="b37db-320">Nachdem Sie die Vorhersage festgelegt haben, führt die [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A)-Methode Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="b37db-320">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) method:</span></span>

* <span data-ttu-id="b37db-321">Bewerten des Modells (Vergleich der vorhergesagten Werte mit dem tatsächlichen Dataset `Labels`).</span><span class="sxs-lookup"><span data-stu-id="b37db-321">Assesses the model (compares the predicted values with the actual dataset `Labels`).</span></span>

* <span data-ttu-id="b37db-322">Rückgabe der Modellleistungsmetriken.</span><span class="sxs-lookup"><span data-stu-id="b37db-322">Returns the model performance metrics.</span></span>

<span data-ttu-id="b37db-323">Fügen Sie der `ReuseAndTuneInceptionModel()`-Methode folgenden Code als nächste Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="b37db-323">Add the following code to the `ReuseAndTuneInceptionModel()` method as the next line:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Evaluate)]

<span data-ttu-id="b37db-324">Für die Bildklassifizierung werden die folgenden Metriken ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="b37db-324">The following metrics are evaluated for image classification:</span></span>

* <span data-ttu-id="b37db-325">`Log-loss` – siehe [Protokollverlust](../resources/glossary.md#log-loss).</span><span class="sxs-lookup"><span data-stu-id="b37db-325">`Log-loss` - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="b37db-326">Der Protokollverlust sollte so nahe wie möglich bei 0 liegen.</span><span class="sxs-lookup"><span data-stu-id="b37db-326">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="b37db-327">`Per class Log-loss`.</span><span class="sxs-lookup"><span data-stu-id="b37db-327">`Per class Log-loss`.</span></span> <span data-ttu-id="b37db-328">Der Protokollverlust pro Klasse sollte so nahe wie möglich bei 0 liegen.</span><span class="sxs-lookup"><span data-stu-id="b37db-328">You want per class Log-loss to be as close to zero as possible.</span></span>

<span data-ttu-id="b37db-329">Verwenden Sie den folgenden Code, um die Metriken anzuzeigen, die Ergebnisse freizugeben und dann mit ihnen zu arbeiten:</span><span class="sxs-lookup"><span data-stu-id="b37db-329">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayMetrics)]

 <span data-ttu-id="b37db-330">Fügen Sie den folgenden Code hinzu, um das trainierte Modell als nächste Zeile zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="b37db-330">Add the following code to return the trained model as the next line:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReturnModel)]

## <a name="classify-images-with-a-loaded-model"></a><span data-ttu-id="b37db-331">Klassifizieren von Bildern mit einem geladenen Modell</span><span class="sxs-lookup"><span data-stu-id="b37db-331">Classify images with a loaded model</span></span>

<span data-ttu-id="b37db-332">Fügen Sie den folgenden Aufruf der `ClassifyImages()`-Methode als nächste Codezeile der `Main`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="b37db-332">Add the following call to the `ClassifyImages()` method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallClassifyImages](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifyImages)]

<span data-ttu-id="b37db-333">Die `ClassifyImages()`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="b37db-333">The `ClassifyImages()` method executes the following tasks:</span></span>

* <span data-ttu-id="b37db-334">Einlesen der TSV-Datei in `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="b37db-334">Reads .TSV file into `IEnumerable`.</span></span>
* <span data-ttu-id="b37db-335">Vorhersage der Bildklassifizierungen anhand von Testdaten.</span><span class="sxs-lookup"><span data-stu-id="b37db-335">Predicts image classifications based on test data.</span></span>

<span data-ttu-id="b37db-336">Erstellen Sie die `ClassifyImages()`-Methode mithilfe des folgenden Codes unmittelbar nach der `ReuseAndTuneInceptionModel()`-Methode und direkt vor der `PairAndDisplayResults()`-Methode:</span><span class="sxs-lookup"><span data-stu-id="b37db-336">Create the `ClassifyImages()` method, just after the `ReuseAndTuneInceptionModel()` method and just before the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static void ClassifyImages(MLContext mlContext, string dataLocation, string imagesFolder, string outputModelLocation, ITransformer model)
{

}
```

<span data-ttu-id="b37db-337">Rufen Sie zunächst die `ReadFromTsv()`-Methode zum Erstellen einer `IEnumerable<ImageData>`-Klasse auf, die den vollqualifizierten Pfad für jeden `ImagePath` enthält.</span><span class="sxs-lookup"><span data-stu-id="b37db-337">First, call the `ReadFromTsv()` method to create an `IEnumerable<ImageData>` class that contains the fully qualified path for each `ImagePath`.</span></span> <span data-ttu-id="b37db-338">Sie benötigen diesen Dateipfad, um Ihre Daten und Vorhersageergebnisse zu koppeln.</span><span class="sxs-lookup"><span data-stu-id="b37db-338">You need that file path to pair your data and prediction results.</span></span> <span data-ttu-id="b37db-339">Sie müssen außerdem die `IEnumerable<ImageData>`-Klasse in eine `IDataView` konvertieren, die Sie zur Vorhersage verwenden.</span><span class="sxs-lookup"><span data-stu-id="b37db-339">You also need to convert the `IEnumerable<ImageData>` class to an `IDataView` that you will use to predict.</span></span> <span data-ttu-id="b37db-340">Fügen Sie der `ClassifyImages()`-Methode den folgenden Code in den nächsten beiden Zeilen hinzu:</span><span class="sxs-lookup"><span data-stu-id="b37db-340">Add the following code as the next two lines in the `ClassifyImages()` method:</span></span>

[!code-csharp[CallReadFromTSV](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReadFromTSV)]

<span data-ttu-id="b37db-341">Sagen Sie wie zuvor bei den Trainingsbilddaten die Kategorie der Testbilddaten mit der [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A)-Methode des übergebenen Modells vorher.</span><span class="sxs-lookup"><span data-stu-id="b37db-341">As you did previously with the training image data, predict the category of the test image data using the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method of the model passed in.</span></span> <span data-ttu-id="b37db-342">Fügen Sie der `ClassifyImages()`-Methode den folgenden Code für die Vorhersagen und zum Konvertieren der `predictions` `IDataView` in ein `IEnumerable` für Kopplung und Anzeige hinzu:</span><span class="sxs-lookup"><span data-stu-id="b37db-342">Add the following code to the `ClassifyImages()` method for the predictions and to convert the `predictions` `IDataView` into an `IEnumerable` for pairing and display:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Predict)]

<span data-ttu-id="b37db-343">Fügen Sie zum Koppeln und Anzeigen Ihrer Testbilddaten und Vorhersagen den folgenden Code zum Aufrufen der zuvor erstellten `DisplayResults()`-Methode als nächste Zeile der `ClassifyImages()`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="b37db-343">To pair and display your test image data and predictions, add the following code to call the `DisplayResults()` method previously created as the next line in the `ClassifyImages()` method:</span></span>

[!code-csharp[CallDisplayResults2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults2)]

## <a name="classify-a-single-image-with-a-loaded-model"></a><span data-ttu-id="b37db-344">Klassifizieren eines einzelnen Bilds mit einem geladenen Modell</span><span class="sxs-lookup"><span data-stu-id="b37db-344">Classify a single image with a loaded model</span></span>

<span data-ttu-id="b37db-345">Fügen Sie den folgenden Aufruf der `ClassifySingleImage()`-Methode der `Main`-Methode als nächste Codezeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="b37db-345">Add the following call to the `ClassifySingleImage()` method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallClassifySingleImage](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifySingleImage)]

<span data-ttu-id="b37db-346">Die `ClassifySingleImage()`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="b37db-346">The `ClassifySingleImage()` method executes the following tasks:</span></span>

* <span data-ttu-id="b37db-347">Laden einer `ImageData`-Instanz.</span><span class="sxs-lookup"><span data-stu-id="b37db-347">Loads an `ImageData` instance.</span></span>
* <span data-ttu-id="b37db-348">Vorhersagen der Bildklassifizierung anhand von Testdaten.</span><span class="sxs-lookup"><span data-stu-id="b37db-348">Predicts image classification based on test data.</span></span>

<span data-ttu-id="b37db-349">Erstellen Sie die `ClassifySingleImage()`-Methode mithilfe des folgenden Codes unmittelbar nach der `ClassifyImages()`-Methode und direkt vor der `PairAndDisplayResults()`-Methode:</span><span class="sxs-lookup"><span data-stu-id="b37db-349">Create the `ClassifySingleImage()` method, just after the `ClassifyImages()` method and just before the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static void ClassifySingleImage(MLContext mlContext, string imagePath, string outputModelLocation, ITransformer model)
{

}
```

<span data-ttu-id="b37db-350">Erstellen Sie zunächst eine `ImageData`-Klasse, die den vollqualifizierten Pfad und Bilddateinamen für den einzelnen `ImagePath` enthält.</span><span class="sxs-lookup"><span data-stu-id="b37db-350">First, create an `ImageData` class that contains the fully qualified path and image file name for the single `ImagePath`.</span></span> <span data-ttu-id="b37db-351">Fügen Sie der `ClassifySingleImage()`-Methode folgenden Code als nächste Zeilen hinzu:</span><span class="sxs-lookup"><span data-stu-id="b37db-351">Add the following code as the next  lines in the `ClassifySingleImage()` method:</span></span>

[!code-csharp[LoadImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadImageData)]

<span data-ttu-id="b37db-352">Die [PredictionEngine-Klasse](xref:Microsoft.ML.PredictionEngine%602) ist eine komfortable API, die eine Vorhersage für eine einzelne Dateninstanz ausführt.</span><span class="sxs-lookup"><span data-stu-id="b37db-352">The [PredictionEngine class](xref:Microsoft.ML.PredictionEngine%602) is a convenience API that performs a prediction on a single instance of data.</span></span> <span data-ttu-id="b37db-353">Die [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A)-Funktion trifft eine Vorhersage für eine einzelne Datenspalte.</span><span class="sxs-lookup"><span data-stu-id="b37db-353">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single column of data.</span></span> <span data-ttu-id="b37db-354">Übergeben Sie `imageData` an die `PredictionEngine`, um die Bildkategorie vorherzusagen, indem Sie `ClassifySingleImage()` den folgenden Code hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="b37db-354">Pass `imageData` to the `PredictionEngine` to predict the image category by adding the following code to `ClassifySingleImage()`:</span></span>

[!code-csharp[PredictSingle](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#PredictSingle)]

<span data-ttu-id="b37db-355">Zeigen Sie das Vorhersageergebnis als nächste Codezeile in der `ClassifySingleImage()`-Methode an:</span><span class="sxs-lookup"><span data-stu-id="b37db-355">Display the prediction result as the next line of code in the `ClassifySingleImage()` method:</span></span>

[!code-csharp[DisplayPrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPrediction)]

## <a name="results"></a><span data-ttu-id="b37db-356">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="b37db-356">Results</span></span>

<span data-ttu-id="b37db-357">Nachdem Sie die vorherigen Schritte durchgeführt haben, führen Sie die Konsolen-App aus (STRG+F5).</span><span class="sxs-lookup"><span data-stu-id="b37db-357">After following the previous steps, run your console app (Ctrl + F5).</span></span> <span data-ttu-id="b37db-358">Ihre Ergebnisse sollten der folgenden Ausgabe ähneln.</span><span class="sxs-lookup"><span data-stu-id="b37db-358">Your results should be similar to the following output.</span></span>  <span data-ttu-id="b37db-359">Möglicherweise werden Warnungen oder Verarbeitungsnachrichten angezeigt. Diese wurden jedoch aus Gründen der Übersichtlichkeit aus den folgenden Ergebnissen entfernt.</span><span class="sxs-lookup"><span data-stu-id="b37db-359">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

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

<span data-ttu-id="b37db-360">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="b37db-360">Congratulations!</span></span> <span data-ttu-id="b37db-361">Sie haben nun durch Wiederverwenden eines vortrainierten `TensorFlow`-Modells in ML.NET erfolgreich ein Machine Learning-Modell für die Bildklassifizierung erstellt.</span><span class="sxs-lookup"><span data-stu-id="b37db-361">You've now successfully built a machine learning model for image classification by reusing a pre-trained `TensorFlow` model in ML.NET.</span></span>

<span data-ttu-id="b37db-362">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).</span><span class="sxs-lookup"><span data-stu-id="b37db-362">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span>

<span data-ttu-id="b37db-363">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="b37db-363">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="b37db-364">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="b37db-364">Understand the problem</span></span>
> * <span data-ttu-id="b37db-365">Wiederverwenden und Optimieren des vortrainierten Modells</span><span class="sxs-lookup"><span data-stu-id="b37db-365">Reuse and tune the pre-trained model</span></span>
> * <span data-ttu-id="b37db-366">Klassifizieren von Bildern mit einem geladenen Modell</span><span class="sxs-lookup"><span data-stu-id="b37db-366">Classify images with a loaded model</span></span>

<span data-ttu-id="b37db-367">Sehen Sie sich im GitHub-Repository für Machine Learning-Beispiele nach einem Beispiel für erweiterte Bildklassifizierung um, damit Sie es untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="b37db-367">Check out the Machine Learning samples GitHub repository to explore an expanded image classification sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="b37db-368">dotnet/machinelearning-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="b37db-368">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/)
