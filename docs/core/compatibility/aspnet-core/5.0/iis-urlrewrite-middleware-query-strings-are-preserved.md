---
title: 'Breaking Change: IIS: Abfragezeichenfolgen für die UrlRewrite-Middleware werden beibehalten'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „IIS: Abfragezeichenfolgen für die UrlRewrite-Middleware werden beibehalten'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: e4d1ecba62f9e43e7377aba1138968f15f8895d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759202"
---
# <a name="iis-urlrewrite-middleware-query-strings-are-preserved"></a>IIS: Abfragezeichenfolgen für die UrlRewrite-Middleware werden beibehalten

Ein Fehler bei der IIS-UrlRewrite-Middleware hat verhindert, dass die Abfragezeichenfolge in Neuschreibungsregeln beibehalten wird. Dieser Fehler wurde behoben, um Konsistenz mit dem Verhalten des IIS-UrlRewrite-Moduls sicherzustellen.

Weitere Informationen finden Sie im Issue [dotnet/aspnetcore#22972](https://github.com/dotnet/aspnetcore/issues/22972).

## <a name="version-introduced"></a>Eingeführt in Version

ASP.NET Core 5.0 Preview 7

## <a name="old-behavior"></a>Altes Verhalten

Sehen Sie sich die folgende Neuschreibungsregel an:

```xml
<rule name="MyRule" stopProcessing="true">
  <match url="^about" />
  <action type="Redirect" url="/contact" redirectType="Temporary" appendQueryString="true" />
</rule>
```

Die obige Regel fügt die Abfragezeichenfolge nicht an. Bei einem URI wie `/about?id=1` findet eine Weiterleitung zu `/contact` anstelle von `/contact?id=1` statt. Außerdem ist das Attribut `appendQueryString` standardmäßig auf `true` festgelegt.

## <a name="new-behavior"></a>Neues Verhalten

Die Abfragezeichenfolge wird beibehalten. Der URI aus dem Beispiel unter [Altes Verhalten](#old-behavior) wäre dann `/contact?id=1`.

## <a name="reason-for-change"></a>Grund für die Änderung

Das alte Verhalten entsprach nicht dem des IIS-UrlRewrite-Moduls. Damit ein Übertragen zwischen Middleware und Modul unterstützt wird, soll ein konsistentes Verhalten gewährleistet sein.

## <a name="recommended-action"></a>Empfohlene Aktion

Wenn Sie das Entfernen der Abfragezeichenfolge als Verhalten bevorzugen, legen Sie im `action`-Element `appendQueryString="false"` fest.

## <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`Overload:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite`

-->
