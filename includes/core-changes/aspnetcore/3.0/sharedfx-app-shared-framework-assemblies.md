---
ms.openlocfilehash: a8146db1fb54d63d4716b879ce793f7d817cef59
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937282"
---
### <a name="shared-framework-assemblies-removed-from-microsoftaspnetcoreapp"></a>Freigegebenes Framework: Assemblys aus Microsoft.AspNetCore.App entfernt

Ab ASP.NET Core 3.0 enthält das freigegebene ASP.NET Core-Framework (`Microsoft.AspNetCore.App`) nur Erstanbieterassemblys, die vollständig von Microsoft entwickelt, unterstützt und verwaltet werden.

#### <a name="change-description"></a>Änderungsbeschreibung

Diese Änderung definiert die Grenzen der ASP.NET Core-„Plattform“ neu. Das freigegebene Framework kann [von allen Benutzern über GitHub aus der Quelle erstellt](https://github.com/dotnet/source-build) werden. Es bietet Ihren Apps dabei auch weiterhin die bestehenden Vorteile der freigegebenen .NET Core-Frameworks von .NET Core. Zu den Vorteilen zählen die kleinere Bereitstellungsgröße, das zentralisierte Patchen und die schnellere Startzeit.

Im Rahmen der Änderung werden einige wichtige Breaking Changes in `Microsoft.AspNetCore.App` eingeführt.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Projekte verwiesen über ein `<PackageReference>`-Element in der Projektdatei auf `Microsoft.AspNetCore.App`.

Außerdem enthielt `Microsoft.AspNetCore.App` die folgenden Unterkomponenten:

- Json.NET (`Newtonsoft.Json`)
- Entity Framework Core (Assemblys mit Präfix `Microsoft.EntityFrameworkCore.`)
- Roslyn (`Microsoft.CodeAnalysis`)

#### <a name="new-behavior"></a>Neues Verhalten

Für einen Verweis auf `Microsoft.AspNetCore.App` ist kein `<PackageReference>`-Element in der Projektdatei mehr erforderlich. Das .NET Core SDK unterstützt ein neues Element mit dem Namen `<FrameworkReference>`, das `<PackageReference>` ersetzt.

Weitere Informationen finden Sie unter [dotnet/aspnetcore#3612](https://github.com/dotnet/aspnetcore/issues/3612).

Entity Framework Core wird als NuGet-Pakete bereitgestellt. Diese Änderung stellt eine Anpassung an das Auslieferungsmodell aller anderen Datenzugriffsbibliotheken in .NET dar. Es bietet Entity Framework Core die einfachste Möglichkeit, weiterhin Innovationen mit Unterstützung der verschiedenen .NET-Plattformen zu schaffen. Das Verschieben von Entity Framework Core aus dem freigegebenen Framework hat keine Auswirkung auf seinen Status als eine von Microsoft entwickelte, unterstützte und gewartete Bibliothek. Die [.NET Core-Supportrichtlinie](https://www.microsoft.com/net/platform/support-policy) gilt auch weiterhin.

Json.NET und Entity Framework Core funktionieren auch In Zukunft mit ASP.NET Core. Sie sind jedoch nicht mehr im freigegebenen Framework enthalten.

Weitere Informationen finden Sie unter [The future of JSON in .NET Core 3.0](https://github.com/dotnet/announcements/issues/90) (Die Zukunft von JSON in .NET Core 3.0). Sehen Sie sich auch [die komplette Liste der Binärdateien](https://github.com/dotnet/aspnetcore/issues/3755) an, die aus dem freigegebenen Framework entfernt wurden.

#### <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung vereinfacht die Verwendung von `Microsoft.AspNetCore.App` und verringert Duplizierungen zwischen NuGet-Paketen und freigegebenen Frameworks.

Weitere Informationen zu den Gründen für diese Änderung finden Sie in [diesem Blogbeitrag](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/).

#### <a name="recommended-action"></a>Empfohlene Aktion

Projekte müssen Assemblys in `Microsoft.AspNetCore.App` nicht als NuGet-Pakete verwenden. Um die Ausrichtung und Verwendung des freigegebenen ASP.NET Core-Frameworks zu vereinfachen, werden viele NuGet-Pakete, die seit ASP.NET Core 1.0 eingeführt wurden, nicht mehr erstellt. Die von diesen Paketen bereitgestellten APIs sind für Apps weiterhin mithilfe eines `<FrameworkReference>` auf `Microsoft.AspNetCore.App` verfügbar. Beispiele für gängige APIs sind Kestrel, MVC und Razor.

Diese Änderung gilt nicht für alle Binärdateien, auf die über `Microsoft.AspNetCore.App` in ASP.NET Core 2.x verwiesen wird. Wichtige Ausnahmen sind:

- `Microsoft.Extensions`-Bibliotheken, die weiterhin auf .NET Standard abzielen, werden als NuGet-Pakete verfügbar gemacht (siehe https://github.com/dotnet/extensions).
- APIs, die vom ASP.NET Core-Team erstellt werden und die nicht Teil `Microsoft.AspNetCore.App` sind. Die folgenden Komponenten sind beispielsweise als NuGet-Pakete verfügbar:
  - Entity Framework Core
  - APIs, die eine Integration von Drittanbietern bereitstellen
  - Experimentelle Features
  - APIs mit Abhängigkeiten, die die [Anforderungen für die Aufnahme in das freigegebene Framework](https://github.com/dotnet/aspnetcore/blob/4e44e5bcbedd961cc0d4f6b846699c7c494f5597/docs/SharedFramework.md) nicht erfüllen konnten
- Erweiterungen für MVC zur Unterstützung von Json.NET. Eine API wird als NuGet-Paket bereitgestellt, um die Verwendung von Json.NET und MVC zu unterstützen.
- Der SignalR-.NET-Client unterstützt weiterhin .NET Standard und wird als NuGet-Paket bereitgestellt. Er ist für die Verwendung in vielen .NET-Runtimes vorgesehen, z. B. Xamarin und UWP.

Weitere Informationen finden Sie unter [Stop producing packages for shared framework assemblies in 3.0](https://github.com/dotnet/aspnetcore/issues/3756) (Beenden der Erstellung von Paketen für Assemblys in freigegebenen Frameworks in 3.0). Weitere Informationen finden Sie unter [dotnet/aspnetcore#3757](https://github.com/dotnet/aspnetcore/issues/3757).

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:Microsoft.CodeAnalysis?displayProperty=nameWithType>
- <xref:Microsoft.EntityFrameworkCore?displayProperty=nameWithType>

<!--

#### Affected APIs

- `N:Microsoft.CodeAnalysis`
- `N:Microsoft.EntityFrameworkCore`

-->
