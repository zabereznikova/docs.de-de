---
ms.openlocfilehash: f202b39f1a45f740625827be25e72df0e403d605
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901997"
---
### <a name="signalr-javascript-client-package-name-changed"></a>SignalR: Name des JavaScript-Clientpakets geändert

In ASP.NET Core 3.0 Preview 7 wurde der Name des SignalR-JavaScript-Clientpakets von `@aspnet/signalr` in `@microsoft/signalr` geändert. Die Namensänderung spiegelt die Tatsache wider, dass SignalR dank Azure SignalR Service für mehr als nur ASP.NET Core-Apps nützlich ist.

Um auf diese Änderung zu reagieren, ändern Sie die Verweise in Ihren *package.json*-Dateien, `require`-Anweisungen und ECMAScript-`import`-Anweisungen. Im Rahmen dieser Umbenennung werden keine APIs geändert.

Weitere Informationen finden Sie unter [dotnet/aspnetcore#11637](https://github.com/dotnet/aspnetcore/issues/11637).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Das Clientpaket hatte den Namen `@aspnet/signalr`.

#### <a name="new-behavior"></a>Neues Verhalten

Das Clientpaket hat jetzt den Namen `@microsoft/signalr`.

#### <a name="reason-for-change"></a>Grund für die Änderung

Die Namensänderung macht deutlich, dass SignalR dank Azure SignalR Service für mehr als nur ASP.NET Core-Apps nützlich ist.

#### <a name="recommended-action"></a>Empfohlene Aktion

Stellen Sie auf das neue Paket `@microsoft/signalr` um.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
