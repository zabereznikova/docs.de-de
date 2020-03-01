---
title: Befehl „dotnet tool run“
description: Mit dem Befehl „dotnet tool run“ wird ein lokales Tool aufgerufen.
ms.date: 02/14/2020
ms.openlocfilehash: 76830b8a8088fbf21f14ab0722b9547eabde7ba4
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156958"
---
# <a name="dotnet-tool-run"></a><span data-ttu-id="67317-103">dotnet tool run</span><span class="sxs-lookup"><span data-stu-id="67317-103">dotnet tool run</span></span>

<span data-ttu-id="67317-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="67317-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="67317-105">name</span><span class="sxs-lookup"><span data-stu-id="67317-105">Name</span></span>

<span data-ttu-id="67317-106">`dotnet tool run`: ruft ein lokales Tool auf.</span><span class="sxs-lookup"><span data-stu-id="67317-106">`dotnet tool run` - Invokes a local tool.</span></span>

## <a name="synopsis"></a><span data-ttu-id="67317-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="67317-107">Synopsis</span></span>

```dotnetcli
dotnet tool run <COMMAND NAME>
dotnet tool run <-h|--help>
```

## <a name="description"></a><span data-ttu-id="67317-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="67317-108">Description</span></span>

<span data-ttu-id="67317-109">Der `dotnet tool run`-Befehl durchsucht Manifestdateien des Tools, die sich im Geltungsbereich des aktuellen Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="67317-109">The `dotnet tool run` command searches tool manifest files that are in scope for the current directory.</span></span> <span data-ttu-id="67317-110">Wenn ein Verweis auf das angegebene Tool gefunden wird, wird das Tool ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="67317-110">When it finds a reference to the specified tool, it runs the tool.</span></span> <span data-ttu-id="67317-111">Weitere Informationen finden Sie unter [Aufrufen eines lokalen Tools](global-tools.md#invoke-a-local-tool).</span><span class="sxs-lookup"><span data-stu-id="67317-111">For more information, see [Invoke a local tool](global-tools.md#invoke-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="67317-112">Argumente</span><span class="sxs-lookup"><span data-stu-id="67317-112">Arguments</span></span>

- **`COMMAND_NAME`**

  <span data-ttu-id="67317-113">Der Befehlsname des auszuführenden Tools.</span><span class="sxs-lookup"><span data-stu-id="67317-113">The command name of the tool to run.</span></span>

## <a name="options"></a><span data-ttu-id="67317-114">Optionen</span><span class="sxs-lookup"><span data-stu-id="67317-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="67317-115">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="67317-115">Prints out a short help for the command.</span></span>

## <a name="example"></a><span data-ttu-id="67317-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="67317-116">Example</span></span>

- **`dotnet tool run dotnetsay`**

  <span data-ttu-id="67317-117">Führt das lokale Tool `dotnetsay` aus.</span><span class="sxs-lookup"><span data-stu-id="67317-117">Runs the `dotnetsay` local tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="67317-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67317-118">See also</span></span>

- [<span data-ttu-id="67317-119">.NET Core-Tools</span><span class="sxs-lookup"><span data-stu-id="67317-119">.NET Core tools</span></span>](global-tools.md)
