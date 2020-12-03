---
title: 'NETSDK1005 und NETSDK1047: Ziel für eine Objektdatei fehlt'
description: Hier erfahren Sie, wie Sie das Problem beheben, wenn einer Objektdatei ein Ziel fehlt.
author: sfoslund
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1005
- NETSDK1047
ms.openlocfilehash: 207c8b0274c13e7af594e05cfac2a95907f85b81
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717902"
---
# <a name="netsdk1005-and-netsdk1047-asset-file-is-missing-target"></a>NETSDK1005 und NETSDK1047: Ziel für eine Objektdatei fehlt

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1.100 SDK und höhere Versionen

Wenn das .NET SDK den Fehler NETSDK1005 oder NETSDK1047 zurückgibt, fehlen der Objektdatei des Projekts Informationen eines Ihrer Zielframeworks. Dies kann in der Regel behoben werden, indem dafür gesorgt wird, dass eine Wiederherstellung ausgeführt wird und dass der fehlende Zielwert in die `TargetFrameworks`-Eigenschaft Ihres Projekts eingeschlossen wird.

> [!NOTE]
> Bei früheren Builds von .NET 5 Preview 8 bestand ein bekanntes Problem, wenn diese zusammen mit Vorschauversionen von Visual Studio 16.8 verwendet wurden, was zu diesem Fehler führte. Wenn das fehlende Ziel `net5.0-windows7.0` oder `net5.0` ist, überprüfen Sie, ob Sie die jeweils aktuelle Version von Visual Studio und .NET 5 SDK verwenden.
