---
ms.openlocfilehash: 8209c5336983bde13a698fbc68e6a099091071f7
ms.sourcegitcommit: a6bd4cad438fe479cbd112eae10f2cd449f06e40
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2020
ms.locfileid: "91844504"
---
### <a name="jsonserializerdeserialize-requires-single-character-string"></a>JsonSerializer.Deserialize erfordert Zeichenfolgen mit einzelnem Zeichen

Wenn der Typparameter <xref:System.Char> ist, muss das Zeichenfolgenargument für <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> ein einzelnes Zeichen enthalten, damit die Deserialisierung erfolgreich ist.

#### <a name="change-description"></a>Änderungsbeschreibung

In bisherigen .NET-Versionen war die Deserialisierung erfolgreich, wenn Sie eine Zeichenfolge mit mehreren Zeichen an <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> übergeben und der Typparameter <xref:System.Char> ist, und nur das erste Zeichen wird deserialisiert.

In .NET 5.0 und höher wird eine <xref:System.Text.Json.JsonException>-Ausnahme ausgelöst, wenn der Parameter <xref:System.Char> ist und etwas anderes wie eine Zeichenfolge mit einzelnem Zeichen übergeben wird.

```csharp
// .NET Core 3.0 and 3.1: Returns the first character 'a'.
// .NET 5.0 and later: Throws JsonException because payload has more than one character.
JsonSerializer.Deserialize<char>("\"abc\"");

// Correct usage.
JsonSerializer.Deserialize<char>("\"a\"");
```

#### <a name="version-introduced"></a>Eingeführt in Version

5.0

#### <a name="reason-for-change"></a>Grund für die Änderung

<xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> analysiert den Text, der einen einzelnen JSON-Wert darstellt, in eine Instanz des Typs, der durch einen generischen Typparameter angegeben wird. Das Parsen sollte nur erfolgreich sein, wenn die bereitgestellten Nutzdaten für den angegebenen generischen Typparameter gültig sind. Für einen <xref:System.Char>-Werttyp bestehen gültige Nutzdaten aus einer Zeichenfolge mit einzelnem Zeichen.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Beim Parsen einer Zeichenfolge in einen <xref:System.Char>-Typ mithilfe von <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> sollten Sie dafür sorgen, dass die Zeichenfolge aus einem einzelnen Zeichen besteht.

#### <a name="category"></a>Kategorie

Serialisierung

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Text.Json.JsonSerializer.Deserialize``1(System.String,System.Text.Json.JsonSerializerOptions)`

-->
