---
ms.openlocfilehash: 0c88d40e34d2d6458bb463a09d716dea42b711fe
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901850"
---
### <a name="authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters"></a>Autorisierung: IAllowAnonymous aus AuthorizationFilterContext.Filters entfernt

Ab ASP.NET Core 3.0 fügt MVC keine [AllowAnonymousFilters](xref:Microsoft.AspNetCore.Mvc.Authorization.AllowAnonymousFilter) für [[AllowAnonymous]](xref:Microsoft.AspNetCore.Authorization.AllowAnonymousAttribute)-Attribute hinzu, die für Controller und Aktionsmethoden ermittelt wurden. Diese Änderung wird lokal für Ableitungen von <xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute>behandelt, ist aber ein Breaking Change für <xref:Microsoft.AspNetCore.Mvc.Filters.IAsyncAuthorizationFilter>- und <xref:Microsoft.AspNetCore.Mvc.Filters.IAuthorizationFilter>-Implementierungen. Solche Implementierungen, die ein [[TypeFilter]](xref:Microsoft.AspNetCore.Mvc.TypeFilterAttribute)-Attribut als Wrapper verwenden, sind eine [gängige](https://stackoverflow.com/a/41348219/608220) und unterstützte Möglichkeit, um eine stark typisierte, attributbasierte Autorisierung zu erreichen, wenn sowohl Konfiguration als auch Abhängigkeitsinjektion (Dependency Injection, DI) erforderlich sind.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

<xref:Microsoft.AspNetCore.Authorization.IAllowAnonymous> war in der [AuthorizationFilterContext.Filters](xref:Microsoft.AspNetCore.Mvc.Filters.FilterContext.Filters%2A)-Sammlung enthalten. Das Testen auf das Vorhandensein der Schnittstelle war ein gültiger Ansatz, um den Filter für einzelne Controllermethoden zu überschreiben oder zu deaktivieren.

#### <a name="new-behavior"></a>Neues Verhalten

`IAllowAnonymous` ist nicht mehr in der `AuthorizationFilterContext.Filters`-Sammlung enthalten. `IAsyncAuthorizationFilter`-Implementierungen, die vom alten Verhalten abhängig sind, verursachen in der Regel vorübergehende HTTP 401- (Nicht autorisiert) oder HTTP 403-Antworten (Unzulässig).

#### <a name="reason-for-change"></a>Grund für die Änderung

In ASP.NET Core 3.0 wurde eine neue Endpunktroutingstrategie eingeführt.

#### <a name="recommended-action"></a>Empfohlene Aktion

Suchen Sie nach den Endpunktmetadaten für `IAllowAnonymous`. Zum Beispiel:

```csharp
var endpoint = context.HttpContext.GetEndpoint();
if (endpoint?.Metadata?.GetMetadata<IAllowAnonymous>() != null)
{
}
```

Ein Beispiel für diese Technik finden Sie in [dieser HasAllowAnonymous-Methode](https://github.com/dotnet/aspnetcore/blob/bd65275148abc9b07a3b59797a88d485341152bf/src/Mvc/Mvc.Core/src/Authorization/AuthorizeFilter.cs#L236).

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!--

#### Affected APIs

Not detectable via API analysis

-->
