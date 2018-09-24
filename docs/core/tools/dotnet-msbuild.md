---
title: dotnet-msbuild-Befehl – .NET Core-CLI
description: Der Befehl dotnet msbuild ermöglicht den Zugriff auf die MSBuild-Befehlszeile.
author: mairaw
ms.author: mairaw
ms.date: 05/25/2018
ms.openlocfilehash: 76165590478b0e76d19d546c87e012da4716b6db
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46578895"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="3b8e7-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="3b8e7-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="3b8e7-104">name</span><span class="sxs-lookup"><span data-stu-id="3b8e7-104">Name</span></span>

<span data-ttu-id="3b8e7-105">`dotnet msbuild`: Erstellt ein Projekt und alle seine Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="3b8e7-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3b8e7-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="3b8e7-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="3b8e7-107">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="3b8e7-107">Description</span></span>

<span data-ttu-id="3b8e7-108">Der `dotnet msbuild`-Befehl ermöglicht den Zugriff auf eine voll funktionsfähige MSBuild-Instanz.</span><span class="sxs-lookup"><span data-stu-id="3b8e7-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="3b8e7-109">Der Befehl weist genau die gleichen Funktionen wie der vorhandene MSBuild-Befehlszeilenclient auf.</span><span class="sxs-lookup"><span data-stu-id="3b8e7-109">The command has the exact same capabilities as existing MSBuild command-line client.</span></span> <span data-ttu-id="3b8e7-110">Alle Optionen sind gleich.</span><span class="sxs-lookup"><span data-stu-id="3b8e7-110">The options are all the same.</span></span> <span data-ttu-id="3b8e7-111">Weitere Informationen zu den verfügbaren Optionen finden Sie in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="3b8e7-111">For more information about the available options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

## <a name="examples"></a><span data-ttu-id="3b8e7-112">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3b8e7-112">Examples</span></span>

<span data-ttu-id="3b8e7-113">Erstellt ein Projekt und seine Abhängigkeiten:</span><span class="sxs-lookup"><span data-stu-id="3b8e7-113">Build a project and its dependencies:</span></span>

`dotnet msbuild`

<span data-ttu-id="3b8e7-114">Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="3b8e7-114">Build a project and its dependencies using Release configuration:</span></span>

`dotnet msbuild -p:Configuration=Release`

<span data-ttu-id="3b8e7-115">Führt das Veröffentlichungsziel aus und veröffentlicht für die RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="3b8e7-115">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

`dotnet msbuild -t:Publish -p:RuntimeIdentifiers=osx.10.11-x64`

<span data-ttu-id="3b8e7-116">Zeigen Sie das gesamte Projekt mit allen Zielen an, die über das SDK eingeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="3b8e7-116">See the whole project with all targets included by the SDK:</span></span>

`dotnet msbuild -pp`
