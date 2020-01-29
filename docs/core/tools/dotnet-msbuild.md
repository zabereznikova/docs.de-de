---
title: Befehl „dotnet msbuild“
description: Der Befehl dotnet msbuild ermöglicht den Zugriff auf die MSBuild-Befehlszeile.
ms.date: 12/03/2018
ms.openlocfilehash: dae1e9f0ca355166d41c11fbafb80c7c9fb29748
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733195"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="0c918-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="0c918-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="0c918-104">name</span><span class="sxs-lookup"><span data-stu-id="0c918-104">Name</span></span>

<span data-ttu-id="0c918-105">`dotnet msbuild`: Erstellt ein Projekt und alle seine Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="0c918-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0c918-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="0c918-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="0c918-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0c918-107">Description</span></span>

<span data-ttu-id="0c918-108">Der `dotnet msbuild`-Befehl ermöglicht den Zugriff auf eine voll funktionsfähige MSBuild-Instanz.</span><span class="sxs-lookup"><span data-stu-id="0c918-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="0c918-109">Der Befehl weist genau die gleichen Funktionen wie der vorhandene MSBuild-Befehlszeilenclient für ausschließlich im SDK-Stil geschriebene Projekte auf.</span><span class="sxs-lookup"><span data-stu-id="0c918-109">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style projects only.</span></span> <span data-ttu-id="0c918-110">Alle Optionen sind gleich.</span><span class="sxs-lookup"><span data-stu-id="0c918-110">The options are all the same.</span></span> <span data-ttu-id="0c918-111">Weitere Informationen zu den verfügbaren Optionen finden Sie in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="0c918-111">For more information about the available options, see the [MSBuild command-line reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="0c918-112">Der [dotnet build](dotnet-build.md)-Befehl ist äquivalent zu `dotnet msbuild -restore -target:Build`.</span><span class="sxs-lookup"><span data-stu-id="0c918-112">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore -target:Build`.</span></span> <span data-ttu-id="0c918-113">Der [dotnet build](dotnet-build.md)-Befehl wird häufiger zum Erstellen von Projekten verwendet, aber da dieser immer das Buildziel ausführt, können Sie `dotnet msbuild` verwenden, wenn Sie das Projekt nicht erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="0c918-113">[dotnet build](dotnet-build.md) is more commonly used for building projects, but because it always runs the build target, you can use `dotnet msbuild` when you don't want to build the project.</span></span> <span data-ttu-id="0c918-114">Wenn Sie z. B. ein bestimmtes Ziel haben, das Sie ausführen möchten, ohne das Projekt zu erstellen, verwenden Sie `dotnet msbuild`, und geben Sie das Ziel an.</span><span class="sxs-lookup"><span data-stu-id="0c918-114">For example, if you have a specific target you want to run without building the project, use `dotnet msbuild` and specify the target.</span></span>

## <a name="examples"></a><span data-ttu-id="0c918-115">Beispiele</span><span class="sxs-lookup"><span data-stu-id="0c918-115">Examples</span></span>

* <span data-ttu-id="0c918-116">Erstellt ein Projekt und seine Abhängigkeiten:</span><span class="sxs-lookup"><span data-stu-id="0c918-116">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet msbuild
  ```

* <span data-ttu-id="0c918-117">Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="0c918-117">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

* <span data-ttu-id="0c918-118">Führt das Veröffentlichungsziel aus und veröffentlicht für die RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="0c918-118">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

* <span data-ttu-id="0c918-119">Zeigen Sie das gesamte Projekt mit allen Zielen an, die über das SDK eingeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="0c918-119">See the whole project with all targets included by the SDK:</span></span>

  ```dotnetcli
  dotnet msbuild -preprocess
  ```
