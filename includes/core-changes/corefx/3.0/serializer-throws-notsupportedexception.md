---
ms.openlocfilehash: e6e10b2ec451c07bf397cbdcac51ef57c29dab47
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568240"
---
### <a name="json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception"></a>JSON-Serialisierungsausnahmetyp von `JsonException` in `NotSupportedException` geändert

In .NET Core 3.0 Vorschau 6 bis 8 hat das Serialisierungsmodul eine <xref:System.Text.Json.JsonException> ausgelöst, wenn ein nicht unterstützter abgeleiteter Sammlungstyp vorhanden war. Ab .NET Core 3.0 Vorschau 9 löst das Serialisierungsmodul stattdessen eine <xref:System.NotSupportedException> aus.

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Core 3.0 Vorschau 6 bis Vorschau 8 hat das Serialisierungsmodul eine <xref:System.Text.Json.JsonException> ausgelöst, wenn ein nicht unterstützter abgeleiteter Sammlungstyp vorhanden war. Ein *nicht unterstützter abgeleiteter Sammlungstyp* ist ein beliebiger Sammlungstyp, der keinem der folgenden Typen zugewiesen werden kann:

- <xref:System.Collections.IList>
- <xref:System.Collections.Generic.ICollection%601>
- <xref:System.Collections.Generic.Stack%601>
- <xref:System.Collections.Generic.Queue%601>
- <xref:System.Collections.IDictionary>
- [IDictionary\<String,T>](xref:System.Collections.Generic.IDictionary%602)

Ab .NET Core 3.0 Vorschau 9 löst das Serialisierungsmodul eine <xref:System.NotSupportedException> aus, wenn ein nicht unterstützter Auflistungstyp vorhanden ist. Der neue Ausnahmetyp spiegelt besser wider, warum der Deserialisierungsvorgang fehlschlägt.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0 Vorschau 9

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Wenn Sie <xref:System.Text.Json.JsonException> bei der Deserialisierung abfangen, sollten Sie auch <xref:System.NotSupportedException> abfangen.

#### <a name="category"></a>Kategorie

CoreFx

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
