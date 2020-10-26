---
ms.openlocfilehash: 07980cf94d5de0173808da2ce44adb409fdd5419
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050464"
---
### <a name="propertynamingpolicy-propertynamecaseinsensitive-and-encoder-options-are-honored-when-serializing-and-deserializing-key-value-pairs"></a><span data-ttu-id="afce4-101">Die Optionen „PropertyNamingPolicy“, „PropertyNamingPolicy“ und „Encoder“ werden beim Serialisieren und Deserialisieren von Schlüssel-Wert-Paaren berücksichtigt</span><span class="sxs-lookup"><span data-stu-id="afce4-101">PropertyNamingPolicy, PropertyNameCaseInsensitive, and Encoder options are honored when serializing and deserializing key-value pairs</span></span>

<span data-ttu-id="afce4-102"><xref:System.Text.Json.JsonSerializer> berücksichtigt nun die Optionen <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> und <xref:System.Text.Json.JsonSerializerOptions.Encoder> beim Serialisieren der Eigenschaftsnamen <xref:System.Collections.Generic.KeyValuePair%602.Key> und <xref:System.Collections.Generic.KeyValuePair%602.Value> einer <xref:System.Collections.Generic.KeyValuePair%602>-Instanz.</span><span class="sxs-lookup"><span data-stu-id="afce4-102"><xref:System.Text.Json.JsonSerializer> now honors the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> and <xref:System.Text.Json.JsonSerializerOptions.Encoder> options when serializing the <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> property names of a <xref:System.Collections.Generic.KeyValuePair%602> instance.</span></span> <span data-ttu-id="afce4-103">Außerdem berücksichtigt <xref:System.Text.Json.JsonSerializer> die Optionen <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> und <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> beim Deserialisieren von <xref:System.Collections.Generic.KeyValuePair%602>-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="afce4-103">Additionally, <xref:System.Text.Json.JsonSerializer> honors the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> and <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> options when deserializing <xref:System.Collections.Generic.KeyValuePair%602> instances.</span></span>

#### <a name="change-description"></a><span data-ttu-id="afce4-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="afce4-104">Change description</span></span>

##### <a name="serialization"></a><span data-ttu-id="afce4-105">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="afce4-105">Serialization</span></span>

<span data-ttu-id="afce4-106">In .NET Core 3.x-Versionen und in den Versionen 4.6.0–4.7.2 des [NuGet-Pakets „System.Text.Json“](https://www.nuget.org/packages/System.Text.Json) werden die Eigenschaften der <xref:System.Collections.Generic.KeyValuePair%602>-Instanzen immer als „Key“ und „Value“ serialisiert – unabhängig von jeglichen <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>- und <xref:System.Text.Json.JsonSerializerOptions.Encoder?displayProperty=nameWithType>-Optionen.</span><span class="sxs-lookup"><span data-stu-id="afce4-106">In .NET Core 3.x versions and in the 4.6.0-4.7.2 versions of the [System.Text.Json NuGet package](https://www.nuget.org/packages/System.Text.Json), the properties of <xref:System.Collections.Generic.KeyValuePair%602> instances are always serialized as "Key" and "Value" exactly, regardless of any <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> and <xref:System.Text.Json.JsonSerializerOptions.Encoder?displayProperty=nameWithType> options.</span></span> <span data-ttu-id="afce4-107">Im folgenden Codebeispiel wird gezeigt, wie die Eigenschaften <xref:System.Collections.Generic.KeyValuePair%602.Key> und <xref:System.Collections.Generic.KeyValuePair%602.Value> nach der Serialisierung *nicht* mit gemischter Groß-/Kleinschreibung geschrieben werden, obwohl dies von der Richtlinie für die Benennung von Eigenschaften vorgeschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="afce4-107">The following code example shows how the <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> properties are *not* camel-cased after serialization, even though the specified property-naming policy dictates so.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
KeyValuePair<int, int> kvp = KeyValuePair.Create(1, 1);
Console.WriteLine(JsonSerializer.Serialize(kvp, options));
// Expected: {"key":1,"value":1}
// Actual: {"Key":1,"Value":1}
```

<span data-ttu-id="afce4-108">Ab .NET 5.0 werden die Optionen <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> und <xref:System.Text.Json.JsonSerializerOptions.Encoder> beim Serialisieren von <xref:System.Collections.Generic.KeyValuePair%602>-Instanzen berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="afce4-108">Starting in .NET 5.0, the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> and <xref:System.Text.Json.JsonSerializerOptions.Encoder> options are honored when serializing <xref:System.Collections.Generic.KeyValuePair%602> instances.</span></span> <span data-ttu-id="afce4-109">Im folgenden Codebeispiel wird gezeigt, wie die Eigenschaften <xref:System.Collections.Generic.KeyValuePair%602.Key> und <xref:System.Collections.Generic.KeyValuePair%602.Value> gemäß der Richtlinie für die Benennung von Eigenschaften nach der Serialisierung mit gemischter Groß-/Kleinschreibung geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="afce4-109">The following code example shows how the <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> properties are camel-cased after serialization, in accordance with the specified property-naming policy.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
KeyValuePair<int, int> kvp = KeyValuePair.Create(1, 1);
Console.WriteLine(JsonSerializer.Serialize(kvp, options));
// {"key":1,"value":1}
```

##### <a name="deserialization"></a><span data-ttu-id="afce4-110">Deserialisierung</span><span class="sxs-lookup"><span data-stu-id="afce4-110">Deserialization</span></span>

<span data-ttu-id="afce4-111">In .NET Core 3.x-Versionen und in 4.7.x-Versionen des [NuGet-Pakets „System.Text.Json“](https://www.nuget.org/packages/System.Text.Json)wird eine <xref:System.Text.Json.JsonException> ausgelöst, wenn die JSON-Eigenschaftsnamen nicht exakt `Key` und `Value` entsprechen, also z. B. nicht mit einem Großbuchstaben beginnen.</span><span class="sxs-lookup"><span data-stu-id="afce4-111">In .NET Core 3.x versions and in the 4.7.x versions of the [System.Text.Json NuGet package](https://www.nuget.org/packages/System.Text.Json), a <xref:System.Text.Json.JsonException> is thrown when the JSON property names are not precisely `Key` and `Value`, for example, if they don't start with an uppercase letter.</span></span> <span data-ttu-id="afce4-112">Die Ausnahme wird auch dann ausgelöst, wenn eine bestimmte Richtlinie zur Benennung von Eigenschaften dies ausdrücklich gestattet.</span><span class="sxs-lookup"><span data-stu-id="afce4-112">The exception is thrown even if a specified property-naming policy expressly permits it.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""key"":1,""value"":1}";
// Throws JsonException.
JsonSerializer.Deserialize<KeyValuePair<int, int>>(json, options);
```

<span data-ttu-id="afce4-113">Ab .NET 5.0 werden die Optionen <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> und <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> bei der Deserialisierung mithilfe von <xref:System.Text.Json.JsonSerializer> berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="afce4-113">Starting in .NET 5.0, the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> and <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> options are honored when deserializing using <xref:System.Text.Json.JsonSerializer>.</span></span> <span data-ttu-id="afce4-114">Der folgende Codeausschnitt zeigt z. B. die erfolgreiche Deserialisierung der Eigenschaftsnamen <xref:System.Collections.Generic.KeyValuePair%602.Key> und <xref:System.Collections.Generic.KeyValuePair%602.Value> in Kleinbuchstaben, weil die entsprechende Richtlinie für die Benennung von Eigenschaften dies gestattet.</span><span class="sxs-lookup"><span data-stu-id="afce4-114">For example, the following code snippet shows successful deserialization of lowercased <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> property names because the specified property-naming policy permits it.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""key"":1,""value"":1}";

KeyValuePair<int, int> kvp = JsonSerializer.Deserialize<KeyValuePair<int, int>>(json);
Console.WriteLine(kvp.Key); // 1
Console.WriteLine(kvp.Value); // 1
```

<span data-ttu-id="afce4-115">Zur Unterstützung von Nutzdaten, die mit früheren Versionen deserialisiert wurden, gilt für die Eigenschaftsnamen „Key“ und „Value“ ein Sonderfall in Bezug auf die Groß-/Kleinschreibung, um diese bei der Deserialisierung abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="afce4-115">To accommodate payloads that were serialized with previous versions, "Key" and "Value" are special-cased to match when deserializing.</span></span> <span data-ttu-id="afce4-116">Obwohl die Eigenschaftsnamen <xref:System.Collections.Generic.KeyValuePair%602.Key> und <xref:System.Collections.Generic.KeyValuePair%602.Value> im folgenden Codebeispiel nicht entsprechend der Option <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> mit gemischter Groß-/Kleinschreibung geschrieben werden, werden sie erfolgreich deserialisiert.</span><span class="sxs-lookup"><span data-stu-id="afce4-116">Even though the <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> property names aren't camel-cased according to the in <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> option in the following code example, they deserialize successfully.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""Key"":1,""Value"":1}";

KeyValuePair<int, int> kvp = JsonSerializer.Deserialize<KeyValuePair<int, int>>(json);
Console.WriteLine(kvp.Key); // 1
Console.WriteLine(kvp.Value); // 1
```

#### <a name="version-introduced"></a><span data-ttu-id="afce4-117">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="afce4-117">Version introduced</span></span>

<span data-ttu-id="afce4-118">5.0</span><span class="sxs-lookup"><span data-stu-id="afce4-118">5.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="afce4-119">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="afce4-119">Reason for change</span></span>

<span data-ttu-id="afce4-120">Umfassendes Kundenfeedback hat ergeben, dass die Eigenschaft <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> berücksichtigt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="afce4-120">Substantial customer feedback indicated that the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> should be honored.</span></span> <span data-ttu-id="afce4-121">Aus Gründen der Vollständigkeit werden die Optionen <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> und <xref:System.Text.Json.JsonSerializerOptions.Encoder> ebenfalls berücksichtigt, sodass <xref:System.Collections.Generic.KeyValuePair%602>-Instanzen genauso wie alle anderen Plain Old CLR Objects (POCO) behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="afce4-121">For completeness, the <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> and <xref:System.Text.Json.JsonSerializerOptions.Encoder> options are also honored, so that <xref:System.Collections.Generic.KeyValuePair%602> instances are treated the same as any other plain old CLR object (POCO).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="afce4-122">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="afce4-122">Recommended action</span></span>

<span data-ttu-id="afce4-123">Wenn Sie diese Änderung stört, können Sie einen [benutzerdefinierten Konverter](../../../../docs/standard/serialization/system-text-json-converters-how-to.md) verwenden, der die gewünschte Semantik implementiert.</span><span class="sxs-lookup"><span data-stu-id="afce4-123">If this change is disruptive to you, you can use a [custom converter](../../../../docs/standard/serialization/system-text-json-converters-how-to.md) that implements the desired semantics.</span></span>

#### <a name="category"></a><span data-ttu-id="afce4-124">Kategorie</span><span class="sxs-lookup"><span data-stu-id="afce4-124">Category</span></span>

<span data-ttu-id="afce4-125">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="afce4-125">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="afce4-126">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="afce4-126">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Serialize`
- `Overload:System.Text.Json.JsonSerializer.SerializeAsync`
- `Overload:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes`
- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
