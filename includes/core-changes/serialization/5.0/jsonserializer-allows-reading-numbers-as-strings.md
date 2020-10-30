---
ms.openlocfilehash: a93856aac97af5c392a2e4698d2da42413cfc3c8
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434994"
---
### <a name="aspnet-core-apps-allow-deserializing-quoted-numbers"></a>ASP.NET Core-Apps erlauben die Deserialisierung von Zahlen in Anführungszeichen

Ab .NET 5.0 verwenden ASP.NET Core-Apps, wie von <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType> angegeben, die Standardoptionen für die Deserialisierung. Die <xref:System.Text.Json.JsonSerializerDefaults.Web>-Optionen umfassen das Festlegen von <xref:System.Text.Json.JsonSerializerOptions.NumberHandling> auf <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString?displayProperty=nameWithType>. Diese Änderung bedeutet, dass ASP.NET Core-Apps alle Zahlen, die als JSON-Zeichenfolgen dargestellt sind, erfolgreich deserialisieren können, anstatt eine Ausnahme auszulösen.

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Core 3.0 bis 3.1 löst <xref:System.Text.Json.JsonSerializer> während der Deserialisierung eine Ausnahme des Typs <xref:System.Text.Json.JsonException> aus, wenn JSON-Nutzdaten eine Zahl in Anführungszeichen enthalten. Mithilfe der in Anführungszeichen gesetzten Zahlen werden Zuordnungen zu Zahleneigenschaften in Objektgraphen vorgenommen. In .NET Core 3.0 bis 3.1 werden Zahlen nur aus <xref:System.Text.Json.JsonTokenType.Number?displayProperty=nameWithType>-Token gelesen.

Ab .NET 5.0 gelten in Anführungszeichen gesetzte Zahlen in JSON-Nutzdaten für ASP.NET Core-Apps standardmäßig als gültig. Während der Deserialisierung von in Anführungszeichen gesetzten Zahlen wird keine Ausnahme ausgelöst.

> [!TIP]
>
> - Es gibt keinen Behavior Change für die eigenständigen Standardklassen <xref:System.Text.Json.JsonSerializer> oder <xref:System.Text.Json.JsonSerializerOptions>.
> - Dies ist fachlich gesehen kein Breaking Change, da diese Änderung zu liberaleren statt restriktiveren Szenarios führt (d. h., eine JSON-Zeichenfolge wird erfolgreich in eine Zahl konvertiert, anstatt eine Ausnahme auszulösen). Da es sich hierbei jedoch um einen bedeutenden Behavior Change handelt, der sich auf viele ASP.NET Core-Apps auswirkt, wird er hier dokumentiert.
> - Die Erweiterungsmethoden <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> und <xref:System.Net.Http.Json.HttpContentJsonExtensions.ReadFromJsonAsync%2A?displayProperty=nameWithType> verwenden ebenfalls die <xref:System.Text.Json.JsonSerializerDefaults.Web>-Serialisierungsoptionen.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0

#### <a name="reason-for-change"></a>Grund für die Änderung

Viele Benutzer haben um eine Möglichkeit für einen liberaleren Umgang mit Zahlen in <xref:System.Text.Json.JsonSerializer> gebeten. Dieses Feedback zeigt, dass viele Entitäten, die JSON erzeugen (z. B. Dienste im Web), Zahlen in Anführungszeichen ausgeben. Wenn Sie das Lesen von in Anführungszeichen gesetzten Zahlen zulassen (Deserialisierung), können .NET-Apps diese Nutzdaten standardmäßig erfolgreich in Webkontexten analysieren. Die Konfiguration wird über <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType> verfügbar gemacht, sodass Sie dieselben Optionen für verschiedene Anwendungsebenen angeben können, z. B. Client, Server und freigegeben.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Ist diese Änderung disruptiv, weil Sie z. B. bei Überprüfungen von einer strikten Zahlenverarbeitung abhängig sind, können Sie das vorherige Verhalten wiederherstellen. Legen Sie einfach die Option <xref:System.Text.Json.JsonSerializerOptions.NumberHandling?displayProperty=nameWithType> auf <xref:System.Text.Json.Serialization.JsonNumberHandling.Strict?displayProperty=nameWithType> fest.

Für MVC- und Web-API-Apps in ASP.NET Core können Sie mithilfe des folgenden Codes die Option in `Startup` konfigurieren:

```csharp
services.AddControllers()
   .AddJsonOptions(options.NumberHandling = JsonNumberHandling.Strict);
```

#### <a name="category"></a>Kategorie

- ASP.NET Core
- Serialisierung

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
