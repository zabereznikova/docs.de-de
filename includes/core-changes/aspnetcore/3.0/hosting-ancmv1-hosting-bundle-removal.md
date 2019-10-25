---
ms.openlocfilehash: 04e5ca41374fc333a31f0422bc2e89f54b3cb049
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394299"
---
### <a name="hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle"></a>Hosting: AspNetCoreModule v1 wurde aus dem Windows-Hostingpaket entfernt.

Ab ASP.NET Core 3.0 ist AspNetCoreModule v1 (ANCM) nicht mehr im Windows-Hostingpaket enthalten.

ANCM v2 ist abwärtskompatibel mit ANCM OutOfProcess und wird für die Verwendung mit ASP.NET Core 3.0-Apps empfohlen.

Weitere Informationen finden Sie unter [aspnet/AspNetCore#7095](https://github.com/aspnet/AspNetCore/issues/7095).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

ANCM v1 war im Windows-Hostingpaket enthalten.

#### <a name="new-behavior"></a>Neues Verhalten

ANCM v1 ist nicht mehr im Windows-Hostingpaket enthalten.

#### <a name="reason-for-change"></a>Grund für die Änderung

ANCM v2 ist abwärtskompatibel mit ANCM OutOfProcess und wird für die Verwendung mit ASP.NET Core 3.0-Apps empfohlen.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

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
