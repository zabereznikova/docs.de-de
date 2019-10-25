---
ms.openlocfilehash: acef6d7177ee5ad7e18dc8ba1e383d6f76263623
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394446"
---
### <a name="signalr-javascript-client-package-name-changed"></a>SignalR: Name des JavaScript-Clientpakets geändert

In ASP.NET Core 3.0 Preview 7 wurde der Name des SignalR-JavaScript-Clientpakets von `@aspnet/signalr` in `@microsoft/signalr` geändert. Die Namensänderung spiegelt die Tatsache wider, dass SignalR dank Azure SignalR Service für mehr als nur ASP.NET Core-Apps nützlich ist.

Um auf diese Änderung zu reagieren, ändern Sie die Verweise in Ihren *package.json*-Dateien, `require`-Anweisungen und ECMAScript-`import`-Anweisungen. Im Rahmen dieser Umbenennung werden keine APIs geändert.

Weitere Informationen finden Sie unter [aspnet/AspNetCore#11637](https://github.com/aspnet/AspNetCore/issues/11637).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Das Clientpaket hatte den Namen `@aspnet/signalr`.

#### <a name="new-behavior"></a>Neues Verhalten

Das Clientpaket hat jetzt den Namen `@microsoft/signalr`.

#### <a name="reason-for-change"></a>Grund für die Änderung

Die Namensänderung macht deutlich, dass SignalR dank Azure SignalR Service für mehr als nur ASP.NET Core-Apps nützlich ist.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Stellen Sie auf das neue Paket `@microsoft/signalr` um.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
