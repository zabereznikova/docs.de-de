---
ms.openlocfilehash: 2819fb3857fa6d40a2b2e42eeaec2d9c6e50eef0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96299352"
---
### <a name="authorization-addauthorization-overload-moved-to-different-assembly"></a>Autorisierung: AddAuthorization-Überladung in andere Assembly verschoben

Die wichtigsten `AddAuthorization`-Methoden, die bisher in `Microsoft.AspNetCore.Authorization` enthalten waren, wurden in `AddAuthorizationCore` umbenannt. Die alten `AddAuthorization`-Methoden sind immer noch vorhanden, befinden sich jedoch stattdessen in der Assembly `Microsoft.AspNetCore.Authorization.Policy`. Dies sollte auf Apps, die beide Methoden verwenden, keine Auswirkung haben. Beachten Sie, dass `Microsoft.AspNetCore.Authorization.Policy` nun im freigegebenen Framework und nicht mehr in einem eigenständigen Paket enthalten ist, wie unter [Freigegebenes Framework: Assemblys aus Microsoft.AspNetCore.App entfernt](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp) dargestellt wird.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Die `AddAuthorization`-Methoden waren in `Microsoft.AspNetCore.Authorization` enthalten.

#### <a name="new-behavior"></a>Neues Verhalten

Die `AddAuthorization`-Methoden sind jetzt in `Microsoft.AspNetCore.Authorization.Policy` enthalten. `AddAuthorizationCore` ist der neue Name für die alten Methoden.

#### <a name="reason-for-change"></a>Grund für die Änderung

`AddAuthorization` ist ein besserer Methodenname für das Hinzufügen aller allgemeinen Dienste, die für die Autorisierung benötigt werden.

#### <a name="recommended-action"></a>Empfohlene Aktion

Fügen Sie entweder einen Verweis auf `Microsoft.AspNetCore.Authorization.Policy` hinzu, oder verwenden Sie stattdessen `AddAuthorizationCore`.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})`

-->
