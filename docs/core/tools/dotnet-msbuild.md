---
title: dotnet-msbuild-Befehl – .NET Core-CLI
description: Der Befehl dotnet msbuild ermöglicht den Zugriff auf die MSBuild-Befehlszeile.
ms.date: 12/03/2018
ms.openlocfilehash: 93471ded9614502ab89d5afb19dd9992f068ef80
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128046"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="1a36a-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="1a36a-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="1a36a-104">name</span><span class="sxs-lookup"><span data-stu-id="1a36a-104">Name</span></span>

<span data-ttu-id="1a36a-105">`dotnet msbuild`: Erstellt ein Projekt und alle seine Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="1a36a-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1a36a-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="1a36a-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="1a36a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a36a-107">Description</span></span>

<span data-ttu-id="1a36a-108">Der `dotnet msbuild`-Befehl ermöglicht den Zugriff auf eine voll funktionsfähige MSBuild-Instanz.</span><span class="sxs-lookup"><span data-stu-id="1a36a-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="1a36a-109">Der Befehl weist genau die gleichen Funktionen wie der vorhandene MSBuild-Befehlszeilenclient für ausschließlich im SDK-Stil geschriebene Projekte auf.</span><span class="sxs-lookup"><span data-stu-id="1a36a-109">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style project only.</span></span> <span data-ttu-id="1a36a-110">Alle Optionen sind gleich.</span><span class="sxs-lookup"><span data-stu-id="1a36a-110">The options are all the same.</span></span> <span data-ttu-id="1a36a-111">Weitere Informationen zu den verfügbaren Optionen finden Sie in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="1a36a-111">For more information about the available options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="1a36a-112">Der [dotnet build](dotnet-build.md)-Befehl ist äquivalent zu `dotnet msbuild -restore -target:Build`.</span><span class="sxs-lookup"><span data-stu-id="1a36a-112">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore -target:Build`.</span></span> <span data-ttu-id="1a36a-113">`dotnet build` wird häufiger zum Erstellen von Projekten verwendet, aber mit `dotnet msbuild` haben Sie mehr Kontrolle.</span><span class="sxs-lookup"><span data-stu-id="1a36a-113">`dotnet build` is more commonly used for building projects, but `dotnet msbuild` gives you more control.</span></span> <span data-ttu-id="1a36a-114">Wenn Sie z.B. ein bestimmtes Ausführungsziel haben (ohne Ausführung des Buildziels), verwenden Sie wahrscheinlich `dotnet msbuild`.</span><span class="sxs-lookup"><span data-stu-id="1a36a-114">For example, if you have a specific target you want to run (without running the build target), you probably want to use `dotnet msbuild`.</span></span>

## <a name="examples"></a><span data-ttu-id="1a36a-115">Beispiele</span><span class="sxs-lookup"><span data-stu-id="1a36a-115">Examples</span></span>

* <span data-ttu-id="1a36a-116">Erstellt ein Projekt und seine Abhängigkeiten:</span><span class="sxs-lookup"><span data-stu-id="1a36a-116">Build a project and its dependencies:</span></span>

  ```console
  dotnet msbuild
  ```

* <span data-ttu-id="1a36a-117">Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="1a36a-117">Build a project and its dependencies using Release configuration:</span></span>

  ```console
  dotnet msbuild -p:Configuration=Release
  ```

* <span data-ttu-id="1a36a-118">Führt das Veröffentlichungsziel aus und veröffentlicht für die RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="1a36a-118">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```console
  dotnet msbuild -t:Publish -p:RuntimeIdentifiers=osx.10.11-x64
  ```

* <span data-ttu-id="1a36a-119">Zeigen Sie das gesamte Projekt mit allen Zielen an, die über das SDK eingeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="1a36a-119">See the whole project with all targets included by the SDK:</span></span>

  ```console
  dotnet msbuild -pp
  ```