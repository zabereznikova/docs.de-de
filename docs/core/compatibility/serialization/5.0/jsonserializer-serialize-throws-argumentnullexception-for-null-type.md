---
title: 'Breaking Change: Serialize löst eine Ausnahme aus, wenn der Typparameter NULL ist.'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den die Serialisierungsmethoden für JsonSerialize, die einen Typparameter aufweisen, jetzt eine Ausnahme auslösen, wenn ein NULL-Wert für diesen Parameter übergeben wird.
ms.date: 10/18/2020
ms.openlocfilehash: af2885394418072ad7efec5855490b5b80152fe6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759523"
---
# <a name="jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null"></a><span data-ttu-id="35689-103">JsonSerializer.Serialize gibt eine ArgumentNullException-Ausnahme zurück, wenn für den Typparameter NULL gilt</span><span class="sxs-lookup"><span data-stu-id="35689-103">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>

<span data-ttu-id="35689-104"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType>- und <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>-Überladungen, die einen Parameter vom Typ <xref:System.Type> aufweisen, geben ab sofort eine <xref:System.ArgumentNullException>-Ausnahme zurück, sobald `null` für diesen Parameter übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="35689-104"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType>, and <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> overloads that have a parameter of type <xref:System.Type> now throw an <xref:System.ArgumentNullException> whenever `null` is passed for that parameter.</span></span>

## <a name="change-description"></a><span data-ttu-id="35689-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="35689-105">Change description</span></span>

<span data-ttu-id="35689-106">In .NET Core 3.1 geben die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-, <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType>- und <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>-Überladungen, die über einen <xref:System.Type>-Parameter verfügen, eine <xref:System.ArgumentNullException>-Ausnahme zurück, wenn `null` für den `Type inputType`-Parameter übergeben wird, jedoch nicht, wenn für den `Object value`-Parameter auch `null` gilt.</span><span class="sxs-lookup"><span data-stu-id="35689-106">In .NET Core 3.1, the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType>, and <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> overloads that have a <xref:System.Type> parameter throw an <xref:System.ArgumentNullException> when `null` is passed for the `Type inputType` parameter, but not if the `Object value` parameter is also `null`.</span></span> <span data-ttu-id="35689-107">Ab .NET 5.0 geben diese Methoden *immer* eine <xref:System.ArgumentNullException>-Ausnahme zurück, wenn `null` für den <xref:System.Type>-Parameter übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="35689-107">Starting in .NET 5.0, these methods *always* throw an <xref:System.ArgumentNullException> when `null` is passed for the <xref:System.Type> parameter.</span></span>

<span data-ttu-id="35689-108">Verhalten in .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="35689-108">Behavior in .NET Core 3.1:</span></span>

```csharp
// Returns a string with value "null".
JsonSerializer.Serialize(null, null);

// Returns a byte array with value "null".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

<span data-ttu-id="35689-109">Verhalten in .NET 5.0 und höher:</span><span class="sxs-lookup"><span data-stu-id="35689-109">Behavior in .NET 5.0 and later:</span></span>

```csharp
// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.Serialize(null, null);

// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

## <a name="version-introduced"></a><span data-ttu-id="35689-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="35689-110">Version introduced</span></span>

<span data-ttu-id="35689-111">5.0</span><span class="sxs-lookup"><span data-stu-id="35689-111">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="35689-112">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="35689-112">Reason for change</span></span>

<span data-ttu-id="35689-113">Das Übergeben von `null` für den `Type inputType`-Parameter wird nicht akzeptiert und sollte immer eine <xref:System.ArgumentNullException>-Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="35689-113">Passing in `null` for the `Type inputType` parameter is unacceptable and should always throw an <xref:System.ArgumentNullException>.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="35689-114">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="35689-114">Recommended action</span></span>

<span data-ttu-id="35689-115">Achten Sie darauf, `null` nicht für den `Type inputType`-Parameter dieser Methoden zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="35689-115">Make sure that you are not passing `null` for the `Type inputType` parameter of these methods.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="35689-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="35689-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)`
- `M:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`

### Category

Serialization

-->
