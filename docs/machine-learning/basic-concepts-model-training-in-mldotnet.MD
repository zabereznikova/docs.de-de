---
title: Basiskonzepte für das Modelltraining in ML.NET
description: In diesem Artikel werden die grundlegenden Konzepte für Szenarios für *Modelltraining* in ML.NET erläutert. Nicht alle Konzepte sind für das einfachere Szenario für die *Vorhersage mit einem vorhandenen Modell* relevant.
ms.date: 02/13/2019
ms.topic: overview
ms.custom: mvc
ms.openlocfilehash: c47d5832527dca1416abfc55756dca48f1daf493
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2019
ms.locfileid: "56303659"
---
# <a name="basic-concepts-for-model-training-in-mlnet"></a><span data-ttu-id="3d0bd-104">Basiskonzepte für das Modelltraining in ML.NET</span><span class="sxs-lookup"><span data-stu-id="3d0bd-104">Basic concepts for model training in ML.NET</span></span>

<span data-ttu-id="3d0bd-105">In diesem Artikel werden die grundlegenden Konzepte für Szenarios für *Modelltraining* in ML.NET erläutert.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-105">This article explains the basic concepts covering *model training* scenarios in ML.NET.</span></span> <span data-ttu-id="3d0bd-106">Nicht alle Konzepte sind für das einfachere Szenario für die *Vorhersage mit einem vorhandenen Modell* relevant.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-106">Not all concepts are relevant to the more simple scenario of *prediction with an existing model*.</span></span>

## <a name="model-training-concepts"></a><span data-ttu-id="3d0bd-107">Konzepte für das Modelltraining</span><span class="sxs-lookup"><span data-stu-id="3d0bd-107">Model training concepts</span></span>

<span data-ttu-id="3d0bd-108">In dieser Dokumentation werden folgende Konzepte im Zusammenhang mit dem Modelltraining in ML.NET erläutert:</span><span class="sxs-lookup"><span data-stu-id="3d0bd-108">This document covers the following concepts related to model training in ML.NET:</span></span>

- <span data-ttu-id="3d0bd-109">[*Data*](#data) (Daten) als `IDataView`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-109">[*Data*](#data) represented as an `IDataView` interface.</span></span>
  - <span data-ttu-id="3d0bd-110">In ML.NET ähneln die Daten einer SQL-Ansicht: Es handelt sich um ein unveränderliches, cursorfähiges, heterogenes und schematisiertes Dataset, das verzögert ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-110">In ML.NET, data is similar to a SQL view: It's a lazily evaluated, immutable, cursorable, heterogenous, schematized dataset.</span></span> 
  - <span data-ttu-id="3d0bd-111">Eine hervorragende Dokumentation zur Data-Schnittstelle finden Sie unter [IDataView Design Principles (Entwurfsprinzipien von IDataView)](https://github.com/dotnet/machinelearning/blob/master/docs/code/IDataViewDesignPrinciples.md).</span><span class="sxs-lookup"><span data-stu-id="3d0bd-111">An excellent document about the data interface is [IDataView Design Principles](https://github.com/dotnet/machinelearning/blob/master/docs/code/IDataViewDesignPrinciples.md).</span></span>
- <span data-ttu-id="3d0bd-112">[*Transformer*](#transformer) (Transformator) als `ITransformer`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-112">[*Transformer*](#transformer) represented as `ITransformer` interface.</span></span>
  - <span data-ttu-id="3d0bd-113">Transformatoren sind Komponenten, die Daten erfassen, bearbeiten und anschließend neue, transformierte Daten zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-113">A transformer is a component that takes data, does some work on it, and returns new transformed data.</span></span>
  - <span data-ttu-id="3d0bd-114">Sie können sich ein Machine Learning-Modell beispielsweise als Transformator vorstellen, der Features erfasst und Vorhersagen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-114">For example, you can think of a machine learning model as a transformer that takes features and returns predictions.</span></span>
  - <span data-ttu-id="3d0bd-115">Ein weiteres Beispiel ist der Text-Tokenizer, der eine einzelne Textspalte verwendet und eine Vektorspalte mit einzelnen Wörtern ausgibt, die aus dem Text extrahiert wurden.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-115">Another example, text tokenizer takes a single text column and outputs a vector column with individual words extracted out of the texts.</span></span>
- <span data-ttu-id="3d0bd-116">[*Data reader*](#data-reader) (Datenleser) als `IDataReader<T>`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-116">[*Data reader*](#data-reader) represented as an `IDataReader<T>` interface.</span></span>
  - <span data-ttu-id="3d0bd-117">Der Datenleser ist die ML.NET-Komponente zum Erstellen von Daten.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-117">The data reader is ML.NET component to create data.</span></span> <span data-ttu-id="3d0bd-118">Sie verwendet eine Instanz von `T` und gibt Daten aus dieser zurück.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-118">It takes an instance of `T` and returns data out of it.</span></span> 
  - <span data-ttu-id="3d0bd-119">Eine *TextLoader*-Klasse ist beispielsweise `IDataReader<IMultiStreamSource>`.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-119">For example, a *TextLoader* is an `IDataReader<IMultiStreamSource>`.</span></span> <span data-ttu-id="3d0bd-120">Sie erfasst die Quelle und erzeugt Daten.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-120">It takes the source and produces data.</span></span> 
- <span data-ttu-id="3d0bd-121">[*Estimator*](#estimator) als `IEstimator<T>`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-121">[*Estimator*](#estimator) represented as an `IEstimator<T>` interface.</span></span>
  - <span data-ttu-id="3d0bd-122">Dieses Objekt lernt anhand von Daten.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-122">This is an object that learns from data.</span></span> <span data-ttu-id="3d0bd-123">Das Ergebnis des Lernvorgangs ist ein *Transformator*.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-123">The result of the learning is a *transformer*.</span></span>
  - <span data-ttu-id="3d0bd-124">Sie können sich einen Machine Learning-*Algorithmus* als Estimator-Objekt vorstellen, das anhand von Daten lernt und ein Machine Learning-*Modell* erzeugt.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-124">You can think of a machine learning *algorithm* as an estimator that learns on data and produces a machine learning *model*.</span></span>
- <span data-ttu-id="3d0bd-125">[*Vorhersagefunktion*](#prediction-function) als `PredictionEngine<TSrc, TDst>`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-125">[*Prediction function*](#prediction-function) represented as a `PredictionEngine<TSrc, TDst>` class.</span></span>
  - <span data-ttu-id="3d0bd-126">Die Vorhersagefunktion kann als Computer interpretiert werden, der einen Transformator auf eine Zeile anwendet, z. B. zum Zeitpunkt der Vorhersage.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-126">The prediction function can be seen as a machine that applies a transformer to one row, such as at prediction time.</span></span>

## <a name="data"></a><span data-ttu-id="3d0bd-127">Daten</span><span class="sxs-lookup"><span data-stu-id="3d0bd-127">Data</span></span>

<span data-ttu-id="3d0bd-128">In ML.NET ähneln die Daten einer SQL-Ansicht: Es handelt sich um ein cursorfähiges, heterogenes und schematisiertes Dataset, das verzögert ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-128">In ML.NET, data is similar to a SQL view: It's a lazily evaluated, cursorable, heterogenous, schematized dataset.</span></span>

- <span data-ttu-id="3d0bd-129">Dieses verfügt über ein *Schema* (eine Instanz einer `ISchema`-Schnittstelle), das die Informationen zu den Spalten der Datenansicht enthält.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-129">It has *Schema* (an instance of an `ISchema` interface) that contains the information about the data view's columns.</span></span>
  - <span data-ttu-id="3d0bd-130">Jede Spalte verfügt über einen *Namen*, einen *Typ* und arbiträre *Metadaten*, die ihr zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-130">Each column has a *Name*, a *Type*, and an arbitrary set of *metadata* associated with it.</span></span>
  - <span data-ttu-id="3d0bd-131">Die *Metadaten* der Spalte enthalten Informationen wie Namen der Slots einer Vektorspalte und ähnliches.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-131">The column's *metadata* contains information like slot names of a vector column and the like.</span></span> <span data-ttu-id="3d0bd-132">Die Metadaten selbst werden als andere einzeilige *Daten* dargestellt, die für jede Spalte eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-132">The metadata itself is represented as another one-row *data* that is unique to each column.</span></span>
  - <span data-ttu-id="3d0bd-133">Die Datenansicht ist eine Quelle für *Cursor*.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-133">The data view is a source of *cursors*.</span></span> <span data-ttu-id="3d0bd-134">Sie können sich das wie SQL-Cursor vorstellen: Ein Cursor ist ein Objekt, das die Daten zeilenweise durchläuft und die verfügbaren Daten anzeigt.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-134">Think SQL cursors: A cursor is an object that iterates through the data, one row at a time, and presents the available data.</span></span>
  - <span data-ttu-id="3d0bd-135">Daten können natürlich so viele aktive Cursor wie nötig enthalten.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-135">Naturally, data can have as many active cursors over it as needed.</span></span> <span data-ttu-id="3d0bd-136">Da die Daten selbst unveränderlich sind, sind Cursor vollkommen unabhängig.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-136">Since data itself is immutable, cursors are truly independent.</span></span>
  - <span data-ttu-id="3d0bd-137">Cursor greifen in der Regel nur auf eine Teilmenge der Spalten zu: Aus Effizienzgründen verarbeitet ML.NET nur die Werte aus Spalten, die für den Cursor erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-137">Cursors typically access only a subset of columns: For efficiency, ML.NET computes only the values of columns that are needed by the cursor.</span></span>

## <a name="transformer"></a><span data-ttu-id="3d0bd-138">Transformator</span><span class="sxs-lookup"><span data-stu-id="3d0bd-138">Transformer</span></span>

<span data-ttu-id="3d0bd-139">Transformatoren sind Komponenten, die Daten erfassen, bearbeiten und anschließend neue, transformierte Daten zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-139">A transformer is a component that takes data, does some work on it, and returns new transformed data.</span></span>

<span data-ttu-id="3d0bd-140">In ML.NET verarbeiten die meisten Transformatoren in der Regel jeweils eine *Eingabespalte* und erzeugen die *Ausgabespalte*.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-140">Most transformers in ML.NET tend to operate on one *input column* at a time, and produce the *output column*.</span></span> <span data-ttu-id="3d0bd-141">`new HashTransformer("bar", "foo")` nimmt beispielsweise die Werte der Spalte „foo“, verschlüsselt diese per Hash und fügt sie in die Spalte „bar“ ein.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-141">For example, a `new HashTransformer("bar", "foo")` takes the values from column "foo", hashes them, and puts them into column "bar".</span></span> 

<span data-ttu-id="3d0bd-142">Die Namen der Eingabe- und Ausgabespalten sind oft identisch.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-142">It's also common that the input and output column names are the same.</span></span> <span data-ttu-id="3d0bd-143">In diesem Fall wird die alte Spalte durch die neue ersetzt.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-143">In this case, the old column is replaced with the new one.</span></span> <span data-ttu-id="3d0bd-144">`new HashTransformer("foo")` nimmt beispielsweise die Werte der Spalte „foo“, verschlüsselt diese per Hash und fügt sie wieder in die Spalte „foo“ ein.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-144">For example, a `new HashTransformer("foo")` takes the values from column "foo", hashes them, and puts them back into "foo".</span></span> 

<span data-ttu-id="3d0bd-145">Natürlich erzeugt jeder Transformator eine neue Datenansicht, wenn `Transform` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-145">Any transformer, produces a new data view when `Transform` is called.</span></span> <span data-ttu-id="3d0bd-146">Vergessen Sie nicht, dass Datenansichten unveränderlich sind.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-146">Remember, data views are immutable.</span></span>

<span data-ttu-id="3d0bd-147">Ein weiterer zu beachtender Aspekt ist, dass *auch Transformatoren Verzögerungen aufweisen*, da Daten verzögert ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-147">Another important consideration is that, because data is lazily evaluated, *transformers are lazy too*.</span></span> <span data-ttu-id="3d0bd-148">Nach folgendem Aufruf</span><span class="sxs-lookup"><span data-stu-id="3d0bd-148">Essentially, after you call</span></span>

```csharp
var newData = transformer.Transform(oldData)
```

<span data-ttu-id="3d0bd-149">erfolgt im Grunde genommen keine tatsächliche Berechnung.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-149">no actual computation happens.</span></span> <span data-ttu-id="3d0bd-150">Erst nachdem Sie einen Cursor von `newData` erhalten haben und mit der Verarbeitung des Werts begonnen wurde, ruft `newData` die Transformationslogik `transformer` auf. (Selbst das geschieht nur, wenn `transformer` zum Erzeugen der angeforderten Spalten erforderlich ist.)</span><span class="sxs-lookup"><span data-stu-id="3d0bd-150">Only after you get a cursor from `newData` and start consuming the value does `newData` invoke the `transformer` transformation logic (and even then, it only happens if the `transformer` in question is needed to produce the requested columns).</span></span>

### <a name="transformer-chains"></a><span data-ttu-id="3d0bd-151">Transformator-Ketten</span><span class="sxs-lookup"><span data-stu-id="3d0bd-151">Transformer chains</span></span>

<span data-ttu-id="3d0bd-152">Eine nützliche Eigenschaft von Transformatoren ist, dass *Sie die aufeinanderfolgende Anwendung von Transformatoren als einen weiteren Transformator erstellen können*:</span><span class="sxs-lookup"><span data-stu-id="3d0bd-152">A useful property of a transformer is that *you can build a sequential application of transformers as yet another transformer*:</span></span>

```csharp
var fullTransformer = transformer1.Append(transformer2).Append(transformer3);
```

<span data-ttu-id="3d0bd-153">Dieser Eigenschaft wird in ML.NET häufig verwendet: In der Regel besteht das trainierte ML.NET-Modell aus einer Kette von Transformatoren, d. h., es besteht im Grunde genommen aus einem *Transformator*.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-153">This property is commonly used in ML.NET: typically, the trained ML.NET model is a chain of transformers, which is, for all intents and purposes, a *transformer*.</span></span>

## <a name="data-reader"></a><span data-ttu-id="3d0bd-154">Datenleser</span><span class="sxs-lookup"><span data-stu-id="3d0bd-154">Data reader</span></span>

<span data-ttu-id="3d0bd-155">Der Datenleser ist die ML.NET-Komponente zum „Erstellen“ von Daten: Er erfasst eine Instanz von `T` und gibt Daten aus dieser zurück.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-155">The data reader is an ML.NET component to 'create' data: it takes an instance of `T` and returns data out of it.</span></span>

<span data-ttu-id="3d0bd-156">Diese Datenleser verfügen über die interessante Eigenschaft, dass sie erstellt werden können, indem ein Transformator an einen vorhandenen Datenleser angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-156">An interesting property to note is that you can create a data reader by attaching a transformer to an existing data reader.</span></span> <span data-ttu-id="3d0bd-157">Auf diese Weise können Sie über einen Datenleser mit integriertem Transformationsverhalten verfügen:</span><span class="sxs-lookup"><span data-stu-id="3d0bd-157">This way you can have a reader with transformation behavior baked in:</span></span>

```csharp
var newReader = reader.Append(transformer1).Append(transformer2)
```

<span data-ttu-id="3d0bd-158">Eine weitere Ähnlichkeit mit Transformatoren besteht darin, dass *Datenleser verzögert sind*, weil Daten verzögert ausgewertet werden: Es erfolgen keine (oder nur minimale) tatsächliche „Lesevorgänge“, wenn Sie `reader.Read()` aufrufen. Erst wenn ein Cursor für die resultierenden Daten angefordert wird, beginnt der Datenleser mit dem Lesen.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-158">Another similarity to transformers is that, since data is lazily evaluated, *readers are lazy*: no (or minimal) actual 'reading' happens when you call `reader.Read()`: only when a cursor is requested on the resulting data does the reader begin to work.</span></span>

## <a name="estimator"></a><span data-ttu-id="3d0bd-159">Estimator</span><span class="sxs-lookup"><span data-stu-id="3d0bd-159">Estimator</span></span>

<span data-ttu-id="3d0bd-160">*Estimator* ist ein Objekt, das anhand von Daten lernt.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-160">The *estimator* is an object that learns from data.</span></span> <span data-ttu-id="3d0bd-161">Das Ergebnis des Lernvorgangs ist ein *Transformator*.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-161">The result of the learning is a *transformer*.</span></span>

<span data-ttu-id="3d0bd-162">Verwenden Sie diese Eigenschaft in ML.NET, um Lernpipelines zu erstellen, die verschiedene Estimator-Objekte verketten:</span><span class="sxs-lookup"><span data-stu-id="3d0bd-162">In ML.NET, use this property to create learning pipelines that chain together different estimators:</span></span>

```csharp
MLContext mlContext = new MLContext(seed: 0);

var pipeline = mlContext.Transforms.CopyColumns("Label","FareAmount")
    .Append(mlContext.Transforms.Categorical.OneHotEncoding("VendorId"))
    .Append(mlContext.Transforms.Categorical.OneHotEncoding("RateCode"))
    .Append(mlContext.Transforms.Categorical.OneHotEncoding("PaymentType"))
    .Append(mlContext.Transforms.Concatenate("Features","VendorId","RateCode","PassengerCount","TripTime","TripDistance","PaymentType"))
    .Append(mlContext.Regression.Trainers.FastTree("Label","Features"));

var model = pipeline.Fit(dataView);
```

<span data-ttu-id="3d0bd-163">Eine wichtige Eigenschaft der Estimator-Objekte ist, dass sie *nicht verzögert sind*: jeder Aufruf von `Fit` führt zu Lernvorgängen, was zu einem zeitaufwendigen Vorgang führen kann.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-163">One important property of estimators is that *estimators are eager, not lazy*: every call to `Fit` is causing learning to happen, which is potentially a time-consuming operation.</span></span>

## <a name="prediction-function"></a><span data-ttu-id="3d0bd-164">Vorhersagefunktion</span><span class="sxs-lookup"><span data-stu-id="3d0bd-164">Prediction function</span></span>

<span data-ttu-id="3d0bd-165">Die Vorhersagefunktion kann als Komponente interpretiert werden, die einen Transformator auf eine Zeile anwendet.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-165">The prediction function can be seen as a component that applies a transformer to one row.</span></span>

<span data-ttu-id="3d0bd-166">Sobald Sie das Modell (einen *Transformator*, der mit `Fit()` trainiert wurde oder aus einer anderen Quelle stammt) abrufen, können Sie es verwenden, um Vorhersagen mit den normalen Aufrufen von `model.Transform(data)` zu treffen.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-166">Once you get the model (a *transformer* either trained via `Fit()`, or loaded from somewhere), you can use it to make predictions using the normal calls to `model.Transform(data)`.</span></span> <span data-ttu-id="3d0bd-167">Wenn Sie dieses Modell jedoch in einem realen Szenario anwenden, verfügen Sie meist über zu wenige Beispiele für die Vorhersage.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-167">However, when you use this model in a real-life scenario, you often don't have many examples to predict on.</span></span> <span data-ttu-id="3d0bd-168">Stattdessen haben Sie immer ein Beispiel, für das Sie sofort Vorhersagen treffen müssen.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-168">Instead, you have one example at a time, and you need to make timely predictions on them immediately.</span></span>

<span data-ttu-id="3d0bd-169">Sie können dies auf die Batchvorhersage reduzieren:</span><span class="sxs-lookup"><span data-stu-id="3d0bd-169">Of course, you can reduce this to the batch prediction:</span></span>

- <span data-ttu-id="3d0bd-170">Erstellen Sie eine Datenansicht mit genau einer Zeile.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-170">Create a data view with exactly one row.</span></span>
- <span data-ttu-id="3d0bd-171">Rufen Sie `model.Transform(data)` auf, um die vorhergesagte Datenansicht zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-171">Call `model.Transform(data)` to get the predicted data view.</span></span>
- <span data-ttu-id="3d0bd-172">Rufen Sie einen Cursor für die resultierenden Daten ab.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-172">Get a cursor over the resulting data.</span></span>
- <span data-ttu-id="3d0bd-173">Bewegen Sie den Cursor einen Schritt vorwärts, um zur ersten (und einzigen) Zeile zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-173">Advance the cursor one step to get to the first (and only) row.</span></span>
- <span data-ttu-id="3d0bd-174">Extrahieren Sie die vorhergesagten Werte.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-174">Extract the predicted values out of it.</span></span>

<span data-ttu-id="3d0bd-175">Der obige Algorithmus kann folgendermaßen mithilfe des [Schemaverständnisses](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md) und den zwei benutzerdefinierten Objekten `InputExample` und `OutputPrediction` implementiert werden:</span><span class="sxs-lookup"><span data-stu-id="3d0bd-175">The preceding algorithm can be implemented using the [schema comprehension](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md), with two user-defined objects `InputExample` and `OutputPrediction` as follows:</span></span>

```csharp
var inputData = mlContext.Data.ReadFromEnumerable(new InputExample[] { example });
var outputData = model.Transform(inputData);
var output = mlContext.CreateEnumerable<OutputPrediction>(outputData,reuseRowObject:false).First();
```

<span data-ttu-id="3d0bd-176">Dies ist jedoch umständlich und verursacht Leistungsverluste.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-176">But this is cumbersome and incurs performance costs.</span></span> <span data-ttu-id="3d0bd-177">Dieselbe Funktion kann mithilfe der Erweiterungsmethode `CreatePredictionEngine` von einem Vorhersagefunktionsobjekt schneller und praktischer durchgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="3d0bd-177">Instead, a prediction function object performs the same work, but faster and more convenient, via an extension method `CreatePredictionEngine`:</span></span>

```csharp
var predictionEngine = model.CreatePredictionEngine<InputExample,OutputPrediction>(mlContext);
var prediction = predictionEngine.Predict(example);
```

<span data-ttu-id="3d0bd-178">Die Vorhersagefunktion ist *nicht wiedereintrittsfähig/threadsicher*.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-178">The prediction function is *not re-entrant / thread-safe*.</span></span> <span data-ttu-id="3d0bd-179">Wenn Sie Vorhersagen mit mehreren Threads gleichzeitig durchführen möchten, benötigen Sie pro Thread eine Vorhersagefunktion.</span><span class="sxs-lookup"><span data-stu-id="3d0bd-179">If you want to conduct predictions simultaneously with multiple threads, you need to have a prediction function per thread.</span></span>
