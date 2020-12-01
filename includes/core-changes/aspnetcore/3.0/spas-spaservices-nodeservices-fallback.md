---
ms.openlocfilehash: e5355387d5cb6d9e6de89f5b85e64bc100b32ae1
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032682"
---
### <a name="spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger"></a>SPAs: Kein Fallback für SpaServices und NodeServices mehr auf die Konsolenprotokollierung

<xref:Microsoft.AspNetCore.SpaServices?displayProperty=nameWithType> und <xref:Microsoft.AspNetCore.NodeServices?displayProperty=nameWithType> zeigen nur dann Konsolenprotokolle an, wenn die Protokollierung konfiguriert wurde.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

`Microsoft.AspNetCore.SpaServices` und `Microsoft.AspNetCore.NodeServices` erstellten automatisch eine Konsolenprotokollierung, wenn die Protokollierung nicht konfiguriert war.

#### <a name="new-behavior"></a>Neues Verhalten

`Microsoft.AspNetCore.SpaServices` und `Microsoft.AspNetCore.NodeServices` zeigen nur dann Konsolenprotokolle an, wenn die Protokollierung konfiguriert wurde.

#### <a name="reason-for-change"></a>Grund für die Änderung

Mit dieser Änderung soll eine Anpassung an die Implementierung der Protokollierung in anderen ASP.NET Core-Paketen umgesetzt werden.

#### <a name="recommended-action"></a>Empfohlene Aktion

Wenn das alte Verhalten erforderlich ist, fügen Sie zum Konfigurieren der Konsolenprotokollierung Ihrer `Setup.ConfigureServices`-Methode `services.AddLogging(builder => builder.AddConsole())` hinzu.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!--

#### Affected APIs

Not detectable via API analysis

-->
