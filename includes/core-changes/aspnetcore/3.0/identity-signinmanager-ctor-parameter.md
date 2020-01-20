---
ms.openlocfilehash: 6f8e6d2786d20e055c9bef63891db4d6f88bc64b
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901757"
---
### <a name="identity-signinmanager-constructor-accepts-new-parameter"></a>Identität: SignInManager-Konstruktor akzeptiert neuen Parameter.

Ab ASP.NET Core 3.0 wurde dem `SignInManager`-Konstruktor ein neuer `IUserConfirmation<TUser>`-Parameter hinzugefügt. Weitere Informationen finden Sie unter [dotnet/aspnetcore#8356](https://github.com/dotnet/aspnetcore/issues/8356).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung war erforderlich, um Unterstützung für neue E-Mail-/Bestätigungsflows für Identitäten zu erzielen.

#### <a name="recommended-action"></a>Empfohlene Aktion

Wenn Sie manuell einen `SignInManager` erstellen, stellen Sie eine Implementierung von `IUserConfirmation` bereit, oder nutzen Sie dafür eine der Abhängigkeitsinjektion.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
