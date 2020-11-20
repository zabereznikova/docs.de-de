---
title: Befehl „dotnet tool list“
description: Der Befehl „dotnet tool list“ listet die auf Ihrem Computer installierten .NET-Tools auf.
ms.date: 02/14/2020
ms.openlocfilehash: d884f2c41834dd9704de3a8ca15417ba368fde4b
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634284"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="48d68-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="48d68-103">dotnet tool list</span></span>

<span data-ttu-id="48d68-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="48d68-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="48d68-105">name</span><span class="sxs-lookup"><span data-stu-id="48d68-105">Name</span></span>

<span data-ttu-id="48d68-106">`dotnet tool list`: Der Befehl listet alle [.NET-Tools](global-tools.md) des angegebenen Typs auf, die derzeit auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="48d68-106">`dotnet tool list` - Lists all [.NET tools](global-tools.md) of the specified type currently installed on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="48d68-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="48d68-107">Synopsis</span></span>

```dotnetcli
dotnet tool list -g|--global

dotnet tool list --tool-path <PATH>

dotnet tool list --local

dotnet tool list

dotnet tool list -h|--help
```

## <a name="description"></a><span data-ttu-id="48d68-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48d68-108">Description</span></span>

<span data-ttu-id="48d68-109">Der Befehl `dotnet tool list` bietet die Ihnen Möglichkeit, alle globalen, tool-path- oder lokalen .NET-Tools aufzulisten, die auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="48d68-109">The `dotnet tool list` command provides a way for you to list all .NET global, tool-path, or local tools installed on your machine.</span></span> <span data-ttu-id="48d68-110">Der Befehl listet den Paketnamen, die installierte Version und den Befehl für das Tool auf.</span><span class="sxs-lookup"><span data-stu-id="48d68-110">The command lists the package name, version installed, and the tool command.</span></span>  <span data-ttu-id="48d68-111">Um den Befehl zu verwenden, geben Sie eine der folgenden Optionen an:</span><span class="sxs-lookup"><span data-stu-id="48d68-111">To use the command, you specify one of the following:</span></span>

* <span data-ttu-id="48d68-112">Verwenden Sie zum Auflisten globaler Tools am Standardspeicherort die Option `--global`.</span><span class="sxs-lookup"><span data-stu-id="48d68-112">To list global tools installed in the default location, use the `--global` option</span></span>
* <span data-ttu-id="48d68-113">Verwenden Sie zum Auflisten globaler Tools an einem benutzerdefinierten Speicherort die Option `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="48d68-113">To list global tools installed in a custom location, use the `--tool-path` option.</span></span>
* <span data-ttu-id="48d68-114">Verwenden Sie die Option `--local`, oder lassen Sie die Optionen `--global`, `--tool-path` und `--local` aus, um lokale Tools aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="48d68-114">To list local tools, use the `--local` option or omit the `--global`, `--tool-path`, and `--local` options.</span></span>

<span data-ttu-id="48d68-115">**Lokale Tools sind ab .NET Core SDK 3.0 verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="48d68-115">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="options"></a><span data-ttu-id="48d68-116">Optionen</span><span class="sxs-lookup"><span data-stu-id="48d68-116">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="48d68-117">Listet benutzerweite globale Tools auf.</span><span class="sxs-lookup"><span data-stu-id="48d68-117">Lists user-wide global tools.</span></span> <span data-ttu-id="48d68-118">Kann nicht mit der Option `--tool-path` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="48d68-118">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="48d68-119">Bei Weglassen von `--global` und `--tool-path` werden lokale Tools aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="48d68-119">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

- **`-h|--help`**

  <span data-ttu-id="48d68-120">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="48d68-120">Prints out a short help for the command.</span></span>

- **`--local`**

  <span data-ttu-id="48d68-121">Diese Option listet lokale Tools für das aktuelle Verzeichnis auf.</span><span class="sxs-lookup"><span data-stu-id="48d68-121">Lists local tools for the current directory.</span></span> <span data-ttu-id="48d68-122">Sie kann nicht mit der Option `--global` oder `--tool-path` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="48d68-122">Can't be combined with the `--global` or `--tool-path` options.</span></span> <span data-ttu-id="48d68-123">Wenn Sie sowohl `--global` als auch `--tool-path` auslassen, werden lokale Tools aufgelistet, auch wenn `--local` nicht angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="48d68-123">Omitting both `--global` and `--tool-path` lists local tools even if `--local` is not specified.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="48d68-124">Legt einen benutzerdefinierten Speicherort fest, an dem globale Tools gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="48d68-124">Specifies a custom location where to find global tools.</span></span> <span data-ttu-id="48d68-125">„PATH“ kann absolut oder relativ sein.</span><span class="sxs-lookup"><span data-stu-id="48d68-125">PATH can be absolute or relative.</span></span> <span data-ttu-id="48d68-126">Kann nicht mit der Option `--global` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="48d68-126">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="48d68-127">Bei Weglassen von `--global` und `--tool-path` werden lokale Tools aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="48d68-127">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

## <a name="examples"></a><span data-ttu-id="48d68-128">Beispiele</span><span class="sxs-lookup"><span data-stu-id="48d68-128">Examples</span></span>

- **`dotnet tool list -g`**

  <span data-ttu-id="48d68-129">Listet alle globale Tools auf, die benutzerweit auf Ihrem Computer installiert sind (aktuelles Benutzerprofil).</span><span class="sxs-lookup"><span data-stu-id="48d68-129">Lists all global tools installed user-wide on your machine (current user profile).</span></span>

- **`dotnet tool list --tool-path c:\global-tools`**

  <span data-ttu-id="48d68-130">Listet die globalen Tools in einem bestimmten Windows-Verzeichnis auf.</span><span class="sxs-lookup"><span data-stu-id="48d68-130">Lists the global tools from a specific Windows directory.</span></span>

- **`dotnet tool list --tool-path ~/bin`**

  <span data-ttu-id="48d68-131">Listet die globalen Tools in einem bestimmten Linux/macOS-Verzeichnis auf.</span><span class="sxs-lookup"><span data-stu-id="48d68-131">Lists the global tools from a specific Linux/macOS directory.</span></span>

- <span data-ttu-id="48d68-132">**`dotnet tool list`** oder **`dotnet tool list --local`**</span><span class="sxs-lookup"><span data-stu-id="48d68-132">**`dotnet tool list`** or **`dotnet tool list --local`**</span></span>

  <span data-ttu-id="48d68-133">Listet alle lokalen Tools auf, die im aktuellen Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="48d68-133">Lists all local tools available in the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="48d68-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48d68-134">See also</span></span>

- [<span data-ttu-id="48d68-135">.NET-Tools</span><span class="sxs-lookup"><span data-stu-id="48d68-135">.NET tools</span></span>](global-tools.md)
- [<span data-ttu-id="48d68-136">Tutorial: Installieren und Verwenden eines globalen .NET-Tools mithilfe der .NET-CLI</span><span class="sxs-lookup"><span data-stu-id="48d68-136">Tutorial: Install and use a .NET global tool using the .NET CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="48d68-137">Tutorial: Installieren und Verwenden eines lokalen .NET-Tools mithilfe der .NET-CLI</span><span class="sxs-lookup"><span data-stu-id="48d68-137">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>](local-tools-how-to-use.md)
