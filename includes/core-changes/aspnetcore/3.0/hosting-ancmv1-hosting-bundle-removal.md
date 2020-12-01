---
ms.openlocfilehash: 82103d82a6f68c62f3532608718bc71b0ba126bf
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032503"
---
### <a name="hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle"></a>Hosting: AspNetCoreModule v1 wurde aus dem Windows-Hostingpaket entfernt.

Ab ASP.NET Core 3.0 ist AspNetCoreModule v1 (ANCM) nicht mehr im Windows-Hostingpaket enthalten.

ANCM v2 ist abwärtskompatibel mit ANCM OutOfProcess und wird für die Verwendung mit ASP.NET Core 3.0-Apps empfohlen.

Weitere Informationen finden Sie unter [dotnet/aspnetcore#7095](https://github.com/dotnet/aspnetcore/issues/7095).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

ANCM v1 war im Windows-Hostingpaket enthalten.

#### <a name="new-behavior"></a>Neues Verhalten

ANCM v1 ist nicht mehr im Windows-Hostingpaket enthalten.

#### <a name="reason-for-change"></a>Grund für die Änderung

ANCM v2 ist abwärtskompatibel mit ANCM OutOfProcess und wird für die Verwendung mit ASP.NET Core 3.0-Apps empfohlen.

#### <a name="recommended-action"></a>Empfohlene Aktion

Verwenden Sie ANCM v2 mit ASP.NET Core 3.0-Apps.

Wenn ANCM v1 erforderlich ist, kann es mit dem Windows-Hostingpaket für ASP.NET Core 2.1 oder 2.2 installiert werden.

Diese Änderung stellt einen Breaking Change für ASP.NET Core 3.0-Apps dar, für die Folgendes gilt:

- Sie verwenden ANCM v1 explizit über `<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>`.
- Sie verfügen über eine benutzerdefinierte Datei *web.config*  mit `<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />`.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
