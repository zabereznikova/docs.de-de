---
title: Deinstallationstool
description: Eine Übersicht über das .NET Core-Deinstallationstool, ein Tool mit Anleitungen, das die kontrollierte Bereinigung von .NET Core SDKs und -Runtimes ermöglicht.
author: sfoslund
ms.date: 01/06/2020
ms.openlocfilehash: 4944c983cbd02b456c3a09a1b03bc28ba6e458cc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714553"
---
# <a name="net-core-uninstall-tool"></a><span data-ttu-id="b205f-103">.NET Core-Deinstallationstool</span><span class="sxs-lookup"><span data-stu-id="b205f-103">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="b205f-104">Mit dem [.NET Core-Deinstallationstool](https://github.com/dotnet/cli-lab/releases) (`dotnet-core-uninstall`) können Sie .NET Core SDKs und -Runtimes von einem System entfernen.</span><span class="sxs-lookup"><span data-stu-id="b205f-104">The [.NET Core Uninstall Tool](https://github.com/dotnet/cli-lab/releases) (`dotnet-core-uninstall`) lets you remove .NET Core SDKs and Runtimes from a system.</span></span> <span data-ttu-id="b205f-105">Hierfür stehen Ihnen verschiedene Optionen zur Verfügung, mit denen Sie angeben können, welche Versionen deinstalliert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b205f-105">A collection of options is available to specify which versions you want to uninstall.</span></span>

<span data-ttu-id="b205f-106">Das Tool unterstützt Windows und macOS.</span><span class="sxs-lookup"><span data-stu-id="b205f-106">The tool supports Windows and macOS.</span></span> <span data-ttu-id="b205f-107">Linux wird aktuell nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b205f-107">Linux is currently not supported.</span></span>

<span data-ttu-id="b205f-108">Unter Windows kann das Tool nur SDKs und Runtimes deinstallieren, die mit einem der folgenden Installationsprogramme installiert wurden:</span><span class="sxs-lookup"><span data-stu-id="b205f-108">On Windows, the tool can only uninstall SDKs and Runtimes that were installed using one of the following installers:</span></span>

- <span data-ttu-id="b205f-109">.NET Core SDK- und -Runtime-Installer.</span><span class="sxs-lookup"><span data-stu-id="b205f-109">The .NET Core SDK and runtime installer.</span></span>
- <span data-ttu-id="b205f-110">Visual Studio-Installer in früheren Versionen als Visual Studio 2019, Version 16.3.</span><span class="sxs-lookup"><span data-stu-id="b205f-110">The Visual Studio installer in versions earlier than Visual Studio 2019 version 16.3.</span></span>

<span data-ttu-id="b205f-111">Unter macOS kann das Tool nur SDKs und Runtimes deinstallieren, die sich im Ordner */usr/local/share/dotnet* befinden.</span><span class="sxs-lookup"><span data-stu-id="b205f-111">On macOS, the tool can only uninstall SDKs and runtimes located in the */usr/local/share/dotnet* folder.</span></span>

<span data-ttu-id="b205f-112">Aufgrund dieser Einschränkungen ist das Tool möglicherweise nicht in der Lage, alle .NET Core SDKs und -Runtimes auf Ihrem Computer zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="b205f-112">Because of these limitations, the tool may not be able to uninstall all of the .NET Core SDKs and runtimes on your machine.</span></span> <span data-ttu-id="b205f-113">Mit dem Befehl `dotnet --info` können Sie alle installierten .NET Core SDKs und -Runtimes ermitteln, einschließlich der SDKs und Runtimes, die dieses Tool nicht entfernen kann.</span><span class="sxs-lookup"><span data-stu-id="b205f-113">You can use the `dotnet --info` command to find all of the .NET Core SDKs and runtimes installed, including those SDKs and runtimes that this tool can't remove.</span></span> <span data-ttu-id="b205f-114">Der Befehl `dotnet-core-uninstall list` zeigt an, welche SDKs mit dem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="b205f-114">The `dotnet-core-uninstall list` command displays which SDKs can be uninstalled with the tool.</span></span>

## <a name="install-the-tool"></a><span data-ttu-id="b205f-115">Installieren des Tools</span><span class="sxs-lookup"><span data-stu-id="b205f-115">Install the tool</span></span>

<span data-ttu-id="b205f-116">Sie können das .NET Core-Deinstallationstool aus dem GitHub-Repository [dotnet/cli-lab](https://github.com/dotnet/cli-lab/releases) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="b205f-116">You can download the .NET Core Uninstall Tool from the [dotnet/cli-lab](https://github.com/dotnet/cli-lab/releases) GitHub repository.</span></span>

> [!NOTE]
> <span data-ttu-id="b205f-117">Für das Tool ist eine Erhöhung der Rechte erforderlich, um .NET Core SDKs und -Runtimes zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="b205f-117">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="b205f-118">Daher sollte es in einem Verzeichnis mit schreibgeschütztem Zugriff installiert werden, z. B. in *C:\Programme* unter Windows oder in */usr/local/bin* unter macOS.</span><span class="sxs-lookup"><span data-stu-id="b205f-118">Therefore, it should be installed in a write-protected directory such as *C:\Program Files* on Windows or */usr/local/bin* on macOS.</span></span> <span data-ttu-id="b205f-119">Weitere Informationen finden Sie unter [Erhöhte Zugriffsrechte für dotnet-Befehle](../tools/elevated-access.md).</span><span class="sxs-lookup"><span data-stu-id="b205f-119">See also [Elevated access for dotnet commands](../tools/elevated-access.md).</span></span> <span data-ttu-id="b205f-120">Ausführliche Installationsanweisungen finden Sie auf der Seite [GitHub-Releases](https://github.com/dotnet/cli-lab/releases).</span><span class="sxs-lookup"><span data-stu-id="b205f-120">Detailed installation instructions are available on the [GitHub Releases page](https://github.com/dotnet/cli-lab/releases).</span></span>

## <a name="run-the-tool"></a><span data-ttu-id="b205f-121">Ausführen des Tools</span><span class="sxs-lookup"><span data-stu-id="b205f-121">Run the tool</span></span>

<span data-ttu-id="b205f-122">Die folgenden Schritte zeigen die empfohlene Vorgehensweise zum Ausführen des Deinstallationstools:</span><span class="sxs-lookup"><span data-stu-id="b205f-122">The following steps show the recommended approach for running the uninstall tool:</span></span>

- [<span data-ttu-id="b205f-123">Schritt 1: Anzeigen installierter .NET Core SDKs und -Runtimes</span><span class="sxs-lookup"><span data-stu-id="b205f-123">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>](#step-1---display-installed-net-core-sdks-and-runtimes)
- [<span data-ttu-id="b205f-124">Schritt 2: Ausführen eines Testlaufs</span><span class="sxs-lookup"><span data-stu-id="b205f-124">Step 2 - Do a dry run</span></span>](#step-2---do-a-dry-run)
- [<span data-ttu-id="b205f-125">Schritt 3: Deinstallieren von .NET Core SDKs und -Runtimes</span><span class="sxs-lookup"><span data-stu-id="b205f-125">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>](#step-3---uninstall-net-core-sdks-and-runtimes)
- [<span data-ttu-id="b205f-126">Schritt 4: Löschen des NuGet-Fallbackordners (optional)</span><span class="sxs-lookup"><span data-stu-id="b205f-126">Step 4 - Delete the NuGet fallback folder (optional)</span></span>](#step-4---delete-the-nuget-fallback-folder-optional)

### <a name="step-1---display-installed-net-core-sdks-and-runtimes"></a><span data-ttu-id="b205f-127">Schritt 1: Anzeigen installierter .NET Core SDKs und -Runtimes</span><span class="sxs-lookup"><span data-stu-id="b205f-127">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>

<span data-ttu-id="b205f-128">Der Befehl `dotnet-core-uninstall list` listet die installierten .NET Core SDKs und -Runtimes auf, die mit diesem Tool entfernt werden können.</span><span class="sxs-lookup"><span data-stu-id="b205f-128">The `dotnet-core-uninstall list` command lists the installed .NET Core SDKs and runtimes that can be removed with this tool.</span></span> <span data-ttu-id="b205f-129">Einige SDKs und Runtimes werden möglicherweise von Visual Studio benötigt, und es wird ein Hinweis angezeigt, warum es nicht empfohlen wird, diese zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="b205f-129">Some SDKs and runtimes may be required by Visual Studio and they're displayed with a note of why it isn't recommended to uninstall them.</span></span>

<span data-ttu-id="b205f-130">**dotnet-core-uninstall list**</span><span class="sxs-lookup"><span data-stu-id="b205f-130">**dotnet-core-uninstall list**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="b205f-131">Übersicht</span><span class="sxs-lookup"><span data-stu-id="b205f-131">Synopsis</span></span>

```console
dotnet-core-uninstall list [options]
```

#### <a name="options"></a><span data-ttu-id="b205f-132">Optionen</span><span class="sxs-lookup"><span data-stu-id="b205f-132">Options</span></span>

## <a name="windowstabwindows"></a>[<span data-ttu-id="b205f-133">Windows</span><span class="sxs-lookup"><span data-stu-id="b205f-133">Windows</span></span>](#tab/windows)

* **`--aspnet-runtime`**

  <span data-ttu-id="b205f-134">Listet alle ASP.NET Core-Runtimes auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="b205f-134">Lists all the ASP.NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="b205f-135">Listet alle .NET Core-Runtime- und -Hostingpakete auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="b205f-135">Lists all the .NET Core runtime and hosting bundles that can be uninstalled with this tool.</span></span>

* **`--runtime`**

  <span data-ttu-id="b205f-136">Listet alle .NET Core-Runtimes auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="b205f-136">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="b205f-137">Listet alle .NET Core SDKs auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="b205f-137">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="b205f-138">Legt den Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="b205f-138">Sets the verbosity level.</span></span> <span data-ttu-id="b205f-139">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="b205f-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="b205f-140">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="b205f-140">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="b205f-141">Listet alle x64-.NET Core SDKs und -Runtimes auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="b205f-141">Lists all x64 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

* **`--x86`**

  <span data-ttu-id="b205f-142">Listet alle x86-.NET Core SDKs und -Runtimes auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="b205f-142">Lists all x86 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

## <a name="macostabmacos"></a>[<span data-ttu-id="b205f-143">macOS</span><span class="sxs-lookup"><span data-stu-id="b205f-143">macOS</span></span>](#tab/macos)

* **`--runtime`**

  <span data-ttu-id="b205f-144">Listet alle .NET Core-Runtimes auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="b205f-144">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="b205f-145">Listet alle .NET Core SDKs auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="b205f-145">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="b205f-146">Legt den Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="b205f-146">Sets the verbosity level.</span></span> <span data-ttu-id="b205f-147">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="b205f-147">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="b205f-148">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="b205f-148">The default value is `normal`.</span></span>
  
---

#### <a name="examples"></a><span data-ttu-id="b205f-149">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b205f-149">Examples</span></span>

* <span data-ttu-id="b205f-150">Listet alle .NET Core SDKs und -Runtimes auf, die mit diesem Tool entfernt werden können:</span><span class="sxs-lookup"><span data-stu-id="b205f-150">List all .NET Core SDKs and runtimes that can be removed with this tool:</span></span>

  ```console
  dotnet-core-uninstall list
  ```

* <span data-ttu-id="b205f-151">Listet alle  x64-.NET Core SDKs und -Runtimes auf:</span><span class="sxs-lookup"><span data-stu-id="b205f-151">List all x64 .NET Core SDKs and runtimes:</span></span>

  ```console
  dotnet-core-uninstall list --x64
  ```

* <span data-ttu-id="b205f-152">Listet aller x86-.NET Core SDKs auf:</span><span class="sxs-lookup"><span data-stu-id="b205f-152">List all x86 .NET Core SDKs:</span></span>

  ```console
  dotnet-core-uninstall list --sdk --x86
  ```

### <a name="step-2---do-a-dry-run"></a><span data-ttu-id="b205f-153">Schritt 2: Ausführen eines Testlaufs</span><span class="sxs-lookup"><span data-stu-id="b205f-153">Step 2 - Do a dry run</span></span>

<span data-ttu-id="b205f-154">Die Befehle `dotnet-core-uninstall dry-run` und `dotnet-core-uninstall whatif` zeigen die .NET Core SDKs und -Runtimes an, die auf der Grundlage der bereitgestellten Optionen ohne Ausführung der Deinstallation entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="b205f-154">The `dotnet-core-uninstall dry-run` and `dotnet-core-uninstall whatif` commands display the .NET Core SDKs and runtimes that will be removed based on the options provided without performing the uninstall.</span></span> <span data-ttu-id="b205f-155">Diese Befehle sind Synonyme.</span><span class="sxs-lookup"><span data-stu-id="b205f-155">These commands are synonyms.</span></span>

<span data-ttu-id="b205f-156">**dotnet-core-uninstall dry-run und dotnet-core-uninstall whatif**</span><span class="sxs-lookup"><span data-stu-id="b205f-156">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="b205f-157">Übersicht</span><span class="sxs-lookup"><span data-stu-id="b205f-157">Synopsis</span></span>

```console
dotnet-core-uninstall dry-run [options] [<VERSION>...]

dotnet-core-uninstall whatif [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="b205f-158">Argumente</span><span class="sxs-lookup"><span data-stu-id="b205f-158">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="b205f-159">Die angegebene Version, die deinstalliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="b205f-159">The specified version to uninstall.</span></span> <span data-ttu-id="b205f-160">Sie können mehrere Versionen nacheinander (getrennt durch Leerzeichen) auflisten.</span><span class="sxs-lookup"><span data-stu-id="b205f-160">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="b205f-161">Antwortdateien werden ebenfalls unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b205f-161">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="b205f-162">Antwortdateien sind eine Alternative zum Eingeben aller Versionen in die Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="b205f-162">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="b205f-163">Dabei handelt es sich um Textdateien (in der Regel mit der Erweiterung „\*. rsp“), und jede Version wird in einer separaten Zeile aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="b205f-163">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="b205f-164">Um eine Antwortdatei für das `VERSION`-Argument anzugeben, verwenden Sie das Zeichen \@, direkt gefolgt vom Namen der Antwortdatei.</span><span class="sxs-lookup"><span data-stu-id="b205f-164">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="b205f-165">Optionen</span><span class="sxs-lookup"><span data-stu-id="b205f-165">Options</span></span>

## <a name="windowstabwindows"></a>[<span data-ttu-id="b205f-166">Windows</span><span class="sxs-lookup"><span data-stu-id="b205f-166">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="b205f-167">Entfernt alle .NET Core SDKs und -Runtimes.</span><span class="sxs-lookup"><span data-stu-id="b205f-167">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="b205f-168">Entfernt nur die .NET Core SDKs und -Runtimes mit einer Version, die kleiner als die angegebene Version ist.</span><span class="sxs-lookup"><span data-stu-id="b205f-168">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="b205f-169">Die angegebene Version bleibt installiert.</span><span class="sxs-lookup"><span data-stu-id="b205f-169">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="b205f-170">Entfernt alle .NET Core SDKs und -Runtimes mit Ausnahme der angegebenen Versionen.</span><span class="sxs-lookup"><span data-stu-id="b205f-170">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="b205f-171">Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Version.</span><span class="sxs-lookup"><span data-stu-id="b205f-171">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="b205f-172">Entfernt .NET Core SDKs und -Runtimes, die durch höhere Patches abgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="b205f-172">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="b205f-173">Diese Option schützt „global.json“.</span><span class="sxs-lookup"><span data-stu-id="b205f-173">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="b205f-174">Entfernt .NET Core SDKs und -Runtimes, die als Vorschauversionen markiert sind.</span><span class="sxs-lookup"><span data-stu-id="b205f-174">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="b205f-175">Entfernt als Vorschauversion markierte .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Vorschau.</span><span class="sxs-lookup"><span data-stu-id="b205f-175">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="b205f-176">Entfernt nur ASP.NET Core-Runtimes.</span><span class="sxs-lookup"><span data-stu-id="b205f-176">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="b205f-177">Entfernt nur .NET Core-Runtime- und -Hostingpakete.</span><span class="sxs-lookup"><span data-stu-id="b205f-177">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="b205f-178">Entfernt .NET Core SDKs und -Runtimes, die der angegebenen `major.minor`-Version entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b205f-178">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="b205f-179">Entfernt nur .NET Core-Runtimes.</span><span class="sxs-lookup"><span data-stu-id="b205f-179">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="b205f-180">Entfernt nur .NET Core SDKs.</span><span class="sxs-lookup"><span data-stu-id="b205f-180">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="b205f-181">Legt den Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="b205f-181">Sets the verbosity level.</span></span> <span data-ttu-id="b205f-182">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="b205f-182">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="b205f-183">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="b205f-183">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="b205f-184">Muss mit `--sdk`, `--runtime`und `--aspnet-runtime` verwendet werden, um x64-SDKs oder-Runtimes zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="b205f-184">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="b205f-185">Muss mit `--sdk`, `--runtime`und `--aspnet-runtime` verwendet werden, um x86-SDKs oder-Runtimes zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="b205f-185">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="b205f-186">**`--force`** Erzwingt das Entfernen von Versionen, die möglicherweise von Visual Studio verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b205f-186">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="b205f-187">Hinweise:</span><span class="sxs-lookup"><span data-stu-id="b205f-187">Notes:</span></span>

1. <span data-ttu-id="b205f-188">Genau ein Element `--sdk`, `--runtime`, `--aspnet-runtime` und `--hosting-bundle` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b205f-188">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="b205f-189">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` und `[<VERSION>...]` sind exklusiv.</span><span class="sxs-lookup"><span data-stu-id="b205f-189">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="b205f-190">Wenn `--x64` oder `--x86` nicht angegeben wird, werden sowohl x64- als auch x86-Versionen entfernt.</span><span class="sxs-lookup"><span data-stu-id="b205f-190">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macostabmacos"></a>[<span data-ttu-id="b205f-191">macOS</span><span class="sxs-lookup"><span data-stu-id="b205f-191">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="b205f-192">Entfernt alle .NET Core SDKs und -Runtimes.</span><span class="sxs-lookup"><span data-stu-id="b205f-192">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="b205f-193">Entfernt .NET Core SDKs und -Runtimes mit einer kleineren als der angegebenen Version.</span><span class="sxs-lookup"><span data-stu-id="b205f-193">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="b205f-194">Die angegebene Version verbleibt auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="b205f-194">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="b205f-195">Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der angegebenen Versionen.</span><span class="sxs-lookup"><span data-stu-id="b205f-195">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="b205f-196">Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Version.</span><span class="sxs-lookup"><span data-stu-id="b205f-196">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="b205f-197">Entfernt .NET Core SDKs und -Runtimes, die durch höhere Patches abgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="b205f-197">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="b205f-198">Diese Option schützt „global.json“.</span><span class="sxs-lookup"><span data-stu-id="b205f-198">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="b205f-199">Entfernt .NET Core SDKs und -Runtimes, die als Vorschauversionen markiert sind.</span><span class="sxs-lookup"><span data-stu-id="b205f-199">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="b205f-200">Entfernt als Vorschauversion markierte .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Vorschau.</span><span class="sxs-lookup"><span data-stu-id="b205f-200">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="b205f-201">Entfernt .NET Core SDKs und -Runtimes, die der angegebenen `major.minor`-Version entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b205f-201">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="b205f-202">Entfernt nur .NET Core-Runtimes.</span><span class="sxs-lookup"><span data-stu-id="b205f-202">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="b205f-203">Entfernt nur .NET Core SDKs.</span><span class="sxs-lookup"><span data-stu-id="b205f-203">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="b205f-204">Legt den Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="b205f-204">Sets the verbosity level.</span></span> <span data-ttu-id="b205f-205">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="b205f-205">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="b205f-206">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="b205f-206">The default value is `normal`.</span></span>
  
* <span data-ttu-id="b205f-207">**`--force`** Erzwingt das Entfernen von Versionen, die möglicherweise von Visual Studio oder SDKs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b205f-207">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="b205f-208">Hinweise:</span><span class="sxs-lookup"><span data-stu-id="b205f-208">Notes:</span></span>

1. <span data-ttu-id="b205f-209">Genau ein Element `--sdk` und `--runtime` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b205f-209">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="b205f-210">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` und `[<VERSION>...]` sind exklusiv.</span><span class="sxs-lookup"><span data-stu-id="b205f-210">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="b205f-211">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b205f-211">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="b205f-212">Standardmäßig sind .NET Core SDKs und -Runtimes, die möglicherweise von Visual Studio oder anderen SDKs benötigt werden, nicht in der Ausgabe von `dotnet-core-uninstall dry-run` enthalten.</span><span class="sxs-lookup"><span data-stu-id="b205f-212">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are not included in `dotnet-core-uninstall dry-run` output.</span></span> <span data-ttu-id="b205f-213">In den folgenden Beispielen sind einige der angegebenen SDKs und Runtimes abhängig vom Zustand des Computers möglicherweise nicht in der Ausgabe enthalten.</span><span class="sxs-lookup"><span data-stu-id="b205f-213">In the following examples, some of the specified SDKs and runtimes may not be included in the output, depending on the state of the machine.</span></span> <span data-ttu-id="b205f-214">Wenn Sie alle SDKs und Runtimes einbeziehen möchten, führen Sie diese explizit als Argumente auf, oder verwenden Sie die Option `--force`.</span><span class="sxs-lookup"><span data-stu-id="b205f-214">To include all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="b205f-215">Testlauf zum Entfernen aller .NET Core-Runtimes, die durch höhere Patches abgelöst wurden:</span><span class="sxs-lookup"><span data-stu-id="b205f-215">Dry run of removing all .NET Core runtimes that have been superseded by higher patches:</span></span>

  ```console
  dotnet-core-uninstall dry-run --all-lower-patches --runtime
  ```

* <span data-ttu-id="b205f-216">Testlauf zum Entfernen aller .NET Core SDKs mit einer kleineren Version als `2.2.301`:</span><span class="sxs-lookup"><span data-stu-id="b205f-216">Dry run of removing all .NET Core SDKs below the version `2.2.301`:</span></span>

  ```console
  dotnet-core-uninstall whatif --all-below 2.2.301 --sdk
  ```

### <a name="step-3---uninstall-net-core-sdks-and-runtimes"></a><span data-ttu-id="b205f-217">Schritt 3: Deinstallieren von .NET Core SDKs und -Runtimes</span><span class="sxs-lookup"><span data-stu-id="b205f-217">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>

<span data-ttu-id="b205f-218">`dotnet-core-uninstall remove` deinstalliert .NET Core SDKs und -Runtimes, die durch eine Sammlung von Optionen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b205f-218">`dotnet-core-uninstall remove` uninstalls .NET Core SDKs and Runtimes that are specified by a collection of options.</span></span> <span data-ttu-id="b205f-219">Das Tool kann nicht zum Deinstallieren von SDKs und Runtimes mit Version 5.0 oder höher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b205f-219">The tool can't be used to uninstall SDKs and Runtimes with version 5.0 or above.</span></span>

<span data-ttu-id="b205f-220">Da dieses Tool ein destruktives Verhalten aufweist, wird **unbedingt** empfohlen, vor dem Ausführen des Entfernungsbefehls einen Testlauf auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b205f-220">Since this tool has a destructive behavior, it's **highly** recommended that you do a dry run before running the remove command.</span></span> <span data-ttu-id="b205f-221">Der Testlauf zeigt Ihnen, welche .NET Core SDKs und -Runtimes entfernt werden, wenn Sie den Befehl `remove` verwenden.</span><span class="sxs-lookup"><span data-stu-id="b205f-221">The dry run will show you what .NET Core SDKs and runtimes will be removed when you use the `remove` command.</span></span> <span data-ttu-id="b205f-222">Lesen Sie [Sollte ich eine Version entfernen?](../versions/remove-runtime-sdk-versions.md#should-i-remove-a-version), um zu erfahren, welche SDKs und Runtimes sicher entfernt werden können.</span><span class="sxs-lookup"><span data-stu-id="b205f-222">Refer to [Should I remove a version?](../versions/remove-runtime-sdk-versions.md#should-i-remove-a-version) to learn which SDKs and runtimes are safe to remove.</span></span>

> [!CAUTION]
> <span data-ttu-id="b205f-223">Beachten Sie die folgenden Vorbehalte:</span><span class="sxs-lookup"><span data-stu-id="b205f-223">Keep in mind the following caveats:</span></span>
>
>- <span data-ttu-id="b205f-224">Dieses Tool kann Versionen des .NET Core SDK deinstallieren, die von `global.json`-Dateien auf Ihrem Computer benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="b205f-224">This tool can uninstall versions of the .NET Core SDK that are required by `global.json` files on your machine.</span></span> <span data-ttu-id="b205f-225">Sie können .NET Core SDKs über die Seite [.NET Core herunterladen](https://dotnet.microsoft.com/download/dotnet-core) erneut installieren.</span><span class="sxs-lookup"><span data-stu-id="b205f-225">You can reinstall .NET Core SDKs from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="b205f-226">Dieses Tool kann Versionen der .NET Core-Runtime deinstallieren, die von frameworkabhängigen Anwendungen auf Ihrem Computer benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="b205f-226">This tool can uninstall versions of the .NET Core runtime that are required by framework dependent applications on your machine.</span></span> <span data-ttu-id="b205f-227">Sie können .NET Core-Runtimes über die Seite [.NET Core herunterladen](https://dotnet.microsoft.com/download/dotnet-core) erneut installieren.</span><span class="sxs-lookup"><span data-stu-id="b205f-227">You can reinstall .NET Core runtimes from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="b205f-228">Dieses Tool kann Versionen des .NET Core SDK und der -Runtime deinstallieren, die von Visual Studio benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="b205f-228">This tool can uninstall versions of the .NET Core SDK and runtime that Visual Studio relies on.</span></span> <span data-ttu-id="b205f-229">Wenn Sie Ihre Visual Studio-Installation beschädigen, führen Sie „Reparieren“ im Visual Studio-Installer aus, um zu einem funktionsfähigen Zustand zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="b205f-229">If you break your Visual Studio installation, run "Repair" in the Visual Studio installer to get back to a working state.</span></span>

<span data-ttu-id="b205f-230">Standardmäßig behalten alle Befehle die .NET Core SDKs und -Runtimes bei, die möglicherweise von Visual Studio oder anderen SDKs benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="b205f-230">By default, all commands keep the .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs.</span></span> <span data-ttu-id="b205f-231">Diese SDKs und Runtimes können deinstalliert werden, indem sie explizit als Argumente aufgelistet werden oder indem die Option `--force` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b205f-231">These SDKs and runtimes can be uninstalled by listing them explicitly as arguments or by using the `--force` option.</span></span>

<span data-ttu-id="b205f-232">Für das Tool ist eine Erhöhung der Rechte erforderlich, um .NET Core SDKs und -Runtimes zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="b205f-232">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="b205f-233">Führen Sie das Tool in einer Administratoreingabeaufforderung unter Windows und mit `sudo` unter macOS aus.</span><span class="sxs-lookup"><span data-stu-id="b205f-233">Run the tool in an Administrator command prompt on Windows and with `sudo` on macOS.</span></span> <span data-ttu-id="b205f-234">Die Befehle `dry-run` und `whatif` erfordern keine Erhöhung der Rechte.</span><span class="sxs-lookup"><span data-stu-id="b205f-234">The `dry-run` and `whatif` commands don't require elevation.</span></span>

<span data-ttu-id="b205f-235">**dotnet-core-uninstall remove**</span><span class="sxs-lookup"><span data-stu-id="b205f-235">**dotnet-core-uninstall remove**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="b205f-236">Übersicht</span><span class="sxs-lookup"><span data-stu-id="b205f-236">Synopsis</span></span>

```console
dotnet-core-uninstall remove [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="b205f-237">Argumente</span><span class="sxs-lookup"><span data-stu-id="b205f-237">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="b205f-238">Die angegebene Version, die deinstalliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="b205f-238">The specified version to uninstall.</span></span> <span data-ttu-id="b205f-239">Sie können mehrere Versionen nacheinander (getrennt durch Leerzeichen) auflisten.</span><span class="sxs-lookup"><span data-stu-id="b205f-239">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="b205f-240">Antwortdateien werden ebenfalls unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b205f-240">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="b205f-241">Antwortdateien sind eine Alternative zum Eingeben aller Versionen in die Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="b205f-241">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="b205f-242">Dabei handelt es sich um Textdateien (in der Regel mit der Erweiterung „\*. rsp“), und jede Version wird in einer separaten Zeile aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="b205f-242">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="b205f-243">Um eine Antwortdatei für das `VERSION`-Argument anzugeben, verwenden Sie das Zeichen \@, direkt gefolgt vom Namen der Antwortdatei.</span><span class="sxs-lookup"><span data-stu-id="b205f-243">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="b205f-244">Optionen</span><span class="sxs-lookup"><span data-stu-id="b205f-244">Options</span></span>

## <a name="windowstabwindows"></a>[<span data-ttu-id="b205f-245">Windows</span><span class="sxs-lookup"><span data-stu-id="b205f-245">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="b205f-246">Entfernt alle .NET Core SDKs und -Runtimes.</span><span class="sxs-lookup"><span data-stu-id="b205f-246">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="b205f-247">Entfernt nur die .NET Core SDKs und -Runtimes mit einer Version, die kleiner als die angegebene Version ist.</span><span class="sxs-lookup"><span data-stu-id="b205f-247">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="b205f-248">Die angegebene Version bleibt installiert.</span><span class="sxs-lookup"><span data-stu-id="b205f-248">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="b205f-249">Entfernt alle .NET Core SDKs und -Runtimes mit Ausnahme der angegebenen Versionen.</span><span class="sxs-lookup"><span data-stu-id="b205f-249">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="b205f-250">Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Version.</span><span class="sxs-lookup"><span data-stu-id="b205f-250">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="b205f-251">Entfernt .NET Core SDKs und -Runtimes, die durch höhere Patches abgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="b205f-251">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="b205f-252">Diese Option schützt „global.json“.</span><span class="sxs-lookup"><span data-stu-id="b205f-252">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="b205f-253">Entfernt .NET Core SDKs und -Runtimes, die als Vorschauversionen markiert sind.</span><span class="sxs-lookup"><span data-stu-id="b205f-253">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="b205f-254">Entfernt als Vorschauversion markierte .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Vorschau.</span><span class="sxs-lookup"><span data-stu-id="b205f-254">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="b205f-255">Entfernt nur ASP.NET Core-Runtimes.</span><span class="sxs-lookup"><span data-stu-id="b205f-255">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="b205f-256">Entfernt nur .NET Core-Runtime- und -Hostingpakete.</span><span class="sxs-lookup"><span data-stu-id="b205f-256">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="b205f-257">Entfernt .NET Core SDKs und -Runtimes, die der angegebenen `major.minor`-Version entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b205f-257">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="b205f-258">Entfernt nur .NET Core-Runtimes.</span><span class="sxs-lookup"><span data-stu-id="b205f-258">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="b205f-259">Entfernt nur .NET Core SDKs.</span><span class="sxs-lookup"><span data-stu-id="b205f-259">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="b205f-260">Legt den Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="b205f-260">Sets the verbosity level.</span></span> <span data-ttu-id="b205f-261">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="b205f-261">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="b205f-262">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="b205f-262">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="b205f-263">Muss mit `--sdk`, `--runtime`und `--aspnet-runtime` verwendet werden, um x64-SDKs oder-Runtimes zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="b205f-263">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="b205f-264">Muss mit `--sdk`, `--runtime`und `--aspnet-runtime` verwendet werden, um x86-SDKs oder-Runtimes zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="b205f-264">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="b205f-265">**`-y, --yes`** Führt den Befehl aus, ohne dass eine Bestätigung mit „Ja“ oder „Nein“ erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b205f-265">**`-y, --yes`** Executes the command without requiring a yes or no confirmation.</span></span>

* <span data-ttu-id="b205f-266">**`--force`** Erzwingt das Entfernen von Versionen, die möglicherweise von Visual Studio verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b205f-266">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="b205f-267">Hinweise:</span><span class="sxs-lookup"><span data-stu-id="b205f-267">Notes:</span></span>

1. <span data-ttu-id="b205f-268">Genau ein Element `--sdk`, `--runtime`, `--aspnet-runtime` und `--hosting-bundle` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b205f-268">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="b205f-269">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` und `[<VERSION>...]` sind exklusiv.</span><span class="sxs-lookup"><span data-stu-id="b205f-269">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="b205f-270">Wenn `--x64` oder `--x86` nicht angegeben wird, werden sowohl x64- als auch x86-Versionen entfernt.</span><span class="sxs-lookup"><span data-stu-id="b205f-270">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macostabmacos"></a>[<span data-ttu-id="b205f-271">macOS</span><span class="sxs-lookup"><span data-stu-id="b205f-271">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="b205f-272">Entfernt alle .NET Core SDKs und -Runtimes.</span><span class="sxs-lookup"><span data-stu-id="b205f-272">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="b205f-273">Entfernt .NET Core SDKs und -Runtimes mit einer kleineren als der angegebenen Version.</span><span class="sxs-lookup"><span data-stu-id="b205f-273">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="b205f-274">Die angegebene Version verbleibt auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="b205f-274">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="b205f-275">Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der angegebenen Versionen.</span><span class="sxs-lookup"><span data-stu-id="b205f-275">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="b205f-276">Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Version.</span><span class="sxs-lookup"><span data-stu-id="b205f-276">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="b205f-277">Entfernt .NET Core SDKs und -Runtimes, die durch höhere Patches abgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="b205f-277">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="b205f-278">Diese Option schützt „global.json“.</span><span class="sxs-lookup"><span data-stu-id="b205f-278">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="b205f-279">Entfernt .NET Core SDKs und -Runtimes, die als Vorschauversionen markiert sind.</span><span class="sxs-lookup"><span data-stu-id="b205f-279">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="b205f-280">Entfernt als Vorschauversion markierte .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Vorschau.</span><span class="sxs-lookup"><span data-stu-id="b205f-280">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="b205f-281">Entfernt .NET Core SDKs und -Runtimes, die der angegebenen `major.minor`-Version entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b205f-281">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="b205f-282">Entfernt nur .NET Core-Runtimes.</span><span class="sxs-lookup"><span data-stu-id="b205f-282">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="b205f-283">Entfernt nur .NET Core SDKs.</span><span class="sxs-lookup"><span data-stu-id="b205f-283">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="b205f-284">Legt den Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="b205f-284">Sets the verbosity level.</span></span> <span data-ttu-id="b205f-285">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="b205f-285">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="b205f-286">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="b205f-286">The default value is `normal`.</span></span>

* <span data-ttu-id="b205f-287">**`-y, --yes`** Führt den Befehl aus, ohne dass eine J/N-Bestätigung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b205f-287">**`-y, --yes`** Executes the command without requiring Y/N confirmation.</span></span>
  
* <span data-ttu-id="b205f-288">**`--force`** Erzwingt das Entfernen von Versionen, die möglicherweise von Visual Studio oder SDKs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b205f-288">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="b205f-289">Hinweise:</span><span class="sxs-lookup"><span data-stu-id="b205f-289">Notes:</span></span>

1. <span data-ttu-id="b205f-290">Genau ein Element `--sdk` und `--runtime` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b205f-290">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="b205f-291">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` und `[<VERSION>...]` sind exklusiv.</span><span class="sxs-lookup"><span data-stu-id="b205f-291">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="b205f-292">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b205f-292">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="b205f-293">Standardmäßig werden .NET Core SDKs und -Runtimes, die möglicherweise von Visual Studio oder anderen SDKs benötigt werden, beibehalten.</span><span class="sxs-lookup"><span data-stu-id="b205f-293">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are kept.</span></span> <span data-ttu-id="b205f-294">In den folgenden Beispielen bleiben einige der angegebenen SDKs und Runtimes abhängig vom Zustand des Computers ggf. erhalten.</span><span class="sxs-lookup"><span data-stu-id="b205f-294">In the following examples, some of the specified SDKs and runtimes may remain, depending on the state of the machine.</span></span> <span data-ttu-id="b205f-295">Wenn Sie alle SDKs und Runtimes entfernen möchten, führen Sie diese explizit als Argumente auf, oder verwenden Sie die Option `--force`.</span><span class="sxs-lookup"><span data-stu-id="b205f-295">To remove all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="b205f-296">Entfernen aller .NET Core-Runtimes mit Ausnahme der Version `3.0.0-preview6-27804-01`, ohne dass eine J/N-Bestätigung erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="b205f-296">Remove all .NET Core runtimes except the version `3.0.0-preview6-27804-01` without requiring Y/N confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --all-but 3.0.0-preview6-27804-01 --runtime --yes
  ```

* <span data-ttu-id="b205f-297">Entfernen aller .NET Core 1.1 SDKs, ohne dass eine J/N-Bestätigung erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="b205f-297">Remove all .NET Core 1.1 SDKs without requiring Y/n confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --sdk --major-minor 1.1 -y
  ```

* <span data-ttu-id="b205f-298">Entfernen des .NET Core 1.1.11 SDK ohne Konsolenausgabe:</span><span class="sxs-lookup"><span data-stu-id="b205f-298">Remove the .NET Core 1.1.11 SDK with no console output:</span></span>

  ```console
  dotnet-core-uninstall remove 1.1.11 --sdk --yes --verbosity q
  ```

* <span data-ttu-id="b205f-299">Entfernen aller .NET Core SDKs, die sicher von diesem Tool entfernt werden können:</span><span class="sxs-lookup"><span data-stu-id="b205f-299">Remove all .NET Core SDKs that can safely be removed by this tool:</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk
  ```

* <span data-ttu-id="b205f-300">Entfernen aller .NET Core SDKs, die von diesem Tool entfernt werden können, einschließlich der SDKs, die möglicherweise von Visual Studio benötigt werden (nicht empfohlen):</span><span class="sxs-lookup"><span data-stu-id="b205f-300">Remove all .NET Core SDKs that can be removed by this tool, including those SDKs that may be required by Visual Studio (not recommended):</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk --force
  ```

* <span data-ttu-id="b205f-301">Entfernen aller .NET Core SDKs, die in der Antwortdatei `versions.rsp` angegeben sind</span><span class="sxs-lookup"><span data-stu-id="b205f-301">Remove all .NET Core SDKs that are specified in the response file `versions.rsp`</span></span>

  ```console
  dotnet-core-uninstall remove --sdk @versions.rsp
  ```

  <span data-ttu-id="b205f-302">Der Inhalt von *versions.rsp* lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b205f-302">The content of *versions.rsp* is as follows:</span></span>
  
  ```text
  2.2.300
  2.1.700
  ```

### <a name="step-4---delete-the-nuget-fallback-folder-optional"></a><span data-ttu-id="b205f-303">Schritt 4: Löschen des NuGet-Fallbackordners (optional)</span><span class="sxs-lookup"><span data-stu-id="b205f-303">Step 4 - Delete the NuGet fallback folder (optional)</span></span>

<span data-ttu-id="b205f-304">In einigen Fällen benötigen Sie `NuGetFallbackFolder` nicht mehr und möchten den Ordner ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="b205f-304">In some cases, you no longer need the `NuGetFallbackFolder` and may wish to delete it.</span></span> <span data-ttu-id="b205f-305">Weitere Informationen zum Löschen dieses Ordners finden Sie unter [Entfernen des Ordners „NuGetFallbackFolder“](../versions/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span><span class="sxs-lookup"><span data-stu-id="b205f-305">For more information about deleting this folder, see [Remove the NuGetFallbackFolder](../versions/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span></span>

## <a name="uninstall-the-tool"></a><span data-ttu-id="b205f-306">Deinstallieren des Tools</span><span class="sxs-lookup"><span data-stu-id="b205f-306">Uninstall the tool</span></span>

## <a name="windowstabwindows"></a>[<span data-ttu-id="b205f-307">Windows</span><span class="sxs-lookup"><span data-stu-id="b205f-307">Windows</span></span>](#tab/windows)

1. <span data-ttu-id="b205f-308">Öffnen Sie **Software**.</span><span class="sxs-lookup"><span data-stu-id="b205f-308">Open **Add or Remove Programs**.</span></span>
2. <span data-ttu-id="b205f-309">Suchen Sie nach `Microsoft .NET Core SDK Uninstall Tool`.</span><span class="sxs-lookup"><span data-stu-id="b205f-309">Search for `Microsoft .NET Core SDK Uninstall Tool`.</span></span>
3. <span data-ttu-id="b205f-310">Wählen Sie **Deinstallieren** aus.</span><span class="sxs-lookup"><span data-stu-id="b205f-310">Select **Uninstall**.</span></span>

## <a name="macostabmacos"></a>[<span data-ttu-id="b205f-311">macOS</span><span class="sxs-lookup"><span data-stu-id="b205f-311">macOS</span></span>](#tab/macos)

<span data-ttu-id="b205f-312">Löschen Sie die heruntergeladene Datei *dotnet-core-uninstall.tar.gz* aus dem Verzeichnis, in dem sie installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b205f-312">Delete the downloaded *dotnet-core-uninstall.tar.gz* file from the directory where it was installed.</span></span> <span data-ttu-id="b205f-313">Wenn Sie den Inhalt dieser Datei in ein anderes Verzeichnis entzippt haben, stellen Sie sicher, dass Sie auch diesen Inhalt löschen.</span><span class="sxs-lookup"><span data-stu-id="b205f-313">If you unzipped the contents of this file into another directory, be sure to delete that content as well.</span></span>

---
