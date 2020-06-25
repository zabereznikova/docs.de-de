---
title: Befehl „dotnet msbuild“
description: Der Befehl dotnet msbuild ermöglicht den Zugriff auf die MSBuild-Befehlszeile.
ms.date: 02/14/2020
ms.openlocfilehash: 9739fe782e17db3955db087ca1781ad4280cd491
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803173"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="f2dee-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="f2dee-103">dotnet msbuild</span></span>

<span data-ttu-id="f2dee-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="f2dee-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="f2dee-105">name</span><span class="sxs-lookup"><span data-stu-id="f2dee-105">Name</span></span>

<span data-ttu-id="f2dee-106">`dotnet msbuild`: Erstellt ein Projekt und alle seine Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="f2dee-106">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span> <span data-ttu-id="f2dee-107">Hinweis: Wenn mehrere vorhanden sind, muss möglicherweise eine Projektmappe oder eine Projektdatei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f2dee-107">Note: A solution or project file may need to be specified if there are multiple.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f2dee-108">Übersicht</span><span class="sxs-lookup"><span data-stu-id="f2dee-108">Synopsis</span></span>

```dotnetcli
dotnet msbuild <MSBUILD_ARGUMENTS>

dotnet msbuild -h
```

## <a name="description"></a><span data-ttu-id="f2dee-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2dee-109">Description</span></span>

<span data-ttu-id="f2dee-110">Der `dotnet msbuild`-Befehl ermöglicht den Zugriff auf eine voll funktionsfähige MSBuild-Instanz.</span><span class="sxs-lookup"><span data-stu-id="f2dee-110">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="f2dee-111">Der Befehl weist genau die gleichen Funktionen wie der vorhandene MSBuild-Befehlszeilenclient für ausschließlich im SDK-Stil geschriebene Projekte auf.</span><span class="sxs-lookup"><span data-stu-id="f2dee-111">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style projects only.</span></span> <span data-ttu-id="f2dee-112">Alle Optionen sind gleich.</span><span class="sxs-lookup"><span data-stu-id="f2dee-112">The options are all the same.</span></span> <span data-ttu-id="f2dee-113">Weitere Informationen zu den verfügbaren Optionen finden Sie in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="f2dee-113">For more information about the available options, see the [MSBuild command-line reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="f2dee-114">Der [dotnet build](dotnet-build.md)-Befehl ist äquivalent zu `dotnet msbuild -restore`.</span><span class="sxs-lookup"><span data-stu-id="f2dee-114">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore`.</span></span> <span data-ttu-id="f2dee-115">Wenn Sie das Projekt nicht erstellen und ein bestimmtes Ziel ausführen möchten, verwenden Sie `dotnet build` oder `dotnet msbuild`, und geben Sie das Ziel an.</span><span class="sxs-lookup"><span data-stu-id="f2dee-115">When you don't want to build the project and you have a specific target you want to run, use `dotnet build` or `dotnet msbuild` and specify the target.</span></span>

## <a name="examples"></a><span data-ttu-id="f2dee-116">Beispiele</span><span class="sxs-lookup"><span data-stu-id="f2dee-116">Examples</span></span>

- <span data-ttu-id="f2dee-117">Erstellt ein Projekt und seine Abhängigkeiten:</span><span class="sxs-lookup"><span data-stu-id="f2dee-117">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet msbuild
  ```

- <span data-ttu-id="f2dee-118">Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="f2dee-118">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

- <span data-ttu-id="f2dee-119">Führt das Veröffentlichungsziel aus und veröffentlicht für die RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="f2dee-119">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

- <span data-ttu-id="f2dee-120">Zeigen Sie das gesamte Projekt mit allen Zielen an, die über das SDK eingeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="f2dee-120">See the whole project with all targets included by the SDK:</span></span>

  ```dotnetcli
  dotnet msbuild -preprocess
  dotnet msbuild -preprocess:<fileName>.xml
  ```
