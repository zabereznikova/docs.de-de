---
title: Befehl „dotnet remove reference“
description: Der Verweisbefehl „dotnet remove“ bietet eine praktische Option zum Entfernen von Projekt-zu-Projekt-Verweisen.
ms.date: 02/14/2020
ms.openlocfilehash: 92d36bbbde64d806abc8f223c5f08e3f3d79ce9d
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463443"
---
# <a name="dotnet-remove-reference"></a><span data-ttu-id="83477-103">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="83477-103">dotnet remove reference</span></span>

<span data-ttu-id="83477-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="83477-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="83477-105">Name</span><span class="sxs-lookup"><span data-stu-id="83477-105">Name</span></span>

<span data-ttu-id="83477-106">`dotnet remove reference`: Entfernt Projekt-zu-Projekt-Verweise.</span><span class="sxs-lookup"><span data-stu-id="83477-106">`dotnet remove reference` - Removes project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="83477-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="83477-107">Synopsis</span></span>

```dotnetcli
dotnet remove [<PROJECT>] reference [-f|--framework <FRAMEWORK>] <PROJECT_REFERENCES>

dotnet remove reference -h|--help
```

## <a name="description"></a><span data-ttu-id="83477-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="83477-108">Description</span></span>

<span data-ttu-id="83477-109">Der `dotnet remove reference`-Befehl bietet eine praktische Option zum Entfernen von Projektverweisen von einem Projekt.</span><span class="sxs-lookup"><span data-stu-id="83477-109">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="83477-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="83477-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="83477-111">Zielprojektdatei.</span><span class="sxs-lookup"><span data-stu-id="83477-111">Target project file.</span></span> <span data-ttu-id="83477-112">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="83477-112">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="83477-113">Zu entfernende Projekt-zu-Projekt-Verweise (P2P).</span><span class="sxs-lookup"><span data-stu-id="83477-113">Project-to-project (P2P) references to remove.</span></span> <span data-ttu-id="83477-114">Sie können ein oder mehrere Projekte angeben.</span><span class="sxs-lookup"><span data-stu-id="83477-114">You can specify one or multiple projects.</span></span> <span data-ttu-id="83477-115">[Globmuster](https://en.wikipedia.org/wiki/Glob_(programming)) werden auf Unix/Linux-basierten Terminals unterstützt.</span><span class="sxs-lookup"><span data-stu-id="83477-115">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="83477-116">Optionen</span><span class="sxs-lookup"><span data-stu-id="83477-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="83477-117">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="83477-117">Prints out a short help for the command.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="83477-118">Entfernt den Verweis nur, wenn auf ein bestimmtes [Framework](../../standard/frameworks.md) abgezielt wird.</span><span class="sxs-lookup"><span data-stu-id="83477-118">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="83477-119">Beispiele</span><span class="sxs-lookup"><span data-stu-id="83477-119">Examples</span></span>

- <span data-ttu-id="83477-120">Entfernen Sie einen Projektverweis aus dem angegebenen Projekt:</span><span class="sxs-lookup"><span data-stu-id="83477-120">Remove a project reference from the specified project:</span></span>

  ```dotnetcli
  dotnet remove app/app.csproj reference lib/lib.csproj
  ```

- <span data-ttu-id="83477-121">Entfernen Sie mehrere Projektverweise aus dem Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="83477-121">Remove multiple project references from the project in the current directory:</span></span>

  ```dotnetcli
  dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- <span data-ttu-id="83477-122">Entfernen Sie mehrere Projektverweise mithilfe eines Globmusters auf Unix/Linux:</span><span class="sxs-lookup"><span data-stu-id="83477-122">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

  ```dotnetcli
  dotnet remove app/app.csproj reference **/*.csproj`
  ```
