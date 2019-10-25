---
ms.openlocfilehash: e0d0a680915f14c2d33f1864ad5ad05aff3dde5f
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394145"
---
### <a name="http-headernames-constants-changed-to-static-readonly"></a>HTTP: HeaderNames-Konstanten wurden in „static readonly“ geändert.

Ab ASP.NET Core 3.0 Preview 5 wurden die Felder in <xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName> von `const` in `static readonly` geändert.

Weitere Informationen finden Sie unter [aspnet/AspNetCore#9514](https://github.com/aspnet/AspNetCore/issues/9514).

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

#### <a name="recommended-action"></a>Empfohlene Maßnahme

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
