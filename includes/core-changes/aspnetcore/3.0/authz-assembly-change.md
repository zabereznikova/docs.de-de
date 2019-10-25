---
ms.openlocfilehash: 65bac44c84589fb55d2b04c39088c2825c451a6b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394059"
---
### <a name="authorization-addauthorization-overload-moved-to-different-assembly"></a>Autorisierung: AddAuthorization-Überladung in andere Assembly verschoben

Die wichtigsten `AddAuthorization`-Methoden, die bisher in `Microsoft.AspNetCore.Authorization` enthalten waren, wurden in `AddAuthorizationCore` umbenannt. Die alten `AddAuthorization`-Methoden sind immer noch vorhanden, befinden sich jedoch stattdessen im Paket `Microsoft.AspNetCore.Authorization.Policy`. Dies sollte auf Apps, die beide Methoden verwenden, keine Auswirkung haben. Apps, die das Richtlinienpaket nicht verwendet haben, müssen auf die Verwendung von `AddAuthorizationCore` umgestellt werden.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Die `AddAuthorization`-Methoden waren in `Microsoft.AspNetCore.Authorization` enthalten.

#### <a name="new-behavior"></a>Neues Verhalten

Die `AddAuthorization`-Methoden sind jetzt in `Microsoft.AspNetCore.Authorization.Policy` enthalten. `AddAuthorizationCore` ist der neue Name für die alten Methoden.

#### <a name="reason-for-change"></a>Grund für die Änderung

`AddAuthorization` ist ein besserer Methodenname für das Hinzufügen aller allgemeinen Dienste, die für die Autorisierung benötigt werden.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Fügen Sie entweder einen Verweis auf `Microsoft.AspNetCore.Authorization.Policy` hinzu, oder verwenden Sie stattdessen `AddAuthorizationCore`.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})`

-->
