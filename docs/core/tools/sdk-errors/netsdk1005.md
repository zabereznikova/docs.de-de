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
# <a name="netsdk1005-and-netsdk1047-asset-file-is-missing-target"></a><span data-ttu-id="1d875-103">NETSDK1005 und NETSDK1047: Ziel für eine Objektdatei fehlt</span><span class="sxs-lookup"><span data-stu-id="1d875-103">NETSDK1005 and NETSDK1047: Asset file is missing target</span></span>

<span data-ttu-id="1d875-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1.100 SDK und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="1d875-104">**This article applies to:** ✔️ .NET Core 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="1d875-105">Wenn das .NET SDK den Fehler NETSDK1005 oder NETSDK1047 zurückgibt, fehlen der Objektdatei des Projekts Informationen eines Ihrer Zielframeworks.</span><span class="sxs-lookup"><span data-stu-id="1d875-105">When the .NET SDK issues error NETSDK1005 or NETSDK1047, the project's assets file is missing information on one of your target frameworks.</span></span> <span data-ttu-id="1d875-106">NuGet schreibt eine Datei mit dem Namen *project.assets.json* in den Ordner *obj*. Das .NET SDK verwendet diese Datei, um Informationen über Pakete zu erhalten, die es an den Compiler übergibt.</span><span class="sxs-lookup"><span data-stu-id="1d875-106">NuGet writes a file named *project.assets.json* in the *obj* folder, and the .NET SDK uses it to get information about packages to pass into the compiler.</span></span> <span data-ttu-id="1d875-107">In .NET 5 hat NuGet ein neues Feld namens `TargetFrameworkAlias` hinzugefügt. Daher generieren frühere Versionen von MSBuild und NuGet eine Ressourcendatei ohne das neue Feld.</span><span class="sxs-lookup"><span data-stu-id="1d875-107">In .NET 5, NuGet added a new field named `TargetFrameworkAlias`, so earlier versions of MSBuild or NuGet generate an assets file without the new field.</span></span> <span data-ttu-id="1d875-108">Weitere Informationen finden Sie unter [Fehler NETSDK1005](https://developercommunity.visualstudio.com/content/problem/1248649/error-netsdk1005-assets-file-projectassetsjson-doe.html).</span><span class="sxs-lookup"><span data-stu-id="1d875-108">For more information, see [error NETSDK1005](https://developercommunity.visualstudio.com/content/problem/1248649/error-netsdk1005-assets-file-projectassetsjson-doe.html).</span></span>

<span data-ttu-id="1d875-109">Im Folgenden sind einige Aktionen aufgeführt, mit denen Sie den Fehler möglicherweise beheben können:</span><span class="sxs-lookup"><span data-stu-id="1d875-109">Here are some actions you can take that may resolve the error:</span></span>

* <span data-ttu-id="1d875-110">Stellen Sie sicher, dass Sie Version 16.8 oder höher von MSBuild und Version 5.8 oder höher von NuGet verwenden, und stellen Sie das Projekt nach dem Aktualisieren Ihrer Tools wieder her.</span><span class="sxs-lookup"><span data-stu-id="1d875-110">Make sure that you're using MSBuild version 16.8 or later and NuGet version 5.8 or later, and restore the project after updating your tools.</span></span> <span data-ttu-id="1d875-111">Wenn Sie Version 5.8 oder höher von NuGet verwenden, sollten Sie Version 16.8 oder höher von Visual Studio 2019, Version 16.8 oder höher von MSBuild und das .NET 5.0 SDK oder höher verwenden.</span><span class="sxs-lookup"><span data-stu-id="1d875-111">When you're using NuGet version 5.8 or later, you should be using Visual Studio 2019 version 16.8 or later, MSBuild version 16.8 or later, and .NET 5.0 SDK or later.</span></span>

* <span data-ttu-id="1d875-112">Wenn der Fehler beim Kompilieren eines Projekts in Visual Studio 2019 zum ersten Mal nach der Installation von Version 16.8 oder nach der Änderung des Zielframeworks des Projekts auftritt, kompilieren Sie das Projekt ein zweites Mal.</span><span class="sxs-lookup"><span data-stu-id="1d875-112">If you get the error while building a project in Visual Studio 2019 for the first time after installing version 16.8 or after changing the project's target framework, build the project a second time.</span></span>

* <span data-ttu-id="1d875-113">Löschen Sie den Ordner *obj* vor dem Kompilieren des Projekts.</span><span class="sxs-lookup"><span data-stu-id="1d875-113">Delete the *obj* folder before building the project.</span></span>

* <span data-ttu-id="1d875-114">Stellen Sie sicher, dass der fehlende Zielwert in der Eigenschaft `TargetFrameworks` Ihres Projekts enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="1d875-114">Make sure that the missing target value is included in the `TargetFrameworks` property of your project.</span></span>
