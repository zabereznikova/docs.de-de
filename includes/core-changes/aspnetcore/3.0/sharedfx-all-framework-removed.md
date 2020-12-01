---
ms.openlocfilehash: 959f3959c28c7d0159be7a213986345e2865b9a2
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032650"
---
### <a name="shared-framework-removed-microsoftaspnetcoreall"></a>Freigegebenes Framework: Microsoft.AspNetCore.All wurde entfernt

Ab ASP.NET Core 3.0 werden das Metapaket `Microsoft.AspNetCore.All` und das entsprechende freigegebene Framework `Microsoft.AspNetCore.All` nicht mehr erstellt. Dieses Paket ist in ASP.NET Core 2.2 verfügbar und wird auch weiterhin mit Wartungsupdates in ASP.NET Core 2.1 versorgt.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Apps konnten das Metapaket `Microsoft.AspNetCore.All` verwenden, um das freigegebene Framework `Microsoft.AspNetCore.All` als Ziel in .NET Core zu verwenden.

#### <a name="new-behavior"></a>Neues Verhalten

.NET Core 3.0 enthält das freigegebene Framework `Microsoft.AspNetCore.All` nicht mehr.

#### <a name="reason-for-change"></a>Grund für die Änderung

Das Metapaket `Microsoft.AspNetCore.All` enthielt eine große Anzahl externer Abhängigkeiten.

#### <a name="recommended-action"></a>Empfohlene Aktion

Stellen Sie Ihr Projekt auf die Verwendung des Frameworks `Microsoft.AspNetCore.App` um. Komponenten, die zuvor in `Microsoft.AspNetCore.All` verfügbar waren, sind weiterhin in NuGet verfügbar. Diese Komponenten werden nun mit Ihrer App bereitgestellt, anstatt in das freigegebene Framework eingefügt zu werden.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
