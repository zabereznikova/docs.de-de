---
title: Globale .NET Core-Tools
description: Eine Übersicht über globale .NET Core-Tools und die .NET Core-CLI-Befehle, die ihnen zur Verfügung stehen.
author: KathleenDollard
ms.date: 05/29/2018
ms.custom: seodec18
ms.openlocfilehash: 40a0aabcf523e8dac9a3ad226064bbb3c1b3ce5b
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332020"
---
# <a name="net-core-global-tools-overview"></a><span data-ttu-id="afa67-103">Übersicht über globale .NET Core-Tools</span><span class="sxs-lookup"><span data-stu-id="afa67-103">.NET Core Global Tools overview</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

<span data-ttu-id="afa67-104">Ein globales .NET Core-Tool ist ein spezielles NuGet-Paket, das eine Konsolenanwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="afa67-104">A .NET Core Global Tool is a special NuGet package that contains a console application.</span></span> <span data-ttu-id="afa67-105">Ein globales Tool kann an einem benutzerdefinierten Speicherort oder einem Standardspeicherort auf ihrem Computer installiert werden, der in der Umgebungsvariable „PATH“ enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="afa67-105">A Global Tool can be installed on your machine on a default location that is included in the PATH environment variable or on a custom location.</span></span>

<span data-ttu-id="afa67-106">Wenn Sie ein globales .NET Core-Tool verwenden möchten:</span><span class="sxs-lookup"><span data-stu-id="afa67-106">If you want to use a .NET Core Global Tool:</span></span>

* <span data-ttu-id="afa67-107">Erfahren Sie mehr über das Tool (in der Regel über eine Website oder GitHub-Seite).</span><span class="sxs-lookup"><span data-stu-id="afa67-107">Find information about the tool (usually a website or GitHub page).</span></span>
* <span data-ttu-id="afa67-108">Überprüfen Sie den Autor und die Statistiken auf der Startseite des Feeds (in der Regel NuGet.org).</span><span class="sxs-lookup"><span data-stu-id="afa67-108">Check the author and statistics in the home for the feed (usually NuGet.org).</span></span>
* <span data-ttu-id="afa67-109">Installieren Sie das Tool.</span><span class="sxs-lookup"><span data-stu-id="afa67-109">Install the tool.</span></span>
* <span data-ttu-id="afa67-110">Rufen Sie das Tool auf.</span><span class="sxs-lookup"><span data-stu-id="afa67-110">Call the tool.</span></span>
* <span data-ttu-id="afa67-111">Aktualisieren Sie das Tool.</span><span class="sxs-lookup"><span data-stu-id="afa67-111">Update the tool.</span></span>
* <span data-ttu-id="afa67-112">Deinstallieren Sie das Tool.</span><span class="sxs-lookup"><span data-stu-id="afa67-112">Uninstall the tool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="afa67-113">Globale .NET Core-Tools werden in Ihrem Pfad angezeigt und mit voller Vertrauenswürdigkeit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="afa67-113">.NET Core Global Tools appear on your path and run in full trust.</span></span> <span data-ttu-id="afa67-114">Installieren Sie nur globale .NET Core-Tools von Autoren, denen Sie vertrauen.</span><span class="sxs-lookup"><span data-stu-id="afa67-114">Do not install .NET Core Global Tools unless you trust the author.</span></span>

## <a name="find-a-net-core-global-tool"></a><span data-ttu-id="afa67-115">Finden eines globalen .NET Core-Tools</span><span class="sxs-lookup"><span data-stu-id="afa67-115">Find a .NET Core Global Tool</span></span>

<span data-ttu-id="afa67-116">Derzeit gibt es kein Suchfeature für globale Tools in der .NET Core-CLI (Befehlszeilenschnittstelle).</span><span class="sxs-lookup"><span data-stu-id="afa67-116">Currently, there isn't a Global Tool search feature in the .NET Core Command-line Interface (CLI).</span></span>

<span data-ttu-id="afa67-117">Sie können globale .NET Core-Tools auf [NuGet](https://www.nuget.org) finden.</span><span class="sxs-lookup"><span data-stu-id="afa67-117">You can find .NET Core Global Tools on [NuGet](https://www.nuget.org).</span></span> <span data-ttu-id="afa67-118">Allerdings können Sie auf der NuGet-Website nicht spezifisch nach globalen .NET Core-Tools suchen.</span><span class="sxs-lookup"><span data-stu-id="afa67-118">However, NuGet doesn't yet allow you to search specifically for .NET Core Global Tools.</span></span>

<span data-ttu-id="afa67-119">Empfehlungen von Tools können Sie auch in Blogbeiträgen oder im GitHub-Repository [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) finden.</span><span class="sxs-lookup"><span data-stu-id="afa67-119">You may also find tool recommendations in blog posts or in the [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub repository.</span></span>

<span data-ttu-id="afa67-120">Sie können sich auch den Quellcode für die vom ASP.NET-Team erstellten globalen Tools im GitHub-Repository [aspnet/DotNetTools](https://github.com/aspnet/DotNetTools/) ansehen.</span><span class="sxs-lookup"><span data-stu-id="afa67-120">You can also see the source code for the Global Tools created by the ASP.NET team at the [aspnet/DotNetTools](https://github.com/aspnet/DotNetTools/) GitHub repository.</span></span>

## <a name="check-the-author-and-statistics"></a><span data-ttu-id="afa67-121">Überprüfen des Autors und der Statistiken</span><span class="sxs-lookup"><span data-stu-id="afa67-121">Check the author and statistics</span></span>

<span data-ttu-id="afa67-122">Da globale .NET Core-Tools mit voller Vertrauenswürdigkeit ausgeführt und in der Regel auf Ihrem Pfad installiert werden, können sie sehr nützlich sein.</span><span class="sxs-lookup"><span data-stu-id="afa67-122">Since .NET Core Global Tools run in full trust and are generally installed on your path, they can be very powerful.</span></span> <span data-ttu-id="afa67-123">Laden Sie keine Tools von Personen herunter, denen Sie nicht vertrauen.</span><span class="sxs-lookup"><span data-stu-id="afa67-123">Don't download tools from people you don't trust.</span></span>

<span data-ttu-id="afa67-124">Wenn das Tool auf NuGet gehostet wird, können Sie den Autor und seine Statistiken überprüfen, indem Sie nach dem Tool suchen.</span><span class="sxs-lookup"><span data-stu-id="afa67-124">If the tool is hosted on NuGet, you can check the author and statistics by searching for the tool.</span></span>

## <a name="install-a-global-tool"></a><span data-ttu-id="afa67-125">Installieren eines globalen Tools</span><span class="sxs-lookup"><span data-stu-id="afa67-125">Install a Global Tool</span></span>

<span data-ttu-id="afa67-126">Verwenden Sie den .NET Core-CLI-Befehl [dotnet tool install](dotnet-tool-install.md), um ein globales Tool zu installieren.</span><span class="sxs-lookup"><span data-stu-id="afa67-126">To install a Global Tool, you use the [dotnet tool install](dotnet-tool-install.md) .NET Core CLI command.</span></span> <span data-ttu-id="afa67-127">Im folgenden Beispiel wird gezeigt, wie ein globales Tool am Standardspeicherort installiert wird:</span><span class="sxs-lookup"><span data-stu-id="afa67-127">The following example shows how to install a Global Tool in the default location:</span></span>

```dotnetcli
dotnet tool install -g dotnetsay
```

<span data-ttu-id="afa67-128">Wenn das Tool nicht installiert werden kann, werden Fehlermeldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="afa67-128">If the tool can't be installed, error messages are displayed.</span></span> <span data-ttu-id="afa67-129">Stellen Sie sicher, dass die erwarteten Feeds überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="afa67-129">Check that the feeds you expected are being checked.</span></span>

<span data-ttu-id="afa67-130">Wenn Sie versuchen, eine Vorabversion oder eine spezifische Version des Tools zu installieren, können Sie die Versionsnummer im folgenden Format angeben:</span><span class="sxs-lookup"><span data-stu-id="afa67-130">If you're trying to install a pre-release version or a specific version of the tool, you can specify the version number using the following format:</span></span>

```dotnetcli
dotnet tool install -g <package-name> --version <version-number>
```

<span data-ttu-id="afa67-131">Wenn die Installation erfolgreich abgeschlossen wurde, wird eine Meldung angezeigt, die den Befehl zum Aufrufen des Tools und die installierte Version ähnlich wie im folgenden Beispiel anzeigt:</span><span class="sxs-lookup"><span data-stu-id="afa67-131">If installation is successful, a message is displayed showing the command used to call the tool and the version installed, similar to the following example:</span></span>

```output
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.0.0') was successfully installed.
```

<span data-ttu-id="afa67-132">Globale Tools können im Standardverzeichnis oder an einem spezifischen Speicherort installiert werden.</span><span class="sxs-lookup"><span data-stu-id="afa67-132">Global Tools can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="afa67-133">Die Standardverzeichnisse sind:</span><span class="sxs-lookup"><span data-stu-id="afa67-133">The default directories are:</span></span>

| <span data-ttu-id="afa67-134">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="afa67-134">OS</span></span>          | <span data-ttu-id="afa67-135">Pfad</span><span class="sxs-lookup"><span data-stu-id="afa67-135">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="afa67-136">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="afa67-136">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="afa67-137">Windows</span><span class="sxs-lookup"><span data-stu-id="afa67-137">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="afa67-138">Diese Speicherorte werden dem Pfad des Benutzers hinzugefügt, wenn das SDK zum ersten Mal ausgeführt wird, damit dort installierte globale Tools direkt aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="afa67-138">These locations are added to the user's path when the SDK is first run, so Global Tools installed there can be called directly.</span></span>

<span data-ttu-id="afa67-139">Beachten Sie, dass die globalen Tools benutzerspezifisch gespeichert werden und nicht global auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="afa67-139">Note that the Global Tools are user-specific, not machine global.</span></span> <span data-ttu-id="afa67-140">Deshalb können Sie kein globales Tool installieren, das für alle Benutzer auf dem Computer verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="afa67-140">Being user-specific means you cannot install a Global Tool that is available to all users of the machine.</span></span> <span data-ttu-id="afa67-141">Das Tool ist nur für jedes Benutzerprofil verfügbar, auf denen das Tool installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="afa67-141">The tool is only available for each user profile where the tool was installed.</span></span>

<span data-ttu-id="afa67-142">Globale Tools können auch in einem spezifischen Verzeichnis installiert werden.</span><span class="sxs-lookup"><span data-stu-id="afa67-142">Global Tools can also be installed in a specific directory.</span></span> <span data-ttu-id="afa67-143">Wenn sie in einem spezifischen Verzeichnis installiert werden, muss der Benutzer sicherstellen, dass der Befehl verfügbar ist, indem das Verzeichnis in den Pfad eingefügt, der Befehl mit dem angegebenen Verzeichnis aufgerufen oder das Tool aus dem angegebenen Verzeichnis aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="afa67-143">When installed in a specific directory, the user must ensure the command is available, by including that directory in the path, by calling the command with the directory specified, or calling the tool from within the specified directory.</span></span>
<span data-ttu-id="afa67-144">In diesem Fall fügt die .NET Core-CLI diesen Speicherort nicht automatisch der Umgebungsvariable „PATH“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="afa67-144">In this case, the .NET Core CLI doesn't add this location automatically to the PATH environment variable.</span></span>

## <a name="use-the-tool"></a><span data-ttu-id="afa67-145">Verwenden des Tools</span><span class="sxs-lookup"><span data-stu-id="afa67-145">Use the tool</span></span>

<span data-ttu-id="afa67-146">Nachdem das Tool installiert wurde, können Sie es mit dem entsprechenden Befehl aufrufen.</span><span class="sxs-lookup"><span data-stu-id="afa67-146">Once the tool is installed, you can call it by using its command.</span></span> <span data-ttu-id="afa67-147">Beachten Sie, dass der Befehl möglicherweise nicht mit dem Paketnamen übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="afa67-147">Note that the command may not be the same as the package name.</span></span>

<span data-ttu-id="afa67-148">Wenn der Befehl `dotnetsay` ist, rufen Sie ihn wie folgt auf:</span><span class="sxs-lookup"><span data-stu-id="afa67-148">If the command is `dotnetsay`, you call it with:</span></span>

```console
dotnetsay
```

<span data-ttu-id="afa67-149">Wenn der Autor des Tools das Tool im Kontext der `dotnet`-Eingabeaufforderung anzeigen wollte, ist es möglicherweise so geschrieben, dass Sie es als `dotnet <command>` aufrufen, zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="afa67-149">If the tool author wanted the tool to appear in the context of the `dotnet` prompt, they may have written it in a way that you call it as `dotnet <command>`, such as:</span></span>

```dotnetcli
dotnet doc
```

<span data-ttu-id="afa67-150">Sie können herausfinden, welche Tools in einem installierten Paket globaler Tools enthalten sind, indem Sie den Befehl [dotnet tool list](dotnet-tool-list.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="afa67-150">You can find which tools are included in an installed Global Tool package by listing the installed packages using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

<span data-ttu-id="afa67-151">Darüber hinaus können Sie sich die Anweisungen auf der Website zum Tool ansehen oder einen der folgenden Befehle eingeben:</span><span class="sxs-lookup"><span data-stu-id="afa67-151">You can also look for usage instructions at the tool's website or by typing one of the following commands:</span></span>

```console
<command> --help
dotnet <command> --help
```

## <a name="other-cli-commands"></a><span data-ttu-id="afa67-152">Andere CLI-Befehle</span><span class="sxs-lookup"><span data-stu-id="afa67-152">Other CLI commands</span></span>

<span data-ttu-id="afa67-153">Das .NET Core SDK enthält andere Befehle, die globale .NET Core-Tools unterstützen.</span><span class="sxs-lookup"><span data-stu-id="afa67-153">The .NET Core SDK contains other commands that support .NET Core Global Tools.</span></span> <span data-ttu-id="afa67-154">Verwenden Sie einen beliebigen `dotnet tool`-Befehl mit einer der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="afa67-154">Use any of the `dotnet tool` commands with one of the following options:</span></span>

* <span data-ttu-id="afa67-155">`--global` oder `-g` gibt an, dass der Befehl für benutzerweite globale Tools anwendbar ist.</span><span class="sxs-lookup"><span data-stu-id="afa67-155">`--global` or `-g` specifies that the command is applicable to user-wide Global Tools.</span></span>
* <span data-ttu-id="afa67-156">`--tool-path` legt einen benutzerdefinierten Speicherort für globale Tools fest.</span><span class="sxs-lookup"><span data-stu-id="afa67-156">`--tool-path` specifies a custom location for Global Tools.</span></span>

<span data-ttu-id="afa67-157">So finden Sie heraus, welche Befehle für globale Tools verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="afa67-157">To find out which commands are available for Global Tools:</span></span>

```dotnetcli
dotnet tool --help
```

<span data-ttu-id="afa67-158">Das Aktualisieren eines globalen Tools umfasst das Deinstallieren und Neuinstallieren mit der neuesten stabilen Version.</span><span class="sxs-lookup"><span data-stu-id="afa67-158">Updating a Global Tool involves uninstalling and reinstalling it with the latest stable version.</span></span> <span data-ttu-id="afa67-159">Verwenden Sie den Befehl [dotnet tool update](dotnet-tool-update.md), um ein globales Tool zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="afa67-159">To update a Global Tool, use the [dotnet tool update](dotnet-tool-update.md) command:</span></span>

```dotnetcli
dotnet tool update -g <packagename>
```

<span data-ttu-id="afa67-160">Entfernen Sie ein globales Tool mit [dotnet tool uninstall](dotnet-tool-uninstall.md):</span><span class="sxs-lookup"><span data-stu-id="afa67-160">Remove a Global Tool using the [dotnet tool uninstall](dotnet-tool-uninstall.md):</span></span>

```dotnetcli
dotnet tool uninstall -g <packagename>
```

<span data-ttu-id="afa67-161">Verwenden Sie den Befehl [dotnet tool list](dotnet-tool-list.md), um alle derzeit auf dem Computer installierten globalen Tools mit ihren Versionen und Befehlen anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="afa67-161">To display all of the Global Tools currently installed on the machine, along with their version and commands, use the [dotnet tool list](dotnet-tool-list.md) command:</span></span>

```dotnetcli
dotnet tool list -g
```

## <a name="see-also"></a><span data-ttu-id="afa67-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="afa67-162">See also</span></span>

* [<span data-ttu-id="afa67-163">Behandlung von Problemen bei der Nutzung von .NET Core-Tools</span><span class="sxs-lookup"><span data-stu-id="afa67-163">Troubleshoot .NET Core tool usage issues</span></span>](troubleshoot-usage-issues.md)
