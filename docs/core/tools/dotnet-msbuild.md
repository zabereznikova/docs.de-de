---
title: Befehl „dotnet msbuild“
description: Der Befehl dotnet msbuild ermöglicht den Zugriff auf die MSBuild-Befehlszeile.
ms.date: 02/14/2020
ms.openlocfilehash: 28a32a460d644d3e22f16b5dd9416222ae466e2e
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503680"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="6580e-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="6580e-103">dotnet msbuild</span></span>

<span data-ttu-id="6580e-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="6580e-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="6580e-105">name</span><span class="sxs-lookup"><span data-stu-id="6580e-105">Name</span></span>

<span data-ttu-id="6580e-106">`dotnet msbuild`: Erstellt ein Projekt und alle seine Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="6580e-106">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6580e-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="6580e-107">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="6580e-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6580e-108">Description</span></span>

<span data-ttu-id="6580e-109">Der `dotnet msbuild`-Befehl ermöglicht den Zugriff auf eine voll funktionsfähige MSBuild-Instanz.</span><span class="sxs-lookup"><span data-stu-id="6580e-109">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="6580e-110">Der Befehl weist genau die gleichen Funktionen wie der vorhandene MSBuild-Befehlszeilenclient für ausschließlich im SDK-Stil geschriebene Projekte auf.</span><span class="sxs-lookup"><span data-stu-id="6580e-110">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style projects only.</span></span> <span data-ttu-id="6580e-111">Alle Optionen sind gleich.</span><span class="sxs-lookup"><span data-stu-id="6580e-111">The options are all the same.</span></span> <span data-ttu-id="6580e-112">Weitere Informationen zu den verfügbaren Optionen finden Sie in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="6580e-112">For more information about the available options, see the [MSBuild command-line reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="6580e-113">Der [dotnet build](dotnet-build.md)-Befehl ist äquivalent zu `dotnet msbuild -restore -target:Build`.</span><span class="sxs-lookup"><span data-stu-id="6580e-113">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore -target:Build`.</span></span> <span data-ttu-id="6580e-114">Der [dotnet build](dotnet-build.md)-Befehl wird häufiger zum Erstellen von Projekten verwendet, aber da dieser immer das Buildziel ausführt, können Sie `dotnet msbuild` verwenden, wenn Sie das Projekt nicht erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="6580e-114">[dotnet build](dotnet-build.md) is more commonly used for building projects, but because it always runs the build target, you can use `dotnet msbuild` when you don't want to build the project.</span></span> <span data-ttu-id="6580e-115">Wenn Sie z. B. ein bestimmtes Ziel haben, das Sie ausführen möchten, ohne das Projekt zu erstellen, verwenden Sie `dotnet msbuild`, und geben Sie das Ziel an.</span><span class="sxs-lookup"><span data-stu-id="6580e-115">For example, if you have a specific target you want to run without building the project, use `dotnet msbuild` and specify the target.</span></span>

## <a name="examples"></a><span data-ttu-id="6580e-116">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6580e-116">Examples</span></span>

- <span data-ttu-id="6580e-117">Erstellt ein Projekt und seine Abhängigkeiten:</span><span class="sxs-lookup"><span data-stu-id="6580e-117">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet msbuild
  ```

- <span data-ttu-id="6580e-118">Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="6580e-118">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

- <span data-ttu-id="6580e-119">Führt das Veröffentlichungsziel aus und veröffentlicht für die RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="6580e-119">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

- <span data-ttu-id="6580e-120">Zeigen Sie das gesamte Projekt mit allen Zielen an, die über das SDK eingeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="6580e-120">See the whole project with all targets included by the SDK:</span></span>

  ```dotnetcli
  dotnet msbuild -preprocess
  ```
