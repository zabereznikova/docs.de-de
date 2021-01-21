---
title: Deinstallationstool
description: Eine Übersicht über das .NET Core-Deinstallationstool, ein Tool mit Anleitungen, das die kontrollierte Bereinigung von .NET Core SDKs und -Runtimes ermöglicht.
author: sfoslund
ms.date: 05/27/2020
ms.openlocfilehash: ed43b4ec8437ae0ccaf5f1234758dda9f16bd51e
ms.sourcegitcommit: 4f5f1855849cb02c3b610c7006ac21d7429f3348
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "98235351"
---
# <a name="net-core-uninstall-tool"></a><span data-ttu-id="81373-103">.NET Core-Deinstallationstool</span><span class="sxs-lookup"><span data-stu-id="81373-103">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="81373-104">Mit dem [.NET Core-Deinstallationstool](https://aka.ms/dotnet-core-uninstall-tool) (`dotnet-core-uninstall`) können Sie .NET Core SDKs und -Runtimes von einem System entfernen.</span><span class="sxs-lookup"><span data-stu-id="81373-104">The [.NET Core Uninstall Tool](https://aka.ms/dotnet-core-uninstall-tool) (`dotnet-core-uninstall`) lets you remove .NET Core SDKs and Runtimes from a system.</span></span> <span data-ttu-id="81373-105">Hierfür stehen Ihnen verschiedene Optionen zur Verfügung, mit denen Sie angeben können, welche Versionen deinstalliert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="81373-105">A collection of options is available to specify which versions you want to uninstall.</span></span>

<span data-ttu-id="81373-106">Das Tool unterstützt Windows und macOS.</span><span class="sxs-lookup"><span data-stu-id="81373-106">The tool supports Windows and macOS.</span></span> <span data-ttu-id="81373-107">Linux wird aktuell nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="81373-107">Linux is currently not supported.</span></span>

<span data-ttu-id="81373-108">Unter Windows kann das Tool nur SDKs und Runtimes deinstallieren, die mit einem der folgenden Installationsprogramme installiert wurden:</span><span class="sxs-lookup"><span data-stu-id="81373-108">On Windows, the tool can only uninstall SDKs and Runtimes that were installed using one of the following installers:</span></span>

- <span data-ttu-id="81373-109">.NET Core SDK- und -Runtime-Installer.</span><span class="sxs-lookup"><span data-stu-id="81373-109">The .NET Core SDK and runtime installer.</span></span>
- <span data-ttu-id="81373-110">Visual Studio-Installer in früheren Versionen als Visual Studio 2019, Version 16.3.</span><span class="sxs-lookup"><span data-stu-id="81373-110">The Visual Studio installer in versions earlier than Visual Studio 2019 version 16.3.</span></span>

<span data-ttu-id="81373-111">Unter macOS kann das Tool nur SDKs und Runtimes deinstallieren, die sich im Ordner */usr/local/share/dotnet* befinden.</span><span class="sxs-lookup"><span data-stu-id="81373-111">On macOS, the tool can only uninstall SDKs and runtimes located in the */usr/local/share/dotnet* folder.</span></span>

<span data-ttu-id="81373-112">Aufgrund dieser Einschränkungen ist das Tool möglicherweise nicht in der Lage, alle .NET Core SDKs und -Runtimes auf Ihrem Computer zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="81373-112">Because of these limitations, the tool may not be able to uninstall all of the .NET Core SDKs and runtimes on your machine.</span></span> <span data-ttu-id="81373-113">Mit dem Befehl `dotnet --info` können Sie alle installierten .NET Core SDKs und -Runtimes ermitteln, einschließlich der SDKs und Runtimes, die dieses Tool nicht entfernen kann.</span><span class="sxs-lookup"><span data-stu-id="81373-113">You can use the `dotnet --info` command to find all of the .NET Core SDKs and runtimes installed, including those SDKs and runtimes that this tool can't remove.</span></span> <span data-ttu-id="81373-114">Der Befehl `dotnet-core-uninstall list` zeigt an, welche SDKs mit dem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="81373-114">The `dotnet-core-uninstall list` command displays which SDKs can be uninstalled with the tool.</span></span> <span data-ttu-id="81373-115">Ab Version 1.2 und höher können SDKs und Runtimes mit Version 5.0 und früher deinstalliert werden. Auf früheren Versionen des Tools können SDKs und Runtimes mit Version 3.1 und früher deinstalliert werden.</span><span class="sxs-lookup"><span data-stu-id="81373-115">Versions 1.2 and later can uninstall SDKs and runtimes with version 5.0 or earlier, and previous versions of the tool can uninstall 3.1 and earlier.</span></span>

## <a name="install-the-tool"></a><span data-ttu-id="81373-116">Installieren des Tools</span><span class="sxs-lookup"><span data-stu-id="81373-116">Install the tool</span></span>

<span data-ttu-id="81373-117">Sie können das .NET Core-Tool für die Deinstallation auf der [Seite mit den Versionen des Tools](https://aka.ms/dotnet-core-uninstall-tool) herunterladen und den Quellcode im GitHub-Repository [dotnet/cli-lab](https://github.com/dotnet/cli-lab) finden.</span><span class="sxs-lookup"><span data-stu-id="81373-117">You can download the .NET Core Uninstall Tool from [the tool's releases page](https://aka.ms/dotnet-core-uninstall-tool) and find the source code at the [dotnet/cli-lab](https://github.com/dotnet/cli-lab) GitHub repository.</span></span>

> [!NOTE]
> <span data-ttu-id="81373-118">Für das Tool ist eine Erhöhung der Rechte erforderlich, um .NET Core SDKs und -Runtimes zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="81373-118">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="81373-119">Daher sollte es in einem Verzeichnis mit schreibgeschütztem Zugriff installiert werden, z. B. in *C:\Programme* unter Windows oder in */usr/local/bin* unter macOS.</span><span class="sxs-lookup"><span data-stu-id="81373-119">Therefore, it should be installed in a write-protected directory such as *C:\Program Files* on Windows or */usr/local/bin* on macOS.</span></span> <span data-ttu-id="81373-120">Weitere Informationen finden Sie unter [Erhöhte Zugriffsrechte für dotnet-Befehle](../tools/elevated-access.md).</span><span class="sxs-lookup"><span data-stu-id="81373-120">See also [Elevated access for dotnet commands](../tools/elevated-access.md).</span></span> <span data-ttu-id="81373-121">Weitere Informationen finden Sie unter [Ausführliche Installationsanweisungen](https://aka.ms/dotnet-core-uninstall-tool).</span><span class="sxs-lookup"><span data-stu-id="81373-121">For more information, see the [detailed installation instructions](https://aka.ms/dotnet-core-uninstall-tool).</span></span>

## <a name="run-the-tool"></a><span data-ttu-id="81373-122">Ausführen des Tools</span><span class="sxs-lookup"><span data-stu-id="81373-122">Run the tool</span></span>

<span data-ttu-id="81373-123">Die folgenden Schritte zeigen die empfohlene Vorgehensweise zum Ausführen des Deinstallationstools:</span><span class="sxs-lookup"><span data-stu-id="81373-123">The following steps show the recommended approach for running the uninstall tool:</span></span>

- [<span data-ttu-id="81373-124">Schritt 1: Anzeigen installierter .NET Core SDKs und -Runtimes</span><span class="sxs-lookup"><span data-stu-id="81373-124">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>](#step-1---display-installed-net-core-sdks-and-runtimes)
- [<span data-ttu-id="81373-125">Schritt 2: Ausführen eines Testlaufs</span><span class="sxs-lookup"><span data-stu-id="81373-125">Step 2 - Do a dry run</span></span>](#step-2---do-a-dry-run)
- [<span data-ttu-id="81373-126">Schritt 3: Deinstallieren von .NET Core SDKs und -Runtimes</span><span class="sxs-lookup"><span data-stu-id="81373-126">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>](#step-3---uninstall-net-core-sdks-and-runtimes)
- [<span data-ttu-id="81373-127">Schritt 4: Löschen des NuGet-Fallbackordners (optional)</span><span class="sxs-lookup"><span data-stu-id="81373-127">Step 4 - Delete the NuGet fallback folder (optional)</span></span>](#step-4---delete-the-nuget-fallback-folder-optional)

### <a name="step-1---display-installed-net-core-sdks-and-runtimes"></a><span data-ttu-id="81373-128">Schritt 1: Anzeigen installierter .NET Core SDKs und -Runtimes</span><span class="sxs-lookup"><span data-stu-id="81373-128">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>

<span data-ttu-id="81373-129">Der Befehl `dotnet-core-uninstall list` listet die installierten .NET Core SDKs und -Runtimes auf, die mit diesem Tool entfernt werden können.</span><span class="sxs-lookup"><span data-stu-id="81373-129">The `dotnet-core-uninstall list` command lists the installed .NET Core SDKs and runtimes that can be removed with this tool.</span></span> <span data-ttu-id="81373-130">Einige SDKs und Runtimes werden möglicherweise von Visual Studio benötigt, und es wird ein Hinweis angezeigt, warum es nicht empfohlen wird, diese zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="81373-130">Some SDKs and runtimes may be required by Visual Studio and they're displayed with a note of why it isn't recommended to uninstall them.</span></span>

> [!NOTE]
> <span data-ttu-id="81373-131">Die Ausgabe des `dotnet-core-uninstall list`-Befehls stimmt in den meisten Fällen nicht mit der Liste der installierten Versionen in der Ausgabe von `dotnet --info` überein.</span><span class="sxs-lookup"><span data-stu-id="81373-131">The output of the `dotnet-core-uninstall list` command will not match the list of installed versions in the output of `dotnet --info` in most cases.</span></span> <span data-ttu-id="81373-132">Insbesondere zeigt dieses Tool keine Versionen an, die über ZIP-Dateien installiert oder von Visual Studio verwaltet werden (alle Versionen, die mit Visual Studio 2019 16.3 oder höher installiert wurden).</span><span class="sxs-lookup"><span data-stu-id="81373-132">Specifically, this tool will not display versions installed by zip files or managed by Visual Studio (any version installed with Visual Studio 2019 16.3 or later).</span></span> <span data-ttu-id="81373-133">Eine Möglichkeit zur Überprüfung, ob eine Version von Visual Studio verwaltet wird, besteht darin, sie in `Add or Remove Programs` anzuzeigen. Hier werden in Visual Studio verwaltete Versionen in ihren Anzeigenamen als solche gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="81373-133">One way to check if a version is managed by Visual Studio is to view it in `Add or Remove Programs`, where Visual Studio managed versions are marked as such in their display names.</span></span>

<span data-ttu-id="81373-134">**dotnet-core-uninstall list**</span><span class="sxs-lookup"><span data-stu-id="81373-134">**dotnet-core-uninstall list**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="81373-135">Übersicht</span><span class="sxs-lookup"><span data-stu-id="81373-135">Synopsis</span></span>

```console
dotnet-core-uninstall list [options]
```

#### <a name="options"></a><span data-ttu-id="81373-136">Optionen</span><span class="sxs-lookup"><span data-stu-id="81373-136">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="81373-137">Windows</span><span class="sxs-lookup"><span data-stu-id="81373-137">Windows</span></span>](#tab/windows)

* **`--aspnet-runtime`**

  <span data-ttu-id="81373-138">Listet alle ASP.NET Core-Runtimes auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="81373-138">Lists all the ASP.NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="81373-139">Listet alle .NET Core-Hostingpakete auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="81373-139">Lists all the .NET Core hosting bundles that can be uninstalled with this tool.</span></span>

* **`--runtime`**

  <span data-ttu-id="81373-140">Listet alle .NET Core-Runtimes auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="81373-140">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="81373-141">Listet alle .NET Core SDKs auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="81373-141">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="81373-142">Legt den Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="81373-142">Sets the verbosity level.</span></span> <span data-ttu-id="81373-143">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="81373-143">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="81373-144">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="81373-144">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="81373-145">Listet alle x64-.NET Core SDKs und -Runtimes auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="81373-145">Lists all x64 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

* **`--x86`**

  <span data-ttu-id="81373-146">Listet alle x86-.NET Core SDKs und -Runtimes auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="81373-146">Lists all x86 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

## <a name="macos"></a>[<span data-ttu-id="81373-147">macOS</span><span class="sxs-lookup"><span data-stu-id="81373-147">macOS</span></span>](#tab/macos)

* **`--runtime`**

  <span data-ttu-id="81373-148">Listet alle .NET Core-Runtimes auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="81373-148">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="81373-149">Listet alle .NET Core SDKs auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="81373-149">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="81373-150">Legt den Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="81373-150">Sets the verbosity level.</span></span> <span data-ttu-id="81373-151">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="81373-151">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="81373-152">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="81373-152">The default value is `normal`.</span></span>
  
---

#### <a name="examples"></a><span data-ttu-id="81373-153">Beispiele</span><span class="sxs-lookup"><span data-stu-id="81373-153">Examples</span></span>

* <span data-ttu-id="81373-154">Listet alle .NET Core SDKs und -Runtimes auf, die mit diesem Tool entfernt werden können:</span><span class="sxs-lookup"><span data-stu-id="81373-154">List all .NET Core SDKs and runtimes that can be removed with this tool:</span></span>

  ```console
  dotnet-core-uninstall list
  ```

* <span data-ttu-id="81373-155">Listet alle  x64-.NET Core SDKs und -Runtimes auf:</span><span class="sxs-lookup"><span data-stu-id="81373-155">List all x64 .NET Core SDKs and runtimes:</span></span>

  ```console
  dotnet-core-uninstall list --x64
  ```

* <span data-ttu-id="81373-156">Listet aller x86-.NET Core SDKs auf:</span><span class="sxs-lookup"><span data-stu-id="81373-156">List all x86 .NET Core SDKs:</span></span>

  ```console
  dotnet-core-uninstall list --sdk --x86
  ```

### <a name="step-2---do-a-dry-run"></a><span data-ttu-id="81373-157">Schritt 2: Ausführen eines Testlaufs</span><span class="sxs-lookup"><span data-stu-id="81373-157">Step 2 - Do a dry run</span></span>

<span data-ttu-id="81373-158">Die Befehle `dotnet-core-uninstall dry-run` und `dotnet-core-uninstall whatif` zeigen die .NET Core SDKs und -Runtimes an, die auf der Grundlage der bereitgestellten Optionen ohne Ausführung der Deinstallation entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="81373-158">The `dotnet-core-uninstall dry-run` and `dotnet-core-uninstall whatif` commands display the .NET Core SDKs and runtimes that will be removed based on the options provided without performing the uninstall.</span></span> <span data-ttu-id="81373-159">Diese Befehle sind Synonyme.</span><span class="sxs-lookup"><span data-stu-id="81373-159">These commands are synonyms.</span></span>

<span data-ttu-id="81373-160">**dotnet-core-uninstall dry-run und dotnet-core-uninstall whatif**</span><span class="sxs-lookup"><span data-stu-id="81373-160">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="81373-161">Übersicht</span><span class="sxs-lookup"><span data-stu-id="81373-161">Synopsis</span></span>

```console
dotnet-core-uninstall dry-run [options] [<VERSION>...]

dotnet-core-uninstall whatif [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="81373-162">Argumente</span><span class="sxs-lookup"><span data-stu-id="81373-162">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="81373-163">Die angegebene Version, die deinstalliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="81373-163">The specified version to uninstall.</span></span> <span data-ttu-id="81373-164">Sie können mehrere Versionen nacheinander (getrennt durch Leerzeichen) auflisten.</span><span class="sxs-lookup"><span data-stu-id="81373-164">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="81373-165">Antwortdateien werden ebenfalls unterstützt.</span><span class="sxs-lookup"><span data-stu-id="81373-165">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="81373-166">Antwortdateien sind eine Alternative zum Eingeben aller Versionen in die Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="81373-166">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="81373-167">Dabei handelt es sich um Textdateien (in der Regel mit der Erweiterung „\*. rsp“), und jede Version wird in einer separaten Zeile aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="81373-167">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="81373-168">Um eine Antwortdatei für das `VERSION`-Argument anzugeben, verwenden Sie das Zeichen \@, direkt gefolgt vom Namen der Antwortdatei.</span><span class="sxs-lookup"><span data-stu-id="81373-168">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="81373-169">Optionen</span><span class="sxs-lookup"><span data-stu-id="81373-169">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="81373-170">Windows</span><span class="sxs-lookup"><span data-stu-id="81373-170">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="81373-171">Entfernt alle .NET Core SDKs und -Runtimes.</span><span class="sxs-lookup"><span data-stu-id="81373-171">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="81373-172">Entfernt nur die .NET Core SDKs und -Runtimes mit einer Version, die kleiner als die angegebene Version ist.</span><span class="sxs-lookup"><span data-stu-id="81373-172">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="81373-173">Die angegebene Version bleibt installiert.</span><span class="sxs-lookup"><span data-stu-id="81373-173">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="81373-174">Entfernt alle .NET Core SDKs und -Runtimes mit Ausnahme der angegebenen Versionen.</span><span class="sxs-lookup"><span data-stu-id="81373-174">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="81373-175">Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Version.</span><span class="sxs-lookup"><span data-stu-id="81373-175">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="81373-176">Entfernt .NET Core SDKs und -Runtimes, die durch höhere Patches abgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="81373-176">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="81373-177">Diese Option schützt „global.json“.</span><span class="sxs-lookup"><span data-stu-id="81373-177">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="81373-178">Entfernt .NET Core SDKs und -Runtimes, die als Vorschauversionen markiert sind.</span><span class="sxs-lookup"><span data-stu-id="81373-178">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="81373-179">Entfernt als Vorschauversion markierte .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Vorschau.</span><span class="sxs-lookup"><span data-stu-id="81373-179">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="81373-180">Entfernt nur ASP.NET Core-Runtimes.</span><span class="sxs-lookup"><span data-stu-id="81373-180">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="81373-181">Entfernt nur .NET Core-Runtime- und -Hostingpakete.</span><span class="sxs-lookup"><span data-stu-id="81373-181">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="81373-182">Entfernt .NET Core SDKs und -Runtimes, die der angegebenen `major.minor`-Version entsprechen.</span><span class="sxs-lookup"><span data-stu-id="81373-182">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="81373-183">Entfernt nur .NET Core-Runtimes.</span><span class="sxs-lookup"><span data-stu-id="81373-183">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="81373-184">Entfernt nur .NET Core SDKs.</span><span class="sxs-lookup"><span data-stu-id="81373-184">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="81373-185">Legt den Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="81373-185">Sets the verbosity level.</span></span> <span data-ttu-id="81373-186">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="81373-186">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="81373-187">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="81373-187">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="81373-188">Muss mit `--sdk`, `--runtime`und `--aspnet-runtime` verwendet werden, um x64-SDKs oder-Runtimes zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="81373-188">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="81373-189">Muss mit `--sdk`, `--runtime`und `--aspnet-runtime` verwendet werden, um x86-SDKs oder-Runtimes zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="81373-189">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="81373-190">**`--force`** Erzwingt das Entfernen von Versionen, die möglicherweise von Visual Studio verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="81373-190">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="81373-191">Notizen:</span><span class="sxs-lookup"><span data-stu-id="81373-191">Notes:</span></span>

1. <span data-ttu-id="81373-192">Genau ein Element `--sdk`, `--runtime`, `--aspnet-runtime` und `--hosting-bundle` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="81373-192">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="81373-193">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` und `[<VERSION>...]` sind exklusiv.</span><span class="sxs-lookup"><span data-stu-id="81373-193">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="81373-194">Wenn `--x64` oder `--x86` nicht angegeben wird, werden sowohl x64- als auch x86-Versionen entfernt.</span><span class="sxs-lookup"><span data-stu-id="81373-194">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="81373-195">macOS</span><span class="sxs-lookup"><span data-stu-id="81373-195">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="81373-196">Entfernt alle .NET Core SDKs und -Runtimes.</span><span class="sxs-lookup"><span data-stu-id="81373-196">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="81373-197">Entfernt .NET Core SDKs und -Runtimes mit einer kleineren als der angegebenen Version.</span><span class="sxs-lookup"><span data-stu-id="81373-197">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="81373-198">Die angegebene Version verbleibt auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="81373-198">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="81373-199">Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der angegebenen Versionen.</span><span class="sxs-lookup"><span data-stu-id="81373-199">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="81373-200">Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Version.</span><span class="sxs-lookup"><span data-stu-id="81373-200">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="81373-201">Entfernt .NET Core SDKs und -Runtimes, die durch höhere Patches abgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="81373-201">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="81373-202">Diese Option schützt „global.json“.</span><span class="sxs-lookup"><span data-stu-id="81373-202">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="81373-203">Entfernt .NET Core SDKs und -Runtimes, die als Vorschauversionen markiert sind.</span><span class="sxs-lookup"><span data-stu-id="81373-203">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="81373-204">Entfernt als Vorschauversion markierte .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Vorschau.</span><span class="sxs-lookup"><span data-stu-id="81373-204">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="81373-205">Entfernt .NET Core SDKs und -Runtimes, die der angegebenen `major.minor`-Version entsprechen.</span><span class="sxs-lookup"><span data-stu-id="81373-205">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="81373-206">Entfernt nur .NET Core-Runtimes.</span><span class="sxs-lookup"><span data-stu-id="81373-206">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="81373-207">Entfernt nur .NET Core SDKs.</span><span class="sxs-lookup"><span data-stu-id="81373-207">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="81373-208">Legt den Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="81373-208">Sets the verbosity level.</span></span> <span data-ttu-id="81373-209">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="81373-209">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="81373-210">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="81373-210">The default value is `normal`.</span></span>
  
* <span data-ttu-id="81373-211">**`--force`** Erzwingt das Entfernen von Versionen, die möglicherweise von Visual Studio oder SDKs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="81373-211">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="81373-212">Notizen:</span><span class="sxs-lookup"><span data-stu-id="81373-212">Notes:</span></span>

1. <span data-ttu-id="81373-213">Genau ein Element `--sdk` und `--runtime` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="81373-213">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="81373-214">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` und `[<VERSION>...]` sind exklusiv.</span><span class="sxs-lookup"><span data-stu-id="81373-214">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="81373-215">Beispiele</span><span class="sxs-lookup"><span data-stu-id="81373-215">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="81373-216">Standardmäßig sind .NET Core SDKs und -Runtimes, die möglicherweise von Visual Studio oder anderen SDKs benötigt werden, nicht in der Ausgabe von `dotnet-core-uninstall dry-run` enthalten.</span><span class="sxs-lookup"><span data-stu-id="81373-216">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are not included in `dotnet-core-uninstall dry-run` output.</span></span> <span data-ttu-id="81373-217">In den folgenden Beispielen sind einige der angegebenen SDKs und Runtimes abhängig vom Zustand des Computers möglicherweise nicht in der Ausgabe enthalten.</span><span class="sxs-lookup"><span data-stu-id="81373-217">In the following examples, some of the specified SDKs and runtimes may not be included in the output, depending on the state of the machine.</span></span> <span data-ttu-id="81373-218">Wenn Sie alle SDKs und Runtimes einbeziehen möchten, führen Sie diese explizit als Argumente auf, oder verwenden Sie die Option `--force`.</span><span class="sxs-lookup"><span data-stu-id="81373-218">To include all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="81373-219">Testlauf zum Entfernen aller .NET Core-Runtimes, die durch höhere Patches abgelöst wurden:</span><span class="sxs-lookup"><span data-stu-id="81373-219">Dry run of removing all .NET Core runtimes that have been superseded by higher patches:</span></span>

  ```console
  dotnet-core-uninstall dry-run --all-lower-patches --runtime
  ```

* <span data-ttu-id="81373-220">Testlauf zum Entfernen aller .NET Core SDKs mit einer kleineren Version als `2.2.301`:</span><span class="sxs-lookup"><span data-stu-id="81373-220">Dry run of removing all .NET Core SDKs below the version `2.2.301`:</span></span>

  ```console
  dotnet-core-uninstall whatif --all-below 2.2.301 --sdk
  ```

### <a name="step-3---uninstall-net-core-sdks-and-runtimes"></a><span data-ttu-id="81373-221">Schritt 3: Deinstallieren von .NET Core SDKs und -Runtimes</span><span class="sxs-lookup"><span data-stu-id="81373-221">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>

<span data-ttu-id="81373-222">`dotnet-core-uninstall remove` deinstalliert .NET Core SDKs und -Runtimes, die durch eine Sammlung von Optionen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="81373-222">`dotnet-core-uninstall remove` uninstalls .NET Core SDKs and Runtimes that are specified by a collection of options.</span></span> <span data-ttu-id="81373-223">Ab Version 1.2 und höher können SDKs und Runtimes mit Version 5.0 und früher deinstalliert werden. Auf früheren Versionen des Tools können SDKs und Runtimes mit Version 3.1 und früher deinstalliert werden.</span><span class="sxs-lookup"><span data-stu-id="81373-223">Versions 1.2 and later can uninstall SDKs and runtimes with version 5.0 or earlier, and previous versions of the tool can uninstall 3.1 and earlier.</span></span>

<span data-ttu-id="81373-224">Da dieses Tool ein destruktives Verhalten aufweist, wird **unbedingt** empfohlen, vor dem Ausführen des Entfernungsbefehls einen Testlauf auszuführen.</span><span class="sxs-lookup"><span data-stu-id="81373-224">Since this tool has a destructive behavior, it's **highly** recommended that you do a dry run before running the remove command.</span></span> <span data-ttu-id="81373-225">Der Testlauf zeigt Ihnen, welche .NET Core SDKs und -Runtimes entfernt werden, wenn Sie den Befehl `remove` verwenden.</span><span class="sxs-lookup"><span data-stu-id="81373-225">The dry run will show you what .NET Core SDKs and runtimes will be removed when you use the `remove` command.</span></span> <span data-ttu-id="81373-226">Lesen Sie [Sollte ich eine Version entfernen?](../install/remove-runtime-sdk-versions.md#should-i-remove-a-version), um zu erfahren, welche SDKs und Runtimes sicher entfernt werden können.</span><span class="sxs-lookup"><span data-stu-id="81373-226">Refer to [Should I remove a version?](../install/remove-runtime-sdk-versions.md#should-i-remove-a-version) to learn which SDKs and runtimes are safe to remove.</span></span>

> [!CAUTION]
> <span data-ttu-id="81373-227">Beachten Sie die folgenden Vorbehalte:</span><span class="sxs-lookup"><span data-stu-id="81373-227">Keep in mind the following caveats:</span></span>
>
>- <span data-ttu-id="81373-228">Dieses Tool kann Versionen des .NET Core SDK deinstallieren, die von `global.json`-Dateien auf Ihrem Computer benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="81373-228">This tool can uninstall versions of the .NET Core SDK that are required by `global.json` files on your machine.</span></span> <span data-ttu-id="81373-229">Sie können .NET Core SDKs über die Seite [.NET Core herunterladen](https://dotnet.microsoft.com/download/dotnet-core) erneut installieren.</span><span class="sxs-lookup"><span data-stu-id="81373-229">You can reinstall .NET Core SDKs from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="81373-230">Dieses Tool kann Versionen der .NET Core-Runtime deinstallieren, die von frameworkabhängigen Anwendungen auf Ihrem Computer benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="81373-230">This tool can uninstall versions of the .NET Core runtime that are required by framework dependent applications on your machine.</span></span> <span data-ttu-id="81373-231">Sie können .NET Core-Runtimes über die Seite [.NET Core herunterladen](https://dotnet.microsoft.com/download/dotnet-core) erneut installieren.</span><span class="sxs-lookup"><span data-stu-id="81373-231">You can reinstall .NET Core runtimes from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="81373-232">Dieses Tool kann Versionen des .NET Core SDK und der -Runtime deinstallieren, die von Visual Studio benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="81373-232">This tool can uninstall versions of the .NET Core SDK and runtime that Visual Studio relies on.</span></span> <span data-ttu-id="81373-233">Wenn Sie Ihre Visual Studio-Installation beschädigen, führen Sie „Reparieren“ im Visual Studio-Installer aus, um zu einem funktionsfähigen Zustand zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="81373-233">If you break your Visual Studio installation, run "Repair" in the Visual Studio installer to get back to a working state.</span></span>

<span data-ttu-id="81373-234">Standardmäßig behalten alle Befehle die .NET Core SDKs und -Runtimes bei, die möglicherweise von Visual Studio oder anderen SDKs benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="81373-234">By default, all commands keep the .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs.</span></span> <span data-ttu-id="81373-235">Diese SDKs und Runtimes können deinstalliert werden, indem sie explizit als Argumente aufgelistet werden oder indem die Option `--force` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="81373-235">These SDKs and runtimes can be uninstalled by listing them explicitly as arguments or by using the `--force` option.</span></span>

<span data-ttu-id="81373-236">Für das Tool ist eine Erhöhung der Rechte erforderlich, um .NET Core SDKs und -Runtimes zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="81373-236">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="81373-237">Führen Sie das Tool in einer Administratoreingabeaufforderung unter Windows und mit `sudo` unter macOS aus.</span><span class="sxs-lookup"><span data-stu-id="81373-237">Run the tool in an Administrator command prompt on Windows and with `sudo` on macOS.</span></span> <span data-ttu-id="81373-238">Die Befehle `dry-run` und `whatif` erfordern keine Erhöhung der Rechte.</span><span class="sxs-lookup"><span data-stu-id="81373-238">The `dry-run` and `whatif` commands don't require elevation.</span></span>

<span data-ttu-id="81373-239">**dotnet-core-uninstall remove**</span><span class="sxs-lookup"><span data-stu-id="81373-239">**dotnet-core-uninstall remove**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="81373-240">Übersicht</span><span class="sxs-lookup"><span data-stu-id="81373-240">Synopsis</span></span>

```console
dotnet-core-uninstall remove [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="81373-241">Argumente</span><span class="sxs-lookup"><span data-stu-id="81373-241">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="81373-242">Die angegebene Version, die deinstalliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="81373-242">The specified version to uninstall.</span></span> <span data-ttu-id="81373-243">Sie können mehrere Versionen nacheinander (getrennt durch Leerzeichen) auflisten.</span><span class="sxs-lookup"><span data-stu-id="81373-243">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="81373-244">Antwortdateien werden ebenfalls unterstützt.</span><span class="sxs-lookup"><span data-stu-id="81373-244">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="81373-245">Antwortdateien sind eine Alternative zum Eingeben aller Versionen in die Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="81373-245">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="81373-246">Dabei handelt es sich um Textdateien (in der Regel mit der Erweiterung „\*. rsp“), und jede Version wird in einer separaten Zeile aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="81373-246">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="81373-247">Um eine Antwortdatei für das `VERSION`-Argument anzugeben, verwenden Sie das Zeichen \@, direkt gefolgt vom Namen der Antwortdatei.</span><span class="sxs-lookup"><span data-stu-id="81373-247">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="81373-248">Optionen</span><span class="sxs-lookup"><span data-stu-id="81373-248">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="81373-249">Windows</span><span class="sxs-lookup"><span data-stu-id="81373-249">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="81373-250">Entfernt alle .NET Core SDKs und -Runtimes.</span><span class="sxs-lookup"><span data-stu-id="81373-250">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="81373-251">Entfernt nur die .NET Core SDKs und -Runtimes mit einer Version, die kleiner als die angegebene Version ist.</span><span class="sxs-lookup"><span data-stu-id="81373-251">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="81373-252">Die angegebene Version bleibt installiert.</span><span class="sxs-lookup"><span data-stu-id="81373-252">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="81373-253">Entfernt alle .NET Core SDKs und -Runtimes mit Ausnahme der angegebenen Versionen.</span><span class="sxs-lookup"><span data-stu-id="81373-253">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="81373-254">Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Version.</span><span class="sxs-lookup"><span data-stu-id="81373-254">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="81373-255">Entfernt .NET Core SDKs und -Runtimes, die durch höhere Patches abgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="81373-255">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="81373-256">Diese Option schützt „global.json“.</span><span class="sxs-lookup"><span data-stu-id="81373-256">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="81373-257">Entfernt .NET Core SDKs und -Runtimes, die als Vorschauversionen markiert sind.</span><span class="sxs-lookup"><span data-stu-id="81373-257">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="81373-258">Entfernt als Vorschauversion markierte .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Vorschau.</span><span class="sxs-lookup"><span data-stu-id="81373-258">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="81373-259">Entfernt nur ASP.NET Core-Runtimes.</span><span class="sxs-lookup"><span data-stu-id="81373-259">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="81373-260">Entfernt nur .NET Core-Hostingpakete</span><span class="sxs-lookup"><span data-stu-id="81373-260">Removes .NET Core hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="81373-261">Entfernt .NET Core SDKs und -Runtimes, die der angegebenen `major.minor`-Version entsprechen.</span><span class="sxs-lookup"><span data-stu-id="81373-261">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="81373-262">Entfernt nur .NET Core-Runtimes.</span><span class="sxs-lookup"><span data-stu-id="81373-262">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="81373-263">Entfernt nur .NET Core SDKs.</span><span class="sxs-lookup"><span data-stu-id="81373-263">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="81373-264">Legt den Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="81373-264">Sets the verbosity level.</span></span> <span data-ttu-id="81373-265">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="81373-265">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="81373-266">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="81373-266">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="81373-267">Muss mit `--sdk`, `--runtime`und `--aspnet-runtime` verwendet werden, um x64-SDKs oder-Runtimes zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="81373-267">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="81373-268">Muss mit `--sdk`, `--runtime`und `--aspnet-runtime` verwendet werden, um x86-SDKs oder-Runtimes zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="81373-268">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="81373-269">**`-y, --yes`** Führt den Befehl aus, ohne dass eine Bestätigung mit „Ja“ oder „Nein“ erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="81373-269">**`-y, --yes`** Executes the command without requiring a yes or no confirmation.</span></span>

* <span data-ttu-id="81373-270">**`--force`** Erzwingt das Entfernen von Versionen, die möglicherweise von Visual Studio verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="81373-270">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="81373-271">Notizen:</span><span class="sxs-lookup"><span data-stu-id="81373-271">Notes:</span></span>

1. <span data-ttu-id="81373-272">Genau ein Element `--sdk`, `--runtime`, `--aspnet-runtime` und `--hosting-bundle` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="81373-272">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="81373-273">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` und `[<VERSION>...]` sind exklusiv.</span><span class="sxs-lookup"><span data-stu-id="81373-273">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="81373-274">Wenn `--x64` oder `--x86` nicht angegeben wird, werden sowohl x64- als auch x86-Versionen entfernt.</span><span class="sxs-lookup"><span data-stu-id="81373-274">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="81373-275">macOS</span><span class="sxs-lookup"><span data-stu-id="81373-275">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="81373-276">Entfernt alle .NET Core SDKs und -Runtimes.</span><span class="sxs-lookup"><span data-stu-id="81373-276">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="81373-277">Entfernt .NET Core SDKs und -Runtimes mit einer kleineren als der angegebenen Version.</span><span class="sxs-lookup"><span data-stu-id="81373-277">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="81373-278">Die angegebene Version verbleibt auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="81373-278">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="81373-279">Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der angegebenen Versionen.</span><span class="sxs-lookup"><span data-stu-id="81373-279">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="81373-280">Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Version.</span><span class="sxs-lookup"><span data-stu-id="81373-280">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="81373-281">Entfernt .NET Core SDKs und -Runtimes, die durch höhere Patches abgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="81373-281">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="81373-282">Diese Option schützt „global.json“.</span><span class="sxs-lookup"><span data-stu-id="81373-282">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="81373-283">Entfernt .NET Core SDKs und -Runtimes, die als Vorschauversionen markiert sind.</span><span class="sxs-lookup"><span data-stu-id="81373-283">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="81373-284">Entfernt als Vorschauversion markierte .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Vorschau.</span><span class="sxs-lookup"><span data-stu-id="81373-284">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="81373-285">Entfernt .NET Core SDKs und -Runtimes, die der angegebenen `major.minor`-Version entsprechen.</span><span class="sxs-lookup"><span data-stu-id="81373-285">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="81373-286">Entfernt nur .NET Core-Runtimes.</span><span class="sxs-lookup"><span data-stu-id="81373-286">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="81373-287">Entfernt nur .NET Core SDKs.</span><span class="sxs-lookup"><span data-stu-id="81373-287">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="81373-288">Legt den Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="81373-288">Sets the verbosity level.</span></span> <span data-ttu-id="81373-289">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="81373-289">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="81373-290">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="81373-290">The default value is `normal`.</span></span>

* <span data-ttu-id="81373-291">**`-y, --yes`** Führt den Befehl aus, ohne dass eine J/N-Bestätigung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="81373-291">**`-y, --yes`** Executes the command without requiring Y/N confirmation.</span></span>
  
* <span data-ttu-id="81373-292">**`--force`** Erzwingt das Entfernen von Versionen, die möglicherweise von Visual Studio oder SDKs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="81373-292">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="81373-293">Notizen:</span><span class="sxs-lookup"><span data-stu-id="81373-293">Notes:</span></span>

1. <span data-ttu-id="81373-294">Genau ein Element `--sdk` und `--runtime` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="81373-294">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="81373-295">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` und `[<VERSION>...]` sind exklusiv.</span><span class="sxs-lookup"><span data-stu-id="81373-295">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="81373-296">Beispiele</span><span class="sxs-lookup"><span data-stu-id="81373-296">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="81373-297">Standardmäßig werden .NET Core SDKs und -Runtimes, die möglicherweise von Visual Studio oder anderen SDKs benötigt werden, beibehalten.</span><span class="sxs-lookup"><span data-stu-id="81373-297">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are kept.</span></span> <span data-ttu-id="81373-298">In den folgenden Beispielen bleiben einige der angegebenen SDKs und Runtimes abhängig vom Zustand des Computers ggf. erhalten.</span><span class="sxs-lookup"><span data-stu-id="81373-298">In the following examples, some of the specified SDKs and runtimes may remain, depending on the state of the machine.</span></span> <span data-ttu-id="81373-299">Wenn Sie alle SDKs und Runtimes entfernen möchten, führen Sie diese explizit als Argumente auf, oder verwenden Sie die Option `--force`.</span><span class="sxs-lookup"><span data-stu-id="81373-299">To remove all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="81373-300">Entfernen aller .NET Core-Runtimes mit Ausnahme der Version `3.0.0-preview6-27804-01`, ohne dass eine J/N-Bestätigung erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="81373-300">Remove all .NET Core runtimes except the version `3.0.0-preview6-27804-01` without requiring Y/N confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --all-but 3.0.0-preview6-27804-01 --runtime --yes
  ```

* <span data-ttu-id="81373-301">Entfernen aller .NET Core 1.1 SDKs, ohne dass eine J/N-Bestätigung erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="81373-301">Remove all .NET Core 1.1 SDKs without requiring Y/n confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --sdk --major-minor 1.1 -y
  ```

* <span data-ttu-id="81373-302">Entfernen des .NET Core 1.1.11 SDK ohne Konsolenausgabe:</span><span class="sxs-lookup"><span data-stu-id="81373-302">Remove the .NET Core 1.1.11 SDK with no console output:</span></span>

  ```console
  dotnet-core-uninstall remove 1.1.11 --sdk --yes --verbosity q
  ```

* <span data-ttu-id="81373-303">Entfernen aller .NET Core SDKs, die sicher von diesem Tool entfernt werden können:</span><span class="sxs-lookup"><span data-stu-id="81373-303">Remove all .NET Core SDKs that can safely be removed by this tool:</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk
  ```

* <span data-ttu-id="81373-304">Entfernen aller .NET Core SDKs, die von diesem Tool entfernt werden können, einschließlich der SDKs, die möglicherweise von Visual Studio benötigt werden (nicht empfohlen):</span><span class="sxs-lookup"><span data-stu-id="81373-304">Remove all .NET Core SDKs that can be removed by this tool, including those SDKs that may be required by Visual Studio (not recommended):</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk --force
  ```

* <span data-ttu-id="81373-305">Entfernen aller .NET Core SDKs, die in der Antwortdatei `versions.rsp` angegeben sind</span><span class="sxs-lookup"><span data-stu-id="81373-305">Remove all .NET Core SDKs that are specified in the response file `versions.rsp`</span></span>

  ```console
  dotnet-core-uninstall remove --sdk @versions.rsp
  ```

  <span data-ttu-id="81373-306">Der Inhalt von *versions.rsp* lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="81373-306">The content of *versions.rsp* is as follows:</span></span>
  
  ```text
  2.2.300
  2.1.700
  ```

### <a name="step-4---delete-the-nuget-fallback-folder-optional"></a><span data-ttu-id="81373-307">Schritt 4: Löschen des NuGet-Fallbackordners (optional)</span><span class="sxs-lookup"><span data-stu-id="81373-307">Step 4 - Delete the NuGet fallback folder (optional)</span></span>

<span data-ttu-id="81373-308">In einigen Fällen benötigen Sie `NuGetFallbackFolder` nicht mehr und möchten den Ordner ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="81373-308">In some cases, you no longer need the `NuGetFallbackFolder` and may wish to delete it.</span></span> <span data-ttu-id="81373-309">Weitere Informationen zum Löschen dieses Ordners finden Sie unter [Entfernen des Ordners „NuGetFallbackFolder“](../install/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span><span class="sxs-lookup"><span data-stu-id="81373-309">For more information about deleting this folder, see [Remove the NuGetFallbackFolder](../install/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span></span>

## <a name="uninstall-the-tool"></a><span data-ttu-id="81373-310">Deinstallieren des Tools</span><span class="sxs-lookup"><span data-stu-id="81373-310">Uninstall the tool</span></span>

## <a name="windows"></a>[<span data-ttu-id="81373-311">Windows</span><span class="sxs-lookup"><span data-stu-id="81373-311">Windows</span></span>](#tab/windows)

1. <span data-ttu-id="81373-312">Öffnen Sie **Software**.</span><span class="sxs-lookup"><span data-stu-id="81373-312">Open **Add or Remove Programs**.</span></span>
2. <span data-ttu-id="81373-313">Suchen Sie nach `Microsoft .NET Core SDK Uninstall Tool`.</span><span class="sxs-lookup"><span data-stu-id="81373-313">Search for `Microsoft .NET Core SDK Uninstall Tool`.</span></span>
3. <span data-ttu-id="81373-314">Wählen Sie **Deinstallieren** aus.</span><span class="sxs-lookup"><span data-stu-id="81373-314">Select **Uninstall**.</span></span>

## <a name="macos"></a>[<span data-ttu-id="81373-315">macOS</span><span class="sxs-lookup"><span data-stu-id="81373-315">macOS</span></span>](#tab/macos)

<span data-ttu-id="81373-316">Löschen Sie die heruntergeladene Datei *dotnet-core-uninstall.tar.gz* aus dem Verzeichnis, in dem sie installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="81373-316">Delete the downloaded *dotnet-core-uninstall.tar.gz* file from the directory where it was installed.</span></span> <span data-ttu-id="81373-317">Wenn Sie den Inhalt dieser Datei in ein anderes Verzeichnis entzippt haben, stellen Sie sicher, dass Sie auch diesen Inhalt löschen.</span><span class="sxs-lookup"><span data-stu-id="81373-317">If you unzipped the contents of this file into another directory, be sure to delete that content as well.</span></span>

---
