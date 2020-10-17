---
ms.openlocfilehash: 5b49dcae45e44bfd9ec3e150ad25c3f21d62c18e
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955335"
---
### <a name="jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null"></a><span data-ttu-id="e7c98-101">JsonSerializer.Serialize gibt eine ArgumentNullException-Ausnahme zurück, wenn für den Typparameter NULL gilt</span><span class="sxs-lookup"><span data-stu-id="e7c98-101">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>

<span data-ttu-id="e7c98-102"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType>- und <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>-Überladungen, die den <xref:System.Type>-Parameter aufweisen, geben ab sofort eine <xref:System.ArgumentNullException>-Ausnahme zurück, sobald `null` für den <xref:System.Type>-Parameter übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="e7c98-102"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType>, and <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> overloads that have a <xref:System.Type> parameter now throw an <xref:System.ArgumentNullException> whenever `null` is passed for the <xref:System.Type> parameter.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e7c98-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="e7c98-103">Change description</span></span>

<span data-ttu-id="e7c98-104">In .NET Core 3.1 geben die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-, <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType>- und <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>-Überladungen, die über einen <xref:System.Type>-Parameter verfügen, eine <xref:System.ArgumentNullException>-Ausnahme zurück, wenn `null` für den `Type inputType`-Parameter übergeben wird, jedoch nicht, wenn für den `Object value`-Parameter auch `null` gilt.</span><span class="sxs-lookup"><span data-stu-id="e7c98-104">In .NET Core 3.1, the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType>, and <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> overloads that have a <xref:System.Type> parameter throw an <xref:System.ArgumentNullException> when `null` is passed for the `Type inputType` parameter, but not if the `Object value` parameter is also `null`.</span></span> <span data-ttu-id="e7c98-105">Ab .NET 5.0 geben diese Methoden *immer* eine <xref:System.ArgumentNullException>-Ausnahme zurück, wenn `null` für den <xref:System.Type>-Parameter übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="e7c98-105">Starting in .NET 5.0, these methods *always* throw an <xref:System.ArgumentNullException> when `null` is passed for the <xref:System.Type> parameter.</span></span>

<span data-ttu-id="e7c98-106">Verhalten in .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="e7c98-106">Behavior in .NET Core 3.1:</span></span>

```csharp
// Returns a string with value "null".
JsonSerializer.Serialize(null, null);

// Returns a byte array with value "null".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

<span data-ttu-id="e7c98-107">Verhalten in .NET 5.0 und höher:</span><span class="sxs-lookup"><span data-stu-id="e7c98-107">Behavior in .NET 5.0 and later:</span></span>

```csharp
// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.Serialize(null, null);

// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

#### <a name="version-introduced"></a><span data-ttu-id="e7c98-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e7c98-108">Version introduced</span></span>

<span data-ttu-id="e7c98-109">5.0</span><span class="sxs-lookup"><span data-stu-id="e7c98-109">5.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e7c98-110">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="e7c98-110">Reason for change</span></span>

<span data-ttu-id="e7c98-111">Das Übergeben von `null` für den `Type inputType`-Parameter wird nicht akzeptiert und sollte immer eine <xref:System.ArgumentNullException>-Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="e7c98-111">Passing in `null` for the `Type inputType` parameter is unacceptable and should always throw an <xref:System.ArgumentNullException>.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e7c98-112">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="e7c98-112">Recommended action</span></span>

<span data-ttu-id="e7c98-113">Achten Sie darauf, `null` nicht für den `Type inputType`-Parameter dieser Methoden zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="e7c98-113">Make sure that you are not passing `null` for the `Type inputType` parameter of these methods.</span></span>

#### <a name="category"></a><span data-ttu-id="e7c98-114">Kategorie</span><span class="sxs-lookup"><span data-stu-id="e7c98-114">Category</span></span>

<span data-ttu-id="e7c98-115">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="e7c98-115">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e7c98-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="e7c98-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)`
- `M:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`

-->
