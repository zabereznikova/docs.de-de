---
ms.openlocfilehash: 5741e8cdd51e00d5459c4c1032a56682429aab17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901785"
---
### <a name="mvc-pubternal-types-changed-to-internal"></a>MVC: „pubternal“-Typen in „internal“-Typen geändert

In ASP.NET Core 3.0 wurden alle „pubternal“-Typen in MVC je nach Anwendungsfall in `public` in einem unterstützten Namespace oder in `internal` geändert.

#### <a name="change-description"></a>Änderungsbeschreibung

In ASP.NET Core werden „pubternal“-Typen als `public` deklariert, befinden sich jedoch in einem Namespace mit dem Suffix `.Internal`. Diese Typen sind zwar `public`, sie verfügen jedoch nicht über eine Unterstützungsrichtlinie und können daher Breaking Changes unterliegen. Da diese Typen leider relativ häufig versehentlich verwendet werden, können an diesen Projekten Breaking Changes auftreten, und die Fähigkeit zum Verwalten des Frameworks kann eingeschränkt werden.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Einige Typen in MVC waren `public` – aber in einem `.Internal`-Namespace. Diese Typen verfügten nicht über eine Unterstützungsrichtlinie und konnten daher Breaking Changes unterliegen.

#### <a name="new-behavior"></a>Neues Verhalten

Alle diese Typen wurden entweder als `public` in einem unterstützten Namespace oder als `internal` gekennzeichnet.

#### <a name="reason-for-change"></a>Grund für die Änderung

Da die „pubternal“-Typen relativ häufig versehentlich verwendet wurden, konnten an diesen Projekten Breaking Changes auftreten, und die Fähigkeit zum Verwalten des Frameworks konnte eingeschränkt werden.

#### <a name="recommended-action"></a>Empfohlene Aktion

Wenn Sie Typen verwenden, die tatsächlich `public` waren und in einen neuen, unterstützten Namespace verschoben wurden, aktualisieren Sie Ihre Verweise entsprechend den neuen Namespaces.

Wenn Sie Typen verwenden, die als `internal` gekennzeichnet wurden, müssen Sie eine Alternative suchen. Die zuvor als „pubternal“ deklarierten Typen waren nie für die öffentliche Verwendung vorgesehen. Wenn diese Namespaces bestimmte Typen enthalten, die für Ihre Apps wichtig sind, melden Sie ein Problem bei [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues). Es ist eventuell möglich, die angeforderten Typen `public` zu machen.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Diese Änderung umfasst Typen in den folgenden Namespaces:

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

<!--

#### Affected APIs

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

-->
