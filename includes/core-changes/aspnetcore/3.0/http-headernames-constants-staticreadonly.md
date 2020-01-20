---
ms.openlocfilehash: 31e7f84a787d255a474f4c2b1fa3068903dbed52
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901681"
---
### <a name="http-headernames-constants-changed-to-static-readonly"></a>HTTP: HeaderNames-Konstanten wurden in „static readonly“ geändert.

Ab ASP.NET Core 3.0 Preview 5 wurden die Felder in <xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName> von `const` in `static readonly` geändert.

Weitere Informationen finden Sie unter [dotnet/aspnetcore#9514](https://github.com/dotnet/aspnetcore/issues/9514).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Diese Felder waren `const`.

#### <a name="new-behavior"></a>Neues Verhalten

Diese Felder sind nun `static readonly`.

#### <a name="reason-for-change"></a>Grund für die Änderung

Die Änderung hat folgende Gründe:

* Sie verhindert, dass die Werte über Assemblygrenzen hinweg eingebettet werden, sodass bei Bedarf Korrekturen an Werten möglich sind.
* Sie ermöglicht schnellere Überprüfungen der Verweisgleichheit.

#### <a name="recommended-action"></a>Empfohlene Aktion

Kompilieren Sie mit 3.0 neu. Sie müssen Quellcode ändern, der diese Felder auf folgende Weise verwendet:

* Als unzulässiges Attributargument
* Als einen `case` in einer `switch`-Anweisung
* Beim Definieren einer anderen `const`

Um diesen Breaking Change zu umgehen, verwenden Sie selbst definierte Headernamenkonstanten oder Zeichenfolgenliterale.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.Net.Http.Headers.HeaderNames`

-->
