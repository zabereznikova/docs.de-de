---
ms.openlocfilehash: a9545c66d3873b5114fe66e13c77ddc28e20020e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077604"
---
### <a name="blazor-protectedbrowserstorage-feature-moved-to-shared-framework"></a>Blazor: Das Feature ProtectedBrowserStorage wurde in das freigegebene Framework verschoben

Im Rahmen des Release von ASP.NET Core 5.0 RC2 wurde das Feature `ProtectedBrowserStorage` in das freigegebene Framework von ASP.NET Core verschoben.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 RC2

#### <a name="old-behavior"></a>Altes Verhalten

In ASP.NET Core 5.0, Preview 8 ist das Feature als Teil des Pakets [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions) verfügbar, kann aber nur in Blazor WebAssembly verwendet werden.

In ASP.NET Core 5.0 RC1 ist das Feature als Teil des Pakets [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage) verfügbar, das auf das gemeinsame Framework `Microsoft.AspNetCore.App` verweist.

#### <a name="new-behavior"></a>Neues Verhalten

In ASP.NET Core 5.0 RC2 wird kein Verweis auf ein NuGet-Paket mehr benötigt, um auf das Feature zu verweisen und dieses zu verwenden.

#### <a name="reason-for-change"></a>Grund für die Änderung

Die Umstellung auf das freigegebene Framework sorgt für mehr Benutzerfreundlichkeit.

#### <a name="recommended-action"></a>Empfohlene Aktion

Wenn Sie ein Upgrade von ASP.NET Core 5.0 RC1 ausführen, gehen Sie wie folgt vor:

1. Entfernen Sie den Verweis auf das Paket `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` aus dem Projekt.
1. Ersetzen Sie `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` durch `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.
1. Entfernen Sie den Aufruf von `AddProtectedBrowserStorage` aus ihrer `Startup`-Klasse.

Wenn Sie ein Upgrade von ASP.NET Core 5.0, Preview 8 ausführen, gehen Sie wie folgt vor:

1. Entfernen Sie den Verweis auf das Paket `Microsoft.AspNetCore.Components.Web.Extensions` aus dem Projekt.
1. Ersetzen Sie `using Microsoft.AspNetCore.Components.Web.Extensions;` durch `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.
1. Entfernen Sie den Aufruf von `AddProtectedBrowserStorage` aus ihrer `Startup`-Klasse.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!--

#### Affected APIs

Not detectable via API analysis

-->
