---
title: Deinstallationstool
description: Eine Übersicht über das .NET Core-Deinstallationstool, ein Tool mit Anleitungen, das die kontrollierte Bereinigung von .NET Core SDKs und -Runtimes ermöglicht.
author: sfoslund
ms.date: 05/27/2020
ms.openlocfilehash: 4e70fd3438b582bd5a0d6a52d7e58ed5e07f8811
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2020
ms.locfileid: "84446905"
---
# <a name="net-core-uninstall-tool"></a><span data-ttu-id="d399c-103">.NET Core-Deinstallationstool</span><span class="sxs-lookup"><span data-stu-id="d399c-103">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="d399c-104">Mit dem [.NET Core-Deinstallationstool](https://aka.ms/dotnet-core-uninstall-tool) (`dotnet-core-uninstall`) können Sie .NET Core SDKs und -Runtimes von einem System entfernen.</span><span class="sxs-lookup"><span data-stu-id="d399c-104">The [.NET Core Uninstall Tool](https://aka.ms/dotnet-core-uninstall-tool) (`dotnet-core-uninstall`) lets you remove .NET Core SDKs and Runtimes from a system.</span></span> <span data-ttu-id="d399c-105">Hierfür stehen Ihnen verschiedene Optionen zur Verfügung, mit denen Sie angeben können, welche Versionen deinstalliert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d399c-105">A collection of options is available to specify which versions you want to uninstall.</span></span>

<span data-ttu-id="d399c-106">Das Tool unterstützt Windows und macOS.</span><span class="sxs-lookup"><span data-stu-id="d399c-106">The tool supports Windows and macOS.</span></span> <span data-ttu-id="d399c-107">Linux wird aktuell nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d399c-107">Linux is currently not supported.</span></span>

<span data-ttu-id="d399c-108">Unter Windows kann das Tool nur SDKs und Runtimes deinstallieren, die mit einem der folgenden Installationsprogramme installiert wurden:</span><span class="sxs-lookup"><span data-stu-id="d399c-108">On Windows, the tool can only uninstall SDKs and Runtimes that were installed using one of the following installers:</span></span>

- <span data-ttu-id="d399c-109">.NET Core SDK- und -Runtime-Installer.</span><span class="sxs-lookup"><span data-stu-id="d399c-109">The .NET Core SDK and runtime installer.</span></span>
- <span data-ttu-id="d399c-110">Visual Studio-Installer in früheren Versionen als Visual Studio 2019, Version 16.3.</span><span class="sxs-lookup"><span data-stu-id="d399c-110">The Visual Studio installer in versions earlier than Visual Studio 2019 version 16.3.</span></span>

<span data-ttu-id="d399c-111">Unter macOS kann das Tool nur SDKs und Runtimes deinstallieren, die sich im Ordner */usr/local/share/dotnet* befinden.</span><span class="sxs-lookup"><span data-stu-id="d399c-111">On macOS, the tool can only uninstall SDKs and runtimes located in the */usr/local/share/dotnet* folder.</span></span>

<span data-ttu-id="d399c-112">Aufgrund dieser Einschränkungen ist das Tool möglicherweise nicht in der Lage, alle .NET Core SDKs und -Runtimes auf Ihrem Computer zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="d399c-112">Because of these limitations, the tool may not be able to uninstall all of the .NET Core SDKs and runtimes on your machine.</span></span> <span data-ttu-id="d399c-113">Mit dem Befehl `dotnet --info` können Sie alle installierten .NET Core SDKs und -Runtimes ermitteln, einschließlich der SDKs und Runtimes, die dieses Tool nicht entfernen kann.</span><span class="sxs-lookup"><span data-stu-id="d399c-113">You can use the `dotnet --info` command to find all of the .NET Core SDKs and runtimes installed, including those SDKs and runtimes that this tool can't remove.</span></span> <span data-ttu-id="d399c-114">Der Befehl `dotnet-core-uninstall list` zeigt an, welche SDKs mit dem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="d399c-114">The `dotnet-core-uninstall list` command displays which SDKs can be uninstalled with the tool.</span></span>

## <a name="install-the-tool"></a><span data-ttu-id="d399c-115">Installieren des Tools</span><span class="sxs-lookup"><span data-stu-id="d399c-115">Install the tool</span></span>

<span data-ttu-id="d399c-116">Sie können das .NET Core-Tool für die Deinstallation [hier](https://aka.ms/dotnet-core-uninstall-tool) herunterladen und den Quellcode im GitHub-Repository [dotnet/cli-lab](https://github.com/dotnet/cli-lab) finden.</span><span class="sxs-lookup"><span data-stu-id="d399c-116">You can download the .NET Core Uninstall Tool from [here](https://aka.ms/dotnet-core-uninstall-tool) and find the source code at the [dotnet/cli-lab](https://github.com/dotnet/cli-lab) GitHub repository.</span></span>

> [!NOTE]
> <span data-ttu-id="d399c-117">Für das Tool ist eine Erhöhung der Rechte erforderlich, um .NET Core SDKs und -Runtimes zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="d399c-117">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="d399c-118">Daher sollte es in einem Verzeichnis mit schreibgeschütztem Zugriff installiert werden, z. B. in *C:\Programme* unter Windows oder in */usr/local/bin* unter macOS.</span><span class="sxs-lookup"><span data-stu-id="d399c-118">Therefore, it should be installed in a write-protected directory such as *C:\Program Files* on Windows or */usr/local/bin* on macOS.</span></span> <span data-ttu-id="d399c-119">Weitere Informationen finden Sie unter [Erhöhte Zugriffsrechte für dotnet-Befehle](../tools/elevated-access.md).</span><span class="sxs-lookup"><span data-stu-id="d399c-119">See also [Elevated access for dotnet commands](../tools/elevated-access.md).</span></span> <span data-ttu-id="d399c-120">Weitere Informationen finden Sie unter [Ausführliche Installationsanweisungen](https://aka.ms/dotnet-core-uninstall-tool).</span><span class="sxs-lookup"><span data-stu-id="d399c-120">For more information, see the [detailed installation instructions](https://aka.ms/dotnet-core-uninstall-tool).</span></span>

## <a name="run-the-tool"></a><span data-ttu-id="d399c-121">Ausführen des Tools</span><span class="sxs-lookup"><span data-stu-id="d399c-121">Run the tool</span></span>

<span data-ttu-id="d399c-122">Die folgenden Schritte zeigen die empfohlene Vorgehensweise zum Ausführen des Deinstallationstools:</span><span class="sxs-lookup"><span data-stu-id="d399c-122">The following steps show the recommended approach for running the uninstall tool:</span></span>

- [<span data-ttu-id="d399c-123">Schritt 1: Anzeigen installierter .NET Core SDKs und -Runtimes</span><span class="sxs-lookup"><span data-stu-id="d399c-123">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>](#step-1---display-installed-net-core-sdks-and-runtimes)
- [<span data-ttu-id="d399c-124">Schritt 2: Ausführen eines Testlaufs</span><span class="sxs-lookup"><span data-stu-id="d399c-124">Step 2 - Do a dry run</span></span>](#step-2---do-a-dry-run)
- [<span data-ttu-id="d399c-125">Schritt 3: Deinstallieren von .NET Core SDKs und -Runtimes</span><span class="sxs-lookup"><span data-stu-id="d399c-125">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>](#step-3---uninstall-net-core-sdks-and-runtimes)
- [<span data-ttu-id="d399c-126">Schritt 4: Löschen des NuGet-Fallbackordners (optional)</span><span class="sxs-lookup"><span data-stu-id="d399c-126">Step 4 - Delete the NuGet fallback folder (optional)</span></span>](#step-4---delete-the-nuget-fallback-folder-optional)

### <a name="step-1---display-installed-net-core-sdks-and-runtimes"></a><span data-ttu-id="d399c-127">Schritt 1: Anzeigen installierter .NET Core SDKs und -Runtimes</span><span class="sxs-lookup"><span data-stu-id="d399c-127">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>

<span data-ttu-id="d399c-128">Der Befehl `dotnet-core-uninstall list` listet die installierten .NET Core SDKs und -Runtimes auf, die mit diesem Tool entfernt werden können.</span><span class="sxs-lookup"><span data-stu-id="d399c-128">The `dotnet-core-uninstall list` command lists the installed .NET Core SDKs and runtimes that can be removed with this tool.</span></span> <span data-ttu-id="d399c-129">Einige SDKs und Runtimes werden möglicherweise von Visual Studio benötigt, und es wird ein Hinweis angezeigt, warum es nicht empfohlen wird, diese zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="d399c-129">Some SDKs and runtimes may be required by Visual Studio and they're displayed with a note of why it isn't recommended to uninstall them.</span></span>

> [!NOTE]
> <span data-ttu-id="d399c-130">Die Ausgabe des `dotnet-core-uninstall list`-Befehls stimmt in den meisten Fällen nicht mit der Liste der installierten Versionen in der Ausgabe von `dotnet --info` überein.</span><span class="sxs-lookup"><span data-stu-id="d399c-130">The output of the `dotnet-core-uninstall list` command will not match the list of installed versions in the output of `dotnet --info` in most cases.</span></span> <span data-ttu-id="d399c-131">Insbesondere zeigt dieses Tool keine Versionen an, die über ZIP-Dateien installiert oder von Visual Studio verwaltet werden (alle Versionen, die mit Visual Studio 2019 16.3 oder höher installiert wurden).</span><span class="sxs-lookup"><span data-stu-id="d399c-131">Specifically, this tool will not display versions installed by zip files or managed by Visual Studio (any version installed with Visual Studio 2019 16.3 or later).</span></span> <span data-ttu-id="d399c-132">Eine Möglichkeit zur Überprüfung, ob eine Version von Visual Studio verwaltet wird, besteht darin, sie in `Add or Remove Programs` anzuzeigen. Hier werden in Visual Studio verwaltete Versionen in ihren Anzeigenamen als solche gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="d399c-132">One way to check if a version is managed by Visual Studio is to view it in `Add or Remove Programs`, where Visual Studio managed versions are marked as such in their display names.</span></span>

<span data-ttu-id="d399c-133">**dotnet-core-uninstall list**</span><span class="sxs-lookup"><span data-stu-id="d399c-133">**dotnet-core-uninstall list**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="d399c-134">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d399c-134">Synopsis</span></span>

```console
dotnet-core-uninstall list [options]
```

#### <a name="options"></a><span data-ttu-id="d399c-135">Optionen</span><span class="sxs-lookup"><span data-stu-id="d399c-135">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="d399c-136">Windows</span><span class="sxs-lookup"><span data-stu-id="d399c-136">Windows</span></span>](#tab/windows)

* **`--aspnet-runtime`**

  <span data-ttu-id="d399c-137">Listet alle ASP.NET Core-Runtimes auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="d399c-137">Lists all the ASP.NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="d399c-138">Listet alle .NET Core-Hostingpakete auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="d399c-138">Lists all the .NET Core hosting bundles that can be uninstalled with this tool.</span></span>

* **`--runtime`**

  <span data-ttu-id="d399c-139">Listet alle .NET Core-Runtimes auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="d399c-139">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="d399c-140">Listet alle .NET Core SDKs auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="d399c-140">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="d399c-141">Legt den Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="d399c-141">Sets the verbosity level.</span></span> <span data-ttu-id="d399c-142">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d399c-142">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="d399c-143">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="d399c-143">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="d399c-144">Listet alle x64-.NET Core SDKs und -Runtimes auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="d399c-144">Lists all x64 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

* **`--x86`**

  <span data-ttu-id="d399c-145">Listet alle x86-.NET Core SDKs und -Runtimes auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="d399c-145">Lists all x86 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

## <a name="macos"></a>[<span data-ttu-id="d399c-146">macOS</span><span class="sxs-lookup"><span data-stu-id="d399c-146">macOS</span></span>](#tab/macos)

* **`--runtime`**

  <span data-ttu-id="d399c-147">Listet alle .NET Core-Runtimes auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="d399c-147">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="d399c-148">Listet alle .NET Core SDKs auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="d399c-148">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="d399c-149">Legt den Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="d399c-149">Sets the verbosity level.</span></span> <span data-ttu-id="d399c-150">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d399c-150">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="d399c-151">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="d399c-151">The default value is `normal`.</span></span>
  
---

#### <a name="examples"></a><span data-ttu-id="d399c-152">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d399c-152">Examples</span></span>

* <span data-ttu-id="d399c-153">Listet alle .NET Core SDKs und -Runtimes auf, die mit diesem Tool entfernt werden können:</span><span class="sxs-lookup"><span data-stu-id="d399c-153">List all .NET Core SDKs and runtimes that can be removed with this tool:</span></span>

  ```console
  dotnet-core-uninstall list
  ```

* <span data-ttu-id="d399c-154">Listet alle  x64-.NET Core SDKs und -Runtimes auf:</span><span class="sxs-lookup"><span data-stu-id="d399c-154">List all x64 .NET Core SDKs and runtimes:</span></span>

  ```console
  dotnet-core-uninstall list --x64
  ```

* <span data-ttu-id="d399c-155">Listet aller x86-.NET Core SDKs auf:</span><span class="sxs-lookup"><span data-stu-id="d399c-155">List all x86 .NET Core SDKs:</span></span>

  ```console
  dotnet-core-uninstall list --sdk --x86
  ```

### <a name="step-2---do-a-dry-run"></a><span data-ttu-id="d399c-156">Schritt 2: Ausführen eines Testlaufs</span><span class="sxs-lookup"><span data-stu-id="d399c-156">Step 2 - Do a dry run</span></span>

<span data-ttu-id="d399c-157">Die Befehle `dotnet-core-uninstall dry-run` und `dotnet-core-uninstall whatif` zeigen die .NET Core SDKs und -Runtimes an, die auf der Grundlage der bereitgestellten Optionen ohne Ausführung der Deinstallation entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="d399c-157">The `dotnet-core-uninstall dry-run` and `dotnet-core-uninstall whatif` commands display the .NET Core SDKs and runtimes that will be removed based on the options provided without performing the uninstall.</span></span> <span data-ttu-id="d399c-158">Diese Befehle sind Synonyme.</span><span class="sxs-lookup"><span data-stu-id="d399c-158">These commands are synonyms.</span></span>

<span data-ttu-id="d399c-159">**dotnet-core-uninstall dry-run und dotnet-core-uninstall whatif**</span><span class="sxs-lookup"><span data-stu-id="d399c-159">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="d399c-160">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d399c-160">Synopsis</span></span>

```console
dotnet-core-uninstall dry-run [options] [<VERSION>...]

dotnet-core-uninstall whatif [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="d399c-161">Argumente</span><span class="sxs-lookup"><span data-stu-id="d399c-161">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="d399c-162">Die angegebene Version, die deinstalliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d399c-162">The specified version to uninstall.</span></span> <span data-ttu-id="d399c-163">Sie können mehrere Versionen nacheinander (getrennt durch Leerzeichen) auflisten.</span><span class="sxs-lookup"><span data-stu-id="d399c-163">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="d399c-164">Antwortdateien werden ebenfalls unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d399c-164">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="d399c-165">Antwortdateien sind eine Alternative zum Eingeben aller Versionen in die Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="d399c-165">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="d399c-166">Dabei handelt es sich um Textdateien (in der Regel mit der Erweiterung „\*. rsp“), und jede Version wird in einer separaten Zeile aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="d399c-166">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="d399c-167">Um eine Antwortdatei für das `VERSION`-Argument anzugeben, verwenden Sie das Zeichen \@, direkt gefolgt vom Namen der Antwortdatei.</span><span class="sxs-lookup"><span data-stu-id="d399c-167">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="d399c-168">Optionen</span><span class="sxs-lookup"><span data-stu-id="d399c-168">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="d399c-169">Windows</span><span class="sxs-lookup"><span data-stu-id="d399c-169">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="d399c-170">Entfernt alle .NET Core SDKs und -Runtimes.</span><span class="sxs-lookup"><span data-stu-id="d399c-170">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="d399c-171">Entfernt nur die .NET Core SDKs und -Runtimes mit einer Version, die kleiner als die angegebene Version ist.</span><span class="sxs-lookup"><span data-stu-id="d399c-171">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="d399c-172">Die angegebene Version bleibt installiert.</span><span class="sxs-lookup"><span data-stu-id="d399c-172">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="d399c-173">Entfernt alle .NET Core SDKs und -Runtimes mit Ausnahme der angegebenen Versionen.</span><span class="sxs-lookup"><span data-stu-id="d399c-173">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="d399c-174">Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Version.</span><span class="sxs-lookup"><span data-stu-id="d399c-174">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="d399c-175">Entfernt .NET Core SDKs und -Runtimes, die durch höhere Patches abgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="d399c-175">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="d399c-176">Diese Option schützt „global.json“.</span><span class="sxs-lookup"><span data-stu-id="d399c-176">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="d399c-177">Entfernt .NET Core SDKs und -Runtimes, die als Vorschauversionen markiert sind.</span><span class="sxs-lookup"><span data-stu-id="d399c-177">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="d399c-178">Entfernt als Vorschauversion markierte .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Vorschau.</span><span class="sxs-lookup"><span data-stu-id="d399c-178">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="d399c-179">Entfernt nur ASP.NET Core-Runtimes.</span><span class="sxs-lookup"><span data-stu-id="d399c-179">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="d399c-180">Entfernt nur .NET Core-Runtime- und -Hostingpakete.</span><span class="sxs-lookup"><span data-stu-id="d399c-180">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="d399c-181">Entfernt .NET Core SDKs und -Runtimes, die der angegebenen `major.minor`-Version entsprechen.</span><span class="sxs-lookup"><span data-stu-id="d399c-181">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="d399c-182">Entfernt nur .NET Core-Runtimes.</span><span class="sxs-lookup"><span data-stu-id="d399c-182">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="d399c-183">Entfernt nur .NET Core SDKs.</span><span class="sxs-lookup"><span data-stu-id="d399c-183">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="d399c-184">Legt den Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="d399c-184">Sets the verbosity level.</span></span> <span data-ttu-id="d399c-185">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d399c-185">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="d399c-186">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="d399c-186">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="d399c-187">Muss mit `--sdk`, `--runtime`und `--aspnet-runtime` verwendet werden, um x64-SDKs oder-Runtimes zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="d399c-187">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="d399c-188">Muss mit `--sdk`, `--runtime`und `--aspnet-runtime` verwendet werden, um x86-SDKs oder-Runtimes zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="d399c-188">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="d399c-189">**`--force`** Erzwingt das Entfernen von Versionen, die möglicherweise von Visual Studio verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d399c-189">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="d399c-190">Notizen:</span><span class="sxs-lookup"><span data-stu-id="d399c-190">Notes:</span></span>

1. <span data-ttu-id="d399c-191">Genau ein Element `--sdk`, `--runtime`, `--aspnet-runtime` und `--hosting-bundle` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d399c-191">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="d399c-192">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` und `[<VERSION>...]` sind exklusiv.</span><span class="sxs-lookup"><span data-stu-id="d399c-192">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="d399c-193">Wenn `--x64` oder `--x86` nicht angegeben wird, werden sowohl x64- als auch x86-Versionen entfernt.</span><span class="sxs-lookup"><span data-stu-id="d399c-193">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="d399c-194">macOS</span><span class="sxs-lookup"><span data-stu-id="d399c-194">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="d399c-195">Entfernt alle .NET Core SDKs und -Runtimes.</span><span class="sxs-lookup"><span data-stu-id="d399c-195">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="d399c-196">Entfernt .NET Core SDKs und -Runtimes mit einer kleineren als der angegebenen Version.</span><span class="sxs-lookup"><span data-stu-id="d399c-196">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="d399c-197">Die angegebene Version verbleibt auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="d399c-197">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="d399c-198">Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der angegebenen Versionen.</span><span class="sxs-lookup"><span data-stu-id="d399c-198">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="d399c-199">Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Version.</span><span class="sxs-lookup"><span data-stu-id="d399c-199">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="d399c-200">Entfernt .NET Core SDKs und -Runtimes, die durch höhere Patches abgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="d399c-200">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="d399c-201">Diese Option schützt „global.json“.</span><span class="sxs-lookup"><span data-stu-id="d399c-201">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="d399c-202">Entfernt .NET Core SDKs und -Runtimes, die als Vorschauversionen markiert sind.</span><span class="sxs-lookup"><span data-stu-id="d399c-202">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="d399c-203">Entfernt als Vorschauversion markierte .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Vorschau.</span><span class="sxs-lookup"><span data-stu-id="d399c-203">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="d399c-204">Entfernt .NET Core SDKs und -Runtimes, die der angegebenen `major.minor`-Version entsprechen.</span><span class="sxs-lookup"><span data-stu-id="d399c-204">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="d399c-205">Entfernt nur .NET Core-Runtimes.</span><span class="sxs-lookup"><span data-stu-id="d399c-205">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="d399c-206">Entfernt nur .NET Core SDKs.</span><span class="sxs-lookup"><span data-stu-id="d399c-206">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="d399c-207">Legt den Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="d399c-207">Sets the verbosity level.</span></span> <span data-ttu-id="d399c-208">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d399c-208">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="d399c-209">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="d399c-209">The default value is `normal`.</span></span>
  
* <span data-ttu-id="d399c-210">**`--force`** Erzwingt das Entfernen von Versionen, die möglicherweise von Visual Studio oder SDKs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d399c-210">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="d399c-211">Notizen:</span><span class="sxs-lookup"><span data-stu-id="d399c-211">Notes:</span></span>

1. <span data-ttu-id="d399c-212">Genau ein Element `--sdk` und `--runtime` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d399c-212">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="d399c-213">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` und `[<VERSION>...]` sind exklusiv.</span><span class="sxs-lookup"><span data-stu-id="d399c-213">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="d399c-214">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d399c-214">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="d399c-215">Standardmäßig sind .NET Core SDKs und -Runtimes, die möglicherweise von Visual Studio oder anderen SDKs benötigt werden, nicht in der Ausgabe von `dotnet-core-uninstall dry-run` enthalten.</span><span class="sxs-lookup"><span data-stu-id="d399c-215">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are not included in `dotnet-core-uninstall dry-run` output.</span></span> <span data-ttu-id="d399c-216">In den folgenden Beispielen sind einige der angegebenen SDKs und Runtimes abhängig vom Zustand des Computers möglicherweise nicht in der Ausgabe enthalten.</span><span class="sxs-lookup"><span data-stu-id="d399c-216">In the following examples, some of the specified SDKs and runtimes may not be included in the output, depending on the state of the machine.</span></span> <span data-ttu-id="d399c-217">Wenn Sie alle SDKs und Runtimes einbeziehen möchten, führen Sie diese explizit als Argumente auf, oder verwenden Sie die Option `--force`.</span><span class="sxs-lookup"><span data-stu-id="d399c-217">To include all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="d399c-218">Testlauf zum Entfernen aller .NET Core-Runtimes, die durch höhere Patches abgelöst wurden:</span><span class="sxs-lookup"><span data-stu-id="d399c-218">Dry run of removing all .NET Core runtimes that have been superseded by higher patches:</span></span>

  ```console
  dotnet-core-uninstall dry-run --all-lower-patches --runtime
  ```

* <span data-ttu-id="d399c-219">Testlauf zum Entfernen aller .NET Core SDKs mit einer kleineren Version als `2.2.301`:</span><span class="sxs-lookup"><span data-stu-id="d399c-219">Dry run of removing all .NET Core SDKs below the version `2.2.301`:</span></span>

  ```console
  dotnet-core-uninstall whatif --all-below 2.2.301 --sdk
  ```

### <a name="step-3---uninstall-net-core-sdks-and-runtimes"></a><span data-ttu-id="d399c-220">Schritt 3: Deinstallieren von .NET Core SDKs und -Runtimes</span><span class="sxs-lookup"><span data-stu-id="d399c-220">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>

<span data-ttu-id="d399c-221">`dotnet-core-uninstall remove` deinstalliert .NET Core SDKs und -Runtimes, die durch eine Sammlung von Optionen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d399c-221">`dotnet-core-uninstall remove` uninstalls .NET Core SDKs and Runtimes that are specified by a collection of options.</span></span> <span data-ttu-id="d399c-222">Das Tool kann nicht zum Deinstallieren von SDKs und Runtimes mit Version 5.0 oder höher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d399c-222">The tool can't be used to uninstall SDKs and Runtimes with version 5.0 or above.</span></span>

<span data-ttu-id="d399c-223">Da dieses Tool ein destruktives Verhalten aufweist, wird **unbedingt** empfohlen, vor dem Ausführen des Entfernungsbefehls einen Testlauf auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d399c-223">Since this tool has a destructive behavior, it's **highly** recommended that you do a dry run before running the remove command.</span></span> <span data-ttu-id="d399c-224">Der Testlauf zeigt Ihnen, welche .NET Core SDKs und -Runtimes entfernt werden, wenn Sie den Befehl `remove` verwenden.</span><span class="sxs-lookup"><span data-stu-id="d399c-224">The dry run will show you what .NET Core SDKs and runtimes will be removed when you use the `remove` command.</span></span> <span data-ttu-id="d399c-225">Lesen Sie [Sollte ich eine Version entfernen?](../install/remove-runtime-sdk-versions.md#should-i-remove-a-version), um zu erfahren, welche SDKs und Runtimes sicher entfernt werden können.</span><span class="sxs-lookup"><span data-stu-id="d399c-225">Refer to [Should I remove a version?](../install/remove-runtime-sdk-versions.md#should-i-remove-a-version) to learn which SDKs and runtimes are safe to remove.</span></span>

> [!CAUTION]
> <span data-ttu-id="d399c-226">Beachten Sie die folgenden Vorbehalte:</span><span class="sxs-lookup"><span data-stu-id="d399c-226">Keep in mind the following caveats:</span></span>
>
>- <span data-ttu-id="d399c-227">Dieses Tool kann Versionen des .NET Core SDK deinstallieren, die von `global.json`-Dateien auf Ihrem Computer benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="d399c-227">This tool can uninstall versions of the .NET Core SDK that are required by `global.json` files on your machine.</span></span> <span data-ttu-id="d399c-228">Sie können .NET Core SDKs über die Seite [.NET Core herunterladen](https://dotnet.microsoft.com/download/dotnet-core) erneut installieren.</span><span class="sxs-lookup"><span data-stu-id="d399c-228">You can reinstall .NET Core SDKs from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="d399c-229">Dieses Tool kann Versionen der .NET Core-Runtime deinstallieren, die von frameworkabhängigen Anwendungen auf Ihrem Computer benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="d399c-229">This tool can uninstall versions of the .NET Core runtime that are required by framework dependent applications on your machine.</span></span> <span data-ttu-id="d399c-230">Sie können .NET Core-Runtimes über die Seite [.NET Core herunterladen](https://dotnet.microsoft.com/download/dotnet-core) erneut installieren.</span><span class="sxs-lookup"><span data-stu-id="d399c-230">You can reinstall .NET Core runtimes from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="d399c-231">Dieses Tool kann Versionen des .NET Core SDK und der -Runtime deinstallieren, die von Visual Studio benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="d399c-231">This tool can uninstall versions of the .NET Core SDK and runtime that Visual Studio relies on.</span></span> <span data-ttu-id="d399c-232">Wenn Sie Ihre Visual Studio-Installation beschädigen, führen Sie „Reparieren“ im Visual Studio-Installer aus, um zu einem funktionsfähigen Zustand zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="d399c-232">If you break your Visual Studio installation, run "Repair" in the Visual Studio installer to get back to a working state.</span></span>

<span data-ttu-id="d399c-233">Standardmäßig behalten alle Befehle die .NET Core SDKs und -Runtimes bei, die möglicherweise von Visual Studio oder anderen SDKs benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="d399c-233">By default, all commands keep the .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs.</span></span> <span data-ttu-id="d399c-234">Diese SDKs und Runtimes können deinstalliert werden, indem sie explizit als Argumente aufgelistet werden oder indem die Option `--force` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d399c-234">These SDKs and runtimes can be uninstalled by listing them explicitly as arguments or by using the `--force` option.</span></span>

<span data-ttu-id="d399c-235">Für das Tool ist eine Erhöhung der Rechte erforderlich, um .NET Core SDKs und -Runtimes zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="d399c-235">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="d399c-236">Führen Sie das Tool in einer Administratoreingabeaufforderung unter Windows und mit `sudo` unter macOS aus.</span><span class="sxs-lookup"><span data-stu-id="d399c-236">Run the tool in an Administrator command prompt on Windows and with `sudo` on macOS.</span></span> <span data-ttu-id="d399c-237">Die Befehle `dry-run` und `whatif` erfordern keine Erhöhung der Rechte.</span><span class="sxs-lookup"><span data-stu-id="d399c-237">The `dry-run` and `whatif` commands don't require elevation.</span></span>

<span data-ttu-id="d399c-238">**dotnet-core-uninstall remove**</span><span class="sxs-lookup"><span data-stu-id="d399c-238">**dotnet-core-uninstall remove**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="d399c-239">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d399c-239">Synopsis</span></span>

```console
dotnet-core-uninstall remove [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="d399c-240">Argumente</span><span class="sxs-lookup"><span data-stu-id="d399c-240">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="d399c-241">Die angegebene Version, die deinstalliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d399c-241">The specified version to uninstall.</span></span> <span data-ttu-id="d399c-242">Sie können mehrere Versionen nacheinander (getrennt durch Leerzeichen) auflisten.</span><span class="sxs-lookup"><span data-stu-id="d399c-242">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="d399c-243">Antwortdateien werden ebenfalls unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d399c-243">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="d399c-244">Antwortdateien sind eine Alternative zum Eingeben aller Versionen in die Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="d399c-244">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="d399c-245">Dabei handelt es sich um Textdateien (in der Regel mit der Erweiterung „\*. rsp“), und jede Version wird in einer separaten Zeile aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="d399c-245">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="d399c-246">Um eine Antwortdatei für das `VERSION`-Argument anzugeben, verwenden Sie das Zeichen \@, direkt gefolgt vom Namen der Antwortdatei.</span><span class="sxs-lookup"><span data-stu-id="d399c-246">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="d399c-247">Optionen</span><span class="sxs-lookup"><span data-stu-id="d399c-247">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="d399c-248">Windows</span><span class="sxs-lookup"><span data-stu-id="d399c-248">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="d399c-249">Entfernt alle .NET Core SDKs und -Runtimes.</span><span class="sxs-lookup"><span data-stu-id="d399c-249">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="d399c-250">Entfernt nur die .NET Core SDKs und -Runtimes mit einer Version, die kleiner als die angegebene Version ist.</span><span class="sxs-lookup"><span data-stu-id="d399c-250">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="d399c-251">Die angegebene Version bleibt installiert.</span><span class="sxs-lookup"><span data-stu-id="d399c-251">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="d399c-252">Entfernt alle .NET Core SDKs und -Runtimes mit Ausnahme der angegebenen Versionen.</span><span class="sxs-lookup"><span data-stu-id="d399c-252">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="d399c-253">Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Version.</span><span class="sxs-lookup"><span data-stu-id="d399c-253">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="d399c-254">Entfernt .NET Core SDKs und -Runtimes, die durch höhere Patches abgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="d399c-254">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="d399c-255">Diese Option schützt „global.json“.</span><span class="sxs-lookup"><span data-stu-id="d399c-255">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="d399c-256">Entfernt .NET Core SDKs und -Runtimes, die als Vorschauversionen markiert sind.</span><span class="sxs-lookup"><span data-stu-id="d399c-256">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="d399c-257">Entfernt als Vorschauversion markierte .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Vorschau.</span><span class="sxs-lookup"><span data-stu-id="d399c-257">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="d399c-258">Entfernt nur ASP.NET Core-Runtimes.</span><span class="sxs-lookup"><span data-stu-id="d399c-258">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="d399c-259">Entfernt nur .NET Core-Hostingpakete</span><span class="sxs-lookup"><span data-stu-id="d399c-259">Removes .NET Core hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="d399c-260">Entfernt .NET Core SDKs und -Runtimes, die der angegebenen `major.minor`-Version entsprechen.</span><span class="sxs-lookup"><span data-stu-id="d399c-260">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="d399c-261">Entfernt nur .NET Core-Runtimes.</span><span class="sxs-lookup"><span data-stu-id="d399c-261">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="d399c-262">Entfernt nur .NET Core SDKs.</span><span class="sxs-lookup"><span data-stu-id="d399c-262">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="d399c-263">Legt den Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="d399c-263">Sets the verbosity level.</span></span> <span data-ttu-id="d399c-264">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d399c-264">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="d399c-265">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="d399c-265">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="d399c-266">Muss mit `--sdk`, `--runtime`und `--aspnet-runtime` verwendet werden, um x64-SDKs oder-Runtimes zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="d399c-266">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="d399c-267">Muss mit `--sdk`, `--runtime`und `--aspnet-runtime` verwendet werden, um x86-SDKs oder-Runtimes zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="d399c-267">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="d399c-268">**`-y, --yes`** Führt den Befehl aus, ohne dass eine Bestätigung mit „Ja“ oder „Nein“ erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d399c-268">**`-y, --yes`** Executes the command without requiring a yes or no confirmation.</span></span>

* <span data-ttu-id="d399c-269">**`--force`** Erzwingt das Entfernen von Versionen, die möglicherweise von Visual Studio verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d399c-269">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="d399c-270">Notizen:</span><span class="sxs-lookup"><span data-stu-id="d399c-270">Notes:</span></span>

1. <span data-ttu-id="d399c-271">Genau ein Element `--sdk`, `--runtime`, `--aspnet-runtime` und `--hosting-bundle` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d399c-271">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="d399c-272">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` und `[<VERSION>...]` sind exklusiv.</span><span class="sxs-lookup"><span data-stu-id="d399c-272">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="d399c-273">Wenn `--x64` oder `--x86` nicht angegeben wird, werden sowohl x64- als auch x86-Versionen entfernt.</span><span class="sxs-lookup"><span data-stu-id="d399c-273">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="d399c-274">macOS</span><span class="sxs-lookup"><span data-stu-id="d399c-274">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="d399c-275">Entfernt alle .NET Core SDKs und -Runtimes.</span><span class="sxs-lookup"><span data-stu-id="d399c-275">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="d399c-276">Entfernt .NET Core SDKs und -Runtimes mit einer kleineren als der angegebenen Version.</span><span class="sxs-lookup"><span data-stu-id="d399c-276">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="d399c-277">Die angegebene Version verbleibt auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="d399c-277">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="d399c-278">Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der angegebenen Versionen.</span><span class="sxs-lookup"><span data-stu-id="d399c-278">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="d399c-279">Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Version.</span><span class="sxs-lookup"><span data-stu-id="d399c-279">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="d399c-280">Entfernt .NET Core SDKs und -Runtimes, die durch höhere Patches abgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="d399c-280">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="d399c-281">Diese Option schützt „global.json“.</span><span class="sxs-lookup"><span data-stu-id="d399c-281">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="d399c-282">Entfernt .NET Core SDKs und -Runtimes, die als Vorschauversionen markiert sind.</span><span class="sxs-lookup"><span data-stu-id="d399c-282">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="d399c-283">Entfernt als Vorschauversion markierte .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Vorschau.</span><span class="sxs-lookup"><span data-stu-id="d399c-283">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="d399c-284">Entfernt .NET Core SDKs und -Runtimes, die der angegebenen `major.minor`-Version entsprechen.</span><span class="sxs-lookup"><span data-stu-id="d399c-284">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="d399c-285">Entfernt nur .NET Core-Runtimes.</span><span class="sxs-lookup"><span data-stu-id="d399c-285">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="d399c-286">Entfernt nur .NET Core SDKs.</span><span class="sxs-lookup"><span data-stu-id="d399c-286">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="d399c-287">Legt den Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="d399c-287">Sets the verbosity level.</span></span> <span data-ttu-id="d399c-288">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d399c-288">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="d399c-289">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="d399c-289">The default value is `normal`.</span></span>

* <span data-ttu-id="d399c-290">**`-y, --yes`** Führt den Befehl aus, ohne dass eine J/N-Bestätigung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d399c-290">**`-y, --yes`** Executes the command without requiring Y/N confirmation.</span></span>
  
* <span data-ttu-id="d399c-291">**`--force`** Erzwingt das Entfernen von Versionen, die möglicherweise von Visual Studio oder SDKs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d399c-291">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="d399c-292">Notizen:</span><span class="sxs-lookup"><span data-stu-id="d399c-292">Notes:</span></span>

1. <span data-ttu-id="d399c-293">Genau ein Element `--sdk` und `--runtime` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d399c-293">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="d399c-294">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` und `[<VERSION>...]` sind exklusiv.</span><span class="sxs-lookup"><span data-stu-id="d399c-294">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="d399c-295">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d399c-295">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="d399c-296">Standardmäßig werden .NET Core SDKs und -Runtimes, die möglicherweise von Visual Studio oder anderen SDKs benötigt werden, beibehalten.</span><span class="sxs-lookup"><span data-stu-id="d399c-296">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are kept.</span></span> <span data-ttu-id="d399c-297">In den folgenden Beispielen bleiben einige der angegebenen SDKs und Runtimes abhängig vom Zustand des Computers ggf. erhalten.</span><span class="sxs-lookup"><span data-stu-id="d399c-297">In the following examples, some of the specified SDKs and runtimes may remain, depending on the state of the machine.</span></span> <span data-ttu-id="d399c-298">Wenn Sie alle SDKs und Runtimes entfernen möchten, führen Sie diese explizit als Argumente auf, oder verwenden Sie die Option `--force`.</span><span class="sxs-lookup"><span data-stu-id="d399c-298">To remove all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="d399c-299">Entfernen aller .NET Core-Runtimes mit Ausnahme der Version `3.0.0-preview6-27804-01`, ohne dass eine J/N-Bestätigung erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="d399c-299">Remove all .NET Core runtimes except the version `3.0.0-preview6-27804-01` without requiring Y/N confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --all-but 3.0.0-preview6-27804-01 --runtime --yes
  ```

* <span data-ttu-id="d399c-300">Entfernen aller .NET Core 1.1 SDKs, ohne dass eine J/N-Bestätigung erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="d399c-300">Remove all .NET Core 1.1 SDKs without requiring Y/n confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --sdk --major-minor 1.1 -y
  ```

* <span data-ttu-id="d399c-301">Entfernen des .NET Core 1.1.11 SDK ohne Konsolenausgabe:</span><span class="sxs-lookup"><span data-stu-id="d399c-301">Remove the .NET Core 1.1.11 SDK with no console output:</span></span>

  ```console
  dotnet-core-uninstall remove 1.1.11 --sdk --yes --verbosity q
  ```

* <span data-ttu-id="d399c-302">Entfernen aller .NET Core SDKs, die sicher von diesem Tool entfernt werden können:</span><span class="sxs-lookup"><span data-stu-id="d399c-302">Remove all .NET Core SDKs that can safely be removed by this tool:</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk
  ```

* <span data-ttu-id="d399c-303">Entfernen aller .NET Core SDKs, die von diesem Tool entfernt werden können, einschließlich der SDKs, die möglicherweise von Visual Studio benötigt werden (nicht empfohlen):</span><span class="sxs-lookup"><span data-stu-id="d399c-303">Remove all .NET Core SDKs that can be removed by this tool, including those SDKs that may be required by Visual Studio (not recommended):</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk --force
  ```

* <span data-ttu-id="d399c-304">Entfernen aller .NET Core SDKs, die in der Antwortdatei `versions.rsp` angegeben sind</span><span class="sxs-lookup"><span data-stu-id="d399c-304">Remove all .NET Core SDKs that are specified in the response file `versions.rsp`</span></span>

  ```console
  dotnet-core-uninstall remove --sdk @versions.rsp
  ```

  <span data-ttu-id="d399c-305">Der Inhalt von *versions.rsp* lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d399c-305">The content of *versions.rsp* is as follows:</span></span>
  
  ```text
  2.2.300
  2.1.700
  ```

### <a name="step-4---delete-the-nuget-fallback-folder-optional"></a><span data-ttu-id="d399c-306">Schritt 4: Löschen des NuGet-Fallbackordners (optional)</span><span class="sxs-lookup"><span data-stu-id="d399c-306">Step 4 - Delete the NuGet fallback folder (optional)</span></span>

<span data-ttu-id="d399c-307">In einigen Fällen benötigen Sie `NuGetFallbackFolder` nicht mehr und möchten den Ordner ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="d399c-307">In some cases, you no longer need the `NuGetFallbackFolder` and may wish to delete it.</span></span> <span data-ttu-id="d399c-308">Weitere Informationen zum Löschen dieses Ordners finden Sie unter [Entfernen des Ordners „NuGetFallbackFolder“](../install/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span><span class="sxs-lookup"><span data-stu-id="d399c-308">For more information about deleting this folder, see [Remove the NuGetFallbackFolder](../install/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span></span>

## <a name="uninstall-the-tool"></a><span data-ttu-id="d399c-309">Deinstallieren des Tools</span><span class="sxs-lookup"><span data-stu-id="d399c-309">Uninstall the tool</span></span>

## <a name="windows"></a>[<span data-ttu-id="d399c-310">Windows</span><span class="sxs-lookup"><span data-stu-id="d399c-310">Windows</span></span>](#tab/windows)

1. <span data-ttu-id="d399c-311">Öffnen Sie **Software**.</span><span class="sxs-lookup"><span data-stu-id="d399c-311">Open **Add or Remove Programs**.</span></span>
2. <span data-ttu-id="d399c-312">Suchen Sie nach `Microsoft .NET Core SDK Uninstall Tool`.</span><span class="sxs-lookup"><span data-stu-id="d399c-312">Search for `Microsoft .NET Core SDK Uninstall Tool`.</span></span>
3. <span data-ttu-id="d399c-313">Wählen Sie **Deinstallieren** aus.</span><span class="sxs-lookup"><span data-stu-id="d399c-313">Select **Uninstall**.</span></span>

## <a name="macos"></a>[<span data-ttu-id="d399c-314">macOS</span><span class="sxs-lookup"><span data-stu-id="d399c-314">macOS</span></span>](#tab/macos)

<span data-ttu-id="d399c-315">Löschen Sie die heruntergeladene Datei *dotnet-core-uninstall.tar.gz* aus dem Verzeichnis, in dem sie installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="d399c-315">Delete the downloaded *dotnet-core-uninstall.tar.gz* file from the directory where it was installed.</span></span> <span data-ttu-id="d399c-316">Wenn Sie den Inhalt dieser Datei in ein anderes Verzeichnis entzippt haben, stellen Sie sicher, dass Sie auch diesen Inhalt löschen.</span><span class="sxs-lookup"><span data-stu-id="d399c-316">If you unzipped the contents of this file into another directory, be sure to delete that content as well.</span></span>

---
