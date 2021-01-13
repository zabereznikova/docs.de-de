---
title: 'NETSDK1005 und NETSDK1047: Ziel für eine Objektdatei fehlt'
description: Hier erfahren Sie, wie Sie das Problem beheben, wenn einer Objektdatei ein Ziel fehlt.
author: sfoslund
ms.topic: error-reference
ms.date: 12/17/2020
f1_keywords:
- NETSDK1005
- NETSDK1047
ms.openlocfilehash: e3e7389adf6a9a715d44661a5f7cbae5efe299e4
ms.sourcegitcommit: 4b79862c5b41fbd86cf38f926f6a49516059f6f2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/18/2020
ms.locfileid: "97678175"
---
# <a name="netsdk1005-and-netsdk1047-asset-file-is-missing-target"></a>NETSDK1005 und NETSDK1047: Ziel für eine Objektdatei fehlt

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1.100 SDK und höhere Versionen

Wenn das .NET SDK den Fehler NETSDK1005 oder NETSDK1047 zurückgibt, fehlen der Objektdatei des Projekts Informationen eines Ihrer Zielframeworks. NuGet schreibt eine Datei mit dem Namen *project.assets.json* in den Ordner *obj*. Das .NET SDK verwendet diese Datei, um Informationen über Pakete zu erhalten, die es an den Compiler übergibt. In .NET 5 hat NuGet ein neues Feld namens `TargetFrameworkAlias` hinzugefügt. Daher generieren frühere Versionen von MSBuild und NuGet eine Ressourcendatei ohne das neue Feld. Weitere Informationen finden Sie unter [Fehler NETSDK1005](https://developercommunity.visualstudio.com/content/problem/1248649/error-netsdk1005-assets-file-projectassetsjson-doe.html).

Im Folgenden sind einige Aktionen aufgeführt, mit denen Sie den Fehler möglicherweise beheben können:

* Stellen Sie sicher, dass Sie Version 16.8 oder höher von MSBuild und Version 5.8 oder höher von NuGet verwenden, und stellen Sie das Projekt nach dem Aktualisieren Ihrer Tools wieder her. Wenn Sie Version 5.8 oder höher von NuGet verwenden, sollten Sie Version 16.8 oder höher von Visual Studio 2019, Version 16.8 oder höher von MSBuild und das .NET 5.0 SDK oder höher verwenden.

* Wenn der Fehler beim Kompilieren eines Projekts in Visual Studio 2019 zum ersten Mal nach der Installation von Version 16.8 oder nach der Änderung des Zielframeworks des Projekts auftritt, kompilieren Sie das Projekt ein zweites Mal.

* Löschen Sie den Ordner *obj* vor dem Kompilieren des Projekts.

* Stellen Sie sicher, dass der fehlende Zielwert in der Eigenschaft `TargetFrameworks` Ihres Projekts enthalten ist.
