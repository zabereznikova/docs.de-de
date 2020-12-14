---
title: Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung – .NET
description: Erfahren Sie, wie Sie benutzerdefinierte Konverter für JSON-Serialisierungsklassen erstellen, die im System.Text.Json-Namespace bereitgestellt werden.
ms.date: 12/09/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: 33334ccd8bad4ac5a9f5dccde79ff3ae09ca8f89
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008863"
---
# <a name="how-to-write-custom-converters-for-json-serialization-marshalling-in-net"></a><span data-ttu-id="0f0a0-103">Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung (Marshallen) in .NET</span><span class="sxs-lookup"><span data-stu-id="0f0a0-103">How to write custom converters for JSON serialization (marshalling) in .NET</span></span>

<span data-ttu-id="0f0a0-104">In diesem Artikel wird gezeigt, wie Sie benutzerdefinierte Konverter für JSON-Serialisierungsklassen erstellen, die im <xref:System.Text.Json>-Namespace bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-104">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:System.Text.Json> namespace.</span></span> <span data-ttu-id="0f0a0-105">Eine Einführung zu `System.Text.Json` finden Sie unter [Serialisieren und Deserialisieren von JSON-Daten in .NET](system-text-json-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="0f0a0-105">For an introduction to `System.Text.Json`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="0f0a0-106">Ein *Konverter* ist eine Klasse, die ein Objekt oder einen Wert in und aus JSON konvertiert.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-106">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="0f0a0-107">Der `System.Text.Json`-Namespace verfügt über integrierte Konverter für die meisten primitiven Typen, die JavaScript-Primitiven entsprechen.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-107">The `System.Text.Json` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="0f0a0-108">Sie können benutzerdefinierte Konverter schreiben:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-108">You can write custom converters:</span></span>

* <span data-ttu-id="0f0a0-109">Um das Standardverhalten eines integrierten Konverters außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-109">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="0f0a0-110">Sie könnten beispielsweise beschließen, dass `DateTime`-Werte im Format MM/TT/JJJJ dargestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-110">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format.</span></span> <span data-ttu-id="0f0a0-111">Standardmäßig wird ISO 8601-1:2019 einschließlich des Profils RFC 3339 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-111">By default, ISO 8601-1:2019 is supported, including the RFC 3339 profile.</span></span> <span data-ttu-id="0f0a0-112">Weitere Informationen finden Sie unter [Unterstützung von „DateTime“ und „DateTimeOffset“ in System.Text.Json](../datetime/system-text-json-support.md).</span><span class="sxs-lookup"><span data-stu-id="0f0a0-112">For more information, see [DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md).</span></span>
* <span data-ttu-id="0f0a0-113">Um einen benutzerdefinierten Werttyp zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-113">To support a custom value type.</span></span> <span data-ttu-id="0f0a0-114">Beispielsweise eine `PhoneNumber`-Struktur.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-114">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="0f0a0-115">Sie können auch benutzerdefinierte Konverter schreiben, um `System.Text.Json` mit Funktionen anzupassen oder zu erweitern, die nicht im aktuellen Release enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-115">You can also write custom converters to customize or extend `System.Text.Json` with functionality not included in the current release.</span></span> <span data-ttu-id="0f0a0-116">Folgende Szenarien werden später in diesem Artikel abgedeckt:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-116">The following scenarios are covered later in this article:</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="0f0a0-117">[Deserialisieren abgeleiteter Typen in Objekteigenschaften](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="0f0a0-117">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="0f0a0-118">[Unterstützung polymorpher Deserialisierung](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="0f0a0-118">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>
* <span data-ttu-id="0f0a0-119">[Unterstützung von Roundtrips für Stack\<T>](#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="0f0a0-119">[Support round-trip for Stack\<T>](#support-round-trip-for-stackt).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="0f0a0-120">[Deserialisieren abgeleiteter Typen in Objekteigenschaften](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="0f0a0-120">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="0f0a0-121">[Unterstützung für Wörterbücher mit Schlüsseln, die keine Zeichenfolgen sind](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="0f0a0-121">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="0f0a0-122">[Unterstützung polymorpher Deserialisierung](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="0f0a0-122">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>
* <span data-ttu-id="0f0a0-123">[Unterstützung von Roundtrips für Stack\<T>](#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="0f0a0-123">[Support round-trip for Stack\<T>](#support-round-trip-for-stackt).</span></span>
::: zone-end

<span data-ttu-id="0f0a0-124">Berücksichtigen Sie beim Programmieren eines benutzerdefinierten Konverters die erheblichen Leistungseinbußen, die bei der Verwendung neuer <xref:System.Text.Json.JsonSerializerOptions>-Instanzen entstehen.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-124">In the code you write for a custom converter, be aware of the substantial performance penalty for using new <xref:System.Text.Json.JsonSerializerOptions> instances.</span></span> <span data-ttu-id="0f0a0-125">Weitere Informationen finden Sie unter [Wiederverwenden von JsonSerializerOptions-Instanzen](system-text-json-configure-options.md#reuse-jsonserializeroptions-instances).</span><span class="sxs-lookup"><span data-stu-id="0f0a0-125">For more information, see [Reuse JsonSerializerOptions instances](system-text-json-configure-options.md#reuse-jsonserializeroptions-instances).</span></span>

## <a name="custom-converter-patterns"></a><span data-ttu-id="0f0a0-126">Benutzerdefinierte Konvertermuster</span><span class="sxs-lookup"><span data-stu-id="0f0a0-126">Custom converter patterns</span></span>

<span data-ttu-id="0f0a0-127">Es gibt zwei Muster zum Erstellen eines benutzerdefinierten Konverters: das grundlegende Muster und das Factorymuster.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-127">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="0f0a0-128">Das Factorymuster ist für Konverter vorgesehen, die den `Enum`-Typ oder offene generische Typen verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-128">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="0f0a0-129">Das grundlegende Muster ist für nicht generische und geschlossene generische Typen gedacht.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-129">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="0f0a0-130">Konverter für die folgenden Typen erfordern z. B. das Factorymuster:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-130">For example, converters for the following types require the factory pattern:</span></span>

* <xref:System.Collections.Generic.Dictionary%602>
* <xref:System.Enum>
* <xref:System.Collections.Generic.List%601>

<span data-ttu-id="0f0a0-131">Einige Beispiele für Typen, die vom grundlegenden Muster verarbeitet werden können, sind u. a.:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-131">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* <xref:System.DateTime>
* <xref:System.Int32>

<span data-ttu-id="0f0a0-132">Das grundlegende Muster erstellt eine Klasse, die einen Typ verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-132">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="0f0a0-133">Das Factorymuster erstellt eine Klasse, die zur Laufzeit bestimmt, welcher spezifische Typ erforderlich ist, und erstellt dynamisch den entsprechenden Konverter.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-133">The factory pattern creates a class that determines, at run time, which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="0f0a0-134">Grundlegender Konverter – Beispiel</span><span class="sxs-lookup"><span data-stu-id="0f0a0-134">Sample basic converter</span></span>

<span data-ttu-id="0f0a0-135">Das folgende Beispiel ist ein Konverter, der die Standardserialisierung für einen vorhandenen Datentyp außer Kraft setzt.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-135">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="0f0a0-136">Der Konverter verwendet das Format „mm/dd/yyyy“ für `DateTimeOffset`-Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-136">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DateTimeOffsetConverter.cs":::

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="0f0a0-137">Factorymusterkonverter – Beispiel</span><span class="sxs-lookup"><span data-stu-id="0f0a0-137">Sample factory pattern converter</span></span>

<span data-ttu-id="0f0a0-138">Im folgenden Code wird ein benutzerdefinierter Konverter gezeigt, der mit `Dictionary<Enum,TValue>` arbeitet.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-138">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="0f0a0-139">Der Code folgt dem Factorymuster, da der erste generische Typparameter `Enum` und der zweite offen ist.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-139">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="0f0a0-140">Die `CanConvert`-Methode gibt `true` nur für ein `Dictionary` mit zwei generischen Parametern zurück, wobei der erste ein `Enum`-Typ ist.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-140">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="0f0a0-141">Der innere Konverter ruft einen vorhandenen Konverter ab, um jeglichen Typ zu verarbeiten, der zur Laufzeit für `TValue` bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-141">The inner converter gets an existing converter to handle whichever type is provided at run time for `TValue`.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DictionaryTKeyEnumTValueConverter.cs":::

<span data-ttu-id="0f0a0-142">Der vorangehende Code ist identisch mit dem, der weiter unten in diesem Artikel unter [Unterstützung für Wörterbücher mit Schlüsseln, die keine Zeichenfolgen sind](#support-dictionary-with-non-string-key) gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-142">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="0f0a0-143">Schritte zum Einhalten des grundlegenden Musters</span><span class="sxs-lookup"><span data-stu-id="0f0a0-143">Steps to follow the basic pattern</span></span>

<span data-ttu-id="0f0a0-144">Die folgenden Schritte erläutern, wie Sie einen Konverter erstellen, indem Sie dem grundlegenden Muster folgen:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-144">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="0f0a0-145">Erstellen Sie eine Klasse, die von <xref:System.Text.Json.Serialization.JsonConverter%601> abgeleitet ist, wobei `T` der Typ ist, der serialisiert und deserialisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-145">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="0f0a0-146">Setzen Sie die `Read`-Methode außer Kraft, um den eingehenden JSON-Code zu deserialisieren und in den Typ `T` zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-146">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="0f0a0-147">Verwenden Sie den <xref:System.Text.Json.Utf8JsonReader>, der an die Methode übergeben wird, um den JSON-Code zu lesen.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-147">Use the <xref:System.Text.Json.Utf8JsonReader> that is passed to the method to read the JSON.</span></span>
* <span data-ttu-id="0f0a0-148">Setzen Sie die `Write`-Methode außer Kraft, um das eingehende Objekt vom Typ `T` zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-148">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="0f0a0-149">Verwenden Sie den <xref:System.Text.Json.Utf8JsonWriter>, der an die Methode übergeben wird, um den JSON-Code zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-149">Use the <xref:System.Text.Json.Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="0f0a0-150">Setzen Sie die `CanConvert`-Methode nur außer Kraft, wenn dies notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-150">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="0f0a0-151">Die Standardimplementierung gibt `true` zurück, wenn der zu konvertierende Typ vom Typ `T` ist.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-151">The default implementation returns `true` when the type to convert is of type `T`.</span></span> <span data-ttu-id="0f0a0-152">Daher müssen Konverter, die nur den Typ `T` unterstützen, diese Methode nicht außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-152">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="0f0a0-153">Ein Beispiel für einen Konverter, der diese Methode außer Kraft setzen muss, finden Sie im weiter unten in diesem Artikel im Abschnitt [Polymorphe Deserialisierung](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="0f0a0-153">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="0f0a0-154">Sie können den [Quellcode des integrierten Konverters](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/) als Referenzimplementierungen zum Schreiben von benutzerdefinierten Konvertern verwenden.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-154">You can refer to the [built-in converters source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="0f0a0-155">Schritte zum Einhalten des Factorymusters</span><span class="sxs-lookup"><span data-stu-id="0f0a0-155">Steps to follow the factory pattern</span></span>

<span data-ttu-id="0f0a0-156">Die folgenden Schritte erläutern, wie Sie einen Konverter erstellen, indem Sie dem Factorymuster folgen:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-156">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="0f0a0-157">Erstellen Sie eine von der <xref:System.Text.Json.Serialization.JsonConverterFactory>-Klasse abgeleitete Klasse.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-157">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="0f0a0-158">Überschreiben Sie die `CanConvert`-Methode, um „true“ zurückzugeben, wenn der zu konvertierende Typ einer ist, den der Konverter verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-158">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="0f0a0-159">Wenn der Konverter z. B. für `List<T>` ist, kann er eventuell nur `List<int>`, `List<string>` und `List<DateTime>` verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-159">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span>
* <span data-ttu-id="0f0a0-160">Setzen Sie die `CreateConverter`-Methode außer Kraft, um eine Instanz einer Konverterklasse zurückzugeben, die den zur Laufzeit bereitgestellten zu konvertierenden Typ verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-160">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at run time.</span></span>
* <span data-ttu-id="0f0a0-161">Erstellen Sie die Konverterklasse, die von der `CreateConverter`-Methode instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-161">Create the converter class that the `CreateConverter` method instantiates.</span></span>

<span data-ttu-id="0f0a0-162">Das Factorymuster ist für offene generische Typen erforderlich, da der Code, mit dem ein Objekt in eine und aus einer Zeichenfolge konvertiert werden soll, nicht für alle Typen identisch ist.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-162">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="0f0a0-163">Ein Konverter für einen offenen generischen Typ (z. B. `List<T>`) muss verdeckt einen Konverter für einen geschlossenen generischen Typ erstellen (z. B. `List<DateTime>`).</span><span class="sxs-lookup"><span data-stu-id="0f0a0-163">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="0f0a0-164">Es muss Code geschrieben werden, um jeden geschlossenen generischen Typ zu verarbeiten, den der Konverter verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-164">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="0f0a0-165">Der Typ `Enum` ähnelt einem offenen generischen Typ: Ein Konverter für `Enum` muss verdeckt einen Konverter für einen spezifischen `Enum` (z. B. `WeekdaysEnum`) erstellen.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-165">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span>

## <a name="error-handling"></a><span data-ttu-id="0f0a0-166">Fehlerbehandlung</span><span class="sxs-lookup"><span data-stu-id="0f0a0-166">Error handling</span></span>

<span data-ttu-id="0f0a0-167">Das Serialisierungsmodul beinhaltet spezielle Verarbeitungsmethoden für die Ausnahmetypen <xref:System.Text.Json.JsonException> und <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-167">The serializer provides special handling for exception types <xref:System.Text.Json.JsonException> and <xref:System.NotSupportedException>.</span></span>

### <a name="jsonexception"></a><span data-ttu-id="0f0a0-168">JsonException</span><span class="sxs-lookup"><span data-stu-id="0f0a0-168">JsonException</span></span>

<span data-ttu-id="0f0a0-169">Wenn Sie die Ausnahme `JsonException` ohne Fehlermeldung auslösen, erstellt das Serialisierungsmodul automatisch eine Meldung, die den Pfad zu dem Teil des JSON-Codes enthält, der den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-169">If you throw a `JsonException` without a message, the serializer creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="0f0a0-170">Beispielsweise erzeugt die Anweisung `throw new JsonException()` eine Fehlermeldung wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-170">For example, the statement `throw new JsonException()` produces an error message like the following example:</span></span>

```output
Unhandled exception. System.Text.Json.JsonException:
The JSON value could not be converted to System.Object.
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="0f0a0-171">Wenn Sie eine Meldung wie `throw new JsonException("Error occurred")` angeben, legt das Serialisierungsmodul die Eigenschaften <xref:System.Text.Json.JsonException.Path>, <xref:System.Text.Json.JsonException.LineNumber> und <xref:System.Text.Json.JsonException.BytePositionInLine> dennoch fest.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-171">If you do provide a message (for example, `throw new JsonException("Error occurred")`, the serializer still sets the <xref:System.Text.Json.JsonException.Path>, <xref:System.Text.Json.JsonException.LineNumber>, and <xref:System.Text.Json.JsonException.BytePositionInLine> properties.</span></span>

### <a name="notsupportedexception"></a><span data-ttu-id="0f0a0-172">NotSupportedException</span><span class="sxs-lookup"><span data-stu-id="0f0a0-172">NotSupportedException</span></span>

<span data-ttu-id="0f0a0-173">Wenn Sie die Ausnahme `NotSupportedException` auslösen, sind in der Meldung immer die Pfadinformationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-173">If you throw a `NotSupportedException`, you always get the path information in the message.</span></span> <span data-ttu-id="0f0a0-174">Wenn Sie eine Meldung angeben, werden die Pfadinformationen an diese angefügt.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-174">If you provide a message, the path information is appended to it.</span></span> <span data-ttu-id="0f0a0-175">Beispielsweise erzeugt die Anweisung `throw new NotSupportedException("Error occurred.")` eine Fehlermeldung wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-175">For example, the statement `throw new NotSupportedException("Error occurred.")` produces an error message like the following example:</span></span>

```output
Error occurred. The unsupported member type is located on type
'System.Collections.Generic.Dictionary`2[Samples.SummaryWords,System.Int32]'.
Path: $.TemperatureRanges | LineNumber: 4 | BytePositionInLine: 24
```

### <a name="when-to-throw-which-exception-type"></a><span data-ttu-id="0f0a0-176">Auswahl des richtigen Ausnahmetyps</span><span class="sxs-lookup"><span data-stu-id="0f0a0-176">When to throw which exception type</span></span>

<span data-ttu-id="0f0a0-177">Wenn die JSON-Nutzdaten Token enthalten, die für den deserialisierten Typ nicht gültig sind, sollten Sie die Ausnahme `JsonException` auslösen.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-177">When the JSON payload contains tokens that are not valid for the type being deserialized, throw a `JsonException`.</span></span>

<span data-ttu-id="0f0a0-178">Wenn bestimmte Typen nicht zugelassen werden sollen, lösen Sie die Ausnahme `NotSupportedException` aus.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-178">When you want to disallow certain types, throw a `NotSupportedException`.</span></span> <span data-ttu-id="0f0a0-179">Diese Ausnahme löst das Serialisierungsmodul automatisch für nicht unterstützte Typen aus.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-179">This exception is what the serializer automatically throws for types that are not supported.</span></span> <span data-ttu-id="0f0a0-180">Beispielsweise wird `System.Type` aus Sicherheitsgründen nicht unterstützt, sodass der Versuch, diesen Typ zu deserialisieren, zu einer `NotSupportedException`-Ausnahme führt.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-180">For example, `System.Type` is not supported for security reasons, so an attempt to deserialize it results in a `NotSupportedException`.</span></span>

<span data-ttu-id="0f0a0-181">Sie können bei Bedarf andere Ausnahmen auslösen. Diese enthalten jedoch nicht automatisch JSON-Pfadinformationen.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-181">You can throw other exceptions as needed, but they don't automatically include JSON path information.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="0f0a0-182">Registrieren eines benutzerdefinierten Konverters</span><span class="sxs-lookup"><span data-stu-id="0f0a0-182">Register a custom converter</span></span>

<span data-ttu-id="0f0a0-183">*Registrieren Sie* einen benutzerdefinierten Konverter, damit die Methoden `Serialize` und `Deserialize` diesen verwenden.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-183">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="0f0a0-184">Wählen Sie einen der folgenden Ansätze aus:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-184">Choose one of the following approaches:</span></span>

* <span data-ttu-id="0f0a0-185">Hinzufügen einer Instanz des Konverters zu der <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType>-Sammlung.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-185">Add an instance of the converter class to the <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="0f0a0-186">Anwenden des [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute)-Attributs auf die Eigenschaften, die den benutzerdefinierten Konverter benötigen.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-186">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="0f0a0-187">Anwenden des [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute)-Attributs auf eine Klasse oder Struktur, die einen benutzerdefinierten Werttyp darstellt.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-187">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="0f0a0-188">Registrierungsbeispiel – Converters-Sammlung</span><span class="sxs-lookup"><span data-stu-id="0f0a0-188">Registration sample - Converters collection</span></span>

<span data-ttu-id="0f0a0-189">Im Folgenden finden Sie ein Beispiel, mit dem der <xref:System.ComponentModel.DateTimeOffsetConverter> zum Standard für Eigenschaften vom Typ <xref:System.DateTimeOffset> gemacht wird:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-189">Here's an example that makes the <xref:System.ComponentModel.DateTimeOffsetConverter> the default for properties of type <xref:System.DateTimeOffset>:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RegisterConverterWithConvertersCollection.cs" id="Serialize":::

<span data-ttu-id="0f0a0-190">Angenommen, Sie serialisieren eine Instanz des folgenden Typs:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-190">Suppose you serialize an instance of the following type:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

<span data-ttu-id="0f0a0-191">Hier sehen Sie ein Beispiel für eine JSON-Ausgabe, die anzeigt, dass der benutzerdefinierte Konverter verwendet wurde:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-191">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="0f0a0-192">Der folgende Code verwendet denselben Ansatz zum Deserialisieren mithilfe des benutzerdefinierten `DateTimeOffset`-Konverters:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-192">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RegisterConverterWithConvertersCollection.cs" id="Deserialize":::

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="0f0a0-193">Registrierungsbeispiel – [JsonConverter]-Attribut für eine Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0f0a0-193">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="0f0a0-194">Im folgenden Code wird ein benutzerdefinierter Konverter für die `Date`-Eigenschaft ausgewählt:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-194">The following code selects a custom converter for the `Date` property:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithConverterAttribute":::

<span data-ttu-id="0f0a0-195">Der Code zum Serialisieren von `WeatherForecastWithConverterAttribute` erfordert nicht die Verwendung von `JsonSerializeOptions.Converters`:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-195">The code to serialize `WeatherForecastWithConverterAttribute` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RegisterConverterWithAttributeOnProperty.cs" id="Serialize":::

<span data-ttu-id="0f0a0-196">Der Code zum Deserialisieren erfordert ebenfalls nicht die Verwendung von `Converters`:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-196">The code to deserialize also doesn't require the use of `Converters`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RegisterConverterWithAttributeOnProperty.cs" id="Deserialize":::

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="0f0a0-197">Registrierungsbeispiel – [JsonConverter]-Attribut für einen Typ</span><span class="sxs-lookup"><span data-stu-id="0f0a0-197">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="0f0a0-198">Der folgende Code erstellt eine Struktur und wendet das `[JsonConverter]`-Attribut darauf an:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-198">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Temperature.cs":::

<span data-ttu-id="0f0a0-199">Hier sehen Sie den benutzerdefinierten Konverter für die vorangehende Struktur:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-199">Here's the custom converter for the preceding struct:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/TemperatureConverter.cs":::

<span data-ttu-id="0f0a0-200">Das `[JsonConvert]`-Attribut der Struktur registriert den benutzerdefinierten Konverter als Standard für Eigenschaften vom Typ `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-200">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="0f0a0-201">Der Konverter wird automatisch für die `TemperatureCelsius`-Eigenschaft des folgenden Typs verwendet, wenn Sie sie serialisieren oder deserialisieren:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-201">The converter is automatically used on the `TemperatureCelsius` property of the following type when you serialize or deserialize it:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithTemperatureStruct":::

## <a name="converter-registration-precedence"></a><span data-ttu-id="0f0a0-202">Rangfolge für die Registrierung von Konvertern</span><span class="sxs-lookup"><span data-stu-id="0f0a0-202">Converter registration precedence</span></span>

<span data-ttu-id="0f0a0-203">Während der Serialisierung oder Deserialisierung wird für jedes JSON-Element ein Konverter in der folgenden Reihenfolge ausgewählt, wobei die Auflistung von der höchsten Priorität zur niedrigsten erfolgt:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-203">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="0f0a0-204">Auf eine Eigenschaft angewendeter `[JsonConverter]`.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-204">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="0f0a0-205">Ein der `Converters`-Sammlung hinzugefügt er Konverter.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-205">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="0f0a0-206">Auf einen benutzerdefinierten Werttyp oder ein POCO angewendeter `[JsonConverter]`.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-206">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="0f0a0-207">Wenn mehrere benutzerdefinierte Konverter für einen Typ in der `Converters`-Sammlung registriert sind, wird der erste Konverter verwendet, der für `CanConvert` „true“ zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-207">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="0f0a0-208">Ein integrierter Konverter wird nur ausgewählt, wenn kein anwendbarer benutzerdefinierter Konverter registriert ist.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-208">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="0f0a0-209">Konverterbeispiele für gängige Szenarien</span><span class="sxs-lookup"><span data-stu-id="0f0a0-209">Converter samples for common scenarios</span></span>

<span data-ttu-id="0f0a0-210">In den folgenden Abschnitten werden Konverterbeispiele bereitgestellt, in denen einige gängige Szenarien behandelt werden, die von integrierten Funktionen nicht verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-210">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="0f0a0-211">[Deserialisieren abgeleiteter Typen in Objekteigenschaften](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="0f0a0-211">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="0f0a0-212">[Unterstützung polymorpher Deserialisierung](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="0f0a0-212">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>
* <span data-ttu-id="0f0a0-213">[Unterstützung von Roundtrips für Stack\<T>](#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="0f0a0-213">[Support round-trip for Stack\<T>](#support-round-trip-for-stackt).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="0f0a0-214">[Deserialisieren abgeleiteter Typen in Objekteigenschaften](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="0f0a0-214">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="0f0a0-215">[Unterstützung für Wörterbücher mit Schlüsseln, die keine Zeichenfolgen sind](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="0f0a0-215">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="0f0a0-216">[Unterstützung polymorpher Deserialisierung](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="0f0a0-216">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>
* <span data-ttu-id="0f0a0-217">[Unterstützung von Roundtrips für Stack\<T>](#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="0f0a0-217">[Support round-trip for Stack\<T>](#support-round-trip-for-stackt).</span></span>
::: zone-end

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="0f0a0-218">Deserialisieren abgeleiteter Typen in Objekteigenschaften</span><span class="sxs-lookup"><span data-stu-id="0f0a0-218">Deserialize inferred types to object properties</span></span>

<span data-ttu-id="0f0a0-219">Beim Deserialisieren in eine Eigenschaft vom Typ `object` wird ein `JsonElement` Objekt erstellt.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-219">When deserializing to a property of type `object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="0f0a0-220">Der Grund dafür ist, dass der Deserialisierer nicht weiß, welcher CLR-Typ erstellt werden soll, und nicht versucht, diesen vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-220">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="0f0a0-221">Wenn z. B. eine JSON-Eigenschaft den Wert „true“ hat, leitet der Deserialisierer nicht ab, dass der Wert vom Typ `Boolean` ist, und wenn ein Element „01/01/2019“ aufweist, leitet der Deserialisierer nicht ab, dass es sich um einen `DateTime`-Typ handelt.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-221">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="0f0a0-222">Typableitung kann ungenau sein.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-222">Type inference can be inaccurate.</span></span> <span data-ttu-id="0f0a0-223">Wenn der Deserialisierer eine JSON-Zahl, die kein Dezimaltrennzeichen aufweist, als `long` analysiert, kann dies zu einem „außerhalb des zulässigen Bereichs“-Probleme führen, wenn der Wert ursprünglich als `ulong` oder `BigInteger` serialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-223">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="0f0a0-224">Wird eine Zahl, die ein Dezimaltrennzeichen aufweist, als `double` analysiert, kann hierdurch die Genauigkeit verloren gehen, wenn die Zahl ursprünglich als `decimal` serialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-224">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="0f0a0-225">Für Szenarien, die eine Typableitung erfordern, zeigt der folgende Code einen benutzerdefinierten Konverter für `object`-Eigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-225">For scenarios that require type inference, the following code shows a custom converter for `object` properties.</span></span> <span data-ttu-id="0f0a0-226">Der Code konvertiert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-226">The code converts:</span></span>

* <span data-ttu-id="0f0a0-227">`true` un `false` in `Boolean`</span><span class="sxs-lookup"><span data-stu-id="0f0a0-227">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="0f0a0-228">Zahlen ohne Dezimaltrennzeichen in `long`</span><span class="sxs-lookup"><span data-stu-id="0f0a0-228">Numbers without a decimal to `long`</span></span>
* <span data-ttu-id="0f0a0-229">Zahlen mit Dezimaltrennzeichen in `double`</span><span class="sxs-lookup"><span data-stu-id="0f0a0-229">Numbers with a decimal to `double`</span></span>
* <span data-ttu-id="0f0a0-230">Datumsangaben in `DateTime`</span><span class="sxs-lookup"><span data-stu-id="0f0a0-230">Dates to `DateTime`</span></span>
* <span data-ttu-id="0f0a0-231">Zeichenfolgen in `string`</span><span class="sxs-lookup"><span data-stu-id="0f0a0-231">Strings to `string`</span></span>
* <span data-ttu-id="0f0a0-232">Alles andere in `JsonElement`</span><span class="sxs-lookup"><span data-stu-id="0f0a0-232">Everything else to `JsonElement`</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/ObjectToInferredTypesConverter.cs":::

<span data-ttu-id="0f0a0-233">Der folgende Code registriert den Konverter:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-233">The following code registers the converter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeInferredTypesToObject.cs" id="Register":::

<span data-ttu-id="0f0a0-234">Hier ist ein Beispieltyp mit `object`-Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-234">Here's an example type with `object` properties:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithObjectProperties":::

<span data-ttu-id="0f0a0-235">Das folgende Beispiel für zu deserialisierenden JSON-Code enthält Werte, die als `DateTime`, `long` und `string` deserialisiert werden:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-235">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="0f0a0-236">Ohne den benutzerdefinierten Konverter fügt die Deserialisierung eine `JsonElement` in jede Eigenschaft ein.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-236">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="0f0a0-237">Der Ordner [unit tests](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) (Komponententests) im `System.Text.Json.Serialization`-Namespace enthält weitere Beispiele für benutzerdefinierte Konverter, die die Deserialisierung in `object`-Eigenschaften verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-237">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to `object` properties.</span></span>

::: zone pivot="dotnet-core-3-1"

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="0f0a0-238">Unterstützung für Wörterbücher mit Schlüsseln, die keine Zeichenfolgen sind</span><span class="sxs-lookup"><span data-stu-id="0f0a0-238">Support Dictionary with non-string key</span></span>

<span data-ttu-id="0f0a0-239">Die integrierte Unterstützung für Wörterbuchsammlungen ist für `Dictionary<string, TValue>`.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-239">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="0f0a0-240">Das heißt, der Schlüssel muss eine Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-240">That is, the key must be a string.</span></span> <span data-ttu-id="0f0a0-241">Um ein Wörterbuch mit einem Schlüssel vom Typ „integer“ (Ganzzahl) oder einem anderen Typ zu unterstützen, ist ein benutzerdefinierter Konverter erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-241">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="0f0a0-242">Im folgenden Code wird ein benutzerdefinierter Konverter gezeigt, der mit `Dictionary<Enum,TValue>` arbeitet:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-242">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DictionaryTKeyEnumTValueConverter.cs":::

<span data-ttu-id="0f0a0-243">Der folgende Code registriert den Konverter:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-243">The following code registers the converter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripDictionaryTkeyEnumTValue.cs" id="Register":::

<span data-ttu-id="0f0a0-244">Der Konverter kann die `TemperatureRanges`-Eigenschaft der folgenden Klasse serialisieren und deserialisieren, die die folgende `Enum` verwendet:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-244">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithEnumDictionary":::

<span data-ttu-id="0f0a0-245">Die JSON-Ausgabe der Serialisierung sieht wie im folgenden Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-245">The JSON output from serialization looks like the following example:</span></span>

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

<span data-ttu-id="0f0a0-246">Der Ordner [unit tests](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) (Komponententests) im `System.Text.Json.Serialization`-Namespace enthält weitere Beispiele für benutzerdefinierte Konverter, die Wörterbücher mit Schlüsseln, die keine Zeichenfolgen sind, verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-246">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>
::: zone-end

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="0f0a0-247">Unterstützung polymorpher Deserialisierung</span><span class="sxs-lookup"><span data-stu-id="0f0a0-247">Support polymorphic deserialization</span></span>

<span data-ttu-id="0f0a0-248">Integrierte Funktionen bieten einen begrenzten Funktionsbereich der [polymorphen Serialisierung](system-text-json-polymorphism.md), aber gar keine Unterstützung für Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-248">Built-in features provide a limited range of [polymorphic serialization](system-text-json-polymorphism.md) but no support for deserialization at all.</span></span> <span data-ttu-id="0f0a0-249">Die Deserialisierung erfordert einen benutzerdefinierten Konverter.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-249">Deserialization requires a custom converter.</span></span>

<span data-ttu-id="0f0a0-250">Angenommen, Sie verfügen beispielsweise über eine abstrakte Basisklasse `Person` mit den abgeleiteten Klassen `Employee` und `Customer`.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-250">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="0f0a0-251">Polymorphe Deserialisierung bedeutet, dass Sie zur Entwurfszeit `Person` als Deserialisierungsziel angeben können, und dass die Objekte `Customer` und `Employee` im JSON-Code zur Laufzeit ordnungsgemäß deserialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-251">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at run time.</span></span> <span data-ttu-id="0f0a0-252">Während der Deserialisierung müssen Sie nach Hinweisen suchen, die den erforderlichen Typ in JSON identifizieren.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-252">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="0f0a0-253">Die Arten der verfügbaren Hinweise variieren in jedem Szenario.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-253">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="0f0a0-254">Beispielsweise kann eine Diskriminatoreigenschaft verfügbar sein, oder Sie müssen sich darauf verlassen, dass eine bestimmte Eigenschaft vorhanden oder nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-254">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="0f0a0-255">Das aktuelle Release von `System.Text.Json` stellt keine Attribute bereit, um anzugeben, wie polymorphe Deserialisierungsszenarien behandelt werden sollen, sodass benutzerdefinierte Konverter erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-255">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="0f0a0-256">Der folgende Code zeigt eine Basisklasse, zwei abgeleitete Klassen und einen benutzerdefinierten Konverter für diese.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-256">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="0f0a0-257">Der Konverter verwendet eine Diskriminatoreigenschaft, um die polymorphe Deserialisierung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-257">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="0f0a0-258">Der Typdiskriminator befindet sich nicht in den Klassendefinitionen, wird aber während der Serialisierung erstellt und während der Deserialisierung gelesen.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-258">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Person.cs" id="Person":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/PersonConverterWithTypeDiscriminator.cs":::

<span data-ttu-id="0f0a0-259">Der folgende Code registriert den Konverter:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-259">The following code registers the converter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripPolymorphic.cs" id="Register":::

<span data-ttu-id="0f0a0-260">Das JSON kann mit demselben Konverter deserialisiert werde, mit dem es auch serialisiert wurde, z. B.:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-260">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

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

<span data-ttu-id="0f0a0-261">Mit dem Konvertercode im vorherigen Beispiel wird jede Eigenschaft manuell gelesen und geschrieben.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-261">The converter code in the preceding example reads and writes each property manually.</span></span> <span data-ttu-id="0f0a0-262">Eine Alternative besteht darin, `Deserialize` oder `Serialize` aufzurufen, um einen Teil der Arbeit zu erledigen.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-262">An alternative is to call `Deserialize` or `Serialize` to do some of the work.</span></span> <span data-ttu-id="0f0a0-263">Ein Beispiel hierzu finden Sie in [diesem StackOverflow-Beitrag](https://stackoverflow.com/a/59744873/12509023).</span><span class="sxs-lookup"><span data-stu-id="0f0a0-263">For an example, see [this StackOverflow post](https://stackoverflow.com/a/59744873/12509023).</span></span>

### <a name="support-round-trip-for-stackt"></a><span data-ttu-id="0f0a0-264">Unterstützung von Roundtrips für Stack\<T></span><span class="sxs-lookup"><span data-stu-id="0f0a0-264">Support round trip for Stack\<T></span></span>

<span data-ttu-id="0f0a0-265">Wenn Sie eine JSON-Zeichenfolge in ein <xref:System.Collections.Generic.Stack%601>-Objekt deserialisieren und dieses Objekt anschließend serialisieren, ist die Reihenfolge des Stapelinhalts umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-265">If you deserialize a JSON string into a <xref:System.Collections.Generic.Stack%601> object and then serialize that object, the contents of the stack are in reverse order.</span></span> <span data-ttu-id="0f0a0-266">Dieses Verhalten gilt für die folgenden Typen und Schnittstellen sowie für benutzerdefinierte Typen, die von ihnen abgeleitet werden:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-266">This behavior applies to the following types and interface, and user-defined types that derive from them:</span></span>

* <xref:System.Collections.Stack>
* <xref:System.Collections.Generic.Stack%601>
* <xref:System.Collections.Concurrent.ConcurrentStack%601>
* <xref:System.Collections.Immutable.ImmutableStack%601>
* <xref:System.Collections.Immutable.IImmutableStack%601>

<span data-ttu-id="0f0a0-267">Um die Serialisierung und Deserialisierung zu unterstützen, die die ursprüngliche Reihenfolge im Stapel beibehält, ist ein benutzerdefinierter Konverter erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-267">To support serialization and deserialization that retains the original order in the stack, a custom converter is required.</span></span>

<span data-ttu-id="0f0a0-268">Der folgende Code zeigt einen benutzerdefinierten Konverter, der Roundtrips zu und von `Stack<T>`-Objekten ermöglicht:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-268">The following code shows a custom converter that enables round-tripping to and from `Stack<T>` objects:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/JsonConverterFactoryForStackOfT.cs":::

<span data-ttu-id="0f0a0-269">Der folgende Code registriert den Konverter:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-269">The following code registers the converter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripStackOfT.cs" id="Register":::

## <a name="handle-null-values"></a><span data-ttu-id="0f0a0-270">Behandeln von NULL-Werten</span><span class="sxs-lookup"><span data-stu-id="0f0a0-270">Handle null values</span></span>

<span data-ttu-id="0f0a0-271">Standardmäßig verarbeitet das Serialisierungsmodul NULL-Werte wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-271">By default, the serializer handles null values as follows:</span></span>

* <span data-ttu-id="0f0a0-272">Für Verweis- und <xref:System.Nullable%601>-Typen:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-272">For reference types and <xref:System.Nullable%601> types:</span></span>

  * <span data-ttu-id="0f0a0-273">`null` wird bei der Serialisierung nicht an benutzerdefinierte Konverter übergeben.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-273">It does not pass `null` to custom converters on serialization.</span></span>
  * <span data-ttu-id="0f0a0-274">`JsonTokenType.Null` wird bei der Deserialisierung nicht an benutzerdefinierte Konverter übergeben.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-274">It does not pass `JsonTokenType.Null` to custom converters on deserialization.</span></span>
  * <span data-ttu-id="0f0a0-275">Bei der Deserialisierung wird eine `null`-Instanz zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-275">It returns a `null` instance on deserialization.</span></span>
  * <span data-ttu-id="0f0a0-276">`null` wird bei der Serialisierung direkt mit dem Writer geschrieben.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-276">It writes `null` directly with the writer on serialization.</span></span>

* <span data-ttu-id="0f0a0-277">Für nicht auf NULL festlegbare Werttypen:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-277">For non-nullable value types:</span></span>

  * <span data-ttu-id="0f0a0-278">`JsonTokenType.Null` wird bei der Deserialisierung an benutzerdefinierte Konverter übergeben.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-278">It passes `JsonTokenType.Null` to custom converters on deserialization.</span></span> <span data-ttu-id="0f0a0-279">(Wenn kein benutzerdefinierter Konverter verfügbar ist, wird vom internen Konverter für den Typ die Ausnahme `JsonException` ausgelöst.)</span><span class="sxs-lookup"><span data-stu-id="0f0a0-279">(If no custom converter is available, a `JsonException` exception is thrown by the internal converter for the type.)</span></span>

<span data-ttu-id="0f0a0-280">Dieses Verhalten für die Behandlung von NULL-Werten dient hauptsächlich zum Optimieren der Leistung, indem ein zusätzlicher Rückruf an den Konverter übersprungen wird.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-280">This null-handling behavior is primarily to optimize performance by skipping an extra call to the converter.</span></span> <span data-ttu-id="0f0a0-281">Darüber hinaus wird vermieden, dass Konverter für auf NULL festlegbare Typen gezwungen werden, am Anfang jeder Überschreibung der Methoden `Read` und `Write` nach `null` zu suchen.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-281">In addition, it avoids forcing converters for nullable types to check for `null` at the start of every `Read` and `Write` method override.</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="0f0a0-282">Um einem benutzerdefinierten Konverter zu ermöglichen, `null` für einen Verweis- oder Werttyp zu verarbeiten, überschreiben Sie <xref:System.Text.Json.Serialization.JsonConverter%601.HandleNull%2A?displayProperty=nameWithType> so, dass `true` zurückgegeben wird, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-282">To enable a custom converter to handle `null` for a reference or value type, override <xref:System.Text.Json.Serialization.JsonConverter%601.HandleNull%2A?displayProperty=nameWithType> to return `true`, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CustomConverterHandleNull.cs" highlight="19":::
::: zone-end

## <a name="other-custom-converter-samples"></a><span data-ttu-id="0f0a0-283">Weitere Beispiele für benutzerdefinierte Konverter</span><span class="sxs-lookup"><span data-stu-id="0f0a0-283">Other custom converter samples</span></span>

<span data-ttu-id="0f0a0-284">Im Artikel [Migrieren von Newtonsoft.Json zu System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) finden Sie zusätzliche Beispiele für benutzerdefinierte Konverter.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-284">The [Migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) article contains additional samples of custom converters.</span></span>

<span data-ttu-id="0f0a0-285">Der Ordner [unit tests](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) (Komponententests) im `System.Text.Json.Serialization`-Quellcode enthält weitere Beispiele für benutzerdefinierte Konverter, wie z. B.:</span><span class="sxs-lookup"><span data-stu-id="0f0a0-285">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* <span data-ttu-id="0f0a0-286">[Int32-Konverter, der bei der Deserialisierung Null in 0 konvertiert](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span><span class="sxs-lookup"><span data-stu-id="0f0a0-286">[Int32 converter that converts null to 0 on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span></span>
* <span data-ttu-id="0f0a0-287">[Int32-Konverter, der beim Deserialisieren sowohl Zeichenfolgen- als auch Zahlenwerte zulässt](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span><span class="sxs-lookup"><span data-stu-id="0f0a0-287">[Int32 converter that allows both string and number values on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span></span>
* <span data-ttu-id="0f0a0-288">[Enum-Konverter](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span><span class="sxs-lookup"><span data-stu-id="0f0a0-288">[Enum converter](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span></span>
* <span data-ttu-id="0f0a0-289">[List\<T>-Konverter, der externe Daten akzeptiert](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span><span class="sxs-lookup"><span data-stu-id="0f0a0-289">[List\<T> converter that accepts external data](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span></span>
* <span data-ttu-id="0f0a0-290">[„Long[]“-Konverter, der mit einer durch Trennzeichen getrennten Liste von Zahlen arbeitet](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span><span class="sxs-lookup"><span data-stu-id="0f0a0-290">[Long[] converter that works with a comma-delimited list of numbers](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span></span>

<span data-ttu-id="0f0a0-291">Wenn Sie einen Konverter erstellen müssen, der das Verhalten eines vorhandenen integrierten Konverters ändert, können Sie [den Quellcode des vorhandenen Konverters](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) abrufen, um diesen als Ausgangspunkt für die Anpassung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0f0a0-291">If you need to make a converter that modifies the behavior of an existing built-in converter, you can get [the source code of the existing converter](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) to serve as a starting point for customization.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0f0a0-292">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="0f0a0-292">Additional resources</span></span>

* <span data-ttu-id="0f0a0-293">[Quellcode für integrierte Konverter](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span><span class="sxs-lookup"><span data-stu-id="0f0a0-293">[Source code for built-in converters](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span></span>
* [<span data-ttu-id="0f0a0-294">System.Text.Json – Übersicht</span><span class="sxs-lookup"><span data-stu-id="0f0a0-294">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="0f0a0-295">Vorgehensweise: Serialisieren und Deserialisieren von JSON-Daten</span><span class="sxs-lookup"><span data-stu-id="0f0a0-295">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="0f0a0-296">Instanziieren von JsonSerializerOptions-Instanzen</span><span class="sxs-lookup"><span data-stu-id="0f0a0-296">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="0f0a0-297">Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="0f0a0-297">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="0f0a0-298">Anpassen von Eigenschaftsnamen und -werten</span><span class="sxs-lookup"><span data-stu-id="0f0a0-298">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="0f0a0-299">Ignorieren von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="0f0a0-299">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="0f0a0-300">Zulassen von ungültigem JSON-Code</span><span class="sxs-lookup"><span data-stu-id="0f0a0-300">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="0f0a0-301">Verarbeiten von Überlauf-JSON</span><span class="sxs-lookup"><span data-stu-id="0f0a0-301">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="0f0a0-302">Beibehalten von Verweisen</span><span class="sxs-lookup"><span data-stu-id="0f0a0-302">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="0f0a0-303">Unveränderliche Typen und nicht öffentliche Zugriffsmethoden</span><span class="sxs-lookup"><span data-stu-id="0f0a0-303">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="0f0a0-304">Polymorphe Serialisierung</span><span class="sxs-lookup"><span data-stu-id="0f0a0-304">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="0f0a0-305">Migrieren von Newtonsoft.Json zu System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="0f0a0-305">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="0f0a0-306">Anpassen der Zeichencodierung</span><span class="sxs-lookup"><span data-stu-id="0f0a0-306">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="0f0a0-307">Schreiben benutzerdefinierter Serialisierungsmodule und Deserialisierer</span><span class="sxs-lookup"><span data-stu-id="0f0a0-307">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="0f0a0-308">Unterstützung von DateTime und DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="0f0a0-308">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="0f0a0-309">[System.Text.Json-API-Referenz](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="0f0a0-309">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="0f0a0-310">[System.Text.Json-Serialisierungs-API-Referenz](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="0f0a0-310">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
