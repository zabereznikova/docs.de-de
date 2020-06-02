---
title: Deinstallationstool
description: Eine Übersicht über das .NET Core-Deinstallationstool, ein Tool mit Anleitungen, das die kontrollierte Bereinigung von .NET Core SDKs und -Runtimes ermöglicht.
author: sfoslund
ms.date: 05/27/2020
ms.openlocfilehash: 1ad31cd42d8f8f87e3501b422fc4298c643e2067
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144512"
---
# <a name="net-core-uninstall-tool"></a><span data-ttu-id="f3596-103">.NET Core-Deinstallationstool</span><span class="sxs-lookup"><span data-stu-id="f3596-103">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="f3596-104">Mit dem [.NET Core-Deinstallationstool](https://aka.ms/dotnet-core-uninstall-tool) (`dotnet-core-uninstall`) können Sie .NET Core SDKs und -Runtimes von einem System entfernen.</span><span class="sxs-lookup"><span data-stu-id="f3596-104">The [.NET Core Uninstall Tool](https://aka.ms/dotnet-core-uninstall-tool) (`dotnet-core-uninstall`) lets you remove .NET Core SDKs and Runtimes from a system.</span></span> <span data-ttu-id="f3596-105">Hierfür stehen Ihnen verschiedene Optionen zur Verfügung, mit denen Sie angeben können, welche Versionen deinstalliert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f3596-105">A collection of options is available to specify which versions you want to uninstall.</span></span>

<span data-ttu-id="f3596-106">Das Tool unterstützt Windows und macOS.</span><span class="sxs-lookup"><span data-stu-id="f3596-106">The tool supports Windows and macOS.</span></span> <span data-ttu-id="f3596-107">Linux wird aktuell nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f3596-107">Linux is currently not supported.</span></span>

<span data-ttu-id="f3596-108">Unter Windows kann das Tool nur SDKs und Runtimes deinstallieren, die mit einem der folgenden Installationsprogramme installiert wurden:</span><span class="sxs-lookup"><span data-stu-id="f3596-108">On Windows, the tool can only uninstall SDKs and Runtimes that were installed using one of the following installers:</span></span>

- <span data-ttu-id="f3596-109">.NET Core SDK- und -Runtime-Installer.</span><span class="sxs-lookup"><span data-stu-id="f3596-109">The .NET Core SDK and runtime installer.</span></span>
- <span data-ttu-id="f3596-110">Visual Studio-Installer in früheren Versionen als Visual Studio 2019, Version 16.3.</span><span class="sxs-lookup"><span data-stu-id="f3596-110">The Visual Studio installer in versions earlier than Visual Studio 2019 version 16.3.</span></span>

<span data-ttu-id="f3596-111">Unter macOS kann das Tool nur SDKs und Runtimes deinstallieren, die sich im Ordner */usr/local/share/dotnet* befinden.</span><span class="sxs-lookup"><span data-stu-id="f3596-111">On macOS, the tool can only uninstall SDKs and runtimes located in the */usr/local/share/dotnet* folder.</span></span>

<span data-ttu-id="f3596-112">Aufgrund dieser Einschränkungen ist das Tool möglicherweise nicht in der Lage, alle .NET Core SDKs und -Runtimes auf Ihrem Computer zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="f3596-112">Because of these limitations, the tool may not be able to uninstall all of the .NET Core SDKs and runtimes on your machine.</span></span> <span data-ttu-id="f3596-113">Mit dem Befehl `dotnet --info` können Sie alle installierten .NET Core SDKs und -Runtimes ermitteln, einschließlich der SDKs und Runtimes, die dieses Tool nicht entfernen kann.</span><span class="sxs-lookup"><span data-stu-id="f3596-113">You can use the `dotnet --info` command to find all of the .NET Core SDKs and runtimes installed, including those SDKs and runtimes that this tool can't remove.</span></span> <span data-ttu-id="f3596-114">Der Befehl `dotnet-core-uninstall list` zeigt an, welche SDKs mit dem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="f3596-114">The `dotnet-core-uninstall list` command displays which SDKs can be uninstalled with the tool.</span></span>

## <a name="install-the-tool"></a><span data-ttu-id="f3596-115">Installieren des Tools</span><span class="sxs-lookup"><span data-stu-id="f3596-115">Install the tool</span></span>

<span data-ttu-id="f3596-116">Sie können das .NET Core-Tool für die Deinstallation [hier](https://aka.ms/dotnet-core-uninstall-tool) herunterladen und den Quellcode im GitHub-Repository [dotnet/cli-lab](https://github.com/dotnet/cli-lab) finden.</span><span class="sxs-lookup"><span data-stu-id="f3596-116">You can download the .NET Core Uninstall Tool from [here](https://aka.ms/dotnet-core-uninstall-tool) and find the source code at the [dotnet/cli-lab](https://github.com/dotnet/cli-lab) GitHub repository.</span></span>

> [!NOTE]
> <span data-ttu-id="f3596-117">Für das Tool ist eine Erhöhung der Rechte erforderlich, um .NET Core SDKs und -Runtimes zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="f3596-117">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="f3596-118">Daher sollte es in einem Verzeichnis mit schreibgeschütztem Zugriff installiert werden, z. B. in *C:\Programme* unter Windows oder in */usr/local/bin* unter macOS.</span><span class="sxs-lookup"><span data-stu-id="f3596-118">Therefore, it should be installed in a write-protected directory such as *C:\Program Files* on Windows or */usr/local/bin* on macOS.</span></span> <span data-ttu-id="f3596-119">Weitere Informationen finden Sie unter [Erhöhte Zugriffsrechte für dotnet-Befehle](../tools/elevated-access.md).</span><span class="sxs-lookup"><span data-stu-id="f3596-119">See also [Elevated access for dotnet commands](../tools/elevated-access.md).</span></span> <span data-ttu-id="f3596-120">Weitere Informationen finden Sie unter [Ausführliche Installationsanweisungen](https://aka.ms/dotnet-core-uninstall-tool).</span><span class="sxs-lookup"><span data-stu-id="f3596-120">For more information, see the [detailed installation instructions](https://aka.ms/dotnet-core-uninstall-tool).</span></span>

## <a name="run-the-tool"></a><span data-ttu-id="f3596-121">Ausführen des Tools</span><span class="sxs-lookup"><span data-stu-id="f3596-121">Run the tool</span></span>

<span data-ttu-id="f3596-122">Die folgenden Schritte zeigen die empfohlene Vorgehensweise zum Ausführen des Deinstallationstools:</span><span class="sxs-lookup"><span data-stu-id="f3596-122">The following steps show the recommended approach for running the uninstall tool:</span></span>

- [<span data-ttu-id="f3596-123">Schritt 1: Anzeigen installierter .NET Core SDKs und -Runtimes</span><span class="sxs-lookup"><span data-stu-id="f3596-123">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>](#step-1---display-installed-net-core-sdks-and-runtimes)
- [<span data-ttu-id="f3596-124">Schritt 2: Ausführen eines Testlaufs</span><span class="sxs-lookup"><span data-stu-id="f3596-124">Step 2 - Do a dry run</span></span>](#step-2---do-a-dry-run)
- [<span data-ttu-id="f3596-125">Schritt 3: Deinstallieren von .NET Core SDKs und -Runtimes</span><span class="sxs-lookup"><span data-stu-id="f3596-125">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>](#step-3---uninstall-net-core-sdks-and-runtimes)
- [<span data-ttu-id="f3596-126">Schritt 4: Löschen des NuGet-Fallbackordners (optional)</span><span class="sxs-lookup"><span data-stu-id="f3596-126">Step 4 - Delete the NuGet fallback folder (optional)</span></span>](#step-4---delete-the-nuget-fallback-folder-optional)

### <a name="step-1---display-installed-net-core-sdks-and-runtimes"></a><span data-ttu-id="f3596-127">Schritt 1: Anzeigen installierter .NET Core SDKs und -Runtimes</span><span class="sxs-lookup"><span data-stu-id="f3596-127">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>

<span data-ttu-id="f3596-128">Der Befehl `dotnet-core-uninstall list` listet die installierten .NET Core SDKs und -Runtimes auf, die mit diesem Tool entfernt werden können.</span><span class="sxs-lookup"><span data-stu-id="f3596-128">The `dotnet-core-uninstall list` command lists the installed .NET Core SDKs and runtimes that can be removed with this tool.</span></span> <span data-ttu-id="f3596-129">Einige SDKs und Runtimes werden möglicherweise von Visual Studio benötigt, und es wird ein Hinweis angezeigt, warum es nicht empfohlen wird, diese zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="f3596-129">Some SDKs and runtimes may be required by Visual Studio and they're displayed with a note of why it isn't recommended to uninstall them.</span></span>

> [!NOTE]
> <span data-ttu-id="f3596-130">Die Ausgabe des `dotnet-core-uninstall list`-Befehls stimmt in den meisten Fällen nicht mit der Liste der installierten Versionen in der Ausgabe von `dotnet --info` überein.</span><span class="sxs-lookup"><span data-stu-id="f3596-130">The output of the `dotnet-core-uninstall list` command will not match the list of installed versions in the output of `dotnet --info` in most cases.</span></span> <span data-ttu-id="f3596-131">Insbesondere zeigt dieses Tool keine Versionen an, die über ZIP-Dateien installiert oder von Visual Studio verwaltet werden (alle Versionen, die mit Visual Studio 2019 16.3 oder höher installiert wurden).</span><span class="sxs-lookup"><span data-stu-id="f3596-131">Specifically, this tool will not display versions installed by zip files or managed by Visual Studio (any version installed with Visual Studio 2019 16.3 or later).</span></span> <span data-ttu-id="f3596-132">Eine Möglichkeit zur Überprüfung, ob eine Version von Visual Studio verwaltet wird, besteht darin, sie in `Add or Remove Programs` anzuzeigen. Hier werden in Visual Studio verwaltete Versionen in ihren Anzeigenamen als solche gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="f3596-132">One way to check if a version is managed by Visual Studio is to view it in `Add or Remove Programs`, where Visual Studio managed versions are marked as such in their display names.</span></span>

<span data-ttu-id="f3596-133">**dotnet-core-uninstall list**</span><span class="sxs-lookup"><span data-stu-id="f3596-133">**dotnet-core-uninstall list**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="f3596-134">Übersicht</span><span class="sxs-lookup"><span data-stu-id="f3596-134">Synopsis</span></span>

```console
dotnet-core-uninstall list [options]
```

#### <a name="options"></a><span data-ttu-id="f3596-135">Optionen</span><span class="sxs-lookup"><span data-stu-id="f3596-135">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="f3596-136">Windows</span><span class="sxs-lookup"><span data-stu-id="f3596-136">Windows</span></span>](#tab/windows)

* **`--aspnet-runtime`**

  <span data-ttu-id="f3596-137">Listet alle ASP.NET Core-Runtimes auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="f3596-137">Lists all the ASP.NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="f3596-138">Listet alle .NET Core-Hostingpakete auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="f3596-138">Lists all the .NET Core hosting bundles that can be uninstalled with this tool.</span></span>

* **`--runtime`**

  <span data-ttu-id="f3596-139">Listet alle .NET Core-Runtimes auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="f3596-139">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="f3596-140">Listet alle .NET Core SDKs auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="f3596-140">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="f3596-141">Legt den Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="f3596-141">Sets the verbosity level.</span></span> <span data-ttu-id="f3596-142">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f3596-142">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f3596-143">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="f3596-143">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="f3596-144">Listet alle x64-.NET Core SDKs und -Runtimes auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="f3596-144">Lists all x64 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

* **`--x86`**

  <span data-ttu-id="f3596-145">Listet alle x86-.NET Core SDKs und -Runtimes auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="f3596-145">Lists all x86 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

## <a name="macos"></a>[<span data-ttu-id="f3596-146">macOS</span><span class="sxs-lookup"><span data-stu-id="f3596-146">macOS</span></span>](#tab/macos)

* **`--runtime`**

  <span data-ttu-id="f3596-147">Listet alle .NET Core-Runtimes auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="f3596-147">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="f3596-148">Listet alle .NET Core SDKs auf, die mit diesem Tool deinstalliert werden können.</span><span class="sxs-lookup"><span data-stu-id="f3596-148">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="f3596-149">Legt den Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="f3596-149">Sets the verbosity level.</span></span> <span data-ttu-id="f3596-150">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f3596-150">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f3596-151">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="f3596-151">The default value is `normal`.</span></span>
  
---

#### <a name="examples"></a><span data-ttu-id="f3596-152">Beispiele</span><span class="sxs-lookup"><span data-stu-id="f3596-152">Examples</span></span>

* <span data-ttu-id="f3596-153">Listet alle .NET Core SDKs und -Runtimes auf, die mit diesem Tool entfernt werden können:</span><span class="sxs-lookup"><span data-stu-id="f3596-153">List all .NET Core SDKs and runtimes that can be removed with this tool:</span></span>

  ```console
  dotnet-core-uninstall list
  ```

* <span data-ttu-id="f3596-154">Listet alle  x64-.NET Core SDKs und -Runtimes auf:</span><span class="sxs-lookup"><span data-stu-id="f3596-154">List all x64 .NET Core SDKs and runtimes:</span></span>

  ```console
  dotnet-core-uninstall list --x64
  ```

* <span data-ttu-id="f3596-155">Listet aller x86-.NET Core SDKs auf:</span><span class="sxs-lookup"><span data-stu-id="f3596-155">List all x86 .NET Core SDKs:</span></span>

  ```console
  dotnet-core-uninstall list --sdk --x86
  ```

### <a name="step-2---do-a-dry-run"></a><span data-ttu-id="f3596-156">Schritt 2: Ausführen eines Testlaufs</span><span class="sxs-lookup"><span data-stu-id="f3596-156">Step 2 - Do a dry run</span></span>

<span data-ttu-id="f3596-157">Die Befehle `dotnet-core-uninstall dry-run` und `dotnet-core-uninstall whatif` zeigen die .NET Core SDKs und -Runtimes an, die auf der Grundlage der bereitgestellten Optionen ohne Ausführung der Deinstallation entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="f3596-157">The `dotnet-core-uninstall dry-run` and `dotnet-core-uninstall whatif` commands display the .NET Core SDKs and runtimes that will be removed based on the options provided without performing the uninstall.</span></span> <span data-ttu-id="f3596-158">Diese Befehle sind Synonyme.</span><span class="sxs-lookup"><span data-stu-id="f3596-158">These commands are synonyms.</span></span>

<span data-ttu-id="f3596-159">**dotnet-core-uninstall dry-run und dotnet-core-uninstall whatif**</span><span class="sxs-lookup"><span data-stu-id="f3596-159">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="f3596-160">Übersicht</span><span class="sxs-lookup"><span data-stu-id="f3596-160">Synopsis</span></span>

```console
dotnet-core-uninstall dry-run [options] [<VERSION>...]

dotnet-core-uninstall whatif [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="f3596-161">Argumente</span><span class="sxs-lookup"><span data-stu-id="f3596-161">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="f3596-162">Die angegebene Version, die deinstalliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f3596-162">The specified version to uninstall.</span></span> <span data-ttu-id="f3596-163">Sie können mehrere Versionen nacheinander (getrennt durch Leerzeichen) auflisten.</span><span class="sxs-lookup"><span data-stu-id="f3596-163">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="f3596-164">Antwortdateien werden ebenfalls unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f3596-164">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="f3596-165">Antwortdateien sind eine Alternative zum Eingeben aller Versionen in die Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="f3596-165">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="f3596-166">Dabei handelt es sich um Textdateien (in der Regel mit der Erweiterung „\*. rsp“), und jede Version wird in einer separaten Zeile aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f3596-166">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="f3596-167">Um eine Antwortdatei für das `VERSION`-Argument anzugeben, verwenden Sie das Zeichen \@, direkt gefolgt vom Namen der Antwortdatei.</span><span class="sxs-lookup"><span data-stu-id="f3596-167">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="f3596-168">Optionen</span><span class="sxs-lookup"><span data-stu-id="f3596-168">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="f3596-169">Windows</span><span class="sxs-lookup"><span data-stu-id="f3596-169">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="f3596-170">Entfernt alle .NET Core SDKs und -Runtimes.</span><span class="sxs-lookup"><span data-stu-id="f3596-170">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="f3596-171">Entfernt nur die .NET Core SDKs und -Runtimes mit einer Version, die kleiner als die angegebene Version ist.</span><span class="sxs-lookup"><span data-stu-id="f3596-171">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="f3596-172">Die angegebene Version bleibt installiert.</span><span class="sxs-lookup"><span data-stu-id="f3596-172">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="f3596-173">Entfernt alle .NET Core SDKs und -Runtimes mit Ausnahme der angegebenen Versionen.</span><span class="sxs-lookup"><span data-stu-id="f3596-173">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="f3596-174">Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Version.</span><span class="sxs-lookup"><span data-stu-id="f3596-174">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="f3596-175">Entfernt .NET Core SDKs und -Runtimes, die durch höhere Patches abgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="f3596-175">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="f3596-176">Diese Option schützt „global.json“.</span><span class="sxs-lookup"><span data-stu-id="f3596-176">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="f3596-177">Entfernt .NET Core SDKs und -Runtimes, die als Vorschauversionen markiert sind.</span><span class="sxs-lookup"><span data-stu-id="f3596-177">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="f3596-178">Entfernt als Vorschauversion markierte .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Vorschau.</span><span class="sxs-lookup"><span data-stu-id="f3596-178">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="f3596-179">Entfernt nur ASP.NET Core-Runtimes.</span><span class="sxs-lookup"><span data-stu-id="f3596-179">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="f3596-180">Entfernt nur .NET Core-Runtime- und -Hostingpakete.</span><span class="sxs-lookup"><span data-stu-id="f3596-180">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="f3596-181">Entfernt .NET Core SDKs und -Runtimes, die der angegebenen `major.minor`-Version entsprechen.</span><span class="sxs-lookup"><span data-stu-id="f3596-181">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="f3596-182">Entfernt nur .NET Core-Runtimes.</span><span class="sxs-lookup"><span data-stu-id="f3596-182">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="f3596-183">Entfernt nur .NET Core SDKs.</span><span class="sxs-lookup"><span data-stu-id="f3596-183">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="f3596-184">Legt den Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="f3596-184">Sets the verbosity level.</span></span> <span data-ttu-id="f3596-185">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f3596-185">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f3596-186">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="f3596-186">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="f3596-187">Muss mit `--sdk`, `--runtime`und `--aspnet-runtime` verwendet werden, um x64-SDKs oder-Runtimes zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="f3596-187">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="f3596-188">Muss mit `--sdk`, `--runtime`und `--aspnet-runtime` verwendet werden, um x86-SDKs oder-Runtimes zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="f3596-188">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="f3596-189">**`--force`** Erzwingt das Entfernen von Versionen, die möglicherweise von Visual Studio verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f3596-189">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="f3596-190">Notizen:</span><span class="sxs-lookup"><span data-stu-id="f3596-190">Notes:</span></span>

1. <span data-ttu-id="f3596-191">Genau ein Element `--sdk`, `--runtime`, `--aspnet-runtime` und `--hosting-bundle` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f3596-191">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="f3596-192">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` und `[<VERSION>...]` sind exklusiv.</span><span class="sxs-lookup"><span data-stu-id="f3596-192">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="f3596-193">Wenn `--x64` oder `--x86` nicht angegeben wird, werden sowohl x64- als auch x86-Versionen entfernt.</span><span class="sxs-lookup"><span data-stu-id="f3596-193">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="f3596-194">macOS</span><span class="sxs-lookup"><span data-stu-id="f3596-194">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="f3596-195">Entfernt alle .NET Core SDKs und -Runtimes.</span><span class="sxs-lookup"><span data-stu-id="f3596-195">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="f3596-196">Entfernt .NET Core SDKs und -Runtimes mit einer kleineren als der angegebenen Version.</span><span class="sxs-lookup"><span data-stu-id="f3596-196">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="f3596-197">Die angegebene Version verbleibt auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="f3596-197">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="f3596-198">Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der angegebenen Versionen.</span><span class="sxs-lookup"><span data-stu-id="f3596-198">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="f3596-199">Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Version.</span><span class="sxs-lookup"><span data-stu-id="f3596-199">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="f3596-200">Entfernt .NET Core SDKs und -Runtimes, die durch höhere Patches abgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="f3596-200">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="f3596-201">Diese Option schützt „global.json“.</span><span class="sxs-lookup"><span data-stu-id="f3596-201">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="f3596-202">Entfernt .NET Core SDKs und -Runtimes, die als Vorschauversionen markiert sind.</span><span class="sxs-lookup"><span data-stu-id="f3596-202">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="f3596-203">Entfernt als Vorschauversion markierte .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Vorschau.</span><span class="sxs-lookup"><span data-stu-id="f3596-203">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="f3596-204">Entfernt .NET Core SDKs und -Runtimes, die der angegebenen `major.minor`-Version entsprechen.</span><span class="sxs-lookup"><span data-stu-id="f3596-204">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="f3596-205">Entfernt nur .NET Core-Runtimes.</span><span class="sxs-lookup"><span data-stu-id="f3596-205">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="f3596-206">Entfernt nur .NET Core SDKs.</span><span class="sxs-lookup"><span data-stu-id="f3596-206">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="f3596-207">Legt den Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="f3596-207">Sets the verbosity level.</span></span> <span data-ttu-id="f3596-208">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f3596-208">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f3596-209">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="f3596-209">The default value is `normal`.</span></span>
  
* <span data-ttu-id="f3596-210">**`--force`** Erzwingt das Entfernen von Versionen, die möglicherweise von Visual Studio oder SDKs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f3596-210">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="f3596-211">Notizen:</span><span class="sxs-lookup"><span data-stu-id="f3596-211">Notes:</span></span>

1. <span data-ttu-id="f3596-212">Genau ein Element `--sdk` und `--runtime` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f3596-212">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="f3596-213">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` und `[<VERSION>...]` sind exklusiv.</span><span class="sxs-lookup"><span data-stu-id="f3596-213">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="f3596-214">Beispiele</span><span class="sxs-lookup"><span data-stu-id="f3596-214">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="f3596-215">Standardmäßig sind .NET Core SDKs und -Runtimes, die möglicherweise von Visual Studio oder anderen SDKs benötigt werden, nicht in der Ausgabe von `dotnet-core-uninstall dry-run` enthalten.</span><span class="sxs-lookup"><span data-stu-id="f3596-215">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are not included in `dotnet-core-uninstall dry-run` output.</span></span> <span data-ttu-id="f3596-216">In den folgenden Beispielen sind einige der angegebenen SDKs und Runtimes abhängig vom Zustand des Computers möglicherweise nicht in der Ausgabe enthalten.</span><span class="sxs-lookup"><span data-stu-id="f3596-216">In the following examples, some of the specified SDKs and runtimes may not be included in the output, depending on the state of the machine.</span></span> <span data-ttu-id="f3596-217">Wenn Sie alle SDKs und Runtimes einbeziehen möchten, führen Sie diese explizit als Argumente auf, oder verwenden Sie die Option `--force`.</span><span class="sxs-lookup"><span data-stu-id="f3596-217">To include all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="f3596-218">Testlauf zum Entfernen aller .NET Core-Runtimes, die durch höhere Patches abgelöst wurden:</span><span class="sxs-lookup"><span data-stu-id="f3596-218">Dry run of removing all .NET Core runtimes that have been superseded by higher patches:</span></span>

  ```console
  dotnet-core-uninstall dry-run --all-lower-patches --runtime
  ```

* <span data-ttu-id="f3596-219">Testlauf zum Entfernen aller .NET Core SDKs mit einer kleineren Version als `2.2.301`:</span><span class="sxs-lookup"><span data-stu-id="f3596-219">Dry run of removing all .NET Core SDKs below the version `2.2.301`:</span></span>

  ```console
  dotnet-core-uninstall whatif --all-below 2.2.301 --sdk
  ```

### <a name="step-3---uninstall-net-core-sdks-and-runtimes"></a><span data-ttu-id="f3596-220">Schritt 3: Deinstallieren von .NET Core SDKs und -Runtimes</span><span class="sxs-lookup"><span data-stu-id="f3596-220">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>

<span data-ttu-id="f3596-221">`dotnet-core-uninstall remove` deinstalliert .NET Core SDKs und -Runtimes, die durch eine Sammlung von Optionen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f3596-221">`dotnet-core-uninstall remove` uninstalls .NET Core SDKs and Runtimes that are specified by a collection of options.</span></span> <span data-ttu-id="f3596-222">Das Tool kann nicht zum Deinstallieren von SDKs und Runtimes mit Version 5.0 oder höher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f3596-222">The tool can't be used to uninstall SDKs and Runtimes with version 5.0 or above.</span></span>

<span data-ttu-id="f3596-223">Da dieses Tool ein destruktives Verhalten aufweist, wird **unbedingt** empfohlen, vor dem Ausführen des Entfernungsbefehls einen Testlauf auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f3596-223">Since this tool has a destructive behavior, it's **highly** recommended that you do a dry run before running the remove command.</span></span> <span data-ttu-id="f3596-224">Der Testlauf zeigt Ihnen, welche .NET Core SDKs und -Runtimes entfernt werden, wenn Sie den Befehl `remove` verwenden.</span><span class="sxs-lookup"><span data-stu-id="f3596-224">The dry run will show you what .NET Core SDKs and runtimes will be removed when you use the `remove` command.</span></span> <span data-ttu-id="f3596-225">Lesen Sie [Sollte ich eine Version entfernen?](../install/remove-runtime-sdk-versions.md#should-i-remove-a-version), um zu erfahren, welche SDKs und Runtimes sicher entfernt werden können.</span><span class="sxs-lookup"><span data-stu-id="f3596-225">Refer to [Should I remove a version?](../install/remove-runtime-sdk-versions.md#should-i-remove-a-version) to learn which SDKs and runtimes are safe to remove.</span></span>

> [!CAUTION]
> <span data-ttu-id="f3596-226">Beachten Sie die folgenden Vorbehalte:</span><span class="sxs-lookup"><span data-stu-id="f3596-226">Keep in mind the following caveats:</span></span>
>
>- <span data-ttu-id="f3596-227">Dieses Tool kann Versionen des .NET Core SDK deinstallieren, die von `global.json`-Dateien auf Ihrem Computer benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="f3596-227">This tool can uninstall versions of the .NET Core SDK that are required by `global.json` files on your machine.</span></span> <span data-ttu-id="f3596-228">Sie können .NET Core SDKs über die Seite [.NET Core herunterladen](https://dotnet.microsoft.com/download/dotnet-core) erneut installieren.</span><span class="sxs-lookup"><span data-stu-id="f3596-228">You can reinstall .NET Core SDKs from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="f3596-229">Dieses Tool kann Versionen der .NET Core-Runtime deinstallieren, die von frameworkabhängigen Anwendungen auf Ihrem Computer benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="f3596-229">This tool can uninstall versions of the .NET Core runtime that are required by framework dependent applications on your machine.</span></span> <span data-ttu-id="f3596-230">Sie können .NET Core-Runtimes über die Seite [.NET Core herunterladen](https://dotnet.microsoft.com/download/dotnet-core) erneut installieren.</span><span class="sxs-lookup"><span data-stu-id="f3596-230">You can reinstall .NET Core runtimes from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="f3596-231">Dieses Tool kann Versionen des .NET Core SDK und der -Runtime deinstallieren, die von Visual Studio benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="f3596-231">This tool can uninstall versions of the .NET Core SDK and runtime that Visual Studio relies on.</span></span> <span data-ttu-id="f3596-232">Wenn Sie Ihre Visual Studio-Installation beschädigen, führen Sie „Reparieren“ im Visual Studio-Installer aus, um zu einem funktionsfähigen Zustand zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="f3596-232">If you break your Visual Studio installation, run "Repair" in the Visual Studio installer to get back to a working state.</span></span>

<span data-ttu-id="f3596-233">Standardmäßig behalten alle Befehle die .NET Core SDKs und -Runtimes bei, die möglicherweise von Visual Studio oder anderen SDKs benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="f3596-233">By default, all commands keep the .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs.</span></span> <span data-ttu-id="f3596-234">Diese SDKs und Runtimes können deinstalliert werden, indem sie explizit als Argumente aufgelistet werden oder indem die Option `--force` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f3596-234">These SDKs and runtimes can be uninstalled by listing them explicitly as arguments or by using the `--force` option.</span></span>

<span data-ttu-id="f3596-235">Für das Tool ist eine Erhöhung der Rechte erforderlich, um .NET Core SDKs und -Runtimes zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="f3596-235">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="f3596-236">Führen Sie das Tool in einer Administratoreingabeaufforderung unter Windows und mit `sudo` unter macOS aus.</span><span class="sxs-lookup"><span data-stu-id="f3596-236">Run the tool in an Administrator command prompt on Windows and with `sudo` on macOS.</span></span> <span data-ttu-id="f3596-237">Die Befehle `dry-run` und `whatif` erfordern keine Erhöhung der Rechte.</span><span class="sxs-lookup"><span data-stu-id="f3596-237">The `dry-run` and `whatif` commands don't require elevation.</span></span>

<span data-ttu-id="f3596-238">**dotnet-core-uninstall remove**</span><span class="sxs-lookup"><span data-stu-id="f3596-238">**dotnet-core-uninstall remove**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="f3596-239">Übersicht</span><span class="sxs-lookup"><span data-stu-id="f3596-239">Synopsis</span></span>

```console
dotnet-core-uninstall remove [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="f3596-240">Argumente</span><span class="sxs-lookup"><span data-stu-id="f3596-240">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="f3596-241">Die angegebene Version, die deinstalliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f3596-241">The specified version to uninstall.</span></span> <span data-ttu-id="f3596-242">Sie können mehrere Versionen nacheinander (getrennt durch Leerzeichen) auflisten.</span><span class="sxs-lookup"><span data-stu-id="f3596-242">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="f3596-243">Antwortdateien werden ebenfalls unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f3596-243">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="f3596-244">Antwortdateien sind eine Alternative zum Eingeben aller Versionen in die Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="f3596-244">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="f3596-245">Dabei handelt es sich um Textdateien (in der Regel mit der Erweiterung „\*. rsp“), und jede Version wird in einer separaten Zeile aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f3596-245">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="f3596-246">Um eine Antwortdatei für das `VERSION`-Argument anzugeben, verwenden Sie das Zeichen \@, direkt gefolgt vom Namen der Antwortdatei.</span><span class="sxs-lookup"><span data-stu-id="f3596-246">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="f3596-247">Optionen</span><span class="sxs-lookup"><span data-stu-id="f3596-247">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="f3596-248">Windows</span><span class="sxs-lookup"><span data-stu-id="f3596-248">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="f3596-249">Entfernt alle .NET Core SDKs und -Runtimes.</span><span class="sxs-lookup"><span data-stu-id="f3596-249">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="f3596-250">Entfernt nur die .NET Core SDKs und -Runtimes mit einer Version, die kleiner als die angegebene Version ist.</span><span class="sxs-lookup"><span data-stu-id="f3596-250">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="f3596-251">Die angegebene Version bleibt installiert.</span><span class="sxs-lookup"><span data-stu-id="f3596-251">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="f3596-252">Entfernt alle .NET Core SDKs und -Runtimes mit Ausnahme der angegebenen Versionen.</span><span class="sxs-lookup"><span data-stu-id="f3596-252">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="f3596-253">Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Version.</span><span class="sxs-lookup"><span data-stu-id="f3596-253">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="f3596-254">Entfernt .NET Core SDKs und -Runtimes, die durch höhere Patches abgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="f3596-254">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="f3596-255">Diese Option schützt „global.json“.</span><span class="sxs-lookup"><span data-stu-id="f3596-255">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="f3596-256">Entfernt .NET Core SDKs und -Runtimes, die als Vorschauversionen markiert sind.</span><span class="sxs-lookup"><span data-stu-id="f3596-256">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="f3596-257">Entfernt als Vorschauversion markierte .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Vorschau.</span><span class="sxs-lookup"><span data-stu-id="f3596-257">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="f3596-258">Entfernt nur ASP.NET Core-Runtimes.</span><span class="sxs-lookup"><span data-stu-id="f3596-258">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="f3596-259">Entfernt nur .NET Core-Runtime- und -Hostingpakete.</span><span class="sxs-lookup"><span data-stu-id="f3596-259">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="f3596-260">Entfernt .NET Core SDKs und -Runtimes, die der angegebenen `major.minor`-Version entsprechen.</span><span class="sxs-lookup"><span data-stu-id="f3596-260">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="f3596-261">Entfernt nur .NET Core-Runtimes.</span><span class="sxs-lookup"><span data-stu-id="f3596-261">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="f3596-262">Entfernt nur .NET Core SDKs.</span><span class="sxs-lookup"><span data-stu-id="f3596-262">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="f3596-263">Legt den Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="f3596-263">Sets the verbosity level.</span></span> <span data-ttu-id="f3596-264">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f3596-264">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f3596-265">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="f3596-265">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="f3596-266">Muss mit `--sdk`, `--runtime`und `--aspnet-runtime` verwendet werden, um x64-SDKs oder-Runtimes zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="f3596-266">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="f3596-267">Muss mit `--sdk`, `--runtime`und `--aspnet-runtime` verwendet werden, um x86-SDKs oder-Runtimes zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="f3596-267">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="f3596-268">**`-y, --yes`** Führt den Befehl aus, ohne dass eine Bestätigung mit „Ja“ oder „Nein“ erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f3596-268">**`-y, --yes`** Executes the command without requiring a yes or no confirmation.</span></span>

* <span data-ttu-id="f3596-269">**`--force`** Erzwingt das Entfernen von Versionen, die möglicherweise von Visual Studio verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f3596-269">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="f3596-270">Notizen:</span><span class="sxs-lookup"><span data-stu-id="f3596-270">Notes:</span></span>

1. <span data-ttu-id="f3596-271">Genau ein Element `--sdk`, `--runtime`, `--aspnet-runtime` und `--hosting-bundle` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f3596-271">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="f3596-272">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` und `[<VERSION>...]` sind exklusiv.</span><span class="sxs-lookup"><span data-stu-id="f3596-272">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="f3596-273">Wenn `--x64` oder `--x86` nicht angegeben wird, werden sowohl x64- als auch x86-Versionen entfernt.</span><span class="sxs-lookup"><span data-stu-id="f3596-273">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="f3596-274">macOS</span><span class="sxs-lookup"><span data-stu-id="f3596-274">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="f3596-275">Entfernt alle .NET Core SDKs und -Runtimes.</span><span class="sxs-lookup"><span data-stu-id="f3596-275">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="f3596-276">Entfernt .NET Core SDKs und -Runtimes mit einer kleineren als der angegebenen Version.</span><span class="sxs-lookup"><span data-stu-id="f3596-276">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="f3596-277">Die angegebene Version verbleibt auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="f3596-277">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="f3596-278">Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der angegebenen Versionen.</span><span class="sxs-lookup"><span data-stu-id="f3596-278">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="f3596-279">Entfernt .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Version.</span><span class="sxs-lookup"><span data-stu-id="f3596-279">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="f3596-280">Entfernt .NET Core SDKs und -Runtimes, die durch höhere Patches abgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="f3596-280">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="f3596-281">Diese Option schützt „global.json“.</span><span class="sxs-lookup"><span data-stu-id="f3596-281">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="f3596-282">Entfernt .NET Core SDKs und -Runtimes, die als Vorschauversionen markiert sind.</span><span class="sxs-lookup"><span data-stu-id="f3596-282">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="f3596-283">Entfernt als Vorschauversion markierte .NET Core SDKs und -Runtimes mit Ausnahme der höchsten Vorschau.</span><span class="sxs-lookup"><span data-stu-id="f3596-283">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="f3596-284">Entfernt .NET Core SDKs und -Runtimes, die der angegebenen `major.minor`-Version entsprechen.</span><span class="sxs-lookup"><span data-stu-id="f3596-284">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="f3596-285">Entfernt nur .NET Core-Runtimes.</span><span class="sxs-lookup"><span data-stu-id="f3596-285">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="f3596-286">Entfernt nur .NET Core SDKs.</span><span class="sxs-lookup"><span data-stu-id="f3596-286">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="f3596-287">Legt den Ausführlichkeitsgrad fest.</span><span class="sxs-lookup"><span data-stu-id="f3596-287">Sets the verbosity level.</span></span> <span data-ttu-id="f3596-288">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f3596-288">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f3596-289">Der Standardwert ist `normal`.</span><span class="sxs-lookup"><span data-stu-id="f3596-289">The default value is `normal`.</span></span>

* <span data-ttu-id="f3596-290">**`-y, --yes`** Führt den Befehl aus, ohne dass eine J/N-Bestätigung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f3596-290">**`-y, --yes`** Executes the command without requiring Y/N confirmation.</span></span>
  
* <span data-ttu-id="f3596-291">**`--force`** Erzwingt das Entfernen von Versionen, die möglicherweise von Visual Studio oder SDKs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f3596-291">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="f3596-292">Notizen:</span><span class="sxs-lookup"><span data-stu-id="f3596-292">Notes:</span></span>

1. <span data-ttu-id="f3596-293">Genau ein Element `--sdk` und `--runtime` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f3596-293">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="f3596-294">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` und `[<VERSION>...]` sind exklusiv.</span><span class="sxs-lookup"><span data-stu-id="f3596-294">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="f3596-295">Beispiele</span><span class="sxs-lookup"><span data-stu-id="f3596-295">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="f3596-296">Standardmäßig werden .NET Core SDKs und -Runtimes, die möglicherweise von Visual Studio oder anderen SDKs benötigt werden, beibehalten.</span><span class="sxs-lookup"><span data-stu-id="f3596-296">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are kept.</span></span> <span data-ttu-id="f3596-297">In den folgenden Beispielen bleiben einige der angegebenen SDKs und Runtimes abhängig vom Zustand des Computers ggf. erhalten.</span><span class="sxs-lookup"><span data-stu-id="f3596-297">In the following examples, some of the specified SDKs and runtimes may remain, depending on the state of the machine.</span></span> <span data-ttu-id="f3596-298">Wenn Sie alle SDKs und Runtimes entfernen möchten, führen Sie diese explizit als Argumente auf, oder verwenden Sie die Option `--force`.</span><span class="sxs-lookup"><span data-stu-id="f3596-298">To remove all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="f3596-299">Entfernen aller .NET Core-Runtimes mit Ausnahme der Version `3.0.0-preview6-27804-01`, ohne dass eine J/N-Bestätigung erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="f3596-299">Remove all .NET Core runtimes except the version `3.0.0-preview6-27804-01` without requiring Y/N confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --all-but 3.0.0-preview6-27804-01 --runtime --yes
  ```

* <span data-ttu-id="f3596-300">Entfernen aller .NET Core 1.1 SDKs, ohne dass eine J/N-Bestätigung erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="f3596-300">Remove all .NET Core 1.1 SDKs without requiring Y/n confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --sdk --major-minor 1.1 -y
  ```

* <span data-ttu-id="f3596-301">Entfernen des .NET Core 1.1.11 SDK ohne Konsolenausgabe:</span><span class="sxs-lookup"><span data-stu-id="f3596-301">Remove the .NET Core 1.1.11 SDK with no console output:</span></span>

  ```console
  dotnet-core-uninstall remove 1.1.11 --sdk --yes --verbosity q
  ```

* <span data-ttu-id="f3596-302">Entfernen aller .NET Core SDKs, die sicher von diesem Tool entfernt werden können:</span><span class="sxs-lookup"><span data-stu-id="f3596-302">Remove all .NET Core SDKs that can safely be removed by this tool:</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk
  ```

* <span data-ttu-id="f3596-303">Entfernen aller .NET Core SDKs, die von diesem Tool entfernt werden können, einschließlich der SDKs, die möglicherweise von Visual Studio benötigt werden (nicht empfohlen):</span><span class="sxs-lookup"><span data-stu-id="f3596-303">Remove all .NET Core SDKs that can be removed by this tool, including those SDKs that may be required by Visual Studio (not recommended):</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk --force
  ```

* <span data-ttu-id="f3596-304">Entfernen aller .NET Core SDKs, die in der Antwortdatei `versions.rsp` angegeben sind</span><span class="sxs-lookup"><span data-stu-id="f3596-304">Remove all .NET Core SDKs that are specified in the response file `versions.rsp`</span></span>

  ```console
  dotnet-core-uninstall remove --sdk @versions.rsp
  ```

  <span data-ttu-id="f3596-305">Der Inhalt von *versions.rsp* lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="f3596-305">The content of *versions.rsp* is as follows:</span></span>
  
  ```text
  2.2.300
  2.1.700
  ```

### <a name="step-4---delete-the-nuget-fallback-folder-optional"></a><span data-ttu-id="f3596-306">Schritt 4: Löschen des NuGet-Fallbackordners (optional)</span><span class="sxs-lookup"><span data-stu-id="f3596-306">Step 4 - Delete the NuGet fallback folder (optional)</span></span>

<span data-ttu-id="f3596-307">In einigen Fällen benötigen Sie `NuGetFallbackFolder` nicht mehr und möchten den Ordner ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="f3596-307">In some cases, you no longer need the `NuGetFallbackFolder` and may wish to delete it.</span></span> <span data-ttu-id="f3596-308">Weitere Informationen zum Löschen dieses Ordners finden Sie unter [Entfernen des Ordners „NuGetFallbackFolder“](../install/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span><span class="sxs-lookup"><span data-stu-id="f3596-308">For more information about deleting this folder, see [Remove the NuGetFallbackFolder](../install/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span></span>

## <a name="uninstall-the-tool"></a><span data-ttu-id="f3596-309">Deinstallieren des Tools</span><span class="sxs-lookup"><span data-stu-id="f3596-309">Uninstall the tool</span></span>

## <a name="windows"></a>[<span data-ttu-id="f3596-310">Windows</span><span class="sxs-lookup"><span data-stu-id="f3596-310">Windows</span></span>](#tab/windows)

1. <span data-ttu-id="f3596-311">Öffnen Sie **Software**.</span><span class="sxs-lookup"><span data-stu-id="f3596-311">Open **Add or Remove Programs**.</span></span>
2. <span data-ttu-id="f3596-312">Suchen Sie nach `Microsoft .NET Core SDK Uninstall Tool`.</span><span class="sxs-lookup"><span data-stu-id="f3596-312">Search for `Microsoft .NET Core SDK Uninstall Tool`.</span></span>
3. <span data-ttu-id="f3596-313">Wählen Sie **Deinstallieren** aus.</span><span class="sxs-lookup"><span data-stu-id="f3596-313">Select **Uninstall**.</span></span>

## <a name="macos"></a>[<span data-ttu-id="f3596-314">macOS</span><span class="sxs-lookup"><span data-stu-id="f3596-314">macOS</span></span>](#tab/macos)

<span data-ttu-id="f3596-315">Löschen Sie die heruntergeladene Datei *dotnet-core-uninstall.tar.gz* aus dem Verzeichnis, in dem sie installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f3596-315">Delete the downloaded *dotnet-core-uninstall.tar.gz* file from the directory where it was installed.</span></span> <span data-ttu-id="f3596-316">Wenn Sie den Inhalt dieser Datei in ein anderes Verzeichnis entzippt haben, stellen Sie sicher, dass Sie auch diesen Inhalt löschen.</span><span class="sxs-lookup"><span data-stu-id="f3596-316">If you unzipped the contents of this file into another directory, be sure to delete that content as well.</span></span>

---
