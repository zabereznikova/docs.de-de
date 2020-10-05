---
ms.openlocfilehash: 46f6f77a543dfcf2073063d8ec200ef7d71e6b1f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077591"
---
### <a name="blazor-jsobjectreference-and-jsinprocessobjectreference-types-changed-to-internal"></a>Blazor: Die Typen JSObjectReference und JSInProcessObjectReference wurden in „internal“ geändert

Die neuen Typen `Microsoft.JSInterop.JSObjectReference` und `Microsoft.JSInterop.JSInProcessObjectReference`, die in ASP.NET Core 5.0 RC1 eingeführt wurden, wurden als `internal` gekennzeichnet.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 RC2

#### <a name="old-behavior"></a>Altes Verhalten

`JSObjectReference` kann über `IJSRuntime` über einen JavaScript-Interop-Befehl abgerufen werden. Beispiel:

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<JSObjectReference>(...);
```

#### <a name="new-behavior"></a>Neues Verhalten

`JSObjectReference` verwendet den Zugriffsmodifizierer [internal](../../../../docs/csharp/language-reference/keywords/internal.md). Stattdessen muss die `public` `IJSObjectReference`-Schnittstelle verwendet werden. Beispiel:

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<IJSObjectReference>(...);
```

`JSInProcessObjectReference` wurde ebenfalls als `internal` gekennzeichnet und durch `IJSInProcessObjectReference` ersetzt.

#### <a name="reason-for-change"></a>Grund für die Änderung

Durch die Änderung wird das JavaScript-Interop-Feature mit anderen Mustern in Blazor vereinheitlicht. `IJSObjectReference` ist analog zu `IJSRuntime`, da beide Objekte einen ähnlichen Zweck erfüllen und ähnliche Methoden und Erweiterung umfassen.

#### <a name="recommended-action"></a>Empfohlene Aktion

Ersetzen Sie `JSObjectReference` durch `IJSObjectReference` und `JSInProcessObjectReference` durch `IJSInProcessObjectReference`.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

- `Microsoft.JSInterop.JSObjectReference`
- `Microsoft.JSInterop.JSInProcessObjectReference`

<!--

#### Affected APIs

- `T:Microsoft.JSInterop.JSObjectReference`
- `T:Microsoft.JSInterop.JSInProcessObjectReference`

-->
