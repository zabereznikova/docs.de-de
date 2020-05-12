---
title: Tools für das Portieren zu .NET Core
description: Erfahren Sie mehr über einige der Tools, die Sie zum Portieren zu .NET Core verwenden können.
author: cartermp
ms.date: 05/03/2020
ms.openlocfilehash: d0cf0abf206950beb34556ca3ba7243d8cad241e
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795585"
---
# <a name="tools-to-help-with-porting-to-net-core"></a><span data-ttu-id="c0d14-103">Tools für das Portieren zu .NET Core</span><span class="sxs-lookup"><span data-stu-id="c0d14-103">Tools to help with porting to .NET Core</span></span>

<span data-ttu-id="c0d14-104">Die folgenden, in diesem Artikel aufgeführten Tools können sich beim Portieren als nützlich erweisen:</span><span class="sxs-lookup"><span data-stu-id="c0d14-104">You may find the tools listed in this article helpful when porting:</span></span>

- <span data-ttu-id="c0d14-105">[.NET Portability Analyzer:](../../standard/analyzers/portability-analyzer.md) eine Toolkette, mit der ein Bericht darüber generiert werden kann, wie portabel Ihr Code zwischen .NET Framework und .NET Core ist:</span><span class="sxs-lookup"><span data-stu-id="c0d14-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) - A toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core:</span></span>
  - <span data-ttu-id="c0d14-106">Als [Befehlszeilentool](https://github.com/Microsoft/dotnet-apiport/releases)</span><span class="sxs-lookup"><span data-stu-id="c0d14-106">As a [command-line tool](https://github.com/Microsoft/dotnet-apiport/releases)</span></span>
  - <span data-ttu-id="c0d14-107">Als [Visual Studio-Erweiterung](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)</span><span class="sxs-lookup"><span data-stu-id="c0d14-107">As a [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)</span></span>
- <span data-ttu-id="c0d14-108">[.NET API-Analysetool:](../../standard/analyzers/api-analyzer.md) Hierbei handelt es sich um ein Roslyn-Analysetool, das potenzielle Kompatibilitätsrisiken für C#-APIs auf verschiedenen Plattformen erkennt und Aufrufe an veraltete APIs ermittelt.</span><span class="sxs-lookup"><span data-stu-id="c0d14-108">[.NET API analyzer](../../standard/analyzers/api-analyzer.md) - A Roslyn analyzer that discovers potential compatibility risks for C# APIs on different platforms and detects calls to deprecated APIs.</span></span>
- <span data-ttu-id="c0d14-109">[try-convert](https://www.nuget.org/packages/try-convert/): Ein globales .NET Core-Tool, das ein Projekt oder eine ganze Projektmappe in das .NET SDK konvertieren kann, einschließlich des Verschiebens von Desktop-Apps in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c0d14-109">[try-convert](https://www.nuget.org/packages/try-convert/) - A .NET Core global tool that can convert a project or entire solution to the .NET SDK, including moving desktop apps to .NET Core.</span></span> <span data-ttu-id="c0d14-110">Es wird nicht empfohlen, wenn Sie einen komplizierteren Build eingerichtet haben (z. B. benutzerdefinierte Aufgaben, Ziele oder Importe), und viele Projekttypen kommen dafür nicht infrage, die mit .NET Core nicht kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="c0d14-110">It is not recommended if you have a more complicated build established (such as custom tasks, targets, or imports), and it rejects many project types that are incompatible with .NET Core.</span></span>
