---
title: Befehl „dotnet tool list“
description: Der Befehl „dotnet tool list“ listet die auf Ihrem Computer installierten .NET Core-Tools auf.
ms.date: 02/14/2020
ms.openlocfilehash: f231dcfe64a925f75f948d508e7a2d83befd9a00
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156984"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="5b9c0-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="5b9c0-103">dotnet tool list</span></span>

<span data-ttu-id="5b9c0-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="5b9c0-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="5b9c0-105">name</span><span class="sxs-lookup"><span data-stu-id="5b9c0-105">Name</span></span>

<span data-ttu-id="5b9c0-106">`dotnet tool list`: Listet alle [.NET Core-Tools](global-tools.md) des angegebenen Typs auf, der derzeit auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="5b9c0-106">`dotnet tool list` - Lists all [.NET Core tools](global-tools.md) of the specified type currently installed on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5b9c0-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="5b9c0-107">Synopsis</span></span>

```dotnetcli
dotnet tool list <-g|--global>
dotnet tool list <--tool-path>
dotnet tool list
dotnet tool list <-h|--help>
```

## <a name="description"></a><span data-ttu-id="5b9c0-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b9c0-108">Description</span></span>

<span data-ttu-id="5b9c0-109">Der Befehl `dotnet tool list` bietet die Möglichkeit, alle globalen, Toolpfad- oder lokalen .NET Core-Tools aufzulisten, die auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="5b9c0-109">The `dotnet tool list` command provides a way for you to list all .NET Core global, tool-path, or local Tools installed on your machine.</span></span> <span data-ttu-id="5b9c0-110">Der Befehl listet den Paketnamen, die installierte Version und den Befehl für das Tool auf.</span><span class="sxs-lookup"><span data-stu-id="5b9c0-110">The command lists the package name, version installed, and the tool command.</span></span>  <span data-ttu-id="5b9c0-111">Um den Befehl zu verwenden, geben Sie eine der folgenden Optionen an:</span><span class="sxs-lookup"><span data-stu-id="5b9c0-111">To use the command, you specify one of the following:</span></span>

* <span data-ttu-id="5b9c0-112">Ein globales Tool, das am Standardspeicherort installiert ist.</span><span class="sxs-lookup"><span data-stu-id="5b9c0-112">A global tool installed in the default location.</span></span> <span data-ttu-id="5b9c0-113">Verwenden Sie die Option `--global`.</span><span class="sxs-lookup"><span data-stu-id="5b9c0-113">Use the `--global` option</span></span>
* <span data-ttu-id="5b9c0-114">Ein globales Tool, das an einem benutzerdefinierten Speicherort installiert ist.</span><span class="sxs-lookup"><span data-stu-id="5b9c0-114">A global tool installed in a custom location.</span></span> <span data-ttu-id="5b9c0-115">Verwenden Sie die `--tool-path`-Option.</span><span class="sxs-lookup"><span data-stu-id="5b9c0-115">Use the `--tool-path` option.</span></span>
* <span data-ttu-id="5b9c0-116">Ein lokales Tool.</span><span class="sxs-lookup"><span data-stu-id="5b9c0-116">A local tool.</span></span> <span data-ttu-id="5b9c0-117">Lassen Sie die Optionen `--global` und `--tool-path` weg.</span><span class="sxs-lookup"><span data-stu-id="5b9c0-117">Omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="5b9c0-118">**Lokale Tools sind ab .NET Core SDK 3.0 verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="5b9c0-118">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="options"></a><span data-ttu-id="5b9c0-119">Optionen</span><span class="sxs-lookup"><span data-stu-id="5b9c0-119">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="5b9c0-120">Listet benutzerweite globale Tools auf.</span><span class="sxs-lookup"><span data-stu-id="5b9c0-120">Lists user-wide global tools.</span></span> <span data-ttu-id="5b9c0-121">Kann nicht mit der Option `--tool-path` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="5b9c0-121">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="5b9c0-122">Bei Weglassen von `--global` und `--tool-path` werden lokale Tools aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="5b9c0-122">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

- **`-h|--help`**

  <span data-ttu-id="5b9c0-123">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="5b9c0-123">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="5b9c0-124">Legt einen benutzerdefinierten Speicherort fest, an dem globale Tools gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="5b9c0-124">Specifies a custom location where to find global tools.</span></span> <span data-ttu-id="5b9c0-125">„PATH“ kann absolut oder relativ sein.</span><span class="sxs-lookup"><span data-stu-id="5b9c0-125">PATH can be absolute or relative.</span></span> <span data-ttu-id="5b9c0-126">Kann nicht mit der Option `--global` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="5b9c0-126">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="5b9c0-127">Bei Weglassen von `--global` und `--tool-path` werden lokale Tools aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="5b9c0-127">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

## <a name="examples"></a><span data-ttu-id="5b9c0-128">Beispiele</span><span class="sxs-lookup"><span data-stu-id="5b9c0-128">Examples</span></span>

- **`dotnet tool list -g`**

  <span data-ttu-id="5b9c0-129">Listet alle globale Tools auf, die benutzerweit auf Ihrem Computer installiert sind (aktuelles Benutzerprofil).</span><span class="sxs-lookup"><span data-stu-id="5b9c0-129">Lists all global tools installed user-wide on your machine (current user profile).</span></span>

- **`dotnet tool list --tool-path c:\global-tools`**

  <span data-ttu-id="5b9c0-130">Listet die globalen Tools in einem bestimmten Windows-Verzeichnis auf.</span><span class="sxs-lookup"><span data-stu-id="5b9c0-130">Lists the global tools from a specific Windows directory.</span></span>

- **`dotnet tool list --tool-path ~/bin`**

  <span data-ttu-id="5b9c0-131">Listet die globalen Tools in einem bestimmten Linux/macOS-Verzeichnis auf.</span><span class="sxs-lookup"><span data-stu-id="5b9c0-131">Lists the global tools from a specific Linux/macOS directory.</span></span>

- **`dotnet tool list`**

  <span data-ttu-id="5b9c0-132">Listet alle lokalen Tools auf, die im aktuellen Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5b9c0-132">Lists all local tools available in the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b9c0-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b9c0-133">See also</span></span>

- [<span data-ttu-id="5b9c0-134">.NET Core-Tools</span><span class="sxs-lookup"><span data-stu-id="5b9c0-134">.NET Core tools</span></span>](global-tools.md)
