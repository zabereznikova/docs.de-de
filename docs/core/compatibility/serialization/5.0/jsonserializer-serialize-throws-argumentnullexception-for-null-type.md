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
# <a name="jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null"></a>JsonSerializer.Serialize gibt eine ArgumentNullException-Ausnahme zurück, wenn für den Typparameter NULL gilt

<xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType>- und <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>-Überladungen, die einen Parameter vom Typ <xref:System.Type> aufweisen, geben ab sofort eine <xref:System.ArgumentNullException>-Ausnahme zurück, sobald `null` für diesen Parameter übergeben wird.

## <a name="change-description"></a>Änderungsbeschreibung

In .NET Core 3.1 geben die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-, <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType>- und <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>-Überladungen, die über einen <xref:System.Type>-Parameter verfügen, eine <xref:System.ArgumentNullException>-Ausnahme zurück, wenn `null` für den `Type inputType`-Parameter übergeben wird, jedoch nicht, wenn für den `Object value`-Parameter auch `null` gilt. Ab .NET 5.0 geben diese Methoden *immer* eine <xref:System.ArgumentNullException>-Ausnahme zurück, wenn `null` für den <xref:System.Type>-Parameter übergeben wird.

Verhalten in .NET Core 3.1:

```csharp
// Returns a string with value "null".
JsonSerializer.Serialize(null, null);

// Returns a byte array with value "null".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

Verhalten in .NET 5.0 und höher:

```csharp
// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.Serialize(null, null);

// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="reason-for-change"></a>Grund für die Änderung

Das Übergeben von `null` für den `Type inputType`-Parameter wird nicht akzeptiert und sollte immer eine <xref:System.ArgumentNullException>-Ausnahme auslösen.

## <a name="recommended-action"></a>Empfohlene Maßnahme

Achten Sie darauf, `null` nicht für den `Type inputType`-Parameter dieser Methoden zu übergeben.

## <a name="affected-apis"></a>Betroffene APIs

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
