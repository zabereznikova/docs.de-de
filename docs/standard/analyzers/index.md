---
title: "Die auf Roslyn basierenden Analysetools – .NET"
description: Erfahren Sie mehr zu auf Roslyn basierenden Analysetools, die Probleme erkennen und Problembehebungen vorschlagen.
keywords: .NET, .NET Core
author: billwagner
ms.author: billwagner
ms.date: 01/24/2018
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.openlocfilehash: 8c6524716ba403bc426df8dc33e64b8b2934d3d7
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2018
---
# <a name="the-roslyn-based-analyzers"></a><span data-ttu-id="0e8d1-104">Die auf Roslyn basierenden Analysetools</span><span class="sxs-lookup"><span data-stu-id="0e8d1-104">The Roslyn based Analyzers</span></span>

<span data-ttu-id="0e8d1-105">Auf Roslyn basierende Analysetools verwenden das .NET Compiler SDK (Roslyn-APIs), um den Quellcode Ihres Projekts zu analysieren, um Probleme zu finden und Korrekturen vorzuschlagen.</span><span class="sxs-lookup"><span data-stu-id="0e8d1-105">Roslyn-based analyzers use the .NET Compiler SDK (Roslyn APIs) to analyze your project's source code to find issues and suggest corrections.</span></span> <span data-ttu-id="0e8d1-106">Unterschiedliche Analysetools suchen nach verschiedenen Klassen von Problemen, angefangen bei Methoden, die wahrscheinlich Fehler verursachen, bis hin zu Sicherheitsaspekten bei der API-Kompatibilität.</span><span class="sxs-lookup"><span data-stu-id="0e8d1-106">Different analyzers look for different classes of issues, ranging from practices that are likely to cause bugs to security concerns to API compatibility.</span></span>

<span data-ttu-id="0e8d1-107">Auf Roslyn basierende Analysetools funktionieren sowohl interaktiv als auch während der Builderstellung.</span><span class="sxs-lookup"><span data-stu-id="0e8d1-107">Roslyn-based analyzers work both interactively and during builds.</span></span> <span data-ttu-id="0e8d1-108">Das Analysetool bietet in Visual Studio oder in Befehlszeilenbuilds unterschiedliche Hilfen.</span><span class="sxs-lookup"><span data-stu-id="0e8d1-108">The analyzer provides different guidance when in Visual Studio or in command-line builds.</span></span>

<span data-ttu-id="0e8d1-109">Während Sie Code in Visual Studio bearbeiten, werden die Analysetools bei der Durchführung von Änderungen ausgeführt und erfassen dabei mögliche Fehler, sobald Sie Code erstellen, der Probleme verursacht.</span><span class="sxs-lookup"><span data-stu-id="0e8d1-109">While you edit code in Visual Studio, the analyzers run as you make changes, catching possible issues as soon as you create code that trigger concerns.</span></span> <span data-ttu-id="0e8d1-110">Probleme werden durch Wellenlinien unter einem Problem markiert.</span><span class="sxs-lookup"><span data-stu-id="0e8d1-110">Any issues are highlighted with squiggles under any issue.</span></span> <span data-ttu-id="0e8d1-111">In Visual Studio wird eine Glühbirne angezeigt. Wenn Sie darauf klicken, schlägt das Analysetool mögliche Problembehebungen vor.</span><span class="sxs-lookup"><span data-stu-id="0e8d1-111">Visual Studio displays a light bulb, and when you click on it the analyzer will suggest possible fixes for that issue.</span></span> <span data-ttu-id="0e8d1-112">Wenn Sie das Projekt erstellen – entweder in Visual Studio oder über die Befehlszeile – wird der gesamte Quellcode analysiert, und das Analysetool stellt eine vollständige Liste möglicher Probleme bereit.</span><span class="sxs-lookup"><span data-stu-id="0e8d1-112">When you build the project, either in Visual Studio or from the command line, all the source code is analyzed and the analyzer provides a full list of potential issues.</span></span> <span data-ttu-id="0e8d1-113">Die folgende Abbildung zeigt ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="0e8d1-113">The following figure shows one example.</span></span>

![Probleme, die vom Framework Analyzer gemeldet werden.](./media/framework-analyzers-2.png)

<span data-ttu-id="0e8d1-115">Die auf Roslyn basierenden Analysetools melden mögliche Probleme anhand des Schweregrads des Problems als Fehler, Warnungen oder Informationen.</span><span class="sxs-lookup"><span data-stu-id="0e8d1-115">Roslyn-based analyzers report potential issues as errors, warnings, or information based on the severity of the issue.</span></span>

<span data-ttu-id="0e8d1-116">Sie installieren auf Roslyn basierende Analysetools in Ihrem Projekt als NuGet-Pakete.</span><span class="sxs-lookup"><span data-stu-id="0e8d1-116">You install Roslyn-based analyzers as NuGet packages in your project.</span></span> <span data-ttu-id="0e8d1-117">Das konfigurierte Analysetool sowie Einstellungen für jedes Analysetool werden wiederhergestellt und auf einem beliebigen Computer eines Entwicklers für diese Projekt ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0e8d1-117">The configured analyzers and any settings for each analyzer are restored and run on any developer's machine for that project.</span></span>

> [!NOTE]
> <span data-ttu-id="0e8d1-118">Die Benutzererfahrung für auf Roslyn basierenden Analysetools unterscheidet sich von den Codeanalysebibliotheken, wie etwa die älteren Versionen von FxCop und die Sicherheitsanalysetools.</span><span class="sxs-lookup"><span data-stu-id="0e8d1-118">The user experience for Roslyn-based analyzers is different than that of the Code Analysis libraries like the older versions of FxCop and the security analysis tools.</span></span>  <span data-ttu-id="0e8d1-119">Sie müssen nicht explizit die auf Roslyn basierenden Analysetools ausführen.</span><span class="sxs-lookup"><span data-stu-id="0e8d1-119">You don't need to explicitly run the Roslyn-based analyzers.</span></span> <span data-ttu-id="0e8d1-120">Es ist nicht erforderlich, das Menüelemente„Codeanalyse ausführen“ in Visual Studio im Menü „Analysieren“ zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0e8d1-120">There's no need to use the "Run Code Analysis" menu items on the "Analyze" menu in Visual Studio.</span></span> <span data-ttu-id="0e8d1-121">Auf Roslyn basierende Analysetools werden asynchron ausgeführt, während Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="0e8d1-121">Roslyn-based analyzers run asychronously as you work.</span></span> 

## <a name="more-information-on-specific-analyzers"></a><span data-ttu-id="0e8d1-122">Weitere Informationen zu bestimmten Analysetools</span><span class="sxs-lookup"><span data-stu-id="0e8d1-122">More information on specific analyzers</span></span>

<span data-ttu-id="0e8d1-123">In diesem Abschnitt werden die folgenden Analysetools behandelt:</span><span class="sxs-lookup"><span data-stu-id="0e8d1-123">The following analyzers are covered in this section:</span></span>

<span data-ttu-id="0e8d1-124">[API Analyzer](api-analyzer.md): Dieses Analysetool untersucht Ihren Code auf potentielle Kompatibilitätsrisiken oder die Verwendung veralteter APIs.</span><span class="sxs-lookup"><span data-stu-id="0e8d1-124">[API Analyzer](api-analyzer.md): This analyzer examines your code for potential compatibility risks or uses of deprecated APIs.</span></span>    
<span data-ttu-id="0e8d1-125">[Framework Analyzer](framework-analyzer.md): Dieses Analysetool untersucht Ihren Code, um sicherzustellen, dass dieser die Richtlinien für .NET Framework-Anwendungen befolgt.</span><span class="sxs-lookup"><span data-stu-id="0e8d1-125">[Framework Analyzer](framework-analyzer.md): This analyzer examines your code to ensure it follows the guidelines for .NET Framework applications.</span></span> <span data-ttu-id="0e8d1-126">Diese Regeln umfassen mehrere sicherheitsbasierte Empfehlungen.</span><span class="sxs-lookup"><span data-stu-id="0e8d1-126">These rules include several security-based recommendations.</span></span>
