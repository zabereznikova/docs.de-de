---
title: Portieren von .NET Framework auf .NET Core
description: "Verstehen Sie den Portiervorgang und entdecken Sie Tools, die Ihnen beim Portieren eines .NET Framework-Projekts zu .NET Core behilflich sein können."
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 00d00d38-99af-44f4-a75f-defcd9729dc5
ms.translationtype: HT
ms.sourcegitcommit: 3155295489e1188640dae5aa5bf9fdceb7480ed6
ms.openlocfilehash: 4fc68a3dbdec634d8e92a066a46939ba19c65db7
ms.contentlocale: de-de
ms.lasthandoff: 08/05/2017

---

# <a name="porting-to-net-core-from-net-framework"></a><span data-ttu-id="6ee63-104">Portieren von .NET Framework auf .NET Core</span><span class="sxs-lookup"><span data-stu-id="6ee63-104">Porting to .NET Core from .NET Framework</span></span>

<span data-ttu-id="6ee63-105">Wenn Code auf .NET Framework ausgeführt wird, sind Sie vielleicht interessiert daran, Ihren Code auf .NET Core 1.0 auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6ee63-105">If you've got code running on the .NET Framework, you may be interested in running your code on .NET Core 1.0.</span></span>  <span data-ttu-id="6ee63-106">Dieser Artikel enthält eine Übersicht über den Portiervorgang und eine Liste der Tools, die während des Portierens auf .NET Core hilfreich sein können.</span><span class="sxs-lookup"><span data-stu-id="6ee63-106">This article covers an overview of the porting process and a list of the tools you may find helpful when porting to .NET Core.</span></span>

## <a name="overview-of-the-porting-process"></a><span data-ttu-id="6ee63-107">Übersicht über den Portiervorgang</span><span class="sxs-lookup"><span data-stu-id="6ee63-107">Overview of the Porting Process</span></span>

<span data-ttu-id="6ee63-108">Die empfohlene Vorgehensweise für das Portieren ist in den folgenden Schritten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6ee63-108">The recommended process for porting follows the following series of steps.</span></span>  <span data-ttu-id="6ee63-109">Jeder Teil dieses Vorgangs wird in weiteren Artikeln genauer erläutert.</span><span class="sxs-lookup"><span data-stu-id="6ee63-109">Each of these parts of the process are covered in more detail in further articles.</span></span>

1. <span data-ttu-id="6ee63-110">Identifizieren Sie sich und weisen Sie sich für Ihre Drittanbieter-Abhängigkeiten aus.</span><span class="sxs-lookup"><span data-stu-id="6ee63-110">Identify and account for your third-party dependencies.</span></span>

   <span data-ttu-id="6ee63-111">Sie müssen verstehen, was Ihre Drittanbieter-Abhängigkeiten sind, wie Sie von diesen abhängig sind, wie Sie überprüfen können, ob sie ebenso auf .NET Core ausgeführt werden, und welche Schritte Sie durchführen können, falls sie es nicht tun.</span><span class="sxs-lookup"><span data-stu-id="6ee63-111">This will involve understanding what your third-party dependencies are, how you depend on them, how to see if they also run on .NET Core, and steps you can take if they don't.</span></span>
   
2. <span data-ttu-id="6ee63-112">Legen Sie .NET Framework 4.6.2 als neues Ziel für alle Projekte fest, die Sie portieren möchten.</span><span class="sxs-lookup"><span data-stu-id="6ee63-112">Retarget all projects you wish to port to target .NET Framework 4.6.2.</span></span>

   <span data-ttu-id="6ee63-113">Dadurch wird sichergestellt, dass Sie API-Alternativen für bestimmte .NET Framework-Ziele in Fällen verwenden können, in denen .NET Core eine bestimmte API nicht unterstützen kann.</span><span class="sxs-lookup"><span data-stu-id="6ee63-113">This ensures that you can use API alternatives for .NET Framework-specific targets in the cases where .NET Core can't support a particular API.</span></span>
   
3. <span data-ttu-id="6ee63-114">Verwenden Sie das [Tool zum Analysieren der API-Portabilität](https://github.com/Microsoft/dotnet-apiport/), um Ihre Assemblys zu analysieren, und um einen Plan zum Portieren auf Grundlage der Ergebnisse zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="6ee63-114">Use the [API Portability Analyzer tool](https://github.com/Microsoft/dotnet-apiport/) to analyze your assemblies and develop a plan to port based on its results.</span></span>

   <span data-ttu-id="6ee63-115">Das Tool zum Analysieren der API-Portabilität analysiert Ihre kompilierten Assemblys und generiert einen Bericht, der eine allgemeine Zusammenfassung über die Portabilität sowie einen Strukturplan jeder API anzeigt, die Sie verwenden, und die nicht auf .NET Core verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="6ee63-115">The API Portability Analyzer tool will analyze your compiled assemblies and generate a report which shows a high-level portability summary and a breakdown of each API you're using that isn't available on .NET Core.</span></span>  <span data-ttu-id="6ee63-116">Sie können diesen Bericht zusammen mit einer Analyse Ihrer Codebase verwenden, um einen Plan zum Portieren Ihres Codes zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="6ee63-116">You can use this report alongside an analysis of your codebase to develop a plan for how you'll port your code over.</span></span>
   
4. <span data-ttu-id="6ee63-117">Portieren Sie Ihre Testcodes.</span><span class="sxs-lookup"><span data-stu-id="6ee63-117">Port your tests code.</span></span>

   <span data-ttu-id="6ee63-118">Da das Portieren auf .NET Core solch eine große Änderung für Ihre Codebase darstellt, wird empfohlen, Ihre Tests zu portieren, damit Sie Tests ausführen können, wenn Sie Code portieren.</span><span class="sxs-lookup"><span data-stu-id="6ee63-118">Because porting to .NET Core is such a big change to your codebase, it's highly recommended to get your tests ported so that you can run tests as you port code over.</span></span>  <span data-ttu-id="6ee63-119">MSTest, xUnit und NUnit unterstützen derzeit alle .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="6ee63-119">MSTest, xUnit, and NUnit all support .NET Core 1.0 today.</span></span>
   
6. <span data-ttu-id="6ee63-120">Führen Sie Ihren Plan zum Portieren aus!</span><span class="sxs-lookup"><span data-stu-id="6ee63-120">Execute your plan for porting!</span></span>

## <a name="tools-to-help"></a><span data-ttu-id="6ee63-121">Hilfetools</span><span class="sxs-lookup"><span data-stu-id="6ee63-121">Tools to help</span></span>

<span data-ttu-id="6ee63-122">Nachstehend finden Sie eine Liste der Tools, die hilfreich sein können:</span><span class="sxs-lookup"><span data-stu-id="6ee63-122">Here's a short list of the tools you'll find helpful:</span></span>

* <span data-ttu-id="6ee63-123">NuGet – [Nuget Client](https://dist.nuget.org/index.html) oder [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) sind die Paket-Manager von Microsoft für .NET-Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="6ee63-123">NuGet - [Nuget Client](https://dist.nuget.org/index.html) or [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer), Microsoft's package manager for .NET implementations.</span></span>
* <span data-ttu-id="6ee63-124">API Portability Analyzer – [Befehlszeilentool ](https://github.com/Microsoft/dotnet-apiport/releases) oder [Visual Studio-Erweiterung](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b); eine Toolkette, die einen Bericht generieren kann, der aussagt, wie portierbar Ihr Code zwischen .NET Framework und .NET Core ist, mithilfe einem Assembly-zu-Assymbly-Strukturplan der Fehler.</span><span class="sxs-lookup"><span data-stu-id="6ee63-124">Api Portability Analyzer - [command line tool](https://github.com/Microsoft/dotnet-apiport/releases) or [Visual Studio Extension](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b), a toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core, with an assembly-by-assembly breakdown of issues.</span></span>  <span data-ttu-id="6ee63-125">Weitere Informationen finden Sie unter [Tooling to help you on the process (Tools für den Vorgang)](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/).</span><span class="sxs-lookup"><span data-stu-id="6ee63-125">See [Tooling to help you on the process](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/) for more information.</span></span>
* <span data-ttu-id="6ee63-126">Reverse Package Search – ein [nützlicher Webdienst](https://packagesearch.azurewebsites.net), mit dem Sie einen Typ suchen können und Pakete finden können, die diesen Typ enthalten.</span><span class="sxs-lookup"><span data-stu-id="6ee63-126">Reverse Package Search - A [useful web service](https://packagesearch.azurewebsites.net) that allows you to search for a type and find packages containing that type.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6ee63-127">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6ee63-127">Next steps</span></span>

[<span data-ttu-id="6ee63-128">Porting to .NET Core - Analyzing your Third-Party Dependencies (Portieren auf.NET Core – Analysieren Ihrer Drittanbieter-Abhängigkeiten)</span><span class="sxs-lookup"><span data-stu-id="6ee63-128">Analyzing your third-party dependencies.</span></span>](third-party-deps.md)
   

