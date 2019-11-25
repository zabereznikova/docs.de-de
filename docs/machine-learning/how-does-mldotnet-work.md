---
title: Was ist ML.NET, und wie funktioniert es?
description: ML.NET ermöglicht es Ihnen, .NET-Anwendungen in Online- oder Offlineszenarien mit Machine Learning zu versehen. Mit dieser Funktion können Sie automatische Vorhersagen unter Verwendung der Daten treffen, die für Ihre Anwendung verfügbar sind, ohne für die Verwendung von ML.NET mit einem Netzwerk verbunden sein zu müssen. In diesem Artikel werden die Grundlagen von Machine Learning in ML.NET erläutert.
ms.date: 11/5/2019
ms.topic: overview
ms.custom: mvc
ms.author: nakersha
author: natke
ms.openlocfilehash: 5d8093c77799a55f4bc13e82c06c856dbb8d85cd
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976739"
---
# <a name="what-is-mlnet-and-how-does-it-work"></a><span data-ttu-id="f199e-105">Was ist ML.NET, und wie funktioniert es?</span><span class="sxs-lookup"><span data-stu-id="f199e-105">What is ML.NET and how does it work?</span></span>

<span data-ttu-id="f199e-106">ML.NET ermöglicht es Ihnen, .NET-Anwendungen in Online- oder Offlineszenarien mit Machine Learning zu versehen.</span><span class="sxs-lookup"><span data-stu-id="f199e-106">ML.NET gives you the ability to add machine learning to .NET applications, in either online or offline scenarios.</span></span> <span data-ttu-id="f199e-107">Mit dieser Funktion können Sie automatische Vorhersagen unter Verwendung der Daten treffen, die für Ihre Anwendung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f199e-107">With this capability, you can make automatic predictions using the data available to your application.</span></span>

<span data-ttu-id="f199e-108">Zentraler Bestandteil von ML.NET ist ein Machine Learning-**Modell**.</span><span class="sxs-lookup"><span data-stu-id="f199e-108">Central to ML.NET is a machine learning **model**.</span></span> <span data-ttu-id="f199e-109">Das Modell gibt die Schritte an, die erforderlich sind, um Ihre Eingabedaten in eine Vorhersage umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="f199e-109">The model specifies the steps needed to transform your input data into a prediction.</span></span> <span data-ttu-id="f199e-110">Mit ML.NET können Sie ein benutzerdefiniertes Modell trainieren, indem Sie einen Algorithmus angeben, oder Sie können bereits trainierte TensorFlow- und ONNX-Modelle importieren.</span><span class="sxs-lookup"><span data-stu-id="f199e-110">With ML.NET, you can train a custom model by specifying an algorithm, or you can import pre-trained TensorFlow and ONNX models.</span></span>

<span data-ttu-id="f199e-111">Sobald Sie über ein Modell verfügen, können Sie es Ihrer Anwendung hinzufügen, um Vorhersagen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="f199e-111">Once you have a model, you can add it to your application to make the predictions.</span></span>

<span data-ttu-id="f199e-112">ML.NET kann unter Windows, Linux und macOS mit .NET Core oder unter Windows mit .NET Framework ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f199e-112">ML.NET runs on Windows, Linux, and macOS using .NET Core, or Windows using .NET Framework.</span></span> <span data-ttu-id="f199e-113">64-Bit wird auf allen Plattformen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f199e-113">64 bit is supported on all platforms.</span></span> <span data-ttu-id="f199e-114">32-Bit wird unter Windows unterstützt (mit Ausnahme der Funktionen TensorFlow, LightGBM und ONNX).</span><span class="sxs-lookup"><span data-stu-id="f199e-114">32 bit is supported on Windows, except for TensorFlow, LightGBM, and ONNX related functionality.</span></span>

<span data-ttu-id="f199e-115">Beispiele für den Typ von Vorhersagen, die Sie mit ML.NET treffen können:</span><span class="sxs-lookup"><span data-stu-id="f199e-115">Examples of the type of predictions that you can make with ML.NET:</span></span>

|||
|-|-|
|<span data-ttu-id="f199e-116">Klassifizierung/Kategorisierung</span><span class="sxs-lookup"><span data-stu-id="f199e-116">Classification/Categorization</span></span>|<span data-ttu-id="f199e-117">Automatisches Unterteilen von Kundenfeedback in positive und negative Kategorien</span><span class="sxs-lookup"><span data-stu-id="f199e-117">Automatically divide customer feedback into positive and negative categories</span></span>|
|<span data-ttu-id="f199e-118">Regression/Vorhersagen kontinuierlicher Werte</span><span class="sxs-lookup"><span data-stu-id="f199e-118">Regression/Predict continuous values</span></span>|<span data-ttu-id="f199e-119">Vorhersagen des Hauspreises basierend auf Größe und Standort</span><span class="sxs-lookup"><span data-stu-id="f199e-119">Predict the price of houses based on size and location</span></span>|
|<span data-ttu-id="f199e-120">Anomalieerkennung</span><span class="sxs-lookup"><span data-stu-id="f199e-120">Anomaly Detection</span></span>|<span data-ttu-id="f199e-121">Erkennen von betrügerischen Banktransaktionen</span><span class="sxs-lookup"><span data-stu-id="f199e-121">Detect fraudulent banking transactions</span></span> |
|<span data-ttu-id="f199e-122">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="f199e-122">Recommendations</span></span>|<span data-ttu-id="f199e-123">Empfehlen von Produkten, die Onlinekäufern basierend auf ihren vorherigen Käufen wahrscheinlich gerne erwerben würden</span><span class="sxs-lookup"><span data-stu-id="f199e-123">Suggest products that online shoppers may want to buy, based on their previous purchases</span></span>|
|<span data-ttu-id="f199e-124">Zeitreihen/sequenzielle Daten</span><span class="sxs-lookup"><span data-stu-id="f199e-124">Time series/sequential data</span></span>|<span data-ttu-id="f199e-125">Wettervorhersagen/Produktumsatz-Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="f199e-125">Forecast the weather/product sales</span></span>|
|<span data-ttu-id="f199e-126">Bildklassifizierung</span><span class="sxs-lookup"><span data-stu-id="f199e-126">Image classification</span></span>|<span data-ttu-id="f199e-127">Kategorisieren von Pathologien in medizinischen Bildern</span><span class="sxs-lookup"><span data-stu-id="f199e-127">Categorize pathologies in medical images</span></span>|

## <a name="hello-mlnet-world"></a><span data-ttu-id="f199e-128">Hallo ML.NET-Welt</span><span class="sxs-lookup"><span data-stu-id="f199e-128">Hello ML.NET World</span></span>

<span data-ttu-id="f199e-129">Der Code im folgenden Codeausschnitt veranschaulicht die einfachste ML.NET-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="f199e-129">The code in the following snippet demonstrates the simplest ML.NET application.</span></span> <span data-ttu-id="f199e-130">In diesem Beispiel erstellt ein Modell der linearen Regression Hauspreisvorhersagen auf der Basis von Größe- und Preisdaten.</span><span class="sxs-lookup"><span data-stu-id="f199e-130">This example constructs a linear regression model to predict house prices using house size and price data.</span></span> 

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

## <a name="code-workflow"></a><span data-ttu-id="f199e-131">Codeworkflow</span><span class="sxs-lookup"><span data-stu-id="f199e-131">Code workflow</span></span>

<span data-ttu-id="f199e-132">Im folgenden Diagramm werden die Anwendungscodestruktur und der iterative Prozess der Modellentwicklung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="f199e-132">The following diagram represents the application code structure, as well as the iterative process of model development:</span></span>

- <span data-ttu-id="f199e-133">Sammeln und Laden von Trainingsdaten in einem **IDataView**-Objekt</span><span class="sxs-lookup"><span data-stu-id="f199e-133">Collect and load training data into an **IDataView** object</span></span>
- <span data-ttu-id="f199e-134">Angeben einer Pipeline von Vorgängen zum Extrahieren von Features und Anwenden eines Machine Learning-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="f199e-134">Specify a pipeline of operations to extract features and apply a machine learning algorithm</span></span>
- <span data-ttu-id="f199e-135">Trainieren eines Modells durch Aufrufen von **Fit()** auf der Pipeline</span><span class="sxs-lookup"><span data-stu-id="f199e-135">Train a model by calling **Fit()** on the pipeline</span></span>
- <span data-ttu-id="f199e-136">Auswerten des Modells und Iterieren zur Verbesserung</span><span class="sxs-lookup"><span data-stu-id="f199e-136">Evaluate the model and iterate to improve</span></span>
- <span data-ttu-id="f199e-137">Speichern des Modells im Binärformat zur Verwendung in einer Anwendung</span><span class="sxs-lookup"><span data-stu-id="f199e-137">Save the model into binary format, for use in an application</span></span>
- <span data-ttu-id="f199e-138">Rückladen des Modells in ein **ITransformer**-Objekt</span><span class="sxs-lookup"><span data-stu-id="f199e-138">Load the model back into an **ITransformer** object</span></span>
- <span data-ttu-id="f199e-139">Treffen von Vorhersagen durch Aufrufen von **CreatePredictionEngine.Predict()**</span><span class="sxs-lookup"><span data-stu-id="f199e-139">Make predictions by calling **CreatePredictionEngine.Predict()**</span></span>

![ML.NET-Anwendungsentwicklungsfluss einschließlich Komponenten für Datengenerierung, Pipelineentwicklung, Modelltraining, Modellauswertung und Modellverwendung](./media/mldotnet-annotated-workflow.png)

<span data-ttu-id="f199e-141">Wir werden diese Konzepte nun näher betrachten.</span><span class="sxs-lookup"><span data-stu-id="f199e-141">Let's dig a little deeper into those concepts.</span></span>

## <a name="machine-learning-model"></a><span data-ttu-id="f199e-142">Machine Learning-Modell</span><span class="sxs-lookup"><span data-stu-id="f199e-142">Machine learning model</span></span>

<span data-ttu-id="f199e-143">Ein ML.NET-Modell ist ein Objekt, das Transformationen enthält, die auf Ihre Eingabedaten angewendet werden, damit sie die vorhergesagte Ausgabe erreichen.</span><span class="sxs-lookup"><span data-stu-id="f199e-143">An ML.NET model is an object that contains transformations to perform on your input data to arrive at the predicted output.</span></span>

### <a name="basic"></a><span data-ttu-id="f199e-144">Standard</span><span class="sxs-lookup"><span data-stu-id="f199e-144">Basic</span></span>

<span data-ttu-id="f199e-145">Das einfachste Modell ist die zweidimensionale lineare Regression, wobei wie im obigen Hauspreisbeispiel eine kontinuierliche Menge zu einer anderen proportional ist.</span><span class="sxs-lookup"><span data-stu-id="f199e-145">The most basic model is two-dimensional linear regression, where one continuous quantity is proportional to another, as in the house price example above.</span></span>

![Modell der linearen Regression mit Trend- und Gewichtungsparametern](./media/linear-regression-model.svg)

<span data-ttu-id="f199e-147">Das Modell ist einfach: $Price = b + Size \* w$.</span><span class="sxs-lookup"><span data-stu-id="f199e-147">The model is simply: $Price = b + Size \* w$.</span></span> <span data-ttu-id="f199e-148">Die Parameter „$b$“ und „$w$“ werden durch Anpassung einer Linie an eine Gruppe von (size, price)-Paaren geschätzt.</span><span class="sxs-lookup"><span data-stu-id="f199e-148">The parameters $b$ and $w$ are estimated by fitting a line on a set of (size, price) pairs.</span></span> <span data-ttu-id="f199e-149">Die zum Finden der Parameter des Modells verwendeten Daten werden als **Trainingsdaten** bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f199e-149">The data used to find the parameters of the model is called **training data**.</span></span> <span data-ttu-id="f199e-150">Die Eingaben eines Machine Learning-Modells werden als **Features** bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f199e-150">The inputs of a machine learning model are called **features**.</span></span> <span data-ttu-id="f199e-151">In diesem Beispiel ist $Size$ das einzige Feature.</span><span class="sxs-lookup"><span data-stu-id="f199e-151">In this example, $Size$ is the only feature.</span></span> <span data-ttu-id="f199e-152">Die zum Trainieren eines Machine Learning-Modells verwendeten Ground-Truth-Werte werden als **Labels** bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f199e-152">The ground-truth values used to train a machine learning model are called **labels**.</span></span> <span data-ttu-id="f199e-153">Hier sind die $Price$-Werte im Trainingsdataset die Labels.</span><span class="sxs-lookup"><span data-stu-id="f199e-153">Here, the $Price$ values in the training data set are the labels.</span></span>

### <a name="more-complex"></a><span data-ttu-id="f199e-154">Komplexer</span><span class="sxs-lookup"><span data-stu-id="f199e-154">More complex</span></span>

<span data-ttu-id="f199e-155">Ein komplexeres Modell klassifiziert finanzielle Transaktionen mithilfe der Transaktionstextbeschreibung in Kategorien.</span><span class="sxs-lookup"><span data-stu-id="f199e-155">A more complex model classifies financial transactions into categories using the transaction text description.</span></span>

<span data-ttu-id="f199e-156">Jede Transaktionsbeschreibung wird durch Entfernen redundante Wörter und Zeichen und Zählen von Kombinationen aus Word und Zeichen in einen Satz von Features aufgeschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="f199e-156">Each transaction description is broken down into a set of features by removing redundant words and characters, and counting word and character combinations.</span></span> <span data-ttu-id="f199e-157">Die Featuregruppe wird zum Trainieren eines linearen Modells auf der Basis des Kategoriensatzes in den Trainingsdaten verwendet.</span><span class="sxs-lookup"><span data-stu-id="f199e-157">The feature set is used to train a linear model based on the set of categories in the training data.</span></span> <span data-ttu-id="f199e-158">Je mehr eine neue Beschreibung denjenigen im Trainingssatz ähnelt, desto eher wird sie derselben Kategorie zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f199e-158">The more similar a new description is to the ones in the training set, the more likely it will be assigned to the same category.</span></span>

![Textklassifizierungsmodell](./media/text-classification-model.svg)

<span data-ttu-id="f199e-160">Hauspreismodell und Textklassifizierungsmodell sind beide **lineare** Modelle.</span><span class="sxs-lookup"><span data-stu-id="f199e-160">Both the house price model and the text classification model are **linear** models.</span></span> <span data-ttu-id="f199e-161">Je nach Art Ihrer Daten und des Problems, das Sie lösen, können Sie auch **Entscheidungsstrukturmodelle**, verallgemeinert **additive** Modelle, und andere verwenden.</span><span class="sxs-lookup"><span data-stu-id="f199e-161">Depending on the nature of your data and the problem you are solving, you can also use **decision tree** models, **generalized additive** models, and others.</span></span> <span data-ttu-id="f199e-162">Weitere Informationen zu den Modellen finden Sie unter [Aufgaben](./resources/tasks.md).</span><span class="sxs-lookup"><span data-stu-id="f199e-162">You can find out more about the models in [Tasks](./resources/tasks.md).</span></span>

## <a name="data-preparation"></a><span data-ttu-id="f199e-163">Datenvorbereitung</span><span class="sxs-lookup"><span data-stu-id="f199e-163">Data preparation</span></span>

<span data-ttu-id="f199e-164">In den meisten Fällen können die Daten, die Ihnen zur Verfügung stehen, nicht direkt zum Trainieren von Machine Learning-Modellen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f199e-164">In most cases, the data that you have available isn't suitable to be used directly to train a machine learning model.</span></span> <span data-ttu-id="f199e-165">Die unformatierten Daten müssen vorbereitet, d.h. vorverarbeitet werden, bevor Sie sie verwenden können, um die Parameter Ihres Modells zu finden.</span><span class="sxs-lookup"><span data-stu-id="f199e-165">The raw data needs to be prepared, or pre-processed before it can be used to find the parameters of your model.</span></span> <span data-ttu-id="f199e-166">Möglicherweise müssen Ihre Daten von Zeichenfolgenwerten in eine numerische Darstellung konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="f199e-166">Your data may need to be converted from string values to a numerical representation.</span></span> <span data-ttu-id="f199e-167">Vielleicht enthalten Ihre Eingabedaten redundante Informationen.</span><span class="sxs-lookup"><span data-stu-id="f199e-167">You might have redundant information in your input data.</span></span> <span data-ttu-id="f199e-168">Sie müssen möglicherweise die Dimensionen der Eingabedaten reduzieren oder erweitern.</span><span class="sxs-lookup"><span data-stu-id="f199e-168">You may need to reduce or expand the dimensions of your input data.</span></span> <span data-ttu-id="f199e-169">Ihre Daten müssen vielleicht normalisiert oder skaliert werden.</span><span class="sxs-lookup"><span data-stu-id="f199e-169">Your data might need to be normalized or scaled.</span></span>

<span data-ttu-id="f199e-170">Die [ML.NET-Tutorials](./tutorials/index.md) informieren Sie über verschiedene Datenverarbeitungspipelines für Text-, Bild-, numerische und Zeitreihendaten, die für bestimmte Machine Learning-Aufgaben verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f199e-170">The [ML.NET tutorials](./tutorials/index.md) teach you about different data processing pipelines for text, image, numerical, and time-series data used for specific machine learning tasks.</span></span>

<span data-ttu-id="f199e-171">Unter [Vorbereiten von Daten](./how-to-guides/prepare-data-ml-net.md) finden Sie allgemeinere Informationen zur Anwendung der Datenvorbereitung.</span><span class="sxs-lookup"><span data-stu-id="f199e-171">[How to prepare your data](./how-to-guides/prepare-data-ml-net.md) shows you how to applied data preparation more generally.</span></span>

<span data-ttu-id="f199e-172">Im Ressourcenabschnitt finden Sie einen Anhang mit allen [verfügbaren Transformationen](./resources/transforms.md).</span><span class="sxs-lookup"><span data-stu-id="f199e-172">You can find an appendix of all of the [available transformations](./resources/transforms.md) in the resources section.</span></span>

## <a name="model-evaluation"></a><span data-ttu-id="f199e-173">Modellauswertung</span><span class="sxs-lookup"><span data-stu-id="f199e-173">Model evaluation</span></span>

<span data-ttu-id="f199e-174">Wie können Sie nach dem Trainieren Ihres Modells wissen, wie gut es zukünftige Vorhersagen treffen wird?</span><span class="sxs-lookup"><span data-stu-id="f199e-174">Once you have trained your model, how do you know how well it will make future predictions?</span></span> <span data-ttu-id="f199e-175">Mit ML.NET können Sie Ihr Modell anhand einiger neuer Testdaten auswerten.</span><span class="sxs-lookup"><span data-stu-id="f199e-175">With ML.NET, you can evaluate your model against some new test data.</span></span>

<span data-ttu-id="f199e-176">Jede Art von Machine Learning-Aufgabe verfügt über Metriken zum Auswerten der Genauigkeit des Modells anhand eines Testdatasets.</span><span class="sxs-lookup"><span data-stu-id="f199e-176">Each type of machine learning task has metrics used to evaluate the accuracy and precision of the model against the test data set.</span></span>

<span data-ttu-id="f199e-177">In unserem Hauspreisbeispiel haben wir die **Regressionsaufgabe** verwendet.</span><span class="sxs-lookup"><span data-stu-id="f199e-177">For our house price example, we used the **Regression** task.</span></span> <span data-ttu-id="f199e-178">Um das Modell auszuwerten, fügen Sie dem ursprünglichen Beispiel den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="f199e-178">To evaluate the model, add the following code to the original sample.</span></span>

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

<span data-ttu-id="f199e-179">Die Auswertungsmetriken zeigen, dass der Fehler gering ist, und dass die Korrelation zwischen der vorhergesagten Ausgabe und der Testausgabe hoch ist.</span><span class="sxs-lookup"><span data-stu-id="f199e-179">The evaluation metrics tell you that the error is low-ish, and that correlation between the predicted output and the test output is high.</span></span> <span data-ttu-id="f199e-180">Nun, das war einfach.</span><span class="sxs-lookup"><span data-stu-id="f199e-180">That was easy!</span></span> <span data-ttu-id="f199e-181">In realen Beispielen sind weitere Optimierungen erforderlich, um gute Modellmetriken zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="f199e-181">In real examples, it takes more tuning to achieve good model metrics.</span></span>

## <a name="mlnet-architecture"></a><span data-ttu-id="f199e-182">ML.NET-Architektur</span><span class="sxs-lookup"><span data-stu-id="f199e-182">ML.NET architecture</span></span>

<span data-ttu-id="f199e-183">In diesem Abschnitt behandeln wir die Architekturmuster von ML.NET.</span><span class="sxs-lookup"><span data-stu-id="f199e-183">In this section, we go through the architectural patterns of ML.NET.</span></span> <span data-ttu-id="f199e-184">Wenn Sie ein erfahrener .NET-Entwickler sind, werden Ihnen einige dieser Muster vertraut und einige weniger vertraut sein.</span><span class="sxs-lookup"><span data-stu-id="f199e-184">If you are an experienced .NET developer, some of these patterns will be familiar to you, and some will be less familiar.</span></span> <span data-ttu-id="f199e-185">Halten Sie sich fest, es geht sofort los!</span><span class="sxs-lookup"><span data-stu-id="f199e-185">Hold tight, while we dive in!</span></span>

<span data-ttu-id="f199e-186">Eine ML.NET-Anwendung beginnt mit einem <xref:Microsoft.ML.MLContext>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="f199e-186">An ML.NET application starts with an <xref:Microsoft.ML.MLContext> object.</span></span> <span data-ttu-id="f199e-187">Dieses Singletonobjekt enthält **Kataloge**.</span><span class="sxs-lookup"><span data-stu-id="f199e-187">This singleton object contains **catalogs**.</span></span> <span data-ttu-id="f199e-188">Ein Katalog ist eine Factory zum Laden und Speichern von Daten, für Transformationen, Trainer und Modellvorgangskomponenten.</span><span class="sxs-lookup"><span data-stu-id="f199e-188">A catalog is a factory for data loading and saving, transforms, trainers, and model operation components.</span></span> <span data-ttu-id="f199e-189">Jedes Katalogobjekt verfügt über Methoden, um die verschiedenen Typen von Komponenten zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="f199e-189">Each catalog object has methods to create the different types of components:</span></span>

|||||
|-|-|-|-|
|<span data-ttu-id="f199e-190">Laden und Speichern von Daten</span><span class="sxs-lookup"><span data-stu-id="f199e-190">Data loading and saving</span></span>||<xref:Microsoft.ML.DataOperationsCatalog>||
|<span data-ttu-id="f199e-191">Datenvorbereitung</span><span class="sxs-lookup"><span data-stu-id="f199e-191">Data preparation</span></span>||<xref:Microsoft.ML.TransformsCatalog>||
|<span data-ttu-id="f199e-192">Trainingsalgorithmen</span><span class="sxs-lookup"><span data-stu-id="f199e-192">Training algorithms</span></span>|<span data-ttu-id="f199e-193">Binäre Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="f199e-193">Binary classification</span></span>|<xref:Microsoft.ML.BinaryClassificationCatalog>||
||<span data-ttu-id="f199e-194">Multiklassenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="f199e-194">Multiclass classification</span></span>|<xref:Microsoft.ML.MulticlassClassificationCatalog>||
||<span data-ttu-id="f199e-195">Anomalieerkennung</span><span class="sxs-lookup"><span data-stu-id="f199e-195">Anomaly detection</span></span>|<xref:Microsoft.ML.AnomalyDetectionCatalog>||
||<span data-ttu-id="f199e-196">Clusterbildung</span><span class="sxs-lookup"><span data-stu-id="f199e-196">Clustering</span></span>|<xref:Microsoft.ML.ClusteringCatalog>||
||<span data-ttu-id="f199e-197">Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="f199e-197">Forecasting</span></span>|<xref:Microsoft.ML.ForecastingCatalog>||
||<span data-ttu-id="f199e-198">Rangfolge</span><span class="sxs-lookup"><span data-stu-id="f199e-198">Ranking</span></span>|<xref:Microsoft.ML.RankingCatalog>||
||<span data-ttu-id="f199e-199">Regression</span><span class="sxs-lookup"><span data-stu-id="f199e-199">Regression</span></span>|<xref:Microsoft.ML.RegressionCatalog>||
||<span data-ttu-id="f199e-200">Empfehlung</span><span class="sxs-lookup"><span data-stu-id="f199e-200">Recommendation</span></span>|<xref:Microsoft.ML.RecommendationCatalog>|<span data-ttu-id="f199e-201">`Microsoft.ML.Recommender`-NuGet-Paket hinzufügen</span><span class="sxs-lookup"><span data-stu-id="f199e-201">add the `Microsoft.ML.Recommender` NuGet package</span></span>|
||<span data-ttu-id="f199e-202">TimeSeries</span><span class="sxs-lookup"><span data-stu-id="f199e-202">TimeSeries</span></span>|<xref:Microsoft.ML.TimeSeriesCatalog>|<span data-ttu-id="f199e-203">`Microsoft.ML.TimeSeries`-NuGet-Paket hinzufügen</span><span class="sxs-lookup"><span data-stu-id="f199e-203">add the `Microsoft.ML.TimeSeries` NuGet package</span></span>|
|<span data-ttu-id="f199e-204">Modellverwendung</span><span class="sxs-lookup"><span data-stu-id="f199e-204">Model usage</span></span> ||<xref:Microsoft.ML.ModelOperationsCatalog>||

<span data-ttu-id="f199e-205">Sie können in jeder der oben genannten Kategorien zu den Erstellungsmethoden navigieren.</span><span class="sxs-lookup"><span data-stu-id="f199e-205">You can navigate to the creation methods in each of the above categories.</span></span> <span data-ttu-id="f199e-206">Bei Verwendung von Visual Studio werden die Kataloge über IntelliSense angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f199e-206">Using Visual Studio, the catalogs show up via IntelliSense.</span></span>

   ![IntelliSense für Regressionstrainer](./media/catalog-intellisense.png)

### <a name="build-the-pipeline"></a><span data-ttu-id="f199e-208">Erstellen der Pipeline</span><span class="sxs-lookup"><span data-stu-id="f199e-208">Build the pipeline</span></span>

<span data-ttu-id="f199e-209">In jedem Katalog befindet sich eine Reihe von Erweiterungsmethoden.</span><span class="sxs-lookup"><span data-stu-id="f199e-209">Inside each catalog is a set of extension methods.</span></span> <span data-ttu-id="f199e-210">Wir untersuchen, wie Erweiterungsmethoden zum Erstellen einer Trainingspipeline verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f199e-210">Let's look at how extension methods are used to create a training pipeline.</span></span>

```csharp
    var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
        .Append(mlContext.Regression.Trainers.Sdca(labelColumnName: "Price", maximumNumberOfIterations: 100));
```

<span data-ttu-id="f199e-211">Im Codeausschnitt sind `Concatenate` und `Sdca` Methoden im Katalog.</span><span class="sxs-lookup"><span data-stu-id="f199e-211">In the snippet, `Concatenate` and `Sdca` are both methods in the catalog.</span></span> <span data-ttu-id="f199e-212">Sie erstellen jeweils ein [IEstimator](xref:Microsoft.ML.IEstimator%601)-Objekt, das der Pipeline angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="f199e-212">They each create an [IEstimator](xref:Microsoft.ML.IEstimator%601) object that is appended to the pipeline.</span></span>

<span data-ttu-id="f199e-213">An diesem Punkt werden die Objekte nur erstellt.</span><span class="sxs-lookup"><span data-stu-id="f199e-213">At this point, the objects are created only.</span></span> <span data-ttu-id="f199e-214">Es hat keine Ausführung stattgefunden.</span><span class="sxs-lookup"><span data-stu-id="f199e-214">No execution has happened.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="f199e-215">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="f199e-215">Train the model</span></span>

<span data-ttu-id="f199e-216">Nachdem die Objekte in der Pipeline erstellt wurden, können Daten zum Trainieren des Modells verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f199e-216">Once the objects in the pipeline have been created, data can be used to train the model.</span></span>

```csharp
    var model = pipeline.Fit(trainingData);
```

<span data-ttu-id="f199e-217">Beim Aufruf von `Fit()` werden die Eingabetrainingsdaten verwendet, um die Parameter des Modells zu schätzen.</span><span class="sxs-lookup"><span data-stu-id="f199e-217">Calling `Fit()` uses the input training data to estimate the parameters of the model.</span></span> <span data-ttu-id="f199e-218">Dies wird als Trainieren des Modells bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f199e-218">This is known as training the model.</span></span> <span data-ttu-id="f199e-219">Beachten Sie, dass das Modell der linearen Regression oben zwei Modellparameter hatte: **Trend** und **Gewichtung**.</span><span class="sxs-lookup"><span data-stu-id="f199e-219">Remember, the linear regression model above had two model parameters: **bias** and **weight**.</span></span> <span data-ttu-id="f199e-220">Nach dem `Fit()`-Aufruf sind die Werte der Parameter bekannt.</span><span class="sxs-lookup"><span data-stu-id="f199e-220">After the `Fit()` call, the values of the parameters are known.</span></span> <span data-ttu-id="f199e-221">Die meisten Modelle haben viel mehr Parameter als dieses.</span><span class="sxs-lookup"><span data-stu-id="f199e-221">Most models will have many more parameters than this.</span></span>

<span data-ttu-id="f199e-222">Weitere Informationen über das Modelltraining finden Sie unter [Trainieren und Auswerten eines Modells](./how-to-guides/train-machine-learning-model-ml-net.md).</span><span class="sxs-lookup"><span data-stu-id="f199e-222">You can learn more about model training in [How to train your model](./how-to-guides/train-machine-learning-model-ml-net.md)</span></span>

<span data-ttu-id="f199e-223">Das resultierende Modellobjekt implementiert die <xref:Microsoft.ML.ITransformer>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="f199e-223">The resulting model object implements the <xref:Microsoft.ML.ITransformer> interface.</span></span> <span data-ttu-id="f199e-224">Das Modell transformiert also Eingabedaten in Vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="f199e-224">That is, the model transforms input data into predictions.</span></span>

```csharp
   IDataView predictions = model.Transform(inputData);
```

### <a name="use-the-model"></a><span data-ttu-id="f199e-225">Verwenden des Modells</span><span class="sxs-lookup"><span data-stu-id="f199e-225">Use the model</span></span>

<span data-ttu-id="f199e-226">Sie können Eingabedaten in einem Massenvorgang in Vorhersagen umwandeln oder jede Eingabe einzeln.</span><span class="sxs-lookup"><span data-stu-id="f199e-226">You can transform input data into predictions in bulk, or one input at a time.</span></span> <span data-ttu-id="f199e-227">Im Hauspreisbeispiel haben wir beides getan: im Massenvorgang zum Auswerten des Modells und einzeln, um eine neue Vorhersage zu treffen.</span><span class="sxs-lookup"><span data-stu-id="f199e-227">In the house price example, we did both: in bulk for the purpose of evaluating the model, and one at a time to make a new prediction.</span></span> <span data-ttu-id="f199e-228">Wir betrachten nun die einzelnen Vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="f199e-228">Let's look at making single predictions.</span></span>

```csharp
    var size = new HouseData() { Size = 2.5F };
    var predEngine = mlContext.CreatePredictionEngine<HouseData, Prediction>(model);
    var price = predEngine.Predict(size);
```

<span data-ttu-id="f199e-229">Die `CreatePredictionEngine()`-Methode nimmt eine Eingabe- und eine Ausgabeklasse entgegen.</span><span class="sxs-lookup"><span data-stu-id="f199e-229">The `CreatePredictionEngine()` method takes an input class and an output class.</span></span> <span data-ttu-id="f199e-230">Die Feldnamen und/oder Codeattribute bestimmen die Namen der Datenspalten, die beim Trainieren des Modells und der Vorhersage verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f199e-230">The field names and/or code attributes determine the names of the data columns used during model training and prediction.</span></span> <span data-ttu-id="f199e-231">Weitere Informationen finden Sie unter [Treffen von Vorhersagen mit einem trainierten Modell](./how-to-guides/single-predict-model-ml-net.md).</span><span class="sxs-lookup"><span data-stu-id="f199e-231">You can read about  [How to make a single prediction](./how-to-guides/single-predict-model-ml-net.md) in the How-to section.</span></span>

### <a name="data-models-and-schema"></a><span data-ttu-id="f199e-232">Datenmodelle und Schema</span><span class="sxs-lookup"><span data-stu-id="f199e-232">Data models and schema</span></span>

<span data-ttu-id="f199e-233">Das Herzstück einer ML.NET-Machine Learning-Pipeline sind [DataView](xref:Microsoft.ML.IDataView)-Objekte.</span><span class="sxs-lookup"><span data-stu-id="f199e-233">At the core of an ML.NET machine learning pipeline are [DataView](xref:Microsoft.ML.IDataView) objects.</span></span>

<span data-ttu-id="f199e-234">Jede Transformation in der Pipeline weist ein Eingabeschema (Datennamen, -typen und -größen, die die Transformation bei der Eingabe erwartet) und ein Ausgabeschema (nach der Transformation erzeugte Datennamen, -typen und -größen) auf.</span><span class="sxs-lookup"><span data-stu-id="f199e-234">Each transformation in the pipeline has an input schema (data names, types, and sizes that the transform expects to see on its input); and an output schema (data names, types, and sizes that the transform produces after the transformation).</span></span> <span data-ttu-id="f199e-235">Das folgende Dokument enthält eine ausführliche Erläuterung der [Schnittstelle IDataView und deren Typsystem](https://xadupre.github.io/machinelearningext/mlnetdocs/idataviewtypesystem.html).</span><span class="sxs-lookup"><span data-stu-id="f199e-235">The following document provides an in-depth explanation of the [IDataView interface and its type system](https://xadupre.github.io/machinelearningext/mlnetdocs/idataviewtypesystem.html).</span></span>

<span data-ttu-id="f199e-236">Wenn das Ausgabeschema einer Transformation in der Pipeline nicht dem Eingabeschema der nächsten Transformation entspricht, löst ML.NET eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="f199e-236">If the output schema from one transform in the pipeline doesn't match the input schema of the next transform, ML.NET will throw an exception.</span></span>

<span data-ttu-id="f199e-237">Ein Datenansichtsobjekt enthält Spalten und Zeilen.</span><span class="sxs-lookup"><span data-stu-id="f199e-237">A data view object has columns and rows.</span></span> <span data-ttu-id="f199e-238">Jede Spalte hat einen Namen, einen Typ und eine Länge.</span><span class="sxs-lookup"><span data-stu-id="f199e-238">Each column has a name and a type and a length.</span></span> <span data-ttu-id="f199e-239">Beispiel: die Eingabespalten im Hauspreisbeispiel sind **Size** und **Price** („Größe“ und „Preis“).</span><span class="sxs-lookup"><span data-stu-id="f199e-239">For example: the input columns in the house price example are **Size** and **Price**.</span></span> <span data-ttu-id="f199e-240">Beide sind Typen, und sie sind eher Skalar- als Vektormengen.</span><span class="sxs-lookup"><span data-stu-id="f199e-240">They are both type  and they are scalar quantities rather than vector ones.</span></span>

   ![Beispiel der ML.NET-Datenansicht mit Hauspreis-Vorhersagedaten](./media/ml-net-dataview.png)

<span data-ttu-id="f199e-242">Alle ML.NET-Algorithmen suchen nach einer Eingabespalte, die ein Vektor ist.</span><span class="sxs-lookup"><span data-stu-id="f199e-242">All ML.NET algorithms look for an input column that is a vector.</span></span> <span data-ttu-id="f199e-243">Standardmäßig wird diese Vektorspalte mit **Features** bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f199e-243">By default this vector column is called **Features**.</span></span> <span data-ttu-id="f199e-244">Darum haben wir in unserem Hauspreisbeispiel die Spalte **Size** in eine neue Spalte namens **Features** verkettet.</span><span class="sxs-lookup"><span data-stu-id="f199e-244">This is why we concatenated the **Size** column into a new column called **Features** in our house price example.</span></span>

 ```csharp
    var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
 ```

<span data-ttu-id="f199e-245">Alle Algorithmen erstellen auch neue Spalten, nachdem sie eine Vorhersage ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="f199e-245">All algorithms also create new columns after they have performed a prediction.</span></span> <span data-ttu-id="f199e-246">Die festgelegten Namen dieser neuen Spalten hängen vom Typ des Machine Learning-Algorithmus ab.</span><span class="sxs-lookup"><span data-stu-id="f199e-246">The fixed names of these new columns depend on the type of machine learning algorithm.</span></span> <span data-ttu-id="f199e-247">Für die Regressionsaufgabe wird eine der neuen Spalten mit **Score**.</span><span class="sxs-lookup"><span data-stu-id="f199e-247">For the regression task, one of the new columns is called **Score**.</span></span> <span data-ttu-id="f199e-248">Darum haben wir unseren Preisdaten diesen Namen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="f199e-248">This is why we attributed our price data with this name.</span></span>

```csharp
    public class Prediction
    {
        [ColumnName("Score")]
        public float Price { get; set; }
    }
```

<span data-ttu-id="f199e-249">Weitere Informationen über Ausgabespalten anderer Machine Learning-Aufgaben finden Sie im Handbuch [Machine Learning-Aufgaben in ML.NET](resources/tasks.md).</span><span class="sxs-lookup"><span data-stu-id="f199e-249">You can find out more about output columns of different machine learning tasks in the [Machine Learning Tasks](resources/tasks.md) guide.</span></span>

<span data-ttu-id="f199e-250">Eine wichtige Eigenschaft von DataView-Objekten ist, dass sie **verzögert** ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="f199e-250">An important property of DataView objects is that they are evaluated **lazily**.</span></span> <span data-ttu-id="f199e-251">Datenansichten werden nur beim Trainieren und Auswerten des Modells und bei der Datenvorhersage geladen und verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="f199e-251">Data views are only loaded and operated on during model training and evaluation, and data prediction.</span></span> <span data-ttu-id="f199e-252">Beim Schreiben und Testen Ihrer ML.NET-Anwendung können Sie mit dem Visual Studio-Debugger einen Blick auf jedes Datenansichtsobjekt werfen, indem Sie die [Preview](xref:Microsoft.ML.DebuggerExtensions.Preview*)-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f199e-252">While you are writing and testing your ML.NET application, you can use the Visual Studio debugger to take a peek at any data view object by calling the [Preview](xref:Microsoft.ML.DebuggerExtensions.Preview*) method.</span></span>

```csharp
    var debug = testPriceDataView.Preview();
```

<span data-ttu-id="f199e-253">Sie können die `debug`-Variable im Debugger beobachten und ihren Inhalt untersuchen.</span><span class="sxs-lookup"><span data-stu-id="f199e-253">You can watch the `debug` variable in the debugger and examine its contents.</span></span> <span data-ttu-id="f199e-254">Verwenden Sie die Preview-Methode nicht im Produktionscode, da sie die Leistung erheblich beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="f199e-254">Do not use the Preview method in production code, as it significantly degrades performance.</span></span>

### <a name="model-deployment"></a><span data-ttu-id="f199e-255">Modellbereitstellung</span><span class="sxs-lookup"><span data-stu-id="f199e-255">Model Deployment</span></span>

<span data-ttu-id="f199e-256">In realen Anwendungen sind Ihr Modelltrainings- und Auswertungscode von Ihrer Vorhersage getrennt.</span><span class="sxs-lookup"><span data-stu-id="f199e-256">In real-life applications, your model training and evaluation code will be separate from your prediction.</span></span> <span data-ttu-id="f199e-257">Diese beiden Aktivitäten werden in der Tat häufig durch separate Teams ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f199e-257">In fact, these two activities are often performed by separate teams.</span></span> <span data-ttu-id="f199e-258">Ihr Modellbereitstellungsteam kann das Modell zur Verwendung in der Vorhersageanwendung speichern.</span><span class="sxs-lookup"><span data-stu-id="f199e-258">Your model development team can save the model for use in the prediction application.</span></span>

```csharp
   mlContext.Model.Save(model, trainingData.Schema,"model.zip");
```

## <a name="next-steps"></a><span data-ttu-id="f199e-259">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f199e-259">Next steps</span></span>

* <span data-ttu-id="f199e-260">Erfahren Sie in den [Tutorials](./tutorials/index.md), wie Sie mit anderen Machine Learning-Aufgaben Anwendungen mit realistischeren Datasets erstellen.</span><span class="sxs-lookup"><span data-stu-id="f199e-260">Learn how to build applications using different machine learning tasks with more realistic data sets in the [tutorials](./tutorials/index.md).</span></span>

* <span data-ttu-id="f199e-261">Informieren Sie sich in den [Schrittanleitungen](./how-to-guides/index.md) ausführlicher über bestimmte Themen.</span><span class="sxs-lookup"><span data-stu-id="f199e-261">Learn about specific topics in more depth in the [How To Guides](./how-to-guides/index.md).</span></span>

* <span data-ttu-id="f199e-262">Wenn Sie extrem interessiert sind, können Sie direkt in die [API-Referenzdokumentation](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet) eintauchen.</span><span class="sxs-lookup"><span data-stu-id="f199e-262">If you're super keen, you can dive straight into the [API Reference documentation](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet).</span></span>
