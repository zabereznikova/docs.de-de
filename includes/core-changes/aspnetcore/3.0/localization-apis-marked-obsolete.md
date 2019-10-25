---
ms.openlocfilehash: da1ec7908b3082fc61313cb805773aa600bc1b5d
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394416"
---
### <a name="localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete"></a>Lokalisierung: ResourceManagerWithCultureStringLocalizer und WithCulture wurden als veraltet markiert.

Die [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18)-Klasse und der Schnittstellenmember [WithCulture](https://github.com/aspnet/Localization/blob/master/src/Microsoft.Extensions.Localization/ResourceManagerStringLocalizer.cs#L154-L170) führten häufig zu Verwirrung bei Benutzern der Lokalisierung, insbesondere bei der Erstellung einer eigenen Implementierung von `IStringLocalizer`. Diese Elemente vermittelten dem Benutzer den Eindruck, dass eine `IStringLocalizer`-Instanz lediglich „pro Sprache, pro Ressource“ gilt. Tatsächlich sollten die Instanzen nur „pro Ressource“ gelten. Die gesuchte Sprache wird zur Ausführungszeit von der `CultureInfo.CurrentUICulture` festgelegt. Um dieses Problem zu beheben, wurden die APIs in ASP.NET Core 3.0 Preview 3 als veraltet markiert. Die APIs werden in einem der nächsten Releases entfernt.

Weitere Kontextinformationen finden Sie unter [aspnet/AspNetCore#3324](https://github.com/aspnet/AspNetCore/issues/3324). Weitere Informationen finden Sie unter [aspnet/AspNetCore#7756](https://github.com/aspnet/AspNetCore/issues/7756).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Methoden wurden nicht als `Obsolete` gekennzeichnet.

#### <a name="new-behavior"></a>Neues Verhalten

Methoden werden als `Obsolete` gekennzeichnet.

#### <a name="reason-for-change"></a>Grund für die Änderung

Die APIs stellten einen Anwendungsfall dar, der nicht empfohlen wird. Der Entwurf der Lokalisierung war unklar.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Es wird empfohlen, stattdessen `ResourceManagerStringLocalizer` zu verwenden. Lassen Sie die Kultur durch `CurrentCulture` festlegen. Falls dies nicht möglich ist, erstellen Sie eine Kopie von [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18), und verwenden Sie diese.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer>
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
