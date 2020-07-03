---
ms.openlocfilehash: 29908ed916690e67db3cc5d72ebe1b1c6aea45c6
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325247"
---
### <a name="iis-urlrewrite-middleware-query-strings-are-preserved"></a>IIS: Abfragezeichenfolgen für die UrlRewrite-Middleware werden beibehalten

Ein Fehler bei der IIS-UrlRewrite-Middleware hat verhindert, dass die Abfragezeichenfolge in Neuschreibungsregeln beibehalten wird. Dieser Fehler wurde behoben, um Konsistenz mit dem Verhalten des IIS-UrlRewrite-Moduls sicherzustellen.

Weitere Informationen finden Sie im Issue [dotnet/aspnetcore#22972](https://github.com/dotnet/aspnetcore/issues/22972).

#### <a name="version-introduced"></a>Eingeführt in Version

ASP.NET Core 5.0 Preview 7

#### <a name="old-behavior"></a>Altes Verhalten

Sehen Sie sich die folgende Neuschreibungsregel an:

```xml
<rule name="MyRule" stopProcessing="true">
  <match url="^about" />
  <action type="Redirect" url="/contact" redirectType="Temporary" appendQueryString="true" />
</rule>
```

Die obige Regel fügt die Abfragezeichenfolge nicht an. Bei einem URI wie `/about?id=1` findet eine Weiterleitung zu `/contact` anstelle von `/contact?id=1` statt. Außerdem ist das Attribut `appendQueryString` standardmäßig auf `true` festgelegt.

#### <a name="new-behavior"></a>Neues Verhalten

Die Abfragezeichenfolge wird beibehalten. Der URI aus dem Beispiel unter [Altes Verhalten](#old-behavior) wäre dann `/contact?id=1`.

#### <a name="reason-for-change"></a>Grund für die Änderung

Das alte Verhalten entsprach nicht dem des IIS-UrlRewrite-Moduls. Damit ein Übertragen zwischen Middleware und Modul unterstützt wird, soll ein konsistentes Verhalten gewährleistet sein.

#### <a name="recommended-action"></a>Empfohlene Aktion

Wenn Sie das Entfernen der Abfragezeichenfolge als Verhalten bevorzugen, legen Sie im `action`-Element `appendQueryString="false"` fest.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite`

-->
