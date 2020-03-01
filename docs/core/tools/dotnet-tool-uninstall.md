---
title: Befehl „dotnet tool uninstall“
description: Der Befehl „dotnet tool uninstall“ deinstalliert das angegebene .NET Core-Tool von Ihrem Computer.
ms.date: 02/14/2020
ms.openlocfilehash: 7a15c169c73cf5a743e0fa6f47645d6bccedbde3
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157044"
---
# <a name="dotnet-tool-uninstall"></a><span data-ttu-id="d5fb5-103">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="d5fb5-103">dotnet tool uninstall</span></span>

<span data-ttu-id="d5fb5-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="d5fb5-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="d5fb5-105">name</span><span class="sxs-lookup"><span data-stu-id="d5fb5-105">Name</span></span>

<span data-ttu-id="d5fb5-106">`dotnet tool uninstall`: Deinstalliert das angegebene [.NET Core-Tool](global-tools.md) von Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="d5fb5-106">`dotnet tool uninstall` - Uninstalls the specified [.NET Core tool](global-tools.md) from your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d5fb5-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d5fb5-107">Synopsis</span></span>

```dotnetcli
dotnet tool uninstall <PACKAGE_NAME> <-g|--global>
dotnet tool uninstall <PACKAGE_NAME> <--tool-path>
dotnet tool uninstall <PACKAGE_NAME>
dotnet tool uninstall <-h|--help>
```

## <a name="description"></a><span data-ttu-id="d5fb5-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5fb5-108">Description</span></span>

<span data-ttu-id="d5fb5-109">Der `dotnet tool uninstall`-Befehl ermöglicht Ihnen das Deinstallieren von .NET Core-Tools von Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="d5fb5-109">The `dotnet tool uninstall` command provides a way for you to uninstall .NET Core tools from your machine.</span></span> <span data-ttu-id="d5fb5-110">Um den Befehl zu verwenden, geben Sie eine der folgenden Optionen an:</span><span class="sxs-lookup"><span data-stu-id="d5fb5-110">To use the command, you specify one of the following options:</span></span>

* <span data-ttu-id="d5fb5-111">Verwenden Sie zum Deinstallieren eines globalen Tools, das am Standardspeicherort installiert wurde, die Option `--global`.</span><span class="sxs-lookup"><span data-stu-id="d5fb5-111">To uninstall a global tool that was installed in the default location, use the `--global` option.</span></span>
* <span data-ttu-id="d5fb5-112">Verwenden Sie zum Deinstallieren eines globalen Tools, das an einem benutzerdefinierten Speicherort installiert wurde, die Option `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="d5fb5-112">To uninstall a global tool that was installed in a custom location,  use the `--tool-path` option.</span></span>
* <span data-ttu-id="d5fb5-113">Wenn Sie ein lokales Tool deinstallieren möchten, lassen Sie die Optionen `--global` und `--tool-path` weg.</span><span class="sxs-lookup"><span data-stu-id="d5fb5-113">To uninstall a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="d5fb5-114">**Lokale Tools sind ab .NET Core SDK 3.0 verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="d5fb5-114">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="arguments"></a><span data-ttu-id="d5fb5-115">Argumente</span><span class="sxs-lookup"><span data-stu-id="d5fb5-115">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="d5fb5-116">Name oder ID des NuGet-Pakets, das das zu deinstallierende .NET Core-Tool enthält.</span><span class="sxs-lookup"><span data-stu-id="d5fb5-116">Name/ID of the NuGet package that contains the .NET Core tool to uninstall.</span></span> <span data-ttu-id="d5fb5-117">Mithilfe des Befehls [dotnet tool list](dotnet-tool-list.md) können Sie den Paketnamen abrufen.</span><span class="sxs-lookup"><span data-stu-id="d5fb5-117">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="d5fb5-118">Optionen</span><span class="sxs-lookup"><span data-stu-id="d5fb5-118">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="d5fb5-119">Gibt an, dass das zu entfernende Tool von einer benutzerweiten Installation stammt.</span><span class="sxs-lookup"><span data-stu-id="d5fb5-119">Specifies that the tool to be removed is from a user-wide installation.</span></span> <span data-ttu-id="d5fb5-120">Kann nicht mit der Option `--tool-path` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="d5fb5-120">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="d5fb5-121">Durch Weglassen von `--global` und `--tool-path` wird angegeben, dass das zu entfernende Tool ein lokales Tool ist.</span><span class="sxs-lookup"><span data-stu-id="d5fb5-121">Omitting both `--global` and `--tool-path` specifies that the tool to be removed is a local tool.</span></span>

- **`-h|--help`**

  <span data-ttu-id="d5fb5-122">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="d5fb5-122">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="d5fb5-123">Gibt den Speicherort des Tools an, das deinstalliert wird.</span><span class="sxs-lookup"><span data-stu-id="d5fb5-123">Specifies the location where to uninstall the tool.</span></span> <span data-ttu-id="d5fb5-124">„PATH“ kann absolut oder relativ sein.</span><span class="sxs-lookup"><span data-stu-id="d5fb5-124">PATH can be absolute or relative.</span></span> <span data-ttu-id="d5fb5-125">Kann nicht mit der Option `--global` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="d5fb5-125">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="d5fb5-126">Durch Weglassen von `--global` und `--tool-path` wird angegeben, dass das zu entfernende Tool ein lokales Tool ist.</span><span class="sxs-lookup"><span data-stu-id="d5fb5-126">Omitting both `--global` and `--tool-path` specifies that the tool to be removed is a local tool.</span></span>

## <a name="examples"></a><span data-ttu-id="d5fb5-127">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d5fb5-127">Examples</span></span>

- **`dotnet tool uninstall -g dotnetsay`**

  <span data-ttu-id="d5fb5-128">Deinstalliert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/).</span><span class="sxs-lookup"><span data-stu-id="d5fb5-128">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool.</span></span>

- **`dotnet tool uninstall dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="d5fb5-129">Deinstalliert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/) aus einem bestimmten Windows-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d5fb5-129">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool from a specific Windows directory.</span></span>

- **`dotnet tool uninstall dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="d5fb5-130">Deinstalliert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/) aus einem bestimmten Linux/macOS-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d5fb5-130">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool from a specific Linux/macOS directory.</span></span>

- **`dotnet tool uninstall dotnetsay`**

  <span data-ttu-id="d5fb5-131">Deinstalliert das lokale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/) aus dem aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d5fb5-131">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) local tool from the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5fb5-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5fb5-132">See also</span></span>

- [<span data-ttu-id="d5fb5-133">.NET Core-Tools</span><span class="sxs-lookup"><span data-stu-id="d5fb5-133">.NET Core tools</span></span>](global-tools.md)
