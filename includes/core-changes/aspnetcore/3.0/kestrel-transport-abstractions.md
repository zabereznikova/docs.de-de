---
ms.openlocfilehash: fb23418816abcae125106c93b339a546aa9bc2ee
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721233"
---
### <a name="kestrel-transport-abstractions-removed-and-made-public"></a>Kestrel: Datentransportabstraktionen wurden entfernt und öffentlich gemacht.

Im Rahmen der Umstellung von „pubternal“-APIs werden die Kestrel-APIs auf der Datentransportschicht als öffentliche Schnittstelle in der `Microsoft.AspNetCore.Connections.Abstractions`-Bibliothek verfügbar gemacht.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

- Abstraktionen zum Datentransport waren in der `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions`-Bibliothek verfügbar.
- Die `ListenOptions.NoDelay`-Eigenschaft war verfügbar.

#### <a name="new-behavior"></a>Neues Verhalten

- Die `IConnectionListener`-Schnittstelle wurde in der `Microsoft.AspNetCore.Connections.Abstractions`-Bibliothek eingeführt, um die am häufigsten verwendeten Funktionen aus der `...Transport.Abstractions`-Bibliothek verfügbar zu machen.
- `NoDelay` ist nun in den Datentransportoptionen (`LibuvTransportOptions` und `SocketTransportOptions`) verfügbar.
- `SchedulingMode` ist nicht mehr verfügbar.

#### <a name="reason-for-change"></a>Grund für die Änderung

In ASP.NET Core 3.0 werden keine „pubternal“-APIs mehr verwendet.

#### <a name="recommended-action"></a>Empfohlene Aktion

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
