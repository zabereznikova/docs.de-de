---
title: Tools für das Portieren zu .NET Core
description: Erfahren Sie mehr über einige der Tools, die Sie zum Portieren zu .NET Core verwenden können.
author: cartermp
ms.date: 05/03/2020
ms.openlocfilehash: b8678ec72fe5d910d5f8cff4768106e7496f9276
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406127"
---
# <a name="tools-to-help-with-porting-to-net-core"></a><span data-ttu-id="9c154-103">Tools für das Portieren zu .NET Core</span><span class="sxs-lookup"><span data-stu-id="9c154-103">Tools to help with porting to .NET Core</span></span>

<span data-ttu-id="9c154-104">Die folgenden, in diesem Artikel aufgeführten Tools können sich beim Portieren als nützlich erweisen:</span><span class="sxs-lookup"><span data-stu-id="9c154-104">You may find the tools listed in this article helpful when porting:</span></span>

- <span data-ttu-id="9c154-105">[.NET Portability Analyzer:](../../standard/analyzers/portability-analyzer.md) eine Toolkette, mit der ein Bericht darüber generiert werden kann, wie portabel Ihr Code zwischen .NET Framework und .NET Core ist:</span><span class="sxs-lookup"><span data-stu-id="9c154-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) - A toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core:</span></span>
  - <span data-ttu-id="9c154-106">Als [Befehlszeilentool](https://github.com/Microsoft/dotnet-apiport/releases)</span><span class="sxs-lookup"><span data-stu-id="9c154-106">As a [command-line tool](https://github.com/Microsoft/dotnet-apiport/releases)</span></span>
  - <span data-ttu-id="9c154-107">Als [Visual Studio-Erweiterung](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)</span><span class="sxs-lookup"><span data-stu-id="9c154-107">As a [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)</span></span>
- <span data-ttu-id="9c154-108">[Das Analysetool für Plattformkompatibilität](../../standard/analyzers/platform-compat-analyzer.md): ein Roslyn-Analysetool, das Entwicklern mitteilt, wenn sie plattformspezifische APIs von Aufrufsites verwenden, bei denen die API möglicherweise nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="9c154-108">[Platform compatibility analyzer](../../standard/analyzers/platform-compat-analyzer.md) - A Roslyn analyzer that informs developers when they use platform-specific APIs from call sites where the API might not be available.</span></span>
- <span data-ttu-id="9c154-109">[Das .NET API-Analysetool](../../standard/analyzers/api-analyzer.md): ein Roslyn-Analyzer, mit dem in plattformübergreifenden Apps und Bibliotheken Probleme mit der Plattformkompatibilität erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="9c154-109">[.NET API analyzer](../../standard/analyzers/api-analyzer.md) - A Roslyn analyzer that can help detect platform compatibility issues in cross-platform apps and libraries.</span></span>
- <span data-ttu-id="9c154-110">[try-convert](https://www.nuget.org/packages/try-convert/): Ein globales .NET Core-Tool, das ein Projekt oder eine ganze Projektmappe in das .NET SDK konvertieren kann, einschließlich des Verschiebens von Desktop-Apps in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9c154-110">[try-convert](https://www.nuget.org/packages/try-convert/) - A .NET Core global tool that can convert a project or entire solution to the .NET SDK, including moving desktop apps to .NET Core.</span></span> <span data-ttu-id="9c154-111">Es wird nicht empfohlen, wenn Sie einen komplizierteren Build eingerichtet haben (z. B. benutzerdefinierte Aufgaben, Ziele oder Importe), und viele Projekttypen kommen dafür nicht infrage, die mit .NET Core nicht kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="9c154-111">It is not recommended if you have a more complicated build established (such as custom tasks, targets, or imports), and it rejects many project types that are incompatible with .NET Core.</span></span>
