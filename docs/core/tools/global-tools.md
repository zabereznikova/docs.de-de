---
title: Globale .NET Core-Tools
description: Eine Übersicht über globale .NET Core-Tools und die .NET Core-CLI-Befehle, die ihnen zur Verfügung stehen.
author: KathleenDollard
ms.date: 05/29/2018
ms.openlocfilehash: 0df3c1b615adfeaaf41542dc8252a8f14f49f6f9
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899863"
---
# <a name="net-core-global-tools-overview"></a><span data-ttu-id="ad066-103">Übersicht über globale .NET Core-Tools</span><span class="sxs-lookup"><span data-stu-id="ad066-103">.NET Core Global Tools overview</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

<span data-ttu-id="ad066-104">Ein globales .NET Core-Tool ist ein spezielles NuGet-Paket, das eine Konsolenanwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="ad066-104">A .NET Core Global Tool is a special NuGet package that contains a console application.</span></span> <span data-ttu-id="ad066-105">Ein globales Tool kann an einem benutzerdefinierten Speicherort oder einem Standardspeicherort auf ihrem Computer installiert werden, der in der Umgebungsvariable „PATH“ enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="ad066-105">A Global Tool can be installed on your machine on a default location that is included in the PATH environment variable or on a custom location.</span></span>

<span data-ttu-id="ad066-106">Wenn Sie ein globales .NET Core-Tool verwenden möchten:</span><span class="sxs-lookup"><span data-stu-id="ad066-106">If you want to use a .NET Core Global Tool:</span></span>

* <span data-ttu-id="ad066-107">Erfahren Sie mehr über das Tool (in der Regel über eine Website oder GitHub-Seite).</span><span class="sxs-lookup"><span data-stu-id="ad066-107">Find information about the tool (usually a website or GitHub page).</span></span>
* <span data-ttu-id="ad066-108">Überprüfen Sie den Autor und die Statistiken auf der Startseite des Feeds (in der Regel NuGet.org).</span><span class="sxs-lookup"><span data-stu-id="ad066-108">Check the author and statistics in the home for the feed (usually NuGet.org).</span></span>
* <span data-ttu-id="ad066-109">Installieren Sie das Tool.</span><span class="sxs-lookup"><span data-stu-id="ad066-109">Install the tool.</span></span>
* <span data-ttu-id="ad066-110">Rufen Sie das Tool auf.</span><span class="sxs-lookup"><span data-stu-id="ad066-110">Call the tool.</span></span>
* <span data-ttu-id="ad066-111">Aktualisieren Sie das Tool.</span><span class="sxs-lookup"><span data-stu-id="ad066-111">Update the tool.</span></span>
* <span data-ttu-id="ad066-112">Deinstallieren Sie das Tool.</span><span class="sxs-lookup"><span data-stu-id="ad066-112">Uninstall the tool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ad066-113">Globale .NET Core-Tools werden in Ihrem Pfad angezeigt und mit voller Vertrauenswürdigkeit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ad066-113">.NET Core Global Tools appear on your path and run in full trust.</span></span> <span data-ttu-id="ad066-114">Installieren Sie nur globale .NET Core-Tools von Autoren, denen Sie vertrauen.</span><span class="sxs-lookup"><span data-stu-id="ad066-114">Do not install .NET Core Global Tools unless you trust the author.</span></span>

## <a name="find-a-net-core-global-tool"></a><span data-ttu-id="ad066-115">Finden eines globalen .NET Core-Tools</span><span class="sxs-lookup"><span data-stu-id="ad066-115">Find a .NET Core Global Tool</span></span>

<span data-ttu-id="ad066-116">Derzeit gibt es kein Suchfeature für globale Tools in der .NET Core-CLI (Befehlszeilenschnittstelle).</span><span class="sxs-lookup"><span data-stu-id="ad066-116">Currently, there isn't a Global Tool search feature in the .NET Core Command-line Interface (CLI).</span></span> <span data-ttu-id="ad066-117">Im Folgenden finden Sie einige Empfehlungen zum Ermitteln der Tools:</span><span class="sxs-lookup"><span data-stu-id="ad066-117">The following are some recommendations on how to find tools:</span></span>

* <span data-ttu-id="ad066-118">Sie können globale .NET Core-Tools auf [NuGet](https://www.nuget.org) finden.</span><span class="sxs-lookup"><span data-stu-id="ad066-118">You can find .NET Core Global Tools on [NuGet](https://www.nuget.org).</span></span> <span data-ttu-id="ad066-119">Allerdings können Sie auf der NuGet-Website nicht spezifisch nach globalen .NET Core-Tools suchen.</span><span class="sxs-lookup"><span data-stu-id="ad066-119">However, NuGet doesn't yet allow you to search specifically for .NET Core Global Tools.</span></span>
* <span data-ttu-id="ad066-120">Empfehlungen für Tools finden Sie in Blogbeiträgen oder im GitHub-Repository [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools).</span><span class="sxs-lookup"><span data-stu-id="ad066-120">You may find tool recommendations in blog posts or in the [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub repository.</span></span>
* <span data-ttu-id="ad066-121">Sie können sich den Quellcode für die vom ASP.NET-Team erstellten globalen Tools im GitHub-Repository [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/tree/master/src/Tools) ansehen.</span><span class="sxs-lookup"><span data-stu-id="ad066-121">You can see the source code for the Global Tools created by the ASP.NET team at the [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/tree/master/src/Tools) GitHub repository.</span></span>
* <span data-ttu-id="ad066-122">Weitere Informationen zu Diagnosetools finden Sie unter [Globale .NET Core-dotnet-Diagnosetools](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools).</span><span class="sxs-lookup"><span data-stu-id="ad066-122">You can learn about diagnostic tools at [.NET Core dotnet diagnostic Global Tools](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools).</span></span>

## <a name="check-the-author-and-statistics"></a><span data-ttu-id="ad066-123">Überprüfen des Autors und der Statistiken</span><span class="sxs-lookup"><span data-stu-id="ad066-123">Check the author and statistics</span></span>

<span data-ttu-id="ad066-124">Da globale .NET Core-Tools mit voller Vertrauenswürdigkeit ausgeführt und in der Regel auf Ihrem Pfad installiert werden, können sie sehr nützlich sein.</span><span class="sxs-lookup"><span data-stu-id="ad066-124">Since .NET Core Global Tools run in full trust and are generally installed on your path, they can be very powerful.</span></span> <span data-ttu-id="ad066-125">Laden Sie keine Tools von Personen herunter, denen Sie nicht vertrauen.</span><span class="sxs-lookup"><span data-stu-id="ad066-125">Don't download tools from people you don't trust.</span></span>

<span data-ttu-id="ad066-126">Wenn das Tool auf NuGet gehostet wird, können Sie den Autor und seine Statistiken überprüfen, indem Sie nach dem Tool suchen.</span><span class="sxs-lookup"><span data-stu-id="ad066-126">If the tool is hosted on NuGet, you can check the author and statistics by searching for the tool.</span></span>

## <a name="install-a-global-tool"></a><span data-ttu-id="ad066-127">Installieren eines globalen Tools</span><span class="sxs-lookup"><span data-stu-id="ad066-127">Install a Global Tool</span></span>

<span data-ttu-id="ad066-128">Verwenden Sie den .NET Core-CLI-Befehl [dotnet tool install](dotnet-tool-install.md), um ein globales Tool zu installieren.</span><span class="sxs-lookup"><span data-stu-id="ad066-128">To install a Global Tool, you use the [dotnet tool install](dotnet-tool-install.md) .NET Core CLI command.</span></span> <span data-ttu-id="ad066-129">Im folgenden Beispiel wird gezeigt, wie ein globales Tool am Standardspeicherort installiert wird:</span><span class="sxs-lookup"><span data-stu-id="ad066-129">The following example shows how to install a Global Tool in the default location:</span></span>

```dotnetcli
dotnet tool install -g dotnetsay
```

<span data-ttu-id="ad066-130">Wenn das Tool nicht installiert werden kann, werden Fehlermeldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ad066-130">If the tool can't be installed, error messages are displayed.</span></span> <span data-ttu-id="ad066-131">Stellen Sie sicher, dass die erwarteten Feeds überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="ad066-131">Check that the feeds you expected are being checked.</span></span>

<span data-ttu-id="ad066-132">Wenn Sie versuchen, eine Vorabversion oder eine spezifische Version des Tools zu installieren, können Sie die Versionsnummer im folgenden Format angeben:</span><span class="sxs-lookup"><span data-stu-id="ad066-132">If you're trying to install a pre-release version or a specific version of the tool, you can specify the version number using the following format:</span></span>

```dotnetcli
dotnet tool install -g <package-name> --version <version-number>
```

<span data-ttu-id="ad066-133">Wenn die Installation erfolgreich abgeschlossen wurde, wird eine Meldung angezeigt, die den Befehl zum Aufrufen des Tools und die installierte Version ähnlich wie im folgenden Beispiel anzeigt:</span><span class="sxs-lookup"><span data-stu-id="ad066-133">If installation is successful, a message is displayed showing the command used to call the tool and the version installed, similar to the following example:</span></span>

```output
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.0.0') was successfully installed.
```

<span data-ttu-id="ad066-134">Globale Tools können im Standardverzeichnis oder an einem spezifischen Speicherort installiert werden.</span><span class="sxs-lookup"><span data-stu-id="ad066-134">Global Tools can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="ad066-135">Die Standardverzeichnisse sind:</span><span class="sxs-lookup"><span data-stu-id="ad066-135">The default directories are:</span></span>

| <span data-ttu-id="ad066-136">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="ad066-136">OS</span></span>          | <span data-ttu-id="ad066-137">Pfad</span><span class="sxs-lookup"><span data-stu-id="ad066-137">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="ad066-138">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="ad066-138">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="ad066-139">Windows</span><span class="sxs-lookup"><span data-stu-id="ad066-139">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="ad066-140">Diese Speicherorte werden dem Pfad des Benutzers hinzugefügt, wenn das SDK zum ersten Mal ausgeführt wird, damit dort installierte globale Tools direkt aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="ad066-140">These locations are added to the user's path when the SDK is first run, so Global Tools installed there can be called directly.</span></span>

<span data-ttu-id="ad066-141">Beachten Sie, dass die globalen Tools benutzerspezifisch gespeichert werden und nicht global auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="ad066-141">Note that the Global Tools are user-specific, not machine global.</span></span> <span data-ttu-id="ad066-142">Deshalb können Sie kein globales Tool installieren, das für alle Benutzer auf dem Computer verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ad066-142">Being user-specific means you cannot install a Global Tool that is available to all users of the machine.</span></span> <span data-ttu-id="ad066-143">Das Tool ist nur für jedes Benutzerprofil verfügbar, auf denen das Tool installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ad066-143">The tool is only available for each user profile where the tool was installed.</span></span>

<span data-ttu-id="ad066-144">Globale Tools können auch in einem spezifischen Verzeichnis installiert werden.</span><span class="sxs-lookup"><span data-stu-id="ad066-144">Global Tools can also be installed in a specific directory.</span></span> <span data-ttu-id="ad066-145">Wenn sie in einem spezifischen Verzeichnis installiert werden, muss der Benutzer sicherstellen, dass der Befehl verfügbar ist, indem das Verzeichnis in den Pfad eingefügt, der Befehl mit dem angegebenen Verzeichnis aufgerufen oder das Tool aus dem angegebenen Verzeichnis aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ad066-145">When installed in a specific directory, the user must ensure the command is available, by including that directory in the path, by calling the command with the directory specified, or calling the tool from within the specified directory.</span></span>
<span data-ttu-id="ad066-146">In diesem Fall fügt die .NET Core-CLI diesen Speicherort nicht automatisch der Umgebungsvariable „PATH“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="ad066-146">In this case, the .NET Core CLI doesn't add this location automatically to the PATH environment variable.</span></span>

## <a name="use-the-tool"></a><span data-ttu-id="ad066-147">Verwenden des Tools</span><span class="sxs-lookup"><span data-stu-id="ad066-147">Use the tool</span></span>

<span data-ttu-id="ad066-148">Nachdem das Tool installiert wurde, können Sie es mit dem entsprechenden Befehl aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ad066-148">Once the tool is installed, you can call it by using its command.</span></span> <span data-ttu-id="ad066-149">Beachten Sie, dass der Befehl möglicherweise nicht mit dem Paketnamen übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="ad066-149">Note that the command may not be the same as the package name.</span></span>

<span data-ttu-id="ad066-150">Wenn der Befehl `dotnetsay` ist, rufen Sie ihn wie folgt auf:</span><span class="sxs-lookup"><span data-stu-id="ad066-150">If the command is `dotnetsay`, you call it with:</span></span>

```console
dotnetsay
```

<span data-ttu-id="ad066-151">Wenn der Autor des Tools das Tool im Kontext der `dotnet`-Eingabeaufforderung anzeigen wollte, ist es möglicherweise so geschrieben, dass Sie es als `dotnet <command>` aufrufen, zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ad066-151">If the tool author wanted the tool to appear in the context of the `dotnet` prompt, they may have written it in a way that you call it as `dotnet <command>`, such as:</span></span>

```dotnetcli
dotnet doc
```

<span data-ttu-id="ad066-152">Sie können herausfinden, welche Tools in einem installierten Paket globaler Tools enthalten sind, indem Sie den Befehl [dotnet tool list](dotnet-tool-list.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="ad066-152">You can find which tools are included in an installed Global Tool package by listing the installed packages using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

<span data-ttu-id="ad066-153">Darüber hinaus können Sie sich die Anweisungen auf der Website zum Tool ansehen oder einen der folgenden Befehle eingeben:</span><span class="sxs-lookup"><span data-stu-id="ad066-153">You can also look for usage instructions at the tool's website or by typing one of the following commands:</span></span>

```console
<command> --help
dotnet <command> --help
```

## <a name="other-cli-commands"></a><span data-ttu-id="ad066-154">Andere CLI-Befehle</span><span class="sxs-lookup"><span data-stu-id="ad066-154">Other CLI commands</span></span>

<span data-ttu-id="ad066-155">Das .NET Core SDK enthält andere Befehle, die globale .NET Core-Tools unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ad066-155">The .NET Core SDK contains other commands that support .NET Core Global Tools.</span></span> <span data-ttu-id="ad066-156">Verwenden Sie einen beliebigen `dotnet tool`-Befehl mit einer der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="ad066-156">Use any of the `dotnet tool` commands with one of the following options:</span></span>

* <span data-ttu-id="ad066-157">`--global` oder `-g` gibt an, dass der Befehl für benutzerweite globale Tools anwendbar ist.</span><span class="sxs-lookup"><span data-stu-id="ad066-157">`--global` or `-g` specifies that the command is applicable to user-wide Global Tools.</span></span>
* <span data-ttu-id="ad066-158">`--tool-path` legt einen benutzerdefinierten Speicherort für globale Tools fest.</span><span class="sxs-lookup"><span data-stu-id="ad066-158">`--tool-path` specifies a custom location for Global Tools.</span></span>

<span data-ttu-id="ad066-159">So finden Sie heraus, welche Befehle für globale Tools verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="ad066-159">To find out which commands are available for Global Tools:</span></span>

```dotnetcli
dotnet tool --help
```

<span data-ttu-id="ad066-160">Das Aktualisieren eines globalen Tools umfasst das Deinstallieren und Neuinstallieren mit der neuesten stabilen Version.</span><span class="sxs-lookup"><span data-stu-id="ad066-160">Updating a Global Tool involves uninstalling and reinstalling it with the latest stable version.</span></span> <span data-ttu-id="ad066-161">Verwenden Sie den Befehl [dotnet tool update](dotnet-tool-update.md), um ein globales Tool zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="ad066-161">To update a Global Tool, use the [dotnet tool update](dotnet-tool-update.md) command:</span></span>

```dotnetcli
dotnet tool update -g <packagename>
```

<span data-ttu-id="ad066-162">Entfernen Sie ein globales Tool mit [dotnet tool uninstall](dotnet-tool-uninstall.md):</span><span class="sxs-lookup"><span data-stu-id="ad066-162">Remove a Global Tool using the [dotnet tool uninstall](dotnet-tool-uninstall.md):</span></span>

```dotnetcli
dotnet tool uninstall -g <packagename>
```

<span data-ttu-id="ad066-163">Verwenden Sie den Befehl [dotnet tool list](dotnet-tool-list.md), um alle derzeit auf dem Computer installierten globalen Tools mit ihren Versionen und Befehlen anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="ad066-163">To display all of the Global Tools currently installed on the machine, along with their version and commands, use the [dotnet tool list](dotnet-tool-list.md) command:</span></span>

```dotnetcli
dotnet tool list -g
```

## <a name="see-also"></a><span data-ttu-id="ad066-164">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad066-164">See also</span></span>

* [<span data-ttu-id="ad066-165">Behandlung von Problemen bei der Nutzung von .NET Core-Tools</span><span class="sxs-lookup"><span data-stu-id="ad066-165">Troubleshoot .NET Core tool usage issues</span></span>](troubleshoot-usage-issues.md)
