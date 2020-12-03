---
title: 'Breaking Change: Behavior Change von PublishDepsFilePath'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den die MSBuild-Eigenschaft „PublishDepsFilePath“ bei Einzeldateianwendungen leer ist.
ms.date: 09/17/2020
ms.openlocfilehash: 70631beff31aa3388e59f3b79875ef437351451a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759570"
---
# <a name="publishdepsfilepath-behavior-change"></a>Behavior Change von PublishDepsFilePath

Die MSBuild-Eigenschaft `PublishDepsFilePath` ist für Anwendungen mit nur einer Datei leer. Zusätzlich darf bei Anwendungen, die nicht nur aus einer einzelnen Datei bestehen, die Datei *deps.json* erst später im Build in das Ausgabeverzeichnis kopiert werden.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="change-description"></a>Änderungsbeschreibung

In früheren .NET-Versionen ist die MSBuild-Eigenschaft `PublishDepsFilePath` der Pfad zur Datei *deps.json* der App im Ausgabeverzeichnis für Anwendungen, die nicht nur aus einer Datei bestehen, und ein Pfad im Zwischenverzeichnis für Anwendungen mit nur einer Datei.

Ab .NET 5.0 ist `PublishDepsFilePath` bei Anwendungen mit nur einer Datei leer. Die neue Eigenschaft `IntermediateDepsFilePath` gibt den Speicherort von *deps.json* im Zwischenverzeichnis an. Zusätzlich darf bei Anwendungen, die nicht nur aus einer einzelnen Datei bestehen, die Datei *deps.json* erst später im Build in das Ausgabeverzeichnis (d. h. den von `PublishDepsFilePath` angegebenen Pfad) kopiert werden.

## <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung ist aus mehreren Gründen erfolgt:

- Aufgrund eines Refactorings der Veröffentlichungslogik zur Unterstützung [verbesserter Apps mit nur einer Datei](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md) in .NET 5.

- Um sich bei Apps mit nur einer Datei vor Zielen zu schützen, die versuchen, die Datei *deps.json* neu zu schreiben, nachdem die Datei *deps.json* bereits gebündelt wurde, sodass die Anwendung nicht unbemerkt beeinträchtigt wird. Aus diesem Grund ist `PublishDepsFilePath` für Anwendungen mit nur einer Datei leer.

## <a name="recommended-action"></a>Empfohlene Maßnahme

Ziele, die die Datei *deps.json* neu schreiben, sollten dies im Allgemeinen mit der Eigenschaft `IntermediateDepsFilePath` tun.

## <a name="affected-apis"></a>Betroffene APIs

Nicht zutreffend

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
