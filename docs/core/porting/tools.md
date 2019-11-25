---
title: Tools für das Portieren zu .NET Core
description: Erfahren Sie mehr über einige der Tools, die Sie zum Portieren zu .NET Core verwenden können.
author: cartermp
ms.author: mairaw
ms.date: 12/07/2018
ms.openlocfilehash: 0478719617741946768cfe8e220a1dd402667998
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72521347"
---
# <a name="tools-to-help-with-porting-to-net-core"></a><span data-ttu-id="95551-103">Tools für das Portieren zu .NET Core</span><span class="sxs-lookup"><span data-stu-id="95551-103">Tools to help with porting to .NET Core</span></span>

<span data-ttu-id="95551-104">Die folgenden, in diesem Artikel aufgeführten Tools können sich beim Portieren als nützlich erweisen:</span><span class="sxs-lookup"><span data-stu-id="95551-104">You may find the tools listed in this article helpful when porting:</span></span>

- <span data-ttu-id="95551-105">[.NET Portability Analyzer:](../../standard/analyzers/portability-analyzer.md) eine Toolkette, mit der ein Bericht darüber generiert werden kann, wie portabel Ihr Code zwischen .NET Framework und .NET Core ist:  Als [Befehlszeilentool](https://github.com/Microsoft/dotnet-apiport/releases) oder als [Visual Studio-Erweiterung](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)</span><span class="sxs-lookup"><span data-stu-id="95551-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) - A toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core:  As a [command-line tool](https://github.com/Microsoft/dotnet-apiport/releases) As a [Visual Studio Extension](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)</span></span>
- <span data-ttu-id="95551-106">[.NET API-Analysetool:](../../standard/analyzers/api-analyzer.md) Hierbei handelt es sich um ein Roslyn-Analysetool, das potenzielle Kompatibilitätsrisiken für C#-APIs auf verschiedenen Plattformen erkennt und Aufrufe an veraltete APIs ermittelt.</span><span class="sxs-lookup"><span data-stu-id="95551-106">[.NET API analyzer](../../standard/analyzers/api-analyzer.md) - A Roslyn analyzer that discovers potential compatibility risks for C# APIs on different platforms and detects calls to deprecated APIs.</span></span>

<span data-ttu-id="95551-107">Darüber hinaus können Sie mit dem Tool [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017) versuchen, kleinere Lösungen oder einzelne Projekte auf das .NET Core-Projektdateiformat zu portieren.</span><span class="sxs-lookup"><span data-stu-id="95551-107">Additionally, you can attempt to port smaller solutions or individual projects to the .NET Core project file format with the [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017) tool.</span></span>

> [!WARNING] 
> <span data-ttu-id="95551-108">CsprojToVs2017 ist ein Drittanbietertool.</span><span class="sxs-lookup"><span data-stu-id="95551-108">CsprojToVs2017 is a third-party tool.</span></span> <span data-ttu-id="95551-109">Es kann nicht garantiert werden, dass das Tool für all Ihre Projekte funktioniert, und es kann zu subtilen Änderungen bei Verhalten kommen, von dem Sie abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="95551-109">There is no guarantee that it will work for all of your projects, and it may cause subtle changes in behavior that you depend on.</span></span> <span data-ttu-id="95551-110">CsprojToVs2017 sollte als _Ausgangspunkt_ verwendet werden, um grundlegende Elemente zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="95551-110">CsprojToVs2017 should be used as a _starting point_ that automates the basic things that can be automated.</span></span> <span data-ttu-id="95551-111">Es handelt sich nicht um ein garantierte Lösung zum Migrieren von Projektdateiformaten.</span><span class="sxs-lookup"><span data-stu-id="95551-111">It is not a guaranteed solution to migrating project file formats.</span></span>
