---
ms.openlocfilehash: 75945e7ff26c1c6db891d12cef4c16ed210da6af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "72393903"
---
### <a name="mvc-web-api-compatibility-shim-removed"></a>MVC: Web-API-Kompatibilitätsshim wurde entfernt.

Ab ASP.NET Core 3.0 ist das Paket `Microsoft.AspNetCore.Mvc.WebApiCompatShim` nicht mehr verfügbar.

#### <a name="change-description"></a>Änderungsbeschreibung

Das Paket `Microsoft.AspNetCore.Mvc.WebApiCompatShim` (WebApiCompatShim) bietet partielle Kompatibilität in ASP.NET Core mit der ASP.NET 4.x-Web-API 2, um die Migration vorhandener Web-API-Implementierungen zu ASP.NET Core zu vereinfachen. Apps, die WebApiCompatShim verwenden, profitieren jedoch nicht von den API-bezogenen Features der letzten ASP.NET Core-Releases. Zu diesen Features zählen die verbesserte Generierung von Open API-Spezifikationen, die standardisierte Fehlerbehandlung und die Generierung von Clientcode. Um die API in 3.0 noch weiter zu optimieren, wurde WebApiCompatShim entfernt. Vorhandene Apps, die WebApiCompatShim verwenden, sollten zum neueren `[ApiController]`-Modell migriert werden.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="reason-for-change"></a>Grund für die Änderung

Das Web-API-Kompatibilitätsshim war ein Migrationstool. Es beschränkt den Benutzerzugriff auf neue Funktionen, die in ASP.NET Core hinzugefügt wurden.

#### <a name="recommended-action"></a>Empfohlene Aktion

Entfernen Sie alle Verwendungen dieses Shims, und migrieren Sie direkt zu der entsprechenden Funktionalität in ASP.NET Core.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.AspNetCore.Mvc.WebApiCompatShim?displayProperty=fullName>

<!--

#### Affected APIs

N:Microsoft.AspNetCore.Mvc.WebApiCompatShim

-->
