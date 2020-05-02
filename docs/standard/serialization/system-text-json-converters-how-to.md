---
title: Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung – .NET
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
ms.openlocfilehash: 310967f39c3aa7a46d79087bcbf0cb016f7d7284
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159571"
---
# <a name="how-to-write-custom-converters-for-json-serialization-marshalling-in-net"></a><span data-ttu-id="4ff30-102">Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung (Marshallen) in .NET</span><span class="sxs-lookup"><span data-stu-id="4ff30-102">How to write custom converters for JSON serialization (marshalling) in .NET</span></span>

<span data-ttu-id="4ff30-103">In diesem Artikel wird gezeigt, wie Sie benutzerdefinierte Konverter für JSON-Serialisierungsklassen erstellen, die im <xref:[!OP.NO-LOC(System.Text.Json)]>-Namespace bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4ff30-103">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:[!OP.NO-LOC(System.Text.Json)]> namespace.</span></span> <span data-ttu-id="4ff30-104">Eine Einführung zu `[!OP.NO-LOC(System.Text.Json)]` finden Sie unter [Serialisieren und Deserialisieren von JSON-Daten in .NET](system-text-json-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="4ff30-104">For an introduction to `[!OP.NO-LOC(System.Text.Json)]`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="4ff30-105">Ein *Konverter* ist eine Klasse, die ein Objekt oder einen Wert in und aus JSON konvertiert.</span><span class="sxs-lookup"><span data-stu-id="4ff30-105">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="4ff30-106">Der `[!OP.NO-LOC(System.Text.Json)]`-Namespace verfügt über integrierte Konverter für die meisten primitiven Typen, die JavaScript-Primitiven entsprechen.</span><span class="sxs-lookup"><span data-stu-id="4ff30-106">The `[!OP.NO-LOC(System.Text.Json)]` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="4ff30-107">Sie können benutzerdefinierte Konverter schreiben:</span><span class="sxs-lookup"><span data-stu-id="4ff30-107">You can write custom converters:</span></span>

* <span data-ttu-id="4ff30-108">Um das Standardverhalten eines integrierten Konverters außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="4ff30-108">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="4ff30-109">Vielleicht möchten Sie zum Beispiel `DateTime`-Werte im Format „mm/dd/yyyy“ anstatt im Standardformat ISO 8601-1:2019 darstellen.</span><span class="sxs-lookup"><span data-stu-id="4ff30-109">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format instead of the default  ISO 8601-1:2019 format.</span></span>
* <span data-ttu-id="4ff30-110">Um einen benutzerdefinierten Werttyp zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="4ff30-110">To support a custom value type.</span></span> <span data-ttu-id="4ff30-111">Beispielsweise eine `PhoneNumber`-Struktur.</span><span class="sxs-lookup"><span data-stu-id="4ff30-111">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="4ff30-112">Sie können auch benutzerdefinierte Konverter schreiben, um `[!OP.NO-LOC(System.Text.Json)]` mit Funktionen anzupassen oder zu erweitern, die nicht im aktuellen Release enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="4ff30-112">You can also write custom converters to customize or extend `[!OP.NO-LOC(System.Text.Json)]` with functionality not included in the current release.</span></span> <span data-ttu-id="4ff30-113">Folgende Szenarien werden später in diesem Artikel abgedeckt:</span><span class="sxs-lookup"><span data-stu-id="4ff30-113">The following scenarios are covered later in this article:</span></span>

* <span data-ttu-id="4ff30-114">[Deserialisieren abgeleiteter Typen in Objekteigenschaften](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="4ff30-114">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="4ff30-115">[Unterstützung für Wörterbücher mit Schlüsseln, die keine Zeichenfolgen sind](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="4ff30-115">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="4ff30-116">[Unterstützung polymorpher Deserialisierung](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="4ff30-116">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>

## <a name="custom-converter-patterns"></a><span data-ttu-id="4ff30-117">Benutzerdefinierte Konvertermuster</span><span class="sxs-lookup"><span data-stu-id="4ff30-117">Custom converter patterns</span></span>

<span data-ttu-id="4ff30-118">Es gibt zwei Muster zum Erstellen eines benutzerdefinierten Konverters: das grundlegende Muster und das Factorymuster.</span><span class="sxs-lookup"><span data-stu-id="4ff30-118">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="4ff30-119">Das Factorymuster ist für Konverter vorgesehen, die den `Enum`-Typ oder offene generische Typen verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="4ff30-119">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="4ff30-120">Das grundlegende Muster ist für nicht generische und geschlossene generische Typen gedacht.</span><span class="sxs-lookup"><span data-stu-id="4ff30-120">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="4ff30-121">Konverter für die folgenden Typen erfordern z. B. das Factorymuster:</span><span class="sxs-lookup"><span data-stu-id="4ff30-121">For example, converters for the following types require the factory pattern:</span></span>

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

<span data-ttu-id="4ff30-122">Einige Beispiele für Typen, die vom grundlegenden Muster verarbeitet werden können, sind u. a.:</span><span class="sxs-lookup"><span data-stu-id="4ff30-122">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

<span data-ttu-id="4ff30-123">Das grundlegende Muster erstellt eine Klasse, die einen Typ verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="4ff30-123">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="4ff30-124">Das Factorymuster erstellt eine Klasse, die zur Laufzeit bestimmt, welcher spezifische Typ erforderlich ist, und erstellt dynamisch den entsprechenden Konverter.</span><span class="sxs-lookup"><span data-stu-id="4ff30-124">The factory pattern creates a class that determines at runtime which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="4ff30-125">Grundlegender Konverter – Beispiel</span><span class="sxs-lookup"><span data-stu-id="4ff30-125">Sample basic converter</span></span>

<span data-ttu-id="4ff30-126">Das folgende Beispiel ist ein Konverter, der die Standardserialisierung für einen vorhandenen Datentyp außer Kraft setzt.</span><span class="sxs-lookup"><span data-stu-id="4ff30-126">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="4ff30-127">Der Konverter verwendet das Format „mm/dd/yyyy“ für `DateTimeOffset`-Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="4ff30-127">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetConverter.cs)]

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="4ff30-128">Factorymusterkonverter – Beispiel</span><span class="sxs-lookup"><span data-stu-id="4ff30-128">Sample factory pattern converter</span></span>

<span data-ttu-id="4ff30-129">Im folgenden Code wird ein benutzerdefinierter Konverter gezeigt, der mit `Dictionary<Enum,TValue>` arbeitet.</span><span class="sxs-lookup"><span data-stu-id="4ff30-129">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="4ff30-130">Der Code folgt dem Factorymuster, da der erste generische Typparameter `Enum` und der zweite offen ist.</span><span class="sxs-lookup"><span data-stu-id="4ff30-130">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="4ff30-131">Die `CanConvert`-Methode gibt `true` nur für ein `Dictionary` mit zwei generischen Parametern zurück, wobei der erste ein `Enum`-Typ ist.</span><span class="sxs-lookup"><span data-stu-id="4ff30-131">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="4ff30-132">Der innere Konverter ruft einen vorhandenen Konverter ab, um jeglichen Typ zu verarbeiten, der zur Laufzeit für `TValue` bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="4ff30-132">The inner converter gets an existing converter to handle whichever type is provided at runtime for `TValue`.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="4ff30-133">Der vorangehende Code ist identisch mit dem, der weiter unten in diesem Artikel unter [Unterstützung für Wörterbücher mit Schlüsseln, die keine Zeichenfolgen sind](#support-dictionary-with-non-string-key) gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4ff30-133">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="4ff30-134">Schritte zum Einhalten des grundlegenden Musters</span><span class="sxs-lookup"><span data-stu-id="4ff30-134">Steps to follow the basic pattern</span></span>

<span data-ttu-id="4ff30-135">Die folgenden Schritte erläutern, wie Sie einen Konverter erstellen, indem Sie dem grundlegenden Muster folgen:</span><span class="sxs-lookup"><span data-stu-id="4ff30-135">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="4ff30-136">Erstellen Sie eine Klasse, die von <xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverter%601> abgeleitet ist, wobei `T` der Typ ist, der serialisiert und deserialisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4ff30-136">Create a class that derives from <xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="4ff30-137">Setzen Sie die `Read`-Methode außer Kraft, um den eingehenden JSON-Code zu deserialisieren und in den Typ `T` zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="4ff30-137">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="4ff30-138">Verwenden Sie den <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonReader>, der an die Methode übergeben wird, um den JSON-Code zu lesen.</span><span class="sxs-lookup"><span data-stu-id="4ff30-138">Use the <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonReader> that is passed to the method to read the JSON.</span></span>
* <span data-ttu-id="4ff30-139">Setzen Sie die `Write`-Methode außer Kraft, um das eingehende Objekt vom Typ `T` zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="4ff30-139">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="4ff30-140">Verwenden Sie den <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonWriter>, der an die Methode übergeben wird, um den JSON-Code zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="4ff30-140">Use the <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="4ff30-141">Setzen Sie die `CanConvert`-Methode nur außer Kraft, wenn dies notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="4ff30-141">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="4ff30-142">Die Standardimplementierung gibt `true` zurück, wenn der zu konvertierende Typ vom Typ `T` ist.</span><span class="sxs-lookup"><span data-stu-id="4ff30-142">The default implementation returns `true` when the type to convert is of type `T`.</span></span> <span data-ttu-id="4ff30-143">Daher müssen Konverter, die nur den Typ `T` unterstützen, diese Methode nicht außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="4ff30-143">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="4ff30-144">Ein Beispiel für einen Konverter, der diese Methode außer Kraft setzen muss, finden Sie im weiter unten in diesem Artikel im Abschnitt [Polymorphe Deserialisierung](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="4ff30-144">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="4ff30-145">Sie können den [Quellcode des integrierten Konverters](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/[!OP.NO-LOC(System.Text.Json)]/src/[!OP.NO-LOC(System/Text/Json)]/Serialization/Converters/) als Referenzimplementierungen zum Schreiben von benutzerdefinierten Konvertern verwenden.</span><span class="sxs-lookup"><span data-stu-id="4ff30-145">You can refer to the [built-in converters source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/[!OP.NO-LOC(System.Text.Json)]/src/[!OP.NO-LOC(System/Text/Json)]/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="4ff30-146">Schritte zum Einhalten des Factorymusters</span><span class="sxs-lookup"><span data-stu-id="4ff30-146">Steps to follow the factory pattern</span></span>

<span data-ttu-id="4ff30-147">Die folgenden Schritte erläutern, wie Sie einen Konverter erstellen, indem Sie dem Factorymuster folgen:</span><span class="sxs-lookup"><span data-stu-id="4ff30-147">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="4ff30-148">Erstellen Sie eine von der <xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterFactory>-Klasse abgeleitete Klasse.</span><span class="sxs-lookup"><span data-stu-id="4ff30-148">Create a class that derives from <xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="4ff30-149">Überschreiben Sie die `CanConvert`-Methode, um „true“ zurückzugeben, wenn der zu konvertierende Typ einer ist, den der Konverter verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="4ff30-149">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="4ff30-150">Wenn der Konverter z. B. für `List<T>` ist, kann er eventuell nur `List<int>`, `List<string>` und `List<DateTime>` verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="4ff30-150">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span>
* <span data-ttu-id="4ff30-151">Stezen Sie die `CreateConverter`-Methode außer Kraft, um eine Instanz einer Konverterklasse zurückzugeben, die den zur Laufzeit bereitgestellten zu konvertierenden Typ verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="4ff30-151">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at runtime.</span></span>
* <span data-ttu-id="4ff30-152">Erstellen Sie die Konverterklasse, die von der `CreateConverter`-Methode instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="4ff30-152">Create the converter class that the `CreateConverter` method instantiates.</span></span>

<span data-ttu-id="4ff30-153">Das Factorymuster ist für offene generische Typen erforderlich, da der Code, mit dem ein Objekt in eine und aus einer Zeichenfolge konvertiert werden soll, nicht für alle Typen identisch ist.</span><span class="sxs-lookup"><span data-stu-id="4ff30-153">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="4ff30-154">Ein Konverter für einen offenen generischen Typ (z. B. `List<T>`) muss verdeckt einen Konverter für einen geschlossenen generischen Typ erstellen (z. B. `List<DateTime>`).</span><span class="sxs-lookup"><span data-stu-id="4ff30-154">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="4ff30-155">Es muss Code geschrieben werden, um jeden geschlossenen generischen Typ zu verarbeiten, den der Konverter verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="4ff30-155">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="4ff30-156">Der Typ `Enum` ähnelt einem offenen generischen Typ: Ein Konverter für `Enum` muss verdeckt einen Konverter für einen spezifischen `Enum` (z. B. `WeekdaysEnum`) erstellen.</span><span class="sxs-lookup"><span data-stu-id="4ff30-156">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span>

## <a name="error-handling"></a><span data-ttu-id="4ff30-157">Fehlerbehandlung</span><span class="sxs-lookup"><span data-stu-id="4ff30-157">Error handling</span></span>

<span data-ttu-id="4ff30-158">Wenn Sie im Fehlerbehandlungscode eine Ausnahme auslösen müssen, sollten Sie erwägen, eine <xref:[!OP.NO-LOC(System.Text.Json)].JsonException> ohne Meldung auszulösen.</span><span class="sxs-lookup"><span data-stu-id="4ff30-158">If you need to throw an exception in error-handling code, consider throwing a <xref:[!OP.NO-LOC(System.Text.Json)].JsonException> without a message.</span></span> <span data-ttu-id="4ff30-159">Dieser Ausnahmetyp erstellt automatisch eine Meldung, die den Pfad zu dem Teil des JSON-Codes enthält, der den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="4ff30-159">This exception type automatically creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="4ff30-160">Beispielsweise erzeugt die Anweisung `throw new JsonException();` eine Fehlermeldung wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4ff30-160">For example, the statement `throw new JsonException();` produces an error message like the following example:</span></span>

```
Unhandled exception. [!OP.NO-LOC(System.Text.Json)].JsonException:
The JSON value could not be converted to System.Object.
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="4ff30-161">Wenn Sie eine Meldung angeben (z. B. `throw new JsonException("Error occurred")`), stellt die Ausnahme immer noch den Pfad in der <xref:[!OP.NO-LOC(System.Text.Json)].JsonException.Path>-Eigenschaft bereit.</span><span class="sxs-lookup"><span data-stu-id="4ff30-161">If you do provide a message (for example, `throw new JsonException("Error occurred")`, the exception still provides the path in the <xref:[!OP.NO-LOC(System.Text.Json)].JsonException.Path> property.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="4ff30-162">Registrieren eines benutzerdefinierten Konverters</span><span class="sxs-lookup"><span data-stu-id="4ff30-162">Register a custom converter</span></span>

<span data-ttu-id="4ff30-163">*Registrieren Sie* einen benutzerdefinierten Konverter, damit die Methoden `Serialize` und `Deserialize` diesen verwenden.</span><span class="sxs-lookup"><span data-stu-id="4ff30-163">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="4ff30-164">Wählen Sie einen der folgenden Ansätze aus:</span><span class="sxs-lookup"><span data-stu-id="4ff30-164">Choose one of the following approaches:</span></span>

* <span data-ttu-id="4ff30-165">Hinzufügen einer Instanz des Konverters zu der <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializerOptions.Converters?displayProperty=nameWithType>-Sammlung.</span><span class="sxs-lookup"><span data-stu-id="4ff30-165">Add an instance of the converter class to the <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="4ff30-166">Anwenden des [[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute)-Attributs auf die Eigenschaften, die den benutzerdefinierten Konverter benötigen.</span><span class="sxs-lookup"><span data-stu-id="4ff30-166">Apply the [[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="4ff30-167">Anwenden des [[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute)-Attributs auf eine Klasse oder Struktur, die einen benutzerdefinierten Werttyp darstellt.</span><span class="sxs-lookup"><span data-stu-id="4ff30-167">Apply the [[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="4ff30-168">Registrierungsbeispiel – Converters-Sammlung</span><span class="sxs-lookup"><span data-stu-id="4ff30-168">Registration sample - Converters collection</span></span>

<span data-ttu-id="4ff30-169">Im Folgenden finden Sie ein Beispiel, mit dem der <xref:System.ComponentModel.DateTimeOffsetConverter> zum Standard für Eigenschaften vom Typ <xref:System.DateTimeOffset> gemacht wird:</span><span class="sxs-lookup"><span data-stu-id="4ff30-169">Here's an example that makes the <xref:System.ComponentModel.DateTimeOffsetConverter> the default for properties of type <xref:System.DateTimeOffset>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetSerialize)]

<span data-ttu-id="4ff30-170">Angenommen, Sie serialisieren eine Instanz des folgenden Typs:</span><span class="sxs-lookup"><span data-stu-id="4ff30-170">Suppose you serialize an instance of the following type:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="4ff30-171">Hier sehen Sie ein Beispiel für eine JSON-Ausgabe, die anzeigt, dass der benutzerdefinierte Konverter verwendet wurde:</span><span class="sxs-lookup"><span data-stu-id="4ff30-171">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="4ff30-172">Der folgende Code verwendet denselben Ansatz zum Deserialisieren mithilfe des benutzerdefinierten `DateTimeOffset`-Konverters:</span><span class="sxs-lookup"><span data-stu-id="4ff30-172">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="4ff30-173">Registrierungsbeispiel – [JsonConverter]-Attribut für eine Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="4ff30-173">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="4ff30-174">Im folgenden Code wird ein benutzerdefinierter Konverter für die `Date`-Eigenschaft ausgewählt:</span><span class="sxs-lookup"><span data-stu-id="4ff30-174">The following code selects a custom converter for the `Date` property:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithConverterAttribute)]

<span data-ttu-id="4ff30-175">Der Code zum Serialisieren von `WeatherForecastWithConverterAttribute` erfordert nicht die Verwendung von `JsonSerializeOptions.Converters`:</span><span class="sxs-lookup"><span data-stu-id="4ff30-175">The code to serialize `WeatherForecastWithConverterAttribute` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetSerialize)]

<span data-ttu-id="4ff30-176">Der Code zum Deserialisieren erfordert ebenfalls nicht die Verwendung von `Converters`:</span><span class="sxs-lookup"><span data-stu-id="4ff30-176">The code to deserialize also doesn't require the use of `Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="4ff30-177">Registrierungsbeispiel – [JsonConverter]-Attribut für einen Typ</span><span class="sxs-lookup"><span data-stu-id="4ff30-177">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="4ff30-178">Der folgende Code erstellt eine Struktur und wendet das `[JsonConverter]`-Attribut darauf an:</span><span class="sxs-lookup"><span data-stu-id="4ff30-178">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Temperature.cs)]

<span data-ttu-id="4ff30-179">Hier sehen Sie den benutzerdefinierten Konverter für die vorangehende Struktur:</span><span class="sxs-lookup"><span data-stu-id="4ff30-179">Here's the custom converter for the preceding struct:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/TemperatureConverter.cs)]

<span data-ttu-id="4ff30-180">Das `[JsonConvert]`-Attribut der Struktur registriert den benutzerdefinierten Konverter als Standard für Eigenschaften vom Typ `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="4ff30-180">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="4ff30-181">Der Konverter wird automatisch für die `TemperatureCelsius`-Eigenschaft des folgenden Typs verwendet, wenn Sie sie serialisieren oder deserialisieren:</span><span class="sxs-lookup"><span data-stu-id="4ff30-181">The converter is automatically used on the `TemperatureCelsius` property of the following type when you serialize or deserialize it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithTemperatureStruct)]

## <a name="converter-registration-precedence"></a><span data-ttu-id="4ff30-182">Rangfolge für die Registrierung von Konvertern</span><span class="sxs-lookup"><span data-stu-id="4ff30-182">Converter registration precedence</span></span>

<span data-ttu-id="4ff30-183">Während der Serialisierung oder Deserialisierung wird für jedes JSON-Element ein Konverter in der folgenden Reihenfolge ausgewählt, wobei die Auflistung von der höchsten Priorität zur niedrigsten erfolgt:</span><span class="sxs-lookup"><span data-stu-id="4ff30-183">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="4ff30-184">Auf eine Eigenschaft angewendeter `[JsonConverter]`.</span><span class="sxs-lookup"><span data-stu-id="4ff30-184">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="4ff30-185">Ein der `Converters`-Sammlung hinzugefügt er Konverter.</span><span class="sxs-lookup"><span data-stu-id="4ff30-185">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="4ff30-186">Auf einen benutzerdefinierten Werttyp oder ein POCO angewendeter `[JsonConverter]`.</span><span class="sxs-lookup"><span data-stu-id="4ff30-186">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="4ff30-187">Wenn mehrere benutzerdefinierte Konverter für einen Typ in der `Converters`-Sammlung registriert sind, wird der erste Konverter verwendet, der für `CanConvert` „true“ zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="4ff30-187">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="4ff30-188">Ein integrierter Konverter wird nur ausgewählt, wenn kein anwendbarer benutzerdefinierter Konverter registriert ist.</span><span class="sxs-lookup"><span data-stu-id="4ff30-188">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="4ff30-189">Konverterbeispiele für gängige Szenarien</span><span class="sxs-lookup"><span data-stu-id="4ff30-189">Converter samples for common scenarios</span></span>

<span data-ttu-id="4ff30-190">In den folgenden Abschnitten werden Konverterbeispiele bereitgestellt, in denen einige gängige Szenarien behandelt werden, die von integrierten Funktionen nicht verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="4ff30-190">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

* [<span data-ttu-id="4ff30-191">Deserialisieren abgeleiteter Typen in Objekteigenschaften</span><span class="sxs-lookup"><span data-stu-id="4ff30-191">Deserialize inferred types to object properties</span></span>](#deserialize-inferred-types-to-object-properties)
* [<span data-ttu-id="4ff30-192">Unterstützung für Wörterbücher mit Schlüsseln, die keine Zeichenfolgen sind</span><span class="sxs-lookup"><span data-stu-id="4ff30-192">Support Dictionary with non-string key</span></span>](#support-dictionary-with-non-string-key)
* [<span data-ttu-id="4ff30-193">Unterstützung polymorpher Deserialisierung</span><span class="sxs-lookup"><span data-stu-id="4ff30-193">Support polymorphic deserialization</span></span>](#support-polymorphic-deserialization)

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="4ff30-194">Deserialisieren abgeleiteter Typen in Objekteigenschaften</span><span class="sxs-lookup"><span data-stu-id="4ff30-194">Deserialize inferred types to object properties</span></span>

<span data-ttu-id="4ff30-195">Beim Deserialisieren in eine Eigenschaft vom Typ `object` wird ein `JsonElement` Objekt erstellt.</span><span class="sxs-lookup"><span data-stu-id="4ff30-195">When deserializing to a property of type `object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="4ff30-196">Der Grund dafür ist, dass der Deserialisierer nicht weiß, welcher CLR-Typ erstellt werden soll, und nicht versucht, diesen vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="4ff30-196">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="4ff30-197">Wenn z. B. eine JSON-Eigenschaft den Wert „true“ hat, leitet der Deserialisierer nicht ab, dass der Wert vom Typ `Boolean` ist, und wenn ein Element „01/01/2019“ aufweist, leitet der Deserialisierer nicht ab, dass es sich um einen `DateTime`-Typ handelt.</span><span class="sxs-lookup"><span data-stu-id="4ff30-197">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="4ff30-198">Typableitung kann ungenau sein.</span><span class="sxs-lookup"><span data-stu-id="4ff30-198">Type inference can be inaccurate.</span></span> <span data-ttu-id="4ff30-199">Wenn der Deserialisierer eine JSON-Zahl, die kein Dezimaltrennzeichen aufweist, als `long` analysiert, kann dies zu einem „außerhalb des zulässigen Bereichs“-Probleme führen, wenn der Wert ursprünglich als `ulong` oder `BigInteger` serialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="4ff30-199">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="4ff30-200">Wird eine Zahl, die ein Dezimaltrennzeichen aufweist, als `double` analysiert, kann hierdurch die Genauigkeit verloren gehen, wenn die Zahl ursprünglich als `decimal` serialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="4ff30-200">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="4ff30-201">Für Szenarien, die eine Typableitung erfordern, zeigt der folgende Code einen benutzerdefinierten Konverter für `object`-Eigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="4ff30-201">For scenarios that require type inference, the following code shows a custom converter for `object` properties.</span></span> <span data-ttu-id="4ff30-202">Der Code konvertiert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4ff30-202">The code converts:</span></span>

* <span data-ttu-id="4ff30-203">`true` un `false` in `Boolean`</span><span class="sxs-lookup"><span data-stu-id="4ff30-203">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="4ff30-204">Zahlen ohne Dezimaltrennzeichen in `long`</span><span class="sxs-lookup"><span data-stu-id="4ff30-204">Numbers without a decimal to `long`</span></span>
* <span data-ttu-id="4ff30-205">Zahlen mit Dezimaltrennzeichen in `double`</span><span class="sxs-lookup"><span data-stu-id="4ff30-205">Numbers with a decimal to `double`</span></span>
* <span data-ttu-id="4ff30-206">Datumsangaben in `DateTime`</span><span class="sxs-lookup"><span data-stu-id="4ff30-206">Dates to `DateTime`</span></span>
* <span data-ttu-id="4ff30-207">Zeichenfolgen in `string`</span><span class="sxs-lookup"><span data-stu-id="4ff30-207">Strings to `string`</span></span>
* <span data-ttu-id="4ff30-208">Alles andere in `JsonElement`</span><span class="sxs-lookup"><span data-stu-id="4ff30-208">Everything else to `JsonElement`</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ObjectToInferredTypesConverter.cs)]

<span data-ttu-id="4ff30-209">Der folgende Code registriert den Konverter:</span><span class="sxs-lookup"><span data-stu-id="4ff30-209">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeInferredTypesToObject.cs?name=SnippetRegister)]

<span data-ttu-id="4ff30-210">Hier ist ein Beispieltyp mit `object`-Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="4ff30-210">Here's an example type with `object` properties:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithObjectProperties)]

<span data-ttu-id="4ff30-211">Das folgende Beispiel für zu deserialisierenden JSON-Code enthält Werte, die als `DateTime`, `long` und `string` deserialisiert werden:</span><span class="sxs-lookup"><span data-stu-id="4ff30-211">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="4ff30-212">Ohne den benutzerdefinierten Konverter fügt die Deserialisierung eine `JsonElement` in jede Eigenschaft ein.</span><span class="sxs-lookup"><span data-stu-id="4ff30-212">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="4ff30-213">Der Ordner [unit tests](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) (Komponententests) im `System.Text.Json.Serialization`-Namespace enthält weitere Beispiele für benutzerdefinierte Konverter, die die Deserialisierung in `object`-Eigenschaften verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="4ff30-213">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to `object` properties.</span></span>

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="4ff30-214">Unterstützung für Wörterbücher mit Schlüsseln, die keine Zeichenfolgen sind</span><span class="sxs-lookup"><span data-stu-id="4ff30-214">Support Dictionary with non-string key</span></span>

<span data-ttu-id="4ff30-215">Die integrierte Unterstützung für Wörterbuchsammlungen ist für `Dictionary<string, TValue>`.</span><span class="sxs-lookup"><span data-stu-id="4ff30-215">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="4ff30-216">Das heißt, der Schlüssel muss eine Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="4ff30-216">That is, the key must be a string.</span></span> <span data-ttu-id="4ff30-217">Um ein Wörterbuch mit einem Schlüssel vom Typ „integer“ (Ganzzahl) oder einem anderen Typ zu unterstützen, ist ein benutzerdefinierter Konverter erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4ff30-217">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="4ff30-218">Im folgenden Code wird ein benutzerdefinierter Konverter gezeigt, der mit `Dictionary<Enum,TValue>` arbeitet:</span><span class="sxs-lookup"><span data-stu-id="4ff30-218">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="4ff30-219">Der folgende Code registriert den Konverter:</span><span class="sxs-lookup"><span data-stu-id="4ff30-219">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripDictionaryTkeyEnumTValue.cs?name=SnippetRegister)]

<span data-ttu-id="4ff30-220">Der Konverter kann die `TemperatureRanges`-Eigenschaft der folgenden Klasse serialisieren und deserialisieren, die die folgende `Enum` verwendet:</span><span class="sxs-lookup"><span data-stu-id="4ff30-220">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnumDictionary)]

<span data-ttu-id="4ff30-221">Die JSON-Ausgabe der Serialisierung sieht wie im folgenden Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="4ff30-221">The JSON output from serialization looks like the following example:</span></span>

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

<span data-ttu-id="4ff30-222">Der Ordner [unit tests](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) (Komponententests) im `System.Text.Json.Serialization`-Namespace enthält weitere Beispiele für benutzerdefinierte Konverter, die Wörterbücher mit Schlüsseln, die keine Zeichenfolgen sind, verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="4ff30-222">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="4ff30-223">Unterstützung polymorpher Deserialisierung</span><span class="sxs-lookup"><span data-stu-id="4ff30-223">Support polymorphic deserialization</span></span>

<span data-ttu-id="4ff30-224">Integrierte Funktionen bieten einen begrenzten Funktionsbereich der [polymorphen Serialisierung](system-text-json-how-to.md#serialize-properties-of-derived-classes), aber gar keine Unterstützung für Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="4ff30-224">Built-in features provide a limited range of [polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) but no support for deserialization at all.</span></span> <span data-ttu-id="4ff30-225">Die Deserialisierung erfordert einen benutzerdefinierten Konverter.</span><span class="sxs-lookup"><span data-stu-id="4ff30-225">Deserialization requires a custom converter.</span></span>

<span data-ttu-id="4ff30-226">Angenommen, Sie verfügen beispielsweise über eine abstrakte Basisklasse `Person` mit den abgeleiteten Klassen `Employee` und `Customer`.</span><span class="sxs-lookup"><span data-stu-id="4ff30-226">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="4ff30-227">Polymorphe Deserialisierung bedeutet, dass Sie zur Entwurfszeit `Person` als Deserialisierungsziel angeben können, und dass die Objekte `Customer` und `Employee` im JSON-Code zur Laufzeit ordnungsgemäß deserialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="4ff30-227">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at runtime.</span></span> <span data-ttu-id="4ff30-228">Während der Deserialisierung müssen Sie nach Hinweisen suchen, die den erforderlichen Typ in JSON identifizieren.</span><span class="sxs-lookup"><span data-stu-id="4ff30-228">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="4ff30-229">Die Arten der verfügbaren Hinweise variieren in jedem Szenario.</span><span class="sxs-lookup"><span data-stu-id="4ff30-229">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="4ff30-230">Beispielsweise kann eine Diskriminatoreigenschaft verfügbar sein, oder Sie müssen sich darauf verlassen, dass eine bestimmte Eigenschaft vorhanden oder nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4ff30-230">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="4ff30-231">Das aktuelle Release von `System.Text.Json` stellt keine Attribute bereit, um anzugeben, wie polymorphe Deserialisierungsszenarien behandelt werden sollen, sodass benutzerdefinierte Konverter erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4ff30-231">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="4ff30-232">Der folgende Code zeigt eine Basisklasse, zwei abgeleitete Klassen und einen benutzerdefinierten Konverter für diese.</span><span class="sxs-lookup"><span data-stu-id="4ff30-232">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="4ff30-233">Der Konverter verwendet eine Diskriminatoreigenschaft, um die polymorphe Deserialisierung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="4ff30-233">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="4ff30-234">Der Typdiskriminator befindet sich nicht in den Klassendefinitionen, wird aber während der Serialisierung erstellt und während der Deserialisierung gelesen.</span><span class="sxs-lookup"><span data-stu-id="4ff30-234">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Person.cs?name=SnippetPerson)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/PersonConverterWithTypeDiscriminator.cs)]

<span data-ttu-id="4ff30-235">Der folgende Code registriert den Konverter:</span><span class="sxs-lookup"><span data-stu-id="4ff30-235">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPolymorphic.cs?name=SnippetRegister)]

<span data-ttu-id="4ff30-236">Das JSON kann mit demselben Konverter deserialisiert werde, mit dem es auch serialisiert wurde, z. B.:</span><span class="sxs-lookup"><span data-stu-id="4ff30-236">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

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

<span data-ttu-id="4ff30-237">Mit dem Konvertercode im vorherigen Beispiel wird jede Eigenschaft manuell gelesen und geschrieben.</span><span class="sxs-lookup"><span data-stu-id="4ff30-237">The converter code in the preceding example reads and writes each property manually.</span></span> <span data-ttu-id="4ff30-238">Eine Alternative besteht darin, `Deserialize` oder `Serialize` aufzurufen, um einen Teil der Arbeit zu erledigen.</span><span class="sxs-lookup"><span data-stu-id="4ff30-238">An alternative is to call `Deserialize` or `Serialize` to do some of the work.</span></span> <span data-ttu-id="4ff30-239">Ein Beispiel hierzu finden Sie in [diesem StackOverflow-Beitrag](https://stackoverflow.com/a/59744873/12509023).</span><span class="sxs-lookup"><span data-stu-id="4ff30-239">For an example, see [this StackOverflow post](https://stackoverflow.com/a/59744873/12509023).</span></span>

## <a name="other-custom-converter-samples"></a><span data-ttu-id="4ff30-240">Weitere Beispiele für benutzerdefinierte Konverter</span><span class="sxs-lookup"><span data-stu-id="4ff30-240">Other custom converter samples</span></span>

<span data-ttu-id="4ff30-241">Im Artikel [Migrieren von Newtonsoft.Json zu System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) finden Sie zusätzliche Beispiele für benutzerdefinierte Konverter.</span><span class="sxs-lookup"><span data-stu-id="4ff30-241">The [Migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) article contains additional samples of custom converters.</span></span>

<span data-ttu-id="4ff30-242">Der Ordner [unit tests](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) (Komponententests) im `System.Text.Json.Serialization`-Quellcode enthält weitere Beispiele für benutzerdefinierte Konverter, wie z. B.:</span><span class="sxs-lookup"><span data-stu-id="4ff30-242">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* <span data-ttu-id="4ff30-243">[Int32-Konverter, der bei der Deserialisierung Null in 0 konvertiert](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span><span class="sxs-lookup"><span data-stu-id="4ff30-243">[Int32 converter that converts null to 0 on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span></span>
* <span data-ttu-id="4ff30-244">[Int32-Konverter, der beim Deserialisieren sowohl Zeichenfolgen- als auch Zahlenwerte zulässt](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span><span class="sxs-lookup"><span data-stu-id="4ff30-244">[Int32 converter that allows both string and number values on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span></span>
* <span data-ttu-id="4ff30-245">[Enum-Konverter](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span><span class="sxs-lookup"><span data-stu-id="4ff30-245">[Enum converter](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span></span>
* <span data-ttu-id="4ff30-246">[List\<T>-Konverter, der externe Daten akzeptiert](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span><span class="sxs-lookup"><span data-stu-id="4ff30-246">[List\<T> converter that accepts external data](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span></span>
* <span data-ttu-id="4ff30-247">[„Long[]“-Konverter, der mit einer durch Trennzeichen getrennten Liste von Zahlen arbeitet](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span><span class="sxs-lookup"><span data-stu-id="4ff30-247">[Long[] converter that works with a comma-delimited list of numbers](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span></span>

<span data-ttu-id="4ff30-248">Wenn Sie einen Konverter erstellen müssen, der das Verhalten eines vorhandenen integrierten Konverters ändert, können Sie [den Quellcode des vorhandenen Konverters](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) abrufen, um diesen als Ausgangspunkt für die Anpassung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4ff30-248">If you need to make a converter that modifies the behavior of an existing built-in converter, you can get [the source code of the existing converter](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) to serve as a starting point for customization.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4ff30-249">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="4ff30-249">Additional resources</span></span>

* <span data-ttu-id="4ff30-250">[Quellcode für integrierte Konverter](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span><span class="sxs-lookup"><span data-stu-id="4ff30-250">[Source code for built-in converters](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span></span>
* <span data-ttu-id="4ff30-251">[Unterstützung von „DateTime“ und „DateTimeOffset“ in System.Text.Json](../datetime/system-text-json-support.md)</span><span class="sxs-lookup"><span data-stu-id="4ff30-251">[DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md)</span></span>
* <span data-ttu-id="4ff30-252">[System.Text.Json – Übersicht](system-text-json-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4ff30-252">[System.Text.Json overview](system-text-json-overview.md)</span></span>
* <span data-ttu-id="4ff30-253">[Verwenden von System.Text.Json](system-text-json-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="4ff30-253">[How to use System.Text.Json](system-text-json-how-to.md)</span></span>
* <span data-ttu-id="4ff30-254">[Migrieren von Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="4ff30-254">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* <span data-ttu-id="4ff30-255">[System.Text.Json-API-Referenz](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="4ff30-255">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="4ff30-256">[System.Text.Json-Serialisierungs-API-Referenz](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="4ff30-256">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
