---
ms.openlocfilehash: 3692848a0cbd4bbbe3c7bb4d2c22a2b19de732e4
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050466"
---
### <a name="non-public-parameterless-constructors-not-used-for-deserialization"></a>Nicht öffentliche parameterlose Konstruktoren, die nicht für die Deserialisierung verwendet werden

Aus Gründen der Konsistenz in allen unterstützten Zielframeworkmonikern (TFMs) werden nicht öffentliche, parameterlose Konstruktoren nicht mehr standardmäßig für die Deserialisierung mit <xref:System.Text.Json.JsonSerializer> verwendet.

#### <a name="change-description"></a>Änderungsbeschreibung

Die eigenständigen [System.Text.Json-NuGet-Pakete](https://www.nuget.org/packages/System.Text.Json/), die .NET Standard 2.0 und die höheren Versionen 4.6.0 bis 4.7.2 unterstützen, verhalten sich im Vergleich zum integrierten Verhalten in .NET Core 3.0 und 3.1 inkonsistent. In .NET Core 3.x können interne und private Konstruktoren für die Deserialisierung verwendet werden. In den eigenständigen Paketen sind nicht öffentliche Konstruktoren nicht zulässig, und eine <xref:System.MissingMethodException> wird ausgelöst, wenn kein öffentlicher, parameterloser Konstruktor definiert ist.

Ab .NET 5.0 und dem System.Text.Json-NuGet-Paket 5.0.0 ist das Verhalten des NuGet-Pakets und der integrierten APIs konsistent. Nicht öffentliche Konstruktoren einschließlich parameterloser Konstruktoren werden vom Serialisierungsprogramm standardmäßig ignoriert. Das Serialisierungsprogramm verwendet einen der folgenden Konstruktoren für die Deserialisierung:

- öffentlicher Konstruktor mit der Anmerkung <xref:System.Text.Json.Serialization.JsonConstructorAttribute>
- öffentlicher, parameterloser Konstruktor
- öffentlicher, parametrisierter Konstruktor (falls dies der einzige öffentliche Konstruktor ist)

Wenn keiner dieser Konstruktoren verfügbar ist, wird eine <xref:System.NotSupportedException> ausgelöst, wenn Sie versuchen, den Typ zu deserialisieren.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0

#### <a name="reason-for-change"></a>Grund für die Änderung

- Es soll ein konsistentes Verhalten aller Zielframeworkmoniker (TFMs) erzwungen werden, die <xref:System.Text.Json?displayProperty=fullName> für .NET Core 3.0 und höhere Versionen sowie .NET Standard 2.0 erstellt.
- <xref:System.Text.Json.JsonSerializer> soll den nicht öffentlichen Oberflächenbereich eines Typs nicht aufrufen, egal, ob es sich um einen Konstruktor, eine Eigenschaft oder ein Feld handelt.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

- Wenn Sie über den Typ verfügen, veröffentlichen Sie nach Möglichkeit den parameterlosen Konstruktor.
- Implementieren Sie andernfalls einen `JsonConverter<T>` für den Typ, und steuern Sie das Deserialisierungsverhalten.

#### <a name="category"></a>Kategorie

Serialisierung

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
