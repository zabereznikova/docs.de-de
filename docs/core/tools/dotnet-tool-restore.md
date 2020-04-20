---
title: Befehl „dotnet tool restore“
description: Der Befehl dotnet tool restore installiert auf Ihrem Computer die lokalen .NET Core-Tools, die im Geltungsbereich des aktuellen Verzeichnisses liegen.
ms.date: 02/14/2020
ms.openlocfilehash: a518c2d45bbe9522bddfed4bbef61b30f1ad634b
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463335"
---
# <a name="dotnet-tool-restore"></a><span data-ttu-id="2c14f-103">dotnet tool restore</span><span class="sxs-lookup"><span data-stu-id="2c14f-103">dotnet tool restore</span></span>

<span data-ttu-id="2c14f-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="2c14f-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="2c14f-105">name</span><span class="sxs-lookup"><span data-stu-id="2c14f-105">Name</span></span>

<span data-ttu-id="2c14f-106">`dotnet tool restore`: installiert auf Ihrem Computer die lokalen .NET Core-Tools, die im Geltungsbereich des aktuellen Verzeichnisses liegen.</span><span class="sxs-lookup"><span data-stu-id="2c14f-106">`dotnet tool restore` - Installs on your machine the .NET Core local tools that are in scope for the current directory.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2c14f-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="2c14f-107">Synopsis</span></span>

```dotnetcli
dotnet tool restore <PACKAGE_NAME>
    [--configfile <FILE>] [--add-source <SOURCE>]
    [tool-manifest <PATH_TO_MANIFEST_FILE>] [--disable-parallel]
    [--ignore-failed-sources] [--no-cache] [--interactive]
    [-v|--verbosity <LEVEL>]

dotnet tool restore -h|--help
```

## <a name="description"></a><span data-ttu-id="2c14f-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c14f-108">Description</span></span>

<span data-ttu-id="2c14f-109">Der Befehl `dotnet tool restore` findet die Manifestdatei des Tools, die im Geltungsbereich des aktuellen Verzeichnisses liegt, und installiert die darin aufgelisteten Tools.</span><span class="sxs-lookup"><span data-stu-id="2c14f-109">The `dotnet tool restore` command finds the tool manifest file that is in scope for the current directory and installs the tools that are listed in it.</span></span> <span data-ttu-id="2c14f-110">Informationen zu Manifestdateien finden Sie unter [Installieren eines lokalen Tools](global-tools.md#install-a-local-tool) und [Aufrufen eines lokalen Tools](global-tools.md#invoke-a-local-tool).</span><span class="sxs-lookup"><span data-stu-id="2c14f-110">For information about manifest files, see [Install a local tool](global-tools.md#install-a-local-tool) and [Invoke a local tool](global-tools.md#invoke-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="2c14f-111">Argumente</span><span class="sxs-lookup"><span data-stu-id="2c14f-111">Arguments</span></span>

- **`PACKAGE_NAME`**

<span data-ttu-id="2c14f-112">Name oder ID des NuGet-Pakets, das das zu installierende .NET Core-Tool enthält.</span><span class="sxs-lookup"><span data-stu-id="2c14f-112">Name/ID of the NuGet package that contains the .NET Core tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="2c14f-113">Optionen</span><span class="sxs-lookup"><span data-stu-id="2c14f-113">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="2c14f-114">Die zu verwendende NuGet-Konfigurationsdatei (*nuget.config*).</span><span class="sxs-lookup"><span data-stu-id="2c14f-114">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="2c14f-115">Fügt eine zusätzliche NuGet-Paketquelle für die Installation hinzu.</span><span class="sxs-lookup"><span data-stu-id="2c14f-115">Adds an additional NuGet package source to use during installation.</span></span>

- **`--tool-manifest <PATH>`**

  <span data-ttu-id="2c14f-116">Pfad zur Manifestdatei.</span><span class="sxs-lookup"><span data-stu-id="2c14f-116">Path to the manifest file.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="2c14f-117">Verhindert die parallele Wiederherstellung mehrerer Projekte.</span><span class="sxs-lookup"><span data-stu-id="2c14f-117">Prevent restoring multiple projects in parallel.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="2c14f-118">Paketquellenfehler werden als Warnungen behandelt.</span><span class="sxs-lookup"><span data-stu-id="2c14f-118">Treat package source failures as warnings.</span></span>

- **`--no-cache`**

  <span data-ttu-id="2c14f-119">Pakete und HTTP-Anforderungen werden nicht zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="2c14f-119">Do not cache packages and http requests.</span></span>

- **`--interactive`**

  <span data-ttu-id="2c14f-120">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten (z.B. um die Authentifizierung abzuschließen).</span><span class="sxs-lookup"><span data-stu-id="2c14f-120">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span>

- **`-h|--help`**

  <span data-ttu-id="2c14f-121">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="2c14f-121">Prints out a short help for the command.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="2c14f-122">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="2c14f-122">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2c14f-123">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="2c14f-123">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="example"></a><span data-ttu-id="2c14f-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2c14f-124">Example</span></span>

- **`dotnet tool restore`**

  <span data-ttu-id="2c14f-125">Stellt lokale Tools für das aktuelle Verzeichnis wieder her.</span><span class="sxs-lookup"><span data-stu-id="2c14f-125">Restores local tools for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c14f-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c14f-126">See also</span></span>

- [<span data-ttu-id="2c14f-127">.NET Core-Tools</span><span class="sxs-lookup"><span data-stu-id="2c14f-127">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="2c14f-128">Tutorial: Erstellen und Verwenden eines lokalen .NET Core-Tools mithilfe der .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="2c14f-128">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
