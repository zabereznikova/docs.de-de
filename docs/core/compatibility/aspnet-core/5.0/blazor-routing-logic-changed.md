---
title: 'Breaking Change: Blazor: Änderungen der Routinglogik in Blazor-Apps'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „Blazor: Änderungen der Routinglogik in Blazor-Apps'
author: scottaddie
ms.author: scaddie
ms.date: 12/14/2020
ms.openlocfilehash: 4ab8289565c88b17eb204a11724bb12a09b033c2
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513506"
---
# <a name="blazor-route-precedence-logic-changed-in-blazor-apps"></a>Blazor: Logik für die Routingrangfolge in Blazor-Apps geändert

Ein Fehler in der Blazor-Routingimplementierung hat die Bestimmung der Rangfolge von Routen beeinträchtigt. Dieser Fehler betraf Catch-All-Routen oder Routen mit optionalen Parametern in Blazor-Apps.

## <a name="version-introduced"></a>Eingeführt in Version

5.0.1

## <a name="old-behavior"></a>Altes Verhalten

Durch das fehlerhafte Verhalten werden Routen mit niedrigerem Rang gegenüber Routen mit höherem Rang bevorzugt berücksichtigt und abgeglichen. Beispielsweise wird die Route `{*slug}` vor `/customer/{id}` abgeglichen.

## <a name="new-behavior"></a>Neues Verhalten

Das aktuelle Verhalten stimmt stärker mit dem Routingverhalten überein, das in ASP.NET Core-Apps definiert ist. Das Framework bestimmt zuerst die Rangfolge der Routen für die einzelnen Segmente. Die Länge der Route wird nur als zweites Kriterium verwendet, wenn zwei Routen denselben Rang haben.

## <a name="reason-for-change"></a>Grund für die Änderung

Das ursprüngliche Verhalten wird in der Implementierung als Fehler betrachtet. Ziel ist es, dass sich das Routingsystem in Blazor-Apps genauso verhält wie im Rest von ASP.NET Core.

## <a name="recommended-action"></a>Empfohlene Maßnahme

Wenn Sie ein Upgrade von früheren Versionen von Blazor auf Version 5.x durchführen, sollten Sie das Attribut `PreferExactMatches` für die Komponente `Router` verwenden. Dieses Attribut kann verwendet werden, um das richtige Verhalten zu aktivieren. Beispiel:

```razor
<Router AppAssembly="@typeof(Program).Assembly" PreferExactMatches="true">
```

Wenn `PreferExactMatches` auf `true` festgelegt ist, bevorzugt die Routenzuordnung exakte Übereinstimmungen gegenüber Platzhaltern.

## <a name="affected-apis"></a>Betroffene APIs

Keine

<!--

## Category

ASP.NET Core

## Affected APIs

Not detectable via API analysis

-->
