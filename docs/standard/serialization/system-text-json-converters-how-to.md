---
title: Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung (.net)
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: f72d2d83d701b20648140900d65c9098a8abb721
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2020
ms.locfileid: "76164059"
---
# <a name="how-to-write-custom-converters-for-json-serialization-marshalling-in-net"></a><span data-ttu-id="5a7e3-102">Schreiben von benutzerdefinierten Konvertern für JSON-Serialisierung (Marshalling) in .net</span><span class="sxs-lookup"><span data-stu-id="5a7e3-102">How to write custom converters for JSON serialization (marshalling) in .NET</span></span>

<span data-ttu-id="5a7e3-103">In diesem Artikel wird gezeigt, wie Sie benutzerdefinierte Konverter für die JSON-Serialisierungsklassen erstellen, die im <xref:System.Text.Json>-Namespace bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-103">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:System.Text.Json> namespace.</span></span> <span data-ttu-id="5a7e3-104">Eine Einführung in `System.Text.Json`finden Sie unter Gewusst [wie: Serialisieren und Deserialisieren von JSON in .net](system-text-json-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="5a7e3-104">For an introduction to `System.Text.Json`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="5a7e3-105">Ein *Konverter* ist eine Klasse, die ein Objekt oder einen Wert in und aus JSON konvertiert.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-105">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="5a7e3-106">Der `System.Text.Json`-Namespace verfügt über integrierte Konverter für die meisten primitiven Typen, die JavaScript-primitiven zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-106">The `System.Text.Json` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="5a7e3-107">Sie können benutzerdefinierte Konverter schreiben:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-107">You can write custom converters:</span></span>

* <span data-ttu-id="5a7e3-108">, Um das Standardverhalten eines integrierten Konverters zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-108">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="5a7e3-109">Beispielsweise kann es vorkommen, dass `DateTime` Werte durch das Format mm/dd/yyyy anstelle des Standard Formats ISO 8601-1:2019 dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-109">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format instead of the default  ISO 8601-1:2019 format.</span></span>
* <span data-ttu-id="5a7e3-110">Zur Unterstützung eines benutzerdefinierten Werttyps.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-110">To support a custom value type.</span></span> <span data-ttu-id="5a7e3-111">Beispielsweise eine `PhoneNumber` Struktur.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-111">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="5a7e3-112">Sie können auch benutzerdefinierte Konverter schreiben, um `System.Text.Json` mit Funktionen anzupassen oder zu erweitern, die nicht in der aktuellen Version enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-112">You can also write custom converters to customize or extend `System.Text.Json` with functionality not included in the current release.</span></span> <span data-ttu-id="5a7e3-113">Die folgenden Szenarien werden später in diesem Artikel behandelt:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-113">The following scenarios are covered later in this article:</span></span>

* <span data-ttu-id="5a7e3-114">[Deserialisieren von abzurufbaren Typen in Objekteigenschaften](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="5a7e3-114">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="5a7e3-115">[Wörterbuch mit nicht-Zeichen folgen Schlüssel unterstützen](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="5a7e3-115">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="5a7e3-116">[Unterstützung der polymorphen Deserialisierung](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="5a7e3-116">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>

## <a name="custom-converter-patterns"></a><span data-ttu-id="5a7e3-117">Benutzerdefinierte konvertermuster</span><span class="sxs-lookup"><span data-stu-id="5a7e3-117">Custom converter patterns</span></span>

<span data-ttu-id="5a7e3-118">Es gibt zwei Muster zum Erstellen eines benutzerdefinierten Konverters: das grundlegende Muster und das Factorymuster.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-118">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="5a7e3-119">Das Factorymuster ist für Konverter vorgesehen, die Typen `Enum` oder offene Generika verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-119">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="5a7e3-120">Das grundlegende Muster basiert auf nicht generischen und geschlossenen generischen Typen.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-120">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="5a7e3-121">Konverter für die folgenden Typen erfordern z. b. das Factorymuster:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-121">For example, converters for the following types require the factory pattern:</span></span>

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

<span data-ttu-id="5a7e3-122">Einige Beispiele für Typen, die vom grundlegenden Muster behandelt werden können, sind:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-122">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

<span data-ttu-id="5a7e3-123">Das grundlegende Muster erstellt eine Klasse, die einen Typ verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-123">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="5a7e3-124">Das Factorymuster erstellt eine Klasse, die zur Laufzeit bestimmt, welcher bestimmter Typ erforderlich ist, und erstellt dynamisch den entsprechenden Konverter.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-124">The factory pattern creates a class that determines at runtime which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="5a7e3-125">Sample-Grund Konverter</span><span class="sxs-lookup"><span data-stu-id="5a7e3-125">Sample basic converter</span></span>

<span data-ttu-id="5a7e3-126">Das folgende Beispiel ist ein Konverter, der die Standardserialisierung für einen vorhandenen Datentyp überschreibt.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-126">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="5a7e3-127">Der Konverter verwendet das Format "mm/dd/yyyy" für `DateTimeOffset` Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-127">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetConverter.cs)]

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="5a7e3-128">Sample Factory-Muster Konverter</span><span class="sxs-lookup"><span data-stu-id="5a7e3-128">Sample factory pattern converter</span></span>

<span data-ttu-id="5a7e3-129">Der folgende Code zeigt einen benutzerdefinierten Konverter, der mit `Dictionary<Enum,TValue>`funktioniert.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-129">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="5a7e3-130">Der Code folgt dem Factorymuster, da der erste generische Typparameter `Enum` und das zweite geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-130">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="5a7e3-131">Die `CanConvert`-Methode gibt `true` nur für einen `Dictionary` mit zwei generischen Parametern zurück, wobei der erste ein `Enum`-Typ ist.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-131">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="5a7e3-132">Der innere Konverter Ruft einen vorhandenen Konverter ab, um den Typ zu behandeln, der zur Laufzeit für `TValue`bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-132">The inner converter gets an existing converter to handle whichever type is provided at runtime for `TValue`.</span></span> 

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="5a7e3-133">Der vorangehende Code ist identisch mit dem, was im [Unterstützungs Wörterbuch mit einem nicht-Zeichen folgen Schlüssel](#support-dictionary-with-non-string-key) weiter unten in diesem Artikel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-133">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="5a7e3-134">Schritte zum grundlegenden Muster</span><span class="sxs-lookup"><span data-stu-id="5a7e3-134">Steps to follow the basic pattern</span></span>

<span data-ttu-id="5a7e3-135">In den folgenden Schritten wird erläutert, wie Sie einen Konverter erstellen, indem Sie das grundlegende Muster befolgen:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-135">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="5a7e3-136">Erstellen Sie eine Klasse, die von <xref:System.Text.Json.Serialization.JsonConverter%601> abgeleitet ist, wobei `T` der Typ ist, der serialisiert und deserialisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-136">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="5a7e3-137">Überschreiben Sie die `Read`-Methode, um den eingehenden JSON-Code zu deserialisieren und in Type `T`zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-137">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="5a7e3-138">Verwenden Sie die <xref:System.Text.Json.Utf8JsonReader>, die an die-Methode weitergegeben wird, um die JSON zu lesen.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-138">Use the <xref:System.Text.Json.Utf8JsonReader> that is passed to the method to read the JSON.</span></span>
* <span data-ttu-id="5a7e3-139">Überschreiben Sie die `Write`-Methode, um das eingehende Objekt vom Typ `T`zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-139">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="5a7e3-140">Verwenden Sie die <xref:System.Text.Json.Utf8JsonWriter>, die an die-Methode zum Schreiben der JSON-Datei übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-140">Use the <xref:System.Text.Json.Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="5a7e3-141">Überschreiben Sie die `CanConvert`-Methode nur bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-141">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="5a7e3-142">Die Standard Implementierung gibt `true` zurück, wenn der Typ, der konvertiert werden soll, den Typ `T`hat.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-142">The default implementation returns `true` when the type to convert is of type `T`.</span></span> <span data-ttu-id="5a7e3-143">Daher müssen Konverter, die nur den-Typ unterstützen `T` diese Methode nicht überschreiben.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-143">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="5a7e3-144">Ein Beispiel für einen Konverter, der diese Methode überschreiben muss, finden Sie im Abschnitt [polymorphe Deserialisierung](#support-polymorphic-deserialization) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-144">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="5a7e3-145">Sie können den [integrierten Konverter-Quellcode](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/) als Referenzimplementierungen zum Schreiben von benutzerdefinierten Konvertern bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-145">You can refer to the [built-in converters source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="5a7e3-146">Schritte zum Befolgen des Factorymusters</span><span class="sxs-lookup"><span data-stu-id="5a7e3-146">Steps to follow the factory pattern</span></span>

<span data-ttu-id="5a7e3-147">In den folgenden Schritten wird erläutert, wie Sie einen Konverter erstellen, indem Sie das Factorymuster befolgen:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-147">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="5a7e3-148">Erstellen Sie eine Klasse, die von <xref:System.Text.Json.Serialization.JsonConverterFactory> abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-148">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="5a7e3-149">Überschreiben Sie die `CanConvert`-Methode, um true zurückzugeben, wenn der zu konvertierende Typ eine ist, die der Konverter verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-149">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="5a7e3-150">Wenn der Konverter z. b. für `List<T>` ist, kann er nur `List<int>`, `List<string>`und `List<DateTime>`verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-150">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span> 
* <span data-ttu-id="5a7e3-151">Überschreiben Sie die `CreateConverter`-Methode, um eine Instanz einer Konverterklasse zurückzugeben, die den zu konvertierenden Typ zur Laufzeit behandelt.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-151">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at runtime.</span></span>
* <span data-ttu-id="5a7e3-152">Erstellen Sie die Konverterklasse, die von der `CreateConverter`-Methode instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-152">Create the converter class that the `CreateConverter` method instantiates.</span></span> 

<span data-ttu-id="5a7e3-153">Das Factorymuster ist für geöffnete Generika erforderlich, da der Code zum Konvertieren eines Objekts in eine und aus einer Zeichenfolge nicht für alle Typen identisch ist.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-153">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="5a7e3-154">Ein Konverter für einen offenen generischen Typ (z. b.`List<T>`) muss im Hintergrund einen Konverter für einen geschlossenen generischen Typ erstellen (z. b.`List<DateTime>`).</span><span class="sxs-lookup"><span data-stu-id="5a7e3-154">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="5a7e3-155">Code muss geschrieben werden, um jeden geschlossenen generischen Typ zu verarbeiten, den der Konverter verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-155">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="5a7e3-156">Der `Enum` Typ ähnelt einem offenen generischen Typ: ein Konverter für `Enum` muss im Hintergrund einen Konverter für eine bestimmte `Enum` erstellen (z. b.`WeekdaysEnum`).</span><span class="sxs-lookup"><span data-stu-id="5a7e3-156">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span> 

## <a name="error-handling"></a><span data-ttu-id="5a7e3-157">Fehlerbehandlung</span><span class="sxs-lookup"><span data-stu-id="5a7e3-157">Error handling</span></span>

<span data-ttu-id="5a7e3-158">Wenn Sie im Fehler Behandlungs Code eine Ausnahme auslösen müssen, sollten Sie ein <xref:System.Text.Json.JsonException> ohne eine Meldung auslösen.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-158">If you need to throw an exception in error-handling code, consider throwing a <xref:System.Text.Json.JsonException> without a message.</span></span> <span data-ttu-id="5a7e3-159">Dieser Ausnahmetyp erstellt automatisch eine Meldung, die den Pfad zu dem Teil der JSON enthält, der den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-159">This exception type automatically creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="5a7e3-160">Beispielsweise erzeugt die-Anweisung `throw new JsonException();` eine Fehlermeldung wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-160">For example, the statement `throw new JsonException();` produces an error message like the following example:</span></span>

```
Unhandled exception. System.Text.Json.JsonException: 
The JSON value could not be converted to System.Object. 
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="5a7e3-161">Wenn Sie eine Meldung angeben (z. b. `throw new JsonException("Error occurred")`, stellt die Ausnahme weiterhin den Pfad in der <xref:System.Text.Json.JsonException.Path>-Eigenschaft bereit.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-161">If you do provide a message (for example, `throw new JsonException("Error occurred")`, the exception still provides the path in the <xref:System.Text.Json.JsonException.Path> property.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="5a7e3-162">Registrieren eines benutzerdefinierten Konverters</span><span class="sxs-lookup"><span data-stu-id="5a7e3-162">Register a custom converter</span></span>

<span data-ttu-id="5a7e3-163">*Registrieren* Sie einen benutzerdefinierten Konverter, damit der `Serialize` und `Deserialize` Methoden ihn verwenden.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-163">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="5a7e3-164">Wählen Sie einen der folgenden Ansätze:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-164">Choose one of the following approaches:</span></span>

* <span data-ttu-id="5a7e3-165">Fügen Sie der <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> Auflistung eine Instanz der Konverterklasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-165">Add an instance of the converter class to the <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="5a7e3-166">Wenden Sie das [[jsonconverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) -Attribut auf die Eigenschaften an, die den benutzerdefinierten Konverter benötigen.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-166">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="5a7e3-167">Wenden Sie das [[jsonconverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) -Attribut auf eine Klasse oder eine Struktur an, die einen benutzerdefinierten Werttyp darstellt.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-167">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="5a7e3-168">Registrierungs Beispiel: Konverter-Auflistung</span><span class="sxs-lookup"><span data-stu-id="5a7e3-168">Registration sample - Converters collection</span></span> 

<span data-ttu-id="5a7e3-169">Im folgenden finden Sie ein Beispiel, mit dem die <xref:System.ComponentModel.DateTimeOffsetConverter> der Standardeinstellung für Eigenschaften vom Typ <xref:System.DateTimeOffset>wird:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-169">Here's an example that makes the <xref:System.ComponentModel.DateTimeOffsetConverter> the default for properties of type <xref:System.DateTimeOffset>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetSerialize)]

<span data-ttu-id="5a7e3-170">Angenommen, Sie serialisieren eine Instanz des folgenden Typs:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-170">Suppose you serialize an instance of the following type:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="5a7e3-171">Hier ist ein Beispiel für eine JSON-Ausgabe, die anzeigt, dass der benutzerdefinierte Konverter verwendet wurde:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-171">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="5a7e3-172">Der folgende Code verwendet den gleichen Ansatz zum Deserialisieren mithilfe des benutzerdefinierten `DateTimeOffset` Konverters:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-172">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="5a7e3-173">Registrierungs Beispiel-[jsonconverter] für eine Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5a7e3-173">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="5a7e3-174">Der folgende Code wählt einen benutzerdefinierten Konverter für die `Date`-Eigenschaft aus:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-174">The following code selects a custom converter for the `Date` property:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithConverterAttribute)]

<span data-ttu-id="5a7e3-175">Für den Code zum Serialisieren `WeatherForecastWithConverterAttribute` ist die Verwendung `JsonSerializeOptions.Converters`nicht erforderlich:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-175">The code to serialize `WeatherForecastWithConverterAttribute` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetSerialize)]

<span data-ttu-id="5a7e3-176">Der Code zum Deserialisieren erfordert auch nicht die Verwendung von `Converters`:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-176">The code to deserialize also doesn't require the use of `Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="5a7e3-177">Registrierungs Beispiel-[jsonconverter] für einen Typ</span><span class="sxs-lookup"><span data-stu-id="5a7e3-177">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="5a7e3-178">Der folgende Code erstellt eine Struktur und wendet das `[JsonConverter]`-Attribut darauf an:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-178">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Temperature.cs)]

<span data-ttu-id="5a7e3-179">Dies ist der benutzerdefinierte Konverter für die vorangehende Struktur:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-179">Here's the custom converter for the preceding struct:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/TemperatureConverter.cs)]

<span data-ttu-id="5a7e3-180">Das `[JsonConvert]`-Attribut in der Struktur registriert den benutzerdefinierten Konverter als Standardwert für Eigenschaften vom Typ `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-180">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="5a7e3-181">Der Konverter wird bei der Serialisierung oder Deserialisierung automatisch in der `TemperatureCelsius`-Eigenschaft des folgenden Typs verwendet:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-181">The converter is automatically used on the `TemperatureCelsius` property of the following type when you serialize or deserialize it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithTemperatureStruct)]

## <a name="converter-registration-precedence"></a><span data-ttu-id="5a7e3-182">Priorität der konverterregistrierung</span><span class="sxs-lookup"><span data-stu-id="5a7e3-182">Converter registration precedence</span></span>

<span data-ttu-id="5a7e3-183">Während der Serialisierung oder Deserialisierung wird für jedes JSON-Element in der folgenden Reihenfolge ein Konverter ausgewählt, der von der höchsten Priorität bis zum niedrigsten aufgelistet wird:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-183">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="5a7e3-184">`[JsonConverter]` auf eine Eigenschaft angewendet.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-184">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="5a7e3-185">Ein Konverter, der der `Converters` Auflistung hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-185">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="5a7e3-186">`[JsonConverter]` auf einen benutzerdefinierten Werttyp oder poco angewendet.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-186">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="5a7e3-187">Wenn mehrere benutzerdefinierte Konverter für einen Typ in der `Converters` Auflistung registriert sind, wird der erste Konverter verwendet, der für `CanConvert` "true" zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-187">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="5a7e3-188">Ein integrierter Konverter wird nur ausgewählt, wenn kein entsprechender benutzerdefinierter Konverter registriert ist.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-188">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="5a7e3-189">Konverterbeispiele für gängige Szenarien</span><span class="sxs-lookup"><span data-stu-id="5a7e3-189">Converter samples for common scenarios</span></span>

<span data-ttu-id="5a7e3-190">In den folgenden Abschnitten werden konverterbeispiele bereitgestellt, in denen einige gängige Szenarien behandelt werden, die von integrierten Funktionen nicht verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-190">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

* [<span data-ttu-id="5a7e3-191">Deserialisieren von abzurufbaren Typen in Objekteigenschaften</span><span class="sxs-lookup"><span data-stu-id="5a7e3-191">Deserialize inferred types to object properties</span></span>](#deserialize-inferred-types-to-object-properties)
* [<span data-ttu-id="5a7e3-192">Wörterbuch mit nicht-Zeichen folgen Schlüssel unterstützen</span><span class="sxs-lookup"><span data-stu-id="5a7e3-192">Support Dictionary with non-string key</span></span>](#support-dictionary-with-non-string-key)
* [<span data-ttu-id="5a7e3-193">Unterstützung der polymorphen Deserialisierung</span><span class="sxs-lookup"><span data-stu-id="5a7e3-193">Support polymorphic deserialization</span></span>](#support-polymorphic-deserialization)

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="5a7e3-194">Deserialisieren von abzurufbaren Typen in Objekteigenschaften</span><span class="sxs-lookup"><span data-stu-id="5a7e3-194">Deserialize inferred types to object properties</span></span>

<span data-ttu-id="5a7e3-195">Beim Deserialisieren in eine Eigenschaft vom Typ `object`wird ein `JsonElement` Objekt erstellt.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-195">When deserializing to a property of type `object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="5a7e3-196">Der Grund dafür ist, dass das Deserialisierungsprogramm nicht weiß, welcher CLR-Typ erstellt werden soll, und es wird nicht versucht, zu erraten.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-196">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="5a7e3-197">Wenn z. b. eine JSON-Eigenschaft "true" aufweist, wird vom Deserialisierungsprogramm nicht abgeleitet, dass der Wert eine `Boolean`ist, und wenn ein Element "01/01/2019" aufweist, wird vom Deserialisierungsprogramm nicht abgeleitet, dass es sich um eine `DateTime`handelt.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-197">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="5a7e3-198">Der Typrückschluss kann ungenau sein.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-198">Type inference can be inaccurate.</span></span> <span data-ttu-id="5a7e3-199">Wenn das Deserialisierungsprogramm eine JSON-Zahl analysiert, die keinen Dezimaltrennzeichen als `long`aufweist, kann dies zu Problemen außerhalb des gültigen Bereichs führen, wenn der Wert ursprünglich als `ulong` oder `BigInteger`serialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-199">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="5a7e3-200">Das Auswerten einer Zahl, die einen Dezimaltrennzeichen als `double` aufweist, kann die Genauigkeit verlieren, wenn die Zahl ursprünglich als `decimal`serialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-200">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="5a7e3-201">Für Szenarios, die einen Typrückschluss erfordern, zeigt der folgende Code einen benutzerdefinierten Konverter für `object` Eigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-201">For scenarios that require type inference, the following code shows a custom converter for `object` properties.</span></span> <span data-ttu-id="5a7e3-202">Der Code konvertiert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-202">The code converts:</span></span>

* <span data-ttu-id="5a7e3-203">`true` und `false` auf `Boolean`</span><span class="sxs-lookup"><span data-stu-id="5a7e3-203">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="5a7e3-204">Zahlen ohne Dezimal `long`</span><span class="sxs-lookup"><span data-stu-id="5a7e3-204">Numbers without a decimal to `long`</span></span>
* <span data-ttu-id="5a7e3-205">Zahlen mit einem Dezimaltrennzeichen, das `double`</span><span class="sxs-lookup"><span data-stu-id="5a7e3-205">Numbers with a decimal to `double`</span></span>
* <span data-ttu-id="5a7e3-206">Datumsangaben zum `DateTime`</span><span class="sxs-lookup"><span data-stu-id="5a7e3-206">Dates to `DateTime`</span></span>
* <span data-ttu-id="5a7e3-207">Zu `string` Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="5a7e3-207">Strings to `string`</span></span>
* <span data-ttu-id="5a7e3-208">Alles andere `JsonElement`</span><span class="sxs-lookup"><span data-stu-id="5a7e3-208">Everything else to `JsonElement`</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ObjectToInferredTypesConverter.cs)]

<span data-ttu-id="5a7e3-209">Der folgende Code registriert den Konverter:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-209">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeInferredTypesToObject.cs?name=SnippetRegister)]

<span data-ttu-id="5a7e3-210">Hier ist ein Beispiel für einen Typ mit `object` Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-210">Here's an example type with `object` properties:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithObjectProperties)]

<span data-ttu-id="5a7e3-211">Das folgende JSON-Beispiel für die Deserialisierung enthält Werte, die als `DateTime`, `long`und `string`deserialisiert werden:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-211">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="5a7e3-212">Ohne den benutzerdefinierten Konverter fügt die Deserialisierung eine `JsonElement` in jede Eigenschaft ein.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-212">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="5a7e3-213">Der [Ordner Komponententests](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) im `System.Text.Json.Serialization`-Namespace enthält weitere Beispiele für benutzerdefinierte Konverter, die die Deserialisierung zum `object` von Eigenschaften verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-213">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to `object` properties.</span></span>

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="5a7e3-214">Wörterbuch mit nicht-Zeichen folgen Schlüssel unterstützen</span><span class="sxs-lookup"><span data-stu-id="5a7e3-214">Support Dictionary with non-string key</span></span>

<span data-ttu-id="5a7e3-215">Die integrierte Unterstützung für Wörterbuch Sammlungen ist für `Dictionary<string, TValue>`.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-215">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="5a7e3-216">Das heißt, der Schlüssel muss eine Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-216">That is, the key must be a string.</span></span> <span data-ttu-id="5a7e3-217">Um ein Wörterbuch mit einer Ganzzahl oder einem anderen Typ als Schlüssel zu unterstützen, ist ein benutzerdefinierter Konverter erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-217">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="5a7e3-218">Der folgende Code zeigt einen benutzerdefinierten Konverter, der mit `Dictionary<Enum,TValue>`funktioniert:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-218">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="5a7e3-219">Der folgende Code registriert den Konverter:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-219">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripDictionaryTkeyEnumTValue.cs?name=SnippetRegister)]

<span data-ttu-id="5a7e3-220">Der Konverter kann die `TemperatureRanges`-Eigenschaft der folgenden Klasse serialisieren und deserialisieren, die Folgendes `Enum`verwendet:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-220">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnumDictionary)]

<span data-ttu-id="5a7e3-221">Die JSON-Ausgabe der Serialisierung sieht wie im folgenden Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-221">The JSON output from serialization looks like the following example:</span></span>

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

<span data-ttu-id="5a7e3-222">Der [Ordner "Unittests](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) " im `System.Text.Json.Serialization`-Namespace enthält weitere Beispiele für benutzerdefinierte Konverter, die Wörterbücher für nicht-Zeichen folgen Schlüssel verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-222">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="5a7e3-223">Unterstützung der polymorphen Deserialisierung</span><span class="sxs-lookup"><span data-stu-id="5a7e3-223">Support polymorphic deserialization</span></span>

<span data-ttu-id="5a7e3-224">Integrierte Features bieten eine begrenzte Anzahl von [polymorphen Serialisierungen](system-text-json-how-to.md#serialize-properties-of-derived-classes) , aber keine Unterstützung für die Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-224">Built-in features provide a limited range of [polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) but no support for deserialization at all.</span></span> <span data-ttu-id="5a7e3-225">Die Deserialisierung erfordert einen benutzerdefinierten Konverter.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-225">Deserialization requires a custom converter.</span></span>

<span data-ttu-id="5a7e3-226">Angenommen, Sie verfügen beispielsweise über eine `Person` abstrakte Basisklasse mit `Employee` und `Customer` abgeleiteten Klassen.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-226">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="5a7e3-227">Die polymorphe Deserialisierung bedeutet, dass Sie zur Entwurfszeit `Person` als Deserialisierungsziel angeben können und dass `Customer` und `Employee` Objekte in der JSON-Datei zur Laufzeit ordnungsgemäß deserialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-227">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at runtime.</span></span> <span data-ttu-id="5a7e3-228">Während der Deserialisierung müssen Sie nach Hinweisen suchen, mit denen der erforderliche Typ im JSON-Code identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-228">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="5a7e3-229">Die möglichen verfügbaren Hinweise variieren in jedem Szenario.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-229">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="5a7e3-230">Beispielsweise kann eine diskriminatoreigenschaft verfügbar sein, oder Sie müssen sich darauf verlassen, dass eine bestimmte Eigenschaft vorhanden oder nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-230">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="5a7e3-231">Die aktuelle Version von `System.Text.Json` stellt keine Attribute bereit, um anzugeben, wie polymorphe deserialisierungsszenarien behandelt werden sollen, sodass benutzerdefinierte Konverter erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-231">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="5a7e3-232">Der folgende Code zeigt eine Basisklasse, zwei abgeleitete Klassen und einen benutzerdefinierten Konverter.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-232">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="5a7e3-233">Der Konverter verwendet eine diskriminatoreigenschaft, um die polymorphe Deserialisierung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-233">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="5a7e3-234">Der typdiskriminator ist nicht in den Klassendefinitionen, wird aber während der Serialisierung erstellt und während der Deserialisierung gelesen.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-234">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Person.cs?name=SnippetPerson)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/PersonConverterWithTypeDiscriminator.cs)]

<span data-ttu-id="5a7e3-235">Der folgende Code registriert den Konverter:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-235">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPolymorphic.cs?name=SnippetRegister)]

<span data-ttu-id="5a7e3-236">Der Konverter kann JSON deserialisieren, das mit dem gleichen Konverter zum Serialisieren erstellt wurde, z. b.:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-236">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

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

<span data-ttu-id="5a7e3-237">Mit dem Konvertercode im vorherigen Beispiel wird jede Eigenschaft manuell gelesen und geschrieben.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-237">The converter code in the preceding example reads and writes each property manually.</span></span> <span data-ttu-id="5a7e3-238">Eine Alternative besteht darin, `Deserialize` oder `Serialize` aufzurufen, um einige der Aufgaben durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-238">An alternative is to call `Deserialize` or `Serialize` to do some of the work.</span></span> <span data-ttu-id="5a7e3-239">Ein Beispiel finden Sie in [diesem StackOverflow-Beitrag](https://stackoverflow.com/a/59744873/12509023).</span><span class="sxs-lookup"><span data-stu-id="5a7e3-239">For an example, see [this StackOverflow post](https://stackoverflow.com/a/59744873/12509023).</span></span>

## <a name="other-custom-converter-samples"></a><span data-ttu-id="5a7e3-240">Weitere benutzerdefinierte konverterbeispiele</span><span class="sxs-lookup"><span data-stu-id="5a7e3-240">Other custom converter samples</span></span>

<span data-ttu-id="5a7e3-241">Der Artikel [Migrieren von Newtonsoft.Json zu System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) enthält zusätzliche Beispiele für benutzerdefinierte Konverter.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-241">The [Migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) article contains additional samples of custom converters.</span></span>

<span data-ttu-id="5a7e3-242">Der [Ordner Komponententests](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) im `System.Text.Json.Serialization` Quellcode enthält andere benutzerdefinierte konverterbeispiele, wie z. b.:</span><span class="sxs-lookup"><span data-stu-id="5a7e3-242">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* <span data-ttu-id="5a7e3-243">[Int32 Converter, der bei der Deserialisierung NULL in 0 konvertiert.](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span><span class="sxs-lookup"><span data-stu-id="5a7e3-243">[Int32 converter that converts null to 0 on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span></span>
* <span data-ttu-id="5a7e3-244">[Int32 Converter, der beim Deserialisieren sowohl Zeichen folgen-als auch Zahlenwerte zulässt](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span><span class="sxs-lookup"><span data-stu-id="5a7e3-244">[Int32 converter that allows both string and number values on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span></span>
* <span data-ttu-id="5a7e3-245">[Enumerationskonverter](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span><span class="sxs-lookup"><span data-stu-id="5a7e3-245">[Enum converter](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span></span>
* <span data-ttu-id="5a7e3-246">[Auflisten\<t > Konverters, der externe Daten annimmt](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span><span class="sxs-lookup"><span data-stu-id="5a7e3-246">[List\<T> converter that accepts external data](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span></span>
* <span data-ttu-id="5a7e3-247">[Long [] Konverter, der mit einer durch Trennzeichen getrennten Liste von Zahlen funktioniert.](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span><span class="sxs-lookup"><span data-stu-id="5a7e3-247">[Long[] converter that works with a comma-delimited list of numbers](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span></span> 

<span data-ttu-id="5a7e3-248">Wenn Sie einen Konverter erstellen müssen, der das Verhalten eines vorhandenen integrierten Konverters ändert, können Sie [den Quellcode des vorhandenen Konverters](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) als Ausgangspunkt für die Anpassung erhalten.</span><span class="sxs-lookup"><span data-stu-id="5a7e3-248">If you need to make a converter that modifies the behavior of an existing built-in converter, you can get [the source code of the existing converter](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) to serve as a starting point for customization.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5a7e3-249">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5a7e3-249">Additional resources</span></span>

* <span data-ttu-id="5a7e3-250">[Quellcode für integrierte Konverter](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span><span class="sxs-lookup"><span data-stu-id="5a7e3-250">[Source code for built-in converters](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span></span>
* <span data-ttu-id="5a7e3-251">[DateTime-und DateTimeOffset-Unterstützung in System.Text.Json](../datetime/system-text-json-support.md)</span><span class="sxs-lookup"><span data-stu-id="5a7e3-251">[DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md)</span></span>
* <span data-ttu-id="5a7e3-252">[Übersicht über System.Text.Json](system-text-json-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5a7e3-252">[System.Text.Json overview](system-text-json-overview.md)</span></span>
* <span data-ttu-id="5a7e3-253">[Verwendung von System.Text.Json](system-text-json-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="5a7e3-253">[How to use System.Text.Json](system-text-json-how-to.md)</span></span>
* <span data-ttu-id="5a7e3-254">[Migrieren von Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="5a7e3-254">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* <span data-ttu-id="5a7e3-255">[API-Referenz für System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="5a7e3-255">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="5a7e3-256">[System.Text.Json. API-Referenz für die Serialisierung](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="5a7e3-256">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
