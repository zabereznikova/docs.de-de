---
ms.openlocfilehash: 52b9caf2d5b3d44c0c6349501dafc371541fdd70
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396351"
---
### <a name="pubternal-apis-removed"></a>„Pubternal“-APIs entfernt

Um die öffentliche API-Oberfläche von ASP.NET Core besser zu verwalten, sind die meisten Typen in `*.Internal`-Namespaces (als :::no-loc text="\"pubternal\"":::-APIs bezeichnet) wirklich intern geworden. Member in diesen Namespaces sollten nie als öffentlich ausgerichtete APIs unterstützt werden. Bei den APIs konnten in Nebenversionen Fehler auftreten, was auch häufig der Fall war. Bei Code, der von diesen APIs abhängig ist, treten beim Aktualisieren auf ASP.Net Core 3.0 Fehler auf.

Weitere Informationen finden Sie unter [dotnet/aspnetcore#4932](https://github.com/dotnet/aspnetcore/issues/4932) und [dotnet/aspnetcore#11312](https://github.com/dotnet/aspnetcore/issues/11312).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Die betroffenen APIs werden mit dem `public`-Zugriffsmodifizierer gekennzeichnet und sind in `*.Internal`-Namespaces vorhanden.

#### <a name="new-behavior"></a>Neues Verhalten

Die betroffenen APIs sind mit dem [internal(~/docs/csharp/language-reference/keywords/internal.md)]-Zugriffsmodifizierer gekennzeichnet und können nicht mehr von Code außerhalb dieser Assembly verwendet werden.

#### <a name="reason-for-change"></a>Grund für die Änderung

Die Richtlinie für diese :::no-loc text="\"pubternal\"":::-APIs war:

* Sie konnten ohne vorherige Ankündigung geändert werden.
* Sie unterlagen nicht den .NET-Richtlinien zum Verhindern von Breaking Changes.

Die APIs `public` zu lassen (selbst in den `*.Internal`-Namespaces), war für Kunden verwirrend.

#### <a name="recommended-action"></a>Empfohlene Aktion

Verwenden Sie diese :::no-loc text="\"pubternal\"":::-APIs nicht mehr. Wenn Sie Fragen zu alternativen APIs haben, öffnen Sie ein Issue im [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues)-Repository.

Sehen Sie sich beispielsweise den folgenden HTTP-Anforderungspuffercode in einem ASP.NET Core 2.2-Projekt an. Die `EnableRewind`-Erweiterungsmethode ist im `Microsoft.AspNetCore.Http.Internal`-Namespace vorhanden.

```csharp
HttpContext.Request.EnableRewind();
```

Ersetzen Sie den `EnableRewind`-Aufruf in einem ASP.NET Core 3.0-Projekt durch einen Aufruf der `EnableBuffering`-Erweiterungsmethode. Das Feature für die Anforderungspufferung funktioniert wie bisher. `EnableBuffering` ruft die jetzige `internal`-API auf.

```csharp
HttpContext.Request.EnableBuffering();
```

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Alle APIs in den `Microsoft.AspNetCore.*`-und `Microsoft.Extensions.*`-Namespaces mit einem `Internal`-Segment im Namespacenamen. Zum Beispiel:

- `Microsoft.AspNetCore.Authentication.Internal`
- `Microsoft.AspNetCore.Builder.Internal`
- `Microsoft.AspNetCore.DataProtection.Cng.Internal`
- `Microsoft.AspNetCore.DataProtection.Internal`
- `Microsoft.AspNetCore.Hosting.Internal`
- `Microsoft.AspNetCore.Http.Internal`
- `Microsoft.AspNetCore.Mvc.Core.Infrastructure`
- `Microsoft.AspNetCore.Mvc.Core.Internal`
- `Microsoft.AspNetCore.Mvc.Cors.Internal`
- `Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `Microsoft.AspNetCore.Mvc.Internal`
- `Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `Microsoft.AspNetCore.Mvc.Razor.Internal`
- `Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`
- `Microsoft.AspNetCore.Rewrite.Internal`
- `Microsoft.AspNetCore.Routing.Internal`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Http`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Infrastructure`
- `Microsoft.AspNetCore.Server.Kestrel.Https.Internal`

<!--

#### Affected APIs

- `N:Microsoft.AspNetCore.Authentication.Internal`
- `N:Microsoft.AspNetCore.Builder.Internal`
- `N:Microsoft.AspNetCore.DataProtection.Cng.Internal`
- `N:Microsoft.AspNetCore.DataProtection.Internal`
- `N:Microsoft.AspNetCore.Hosting.Internal`
- `N:Microsoft.AspNetCore.Http.Internal`
- `N:Microsoft.AspNetCore.Mvc.Core.Infrastructure`
- `N:Microsoft.AspNetCore.Mvc.Core.Internal`
- `N:Microsoft.AspNetCore.Mvc.Cors.Internal`
- `N:Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `N:Microsoft.AspNetCore.Mvc.Internal`
- `N:Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `N:Microsoft.AspNetCore.Mvc.Razor.Internal`
- `N:Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `N:Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `N:Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`
- `N:Microsoft.AspNetCore.Rewrite.Internal`
- `N:Microsoft.AspNetCore.Routing.Internal`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Http`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Infrastructure`
- `N:Microsoft.AspNetCore.Server.Kestrel.Https.Internal`

-->
