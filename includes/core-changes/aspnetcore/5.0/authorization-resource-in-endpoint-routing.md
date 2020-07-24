---
ms.openlocfilehash: 2b88ab7cfdd7a0a0a770b305ecd0200afd9a9b4b
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441548"
---
### <a name="authorization-resource-in-endpoint-routing-is-httpcontext"></a>Autorisierung: Die Ressource im Endpunktrouting ist HttpContext

Bei der Verwendung des Endpunktroutings in ASP.NET Core 3.1 ist die für die Autorisierung verwendete Ressource der Endpunkt. Dieser Ansatz war nicht ausreichend, um Zugriff auf die Routendaten (<xref:Microsoft.AspNetCore.Routing.RouteData>) zu erhalten. Bisher wurde in MVC eine <xref:Microsoft.AspNetCore.Http.HttpContext>-Ressource übergeben, die sowohl den Zugriff auf den Endpunkt (<xref:Microsoft.AspNetCore.Http.Endpoint>) als auch auf die Routendaten ermöglicht. Diese Änderung sorgt dafür, dass die für die Autorisierung übergebene Ressource immer `HttpContext` ist.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 7

#### <a name="old-behavior"></a>Altes Verhalten

Wenn Endpunktrouting und die Autorisierungsmiddleware (<xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware>) oder [[Authorize]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute)-Attribute verwendet werden, ist die für die Autorisierung übergebene Ressource der übereinstimmende Endpunkt.

#### <a name="new-behavior"></a>Neues Verhalten

Beim Endpunktrouting wird `HttpContext` für die Autorisierung übergeben.

#### <a name="reason-for-change"></a>Grund für die Änderung

Der Endpunkt kann über `HttpContext` erreicht werden. Es bestand jedoch keine Möglichkeit, vom Endpunkt beispielsweise zu den Routendaten zu gelangen. Beim Nicht-Endpunkt-Routing führte das also zu einer eingeschränkten Funktionalität.

#### <a name="recommended-action"></a>Empfohlene Aktion

Wenn Ihre App die Endpunktressource verwendet, rufen Sie <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A> in `HttpContext` auf, um das Zugreifen auf den Endpunkt fortzusetzen.

In ASP.NET Core 5.0 Preview 8 und höher können Sie das alte Verhalten mit <xref:System.AppContext.SetSwitch%2A> wiederherstellen. Zum Beispiel:

```csharp
AppContext.SetSwitch(
    "Microsoft.AspNetCore.Authorization.SuppressUseHttpContextAsAuthorizationResource",
    isEnabled: true);
```

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!--

#### Affected APIs

Not detectable via API analysis

-->
