---
title: Befehl „dotnet tool restore“
description: Der Befehl „dotnet tool restore“ installiert die lokalen .NET-Tools des aktuellen Verzeichnisses auf Ihrem Computer.
ms.date: 02/14/2020
ms.openlocfilehash: 1b7fd10102f2c957b3eb235f6897b60bc8ca9c07
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634271"
---
# <a name="dotnet-tool-restore"></a><span data-ttu-id="fa05b-103">dotnet tool restore</span><span class="sxs-lookup"><span data-stu-id="fa05b-103">dotnet tool restore</span></span>

<span data-ttu-id="fa05b-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="fa05b-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="fa05b-105">name</span><span class="sxs-lookup"><span data-stu-id="fa05b-105">Name</span></span>

<span data-ttu-id="fa05b-106">`dotnet tool restore`: Dieser Befehl installiert die lokalen .NET-Tools des aktuellen Verzeichnisses auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="fa05b-106">`dotnet tool restore` - Installs on your machine the .NET local tools that are in scope for the current directory.</span></span>

## <a name="synopsis"></a><span data-ttu-id="fa05b-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="fa05b-107">Synopsis</span></span>

```dotnetcli
dotnet tool restore
    [--configfile <FILE>] [--add-source <SOURCE>]
    [tool-manifest <PATH_TO_MANIFEST_FILE>] [--disable-parallel]
    [--ignore-failed-sources] [--no-cache] [--interactive]
    [-v|--verbosity <LEVEL>]

dotnet tool restore -h|--help
```

## <a name="description"></a><span data-ttu-id="fa05b-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa05b-108">Description</span></span>

<span data-ttu-id="fa05b-109">Der Befehl `dotnet tool restore` findet die Manifestdatei des Tools, die im Geltungsbereich des aktuellen Verzeichnisses liegt, und installiert die darin aufgelisteten Tools.</span><span class="sxs-lookup"><span data-stu-id="fa05b-109">The `dotnet tool restore` command finds the tool manifest file that is in scope for the current directory and installs the tools that are listed in it.</span></span> <span data-ttu-id="fa05b-110">Informationen zu Manifestdateien finden Sie unter [Installieren eines lokalen Tools](global-tools.md#install-a-local-tool) und [Aufrufen eines lokalen Tools](global-tools.md#invoke-a-local-tool).</span><span class="sxs-lookup"><span data-stu-id="fa05b-110">For information about manifest files, see [Install a local tool](global-tools.md#install-a-local-tool) and [Invoke a local tool](global-tools.md#invoke-a-local-tool).</span></span>

## <a name="options"></a><span data-ttu-id="fa05b-111">Optionen</span><span class="sxs-lookup"><span data-stu-id="fa05b-111">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="fa05b-112">Die zu verwendende NuGet-Konfigurationsdatei (*nuget.config*).</span><span class="sxs-lookup"><span data-stu-id="fa05b-112">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="fa05b-113">Fügt eine zusätzliche NuGet-Paketquelle für die Installation hinzu.</span><span class="sxs-lookup"><span data-stu-id="fa05b-113">Adds an additional NuGet package source to use during installation.</span></span>

- **`--tool-manifest <PATH>`**

  <span data-ttu-id="fa05b-114">Pfad zur Manifestdatei.</span><span class="sxs-lookup"><span data-stu-id="fa05b-114">Path to the manifest file.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="fa05b-115">Verhindert die parallele Wiederherstellung mehrerer Projekte.</span><span class="sxs-lookup"><span data-stu-id="fa05b-115">Prevent restoring multiple projects in parallel.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="fa05b-116">Paketquellenfehler werden als Warnungen behandelt.</span><span class="sxs-lookup"><span data-stu-id="fa05b-116">Treat package source failures as warnings.</span></span>

- **`--no-cache`**

  <span data-ttu-id="fa05b-117">Pakete und HTTP-Anforderungen werden nicht zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="fa05b-117">Do not cache packages and http requests.</span></span>

- **`--interactive`**

  <span data-ttu-id="fa05b-118">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten (z.B. um die Authentifizierung abzuschließen).</span><span class="sxs-lookup"><span data-stu-id="fa05b-118">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span>

- **`-h|--help`**

  <span data-ttu-id="fa05b-119">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="fa05b-119">Prints out a short help for the command.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="fa05b-120">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="fa05b-120">Sets the verbosity level of the command.</span></span> <span data-ttu-id="fa05b-121">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="fa05b-121">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="example"></a><span data-ttu-id="fa05b-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fa05b-122">Example</span></span>

- **`dotnet tool restore`**

  <span data-ttu-id="fa05b-123">Stellt lokale Tools für das aktuelle Verzeichnis wieder her.</span><span class="sxs-lookup"><span data-stu-id="fa05b-123">Restores local tools for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa05b-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa05b-124">See also</span></span>

- [<span data-ttu-id="fa05b-125">.NET-Tools</span><span class="sxs-lookup"><span data-stu-id="fa05b-125">.NET tools</span></span>](global-tools.md)
- [<span data-ttu-id="fa05b-126">Tutorial: Installieren und Verwenden eines lokalen .NET-Tools mithilfe der .NET-CLI</span><span class="sxs-lookup"><span data-stu-id="fa05b-126">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>](local-tools-how-to-use.md)
