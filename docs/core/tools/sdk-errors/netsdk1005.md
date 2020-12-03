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
# <a name="netsdk1005-and-netsdk1047-asset-file-is-missing-target"></a><span data-ttu-id="35de8-103">NETSDK1005 und NETSDK1047: Ziel für eine Objektdatei fehlt</span><span class="sxs-lookup"><span data-stu-id="35de8-103">NETSDK1005 and NETSDK1047: Asset file is missing target</span></span>

<span data-ttu-id="35de8-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1.100 SDK und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="35de8-104">**This article applies to:** ✔️ .NET Core 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="35de8-105">Wenn das .NET SDK den Fehler NETSDK1005 oder NETSDK1047 zurückgibt, fehlen der Objektdatei des Projekts Informationen eines Ihrer Zielframeworks.</span><span class="sxs-lookup"><span data-stu-id="35de8-105">When the .NET SDK issues error NETSDK1005 or NETSDK1047, the project's assets file is missing information on one of your target frameworks.</span></span> <span data-ttu-id="35de8-106">Dies kann in der Regel behoben werden, indem dafür gesorgt wird, dass eine Wiederherstellung ausgeführt wird und dass der fehlende Zielwert in die `TargetFrameworks`-Eigenschaft Ihres Projekts eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="35de8-106">This can usually be fixed by ensuring that restore is run and that the missing target value is included in the `TargetFrameworks` property of your project.</span></span>

> [!NOTE]
> <span data-ttu-id="35de8-107">Bei früheren Builds von .NET 5 Preview 8 bestand ein bekanntes Problem, wenn diese zusammen mit Vorschauversionen von Visual Studio 16.8 verwendet wurden, was zu diesem Fehler führte.</span><span class="sxs-lookup"><span data-stu-id="35de8-107">There was a known issue with early builds of .NET 5 preview 8 when used with versions of Visual Studio 16.8 previews which resulted in this error.</span></span> <span data-ttu-id="35de8-108">Wenn das fehlende Ziel `net5.0-windows7.0` oder `net5.0` ist, überprüfen Sie, ob Sie die jeweils aktuelle Version von Visual Studio und .NET 5 SDK verwenden.</span><span class="sxs-lookup"><span data-stu-id="35de8-108">Specifically, if the missing target is `net5.0-windows7.0` or `net5.0`, ensure that you have updated to the latest versions of Visual Studio and the .NET 5 SDK.</span></span>
