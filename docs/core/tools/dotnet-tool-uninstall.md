---
title: Befehl „dotnet tool uninstall“
description: Der Befehl „dotnet tool uninstall“ deinstalliert das angegebene .NET Core-Tool von Ihrem Computer.
ms.date: 02/14/2020
ms.openlocfilehash: 82799404c40baa3a39f4e2a5fdb414fb745ef448
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847832"
---
# <a name="dotnet-tool-uninstall"></a><span data-ttu-id="03241-103">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="03241-103">dotnet tool uninstall</span></span>

<span data-ttu-id="03241-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="03241-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="03241-105">name</span><span class="sxs-lookup"><span data-stu-id="03241-105">Name</span></span>

<span data-ttu-id="03241-106">`dotnet tool uninstall`: Deinstalliert das angegebene [.NET Core-Tool](global-tools.md) von Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="03241-106">`dotnet tool uninstall` - Uninstalls the specified [.NET Core tool](global-tools.md) from your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="03241-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="03241-107">Synopsis</span></span>

```dotnetcli
dotnet tool uninstall <PACKAGE_NAME> <-g|--global>

dotnet tool uninstall <PACKAGE_NAME> <--tool-path>

dotnet tool uninstall <PACKAGE_NAME>

dotnet tool uninstall <-h|--help>
```

## <a name="description"></a><span data-ttu-id="03241-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="03241-108">Description</span></span>

<span data-ttu-id="03241-109">Der `dotnet tool uninstall`-Befehl ermöglicht Ihnen das Deinstallieren von .NET Core-Tools von Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="03241-109">The `dotnet tool uninstall` command provides a way for you to uninstall .NET Core tools from your machine.</span></span> <span data-ttu-id="03241-110">Um den Befehl zu verwenden, geben Sie eine der folgenden Optionen an:</span><span class="sxs-lookup"><span data-stu-id="03241-110">To use the command, you specify one of the following options:</span></span>

* <span data-ttu-id="03241-111">Verwenden Sie zum Deinstallieren eines globalen Tools, das am Standardspeicherort installiert wurde, die Option `--global`.</span><span class="sxs-lookup"><span data-stu-id="03241-111">To uninstall a global tool that was installed in the default location, use the `--global` option.</span></span>
* <span data-ttu-id="03241-112">Verwenden Sie zum Deinstallieren eines globalen Tools, das an einem benutzerdefinierten Speicherort installiert wurde, die Option `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="03241-112">To uninstall a global tool that was installed in a custom location,  use the `--tool-path` option.</span></span>
* <span data-ttu-id="03241-113">Wenn Sie ein lokales Tool deinstallieren möchten, lassen Sie die Optionen `--global` und `--tool-path` weg.</span><span class="sxs-lookup"><span data-stu-id="03241-113">To uninstall a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="03241-114">**Lokale Tools sind ab .NET Core SDK 3.0 verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="03241-114">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="arguments"></a><span data-ttu-id="03241-115">Argumente</span><span class="sxs-lookup"><span data-stu-id="03241-115">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="03241-116">Name oder ID des NuGet-Pakets, das das zu deinstallierende .NET Core-Tool enthält.</span><span class="sxs-lookup"><span data-stu-id="03241-116">Name/ID of the NuGet package that contains the .NET Core tool to uninstall.</span></span> <span data-ttu-id="03241-117">Mithilfe des Befehls [dotnet tool list](dotnet-tool-list.md) können Sie den Paketnamen abrufen.</span><span class="sxs-lookup"><span data-stu-id="03241-117">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="03241-118">Optionen</span><span class="sxs-lookup"><span data-stu-id="03241-118">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="03241-119">Gibt an, dass das zu entfernende Tool von einer benutzerweiten Installation stammt.</span><span class="sxs-lookup"><span data-stu-id="03241-119">Specifies that the tool to be removed is from a user-wide installation.</span></span> <span data-ttu-id="03241-120">Kann nicht mit der Option `--tool-path` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="03241-120">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="03241-121">Durch Weglassen von `--global` und `--tool-path` wird angegeben, dass das zu entfernende Tool ein lokales Tool ist.</span><span class="sxs-lookup"><span data-stu-id="03241-121">Omitting both `--global` and `--tool-path` specifies that the tool to be removed is a local tool.</span></span>

- **`-h|--help`**

  <span data-ttu-id="03241-122">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="03241-122">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="03241-123">Gibt den Speicherort des Tools an, das deinstalliert wird.</span><span class="sxs-lookup"><span data-stu-id="03241-123">Specifies the location where to uninstall the tool.</span></span> <span data-ttu-id="03241-124">„PATH“ kann absolut oder relativ sein.</span><span class="sxs-lookup"><span data-stu-id="03241-124">PATH can be absolute or relative.</span></span> <span data-ttu-id="03241-125">Kann nicht mit der Option `--global` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="03241-125">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="03241-126">Durch Weglassen von `--global` und `--tool-path` wird angegeben, dass das zu entfernende Tool ein lokales Tool ist.</span><span class="sxs-lookup"><span data-stu-id="03241-126">Omitting both `--global` and `--tool-path` specifies that the tool to be removed is a local tool.</span></span>

## <a name="examples"></a><span data-ttu-id="03241-127">Beispiele</span><span class="sxs-lookup"><span data-stu-id="03241-127">Examples</span></span>

- **`dotnet tool uninstall -g dotnetsay`**

  <span data-ttu-id="03241-128">Deinstalliert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/).</span><span class="sxs-lookup"><span data-stu-id="03241-128">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool.</span></span>

- **`dotnet tool uninstall dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="03241-129">Deinstalliert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/) aus einem bestimmten Windows-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="03241-129">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool from a specific Windows directory.</span></span>

- **`dotnet tool uninstall dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="03241-130">Deinstalliert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/) aus einem bestimmten Linux/macOS-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="03241-130">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool from a specific Linux/macOS directory.</span></span>

- **`dotnet tool uninstall dotnetsay`**

  <span data-ttu-id="03241-131">Deinstalliert das lokale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/) aus dem aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="03241-131">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) local tool from the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="03241-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03241-132">See also</span></span>

- [<span data-ttu-id="03241-133">.NET Core-Tools</span><span class="sxs-lookup"><span data-stu-id="03241-133">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="03241-134">Tutorial: Erstellen und Verwenden eines globalen .NET Core-Tools mithilfe der .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="03241-134">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="03241-135">Tutorial: Erstellen und Verwenden eines lokalen .NET Core-Tools mithilfe der .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="03241-135">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
