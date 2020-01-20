---
ms.openlocfilehash: 1b4b0aba3ea24682ae972bf283ac387692c83781
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75902010"
---
### <a name="http-defaulthttpcontext-extensibility-removed"></a>HTTP: Erweiterbarkeit von DefaultHttpContext entfernt

Im Rahmen der Leistungsverbesserungen in ASP.NET Core 3.0 wurde die Erweiterbarkeit von `DefaultHttpContext` aufgehoben. Die Klasse ist jetzt `sealed`. Weitere Informationen finden Sie unter [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504).

Wenn Sie für Komponententests `Mock<DefaultHttpContext>` verwenden, nutzen Sie stattdessen `Mock<HttpContext>`.

Weitere Informationen finden Sie unter [dotnet/aspnetcore#6534](https://github.com/dotnet/aspnetcore/issues/6534).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Klassen konnten von `DefaultHttpContext` abgeleitet werden.

#### <a name="new-behavior"></a>Neues Verhalten

Klassen können nicht mehr von `DefaultHttpContext` abgeleitet werden.

#### <a name="reason-for-change"></a>Grund für die Änderung

Die Erweiterbarkeit wurde anfänglich bereitgestellt, um das Pooling des `HttpContext` zu ermöglichen, sie führt aber zu einer unnötigen Komplexität und hat andere Optimierungen behindert.

#### <a name="recommended-action"></a>Empfohlene Aktion

Wenn Sie in Komponententests `Mock<DefaultHttpContext>` verwenden, nutzen Sie stattdessen `Mock<HttpContext>`.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.AspNetCore.Http.DefaultHttpContext?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Http.DefaultHttpContext`

-->
