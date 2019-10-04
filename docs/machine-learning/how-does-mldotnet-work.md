---
title: Was ist ML.NET, und wie funktioniert es?
description: ML.NET ermöglicht es Ihnen, .NET-Anwendungen in Online- oder Offlineszenarien mit Machine Learning zu versehen. Mit dieser Funktion können Sie automatische Vorhersagen unter Verwendung der Daten treffen, die für Ihre Anwendung verfügbar sind, ohne für die Verwendung von ML.NET mit einem Netzwerk verbunden sein zu müssen. In diesem Artikel werden die Grundlagen von Machine Learning in ML.NET erläutert.
ms.date: 09/27/2019
ms.topic: overview
ms.custom: mvc
ms.author: nakersha
author: natke
ms.openlocfilehash: 1ae6b82ada841ad172cbe6a59b667aaaf619e714
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592048"
---
# <a name="what-is-mlnet-and-how-does-it-work"></a><span data-ttu-id="d69fd-105">Was ist ML.NET, und wie funktioniert es?</span><span class="sxs-lookup"><span data-stu-id="d69fd-105">What is ML.NET and how does it work?</span></span>

<span data-ttu-id="d69fd-106">ML.NET ermöglicht es Ihnen, .NET-Anwendungen in Online- oder Offlineszenarien mit Machine Learning zu versehen.</span><span class="sxs-lookup"><span data-stu-id="d69fd-106">ML.NET gives you the ability to add machine learning to .NET applications, in either online or offline scenarios.</span></span> <span data-ttu-id="d69fd-107">Mit dieser Funktion können Sie automatische Vorhersagen unter Verwendung der Daten treffen, die für Ihre Anwendung verfügbar sind, ohne mit einem Netzwerk verbunden sein zu müssen.</span><span class="sxs-lookup"><span data-stu-id="d69fd-107">With this capability, you can make automatic predictions using the data available to your application without having to be connected to a network.</span></span> <span data-ttu-id="d69fd-108">In diesem Artikel werden die Grundlagen von Machine Learning in ML.NET erläutert.</span><span class="sxs-lookup"><span data-stu-id="d69fd-108">This article explains the basics of machine learning in ML.NET.</span></span>

<span data-ttu-id="d69fd-109">ML.NET kann unter Windows, Linux und macOS mit .NET Core oder unter Windows mit .NET Framework ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d69fd-109">ML.NET runs on Windows, Linux, and macOS using .NET Core, or Windows using .NET Framework.</span></span> <span data-ttu-id="d69fd-110">64-Bit wird auf allen Plattformen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d69fd-110">64 bit is supported on all platforms.</span></span> <span data-ttu-id="d69fd-111">32-Bit wird unter Windows unterstützt (mit Ausnahme der Funktionen TensorFlow, LightGBM und ONNX).</span><span class="sxs-lookup"><span data-stu-id="d69fd-111">32 bit is supported on Windows, except for TensorFlow, LightGBM, and ONNX related functionality.</span></span>

<span data-ttu-id="d69fd-112">Zu den Beispielen für den Typ von Vorhersagen, die Sie mit ML.NET treffen können, zählen:</span><span class="sxs-lookup"><span data-stu-id="d69fd-112">Examples of the type of predictions that you can make with ML.NET include:</span></span>

|||
|-|-|
|<span data-ttu-id="d69fd-113">Klassifizierung/Kategorisierung</span><span class="sxs-lookup"><span data-stu-id="d69fd-113">Classification/Categorization</span></span>|<span data-ttu-id="d69fd-114">Automatisches Unterteilen von Kundenfeedback in positive und negative Kategorien</span><span class="sxs-lookup"><span data-stu-id="d69fd-114">Automatically divide customer feedback into positive and negative categories</span></span>|
|<span data-ttu-id="d69fd-115">Regression/Vorhersagen kontinuierlicher Werte</span><span class="sxs-lookup"><span data-stu-id="d69fd-115">Regression/Predict continuous values</span></span>|<span data-ttu-id="d69fd-116">Vorhersagen des Hauspreises basierend auf Größe und Standort</span><span class="sxs-lookup"><span data-stu-id="d69fd-116">Predict the price of houses based on size and location</span></span>|
|<span data-ttu-id="d69fd-117">Anomalieerkennung</span><span class="sxs-lookup"><span data-stu-id="d69fd-117">Anomaly Detection</span></span>|<span data-ttu-id="d69fd-118">Erkennen von betrügerischen Banktransaktionen</span><span class="sxs-lookup"><span data-stu-id="d69fd-118">Detect fraudulent banking transactions</span></span> |
|<span data-ttu-id="d69fd-119">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="d69fd-119">Recommendations</span></span>|<span data-ttu-id="d69fd-120">Empfehlen von Produkten, die Onlinekäufern basierend auf ihren vorherigen Käufen wahrscheinlich gerne erwerben würden</span><span class="sxs-lookup"><span data-stu-id="d69fd-120">Suggest products that online shoppers may want to buy, based on their previous purchases</span></span>|

## <a name="hello-mlnet-world"></a><span data-ttu-id="d69fd-121">Hallo ML.NET-Welt</span><span class="sxs-lookup"><span data-stu-id="d69fd-121">Hello ML.NET World</span></span>

<span data-ttu-id="d69fd-122">Der Code im folgenden Codeausschnitt veranschaulicht die einfachste ML.NET-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="d69fd-122">The code in the following snippet demonstrates the simplest ML.NET application.</span></span> <span data-ttu-id="d69fd-123">In diesem Beispiel erstellt ein Modell der linearen Regression Hauspreisvorhersagen auf der Basis von Größe- und Preisdaten.</span><span class="sxs-lookup"><span data-stu-id="d69fd-123">This example constructs a linear regression model to predict house prices using house size and price data.</span></span> <span data-ttu-id="d69fd-124">In realen Anwendungen sind Daten und Modell wesentlich komplexer.</span><span class="sxs-lookup"><span data-stu-id="d69fd-124">In your real-life applications, your data and model will be much more complex.</span></span>

 ```csharp
    using System;
    using Microsoft.ML;
    using Microsoft.ML.Data;
    
    class Program
    {
        public class HouseData
        {
            public float Size { get; set; }
            public float Price { get; set; }
        }
    
        public class Prediction
        {
            [ColumnName("Score")]
            public float Price { get; set; }
        }
    
        static void Main(string[] args)
        {
            MLContext mlContext = new MLContext();
    
            // 1. Import or create training data
            HouseData[] houseData = {
                new HouseData() { Size = 1.1F, Price = 1.2F },
                new HouseData() { Size = 1.9F, Price = 2.3F },
                new HouseData() { Size = 2.8F, Price = 3.0F },
                new HouseData() { Size = 3.4F, Price = 3.7F } };
            IDataView trainingData = mlContext.Data.LoadFromEnumerable(houseData);

            // 2. Specify data preparation and model training pipeline
            var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
                .Append(mlContext.Regression.Trainers.Sdca(labelColumnName: "Price", maximumNumberOfIterations: 100));
    
            // 3. Train model
            var model = pipeline.Fit(trainingData);
    
            // 4. Make a prediction
            var size = new HouseData() { Size = 2.5F };
            var price = mlContext.Model.CreatePredictionEngine<HouseData, Prediction>(model).Predict(size);

            Console.WriteLine($"Predicted price for size: {size.Size*1000} sq ft= {price.Price*100:C}k");

            // Predicted price for size: 2500 sq ft= $261.98k
        }
    } 
```

## <a name="code-workflow"></a><span data-ttu-id="d69fd-125">Codeworkflow</span><span class="sxs-lookup"><span data-stu-id="d69fd-125">Code workflow</span></span>

<span data-ttu-id="d69fd-126">Im folgenden Diagramm werden die Anwendungscodestruktur und der iterative Prozess der Modellentwicklung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="d69fd-126">The following diagram represents the application code structure, as well as the iterative process of model development:</span></span>

- <span data-ttu-id="d69fd-127">Sammeln und Laden von Trainingsdaten in einem **IDataView**-Objekt</span><span class="sxs-lookup"><span data-stu-id="d69fd-127">Collect and load training data into an **IDataView** object</span></span>
- <span data-ttu-id="d69fd-128">Angeben einer Pipeline von Vorgängen zum Extrahieren von Features und Anwenden eines Machine Learning-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="d69fd-128">Specify a pipeline of operations to extract features and apply a machine learning algorithm</span></span>
- <span data-ttu-id="d69fd-129">Trainieren eines Modells durch Aufrufen von **Fit()** auf der Pipeline</span><span class="sxs-lookup"><span data-stu-id="d69fd-129">Train a model by calling **Fit()** on the pipeline</span></span>
- <span data-ttu-id="d69fd-130">Auswerten des Modells und Iterieren zur Verbesserung</span><span class="sxs-lookup"><span data-stu-id="d69fd-130">Evaluate the model and iterate to improve</span></span>
- <span data-ttu-id="d69fd-131">Speichern des Modells im Binärformat zur Verwendung in einer Anwendung</span><span class="sxs-lookup"><span data-stu-id="d69fd-131">Save the model into binary format, for use in an application</span></span>
- <span data-ttu-id="d69fd-132">Rückladen des Modells in ein **ITransformer**-Objekt</span><span class="sxs-lookup"><span data-stu-id="d69fd-132">Load the model back into an **ITransformer** object</span></span>
- <span data-ttu-id="d69fd-133">Treffen von Vorhersagen durch Aufrufen von **CreatePredictionEngine.Predict()**</span><span class="sxs-lookup"><span data-stu-id="d69fd-133">Make predictions by calling **CreatePredictionEngine.Predict()**</span></span>

![ML.NET-Anwendungsentwicklungsfluss einschließlich Komponenten für Datengenerierung, Pipelineentwicklung, Modelltraining, Modellauswertung und Modellverwendung](./media/mldotnet-annotated-workflow.png) 

<span data-ttu-id="d69fd-135">Wir werden diese Konzepte nun näher betrachten.</span><span class="sxs-lookup"><span data-stu-id="d69fd-135">Let's dig a little deeper into those concepts.</span></span>

## <a name="machine-learning-model"></a><span data-ttu-id="d69fd-136">Machine Learning-Modell</span><span class="sxs-lookup"><span data-stu-id="d69fd-136">Machine learning model</span></span>

<span data-ttu-id="d69fd-137">Ein ML.NET-Modell ist ein Objekt, das Transformationen enthält, die auf Ihre Eingabedaten angewendet werden, damit sie die vorhergesagte Ausgabe erreichen.</span><span class="sxs-lookup"><span data-stu-id="d69fd-137">An ML.NET model is an object that contains transformations to perform on your input data to arrive at the predicted output.</span></span>

### <a name="basic"></a><span data-ttu-id="d69fd-138">Standard</span><span class="sxs-lookup"><span data-stu-id="d69fd-138">Basic</span></span>

<span data-ttu-id="d69fd-139">Das einfachste Modell ist die zweidimensionale lineare Regression, wobei wie im obigen Hauspreisbeispiel eine kontinuierliche Menge zu einer anderen proportional ist.</span><span class="sxs-lookup"><span data-stu-id="d69fd-139">The most basic model is two-dimensional linear regression, where one continuous quantity is proportional to another, as in the house price example above.</span></span> 

![Modell der linearen Regression mit Trend- und Gewichtungsparametern](./media/linear-regression-model.svg)

<span data-ttu-id="d69fd-141">Das Modell ist einfach: $Price = b + Size \* w$.</span><span class="sxs-lookup"><span data-stu-id="d69fd-141">The model is simply: $Price = b + Size \* w$.</span></span> <span data-ttu-id="d69fd-142">Die Parameter „$b$“ und „$w$“ werden durch Anpassung einer Linie an eine Gruppe von (size, price)-Paaren geschätzt.</span><span class="sxs-lookup"><span data-stu-id="d69fd-142">The parameters $b$ and $w$ are estimated by fitting a line on a set of (size, price) pairs.</span></span> <span data-ttu-id="d69fd-143">Die zum Finden der Parameter des Modells verwendeten Daten werden als **Trainingsdaten** bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d69fd-143">The data used to find the parameters of the model is called **training data**.</span></span> <span data-ttu-id="d69fd-144">Die Eingaben eines Machine Learning-Modells werden als **Features** bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d69fd-144">The inputs of a machine learning model are called **features**.</span></span> <span data-ttu-id="d69fd-145">In diesem Beispiel ist $Size$ das einzige Feature.</span><span class="sxs-lookup"><span data-stu-id="d69fd-145">In this example, $Size$ is the only feature.</span></span> <span data-ttu-id="d69fd-146">Die zum Trainieren eines Machine Learning-Modells verwendeten Ground-Truth-Werte werden als **Labels** bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d69fd-146">The ground-truth values used to train a machine learning model are called **labels**.</span></span> <span data-ttu-id="d69fd-147">Hier sind die $Price$-Werte im Trainingsdataset die Labels.</span><span class="sxs-lookup"><span data-stu-id="d69fd-147">Here, the $Price$ values in the training data set are the labels.</span></span>

### <a name="more-complex"></a><span data-ttu-id="d69fd-148">Komplexer</span><span class="sxs-lookup"><span data-stu-id="d69fd-148">More complex</span></span>

<span data-ttu-id="d69fd-149">Ein komplexeres Modell klassifiziert finanzielle Transaktionen mithilfe der Transaktionstextbeschreibung in Kategorien.</span><span class="sxs-lookup"><span data-stu-id="d69fd-149">A more complex model classifies financial transactions into categories using the transaction text description.</span></span>

<span data-ttu-id="d69fd-150">Jede Transaktionsbeschreibung wird durch Entfernen redundante Wörter und Zeichen und Zählen von Kombinationen aus Word und Zeichen in einen Satz von Features aufgeschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="d69fd-150">Each transaction description is broken down into a set of features by removing redundant words and characters, and counting word and character combinations.</span></span> <span data-ttu-id="d69fd-151">Die Featuregruppe wird zum Trainieren eines linearen Modells auf der Basis des Kategoriensatzes in den Trainingsdaten verwendet.</span><span class="sxs-lookup"><span data-stu-id="d69fd-151">The feature set is used to train a linear model based on the set of categories in the training data.</span></span> <span data-ttu-id="d69fd-152">Je mehr eine neue Beschreibung denjenigen im Trainingssatz ähnelt, desto eher wird sie derselben Kategorie zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d69fd-152">The more similar a new description is to the ones in the training set, the more likely it will be assigned to the same category.</span></span> 

![Textklassifizierungsmodell](./media/text-classification-model.svg)

<span data-ttu-id="d69fd-154">Hauspreismodell und Textklassifizierungsmodell sind beide **lineare** Modelle.</span><span class="sxs-lookup"><span data-stu-id="d69fd-154">Both the house price model and the text classification model are **linear** models.</span></span> <span data-ttu-id="d69fd-155">Je nach Art Ihrer Daten und des Problems, das Sie lösen, können Sie auch **Entscheidungsstrukturmodelle**, verallgemeinert **additive** Modelle, und andere verwenden.</span><span class="sxs-lookup"><span data-stu-id="d69fd-155">Depending on the nature of your data and the problem you are solving, you can also use **decision tree** models, **generalized additive** models, and others.</span></span> <span data-ttu-id="d69fd-156">Weitere Informationen zu den Modellen finden Sie unter [Aufgaben](./resources/tasks.md).</span><span class="sxs-lookup"><span data-stu-id="d69fd-156">You can find out more about the models in [Tasks](./resources/tasks.md).</span></span>

## <a name="data-preparation"></a><span data-ttu-id="d69fd-157">Datenvorbereitung</span><span class="sxs-lookup"><span data-stu-id="d69fd-157">Data preparation</span></span>

<span data-ttu-id="d69fd-158">In den meisten Fällen können die Daten, die Ihnen zur Verfügung stehen, nicht direkt zum Trainieren von Machine Learning-Modellen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d69fd-158">In most cases, the data that you have available isn't suitable to be used directly to train a machine learning model.</span></span> <span data-ttu-id="d69fd-159">Die unformatierten Daten müssen vorbereitet, d.h. vorverarbeitet werden, bevor Sie sie verwenden können, um die Parameter Ihres Modells zu finden.</span><span class="sxs-lookup"><span data-stu-id="d69fd-159">The raw data needs to be prepared, or pre-processed before it can be used to find the parameters of your model.</span></span> <span data-ttu-id="d69fd-160">Möglicherweise müssen Ihre Daten von Zeichenfolgenwerten in eine numerische Darstellung konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="d69fd-160">Your data may need to be converted from string values to a numerical representation.</span></span> <span data-ttu-id="d69fd-161">Vielleicht enthalten Ihre Eingabedaten redundante Informationen.</span><span class="sxs-lookup"><span data-stu-id="d69fd-161">You might have redundant information in your input data.</span></span> <span data-ttu-id="d69fd-162">Sie müssen möglicherweise die Dimensionen der Eingabedaten reduzieren oder erweitern.</span><span class="sxs-lookup"><span data-stu-id="d69fd-162">You may need to reduce or expand the dimensions of your input data.</span></span> <span data-ttu-id="d69fd-163">Ihre Daten müssen vielleicht normalisiert oder skaliert werden.</span><span class="sxs-lookup"><span data-stu-id="d69fd-163">Your data might need to be normalized or scaled.</span></span>

<span data-ttu-id="d69fd-164">Die [ML.NET-Tutorials](./tutorials/index.md) informieren Sie über verschiedene Datenverarbeitungspipelines für Text-, Bild-, numerische und Zeitreihendaten, die für bestimmte Machine Learning-Aufgaben verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d69fd-164">The [ML.NET tutorials](./tutorials/index.md) teach you about different data processing pipelines for text, image, numerical, and time-series data used for specific machine learning tasks.</span></span>

<span data-ttu-id="d69fd-165">Unter [Vorbereiten von Daten](./how-to-guides/prepare-data-ml-net.md) finden Sie allgemeinere Informationen zur Anwendung der Datenvorbereitung.</span><span class="sxs-lookup"><span data-stu-id="d69fd-165">[How to prepare your data](./how-to-guides/prepare-data-ml-net.md) shows you how to applied data preparation more generally.</span></span>

<span data-ttu-id="d69fd-166">Im Ressourcenabschnitt finden Sie einen Anhang mit allen [verfügbaren Transformationen](./resources/transforms.md).</span><span class="sxs-lookup"><span data-stu-id="d69fd-166">You can find an appendix of all of the [available transformations](./resources/transforms.md) in the resources section.</span></span>

## <a name="model-evaluation"></a><span data-ttu-id="d69fd-167">Modellauswertung</span><span class="sxs-lookup"><span data-stu-id="d69fd-167">Model evaluation</span></span>

<span data-ttu-id="d69fd-168">Wie können Sie nach dem Trainieren Ihres Modells wissen, wie gut es zukünftige Vorhersagen treffen wird?</span><span class="sxs-lookup"><span data-stu-id="d69fd-168">Once you have trained your model, how do you know how well it will make future predictions?</span></span> <span data-ttu-id="d69fd-169">Mit ML.NET können Sie Ihr Modell anhand einiger neuer Testdaten auswerten.</span><span class="sxs-lookup"><span data-stu-id="d69fd-169">With ML.NET, you can evaluate your model against some new test data.</span></span> 

<span data-ttu-id="d69fd-170">Jede Art von Machine Learning-Aufgabe verfügt über Metriken zum Auswerten der Genauigkeit des Modells anhand eines Testdatasets.</span><span class="sxs-lookup"><span data-stu-id="d69fd-170">Each type of machine learning task has metrics used to evaluate the accuracy and precision of the model against the test data set.</span></span>

<span data-ttu-id="d69fd-171">In unserem Hauspreisbeispiel haben wir die **Regressionsaufgabe** verwendet.</span><span class="sxs-lookup"><span data-stu-id="d69fd-171">For our house price example, we used the **Regression** task.</span></span> <span data-ttu-id="d69fd-172">Um das Modell auszuwerten, fügen Sie dem ursprünglichen Beispiel den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="d69fd-172">To evaluate the model, add the following code to the original sample.</span></span>

```csharp
        HouseData[] testHouseData =
        {
            new HouseData() { Size = 1.1F, Price = 0.98F },
            new HouseData() { Size = 1.9F, Price = 2.1F },
            new HouseData() { Size = 2.8F, Price = 2.9F },
            new HouseData() { Size = 3.4F, Price = 3.6F }
        };

        var testHouseDataView = mlContext.Data.LoadFromEnumerable(testHouseData);
        var testPriceDataView = model.Transform(testHouseDataView);
                
        var metrics = mlContext.Regression.Evaluate(testPriceDataView, labelColumnName: "Price");

        Console.WriteLine($"R^2: {metrics.RSquared:0.##}");
        Console.WriteLine($"RMS error: {metrics.RootMeanSquaredError:0.##}");

        // R^2: 0.96
        // RMS error: 0.19
```

<span data-ttu-id="d69fd-173">Die Auswertungsmetriken zeigen, dass der Fehler gering ist, und dass die Korrelation zwischen der vorhergesagten Ausgabe und der Testausgabe hoch ist.</span><span class="sxs-lookup"><span data-stu-id="d69fd-173">The evaluation metrics tell you that the error is low-ish, and that correlation between the predicted output and the test output is high.</span></span> <span data-ttu-id="d69fd-174">Nun, das war einfach.</span><span class="sxs-lookup"><span data-stu-id="d69fd-174">That was easy!</span></span> <span data-ttu-id="d69fd-175">In realen Beispielen sind weitere Optimierungen erforderlich, um gute Modellmetriken zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="d69fd-175">In real examples, it takes more tuning to achieve good model metrics.</span></span>

## <a name="mlnet-architecture"></a><span data-ttu-id="d69fd-176">ML.NET-Architektur</span><span class="sxs-lookup"><span data-stu-id="d69fd-176">ML.NET architecture</span></span>

<span data-ttu-id="d69fd-177">In diesem Abschnitt behandeln wir die Architekturmuster von ML.NET.</span><span class="sxs-lookup"><span data-stu-id="d69fd-177">In this section, we go through the architectural patterns of ML.NET.</span></span> <span data-ttu-id="d69fd-178">Wenn Sie ein erfahrener .NET-Entwickler sind, werden Ihnen einige dieser Muster vertraut und einige weniger vertraut sein.</span><span class="sxs-lookup"><span data-stu-id="d69fd-178">If you are an experienced .NET developer, some of these patterns will be familiar to you, and some will be less familiar.</span></span> <span data-ttu-id="d69fd-179">Halten Sie sich fest, es geht sofort los!</span><span class="sxs-lookup"><span data-stu-id="d69fd-179">Hold tight, while we dive in!</span></span>

<span data-ttu-id="d69fd-180">Eine ML.NET-Anwendung beginnt mit einem <xref:Microsoft.ML.MLContext>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="d69fd-180">An ML.NET application starts with an <xref:Microsoft.ML.MLContext> object.</span></span> <span data-ttu-id="d69fd-181">Dieses Singletonobjekt enthält **Kataloge**.</span><span class="sxs-lookup"><span data-stu-id="d69fd-181">This singleton object contains **catalogs**.</span></span> <span data-ttu-id="d69fd-182">Ein Katalog ist eine Factory zum Laden und Speichern von Daten, für Transformationen, Trainer und Modellvorgangskomponenten.</span><span class="sxs-lookup"><span data-stu-id="d69fd-182">A catalog is a factory for data loading and saving, transforms, trainers, and model operation components.</span></span> <span data-ttu-id="d69fd-183">Jedes Katalogobjekt verfügt über Methoden, um die verschiedenen Typen von Komponenten zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="d69fd-183">Each catalog object has methods to create the different types of components:</span></span>

|||||
|-|-|-|-|
|<span data-ttu-id="d69fd-184">Laden und Speichern von Daten</span><span class="sxs-lookup"><span data-stu-id="d69fd-184">Data loading and saving</span></span>||<xref:Microsoft.ML.DataOperationsCatalog>||
|<span data-ttu-id="d69fd-185">Datenvorbereitung</span><span class="sxs-lookup"><span data-stu-id="d69fd-185">Data preparation</span></span>||<xref:Microsoft.ML.TransformsCatalog>||
|<span data-ttu-id="d69fd-186">Trainingsalgorithmen</span><span class="sxs-lookup"><span data-stu-id="d69fd-186">Training algorithms</span></span>|<span data-ttu-id="d69fd-187">Binäre Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="d69fd-187">Binary classification</span></span>|<xref:Microsoft.ML.BinaryClassificationCatalog>||
||<span data-ttu-id="d69fd-188">Multiklassenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="d69fd-188">Multiclass classification</span></span>|<xref:Microsoft.ML.MulticlassClassificationCatalog>||
||<span data-ttu-id="d69fd-189">Anomalieerkennung</span><span class="sxs-lookup"><span data-stu-id="d69fd-189">Anomaly detection</span></span>|<xref:Microsoft.ML.AnomalyDetectionCatalog>||
||<span data-ttu-id="d69fd-190">Clusterbildung</span><span class="sxs-lookup"><span data-stu-id="d69fd-190">Clustering</span></span>|<xref:Microsoft.ML.ClusteringCatalog>||
||<span data-ttu-id="d69fd-191">Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="d69fd-191">Forecasting</span></span>|<xref:Microsoft.ML.ForecastingCatalog>||
||<span data-ttu-id="d69fd-192">Rangfolge</span><span class="sxs-lookup"><span data-stu-id="d69fd-192">Ranking</span></span>|<xref:Microsoft.ML.RankingCatalog>||
||<span data-ttu-id="d69fd-193">Regression</span><span class="sxs-lookup"><span data-stu-id="d69fd-193">Regression</span></span>|<xref:Microsoft.ML.RegressionCatalog>||
||<span data-ttu-id="d69fd-194">Empfehlung</span><span class="sxs-lookup"><span data-stu-id="d69fd-194">Recommendation</span></span>|<xref:Microsoft.ML.RecommendationCatalog>|<span data-ttu-id="d69fd-195">`Microsoft.ML.Recommender`-NuGet-Paket hinzufügen</span><span class="sxs-lookup"><span data-stu-id="d69fd-195">add the `Microsoft.ML.Recommender` NuGet package</span></span>|
||<span data-ttu-id="d69fd-196">TimeSeries</span><span class="sxs-lookup"><span data-stu-id="d69fd-196">TimeSeries</span></span>|<xref:Microsoft.ML.TimeSeriesCatalog>|<span data-ttu-id="d69fd-197">`Microsoft.ML.TimeSeries`-NuGet-Paket hinzufügen</span><span class="sxs-lookup"><span data-stu-id="d69fd-197">add the `Microsoft.ML.TimeSeries` NuGet package</span></span>|
|<span data-ttu-id="d69fd-198">Modellverwendung</span><span class="sxs-lookup"><span data-stu-id="d69fd-198">Model usage</span></span> ||<xref:Microsoft.ML.ModelOperationsCatalog>||

<span data-ttu-id="d69fd-199">Sie können in jeder der oben genannten Kategorien zu den Erstellungsmethoden navigieren.</span><span class="sxs-lookup"><span data-stu-id="d69fd-199">You can navigate to the creation methods in each of the above categories.</span></span> <span data-ttu-id="d69fd-200">Bei Verwendung von Visual Studio werden die Kataloge über IntelliSense angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d69fd-200">Using Visual Studio, the catalogs show up via IntelliSense.</span></span>

   ![IntelliSense für Regressionstrainer](./media/catalog-intellisense.png)

### <a name="build-the-pipeline"></a><span data-ttu-id="d69fd-202">Erstellen der Pipeline</span><span class="sxs-lookup"><span data-stu-id="d69fd-202">Build the pipeline</span></span>

<span data-ttu-id="d69fd-203">In jedem Katalog befindet sich eine Reihe von Erweiterungsmethoden.</span><span class="sxs-lookup"><span data-stu-id="d69fd-203">Inside each catalog is a set of extension methods.</span></span> <span data-ttu-id="d69fd-204">Wir untersuchen, wie Erweiterungsmethoden zum Erstellen einer Trainingspipeline verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d69fd-204">Let's look at how extension methods are used to create a training pipeline.</span></span>

```csharp
    var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
        .Append(mlContext.Regression.Trainers.Sdca(labelColumnName: "Price", maximumNumberOfIterations: 100));
```

<span data-ttu-id="d69fd-205">Im Codeausschnitt sind `Concatenate` und `Sdca` Methoden im Katalog.</span><span class="sxs-lookup"><span data-stu-id="d69fd-205">In the snippet, `Concatenate` and `Sdca` are both methods in the catalog.</span></span> <span data-ttu-id="d69fd-206">Sie erstellen jeweils ein [IEstimator](xref:Microsoft.ML.IEstimator%601)-Objekt, das der Pipeline angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="d69fd-206">They each create an [IEstimator](xref:Microsoft.ML.IEstimator%601) object that is appended to the pipeline.</span></span>

<span data-ttu-id="d69fd-207">An diesem Punkt werden die Objekte nur erstellt.</span><span class="sxs-lookup"><span data-stu-id="d69fd-207">At this point, the objects are created only.</span></span> <span data-ttu-id="d69fd-208">Es hat keine Ausführung stattgefunden.</span><span class="sxs-lookup"><span data-stu-id="d69fd-208">No execution has happened.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="d69fd-209">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="d69fd-209">Train the model</span></span>

<span data-ttu-id="d69fd-210">Nachdem die Objekte in der Pipeline erstellt wurden, können Daten zum Trainieren des Modells verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d69fd-210">Once the objects in the pipeline have been created, data can be used to train the model.</span></span>

```csharp
    var model = pipeline.Fit(trainingData);
```

<span data-ttu-id="d69fd-211">Beim Aufruf von `Fit()` werden die Eingabetrainingsdaten verwendet, um die Parameter des Modells zu schätzen.</span><span class="sxs-lookup"><span data-stu-id="d69fd-211">Calling `Fit()` uses the input training data to estimate the parameters of the model.</span></span> <span data-ttu-id="d69fd-212">Dies wird als Trainieren des Modells bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d69fd-212">This is known as training the model.</span></span> <span data-ttu-id="d69fd-213">Beachten Sie, dass das Modell der linearen Regression oben zwei Modellparameter hatte: **Trend** und **Gewichtung**.</span><span class="sxs-lookup"><span data-stu-id="d69fd-213">Remember, the linear regression model above had two model parameters: **bias** and **weight**.</span></span> <span data-ttu-id="d69fd-214">Nach dem `Fit()`-Aufruf sind die Werte der Parameter bekannt.</span><span class="sxs-lookup"><span data-stu-id="d69fd-214">After the `Fit()` call, the values of the parameters are known.</span></span> <span data-ttu-id="d69fd-215">Die meisten Modelle haben viel mehr Parameter als dieses.</span><span class="sxs-lookup"><span data-stu-id="d69fd-215">Most models will have many more parameters than this.</span></span>

<span data-ttu-id="d69fd-216">Weitere Informationen über das Modelltraining finden Sie unter [Trainieren und Auswerten eines Modells](./how-to-guides/train-machine-learning-model-ml-net.md).</span><span class="sxs-lookup"><span data-stu-id="d69fd-216">You can learn more about model training in [How to train your model](./how-to-guides/train-machine-learning-model-ml-net.md)</span></span>

<span data-ttu-id="d69fd-217">Das resultierende Modellobjekt implementiert die <xref:Microsoft.ML.ITransformer>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d69fd-217">The resulting model object implements the <xref:Microsoft.ML.ITransformer> interface.</span></span> <span data-ttu-id="d69fd-218">Das Modell transformiert also Eingabedaten in Vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="d69fd-218">That is, the model transforms input data into predictions.</span></span>

```csharp
   IDataView predictions = model.Transform(inputData);
```

### <a name="use-the-model"></a><span data-ttu-id="d69fd-219">Verwenden des Modells</span><span class="sxs-lookup"><span data-stu-id="d69fd-219">Use the model</span></span>

<span data-ttu-id="d69fd-220">Sie können Eingabedaten in einem Massenvorgang in Vorhersagen umwandeln oder jede Eingabe einzeln.</span><span class="sxs-lookup"><span data-stu-id="d69fd-220">You can transform input data into predictions in bulk, or one input at a time.</span></span> <span data-ttu-id="d69fd-221">Im Hauspreisbeispiel haben wir beides getan: im Massenvorgang zum Auswerten des Modells und einzeln, um eine neue Vorhersage zu treffen.</span><span class="sxs-lookup"><span data-stu-id="d69fd-221">In the house price example, we did both: in bulk for the purpose of evaluating the model, and one at a time to make a new prediction.</span></span> <span data-ttu-id="d69fd-222">Wir betrachten nun die einzelnen Vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="d69fd-222">Let's look at making single predictions.</span></span>

```csharp
    var size = new HouseData() { Size = 2.5F };
    var predEngine = mlContext.CreatePredictionEngine<HouseData, Prediction>(model);
    var price = predEngine.Predict(size);
```
 
<span data-ttu-id="d69fd-223">Die `CreatePredictionEngine()`-Methode nimmt eine Eingabe- und eine Ausgabeklasse entgegen.</span><span class="sxs-lookup"><span data-stu-id="d69fd-223">The `CreatePredictionEngine()` method takes an input class and an output class.</span></span> <span data-ttu-id="d69fd-224">Die Feldnamen und/oder Codeattribute bestimmen die Namen der Datenspalten, die beim Trainieren des Modells und der Vorhersage verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d69fd-224">The field names and/or code attributes determine the names of the data columns used during model training and prediction.</span></span> <span data-ttu-id="d69fd-225">Weitere Informationen finden Sie unter [Treffen von Vorhersagen mit einem trainierten Modell](./how-to-guides/single-predict-model-ml-net.md).</span><span class="sxs-lookup"><span data-stu-id="d69fd-225">You can read about  [How to make a single prediction](./how-to-guides/single-predict-model-ml-net.md) in the How-to section.</span></span>

### <a name="data-models-and-schema"></a><span data-ttu-id="d69fd-226">Datenmodelle und Schema</span><span class="sxs-lookup"><span data-stu-id="d69fd-226">Data models and schema</span></span>

<span data-ttu-id="d69fd-227">Das Herzstück einer ML.NET-Machine Learning-Pipeline sind [DataView](xref:Microsoft.ML.IDataView)-Objekte.</span><span class="sxs-lookup"><span data-stu-id="d69fd-227">At the core of an ML.NET machine learning pipeline are [DataView](xref:Microsoft.ML.IDataView) objects.</span></span>

<span data-ttu-id="d69fd-228">Jede Transformation in der Pipeline weist ein Eingabeschema (Datennamen, -typen und -größen, die die Transformation bei der Eingabe erwartet) und ein Ausgabeschema (nach der Transformation erzeugte Datennamen, -typen und -größen) auf.</span><span class="sxs-lookup"><span data-stu-id="d69fd-228">Each transformation in the pipeline has an input schema (data names, types, and sizes that the transform expects to see on its input); and an output schema (data names, types, and sizes that the transform produces after the transformation).</span></span> <span data-ttu-id="d69fd-229">Das folgende Dokument enthält eine ausführliche Erläuterung der [Schnittstelle IDataView und deren Typsystem](https://xadupre.github.io/machinelearningext/mlnetdocs/idataviewtypesystem.html).</span><span class="sxs-lookup"><span data-stu-id="d69fd-229">The following document provides an in-depth explanation of the [IDataView interface and its type system](https://xadupre.github.io/machinelearningext/mlnetdocs/idataviewtypesystem.html).</span></span>

<span data-ttu-id="d69fd-230">Wenn das Ausgabeschema einer Transformation in der Pipeline nicht dem Eingabeschema der nächsten Transformation entspricht, löst ML.NET eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="d69fd-230">If the output schema from one transform in the pipeline doesn't match the input schema of the next transform, ML.NET will throw an exception.</span></span>

<span data-ttu-id="d69fd-231">Ein Datenansichtsobjekt enthält Spalten und Zeilen.</span><span class="sxs-lookup"><span data-stu-id="d69fd-231">A data view object has columns and rows.</span></span> <span data-ttu-id="d69fd-232">Jede Spalte hat einen Namen, einen Typ und eine Länge.</span><span class="sxs-lookup"><span data-stu-id="d69fd-232">Each column has a name and a type and a length.</span></span> <span data-ttu-id="d69fd-233">Beispiel: die Eingabespalten im Hauspreisbeispiel sind **Size** und **Price** („Größe“ und „Preis“).</span><span class="sxs-lookup"><span data-stu-id="d69fd-233">For example: the input columns in the house price example are **Size** and **Price**.</span></span> <span data-ttu-id="d69fd-234">Beide sind Typen, und sie sind eher Skalar- als Vektormengen.</span><span class="sxs-lookup"><span data-stu-id="d69fd-234">They are both type  and they are scalar quantities rather than vector ones.</span></span>

   ![Beispiel der ML.NET-Datenansicht mit Hauspreis-Vorhersagedaten](./media/ml-net-dataview.png)

<span data-ttu-id="d69fd-236">Alle ML.NET-Algorithmen suchen nach einer Eingabespalte, die ein Vektor ist.</span><span class="sxs-lookup"><span data-stu-id="d69fd-236">All ML.NET algorithms look for an input column that is a vector.</span></span> <span data-ttu-id="d69fd-237">Standardmäßig wird diese Vektorspalte mit **Features** bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d69fd-237">By default this vector column is called **Features**.</span></span> <span data-ttu-id="d69fd-238">Darum haben wir in unserem Hauspreisbeispiel die Spalte **Size** in eine neue Spalte namens **Features** verkettet.</span><span class="sxs-lookup"><span data-stu-id="d69fd-238">This is why we concatenated the **Size** column into a new column called **Features** in our house price example.</span></span>

 ```csharp
    var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
 ```

<span data-ttu-id="d69fd-239">Alle Algorithmen erstellen auch neue Spalten, nachdem sie eine Vorhersage ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="d69fd-239">All algorithms also create new columns after they have performed a prediction.</span></span> <span data-ttu-id="d69fd-240">Die festgelegten Namen dieser neuen Spalten hängen vom Typ des Machine Learning-Algorithmus ab.</span><span class="sxs-lookup"><span data-stu-id="d69fd-240">The fixed names of these new columns depend on the type of machine learning algorithm.</span></span> <span data-ttu-id="d69fd-241">Für die Regressionsaufgabe wird eine der neuen Spalten mit **Score**.</span><span class="sxs-lookup"><span data-stu-id="d69fd-241">For the regression task, one of the new columns is called **Score**.</span></span> <span data-ttu-id="d69fd-242">Darum haben wir unseren Preisdaten diesen Namen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d69fd-242">This is why we attributed our price data with this name.</span></span>

```csharp
    public class Prediction
    {
        [ColumnName("Score")]
        public float Price { get; set; }
    }
```    

<span data-ttu-id="d69fd-243">Weitere Informationen über Ausgabespalten anderer Machine Learning-Aufgaben finden Sie im Handbuch [Machine Learning-Aufgaben in ML.NET](resources/tasks.md).</span><span class="sxs-lookup"><span data-stu-id="d69fd-243">You can find out more about output columns of different machine learning tasks in the [Machine Learning Tasks](resources/tasks.md) guide.</span></span>

<span data-ttu-id="d69fd-244">Eine wichtige Eigenschaft von DataView-Objekten ist, dass sie **verzögert** ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="d69fd-244">An important property of DataView objects is that they are evaluated **lazily**.</span></span> <span data-ttu-id="d69fd-245">Datenansichten werden nur beim Trainieren und Auswerten des Modells und bei der Datenvorhersage geladen und verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d69fd-245">Data views are only loaded and operated on during model training and evaluation, and data prediction.</span></span> <span data-ttu-id="d69fd-246">Beim Schreiben und Testen Ihrer ML.NET-Anwendung können Sie mit dem Visual Studio-Debugger einen Blick auf jedes Datenansichtsobjekt werfen, indem Sie die [Preview](xref:Microsoft.ML.DebuggerExtensions.Preview*)-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d69fd-246">While you are writing and testing your ML.NET application, you can use the Visual Studio debugger to take a peek at any data view object by calling the [Preview](xref:Microsoft.ML.DebuggerExtensions.Preview*) method.</span></span>

```csharp
    var debug = testPriceDataView.Preview();
```

<span data-ttu-id="d69fd-247">Sie können die `debug`-Variable im Debugger beobachten und ihren Inhalt untersuchen.</span><span class="sxs-lookup"><span data-stu-id="d69fd-247">You can watch the `debug` variable in the debugger and examine its contents.</span></span> <span data-ttu-id="d69fd-248">Verwenden Sie die Preview-Methode nicht im Produktionscode, da sie die Leistung erheblich beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="d69fd-248">Do not use the Preview method in production code, as it significantly degrades performance.</span></span>

### <a name="model-deployment"></a><span data-ttu-id="d69fd-249">Modellbereitstellung</span><span class="sxs-lookup"><span data-stu-id="d69fd-249">Model Deployment</span></span>

<span data-ttu-id="d69fd-250">In realen Anwendungen sind Ihr Modelltrainings- und Auswertungscode von Ihrer Vorhersage getrennt.</span><span class="sxs-lookup"><span data-stu-id="d69fd-250">In real-life applications, your model training and evaluation code will be separate from your prediction.</span></span> <span data-ttu-id="d69fd-251">Diese beiden Aktivitäten werden in der Tat häufig durch separate Teams ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d69fd-251">In fact, these two activities are often performed by separate teams.</span></span> <span data-ttu-id="d69fd-252">Ihr Modellbereitstellungsteam kann das Modell zur Verwendung in der Vorhersageanwendung speichern.</span><span class="sxs-lookup"><span data-stu-id="d69fd-252">Your model development team can save the model for use in the prediction application.</span></span>

```csharp   
   mlContext.Model.Save(model, trainingData.Schema,"model.zip");
```

## <a name="where-to-now"></a><span data-ttu-id="d69fd-253">Weitere Themen</span><span class="sxs-lookup"><span data-stu-id="d69fd-253">Where to now?</span></span>

<span data-ttu-id="d69fd-254">Erfahren Sie in den [Tutorials](./tutorials/index.md), wie Sie mit anderen Machine Learning-Aufgaben Anwendungen mit realistischeren Datasets erstellen.</span><span class="sxs-lookup"><span data-stu-id="d69fd-254">You can learn how to build applications using different machine learning tasks with more realistic data sets in the [tutorials](./tutorials/index.md).</span></span>

<span data-ttu-id="d69fd-255">Sie können sich auch in den [Schrittanleitungen für .NET Machine Learning](./how-to-guides/index.md) ausführlicher über bestimmte Themen informieren.</span><span class="sxs-lookup"><span data-stu-id="d69fd-255">Or you can learn about specific topics in more depth in the [How To Guides](./how-to-guides/index.md).</span></span>

<span data-ttu-id="d69fd-256">Und wenn Sie extrem interessiert sind, können Sie direkt in die [API-Referenzdokumentation](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet) eintauchen!</span><span class="sxs-lookup"><span data-stu-id="d69fd-256">And if you're super keen, you can dive straight into the [API Reference documentation](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet)!</span></span>
