---
ms.openlocfilehash: 07980cf94d5de0173808da2ce44adb409fdd5419
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050464"
---
### <a name="propertynamingpolicy-propertynamecaseinsensitive-and-encoder-options-are-honored-when-serializing-and-deserializing-key-value-pairs"></a>Die Optionen „PropertyNamingPolicy“, „PropertyNamingPolicy“ und „Encoder“ werden beim Serialisieren und Deserialisieren von Schlüssel-Wert-Paaren berücksichtigt

<xref:System.Text.Json.JsonSerializer> berücksichtigt nun die Optionen <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> und <xref:System.Text.Json.JsonSerializerOptions.Encoder> beim Serialisieren der Eigenschaftsnamen <xref:System.Collections.Generic.KeyValuePair%602.Key> und <xref:System.Collections.Generic.KeyValuePair%602.Value> einer <xref:System.Collections.Generic.KeyValuePair%602>-Instanz. Außerdem berücksichtigt <xref:System.Text.Json.JsonSerializer> die Optionen <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> und <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> beim Deserialisieren von <xref:System.Collections.Generic.KeyValuePair%602>-Instanzen.

#### <a name="change-description"></a>Änderungsbeschreibung

##### <a name="serialization"></a>Serialisierung

In .NET Core 3.x-Versionen und in den Versionen 4.6.0–4.7.2 des [NuGet-Pakets „System.Text.Json“](https://www.nuget.org/packages/System.Text.Json) werden die Eigenschaften der <xref:System.Collections.Generic.KeyValuePair%602>-Instanzen immer als „Key“ und „Value“ serialisiert – unabhängig von jeglichen <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>- und <xref:System.Text.Json.JsonSerializerOptions.Encoder?displayProperty=nameWithType>-Optionen. Im folgenden Codebeispiel wird gezeigt, wie die Eigenschaften <xref:System.Collections.Generic.KeyValuePair%602.Key> und <xref:System.Collections.Generic.KeyValuePair%602.Value> nach der Serialisierung *nicht* mit gemischter Groß-/Kleinschreibung geschrieben werden, obwohl dies von der Richtlinie für die Benennung von Eigenschaften vorgeschrieben wird.

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
KeyValuePair<int, int> kvp = KeyValuePair.Create(1, 1);
Console.WriteLine(JsonSerializer.Serialize(kvp, options));
// Expected: {"key":1,"value":1}
// Actual: {"Key":1,"Value":1}
```

Ab .NET 5.0 werden die Optionen <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> und <xref:System.Text.Json.JsonSerializerOptions.Encoder> beim Serialisieren von <xref:System.Collections.Generic.KeyValuePair%602>-Instanzen berücksichtigt. Im folgenden Codebeispiel wird gezeigt, wie die Eigenschaften <xref:System.Collections.Generic.KeyValuePair%602.Key> und <xref:System.Collections.Generic.KeyValuePair%602.Value> gemäß der Richtlinie für die Benennung von Eigenschaften nach der Serialisierung mit gemischter Groß-/Kleinschreibung geschrieben werden.

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
KeyValuePair<int, int> kvp = KeyValuePair.Create(1, 1);
Console.WriteLine(JsonSerializer.Serialize(kvp, options));
// {"key":1,"value":1}
```

##### <a name="deserialization"></a>Deserialisierung

In .NET Core 3.x-Versionen und in 4.7.x-Versionen des [NuGet-Pakets „System.Text.Json“](https://www.nuget.org/packages/System.Text.Json)wird eine <xref:System.Text.Json.JsonException> ausgelöst, wenn die JSON-Eigenschaftsnamen nicht exakt `Key` und `Value` entsprechen, also z. B. nicht mit einem Großbuchstaben beginnen. Die Ausnahme wird auch dann ausgelöst, wenn eine bestimmte Richtlinie zur Benennung von Eigenschaften dies ausdrücklich gestattet.

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""key"":1,""value"":1}";
// Throws JsonException.
JsonSerializer.Deserialize<KeyValuePair<int, int>>(json, options);
```

Ab .NET 5.0 werden die Optionen <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> und <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> bei der Deserialisierung mithilfe von <xref:System.Text.Json.JsonSerializer> berücksichtigt. Der folgende Codeausschnitt zeigt z. B. die erfolgreiche Deserialisierung der Eigenschaftsnamen <xref:System.Collections.Generic.KeyValuePair%602.Key> und <xref:System.Collections.Generic.KeyValuePair%602.Value> in Kleinbuchstaben, weil die entsprechende Richtlinie für die Benennung von Eigenschaften dies gestattet.

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""key"":1,""value"":1}";

KeyValuePair<int, int> kvp = JsonSerializer.Deserialize<KeyValuePair<int, int>>(json);
Console.WriteLine(kvp.Key); // 1
Console.WriteLine(kvp.Value); // 1
```

Zur Unterstützung von Nutzdaten, die mit früheren Versionen deserialisiert wurden, gilt für die Eigenschaftsnamen „Key“ und „Value“ ein Sonderfall in Bezug auf die Groß-/Kleinschreibung, um diese bei der Deserialisierung abzugleichen. Obwohl die Eigenschaftsnamen <xref:System.Collections.Generic.KeyValuePair%602.Key> und <xref:System.Collections.Generic.KeyValuePair%602.Value> im folgenden Codebeispiel nicht entsprechend der Option <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> mit gemischter Groß-/Kleinschreibung geschrieben werden, werden sie erfolgreich deserialisiert.

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""Key"":1,""Value"":1}";

KeyValuePair<int, int> kvp = JsonSerializer.Deserialize<KeyValuePair<int, int>>(json);
Console.WriteLine(kvp.Key); // 1
Console.WriteLine(kvp.Value); // 1
```

#### <a name="version-introduced"></a>Eingeführt in Version

5.0

#### <a name="reason-for-change"></a>Grund für die Änderung

Umfassendes Kundenfeedback hat ergeben, dass die Eigenschaft <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> berücksichtigt werden sollte. Aus Gründen der Vollständigkeit werden die Optionen <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> und <xref:System.Text.Json.JsonSerializerOptions.Encoder> ebenfalls berücksichtigt, sodass <xref:System.Collections.Generic.KeyValuePair%602>-Instanzen genauso wie alle anderen Plain Old CLR Objects (POCO) behandelt werden.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Wenn Sie diese Änderung stört, können Sie einen [benutzerdefinierten Konverter](../../../../docs/standard/serialization/system-text-json-converters-how-to.md) verwenden, der die gewünschte Semantik implementiert.

#### <a name="category"></a>Kategorie

Serialisierung

#### <a name="affected-apis"></a>Betroffene APIs

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
