---
title: Befehl „dotnet tool list“
description: Der Befehl „dotnet tool list“ listet die auf Ihrem Computer installierten .NET Core-Tools auf.
ms.date: 02/14/2020
ms.openlocfilehash: 7ca894ab0f5daf0118ff92fb39e0118b952b3d83
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768273"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="6e4e5-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="6e4e5-103">dotnet tool list</span></span>

<span data-ttu-id="6e4e5-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="6e4e5-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="6e4e5-105">name</span><span class="sxs-lookup"><span data-stu-id="6e4e5-105">Name</span></span>

<span data-ttu-id="6e4e5-106">`dotnet tool list`: Listet alle [.NET Core-Tools](global-tools.md) des angegebenen Typs auf, der derzeit auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="6e4e5-106">`dotnet tool list` - Lists all [.NET Core tools](global-tools.md) of the specified type currently installed on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6e4e5-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="6e4e5-107">Synopsis</span></span>

```dotnetcli
dotnet tool list -g|--global

dotnet tool list --tool-path <PATH>

dotnet tool list --local

dotnet tool list

dotnet tool list -h|--help
```

## <a name="description"></a><span data-ttu-id="6e4e5-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6e4e5-108">Description</span></span>

<span data-ttu-id="6e4e5-109">Der Befehl `dotnet tool list` bietet die Möglichkeit, alle globalen, Toolpfad- oder lokalen .NET Core-Tools aufzulisten, die auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="6e4e5-109">The `dotnet tool list` command provides a way for you to list all .NET Core global, tool-path, or local tools installed on your machine.</span></span> <span data-ttu-id="6e4e5-110">Der Befehl listet den Paketnamen, die installierte Version und den Befehl für das Tool auf.</span><span class="sxs-lookup"><span data-stu-id="6e4e5-110">The command lists the package name, version installed, and the tool command.</span></span>  <span data-ttu-id="6e4e5-111">Um den Befehl zu verwenden, geben Sie eine der folgenden Optionen an:</span><span class="sxs-lookup"><span data-stu-id="6e4e5-111">To use the command, you specify one of the following:</span></span>

* <span data-ttu-id="6e4e5-112">Verwenden Sie zum Auflisten globaler Tools am Standardspeicherort die Option `--global`.</span><span class="sxs-lookup"><span data-stu-id="6e4e5-112">To list global tools installed in the default location, use the `--global` option</span></span>
* <span data-ttu-id="6e4e5-113">Verwenden Sie zum Auflisten globaler Tools an einem benutzerdefinierten Speicherort die Option `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="6e4e5-113">To list global tools installed in a custom location, use the `--tool-path` option.</span></span>
* <span data-ttu-id="6e4e5-114">Verwenden Sie zum Auflisten lokaler Tools</span><span class="sxs-lookup"><span data-stu-id="6e4e5-114">To list local tools, A local tool.</span></span> <span data-ttu-id="6e4e5-115">die Option `--local`, oder lassen Sie die Optionen `--global`, `--tool-path` und `--local` aus.</span><span class="sxs-lookup"><span data-stu-id="6e4e5-115">use the `--local` option or omit the `--global`, `--tool-path`, and `--local` options.</span></span>

<span data-ttu-id="6e4e5-116">**Lokale Tools sind ab .NET Core SDK 3.0 verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="6e4e5-116">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="options"></a><span data-ttu-id="6e4e5-117">Optionen</span><span class="sxs-lookup"><span data-stu-id="6e4e5-117">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="6e4e5-118">Listet benutzerweite globale Tools auf.</span><span class="sxs-lookup"><span data-stu-id="6e4e5-118">Lists user-wide global tools.</span></span> <span data-ttu-id="6e4e5-119">Kann nicht mit der Option `--tool-path` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="6e4e5-119">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="6e4e5-120">Bei Weglassen von `--global` und `--tool-path` werden lokale Tools aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="6e4e5-120">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

- **`-h|--help`**

  <span data-ttu-id="6e4e5-121">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="6e4e5-121">Prints out a short help for the command.</span></span>

- **`--local`**

  <span data-ttu-id="6e4e5-122">Diese Option listet lokale Tools für das aktuelle Verzeichnis auf.</span><span class="sxs-lookup"><span data-stu-id="6e4e5-122">Lists local tools for the current directory.</span></span> <span data-ttu-id="6e4e5-123">Sie kann nicht mit der Option `--global` oder `--tool-path` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="6e4e5-123">Can't be combined with the `--global` or `--tool-path` options.</span></span> <span data-ttu-id="6e4e5-124">Wenn Sie sowohl `--global` als auch `--tool-path` auslassen, werden lokale Tools aufgelistet, auch wenn `--local` nicht angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6e4e5-124">Omitting both `--global` and `--tool-path` lists local tools even if `--local` is not specified.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="6e4e5-125">Legt einen benutzerdefinierten Speicherort fest, an dem globale Tools gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="6e4e5-125">Specifies a custom location where to find global tools.</span></span> <span data-ttu-id="6e4e5-126">„PATH“ kann absolut oder relativ sein.</span><span class="sxs-lookup"><span data-stu-id="6e4e5-126">PATH can be absolute or relative.</span></span> <span data-ttu-id="6e4e5-127">Kann nicht mit der Option `--global` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="6e4e5-127">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="6e4e5-128">Bei Weglassen von `--global` und `--tool-path` werden lokale Tools aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="6e4e5-128">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

## <a name="examples"></a><span data-ttu-id="6e4e5-129">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6e4e5-129">Examples</span></span>

- **`dotnet tool list -g`**

  <span data-ttu-id="6e4e5-130">Listet alle globale Tools auf, die benutzerweit auf Ihrem Computer installiert sind (aktuelles Benutzerprofil).</span><span class="sxs-lookup"><span data-stu-id="6e4e5-130">Lists all global tools installed user-wide on your machine (current user profile).</span></span>

- **`dotnet tool list --tool-path c:\global-tools`**

  <span data-ttu-id="6e4e5-131">Listet die globalen Tools in einem bestimmten Windows-Verzeichnis auf.</span><span class="sxs-lookup"><span data-stu-id="6e4e5-131">Lists the global tools from a specific Windows directory.</span></span>

- **`dotnet tool list --tool-path ~/bin`**

  <span data-ttu-id="6e4e5-132">Listet die globalen Tools in einem bestimmten Linux/macOS-Verzeichnis auf.</span><span class="sxs-lookup"><span data-stu-id="6e4e5-132">Lists the global tools from a specific Linux/macOS directory.</span></span>

- <span data-ttu-id="6e4e5-133">**`dotnet tool list`** oder **`dotnet tool list --local`**</span><span class="sxs-lookup"><span data-stu-id="6e4e5-133">**`dotnet tool list`** or **`dotnet tool list --local`**</span></span>

  <span data-ttu-id="6e4e5-134">Listet alle lokalen Tools auf, die im aktuellen Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="6e4e5-134">Lists all local tools available in the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e4e5-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e4e5-135">See also</span></span>

- [<span data-ttu-id="6e4e5-136">.NET Core-Tools</span><span class="sxs-lookup"><span data-stu-id="6e4e5-136">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="6e4e5-137">Tutorial: Erstellen und Verwenden eines globalen .NET Core-Tools mithilfe der .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="6e4e5-137">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="6e4e5-138">Tutorial: Erstellen und Verwenden eines lokalen .NET Core-Tools mithilfe der .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="6e4e5-138">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
