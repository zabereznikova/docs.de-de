---
title: "dotnet-msbuild-Befehl – .NET Core-CLI"
description: "Der Befehl dotnet msbuild ermöglicht den Zugriff auf die MSBuild-Befehlszeile."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 96e4eac528abad2b336a979a98c9be2bee5d17ee
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="94a3c-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="94a3c-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="94a3c-104">Name</span><span class="sxs-lookup"><span data-stu-id="94a3c-104">Name</span></span>

<span data-ttu-id="94a3c-105">`dotnet msbuild`: Erstellt ein Projekt und alle seine Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="94a3c-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="94a3c-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="94a3c-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="94a3c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="94a3c-107">Description</span></span>

<span data-ttu-id="94a3c-108">Der `dotnet msbuild`-Befehl ermöglicht den Zugriff auf eine voll funktionsfähige MSBuild-Instanz.</span><span class="sxs-lookup"><span data-stu-id="94a3c-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="94a3c-109">Der Befehl weist genau die gleichen Funktionen wie der vorhandene MSBuild-Befehlszeilenclient auf.</span><span class="sxs-lookup"><span data-stu-id="94a3c-109">The command has the exact same capabilities as existing MSBuild command-line client.</span></span> <span data-ttu-id="94a3c-110">Alle Optionen sind gleich.</span><span class="sxs-lookup"><span data-stu-id="94a3c-110">The options are all the same.</span></span> <span data-ttu-id="94a3c-111">Informationen zu den verfügbaren Optionen finden Sie unter [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="94a3c-111">Use the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) to obtain information on the available options.</span></span> 

## <a name="examples"></a><span data-ttu-id="94a3c-112">Beispiele</span><span class="sxs-lookup"><span data-stu-id="94a3c-112">Examples</span></span>

<span data-ttu-id="94a3c-113">Erstellt ein Projekt und seine Abhängigkeiten:</span><span class="sxs-lookup"><span data-stu-id="94a3c-113">Build a project and its dependencies:</span></span>

`dotnet msbuild`

<span data-ttu-id="94a3c-114">Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="94a3c-114">Build a project and its dependencies using Release configuration:</span></span>

`dotnet msbuild /p:Configuration=Release`

<span data-ttu-id="94a3c-115">Führt das Veröffentlichungsziel aus und veröffentlicht für die RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="94a3c-115">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`

<span data-ttu-id="94a3c-116">Zeigen Sie das gesamte Projekt mit allen Zielen an, die über das SDK eingeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="94a3c-116">See the whole project with all targets included by the SDK:</span></span>

`dotnet msbuild /pp`
