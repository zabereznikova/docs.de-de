---
title: Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung (.net)
ms.date: 10/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: efbaf852f07b2b59111f0e330cf52470e3eca4c3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705807"
---
# <a name="how-to-write-custom-converters-for-json-serialization-in-net"></a><span data-ttu-id="51c41-102">Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung in .net</span><span class="sxs-lookup"><span data-stu-id="51c41-102">How to write custom converters for JSON serialization in .NET</span></span>

<span data-ttu-id="51c41-103">In diesem Artikel wird gezeigt, wie Sie benutzerdefinierte Konverter für die JSON-Serialisierungsklassen erstellen, die im <xref:System.Text.Json>-Namespace bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="51c41-103">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:System.Text.Json> namespace.</span></span> <span data-ttu-id="51c41-104">Eine Einführung in `System.Text.Json`finden Sie unter Gewusst [wie: Serialisieren und Deserialisieren von JSON in .net](system-text-json-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="51c41-104">For an introduction to `System.Text.Json`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="51c41-105">Ein *Konverter* ist eine Klasse, die ein Objekt oder einen Wert in und aus JSON konvertiert.</span><span class="sxs-lookup"><span data-stu-id="51c41-105">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="51c41-106">Der `System.Text.Json`-Namespace verfügt über integrierte Konverter für die meisten primitiven Typen, die JavaScript-primitiven zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="51c41-106">The `System.Text.Json` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="51c41-107">Sie können benutzerdefinierte Konverter schreiben:</span><span class="sxs-lookup"><span data-stu-id="51c41-107">You can write custom converters:</span></span>

* <span data-ttu-id="51c41-108">, Um das Standardverhalten eines integrierten Konverters zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="51c41-108">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="51c41-109">Beispielsweise kann es vorkommen, dass `DateTime` Werte durch das Format mm/dd/yyyy anstelle des Standard Formats ISO 8601-1:2019 dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="51c41-109">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format instead of the default  ISO 8601-1:2019 format.</span></span>
* <span data-ttu-id="51c41-110">Zur Unterstützung eines benutzerdefinierten Werttyps.</span><span class="sxs-lookup"><span data-stu-id="51c41-110">To support a custom value type.</span></span> <span data-ttu-id="51c41-111">Beispielsweise eine `PhoneNumber` Struktur.</span><span class="sxs-lookup"><span data-stu-id="51c41-111">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="51c41-112">Sie können auch benutzerdefinierte Konverter schreiben, um `System.Text.Json` mit Funktionen zu erweitern, die nicht in der aktuellen Version enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="51c41-112">You can also write custom converters to extend `System.Text.Json` with functionality not included in the current release.</span></span> <span data-ttu-id="51c41-113">Die folgenden Szenarien werden später in diesem Artikel behandelt:</span><span class="sxs-lookup"><span data-stu-id="51c41-113">The following scenarios are covered later in this article:</span></span>

* <span data-ttu-id="51c41-114">[Deserialisieren von abzurufbaren Typen in Objekteigenschaften](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="51c41-114">[Deserialize inferred types to Object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="51c41-115">[Wörterbuch mit nicht-Zeichen folgen Schlüssel unterstützen](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="51c41-115">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="51c41-116">[Unterstützung der polymorphen Deserialisierung](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="51c41-116">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>

## <a name="custom-converter-patterns"></a><span data-ttu-id="51c41-117">Benutzerdefinierte konvertermuster</span><span class="sxs-lookup"><span data-stu-id="51c41-117">Custom converter patterns</span></span>

<span data-ttu-id="51c41-118">Es gibt zwei Muster zum Erstellen eines benutzerdefinierten Konverters: das grundlegende Muster und das Factorymuster.</span><span class="sxs-lookup"><span data-stu-id="51c41-118">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="51c41-119">Das Factorymuster ist für Konverter vorgesehen, die Typen `Enum` oder offene Generika verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="51c41-119">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="51c41-120">Das grundlegende Muster basiert auf nicht generischen und geschlossenen generischen Typen.</span><span class="sxs-lookup"><span data-stu-id="51c41-120">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="51c41-121">Konverter für die folgenden Typen erfordern z. b. das Factorymuster:</span><span class="sxs-lookup"><span data-stu-id="51c41-121">For example, converters for the following types require the factory pattern:</span></span>

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

<span data-ttu-id="51c41-122">Einige Beispiele für Typen, die vom grundlegenden Muster behandelt werden können, sind:</span><span class="sxs-lookup"><span data-stu-id="51c41-122">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

<span data-ttu-id="51c41-123">Das grundlegende Muster erstellt eine Klasse, die einen Typ verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="51c41-123">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="51c41-124">Das Factorymuster erstellt eine Klasse, die zur Laufzeit bestimmt, welcher bestimmter Typ erforderlich ist, und erstellt dynamisch den entsprechenden Konverter.</span><span class="sxs-lookup"><span data-stu-id="51c41-124">The factory pattern creates a class that determines at runtime which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="51c41-125">Sample-Grund Konverter</span><span class="sxs-lookup"><span data-stu-id="51c41-125">Sample basic converter</span></span>

<span data-ttu-id="51c41-126">Das folgende Beispiel ist ein Konverter, der die Standardserialisierung für einen vorhandenen Datentyp überschreibt.</span><span class="sxs-lookup"><span data-stu-id="51c41-126">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="51c41-127">Der Konverter verwendet das Format "mm/dd/yyyy" für `DateTimeOffset` Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="51c41-127">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetConverter.cs)]

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="51c41-128">Sample Factory-Muster Konverter</span><span class="sxs-lookup"><span data-stu-id="51c41-128">Sample factory pattern converter</span></span>

<span data-ttu-id="51c41-129">Der folgende Code zeigt einen benutzerdefinierten Konverter, der mit `Dictionary<Enum,TValue>`funktioniert.</span><span class="sxs-lookup"><span data-stu-id="51c41-129">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="51c41-130">Der Code folgt dem Factorymuster, da der erste generische Typparameter `Enum` und das zweite geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="51c41-130">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="51c41-131">Die `CanConvert`-Methode gibt `true` nur für einen `Dictionary` mit zwei generischen Parametern zurück, wobei der erste ein `Enum`-Typ ist.</span><span class="sxs-lookup"><span data-stu-id="51c41-131">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="51c41-132">Der innere Konverter Ruft einen vorhandenen Konverter ab, um den Typ zu behandeln, der zur Laufzeit für `TValue`bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="51c41-132">The inner converter gets an existing converter to handle whichever type is provided at runtime for `TValue`.</span></span> 

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="51c41-133">Der vorangehende Code ist identisch mit dem, was im [Unterstützungs Wörterbuch mit einem nicht-Zeichen folgen Schlüssel](#support-dictionary-with-non-string-key) weiter unten in diesem Artikel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="51c41-133">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="51c41-134">Schritte zum grundlegenden Muster</span><span class="sxs-lookup"><span data-stu-id="51c41-134">Steps to follow the basic pattern</span></span>

<span data-ttu-id="51c41-135">In den folgenden Schritten wird erläutert, wie Sie einen Konverter erstellen, indem Sie das grundlegende Muster befolgen:</span><span class="sxs-lookup"><span data-stu-id="51c41-135">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="51c41-136">Erstellen Sie eine Klasse, die von <xref:System.Text.Json.Serialization.JsonConverter%601> abgeleitet ist, wobei `T` der Typ ist, der serialisiert und deserialisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="51c41-136">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="51c41-137">Überschreiben Sie die `Read`-Methode, um den eingehenden JSON-Code zu deserialisieren und in Type `T`zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="51c41-137">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="51c41-138">Verwenden Sie die <xref:System.Text.Json.Utf8JsonReader>, die an die-Methode weitergegeben wird, um die JSON zu lesen.</span><span class="sxs-lookup"><span data-stu-id="51c41-138">Use the <xref:System.Text.Json.Utf8JsonReader> that is passed to the method to read the JSON.</span></span>
* <span data-ttu-id="51c41-139">Überschreiben Sie die `Write`-Methode, um das eingehende Objekt vom Typ `T`zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="51c41-139">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="51c41-140">Verwenden Sie die <xref:System.Text.Json.Utf8JsonWriter>, die an die-Methode zum Schreiben der JSON-Datei übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="51c41-140">Use the <xref:System.Text.Json.Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="51c41-141">Überschreiben Sie die `CanConvert`-Methode nur bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="51c41-141">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="51c41-142">Die Standard Implementierung gibt `true` zurück, wenn der zu konvertierende Typ `T`ist.</span><span class="sxs-lookup"><span data-stu-id="51c41-142">The default implementation returns `true` when the type to convert is type `T`.</span></span> <span data-ttu-id="51c41-143">Daher müssen Konverter, die nur den-Typ unterstützen `T` diese Methode nicht überschreiben.</span><span class="sxs-lookup"><span data-stu-id="51c41-143">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="51c41-144">Ein Beispiel für einen Konverter, der diese Methode überschreiben muss, finden Sie im Abschnitt [polymorphe Deserialisierung](#support-polymorphic-deserialization) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="51c41-144">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="51c41-145">Sie können den [integrierten Konverter-Quellcode](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/) als Referenzimplementierungen zum Schreiben von benutzerdefinierten Konvertern bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="51c41-145">You can refer to the [built-in converters source code](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="51c41-146">Schritte zum Befolgen des Factorymusters</span><span class="sxs-lookup"><span data-stu-id="51c41-146">Steps to follow the factory pattern</span></span>

<span data-ttu-id="51c41-147">In den folgenden Schritten wird erläutert, wie Sie einen Konverter erstellen, indem Sie das Factorymuster befolgen:</span><span class="sxs-lookup"><span data-stu-id="51c41-147">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="51c41-148">Erstellen Sie eine Klasse, die von <xref:System.Text.Json.Serialization.JsonConverterFactory> abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="51c41-148">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="51c41-149">Überschreiben Sie die `CanConvert`-Methode, um true zurückzugeben, wenn der zu konvertierende Typ eine ist, die der Konverter verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="51c41-149">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="51c41-150">Wenn der Konverter z. b. für `List<T>` ist, kann er nur `List<int>`, `List<string>`und `List<DateTime>`verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="51c41-150">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span> 
* <span data-ttu-id="51c41-151">Überschreiben Sie die `CreateConverter`-Methode, um eine Instanz einer Konverterklasse zurückzugeben, die den zu konvertierenden Typ zur Laufzeit behandelt.</span><span class="sxs-lookup"><span data-stu-id="51c41-151">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at runtime.</span></span>
* <span data-ttu-id="51c41-152">Erstellen Sie die Konverterklasse, die von der `CreateConverter`-Methode instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="51c41-152">Create the converter class that the `CreateConverter` method instantiates.</span></span> 

<span data-ttu-id="51c41-153">Das Factorymuster ist für geöffnete Generika erforderlich, da der Code zum Konvertieren eines Objekts in eine und aus einer Zeichenfolge nicht für alle Typen identisch ist.</span><span class="sxs-lookup"><span data-stu-id="51c41-153">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="51c41-154">Ein Konverter für einen offenen generischen Typ (z. b.`List<T>`) muss im Hintergrund einen Konverter für einen geschlossenen generischen Typ erstellen (z. b.`List<DateTime>`).</span><span class="sxs-lookup"><span data-stu-id="51c41-154">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="51c41-155">Code muss geschrieben werden, um jeden geschlossenen generischen Typ zu verarbeiten, den der Konverter verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="51c41-155">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="51c41-156">Der `Enum` Typ ähnelt einem offenen generischen Typ: ein Konverter für `Enum` muss im Hintergrund einen Konverter für eine bestimmte `Enum` erstellen (z. b.`WeekdaysEnum`).</span><span class="sxs-lookup"><span data-stu-id="51c41-156">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span> 

## <a name="error-handling"></a><span data-ttu-id="51c41-157">Fehlerbehandlung</span><span class="sxs-lookup"><span data-stu-id="51c41-157">Error handling</span></span>

<span data-ttu-id="51c41-158">Wenn Sie im Fehler Behandlungs Code eine Ausnahme auslösen müssen, sollten Sie ein <xref:System.Text.Json.JsonException> ohne eine Meldung auslösen.</span><span class="sxs-lookup"><span data-stu-id="51c41-158">If you need to throw an exception in error-handling code, consider throwing a <xref:System.Text.Json.JsonException> without a message.</span></span> <span data-ttu-id="51c41-159">Dieser Ausnahmetyp erstellt automatisch eine Meldung, die den Pfad zu dem Teil der JSON enthält, der den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="51c41-159">This exception type automatically creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="51c41-160">Beispielsweise erzeugt die-Anweisung `throw new JsonException();` eine Fehlermeldung wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="51c41-160">For example, the statement `throw new JsonException();` produces an error message like the following example:</span></span>

```
Unhandled exception. System.Text.Json.JsonException: 
The JSON value could not be converted to System.Object. 
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="51c41-161">Wenn Sie eine Meldung angeben (z. b. `throw new JsonException("Error occurred")`, stellt die Ausnahme weiterhin den Pfad in der <xref:System.Text.Json.JsonException.Path>-Eigenschaft bereit.</span><span class="sxs-lookup"><span data-stu-id="51c41-161">If you do provide a message (for example, `throw new JsonException("Error occurred")`, the exception still provides the path in the <xref:System.Text.Json.JsonException.Path> property.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="51c41-162">Registrieren eines benutzerdefinierten Konverters</span><span class="sxs-lookup"><span data-stu-id="51c41-162">Register a custom converter</span></span>

<span data-ttu-id="51c41-163">*Registrieren* Sie einen benutzerdefinierten Konverter, damit der `Serialize` und `Deserialize` Methoden ihn verwenden.</span><span class="sxs-lookup"><span data-stu-id="51c41-163">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="51c41-164">Wählen Sie einen der folgenden Ansätze:</span><span class="sxs-lookup"><span data-stu-id="51c41-164">Choose one of the following approaches:</span></span>

* <span data-ttu-id="51c41-165">Fügen Sie der <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> Auflistung eine Instanz der Konverterklasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="51c41-165">Add an instance of the converter class to the <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="51c41-166">Wenden Sie das [[jsonconverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) -Attribut auf die Eigenschaften an, die den benutzerdefinierten Konverter benötigen.</span><span class="sxs-lookup"><span data-stu-id="51c41-166">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="51c41-167">Wenden Sie das [[jsonconverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) -Attribut auf eine Klasse oder eine Struktur an, die einen benutzerdefinierten Werttyp darstellt.</span><span class="sxs-lookup"><span data-stu-id="51c41-167">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="51c41-168">Registrierungs Beispiel: Konverter-Auflistung</span><span class="sxs-lookup"><span data-stu-id="51c41-168">Registration sample - Converters collection</span></span> 

<span data-ttu-id="51c41-169">Im folgenden finden Sie ein Beispiel, mit dem die <xref:System.ComponentModel.DateTimeOffsetConverter> der Standardeinstellung für Eigenschaften vom Typ <xref:System.DateTimeOffset>wird:</span><span class="sxs-lookup"><span data-stu-id="51c41-169">Here's an example that makes the <xref:System.ComponentModel.DateTimeOffsetConverter> the default for properties of type <xref:System.DateTimeOffset>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetSerialize)]

<span data-ttu-id="51c41-170">Angenommen, Sie serialisieren eine Instanz des folgenden Typs:</span><span class="sxs-lookup"><span data-stu-id="51c41-170">Suppose you serialize an instance of the following type:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="51c41-171">Hier ist ein Beispiel für eine JSON-Ausgabe, die anzeigt, dass der benutzerdefinierte Konverter verwendet wurde:</span><span class="sxs-lookup"><span data-stu-id="51c41-171">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="51c41-172">Der folgende Code verwendet den gleichen Ansatz zum Deserialisieren mithilfe des benutzerdefinierten `DateTimeOffset` Konverters:</span><span class="sxs-lookup"><span data-stu-id="51c41-172">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="51c41-173">Registrierungs Beispiel-[jsonconverter] für eine Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="51c41-173">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="51c41-174">Der folgende Code wählt einen benutzerdefinierten Konverter für die `Date`-Eigenschaft aus:</span><span class="sxs-lookup"><span data-stu-id="51c41-174">The following code selects a custom converter for the `Date` property:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithConverterAttribute)]

<span data-ttu-id="51c41-175">Für den Code zum Serialisieren `WeatherForecastWithConverterAttribute` ist die Verwendung `JsonSerializeOptions.Converters`nicht erforderlich:</span><span class="sxs-lookup"><span data-stu-id="51c41-175">The code to serialize `WeatherForecastWithConverterAttribute` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetSerialize)]

<span data-ttu-id="51c41-176">Der Code zum Deserialisieren erfordert auch nicht die Verwendung von `Converters`:</span><span class="sxs-lookup"><span data-stu-id="51c41-176">The code to deserialize also doesn't require the use of `Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="51c41-177">Registrierungs Beispiel-[jsonconverter] für einen Typ</span><span class="sxs-lookup"><span data-stu-id="51c41-177">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="51c41-178">Der folgende Code erstellt eine Struktur und wendet das `[JsonConverter]`-Attribut darauf an:</span><span class="sxs-lookup"><span data-stu-id="51c41-178">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Temperature.cs)]

<span data-ttu-id="51c41-179">Dies ist der benutzerdefinierte Konverter für die vorangehende Struktur:</span><span class="sxs-lookup"><span data-stu-id="51c41-179">Here's the custom converter for the preceding struct:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/TemperatureConverter.cs)]

<span data-ttu-id="51c41-180">Das `[JsonConvert]`-Attribut in der Struktur registriert den benutzerdefinierten Konverter als Standardwert für Eigenschaften vom Typ `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="51c41-180">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="51c41-181">Der Konverter wird bei der Serialisierung oder Deserialisierung automatisch in der `TemperatureCelsius`-Eigenschaft des folgenden Typs verwendet:</span><span class="sxs-lookup"><span data-stu-id="51c41-181">The converter is automatically used on the `TemperatureCelsius` property of the following type when you serialize or deserialize it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithTemperatureStruct)]

## <a name="converter-registration-precedence"></a><span data-ttu-id="51c41-182">Priorität der konverterregistrierung</span><span class="sxs-lookup"><span data-stu-id="51c41-182">Converter registration precedence</span></span>

<span data-ttu-id="51c41-183">Während der Serialisierung oder Deserialisierung wird für jedes JSON-Element in der folgenden Reihenfolge ein Konverter ausgewählt, der von der höchsten Priorität bis zum niedrigsten aufgelistet wird:</span><span class="sxs-lookup"><span data-stu-id="51c41-183">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="51c41-184">`[JsonConverter]` auf eine Eigenschaft angewendet.</span><span class="sxs-lookup"><span data-stu-id="51c41-184">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="51c41-185">Ein Konverter, der der `Converters` Auflistung hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="51c41-185">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="51c41-186">`[JsonConverter]` auf einen benutzerdefinierten Werttyp oder poco angewendet.</span><span class="sxs-lookup"><span data-stu-id="51c41-186">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="51c41-187">Wenn mehrere benutzerdefinierte Konverter für einen Typ in der `Converters` Auflistung registriert sind, wird der erste Konverter verwendet, der für `CanConvert` "true" zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="51c41-187">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="51c41-188">Ein integrierter Konverter wird nur ausgewählt, wenn kein entsprechender benutzerdefinierter Konverter registriert ist.</span><span class="sxs-lookup"><span data-stu-id="51c41-188">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="51c41-189">Konverterbeispiele für gängige Szenarien</span><span class="sxs-lookup"><span data-stu-id="51c41-189">Converter samples for common scenarios</span></span>

<span data-ttu-id="51c41-190">In den folgenden Abschnitten werden konverterbeispiele bereitgestellt, in denen einige gängige Szenarien behandelt werden, die von integrierten Funktionen nicht verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="51c41-190">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

* [<span data-ttu-id="51c41-191">Deserialisieren von abzurufbaren Typen in Objekteigenschaften</span><span class="sxs-lookup"><span data-stu-id="51c41-191">Deserialize inferred types to Object properties</span></span>](#deserialize-inferred-types-to-object-properties)
* [<span data-ttu-id="51c41-192">Wörterbuch mit nicht-Zeichen folgen Schlüssel unterstützen</span><span class="sxs-lookup"><span data-stu-id="51c41-192">Support Dictionary with non-string key</span></span>](#support-dictionary-with-non-string-key)
* [<span data-ttu-id="51c41-193">Unterstützung der polymorphen Deserialisierung</span><span class="sxs-lookup"><span data-stu-id="51c41-193">Support polymorphic deserialization</span></span>](#support-polymorphic-deserialization)

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="51c41-194">Deserialisieren von abzurufbaren Typen in Objekteigenschaften</span><span class="sxs-lookup"><span data-stu-id="51c41-194">Deserialize inferred types to Object properties</span></span>

<span data-ttu-id="51c41-195">Beim Deserialisieren in eine Eigenschaft vom Typ `Object`wird ein `JsonElement` Objekt erstellt.</span><span class="sxs-lookup"><span data-stu-id="51c41-195">When deserializing to a property of type `Object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="51c41-196">Der Grund dafür ist, dass das Deserialisierungsprogramm nicht weiß, welcher CLR-Typ erstellt werden soll, und es wird nicht versucht, zu erraten.</span><span class="sxs-lookup"><span data-stu-id="51c41-196">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="51c41-197">Wenn z. b. eine JSON-Eigenschaft "true" aufweist, wird vom Deserialisierungsprogramm nicht abgeleitet, dass der Wert eine `Boolean`ist, und wenn ein Element "01/01/2019" aufweist, wird vom Deserialisierungsprogramm nicht abgeleitet, dass es sich um eine `DateTime`handelt.</span><span class="sxs-lookup"><span data-stu-id="51c41-197">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="51c41-198">Der Typrückschluss kann ungenau sein.</span><span class="sxs-lookup"><span data-stu-id="51c41-198">Type inference can be inaccurate.</span></span> <span data-ttu-id="51c41-199">Wenn das Deserialisierungsprogramm eine JSON-Zahl analysiert, die keinen Dezimaltrennzeichen als `long`aufweist, kann dies zu Problemen außerhalb des gültigen Bereichs führen, wenn der Wert ursprünglich als `ulong` oder `BigInteger`serialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="51c41-199">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="51c41-200">Das Auswerten einer Zahl, die einen Dezimaltrennzeichen als `double` aufweist, kann die Genauigkeit verlieren, wenn die Zahl ursprünglich als `decimal`serialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="51c41-200">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="51c41-201">Für Szenarios, die einen Typrückschluss erfordern, zeigt der folgende Code einen benutzerdefinierten Konverter für `Object` Eigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="51c41-201">For scenarios that require type inference, the following code shows a custom converter for `Object` properties.</span></span> <span data-ttu-id="51c41-202">Der Code konvertiert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="51c41-202">The code converts:</span></span>

* <span data-ttu-id="51c41-203">`true` und `false` auf `Boolean`</span><span class="sxs-lookup"><span data-stu-id="51c41-203">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="51c41-204">Zahlen zum `long` oder `double`</span><span class="sxs-lookup"><span data-stu-id="51c41-204">Numbers to `long` or `double`</span></span>
* <span data-ttu-id="51c41-205">Datumsangaben zum `DateTime`</span><span class="sxs-lookup"><span data-stu-id="51c41-205">Dates to `DateTime`</span></span>
* <span data-ttu-id="51c41-206">Zu `string` Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="51c41-206">Strings to `string`</span></span>
* <span data-ttu-id="51c41-207">Alles andere `JsonElement`</span><span class="sxs-lookup"><span data-stu-id="51c41-207">Everything else to `JsonElement`</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ObjectToInferredTypesConverter.cs)]

<span data-ttu-id="51c41-208">Der folgende Code registriert den Konverter:</span><span class="sxs-lookup"><span data-stu-id="51c41-208">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ConvertInferredTypesToObject.cs?name=SnippetRegister)]

<span data-ttu-id="51c41-209">Hier ist ein Beispiel für einen Typ mit `Object` Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="51c41-209">Here's an example type with `Object` properties:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithObjectProperties)]

<span data-ttu-id="51c41-210">Das folgende JSON-Beispiel für die Deserialisierung enthält Werte, die als `DateTime`, `long`und `string`deserialisiert werden:</span><span class="sxs-lookup"><span data-stu-id="51c41-210">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="51c41-211">Ohne den benutzerdefinierten Konverter fügt die Deserialisierung eine `JsonElement` in jede Eigenschaft ein.</span><span class="sxs-lookup"><span data-stu-id="51c41-211">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="51c41-212">Der [Ordner "Unittests](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) " im `System.Text.Json.Serialization`-Namespace enthält weitere Beispiele für benutzerdefinierte Konverter, die die Deserialisierung zu Objekteigenschaften verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="51c41-212">The [unit tests folder](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to Object properties.</span></span>

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="51c41-213">Wörterbuch mit nicht-Zeichen folgen Schlüssel unterstützen</span><span class="sxs-lookup"><span data-stu-id="51c41-213">Support Dictionary with non-string key</span></span>

<span data-ttu-id="51c41-214">Die integrierte Unterstützung für Wörterbuch Sammlungen ist für `Dictionary<string, TValue>`.</span><span class="sxs-lookup"><span data-stu-id="51c41-214">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="51c41-215">Das heißt, der Schlüssel muss eine Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="51c41-215">That is, the key must be a string.</span></span> <span data-ttu-id="51c41-216">Um ein Wörterbuch mit einer Ganzzahl oder einem anderen Typ als Schlüssel zu unterstützen, ist ein benutzerdefinierter Konverter erforderlich.</span><span class="sxs-lookup"><span data-stu-id="51c41-216">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="51c41-217">Der folgende Code zeigt einen benutzerdefinierten Konverter, der mit `Dictionary<Enum,TValue>`funktioniert:</span><span class="sxs-lookup"><span data-stu-id="51c41-217">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="51c41-218">Der folgende Code registriert den Konverter:</span><span class="sxs-lookup"><span data-stu-id="51c41-218">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ConvertDictionaryTkeyEnumTValue.cs?name=SnippetRegister)]

<span data-ttu-id="51c41-219">Der Konverter kann die `TemperatureRanges`-Eigenschaft der folgenden Klasse serialisieren und deserialisieren, die Folgendes `Enum`verwendet:</span><span class="sxs-lookup"><span data-stu-id="51c41-219">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnumDictionary)]

<span data-ttu-id="51c41-220">Die JSON-Ausgabe der Serialisierung sieht wie im folgenden Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="51c41-220">The JSON output from serialization looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "Cold": 20,
    "Hot": 40
  }
}
```

<span data-ttu-id="51c41-221">Der [Ordner "Unittests](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) " im `System.Text.Json.Serialization`-Namespace enthält weitere Beispiele für benutzerdefinierte Konverter, die Wörterbücher für nicht-Zeichen folgen Schlüssel verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="51c41-221">The [unit tests folder](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="51c41-222">Unterstützung der polymorphen Deserialisierung</span><span class="sxs-lookup"><span data-stu-id="51c41-222">Support polymorphic deserialization</span></span>

<span data-ttu-id="51c41-223">Die [polymorphe Serialisierung](system-text-json-how-to.md#serialize-properties-of-derived-classes) erfordert keinen benutzerdefinierten Konverter, aber die Deserialisierung erfordert einen benutzerdefinierten Konverter.</span><span class="sxs-lookup"><span data-stu-id="51c41-223">[Polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) doesn't require a custom converter, but deserialization does require a custom converter.</span></span>

<span data-ttu-id="51c41-224">Angenommen, Sie verfügen beispielsweise über eine `Person` abstrakte Basisklasse mit `Employee` und `Customer` abgeleiteten Klassen.</span><span class="sxs-lookup"><span data-stu-id="51c41-224">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="51c41-225">Die polymorphe Deserialisierung bedeutet, dass Sie zur Entwurfszeit `Person` als Deserialisierungsziel angeben können und dass `Customer` und `Employee` Objekte in der JSON-Datei zur Laufzeit ordnungsgemäß deserialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="51c41-225">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at runtime.</span></span> <span data-ttu-id="51c41-226">Während der Deserialisierung müssen Sie nach Hinweisen suchen, mit denen der erforderliche Typ im JSON-Code identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="51c41-226">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="51c41-227">Die möglichen verfügbaren Hinweise variieren in jedem Szenario.</span><span class="sxs-lookup"><span data-stu-id="51c41-227">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="51c41-228">Beispielsweise kann eine diskriminatoreigenschaft verfügbar sein, oder Sie müssen sich darauf verlassen, dass eine bestimmte Eigenschaft vorhanden oder nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="51c41-228">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="51c41-229">Die aktuelle Version von `System.Text.Json` stellt keine Attribute bereit, um anzugeben, wie polymorphe deserialisierungsszenarien behandelt werden sollen, sodass benutzerdefinierte Konverter erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="51c41-229">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="51c41-230">Der folgende Code zeigt eine Basisklasse, zwei abgeleitete Klassen und einen benutzerdefinierten Konverter.</span><span class="sxs-lookup"><span data-stu-id="51c41-230">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="51c41-231">Der Konverter verwendet eine diskriminatoreigenschaft, um die polymorphe Deserialisierung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="51c41-231">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="51c41-232">Der typdiskriminator ist nicht in den Klassendefinitionen, wird aber während der Serialisierung erstellt und während der Deserialisierung gelesen.</span><span class="sxs-lookup"><span data-stu-id="51c41-232">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Person.cs?name=SnippetPerson)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/PersonConverterWithTypeDiscriminator.cs)]

<span data-ttu-id="51c41-233">Der folgende Code registriert den Konverter:</span><span class="sxs-lookup"><span data-stu-id="51c41-233">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ConvertPolymorphic.cs?name=SnippetRegister)]

<span data-ttu-id="51c41-234">Der Konverter kann JSON deserialisieren, das mit dem gleichen Konverter zum Serialisieren erstellt wurde, z. b.:</span><span class="sxs-lookup"><span data-stu-id="51c41-234">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

```json
[
  {
    "TypeDiscriminator": 1,
    "CreditLimit": 10000,
    "Name": "John"
  },
  {
    "TypeDiscriminator": 2,
    "OfficeNumber": "555-1234",
    "Name": "Nancy"
  }
]
```

## <a name="other-custom-converter-samples"></a><span data-ttu-id="51c41-235">Weitere benutzerdefinierte konverterbeispiele</span><span class="sxs-lookup"><span data-stu-id="51c41-235">Other custom converter samples</span></span>

<span data-ttu-id="51c41-236">Der [Ordner Komponententests](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) im `System.Text.Json.Serialization` Quellcode enthält andere benutzerdefinierte konverterbeispiele, wie z. b.:</span><span class="sxs-lookup"><span data-stu-id="51c41-236">The [unit tests folder](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* <span data-ttu-id="51c41-237">`Int32` Konverter, der bei der Deserialisierung NULL in 0 konvertiert.</span><span class="sxs-lookup"><span data-stu-id="51c41-237">`Int32` converter that converts null to 0 on deserialize</span></span>
* <span data-ttu-id="51c41-238">`Int32` Konverter, der beim Deserialisieren sowohl Zeichen folgen-als auch Zahlenwerte zulässt.</span><span class="sxs-lookup"><span data-stu-id="51c41-238">`Int32` converter that allows both string and number values on deserialize</span></span>
* <span data-ttu-id="51c41-239">`Enum` Konverter</span><span class="sxs-lookup"><span data-stu-id="51c41-239">`Enum` converter</span></span>
* <span data-ttu-id="51c41-240">`List<T>` Konverter, der externe Daten annimmt</span><span class="sxs-lookup"><span data-stu-id="51c41-240">`List<T>` converter that accepts external data</span></span>
* <span data-ttu-id="51c41-241">`Long[]` Konverter, der mit einer durch Trennzeichen getrennten Liste von Zahlen funktioniert.</span><span class="sxs-lookup"><span data-stu-id="51c41-241">`Long[]` converter that works with a comma-delimited list of numbers</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="51c41-242">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="51c41-242">Additional resources</span></span>

* [<span data-ttu-id="51c41-243">Übersicht über System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="51c41-243">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="51c41-244">System. Text. JSON-API-Referenz</span><span class="sxs-lookup"><span data-stu-id="51c41-244">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="51c41-245">Verwenden von "System. Text. JSON"</span><span class="sxs-lookup"><span data-stu-id="51c41-245">How to use System.Text.Json</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="51c41-246">Quellcode für integrierte Konverter</span><span class="sxs-lookup"><span data-stu-id="51c41-246">Source code for built-in converters</span></span>](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/)
* <span data-ttu-id="51c41-247">GitHub-Probleme im Zusammenhang mit benutzerdefinierten Konvertern für `System.Text.Json`</span><span class="sxs-lookup"><span data-stu-id="51c41-247">GitHub issues related to custom converters for `System.Text.Json`</span></span>
  * [<span data-ttu-id="51c41-248">36639 Einführung in benutzerdefinierte Konverter</span><span class="sxs-lookup"><span data-stu-id="51c41-248">36639 Introducing custom converters</span></span>](https://github.com/dotnet/corefx/issues/36639)
  * [<span data-ttu-id="51c41-249">38713 Informationen zur Deserialisierung in ein Objekt</span><span class="sxs-lookup"><span data-stu-id="51c41-249">38713 About deserializing to Object</span></span>](https://github.com/dotnet/corefx/issues/38713)
  * [<span data-ttu-id="51c41-250">40120 Informationen zu nicht-Zeichen folgen Schlüssel Wörterbüchern</span><span class="sxs-lookup"><span data-stu-id="51c41-250">40120 About non-string-key dictionaries</span></span>](https://github.com/dotnet/corefx/issues/40120)
  * [<span data-ttu-id="51c41-251">37787 Informationen zur polymorphen Deserialisierung</span><span class="sxs-lookup"><span data-stu-id="51c41-251">37787 About polymorphic deserialization</span></span>](https://github.com/dotnet/corefx/issues/37787)
