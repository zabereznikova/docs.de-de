---
ms.openlocfilehash: 56b394c4698f60baeb70d3c17d1abee5d867deb7
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394159"
---
### <a name="identity-signinmanager-constructor-accepts-new-parameter"></a>Identität: SignInManager-Konstruktor akzeptiert neuen Parameter.

Ab ASP.NET Core 3.0 wurde dem `SignInManager`-Konstruktor ein neuer `IUserConfirmation<TUser>`-Parameter hinzugefügt. Weitere Informationen finden Sie unter [aspnet/AspNetCore#8356](https://github.com/aspnet/AspNetCore/issues/8356).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung war erforderlich, um Unterstützung für neue E-Mail-/Bestätigungsflows für Identitäten zu erzielen.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Wenn Sie manuell einen `SignInManager` erstellen, stellen Sie eine Implementierung von `IUserConfirmation` bereit, oder nutzen Sie dafür eine der Abhängigkeitsinjektion.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
