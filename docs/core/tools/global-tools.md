---
title: .NET Core-Tools
description: Informationen zum Installieren, Verwenden, Aktualisieren und Entfernen von .NET Core-Tools. In diesem Artikel werden globale, Toolpfad- und lokale Tools vorgestellt.
author: KathleenDollard
ms.date: 02/12/2020
ms.openlocfilehash: d8ee30df3fe063fd41a85072d145b1b5eec7d0d0
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543390"
---
# <a name="how-to-manage-net-core-tools"></a><span data-ttu-id="d0738-104">Verwalten von .NET Core-Tools</span><span class="sxs-lookup"><span data-stu-id="d0738-104">How to manage .NET Core tools</span></span>

<span data-ttu-id="d0738-105">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="d0738-105">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="d0738-106">Ein .NET Core-Tool ist ein spezielles NuGet-Paket, das eine Konsolenanwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="d0738-106">A .NET Core tool is a special NuGet package that contains a console application.</span></span> <span data-ttu-id="d0738-107">Ein Tool kann auf folgende Weisen auf dem Computer installiert werden:</span><span class="sxs-lookup"><span data-stu-id="d0738-107">A tool can be installed on your machine in the following ways:</span></span>

* <span data-ttu-id="d0738-108">Als globales Tool.</span><span class="sxs-lookup"><span data-stu-id="d0738-108">As a global tool.</span></span>

  <span data-ttu-id="d0738-109">Die Binärdateien für das Tool werden in einem Standardverzeichnis installiert, das der Umgebungsvariablen PATH hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="d0738-109">The tool binaries are installed in a default directory that is added to the PATH environment variable.</span></span> <span data-ttu-id="d0738-110">Sie können das Tool aus einem beliebigen Verzeichnis auf dem Computer aufrufen, ohne seinen Speicherort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d0738-110">You can invoke the tool from any directory on the machine without specifying its location.</span></span> <span data-ttu-id="d0738-111">Eine Version eines Tools wird für alle Verzeichnisse auf dem Computer verwendet.</span><span class="sxs-lookup"><span data-stu-id="d0738-111">One version of a tool is used for all directories on the machine.</span></span>

* <span data-ttu-id="d0738-112">Als globales Tool an einem benutzerdefinierten Speicherort (auch „Toolpfadtool“ genannt).</span><span class="sxs-lookup"><span data-stu-id="d0738-112">As a global tool in a custom location (also known as a tool-path tool).</span></span>

  <span data-ttu-id="d0738-113">Die Binärdateien für das Tool werden an einem von Ihnen angegebenen Speicherort installiert.</span><span class="sxs-lookup"><span data-stu-id="d0738-113">The tool binaries are installed in a location that you specify.</span></span> <span data-ttu-id="d0738-114">Sie können das Tool im Installationsverzeichnis aufrufen oder indem Sie das Verzeichnis mit dem Befehlsnamen angeben oder das Verzeichnis zur Umgebungsvariablen PATH hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d0738-114">You can invoke the tool from the installation directory or by providing the directory with the command name or by adding the directory to the PATH environment variable.</span></span> <span data-ttu-id="d0738-115">Eine Version eines Tools wird für alle Verzeichnisse auf dem Computer verwendet.</span><span class="sxs-lookup"><span data-stu-id="d0738-115">One version of a tool is used for all directories on the machine.</span></span>

* <span data-ttu-id="d0738-116">Als lokales Tool (ab .NET Core SDK 3.0).</span><span class="sxs-lookup"><span data-stu-id="d0738-116">As a local tool (applies to .NET Core SDK 3.0 and later).</span></span>

  <span data-ttu-id="d0738-117">Die Binärdateien des Tools werden in einem Standardverzeichnis installiert.</span><span class="sxs-lookup"><span data-stu-id="d0738-117">The tool binaries are installed in a default directory.</span></span> <span data-ttu-id="d0738-118">Sie rufen das Tool im Installationsverzeichnis oder einem seiner Unterverzeichnisse auf.</span><span class="sxs-lookup"><span data-stu-id="d0738-118">You invoke the tool from the installation directory or any of its subdirectories.</span></span> <span data-ttu-id="d0738-119">Verschiedene Verzeichnisse können unterschiedliche Versionen desselben Tools verwenden.</span><span class="sxs-lookup"><span data-stu-id="d0738-119">Different directories can use different versions of the same tool.</span></span>
  
  <span data-ttu-id="d0738-120">Die .NET-CLI nutzt Manifestdateien, um nachzuverfolgen, welche Tools lokal in einem Verzeichnis installiert sind.</span><span class="sxs-lookup"><span data-stu-id="d0738-120">The .NET CLI uses manifest files to keep track of which tools are installed as local to a directory.</span></span> <span data-ttu-id="d0738-121">Wenn die Manifestdatei im Stammverzeichnis eines Quellcoderepositorys gespeichert ist, kann ein Mitwirkender das Repository klonen und einen einzelnen .NET Core-CLI-Befehl aufrufen, mit dem alle in den Manifestdateien aufgeführten Tools installiert werden.</span><span class="sxs-lookup"><span data-stu-id="d0738-121">When the manifest file is saved in the root directory of a source code repository, a contributor can clone the repository and invoke a single .NET Core CLI command that installs all of the tools listed in the manifest files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0738-122">.NET Core-Tools werden mit voller Vertrauenswürdigkeit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d0738-122">.NET Core tools run in full trust.</span></span> <span data-ttu-id="d0738-123">Installieren Sie .NET Core-Tools nur von Autoren, denen Sie vertrauen.</span><span class="sxs-lookup"><span data-stu-id="d0738-123">Do not install a .NET Core tool unless you trust the author.</span></span>

## <a name="find-a-tool"></a><span data-ttu-id="d0738-124">Suchen eines Tools</span><span class="sxs-lookup"><span data-stu-id="d0738-124">Find a tool</span></span>

<span data-ttu-id="d0738-125">Derzeit bietet .NET Core keine Suchfunktion für Tools.</span><span class="sxs-lookup"><span data-stu-id="d0738-125">Currently, .NET Core doesn't have a tool search feature.</span></span> <span data-ttu-id="d0738-126">Es folgen einige Möglichkeiten, Tools zu finden:</span><span class="sxs-lookup"><span data-stu-id="d0738-126">Here are some ways to find tools:</span></span>

* <span data-ttu-id="d0738-127">Sehen Sie sich die Liste der Tools im GitHub-Repository [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) an.</span><span class="sxs-lookup"><span data-stu-id="d0738-127">See the list of tools in the [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub repository.</span></span>
* <span data-ttu-id="d0738-128">Verwenden Sie [ToolGet](https://www.toolget.net/), um nach .NET-Tools zu suchen.</span><span class="sxs-lookup"><span data-stu-id="d0738-128">Use [ToolGet](https://www.toolget.net/) to search for .NET tools.</span></span>
* <span data-ttu-id="d0738-129">Sehen Sie sich den Quellcode der vom ASP.NET Core-Team im [GitHub-Repository dotnet/aspnetcore im Verzeichnis „Tools“](https://github.com/dotnet/aspnetcore/tree/master/src/Tools) erstellten Tools an.</span><span class="sxs-lookup"><span data-stu-id="d0738-129">See the source code for the tools created by the ASP.NET Core team in the [Tools directory of the dotnet/aspnetcore GitHub repository](https://github.com/dotnet/aspnetcore/tree/master/src/Tools).</span></span>
* <span data-ttu-id="d0738-130">Weitere Informationen zu Diagnosetools finden Sie unter [Globale .NET Core-dotnet-Diagnosetools](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools).</span><span class="sxs-lookup"><span data-stu-id="d0738-130">Learn about diagnostic tools at [.NET Core dotnet diagnostic tools](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools).</span></span>
* <span data-ttu-id="d0738-131">Durchsuchen Sie die [NuGet](https://www.nuget.org)-Website.</span><span class="sxs-lookup"><span data-stu-id="d0738-131">Search the [NuGet](https://www.nuget.org) website.</span></span> <span data-ttu-id="d0738-132">Die NuGet-Website bietet jedoch noch keine Funktion, mit der Sie ausschließlich nach Toolpaketen suchen können.</span><span class="sxs-lookup"><span data-stu-id="d0738-132">However, the NuGet site doesn't yet have a feature that lets you search only for tool packages.</span></span>

## <a name="check-the-author-and-statistics"></a><span data-ttu-id="d0738-133">Überprüfen des Autors und der Statistiken</span><span class="sxs-lookup"><span data-stu-id="d0738-133">Check the author and statistics</span></span>

<span data-ttu-id="d0738-134">Da .NET Core-Tools mit voller Vertrauenswürdigkeit ausgeführt und globale Tools der Umgebungsvariablen PATH hinzugefügt werden, können sie sehr leistungsfähig sein.</span><span class="sxs-lookup"><span data-stu-id="d0738-134">Since .NET Core tools run in full trust, and global tools are added to the PATH environment variable, they can be very powerful.</span></span> <span data-ttu-id="d0738-135">Laden Sie keine Tools von Personen herunter, denen Sie nicht vertrauen.</span><span class="sxs-lookup"><span data-stu-id="d0738-135">Don't download tools from people you don't trust.</span></span>

<span data-ttu-id="d0738-136">Wenn das Tool auf NuGet gehostet wird, können Sie den Autor und seine Statistiken überprüfen, indem Sie nach dem Tool suchen.</span><span class="sxs-lookup"><span data-stu-id="d0738-136">If the tool is hosted on NuGet, you can check the author and statistics by searching for the tool.</span></span>

## <a name="install-a-global-tool"></a><span data-ttu-id="d0738-137">Installieren eines globalen Tools</span><span class="sxs-lookup"><span data-stu-id="d0738-137">Install a global tool</span></span>

<span data-ttu-id="d0738-138">Um ein Tool als globales Tool zu installieren, verwenden Sie, wie im folgenden Beispiel gezeigt, mit [dotnet tool install](dotnet-tool-install.md) die Option `-g` oder `--global`:</span><span class="sxs-lookup"><span data-stu-id="d0738-138">To install a tool as a global tool, use the `-g` or `--global` option of [dotnet tool install](dotnet-tool-install.md), as shown in the following example:</span></span>

```dotnetcli
dotnet tool install -g dotnetsay
```

<span data-ttu-id="d0738-139">Die Ausgabe zeigt den zum Aufrufen des Tools verwendeten Befehl und die installierte Version, ähnlich wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d0738-139">The output shows the command used to invoke the tool and the version installed, similar to the following example:</span></span>

```output
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.1.4') was successfully installed.
```

<span data-ttu-id="d0738-140">Der Standardspeicherort der Binärdateien eines Tools hängt vom Betriebssystem ab:</span><span class="sxs-lookup"><span data-stu-id="d0738-140">The default location for a tool's binaries depends on the operating system:</span></span>

| <span data-ttu-id="d0738-141">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="d0738-141">OS</span></span>          | <span data-ttu-id="d0738-142">Pfad</span><span class="sxs-lookup"><span data-stu-id="d0738-142">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="d0738-143">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="d0738-143">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="d0738-144">Windows</span><span class="sxs-lookup"><span data-stu-id="d0738-144">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="d0738-145">Dieser Speicherort wird beim ersten Ausführen des SDK dem Pfad des Benutzers hinzugefügt, sodass globale Tools in jedem beliebigen Verzeichnis aufgerufen werden können, ohne dass der Speicherort des Tools angegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="d0738-145">This location is added to the user's path when the SDK is first run, so global tools can be invoked from any directory without specifying the tool location.</span></span>

<span data-ttu-id="d0738-146">Der Zugriff auf Tools ist benutzerspezifisch und gilt nicht global auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="d0738-146">Tool access is user-specific, not machine global.</span></span> <span data-ttu-id="d0738-147">Ein globales Tool ist nur für den Benutzer verfügbar, der das Tool installiert hat.</span><span class="sxs-lookup"><span data-stu-id="d0738-147">A global tool is only available to the user that installed the tool.</span></span>

### <a name="install-a-global-tool-in-a-custom-location"></a><span data-ttu-id="d0738-148">Installieren eines globalen Tools an einem benutzerdefinierten Speicherort</span><span class="sxs-lookup"><span data-stu-id="d0738-148">Install a global tool in a custom location</span></span>

<span data-ttu-id="d0738-149">Um ein Tool als globales Tool an einem benutzerdefinierten Speicherort zu installieren, verwenden Sie, wie in den folgenden Beispielen gezeigt, mit [dotnet tool install](dotnet-tool-install.md) die Option `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="d0738-149">To install a tool as a global tool in a custom location, use the `--tool-path` option of [dotnet tool install](dotnet-tool-install.md), as shown in the following examples.</span></span>

<span data-ttu-id="d0738-150">Unter Windows:</span><span class="sxs-lookup"><span data-stu-id="d0738-150">On Windows:</span></span>

```dotnetcli
dotnet tool install dotnetsay --tool-path c:\dotnet-tools
```

<span data-ttu-id="d0738-151">Unter Linux oder macOS:</span><span class="sxs-lookup"><span data-stu-id="d0738-151">On Linux or macOS:</span></span>

```dotnetcli
dotnet tool install dotnetsay --tool-path ~/bin
```

<span data-ttu-id="d0738-152">Das .NET Core SDK fügt diesen Speicherort nicht automatisch der Umgebungsvariablen PATH hinzu.</span><span class="sxs-lookup"><span data-stu-id="d0738-152">The .NET Core SDK doesn't add this location automatically to the PATH environment variable.</span></span> <span data-ttu-id="d0738-153">Zum [Aufrufen eines Toolpfadtools](#invoke-a-tool-path-tool) müssen Sie sicherstellen, dass der Befehl verfügbar ist, indem Sie eine der folgenden Methoden verwenden:</span><span class="sxs-lookup"><span data-stu-id="d0738-153">To [invoke a tool-path tool](#invoke-a-tool-path-tool), you have to make sure the command is available by using one of the following methods:</span></span>

* <span data-ttu-id="d0738-154">Fügen Sie das Installationsverzeichnis der Umgebungsvariablen PATH hinzu.</span><span class="sxs-lookup"><span data-stu-id="d0738-154">Add the installation directory to the PATH environment variable.</span></span>
* <span data-ttu-id="d0738-155">Geben Sie den vollständigen Pfad zum Tool an, wenn Sie es aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d0738-155">Specify the full path to the tool when you invoke it.</span></span>
* <span data-ttu-id="d0738-156">Rufen das Tool im Installationsverzeichnis auf.</span><span class="sxs-lookup"><span data-stu-id="d0738-156">Invoke the tool from within the installation directory.</span></span>

## <a name="install-a-local-tool"></a><span data-ttu-id="d0738-157">Installieren eines lokalen Tools</span><span class="sxs-lookup"><span data-stu-id="d0738-157">Install a local tool</span></span>

<span data-ttu-id="d0738-158">**Gilt ab .NET Core 3.0 SDK.**</span><span class="sxs-lookup"><span data-stu-id="d0738-158">**Applies to .NET Core 3.0 SDK and later.**</span></span>

<span data-ttu-id="d0738-159">Um ein Tool nur für den lokalen Zugriff (für das aktuelle Verzeichnis und Unterverzeichnisse) zu installieren, muss es der Manifestdatei des Tools hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d0738-159">To install a tool for local access only (for the current directory and subdirectories), it has to be added to a tool manifest file.</span></span> <span data-ttu-id="d0738-160">Führen Sie den Befehl `dotnet new tool-manifest` aus, um eine Manifestdatei für das Tool zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="d0738-160">To create a tool manifest file, run the `dotnet new tool-manifest` command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="d0738-161">Mit diesem Befehl wird im Verzeichnis *.config* eine Manifestdatei mit dem Namen *dotnet-tools.json* erstellt.</span><span class="sxs-lookup"><span data-stu-id="d0738-161">This command creates a manifest file named *dotnet-tools.json* under the *.config* directory.</span></span> <span data-ttu-id="d0738-162">Um der Manifestdatei ein lokales Tool hinzuzufügen, verwenden Sie den Befehl [dotnet tool install](dotnet-tool-install.md) **ohne** die Optionen `--global` und `--tool-path`, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d0738-162">To add a local tool to the manifest file, use the [dotnet tool install](dotnet-tool-install.md) command and **omit** the `--global` and `--tool-path` options, as shown in the following example:</span></span>

```dotnetcli
dotnet tool install dotnetsay
```

<span data-ttu-id="d0738-163">Die Befehlsausgabe zeigt, in welcher Manifestdatei sich das neu installierte Tool befindet, ähnlich wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d0738-163">The command output shows which manifest file the newly installed tool is in, similar to the following example:</span></span>

```console
You can invoke the tool from this directory using the following command:
dotnet tool run dotnetsay
Tool 'dotnetsay' (version '2.1.4') was successfully installed.
Entry is added to the manifest file /home/name/botsay/.config/dotnet-tools.json.
```

<span data-ttu-id="d0738-164">Das folgende Beispiel zeigt eine Manifestdatei, in der zwei lokale Tools installiert sind:</span><span class="sxs-lookup"><span data-stu-id="d0738-164">The following example shows a manifest file with two local tools installed:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "botsay": {
      "version": "1.0.0",
      "commands": [
        "botsay"
      ]
    },
    "dotnetsay": {
      "version": "2.1.3",
      "commands": [
        "dotnetsay"
      ]
    }
  }
}
```

<span data-ttu-id="d0738-165">In der Regel fügen Sie ein lokales Tool zum Stammverzeichnis des Repositorys hinzu.</span><span class="sxs-lookup"><span data-stu-id="d0738-165">You typically add a local tool to the root directory of the repository.</span></span> <span data-ttu-id="d0738-166">Nach dem Einchecken der Manifestdatei im Repository erhalten Entwickler, die Code aus dem Repository auschecken, die neueste Manifestdatei.</span><span class="sxs-lookup"><span data-stu-id="d0738-166">After you check in the manifest file to the repository, developers who check out code from the repository get the latest manifest file.</span></span> <span data-ttu-id="d0738-167">Um alle in der Manifestdatei aufgeführten Tools zu installieren, führen sie den Befehl `dotnet tool restore` aus:</span><span class="sxs-lookup"><span data-stu-id="d0738-167">To install all of the tools listed in the manifest file, they run the `dotnet tool restore` command:</span></span>

```dotnetcli
dotnet tool restore
```

<span data-ttu-id="d0738-168">Die Ausgabe gibt an, welche Tools wiederhergestellt wurden:</span><span class="sxs-lookup"><span data-stu-id="d0738-168">The output indicates which tools were restored:</span></span>

```console
Tool 'botsay' (version '1.0.0') was restored. Available commands: botsay
Tool 'dotnetsay' (version '2.1.3') was restored. Available commands: dotnetsay
Restore was successful.
```

## <a name="install-a-specific-tool-version"></a><span data-ttu-id="d0738-169">Installieren einer bestimmten Toolversion</span><span class="sxs-lookup"><span data-stu-id="d0738-169">Install a specific tool version</span></span>

<span data-ttu-id="d0738-170">Um eine Vorab- oder bestimmte Version eines Tools zu installieren, geben Sie die Versionsnummer mit der Option `--version` an, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d0738-170">To install a pre-release version or a specific version of a tool, specify the version number by using the `--version` option, as shown in the following example:</span></span>

```dotnetcli
dotnet tool install dotnetsay --version 2.1.3
```

## <a name="use-a-tool"></a><span data-ttu-id="d0738-171">Verwenden eines Tools</span><span class="sxs-lookup"><span data-stu-id="d0738-171">Use a tool</span></span>

<span data-ttu-id="d0738-172">Der Befehl zum Aufrufen eines Tools kann sich vom Namen des Pakets, das Sie installieren, unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="d0738-172">The command that you use to invoke a tool may be different from the name of the package that you install.</span></span> <span data-ttu-id="d0738-173">Um alle derzeit für den aktuellen Benutzer auf dem Computer installierten Tools anzuzeigen, führen Sie den Befehl [dotnet tool list](dotnet-tool-list.md) aus:</span><span class="sxs-lookup"><span data-stu-id="d0738-173">To display all of the tools currently installed on the machine for the current user, use the [dotnet tool list](dotnet-tool-list.md) command:</span></span>

```dotnetcli
dotnet tool list
```

<span data-ttu-id="d0738-174">Die Ausgabe zeigt die Version und den Befehl jedes Tools, ähnlich wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d0738-174">The output shows each tool's version and command, similar to the following example:</span></span>

```console
Package Id      Version      Commands       Manifest
-------------------------------------------------------------------------------------------
botsay          1.0.0        botsay         /home/name/repository/.config/dotnet-tools.json
dotnetsay       2.1.3        dotnetsay      /home/name/repository/.config/dotnet-tools.json
```

<span data-ttu-id="d0738-175">Wie in diesem Beispiel gezeigt, enthält die Liste lokale Tools.</span><span class="sxs-lookup"><span data-stu-id="d0738-175">As shown in this example, the list shows local tools.</span></span> <span data-ttu-id="d0738-176">Zum Anzeigen globaler Tools verwenden Sie die Option `--global`. Zum Anzeigen von Toolpfadtools wählen Sie die Option `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="d0738-176">To see global tools, use the `--global` option, and to see tool-path tools, use the `--tool-path` option.</span></span>

### <a name="invoke-a-global-tool"></a><span data-ttu-id="d0738-177">Aufrufen eines globalen Tools</span><span class="sxs-lookup"><span data-stu-id="d0738-177">Invoke a global tool</span></span>

<span data-ttu-id="d0738-178">Verwenden Sie für globale Tools den Tool-Befehl eigenständig.</span><span class="sxs-lookup"><span data-stu-id="d0738-178">For global tools, use the tool command by itself.</span></span> <span data-ttu-id="d0738-179">Wenn der Befehl beispielsweise `dotnetsay` oder `dotnet-doc` lautet, verwenden Sie Folgendes, um den Befehl aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="d0738-179">For example, if the command is `dotnetsay` or `dotnet-doc`, that's what you use to invoke the command:</span></span>

```console
dotnetsay
dotnet-doc
```

<span data-ttu-id="d0738-180">Wenn der Befehl mit dem Präfix `dotnet-` beginnt, können Sie das Tool alternativ auch mit dem Befehl `dotnet` ohne das Präfix des tool-Befehls aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d0738-180">If the command begins with the prefix `dotnet-`, an alternative way to invoke the tool is to use the `dotnet` command and omit the tool command prefix.</span></span> <span data-ttu-id="d0738-181">Wenn der Befehl z. B. `dotnet-doc` lautet, wird das Tool mit dem folgenden Befehl aufgerufen:</span><span class="sxs-lookup"><span data-stu-id="d0738-181">For example, if the command is `dotnet-doc`, the following command invokes the tool:</span></span>

```dotnetcli
dotnet doc
```

<span data-ttu-id="d0738-182">Im folgenden Szenario können Sie jedoch nicht den Befehl `dotnet` verwenden, um ein globales Tool aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="d0738-182">However, in the following scenario you can't use the `dotnet` command to invoke a global tool:</span></span>

* <span data-ttu-id="d0738-183">Für ein globales Tool und ein lokales Tool gilt der gleiche Befehl mit dem Präfix `dotnet-`.</span><span class="sxs-lookup"><span data-stu-id="d0738-183">A global tool and a local tool have the same command prefixed by `dotnet-`.</span></span>
* <span data-ttu-id="d0738-184">Sie möchten das globale Tool in einem Verzeichnis aufrufen, das im Geltungsbereich des lokalen Tools liegt.</span><span class="sxs-lookup"><span data-stu-id="d0738-184">You want to invoke the global tool from a directory that is in scope for the local tool.</span></span>

<span data-ttu-id="d0738-185">In diesem Fall rufen `dotnet doc` und `dotnet dotnet-doc` das lokale Tool auf.</span><span class="sxs-lookup"><span data-stu-id="d0738-185">In this scenario, `dotnet doc` and `dotnet dotnet-doc` invoke the local tool.</span></span> <span data-ttu-id="d0738-186">Um das globale Tool aufzurufen, verwenden Sie den Befehl eigenständig:</span><span class="sxs-lookup"><span data-stu-id="d0738-186">To invoke the global tool, use the command by itself:</span></span>

```dotnetcli
dotnet-doc
```

### <a name="invoke-a-tool-path-tool"></a><span data-ttu-id="d0738-187">Aufrufen eines Toolpfadtools</span><span class="sxs-lookup"><span data-stu-id="d0738-187">Invoke a tool-path tool</span></span>

<span data-ttu-id="d0738-188">Um ein globales Tool aufzurufen, das mit der Option `tool-path` installiert wurde, stellen Sie sicher, dass der Befehl verfügbar ist, was [weiter oben in diesem Artikel](#install-a-global-tool-in-a-custom-location) erläutert wurde.</span><span class="sxs-lookup"><span data-stu-id="d0738-188">To invoke a global tool that is installed by using the `tool-path` option, make sure the command is available, as explained [earlier in this article](#install-a-global-tool-in-a-custom-location).</span></span>

### <a name="invoke-a-local-tool"></a><span data-ttu-id="d0738-189">Aufrufen eines lokalen Tools</span><span class="sxs-lookup"><span data-stu-id="d0738-189">Invoke a local tool</span></span>

<span data-ttu-id="d0738-190">Um ein lokales Tool aufzurufen, müssen Sie im Installationsverzeichnis den Befehl `dotnet` ausführen.</span><span class="sxs-lookup"><span data-stu-id="d0738-190">To invoke a local tool, you have to use the `dotnet` command from within the installation directory.</span></span> <span data-ttu-id="d0738-191">Sie können die Langform (`dotnet tool run <COMMAND_NAME>`) oder Kurzform (`dotnet <COMMAND_NAME>`) verwenden, wie in den folgenden Beispielen gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d0738-191">You can use the long form (`dotnet tool run <COMMAND_NAME>`) or the short form (`dotnet <COMMAND_NAME>`), as shown in the following examples:</span></span>

```dotnetcli
dotnet tool run dotnetsay
dotnet dotnetsay
```

<span data-ttu-id="d0738-192">Wenn dem Befehl das Präfix `dotnet-` vorangestellt ist, können Sie das Präfix beim Aufruf des Tools einschließen oder weglassen.</span><span class="sxs-lookup"><span data-stu-id="d0738-192">If the command is prefixed by `dotnet-`, you can include or omit the prefix when you invoke the tool.</span></span> <span data-ttu-id="d0738-193">Wenn der Befehl z. B. `dotnet-doc` lautet, ruft eines der folgenden Beispiele das lokale Tool auf:</span><span class="sxs-lookup"><span data-stu-id="d0738-193">For example, if the command is `dotnet-doc`, any of the following examples invokes the local tool:</span></span>

```dotnetcli
dotnet tool run dotnet-doc
dotnet dotnet-doc
dotnet doc
```

## <a name="update-a-tool"></a><span data-ttu-id="d0738-194">Aktualisieren eines Tools</span><span class="sxs-lookup"><span data-stu-id="d0738-194">Update a tool</span></span>

<span data-ttu-id="d0738-195">Das Aktualisieren eines Tools umfasst das Deinstallieren und Neuinstallieren mit der neuesten stabilen Version.</span><span class="sxs-lookup"><span data-stu-id="d0738-195">Updating a tool involves uninstalling and reinstalling it with the latest stable version.</span></span> <span data-ttu-id="d0738-196">Verwenden Sie zum Aktualisieren eines Tools den Befehl [dotnet tool update](dotnet-tool-update.md) mit derselben Option, die Sie auch zur Installation des Tools verwendet haben:</span><span class="sxs-lookup"><span data-stu-id="d0738-196">To update a tool, use the [dotnet tool update](dotnet-tool-update.md) command with the same option that you used to install the tool:</span></span>

```dotnetcli
dotnet tool update --global <packagename>
dotnet tool update --tool-path <packagename>
dotnet tool update <packagename>
```

<span data-ttu-id="d0738-197">Bei einem lokalen Tool findet das SDK die erste Manifestdatei, die die Paket-ID enthält, indem es im aktuellen Verzeichnis und den übergeordneten Verzeichnissen eine Suche durchführt.</span><span class="sxs-lookup"><span data-stu-id="d0738-197">For a local tool, the SDK finds the first manifest file that contains the package ID by looking in the current directory and parent directories.</span></span> <span data-ttu-id="d0738-198">Wenn es in keiner Manifestdatei keine solche Paket-ID gibt, fügt das SDK der nächstgelegenen Manifestdatei einen neuen Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="d0738-198">If there is no such package ID in any manifest file, the SDK adds a new entry to the closest manifest file.</span></span>

## <a name="uninstall-a-tool"></a><span data-ttu-id="d0738-199">Deinstallieren eines Tools</span><span class="sxs-lookup"><span data-stu-id="d0738-199">Uninstall a tool</span></span>

<span data-ttu-id="d0738-200">Entfernen Sie ein Tool mit dem Befehl [dotnet tool uninstall](dotnet-tool-uninstall.md) mit der gleichen Option, die Sie zur Installation des Tools verwendet haben:</span><span class="sxs-lookup"><span data-stu-id="d0738-200">Remove a tool by using the [dotnet tool uninstall](dotnet-tool-uninstall.md) command with the same option that you used to install the tool:</span></span>

```dotnetcli
dotnet tool uninstall --global <packagename>
dotnet tool uninstall --tool-path<packagename>
dotnet tool uninstall <packagename>
```

<span data-ttu-id="d0738-201">Bei einem lokalen Tool findet das SDK die erste Manifestdatei, die die Paket-ID enthält, indem es im aktuellen Verzeichnis und den übergeordneten Verzeichnissen eine Suche durchführt.</span><span class="sxs-lookup"><span data-stu-id="d0738-201">For a local tool, the SDK finds the first manifest file that contains the package ID by looking in the current directory and parent directories.</span></span>

## <a name="get-help-and-troubleshoot"></a><span data-ttu-id="d0738-202">Hilfe und Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="d0738-202">Get help and troubleshoot</span></span>

<span data-ttu-id="d0738-203">Zum Abrufen einer Liste der verfügbaren `dotnet tool`-Befehle geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="d0738-203">To get a list of available `dotnet tool` commands, enter the following command:</span></span>

```dotnetcli
dotnet tool --help
```

<span data-ttu-id="d0738-204">Um Anweisungen zur Nutzung des Tools zu erhalten, geben Sie einen der folgenden Befehle ein, oder besuchen Sie die Website des Tools:</span><span class="sxs-lookup"><span data-stu-id="d0738-204">To get tool usage instructions, enter one of the following commands or see the tool's website:</span></span>

```dotnetcli
<command> --help
dotnet <command> --help
```

<span data-ttu-id="d0738-205">Wenn ein Tool nicht installiert oder ausgeführt werden kann, finden Sie unter [Behandlung von Problemen bei der Nutzung von .NET Core-Tools](troubleshoot-usage-issues.md) weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="d0738-205">If a tool fails to install or run, see [Troubleshoot .NET Core tool usage issues](troubleshoot-usage-issues.md).</span></span>
