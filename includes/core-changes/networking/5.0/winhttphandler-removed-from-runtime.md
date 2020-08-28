---
ms.openlocfilehash: 115cd6be935ae12a1293f948a0f899c6c3ff0d78
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608461"
---
### <a name="winhttphandler-removed-from-net-runtime"></a>Entfernung von WinHttpHandler aus der .NET-Runtime

Die `WinHttpHandler`-Klasse wurde aus der Assembly *System.Net.Http.dll* entfernt. Sie ist jetzt nur als [OOB-NuGet-Paket](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/) (Out-of-Band) verfügbar.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0

#### <a name="change-description"></a>Änderungsbeschreibung

In früheren .NET-Versionen ist die <xref:System.Net.Http.WinHttpHandler>-Klasse als Teil der .NET-Kernbibliotheken verfügbar. Ab .NET 5.0 ist die <xref:System.Net.Http.WinHttpHandler>-Klasse nur als separat installiertes [NuGet-Paket](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/) verfügbar.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Installieren Sie das [NuGet-Paket „System.Net.Http.WinHttpHandler“](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/). Wenn Sie keine WinHTTP-spezifischen Features benötigen, können Sie stattdessen <xref:System.Net.Http.SocketsHttpHandler> verwenden.

#### <a name="category"></a>Kategorie

Netzwerk

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Net.Http.WinHttpHandler?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Net.Http.WinHttpHandler`

-->
