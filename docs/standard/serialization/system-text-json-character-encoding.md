---
title: Anpassen der Zeichencodierung mit System.Text.Json
description: Erfahren Sie, wie Sie in .NET die Zeichencodierung beim Serialisieren in und Deserialisieren aus JSON anpassen können.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: cfb83af0c58e0c9dfb73ecb8e2177d255e403fae
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009624"
---
# <a name="how-to-customize-character-encoding-with-no-locsystemtextjson"></a><span data-ttu-id="76c52-103">Anpassen der Zeichencodierung mit System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="76c52-103">How to customize character encoding with System.Text.Json</span></span>

<span data-ttu-id="76c52-104">Standardmäßig escapet der Serialisierer alle Nicht-ASCII-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="76c52-104">By default, the serializer escapes all non-ASCII characters.</span></span> <span data-ttu-id="76c52-105">Das heißt, dass sie durch `\uxxxx` ersetzt werden, wobei `xxxx` der Unicode-Code des Zeichens ist.</span><span class="sxs-lookup"><span data-stu-id="76c52-105">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span> <span data-ttu-id="76c52-106">Wenn die `Summary`-Eigenschaft im folgenden JSON-Code beispielsweise auf Kyrillisch `жарко` festgelegt ist, wird das `WeatherForecast`-Objekt wie in diesem Beispiel gezeigt serialisiert:</span><span class="sxs-lookup"><span data-stu-id="76c52-106">For example, if the `Summary` property in the following JSON is set to Cyrillic `жарко`, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

## <a name="serialize-language-character-sets"></a><span data-ttu-id="76c52-107">Serialisieren von Sprachzeichensätzen</span><span class="sxs-lookup"><span data-stu-id="76c52-107">Serialize language character sets</span></span>

<span data-ttu-id="76c52-108">Zum Serialisieren der Zeichensätze von mindestens einer Sprache ohne zu escapen geben Sie [Unicode-Bereiche](xref:System.Text.Unicode.UnicodeRanges) an, wenn Sie eine Instanz von <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName> erstellen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="76c52-108">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="LanguageSets":::

<span data-ttu-id="76c52-109">Mit diesem Code werden weder kyrillische noch griechische Zeichen escapet.</span><span class="sxs-lookup"><span data-stu-id="76c52-109">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="76c52-110">Wenn die `Summary`-Eigenschaft auf Kyrillisch `жарко` festgelegt ist, wird das `WeatherForecast`-Objekt wie in diesem Beispiel gezeigt serialisiert:</span><span class="sxs-lookup"><span data-stu-id="76c52-110">If the `Summary` property is set to Cyrillic `жарко`, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="76c52-111">Um alle Sprachensätze ohne zu escapen zu serialisieren, verwenden Sie <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="76c52-111">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

## <a name="serialize-specific-characters"></a><span data-ttu-id="76c52-112">Serialisieren bestimmter Zeichen</span><span class="sxs-lookup"><span data-stu-id="76c52-112">Serialize specific characters</span></span>

<span data-ttu-id="76c52-113">Eine Alternative besteht darin, einzelne Zeichen anzugeben, die Sie zulassen möchten, ohne dass sie escapet werden.</span><span class="sxs-lookup"><span data-stu-id="76c52-113">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="76c52-114">Im folgenden Beispiel werden nur die ersten zwei Zeichen von `жарко` serialisiert:</span><span class="sxs-lookup"><span data-stu-id="76c52-114">The following example serializes only the first two characters of `жарко`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="SelectedCharacters":::

<span data-ttu-id="76c52-115">Hier sehen Sie eine JSON-Beispiel, das vom vorangehenden Code erzeugt wird:</span><span class="sxs-lookup"><span data-stu-id="76c52-115">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

## <a name="serialize-all-characters"></a><span data-ttu-id="76c52-116">Serialisieren aller Zeichen</span><span class="sxs-lookup"><span data-stu-id="76c52-116">Serialize all characters</span></span>

<span data-ttu-id="76c52-117">Um das Escapen zu minimieren, können Sie <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType> verwenden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="76c52-117">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="UnsafeRelaxed":::

> [!CAUTION]
> <span data-ttu-id="76c52-118">Im Vergleich zum Standardencoder ist der `UnsafeRelaxedJsonEscaping`-Encoder weniger streng beim Zulassen von Zeichen, ohne sie zu escapen:</span><span class="sxs-lookup"><span data-stu-id="76c52-118">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="76c52-119">Er escapet keine HTML-abhängigen Zeichen wie `<`, `>`, `&` und `'`.</span><span class="sxs-lookup"><span data-stu-id="76c52-119">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="76c52-120">Er bietet keine zusätzlichen, tief greifenden Abwehrmaßnahmen gegen solche Cross-Site Scripting (XSS)- oder Information-Disclosure-Angriffe (Veröffentlichung von Informationen), die von einem Client und Server, die sich nicht auf einen *Zeichensatz* einigen können, verursacht werden können.</span><span class="sxs-lookup"><span data-stu-id="76c52-120">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="76c52-121">Verwenden Sie den unsicheren Encoder nur dann, wenn bekannt ist, dass der Client die resultierende Nutzlast als UTF-8-codiertes JSON interpretieren wird.</span><span class="sxs-lookup"><span data-stu-id="76c52-121">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="76c52-122">Beispielsweise können Sie ihn verwenden, wenn der Server den Antwortheader `Content-Type: application/json; charset=utf-8` sendet.</span><span class="sxs-lookup"><span data-stu-id="76c52-122">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="76c52-123">Gestatten Sie niemals, dass die `UnsafeRelaxedJsonEscaping`-Rohausgabe in eine HTML-Seite oder ein `<script>`-Element ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="76c52-123">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="76c52-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76c52-124">See also</span></span>

* [<span data-ttu-id="76c52-125">System.Text.Json – Übersicht</span><span class="sxs-lookup"><span data-stu-id="76c52-125">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="76c52-126">Vorgehensweise: Serialisieren und Deserialisieren von JSON-Daten</span><span class="sxs-lookup"><span data-stu-id="76c52-126">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="76c52-127">Instanziieren von JsonSerializerOptions-Instanzen</span><span class="sxs-lookup"><span data-stu-id="76c52-127">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="76c52-128">Aktivieren des Abgleichs ohne Berücksichtigung von Groß- und Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="76c52-128">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="76c52-129">Anpassen von Eigenschaftsnamen und -werten</span><span class="sxs-lookup"><span data-stu-id="76c52-129">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="76c52-130">Ignorieren von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="76c52-130">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="76c52-131">Zulassen von ungültigem JSON-Code</span><span class="sxs-lookup"><span data-stu-id="76c52-131">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="76c52-132">Verarbeiten von Überlauf-JSON</span><span class="sxs-lookup"><span data-stu-id="76c52-132">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="76c52-133">Beibehalten von Verweisen</span><span class="sxs-lookup"><span data-stu-id="76c52-133">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="76c52-134">Unveränderliche Typen und nicht öffentliche Zugriffsmethoden</span><span class="sxs-lookup"><span data-stu-id="76c52-134">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="76c52-135">Polymorphe Serialisierung</span><span class="sxs-lookup"><span data-stu-id="76c52-135">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="76c52-136">Migrieren von Newtonsoft.Json zu System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="76c52-136">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="76c52-137">Schreiben benutzerdefinierter Serialisierungsmodule und Deserialisierer</span><span class="sxs-lookup"><span data-stu-id="76c52-137">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="76c52-138">Schreiben von benutzerdefinierten Konvertern für die JSON-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="76c52-138">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="76c52-139">Unterstützung von DateTime und DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="76c52-139">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="76c52-140">[System.Text.Json-API-Referenz](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="76c52-140">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="76c52-141">[System.Text.Json-Serialisierungs-API-Referenz](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="76c52-141">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
