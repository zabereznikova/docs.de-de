---
ms.openlocfilehash: 177617569a93e09f4c2a05acc21dce362edd58bc
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394311"
---
### <a name="http-defaulthttpcontext-extensibility-removed"></a>HTTP: Erweiterbarkeit von DefaultHttpContext entfernt

Im Rahmen der Leistungsverbesserungen in ASP.NET Core 3.0 wurde die Erweiterbarkeit von `DefaultHttpContext` aufgehoben. Die Klasse ist jetzt `sealed`. Weitere Informationen finden Sie unter [aspnet/AspNetCore#6504](https://github.com/aspnet/AspNetCore/pull/6504).

Wenn Sie für Komponententests `Mock<DefaultHttpContext>` verwenden, nutzen Sie stattdessen `Mock<HttpContext>`. 

Weitere Informationen finden Sie unter [aspnet/AspNetCore#6534](https://github.com/aspnet/AspNetCore/issues/6534).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Klassen konnten von `DefaultHttpContext` abgeleitet werden.

#### <a name="new-behavior"></a>Neues Verhalten

Klassen können nicht mehr von `DefaultHttpContext` abgeleitet werden.

#### <a name="reason-for-change"></a>Grund für die Änderung

Die Erweiterbarkeit wurde anfänglich bereitgestellt, um das Pooling des `HttpContext` zu ermöglichen, sie führt aber zu einer unnötigen Komplexität und hat andere Optimierungen behindert.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Wenn Sie in Komponententests `Mock<DefaultHttpContext>` verwenden, nutzen Sie stattdessen `Mock<HttpContext>`. 

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.AspNetCore.Http.DefaultHttpContext?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Http.DefaultHttpContext`

-->
