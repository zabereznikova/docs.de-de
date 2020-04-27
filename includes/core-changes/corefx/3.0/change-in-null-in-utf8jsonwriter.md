---
ms.openlocfilehash: c9547cdc2f127cf13a3610118a26736930fcd8bd
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021586"
---
### <a name="change-in-semantics-of-stringnull-in-utf8jsonwriter"></a><span data-ttu-id="e9667-101">Änderung der Semantik von `(string)null` in Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="e9667-101">Change in semantics of `(string)null` in Utf8JsonWriter</span></span>

<span data-ttu-id="e9667-102">In .NET Core 3.0 Vorschau 7 wird die NULL-Zeichenfolge wie eine leere Zeichenfolge in <xref:System.Text.Json.Utf8JsonWriter> behandelt.</span><span class="sxs-lookup"><span data-stu-id="e9667-102">In .NET Core 3.0 Preview 7, the null string is treated as the empty string in <xref:System.Text.Json.Utf8JsonWriter>.</span></span> <span data-ttu-id="e9667-103">Ab .NET Core 3.0 Vorschau 8 löst die NULL-Zeichenfolge eine Ausnahme aus, wenn sie als Eigenschaftsname verwendet wird, und gibt das JSON-NULL-Token aus, wenn sie als Wert verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e9667-103">Starting with .NET Core 3.0 Preview 8, the null string throws an exception when used as a property name, and it emits the JSON null token when used as a value.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e9667-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="e9667-104">Change description</span></span>

<span data-ttu-id="e9667-105">In .NET Core 3.0 Vorschau 7 wurde die `null`-Zeichenfolge sowohl beim Schreiben von Eigenschaftsnamen als auch beim Schreiben von Werten als `""` behandelt.</span><span class="sxs-lookup"><span data-stu-id="e9667-105">In .NET Core 3.0 Preview 7, the `null` string was treated as `""` both when writing property names and when writing values.</span></span>  

<span data-ttu-id="e9667-106">Ab .NET Core 3.0 Vorschau 8 löst ein `null`-Eigenschaftsname eine `ArgumentNullException` aus, und ein `null`-Wert wird wie ein Aufruf von <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A?displayProperty=nameWithType> oder <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue?displayProperty=nameWithType> behandelt.</span><span class="sxs-lookup"><span data-stu-id="e9667-106">Starting with .NET Core 3.0 Preview 8, a `null` property name throws an `ArgumentNullException`, and a `null` value is treated as a call to <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A?displayProperty=nameWithType> or <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="e9667-107">Betrachten Sie folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="e9667-107">Consider the following code:</span></span>

```csharp
string propertyName1 = null;
string propertyValue1 = null;
string propertyName2 = "prop2";
string propertyValue2 = null;
string simpleValue1 = null;

using (Utf8JsonWriter writer = new Utf8JsonWriter(stream))
{
    writer.WriteStartArray();

    writer.WriteStartObject();
    writer.WriteString(propertyName1, propertyValue1);
    writer.WriteString(propertyName2, propertyValue2);
    writer.WriteEndObject();

    writer.WriteStringValue(simpleValue1);

    writer.WriteEndArray();
}
```

<span data-ttu-id="e9667-108">Bei Ausführung mit .NET Core 3.0 Vorschau 7 generiert der Writer die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="e9667-108">If run with .NET Core 3.0 Preview 7, the writer produces the following output:</span></span>

```js
[{"":"","prop2":""},""]
```

<span data-ttu-id="e9667-109">Ab . NET Core 3.0 Vorschau 8 löst der Aufruf von `writer.WriteString(propertyName1, propertyValue1)` eine <xref:System.ArgumentNullException> aus.</span><span class="sxs-lookup"><span data-stu-id="e9667-109">Starting with .NET Core 3.0 Preview 8, the call to `writer.WriteString(propertyName1, propertyValue1)` throws an <xref:System.ArgumentNullException>.</span></span>  <span data-ttu-id="e9667-110">Wenn `propertyName1 = null` durch `propertyName1 = string.Empty` ersetzt wird, lautet die Ausgabe nun wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e9667-110">If `propertyName1 = null` is replaced with `propertyName1 = string.Empty`, the output would now be:</span></span>

```js
[{"":null,"prop2":null},null]
```

<span data-ttu-id="e9667-111">Diese Änderung wurde vorgenommen, um die Aufrufererwartungen für `null`-Werte besser zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="e9667-111">This change was made to better align with caller expectations for `null` values.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e9667-112">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e9667-112">Version introduced</span></span>

<span data-ttu-id="e9667-113">3.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="e9667-113">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e9667-114">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="e9667-114">Recommended action</span></span>

<span data-ttu-id="e9667-115">Beim Schreiben von Eigenschaftsnamen und -Werten mit der <xref:System.Text.Json.Utf8JsonWriter>-Klasse:</span><span class="sxs-lookup"><span data-stu-id="e9667-115">When writing property names and values with the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

- <span data-ttu-id="e9667-116">Stellen Sie sicher, dass Zeichenfolgen ungleich `null` als Eigenschaftsnamen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e9667-116">Ensure non-`null` strings are used as property names.</span></span>

- <span data-ttu-id="e9667-117">Wenn das vorherige Verhalten gewünscht wird, verwenden Sie einen NULL-Zusammenführungsaufruf, beispielsweise `writer.WriteString(propertyName1 ?? "", propertyValue1)`.</span><span class="sxs-lookup"><span data-stu-id="e9667-117">If the previous behavior is desired, use a null coalescing invocation; for example, `writer.WriteString(propertyName1 ?? "", propertyValue1)`.</span></span>

- <span data-ttu-id="e9667-118">Wenn das Schreiben eines `null`-Literals für einen `null`-Zeichenfolgenwert nicht wünschenswert ist, verwenden Sie einen NULL-Zusammenführungsaufruf, beispielsweise `writer.WriteString(propertyName2, propertyValue2 ?? "")`.</span><span class="sxs-lookup"><span data-stu-id="e9667-118">If writing a `null` literal for a `null` string value is not desirable, use a null coalescing invocation; for example, `writer.WriteString(propertyName2, propertyValue2 ?? "")`.</span></span>

#### <a name="category"></a><span data-ttu-id="e9667-119">Kategorie</span><span class="sxs-lookup"><span data-stu-id="e9667-119">Category</span></span>

<span data-ttu-id="e9667-120">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="e9667-120">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e9667-121">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="e9667-121">Affected APIs</span></span>

- <xref:System.Text.Json.Utf8JsonWriter.WriteBase64String(System.String,System.ReadOnlySpan%7BSystem.Byte%7D)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteBoolean(System.String,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNull(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int32)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int64)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt32)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt64)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Single)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Double)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Decimal)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteStartArray(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteStartObject(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan%7BSystem.Byte%7D)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan%7BSystem.Char%7D)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Text.Json.JsonEncodedText)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTime)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTimeOffset)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Guid)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName(System.String)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Text.Json.Utf8JsonWriter.WriteBase64String(System.String,System.ReadOnlySpan{System.Byte})`
- `M:System.Text.Json.Utf8JsonWriter.WriteBoolean(System.String,System.Boolean)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNull(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int32)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int64)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt32)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt64)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Single)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Double)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Decimal)`
- `M:System.Text.Json.Utf8JsonWriter.WriteStartArray(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteStartObject(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan{System.Byte})`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan{System.Char})`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Text.Json.JsonEncodedText)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTime)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTimeOffset)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Guid)`
- `M:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WritePropertyName(System.String)`

-->
