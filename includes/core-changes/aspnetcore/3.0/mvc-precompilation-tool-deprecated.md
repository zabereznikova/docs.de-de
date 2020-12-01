---
ms.openlocfilehash: 8395428e1729a00fc1af72cf53fe689ee95b5fdf
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032613"
---
### <a name="mvc-precompilation-tool-deprecated"></a>MVC: Vorkompilierungstool wurde als veraltet markiert.

In ASP.NET Core 1.1 wurde das Paket `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` (MVC-Vorkompilierungstool) eingeführt, um die Kompilierung von Razor-Dateien (*CSHTML*-Dateien) bei der Veröffentlichung zu unterstützen. In ASP.NET Core 2.1 wurde das [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-2.1) eingeführt, um die Funktionen des Vorkompilierungstools zu erweitern. Mit dem Razor SDK wurde auch die Möglichkeit geschaffen, Razor-Dateien bei der Erstellung und Veröffentlichung zu kompilieren. Das SDK überprüft die Richtigkeit der *CSHTML*-Dateien zur Erstellungszeit und verbessert gleichzeitig die Startzeit der App. Das Razor SDK ist standardmäßig aktiviert und kann ohne weitere Aktion verwendet werden.

In ASP.NET Core 3.0 wurde das MVC-Vorkompilierungstool aus der Zeit von ASP.NET Core 1.1 entfernt. Frühere Paketversionen erhalten weiterhin wichtige Fehler- und Sicherheitskorrekturen, wenn Patches veröffentlicht werden.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Das Paket `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` wurde zum Vorkompilieren von MVC-Razor-Ansichten verwendet.

#### <a name="new-behavior"></a>Neues Verhalten

Das Razor SDK unterstützt diese Funktion nun nativ. Das Paket `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` wird nicht mehr aktualisiert.

#### <a name="reason-for-change"></a>Grund für die Änderung

Das Razor SDK bietet mehr Funktionen und überprüft die Richtigkeit der *CSHTML*-Dateien zur Erstellungszeit. Das SDK verbessert auch die Startzeit von Apps.

#### <a name="recommended-action"></a>Empfohlene Aktion

Benutzer von ASP.NET Core 2.1 oder höher sollten auf die native Unterstützung für die Vorkompilierung im [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-3.0) wechseln. Wenn Fehler oder fehlende Features die Migration zum Razor SDK verhindern, melden Sie auf [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues) ein Problem.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
