---
title: 'Breaking Change: Autorisierung: Die Ressource im Endpunktrouting ist HttpContext'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „Autorisierung: Die Ressource im Endpunktrouting ist HttpContext'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 7c5a77cb8999c60a7780b9b4f7ad2a1c79fd8310
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759544"
---
# <a name="authorization-resource-in-endpoint-routing-is-httpcontext"></a>Autorisierung: Die Ressource im Endpunktrouting ist HttpContext

Bei der Verwendung des Endpunktroutings in ASP.NET Core 3.1 ist die für die Autorisierung verwendete Ressource der Endpunkt. Dieser Ansatz war nicht ausreichend, um Zugriff auf die Routendaten (<xref:Microsoft.AspNetCore.Routing.RouteData>) zu erhalten. Bisher wurde in MVC eine <xref:Microsoft.AspNetCore.Http.HttpContext>-Ressource übergeben, die sowohl den Zugriff auf den Endpunkt (<xref:Microsoft.AspNetCore.Http.Endpoint>) als auch auf die Routendaten ermöglicht. Diese Änderung sorgt dafür, dass die für die Autorisierung übergebene Ressource immer `HttpContext` ist.

## <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 7

## <a name="old-behavior"></a>Altes Verhalten

Wenn Endpunktrouting und die Autorisierungsmiddleware (<xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware>) oder [[Authorize]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute)-Attribute verwendet werden, ist die für die Autorisierung übergebene Ressource der übereinstimmende Endpunkt.

## <a name="new-behavior"></a>Neues Verhalten

Beim Endpunktrouting wird `HttpContext` für die Autorisierung übergeben.

## <a name="reason-for-change"></a>Grund für die Änderung

Der Endpunkt kann über `HttpContext` erreicht werden. Es bestand jedoch keine Möglichkeit, vom Endpunkt beispielsweise zu den Routendaten zu gelangen. Beim Nicht-Endpunkt-Routing führte das also zu einer eingeschränkten Funktionalität.

## <a name="recommended-action"></a>Empfohlene Aktion

Wenn Ihre App die Endpunktressource verwendet, rufen Sie <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A> in `HttpContext` auf, um das Zugreifen auf den Endpunkt fortzusetzen.

In ASP.NET Core 5.0 Preview 8 und höher können Sie das alte Verhalten mit <xref:System.AppContext.SetSwitch%2A> wiederherstellen. Zum Beispiel:

```csharp
AppContext.SetSwitch(
    "Microsoft.AspNetCore.Authorization.SuppressUseHttpContextAsAuthorizationResource",
    isEnabled: true);
```

## <a name="affected-apis"></a>Betroffene APIs

Keine

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
