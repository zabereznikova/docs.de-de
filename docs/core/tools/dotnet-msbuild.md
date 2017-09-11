---
title: "Befehl dotnet-msbuild – .NET Core-CLI"
description: "Der Befehl dotnet-msbuild ermöglicht den Zugriff auf die MSBuild-Befehlszeile."
keywords: dotnet-msmsbuild, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 05/24/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: ffdc40ba-ef33-463e-aa35-b0af1fe615a2
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1f02dcd779b9ed249ebd2fedb973383b1dcd8963
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-msbuild"></a><span data-ttu-id="f13af-104">dotnet-msbuild</span><span class="sxs-lookup"><span data-stu-id="f13af-104">dotnet-msbuild</span></span>

## <a name="name"></a><span data-ttu-id="f13af-105">Name</span><span class="sxs-lookup"><span data-stu-id="f13af-105">Name</span></span>

<span data-ttu-id="f13af-106">`dotnet-msbuild`: Erstellt ein Projekt und alle seine Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="f13af-106">`dotnet-msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f13af-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="f13af-107">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="f13af-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f13af-108">Description</span></span>

<span data-ttu-id="f13af-109">Der `dotnet msbuild`-Befehl ermöglicht den Zugriff auf eine voll funktionsfähige MSBuild-Instanz.</span><span class="sxs-lookup"><span data-stu-id="f13af-109">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="f13af-110">Der Befehl weist genau die gleichen Funktionen wie der vorhandene MSBuild-Befehlszeilenclient auf.</span><span class="sxs-lookup"><span data-stu-id="f13af-110">The command has the exact same capabilities as existing MSBuild command-line client.</span></span> <span data-ttu-id="f13af-111">Alle Optionen sind gleich.</span><span class="sxs-lookup"><span data-stu-id="f13af-111">The options are all the same.</span></span> <span data-ttu-id="f13af-112">Informationen zu den verfügbaren Optionen finden Sie unter [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="f13af-112">Use the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) to obtain information on the available options.</span></span> 

## <a name="examples"></a><span data-ttu-id="f13af-113">Beispiele</span><span class="sxs-lookup"><span data-stu-id="f13af-113">Examples</span></span>

<span data-ttu-id="f13af-114">Erstellt ein Projekt und seine Abhängigkeiten:</span><span class="sxs-lookup"><span data-stu-id="f13af-114">Build a project and its dependencies:</span></span>

`dotnet msbuild`

<span data-ttu-id="f13af-115">Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="f13af-115">Build a project and its dependencies using Release configuration:</span></span>

`dotnet msbuild /p:Configuration=Release`

<span data-ttu-id="f13af-116">Führt das Veröffentlichungsziel aus und veröffentlicht für die RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="f13af-116">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`

<span data-ttu-id="f13af-117">Zeigen Sie das gesamte Projekt mit allen Zielen an, die über das SDK eingeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="f13af-117">See the whole project with all targets included by the SDK:</span></span>

`dotnet msbuild /pp`

