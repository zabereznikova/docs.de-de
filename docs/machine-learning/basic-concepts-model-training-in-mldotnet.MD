---
title: Basiskonzepte für das Modelltraining in ML.NET
description: In diesem Artikel werden die grundlegenden Konzepte für Szenarios für *Modelltraining* in ML.NET erläutert. Nicht alle Konzepte sind für das einfachere Szenario für die *Vorhersage mit einem vorhandenen Modell* relevant.
ms.date: 11/06/2018
ms.topic: overview
ms.custom: mvc
ms.openlocfilehash: cff833b45583bc752bb42616820a95ca6c5c6b12
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "55252439"
---
# <a name="basic-concepts-for-model-training-in-mlnet"></a>Basiskonzepte für das Modelltraining in ML.NET

In diesem Artikel werden die grundlegenden Konzepte für Szenarios für *Modelltraining* in ML.NET erläutert. Nicht alle Konzepte sind für das einfachere Szenario für die *Vorhersage mit einem vorhandenen Modell* relevant.

## <a name="model-training-concepts"></a>Konzepte für das Modelltraining

In dieser Dokumentation werden folgende Konzepte im Zusammenhang mit dem Modelltraining in ML.NET erläutert:

- [*Data*](#data) (Daten) als `IDataView`-Schnittstelle.
  - In ML.NET ähneln die Daten einer SQL-Ansicht: Es handelt sich um ein unveränderliches, cursorfähiges, heterogenes und schematisiertes Dataset, das verzögert ausgewertet wird. 
  - Eine hervorragende Dokumentation zur Data-Schnittstelle finden Sie unter [IDataView Design Principles (Entwurfsprinzipien von IDataView)](https://github.com/dotnet/machinelearning/blob/master/docs/code/IDataViewDesignPrinciples.md).
- [*Transformer*](#transformer) (Transformator) als `ITransformer`-Schnittstelle.
  - Transformatoren sind Komponenten, die Daten erfassen, bearbeiten und anschließend neue, transformierte Daten zurückgeben.
  - Sie können sich ein Machine Learning-Modell beispielsweise als Transformator vorstellen, der Features erfasst und Vorhersagen zurückgibt.
  - Ein weiteres Beispiel ist der Text-Tokenizer, der eine einzelne Textspalte verwendet und eine Vektorspalte mit einzelnen Wörtern ausgibt, die aus dem Text extrahiert wurden.
- [*Data reader*](#data-reader) (Datenleser) als `IDataReader<T>`-Schnittstelle.
  - Der Datenleser ist die ML.NET-Komponente zum Erstellen von Daten. Sie verwendet eine Instanz von `T` und gibt Daten aus dieser zurück. 
  - Eine *TextLoader*-Klasse ist beispielsweise `IDataReader<FileSource>`. Sie erfasst die Dateiquelle und erzeugt Daten. 
- [*Estimator*](#estimator) als `IEstimator<T>`-Schnittstelle.
  - Dieses Objekt lernt anhand von Daten. Das Ergebnis des Lernvorgangs ist ein *Transformator*.
  - Sie können sich einen Machine Learning-*Algorithmus* als Estimator-Objekt vorstellen, das anhand von Daten lernt und ein Machine Learning-*Modell* erzeugt.
- [*Vorhersagefunktion*](#prediction-function) als `PredictionFunction<TSrc, TDst>`-Klasse.
  - Die Vorhersagefunktion kann als Computer interpretiert werden, der einen Transformator auf eine Zeile anwendet, z. B. zum Zeitpunkt der Vorhersage.

## <a name="data"></a>Daten

In ML.NET ähneln die Daten einer SQL-Ansicht: Es handelt sich um ein cursorfähiges, heterogenes und schematisiertes Dataset, das verzögert ausgewertet wird.

- Dieses verfügt über ein *Schema* (eine Instanz einer `ISchema`-Schnittstelle), das die Informationen zu den Spalten der Datenansicht enthält.
  - Jede Spalte verfügt über einen *Namen*, einen *Typ* und arbiträre *Metadaten*, die ihr zugeordnet sind.
  - Die *Metadaten* der Spalte enthalten Informationen wie Namen der Slots einer Vektorspalte und ähnliches. Die Metadaten selbst werden als andere einzeilige *Daten* dargestellt, die für jede Spalte eindeutig sind.
  - Die Datenansicht ist eine Quelle für *Cursor*. Sie können sich das wie SQL-Cursor vorstellen: Ein Cursor ist ein Objekt, das die Daten zeilenweise durchläuft und die verfügbaren Daten anzeigt.
  - Daten können natürlich so viele aktive Cursor wie nötig enthalten. Da die Daten selbst unveränderlich sind, sind Cursor vollkommen unabhängig.
  - Cursor greifen in der Regel nur auf eine Teilmenge der Spalten zu: Aus Effizienzgründen verarbeitet ML.NET nur die Werte aus Spalten, die für den Cursor erforderlich sind.

## <a name="transformer"></a>Transformator

Transformatoren sind Komponenten, die Daten erfassen, diese bearbeiten und dann neue, transformierte Daten zurückgeben.

In ML.NET verarbeiten die meisten Transformatoren in der Regel jeweils eine *Eingabespalte* und erzeugen die *Ausgabespalte*. `new HashTransformer("foo", "bar")` nimmt beispielsweise die Werte der Spalte „foo“, verschlüsselt diese per Hash und fügt sie in die Spalte „bar“ ein. 

Die Namen der Eingabe- und Ausgabespalten sind oft identisch. In diesem Fall wird die alte Spalte durch die neue ersetzt. `new HashTransformer("foo")` nimmt beispielsweise die Werte der Spalte „foo“, verschlüsselt diese per Hash und fügt sie wieder in die Spalte „foo“ ein. 

Natürlich erzeugt jeder Transformator eine neue Datenansicht, wenn `Transform` aufgerufen wird. Vergessen Sie nicht, dass Datenansichten unveränderlich sind.

Ein weiterer zu beachtender Aspekt ist, dass *auch Transformatoren Verzögerungen aufweisen*, da Daten verzögert ausgewertet werden. Nach folgendem Aufruf

```csharp
var newData = transformer.Transform(oldData)
```

erfolgt im Grunde genommen keine tatsächliche Berechnung. Erst nachdem Sie einen Cursor von `newData` erhalten haben und mit der Verarbeitung des Werts begonnen wurde, ruft `newData` die Transformationslogik `transformer` auf. (Selbst das geschieht nur, wenn `transformer` zum Erzeugen der angeforderten Spalten erforderlich ist.)

### <a name="transformer-chains"></a>Transformator-Ketten

Eine nützliche Eigenschaft von Transformatoren ist, dass *Sie die aufeinanderfolgende Anwendung von Transformatoren als einen weiteren Transformator formulieren können*:

```csharp
var fullTransformer = transformer1.Append(transformer2).Append(transformer3);
```

Dieser Eigenschaft wird in ML.NET häufig verwendet: In der Regel besteht das trainierte ML.NET-Modell aus einer Kette von Transformatoren, d. h., es besteht im Grunde genommen aus einem *Transformator*. 

## <a name="data-reader"></a>Datenleser

Der Datenleser ist die ML.NET-Komponente zum „Erstellen“ von Daten: Er erfasst eine Instanz von `T` und gibt Daten aus dieser zurück.

Diese Datenleser verfügen über die interessante Eigenschaft, dass sie erstellt werden können, indem ein Transformator an einen vorhandenen Datenleser angefügt wird. Auf diese Weise können Sie über einen Datenleser mit integriertem Transformationsverhalten verfügen:

```c#
var newReader = reader.Append(transformer1).Append(transformer2)
```

Eine weitere Ähnlichkeit mit Transformatoren besteht darin, dass *Datenleser verzögert sind*, weil Daten verzögert ausgewertet werden: Es erfolgen keine (oder nur minimale) tatsächliche „Lesevorgänge“, wenn Sie `dataReader.Read()` aufrufen. Erst wenn ein Cursor für die resultierenden Daten angefordert wird, beginnt der Datenleser mit dem Lesen.

## <a name="estimator"></a>Estimator

*Estimator* ist ein Objekt, das anhand von Daten lernt. Das Ergebnis des Lernvorgangs ist ein *Transformator*.

Verwenden Sie diese Eigenschaft in ML.NET, um Lernpipelines zu erstellen, die verschiedene Estimator-Objekte verketten:

```csharp
MLContext mlContext = new MLContext(seed: 0);

var pipeline = new CopyColumnsEstimator(mlContext, "FareAmount", "Label")
.Append(mlContextml.Transforms.Categorical.OneHotEncoding(mlContext, "VendorId"))
.Append(mlContextml.Transforms.Categorical.OneHotEncoding(mlContext, "RateCode"))
.Append(mlContextml.Transforms.Categorical.OneHotEncoding(mlContext, "PaymentType"))
.Append(new ColumnConcatenatingEstimator(mlContext, "Features", "VendorId", "RateCode", "PassengerCount", "TripTime", "TripDistance", "PaymentType"))
.Append(mlContext.Regression.Trainers.FastTree("Label", "Features"));

var model = pipeline.Fit(dataView);
```

Eine wichtige Eigenschaft der Estimator-Objekte ist, dass sie *nicht verzögert sind*: jeder Aufruf von `Fit` führt zu Lernvorgängen, was zu einem zeitaufwendigen Vorgang führen kann.

## <a name="prediction-function"></a>Vorhersagefunktion

Die Vorhersagefunktion kann als Computer interpretiert werden, der einen Transformator auf eine Zeile anwendet.

Sobald Sie das Modell (einen *Transformator*, der mit `Fit()` trainiert wurde oder aus einer anderen Quelle stammt) abrufen, können Sie es verwenden, um Vorhersagen mit den normalen Aufrufen von `model.Transform(data)` zu treffen. Wenn Sie dieses Modell jedoch in einem realen Szenario anwenden, verfügen Sie meist über zu wenige Beispiele für die Vorhersage. Stattdessen haben Sie immer ein Beispiel, für das Sie sofort Vorhersagen treffen müssen.

Sie können dies auf die Batchvorhersage reduzieren:

- Erstellen Sie eine Datenansicht mit genau einer Zeile.
- Rufen Sie `model.Transform(data)` auf, um die vorhergesagte Datenansicht zu erhalten.
- Rufen Sie einen Cursor für die resultierenden Daten ab.
- Bewegen Sie den Cursor einen Schritt vorwärts, um zur ersten (und einzigen) Zeile zu gelangen.
- Extrahieren Sie die vorhergesagten Werte.

Der obige Algorithmus kann folgendermaßen mithilfe des [Schemaverständnisses](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md) und den zwei benutzerdefinierten Objekten `InputExample` und `OutputPrediction` implementiert werden:

```c#
var inputData = env.CreateDataView(new InputExample[] { example });
var outputData = model.Transform(inputData);
var output = outputData.AsDynamic.AsEnumerable<OutputPrediction>(env, reuseRowObject: false).Single();
```

Dies ist jedoch umständlich und verursacht Leistungsverluste. Dieselbe Funktion kann mithilfe der Erweiterungsmethode `MakePredictionFunction` von einem Vorhersagefunktionsobjekt schneller und praktischer durchgeführt werden:

```c#
var predictionFunc = model.MakePredictionFunction<InputExample, OutputPrediction>(env);
var output = predictionFunc.Predict(example);
```

Die Vorhersagefunktion ist *nicht wiedereintrittsfähig/threadsicher*. Wenn Sie Vorhersagen mit mehreren Threads gleichzeitig durchführen möchten, benötigen Sie pro Thread eine Vorhersagefunktion.
