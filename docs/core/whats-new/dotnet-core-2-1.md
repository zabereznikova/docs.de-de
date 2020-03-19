---
title: Neuigkeiten in .NET Core 2.1
description: Informationen zu den neuen Features in .NET Core 2.1.
dev_langs:
- csharp
- vb
ms.date: 10/10/2018
ms.openlocfilehash: 54ace52fc6a8f4614c1f762b65453979bcb92c7a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79397872"
---
# <a name="whats-new-in-net-core-21"></a><span data-ttu-id="1a65d-103">Neuigkeiten in .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1a65d-103">What's new in .NET Core 2.1</span></span>

<span data-ttu-id="1a65d-104">.NET Core 2.1 enthält Verbesserungen und neue Features in folgenden Bereichen:</span><span class="sxs-lookup"><span data-stu-id="1a65d-104">.NET Core 2.1 includes enhancements and new features in the following areas:</span></span>

- [<span data-ttu-id="1a65d-105">Tools</span><span class="sxs-lookup"><span data-stu-id="1a65d-105">Tooling</span></span>](#tooling)
- [<span data-ttu-id="1a65d-106">Rollforward</span><span class="sxs-lookup"><span data-stu-id="1a65d-106">Roll forward</span></span>](#roll-forward)
- [<span data-ttu-id="1a65d-107">Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="1a65d-107">Deployment</span></span>](#deployment)
- [<span data-ttu-id="1a65d-108">Windows Compatibility Pack</span><span class="sxs-lookup"><span data-stu-id="1a65d-108">Windows Compatibility Pack</span></span>](#windows-compatibility-pack)
- [<span data-ttu-id="1a65d-109">JIT-Kompilierungsverbesserungen</span><span class="sxs-lookup"><span data-stu-id="1a65d-109">JIT compilation improvements</span></span>](#jit-compiler-improvements)
- [<span data-ttu-id="1a65d-110">API-Änderungen</span><span class="sxs-lookup"><span data-stu-id="1a65d-110">API changes</span></span>](#api-changes)

## <a name="tooling"></a><span data-ttu-id="1a65d-111">Tools</span><span class="sxs-lookup"><span data-stu-id="1a65d-111">Tooling</span></span>

<span data-ttu-id="1a65d-112">Das .NET Core 2.1 SDK (Version 2.1.300), die in .NET Core 2.1 enthaltenen Tools, enthält die folgenden Änderungen und Verbesserungen:</span><span class="sxs-lookup"><span data-stu-id="1a65d-112">The .NET Core 2.1 SDK (v 2.1.300), the tooling included with .NET Core 2.1, includes the following changes and enhancements:</span></span>

### <a name="build-performance-improvements"></a><span data-ttu-id="1a65d-113">Buildleistungsverbesserungen</span><span class="sxs-lookup"><span data-stu-id="1a65d-113">Build performance improvements</span></span>

<span data-ttu-id="1a65d-114">Ein wichtiger Schwerpunkt von .NET Core 2.1 ist die Verbesserung der Buildzeitleistung, insbesondere bei inkrementellen Builds.</span><span class="sxs-lookup"><span data-stu-id="1a65d-114">A major focus of .NET Core 2.1 is improving build-time performance, particularly for incremental builds.</span></span> <span data-ttu-id="1a65d-115">Diese Leistungsverbesserungen gelten sowohl für beide Befehlszeilenbuilds mit `dotnet build` als auch Builds in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1a65d-115">These performance improvements apply to both command-line builds using `dotnet build` and to builds in Visual Studio.</span></span> <span data-ttu-id="1a65d-116">Einige individuelle Verbesserungsbereiche sind:</span><span class="sxs-lookup"><span data-stu-id="1a65d-116">Some individual areas of improvement include:</span></span>

- <span data-ttu-id="1a65d-117">Bei der Auflösung von Paketressourcen werden statt aller Ressourcen nur die von einem Build verwendeten Ressourcen aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="1a65d-117">For package asset resolution, resolving only assets used by a build rather than all assets.</span></span>

- <span data-ttu-id="1a65d-118">Zwischenspeichern von Assemblyverweisen.</span><span class="sxs-lookup"><span data-stu-id="1a65d-118">Caching of assembly references.</span></span>

- <span data-ttu-id="1a65d-119">Verwendung von SDK-Buildservern mit langer Ausführungszeit, wobei es sich um Prozesse handelt, die sich über einzelne `dotnet build`-Aufrufe erstrecken.</span><span class="sxs-lookup"><span data-stu-id="1a65d-119">Use of long-running SDK build servers, which are processes that span across individual `dotnet build` invocations.</span></span> <span data-ttu-id="1a65d-120">Sie machen die Notwendigkeit der JIT-Kompilierung großer Codeblöcke bei jeder Ausführung von `dotnet build` überflüssig.</span><span class="sxs-lookup"><span data-stu-id="1a65d-120">They eliminate the need to JIT-compile large blocks of code every time `dotnet build` is run.</span></span> <span data-ttu-id="1a65d-121">Buildserverprozesse können automatisch mithilfe des folgenden Befehls beendet werden:</span><span class="sxs-lookup"><span data-stu-id="1a65d-121">Build server processes can be automatically terminated with the following command:</span></span>

   ```dotnetcli
   dotnet buildserver shutdown
   ```

### <a name="new-cli-commands"></a><span data-ttu-id="1a65d-122">Neue CLI-Befehle</span><span class="sxs-lookup"><span data-stu-id="1a65d-122">New CLI commands</span></span>

<span data-ttu-id="1a65d-123">Eine Reihe von Tools, die nur auf Projektbasis unter Verwendung von `DotnetCliToolReference` verfügbar waren, steht jetzt als Teil des .NET Core SDK zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1a65d-123">A number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="1a65d-124">Zu diesen Tools gehören:</span><span class="sxs-lookup"><span data-stu-id="1a65d-124">These tools include:</span></span>

- <span data-ttu-id="1a65d-125">`dotnet watch` bietet eine Dateisystemüberwachung, die vor der Ausführung eines designierten Satzes von Befehlen auf die Änderung einer Datei wartet.</span><span class="sxs-lookup"><span data-stu-id="1a65d-125">`dotnet watch` provides a file system watcher that waits for a file to change before executing a designated set of commands.</span></span> <span data-ttu-id="1a65d-126">Der folgende Befehl erstellt beispielsweise automatisch das aktuelle Projekt neu und generiert eine ausführliche Ausgabe, sobald sich eine Datei darin ändert:</span><span class="sxs-lookup"><span data-stu-id="1a65d-126">For example, the following command automatically rebuilds the current project and generates verbose output whenever a file in it changes:</span></span>

   ```dotnetcli
   dotnet watch -- --verbose build
   ```

   <span data-ttu-id="1a65d-127">Beachten Sie, dass die `--`-Option der `--verbose`-Option vorausgeht.</span><span class="sxs-lookup"><span data-stu-id="1a65d-127">Note the `--` option that precedes the `--verbose` option.</span></span> <span data-ttu-id="1a65d-128">Sie begrenzt die Optionen, die dem `dotnet watch`-Befehl direkt von den Argumenten übergeben werden, die dem untergeordneten `dotnet`-Prozess übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="1a65d-128">It delimits the options passed directly to the `dotnet watch` command from the arguments that are passed to the child `dotnet` process.</span></span> <span data-ttu-id="1a65d-129">Ohne sie gilt die `--verbose`-Option für den `dotnet watch`-Befehl, nicht den `dotnet build`-Befehl.</span><span class="sxs-lookup"><span data-stu-id="1a65d-129">Without it, the `--verbose` option applies to the `dotnet watch` command, not the `dotnet build` command.</span></span>
  
   <span data-ttu-id="1a65d-130">Weitere Informationen finden Sie unter [Entwickeln von ASP.NET Core-Apps mit dotnet watch](/aspnet/core/tutorials/dotnet-watch).</span><span class="sxs-lookup"><span data-stu-id="1a65d-130">For more information, see [Develop ASP.NET Core apps using dotnet watch](/aspnet/core/tutorials/dotnet-watch).</span></span>

- <span data-ttu-id="1a65d-131">`dotnet dev-certs` generiert und verwaltet Zertifikate, die während der Entwicklung in ASP.NET Core-Anwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1a65d-131">`dotnet dev-certs` generates and manages certificates used during development in ASP.NET Core applications.</span></span>

- <span data-ttu-id="1a65d-132">`dotnet user-secrets` verwaltet die Geheimnisse in einem Benutzergeheimnisspeicher in ASP.NET Core-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="1a65d-132">`dotnet user-secrets` manages the secrets in a user secret store in ASP.NET Core applications.</span></span>

- <span data-ttu-id="1a65d-133">`dotnet sql-cache` erstellt eine Tabelle und Indizes für Distributed Caching in einer Microsoft SQL Server-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="1a65d-133">`dotnet sql-cache` creates a table and indexes in a Microsoft SQL Server database to be used for distributed caching.</span></span>

- <span data-ttu-id="1a65d-134">`dotnet ef` ist ein Tool zum Verwalten von Datenbanken, <xref:Microsoft.EntityFrameworkCore.DbContext>-Objekten und Migrationen in Entity Framework Core-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="1a65d-134">`dotnet ef` is a tool for managing databases, <xref:Microsoft.EntityFrameworkCore.DbContext> objects, and migrations in Entity Framework Core applications.</span></span> <span data-ttu-id="1a65d-135">Weitere Informationen finden Sie unter [EF Core .NET-Befehlszeilentools](/ef/core/miscellaneous/cli/dotnet).</span><span class="sxs-lookup"><span data-stu-id="1a65d-135">For more information, see [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet).</span></span>

### <a name="global-tools"></a><span data-ttu-id="1a65d-136">Globale Tools</span><span class="sxs-lookup"><span data-stu-id="1a65d-136">Global Tools</span></span>

<span data-ttu-id="1a65d-137">.NET Core 2.1 unterstützt *globale Tools* – d.h. benutzerdefinierte Tools, die global über die Befehlszeile verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1a65d-137">.NET Core 2.1 supports *Global Tools* -- that is, custom tools that are available globally from the command line.</span></span> <span data-ttu-id="1a65d-138">Das Erweiterbarkeitsmodell in früheren Versionen von benutzerdefinierten .NET Core-Tools ist auf Projektbasis nur mithilfe von `DotnetCliToolReference` verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1a65d-138">The extensibility model in previous versions of .NET Core made custom tools available on a per project basis only by using `DotnetCliToolReference`.</span></span>

<span data-ttu-id="1a65d-139">Verwenden Sie den [dotnet tool install](../tools/dotnet-tool-install.md)-Befehl, um ein globales Tool zu installieren.</span><span class="sxs-lookup"><span data-stu-id="1a65d-139">To install a Global Tool, you use the [dotnet tool install](../tools/dotnet-tool-install.md) command.</span></span> <span data-ttu-id="1a65d-140">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1a65d-140">For example:</span></span>

```dotnetcli
dotnet tool install -g dotnetsay
```

<span data-ttu-id="1a65d-141">Nach Abschluss der Installation kann das Tool durch Angeben seines Namens in der Befehlszeile ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1a65d-141">Once installed, the tool can be run from the command line by specifying the tool name.</span></span> <span data-ttu-id="1a65d-142">Weitere Informationen finden Sie unter [Übersicht über globale .NET Core-Tools](../tools/global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1a65d-142">For more information, see [.NET Core Global Tools overview](../tools/global-tools.md).</span></span>

### <a name="tool-management-with-the-dotnet-tool-command"></a><span data-ttu-id="1a65d-143">Toolverwaltung mit dem `dotnet tool`-Befehl</span><span class="sxs-lookup"><span data-stu-id="1a65d-143">Tool management with the `dotnet tool` command</span></span>

<span data-ttu-id="1a65d-144">In .NET Core SDK 2.1 verwenden alle Toolsvorgänge den `dotnet tool`-Befehl.</span><span class="sxs-lookup"><span data-stu-id="1a65d-144">In .NET Core 2.1 SDK, all tools operations use the `dotnet tool` command.</span></span> <span data-ttu-id="1a65d-145">Die folgenden Optionen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="1a65d-145">The following options are available:</span></span>

- <span data-ttu-id="1a65d-146">[`dotnet tool install`](../tools/dotnet-tool-install.md) zum Installieren eines Tools.</span><span class="sxs-lookup"><span data-stu-id="1a65d-146">[`dotnet tool install`](../tools/dotnet-tool-install.md) to install a tool.</span></span>

- <span data-ttu-id="1a65d-147">[`dotnet tool update`](../tools/dotnet-tool-update.md) zum Deinstallieren und Neuinstallieren eines Tools, wodurch es eigentlich aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="1a65d-147">[`dotnet tool update`](../tools/dotnet-tool-update.md) to uninstall and reinstall a tool, which effectively updates it.</span></span>

- <span data-ttu-id="1a65d-148">[`dotnet tool list`](../tools/dotnet-tool-list.md) zum Auflisten derzeit installierter Tools.</span><span class="sxs-lookup"><span data-stu-id="1a65d-148">[`dotnet tool list`](../tools/dotnet-tool-list.md) to list currently installed tools.</span></span>

- <span data-ttu-id="1a65d-149">[`dotnet tool uninstall`](../tools/dotnet-tool-uninstall.md) zum Deinstallieren derzeit installierter Tools.</span><span class="sxs-lookup"><span data-stu-id="1a65d-149">[`dotnet tool uninstall`](../tools/dotnet-tool-uninstall.md) to uninstall currently installed tools.</span></span>

## <a name="roll-forward"></a><span data-ttu-id="1a65d-150">Rollforward</span><span class="sxs-lookup"><span data-stu-id="1a65d-150">Roll forward</span></span>

<span data-ttu-id="1a65d-151">Ab .NET Core 2.0 wird für alle .NET Core-Anwendungen automatisch ein Rollforward auf die neueste *Nebenversion* auf einem System installiert.</span><span class="sxs-lookup"><span data-stu-id="1a65d-151">All .NET Core applications starting with .NET Core 2.0 automatically roll forward to the latest *minor version* installed on a system.</span></span>

<span data-ttu-id="1a65d-152">Wenn die Version von .NET Core, mit der eine Anwendung erstellt wurde, nicht zur Runtime vorhanden ist, wird die Anwendung ab .NET Core 2.0 automatisch für die neueste installierte *Nebenversion* von .NET Core ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1a65d-152">Starting with .NET Core 2.0, if the version of .NET Core that an application was built with is not present at runtime, the application automatically runs against the latest installed *minor version* of .NET Core.</span></span> <span data-ttu-id="1a65d-153">Das heißt, wenn eine Anwendung mit .NET Core 2.0 erstellt wurde, und .NET Core 2.0 auf dem Hostsystem nicht vorhanden ist, jedoch .NET Core 2.1, wird die Anwendung mit .NET Core 2.1 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1a65d-153">In other words, if an application is built with .NET Core 2.0, and .NET Core 2.0 is not present on the host system but .NET Core 2.1 is, the application runs with .NET Core 2.1.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a65d-154">Dieses Rollforwardverhalten gilt nicht für Vorschauversionen.</span><span class="sxs-lookup"><span data-stu-id="1a65d-154">This roll-forward behavior doesn't apply to preview releases.</span></span> <span data-ttu-id="1a65d-155">Es wird standardmäßig auch nicht auf Hauptreleases angewendet. Dies können Sie mit den folgenden Einstellungen jedoch ändern.</span><span class="sxs-lookup"><span data-stu-id="1a65d-155">By default, it also doesn't apply to major releases, but this can be changed with the settings below.</span></span>

<span data-ttu-id="1a65d-156">Sie können dieses Verhalten anpassen, indem Sie die Einstellung für den Rollforward auf das freigegebene Framework ohne Candidate.</span><span class="sxs-lookup"><span data-stu-id="1a65d-156">You can modify this behavior by changing the setting for the roll-forward on no candidate shared framework.</span></span> <span data-ttu-id="1a65d-157">Folgende Einstellungen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="1a65d-157">The available settings are:</span></span>

- <span data-ttu-id="1a65d-158">`0`: Das Rollforwardverhalten für Nebenversionen deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="1a65d-158">`0` - disable minor version roll-forward behavior.</span></span> <span data-ttu-id="1a65d-159">Mit dieser Einstellung wird für Anwendungen für .NET Core 2.0.0 ein Rollforward auf .NET Core 2.0.1 ausgeführt, aber nicht für .NET Core 2.2.0 oder .NET Core 3.0.0.</span><span class="sxs-lookup"><span data-stu-id="1a65d-159">With this setting, an application built for .NET Core 2.0.0 will roll forward to .NET Core 2.0.1, but not to .NET Core 2.2.0 or .NET Core 3.0.0.</span></span>
- <span data-ttu-id="1a65d-160">`1`: Das Rollforwardverhalten für Nebenversionen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1a65d-160">`1` - enable minor version roll-forward behavior.</span></span> <span data-ttu-id="1a65d-161">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="1a65d-161">This is the default value for the setting.</span></span> <span data-ttu-id="1a65d-162">Mit dieser Einstellung wird für Anwendungen für .NET Core 2.0.0 ein Rollforward auf .NET Core 2.0.1 oder .NET Core 2.2.0 abhängig davon ausgeführt, was installiert wird. Es wird jedoch kein Rollforward auf .NET Core 3.0.0 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1a65d-162">With this setting, an application built for .NET Core 2.0.0 will roll forward to either .NET Core 2.0.1 or .NET Core 2.2.0, depending on which one is installed, but it will not roll forward to .NET Core 3.0.0.</span></span>
- <span data-ttu-id="1a65d-163">`2`: Das Rollforwardverhalten für Neben- und Hauptversionen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1a65d-163">`2` - enable minor and major version roll-forward behavior.</span></span> <span data-ttu-id="1a65d-164">Wenn diese Einstellung festgelegt wird, werden auch verschiedene Hauptversionen für das Rollforwardverhalten beachtet, d. h., für Anwendungen für .NET Core 2.0.0 wird ein Rollforward auf .NET Core 3.0.0 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1a65d-164">If set, even different major versions are considered, so an application built for .NET Core 2.0.0 will roll forward to .NET Core 3.0.0.</span></span>

<span data-ttu-id="1a65d-165">Sie können diese Einstellung auf drei verschiedene Arten ändern:</span><span class="sxs-lookup"><span data-stu-id="1a65d-165">You can modify this setting in any of three ways:</span></span>

- <span data-ttu-id="1a65d-166">Legen Sie den gewünschten Wert für die Umgebungsvariable `DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` fest.</span><span class="sxs-lookup"><span data-stu-id="1a65d-166">Set the `DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` environment variable to the desired value.</span></span>

- <span data-ttu-id="1a65d-167">Fügen Sie die folgende Zeile mit dem gewünschten Wert in die Datei *.runtimeconfig.json* ein:</span><span class="sxs-lookup"><span data-stu-id="1a65d-167">Add the following line with the desired value to the *.runtimeconfig.json* file:</span></span>

   ```json
   "rollForwardOnNoCandidateFx" : 0
   ```

- <span data-ttu-id="1a65d-168">Fügen Sie bei Verwendung der [.NET Core-CLI](../tools/index.md) die folgende Option mit dem gewünschten Wert zu einem .NET Core-Befehl wie `run` hinzu:</span><span class="sxs-lookup"><span data-stu-id="1a65d-168">When using the [.NET Core CLI](../tools/index.md), add the following option with the desired value to a .NET Core command such as `run`:</span></span>

   ```dotnetcli
   dotnet run --rollForwardOnNoCandidateFx=0
   ```

<span data-ttu-id="1a65d-169">Rollforwards für die Patchversionen sind unabhängig von dieser Einstellung und erfolgen erst, nachdem Rollforwards für Neben- und Hauptversionen ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="1a65d-169">Patch version roll forward is independent of this setting and is done after any potential minor or major version roll forward is applied.</span></span>

## <a name="deployment"></a><span data-ttu-id="1a65d-170">Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="1a65d-170">Deployment</span></span>

### <a name="self-contained-application-servicing"></a><span data-ttu-id="1a65d-171">Wartung einer eigenständigen Anwendung</span><span class="sxs-lookup"><span data-stu-id="1a65d-171">Self-contained application servicing</span></span>

<span data-ttu-id="1a65d-172">`dotnet publish` veröffentlicht jetzt eigenständige Anwendungen mit einer gewarteten Runtimeversion.</span><span class="sxs-lookup"><span data-stu-id="1a65d-172">`dotnet publish` now publishes self-contained applications with a serviced runtime version.</span></span> <span data-ttu-id="1a65d-173">Wenn Sie eine eigenständige Anwendung mit dem .NET Core 2.1 SDK (Version 2.1.300) veröffentlichen, enthält Ihre Anwendung die neueste gewartete Runtimeversion, die diesem SDK bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="1a65d-173">When you publish a self-contained application with the .NET Core 2.1 SDK (v 2.1.300), your application includes the latest serviced runtime version known by that SDK.</span></span> <span data-ttu-id="1a65d-174">Wenn Sie auf das neueste SDK aktualisieren, veröffentlichen Sie mit der neuesten .NET Core-Runtimeversion.</span><span class="sxs-lookup"><span data-stu-id="1a65d-174">When you upgrade to the latest SDK, you'll publish with the latest .NET Core runtime version.</span></span> <span data-ttu-id="1a65d-175">Dies gilt für Runtimes ab .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="1a65d-175">This applies for .NET Core 1.0 runtimes and later.</span></span>

<span data-ttu-id="1a65d-176">Eigenständige Veröffentlichung basiert auf Runtimeversionen auf „NuGet.org“. Die gewartete Runtime muss nicht auf Ihrem Computer vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="1a65d-176">Self-contained publishing relies on runtime versions on NuGet.org. You do not need to have the serviced runtime on your machine.</span></span>

<span data-ttu-id="1a65d-177">Bei Verwendung von .NET Core 2.0 SDK werden eigenständige Anwendungen mit der .NET Core 2.0.0-Runtime veröffentlicht, solange keine andere Version über die `RuntimeFrameworkVersion`-Eigenschaft angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1a65d-177">Using the .NET Core 2.0 SDK, self-contained applications are published with the .NET Core 2.0.0 runtime unless a different version is specified via the `RuntimeFrameworkVersion` property.</span></span> <span data-ttu-id="1a65d-178">Mit diesem neuen Verhalten müssen Sie diese Eigenschaft nicht mehr festlegen, um eine höhere Runtimeversion für eine eigenständige Anwendung auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="1a65d-178">With this new behavior, you'll no longer need to set this property to select a higher runtime version for a self-contained application.</span></span> <span data-ttu-id="1a65d-179">Der einfachste Ansatz, auf eine höhere Version zu aktualisieren, besteht darin, immer mit .NET Core 2.1 SDK (Version 2.1.300) zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="1a65d-179">The easiest approach going forward is to always publish with .NET Core 2.1 SDK (v 2.1.300).</span></span>

<span data-ttu-id="1a65d-180">Weitere Informationen finden Sie unter [Rollforward der eigenständigen Runtimebereitstellung](../deploying/runtime-patch-selection.md).</span><span class="sxs-lookup"><span data-stu-id="1a65d-180">For more information, see [Self-contained deployment runtime roll forward](../deploying/runtime-patch-selection.md).</span></span>
## <a name="windows-compatibility-pack"></a><span data-ttu-id="1a65d-181">Windows Compatibility Pack</span><span class="sxs-lookup"><span data-stu-id="1a65d-181">Windows Compatibility Pack</span></span>

<span data-ttu-id="1a65d-182">Wenn Sie vorhandenen Code aus .NET Framework zu .NET Core portieren, können Sie das [Windows Compatibility Pack](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) verwenden.</span><span class="sxs-lookup"><span data-stu-id="1a65d-182">When you port existing code from the .NET Framework to .NET Core, you can use the [Windows Compatibility Pack](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span></span> <span data-ttu-id="1a65d-183">Es bietet Zugriff auf 20.000 APIs mehr, als in .NET Core verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1a65d-183">It provides access to 20,000 more APIs than are available in .NET Core.</span></span> <span data-ttu-id="1a65d-184">Zu diesen APIs zählen Typen in <xref:System.Drawing?displayProperty=nameWithType>-Namespace, <xref:System.Diagnostics.EventLog>-Klasse, WMI, Leistungsindikatoren, Windows-Diensten sowie die Windows-Registrierungstypen und Member.</span><span class="sxs-lookup"><span data-stu-id="1a65d-184">These APIs include types in the <xref:System.Drawing?displayProperty=nameWithType> namespace, the <xref:System.Diagnostics.EventLog> class, WMI, Performance Counters, Windows Services, and the Windows registry types and members.</span></span>

## <a name="jit-compiler-improvements"></a><span data-ttu-id="1a65d-185">Verbesserungen am JIT-Compiler</span><span class="sxs-lookup"><span data-stu-id="1a65d-185">JIT compiler improvements</span></span>

<span data-ttu-id="1a65d-186">.NET Core umfasst eine neue JIT-Compiler-Technologie namens *mehrstufige Kompilierung* (auch bekannt als *adaptive Optimierung*), die die Leistung erheblich verbessern kann.</span><span class="sxs-lookup"><span data-stu-id="1a65d-186">.NET Core incorporates a new JIT compiler technology called *tiered compilation* (also known as *adaptive optimization*) that can significantly improve performance.</span></span> <span data-ttu-id="1a65d-187">Mehrstufige Kompilierung ist eine optionale Einstellung.</span><span class="sxs-lookup"><span data-stu-id="1a65d-187">Tiered compilation is an opt-in setting.</span></span>

<span data-ttu-id="1a65d-188">Eine der wichtigen Aufgaben, die vom JIT-Compiler ausgeführt werden, ist die Optimierung der Ausführung des Codes.</span><span class="sxs-lookup"><span data-stu-id="1a65d-188">One of the important tasks performed by the JIT compiler is optimizing code execution.</span></span> <span data-ttu-id="1a65d-189">Für wenig genutzte Codepfade muss der Compiler jedoch möglicherweise mehr Zeit zur Optimierung des Codes aufbringen, als die Runtime zur Ausführung nicht optimierten Codes benötigt.</span><span class="sxs-lookup"><span data-stu-id="1a65d-189">For little-used code paths, however, the compiler may spend more time optimizing code than the runtime spends running unoptimized code.</span></span> <span data-ttu-id="1a65d-190">Die mehrstufige Kompilierung unterteilt die JIT-Kompilierung in zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="1a65d-190">Tiered compilation introduces two stages in JIT compilation:</span></span>

- <span data-ttu-id="1a65d-191">Eine **erste Stufe**, die so schnell wie möglich Code generiert.</span><span class="sxs-lookup"><span data-stu-id="1a65d-191">A **first tier**, which generates code as quickly as possible.</span></span>

- <span data-ttu-id="1a65d-192">Eine **zweite Stufe**, die optimiertem Code für Methoden generiert, die häufig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1a65d-192">A **second tier**, which generates optimized code for those methods that are executed frequently.</span></span> <span data-ttu-id="1a65d-193">Die zweite Stufe der Kompilierung wird parallel zum Verbessern der Leistung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1a65d-193">The second tier of compilation is performed in parallel for enhanced performance.</span></span>

<span data-ttu-id="1a65d-194">Zum Aktivieren der mehrstufigen Kompilierung können Sie zwischen zwei Arten wählen.</span><span class="sxs-lookup"><span data-stu-id="1a65d-194">You can opt into tiered compilation in either of two ways.</span></span>

- <span data-ttu-id="1a65d-195">Um mehrstufige Kompilierung in allen Projekten einzusetzen, die das .NET Core 2.1 SDK verwenden, legen Sie die folgende Umgebungsvariable fest:</span><span class="sxs-lookup"><span data-stu-id="1a65d-195">To use tiered compilation in all projects that use the .NET Core 2.1 SDK, set the following environment variable:</span></span>

  ```console
  COMPlus_TieredCompilation="1"
  ```

- <span data-ttu-id="1a65d-196">Um mehrstufige Kompilierung in ausgewählten Projekten einzusetzen, fügen Sie die `<TieredCompilation>`-Eigenschaft dem `<PropertyGroup>`-Abschnitt der MSBuild-Projektdatei hinzu, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1a65d-196">To use tiered compilation on a per-project basis, add the `<TieredCompilation>` property to the `<PropertyGroup>` section of the MSBuild project file, as the following example shows:</span></span>

   ```xml
   <PropertyGroup>
      <!-- other property definitions -->

      <TieredCompilation>true</TieredCompilation>
   </PropertyGroup>
   ```

## <a name="api-changes"></a><span data-ttu-id="1a65d-197">API-Änderungen</span><span class="sxs-lookup"><span data-stu-id="1a65d-197">API changes</span></span>

### <a name="spant-and-memoryt"></a><span data-ttu-id="1a65d-198">`Span<T>` und `Memory<T>`</span><span class="sxs-lookup"><span data-stu-id="1a65d-198">`Span<T>` and `Memory<T>`</span></span>

<span data-ttu-id="1a65d-199">.NET Core 2.1 enthält einige neue Typen, die das Arbeiten mit Arrays und anderen Arten von Arbeitsspeicher wesentlich effizienter machen.</span><span class="sxs-lookup"><span data-stu-id="1a65d-199">.NET Core 2.1 includes some new types that make working with arrays and other types of memory much more efficient.</span></span> <span data-ttu-id="1a65d-200">Die neuen Typen umfassen:</span><span class="sxs-lookup"><span data-stu-id="1a65d-200">The new types include:</span></span>

- <span data-ttu-id="1a65d-201"><xref:System.Span%601?displayProperty=nameWithType> und <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1a65d-201"><xref:System.Span%601?displayProperty=nameWithType> and <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="1a65d-202"><xref:System.Memory%601?displayProperty=nameWithType> und <xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1a65d-202"><xref:System.Memory%601?displayProperty=nameWithType> and <xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="1a65d-203">Ohne diese Typen müssen Sie bei der Übergabe solcher Elemente als Teil eines Arrays oder Abschnitt eines Arbeitsspeicherpuffers eine Kopie eines Teils der Daten anfertigen, bevor Sie sie einer Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="1a65d-203">Without these types, when passing such items as a portion of an array or a section of a memory buffer, you have to make a copy of some portion of the data before passing it to a method.</span></span> <span data-ttu-id="1a65d-204">Diese Typen bieten eine virtuelle Sicht der Daten, die die zusätzliche Speicherzuweisung und Kopiervorgänge überflüssig macht.</span><span class="sxs-lookup"><span data-stu-id="1a65d-204">These types provide a virtual view of that data that eliminates the need for the additional memory allocation and copy operations.</span></span>

<span data-ttu-id="1a65d-205">Das folgende Beispiel verwendet eine <xref:System.Span%601>- und eine <xref:System.Memory%601>-Instanz, um eine virtuelle Ansicht von 10 Elementen eines Arrays bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1a65d-205">The following example uses a <xref:System.Span%601> and <xref:System.Memory%601> instance to provide a virtual view of 10 elements of an array.</span></span>

[!code-csharp[Span\<T>](~/samples/snippets/core/whats-new/whats-new-in-21/csharp/program.cs)]

[!code-vb[Memory\<T>](~/samples/snippets/core/whats-new/whats-new-in-21/vb/program.vb)]

### <a name="brotli-compression"></a><span data-ttu-id="1a65d-206">Brotli-Komprimierung</span><span class="sxs-lookup"><span data-stu-id="1a65d-206">Brotli compression</span></span>

<span data-ttu-id="1a65d-207">Ab .NET Core 2.1 werden Brotli-Komprimierung und -Dekomprimierung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1a65d-207">.NET Core 2.1 adds support for Brotli compression and decompression.</span></span> <span data-ttu-id="1a65d-208">Brotli ist ein allgemein einsetzbarer verlustfreier Komprimierungsalgorithmus, der in [RFC 7932](https://www.ietf.org/rfc/rfc7932.txt) definiert ist und von den meisten Webbrowsern und den wichtigsten Webservern unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="1a65d-208">Brotli is a general-purpose lossless compression algorithm that is defined in [RFC 7932](https://www.ietf.org/rfc/rfc7932.txt) and is supported by most web browsers and major web servers.</span></span> <span data-ttu-id="1a65d-209">Sie können die streambasierte <xref:System.IO.Compression.BrotliStream?displayProperty=nameWithType>-Klasse oder die leistungsstarken, bereichsbasierten Klassen <xref:System.IO.Compression.BrotliEncoder?displayProperty=nameWithType> und <xref:System.IO.Compression.BrotliDecoder?displayProperty=nameWithType> verwenden.</span><span class="sxs-lookup"><span data-stu-id="1a65d-209">You can use the stream-based <xref:System.IO.Compression.BrotliStream?displayProperty=nameWithType> class or the high-performance span-based <xref:System.IO.Compression.BrotliEncoder?displayProperty=nameWithType> and <xref:System.IO.Compression.BrotliDecoder?displayProperty=nameWithType> classes.</span></span> <span data-ttu-id="1a65d-210">Im folgenden Beispiel wird die Komprimierung mit der <xref:System.IO.Compression.BrotliStream>-Klasse veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="1a65d-210">The following example illustrates compression with the <xref:System.IO.Compression.BrotliStream> class:</span></span>

[!code-csharp[Brotli compression](~/samples/snippets/core/whats-new/whats-new-in-21/csharp/brotli.cs#1)]

[!code-vb[Brotli compression](~/samples/snippets/core/whats-new/whats-new-in-21/vb/brotli.vb#1)]

<span data-ttu-id="1a65d-211">Das <xref:System.IO.Compression.BrotliStream>-Verhalten entspricht dem von <xref:System.IO.Compression.DeflateStream> und <xref:System.IO.Compression.GZipStream>. Dies vereinfacht das Konvertieren von Code, der diese APIs nach <xref:System.IO.Compression.BrotliStream> aufruft.</span><span class="sxs-lookup"><span data-stu-id="1a65d-211">The <xref:System.IO.Compression.BrotliStream> behavior is the same as <xref:System.IO.Compression.DeflateStream> and <xref:System.IO.Compression.GZipStream>, which makes it easy to convert code that calls these APIs to <xref:System.IO.Compression.BrotliStream>.</span></span>

### <a name="new-cryptography-apis-and-cryptography-improvements"></a><span data-ttu-id="1a65d-212">Neue Kryptografie-APIs und Kryptografieverbesserungen</span><span class="sxs-lookup"><span data-stu-id="1a65d-212">New cryptography APIs and cryptography improvements</span></span>

<span data-ttu-id="1a65d-213">.NET Core 2.1 enthält zahlreiche Verbesserungen der Kryptografie-APIs:</span><span class="sxs-lookup"><span data-stu-id="1a65d-213">.NET Core 2.1 includes numerous enhancements to the cryptography APIs:</span></span>

- <span data-ttu-id="1a65d-214"><xref:System.Security.Cryptography.Pkcs.SignedCms?displayProperty=nameWithType> ist im Paket System.Security.Cryptography.Pkcs verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1a65d-214"><xref:System.Security.Cryptography.Pkcs.SignedCms?displayProperty=nameWithType> is available in the System.Security.Cryptography.Pkcs package.</span></span> <span data-ttu-id="1a65d-215">Die Implementierung ist identisch mit jener der <xref:System.Security.Cryptography.Pkcs.SignedCms>-Klasse in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1a65d-215">The implementation is the same as the <xref:System.Security.Cryptography.Pkcs.SignedCms> class in the .NET Framework.</span></span>

- <span data-ttu-id="1a65d-216">Neue Überladungen der <xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHash%2A?displayProperty=nameWithType>- und <xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHashString%2A?displayProperty=nameWithType>-Methode akzeptieren einen Hashalgorithmusbezeichner, um Aufrufern zu ermöglichen, Zertifikatfingerabdruck-Werte mit anderen Algorithmen als SHA-1 zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1a65d-216">New overloads of the <xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHash%2A?displayProperty=nameWithType> and <xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHashString%2A?displayProperty=nameWithType> methods accept a hash algorithm identifier to enable callers to get certificate thumbprint values using algorithms other than SHA-1.</span></span>

- <span data-ttu-id="1a65d-217">Neue Kryptografie-APIs auf <xref:System.Span%601>-Basis stehen für Hashvorgänge, HMAC, kryptografische Zufallszahlengenerierung, asymmetrische Signaturgenerierung, asymmetrische Signaturverarbeitung und RSA-Verschlüsselung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1a65d-217">New <xref:System.Span%601>-based cryptography APIs are available for hashing, HMAC, cryptographic random number generation, asymmetric signature generation, asymmetric signature processing, and RSA encryption.</span></span>

- <span data-ttu-id="1a65d-218">Die Leistung von <xref:System.Security.Cryptography.Rfc2898DeriveBytes?displayProperty=nameWithType> wurde mithilfe einer <xref:System.Span%601>-basierten Implementierung um ca. 15% verbessert.</span><span class="sxs-lookup"><span data-stu-id="1a65d-218">The performance of <xref:System.Security.Cryptography.Rfc2898DeriveBytes?displayProperty=nameWithType> has improved by about 15% by using a <xref:System.Span%601>-based implementation.</span></span>

- <span data-ttu-id="1a65d-219">Die neue <xref:System.Security.Cryptography.CryptographicOperations?displayProperty=nameWithType>-Klasse enthält zwei neue Methoden:</span><span class="sxs-lookup"><span data-stu-id="1a65d-219">The new <xref:System.Security.Cryptography.CryptographicOperations?displayProperty=nameWithType> class includes two new methods:</span></span>

  - <span data-ttu-id="1a65d-220"><xref:System.Security.Cryptography.CryptographicOperations.FixedTimeEquals%2A> benötigt eine feste Zeitspanne zur Rückgabe von zwei beliebigen Eingaben derselben Länge, sodass sie zur Verwendung bei kryptografischer Überprüfung geeignet ist, um zu vermeiden, das zu Zeitsteuerungs-Seitenkanalinformationen beigetragen wird.</span><span class="sxs-lookup"><span data-stu-id="1a65d-220"><xref:System.Security.Cryptography.CryptographicOperations.FixedTimeEquals%2A> takes a fixed amount of time to return for any two inputs of the same length, which makes it suitable for use in cryptographic verification to avoid contributing to timing side-channel information.</span></span>

  - <span data-ttu-id="1a65d-221"><xref:System.Security.Cryptography.CryptographicOperations.ZeroMemory%2A> ist eine Arbeitsspeicherlöschroutine, die nicht optimiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="1a65d-221"><xref:System.Security.Cryptography.CryptographicOperations.ZeroMemory%2A> is a memory-clearing routine that cannot be optimized.</span></span>

- <span data-ttu-id="1a65d-222">Die statische <xref:System.Security.Cryptography.RandomNumberGenerator.Fill%2A?displayProperty=nameWithType>-Methode füllt eine <xref:System.Span%601> mit Zufallswerten.</span><span class="sxs-lookup"><span data-stu-id="1a65d-222">The static <xref:System.Security.Cryptography.RandomNumberGenerator.Fill%2A?displayProperty=nameWithType> method fills a <xref:System.Span%601> with random values.</span></span>

- <span data-ttu-id="1a65d-223">Die <xref:System.Security.Cryptography.Pkcs.EnvelopedCms?displayProperty=nameWithType>-Methode wird jetzt unter Linux und macOS unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1a65d-223">The <xref:System.Security.Cryptography.Pkcs.EnvelopedCms?displayProperty=nameWithType> is now supported on Linux and macOS.</span></span>

- <span data-ttu-id="1a65d-224">Elliptic-Curve Diffie-Hellman (ECDH) steht jetzt in der <xref:System.Security.Cryptography.ECDiffieHellman?displayProperty=nameWithType>-Klassenfamilie zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1a65d-224">Elliptic-Curve Diffie-Hellman (ECDH) is now available in the <xref:System.Security.Cryptography.ECDiffieHellman?displayProperty=nameWithType> class family.</span></span> <span data-ttu-id="1a65d-225">Der Oberflächenbereich ist mit dem von .NET Framework identisch.</span><span class="sxs-lookup"><span data-stu-id="1a65d-225">The surface area is the same as in the .NET Framework.</span></span>

- <span data-ttu-id="1a65d-226">Die von <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType> zurückgegebene Instanz kann mit OAEP mit einem SHA-2-Hashwert verschlüsseln oder entschlüsseln als auch Signaturen mit RSA-PSS generieren oder überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1a65d-226">The instance returned by <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType> can encrypt or decrypt with OAEP using a SHA-2 digest, as well as generate or validate signatures using RSA-PSS.</span></span>

### <a name="sockets-improvements"></a><span data-ttu-id="1a65d-227">Socketverbesserungen</span><span class="sxs-lookup"><span data-stu-id="1a65d-227">Sockets improvements</span></span>

<span data-ttu-id="1a65d-228">.NET Core umfasst einen neuen Typ, <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>, und einen umgeschriebenen, <xref:System.Net.Http.HttpMessageHandler?displayProperty=nameWithType>, die gemeinsam die Basis der Netzwerk-APIs auf höherer Ebene bilden.</span><span class="sxs-lookup"><span data-stu-id="1a65d-228">.NET Core includes a new type, <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>, and a rewritten <xref:System.Net.Http.HttpMessageHandler?displayProperty=nameWithType>, that form the basis of higher-level networking APIs.</span></span>  <span data-ttu-id="1a65d-229"><xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> ist z.B. die Grundlage der <xref:System.Net.Http.HttpClient>-Implementierung.</span><span class="sxs-lookup"><span data-stu-id="1a65d-229"><xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>, for example, is the basis of the <xref:System.Net.Http.HttpClient> implementation.</span></span> <span data-ttu-id="1a65d-230">In früheren Versionen von .NET Core basierten APIs auf höherer Ebene auf nativen Netzwerkimplementierungen.</span><span class="sxs-lookup"><span data-stu-id="1a65d-230">In previous versions of .NET Core, higher-level APIs were based on native networking implementations.</span></span>

<span data-ttu-id="1a65d-231">Die in .NET Core 2.1 eingeführte Socketimplementierung hat eine Reihe von Vorteilen:</span><span class="sxs-lookup"><span data-stu-id="1a65d-231">The sockets implementation introduced in .NET Core 2.1 has a number of advantages:</span></span>

- <span data-ttu-id="1a65d-232">Eine beträchtliche Leistungssteigerung im Vergleich zur früheren Implementierung.</span><span class="sxs-lookup"><span data-stu-id="1a65d-232">A significant performance improvement when compared with the previous implementation.</span></span>

- <span data-ttu-id="1a65d-233">Plattformabhängigkeiten wurden eliminiert, was Bereitstellung und Wartung vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="1a65d-233">Elimination of platform dependencies, which simplifies deployment and servicing.</span></span>

- <span data-ttu-id="1a65d-234">Einheitliches Verhalten auf allen .NET Core-Plattformen.</span><span class="sxs-lookup"><span data-stu-id="1a65d-234">Consistent behavior across all .NET Core platforms.</span></span>

<span data-ttu-id="1a65d-235"><xref:System.Net.Http.SocketsHttpHandler> ist die Standardimplementierung in .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="1a65d-235"><xref:System.Net.Http.SocketsHttpHandler> is the default implementation in .NET Core 2.1.</span></span> <span data-ttu-id="1a65d-236">Allerdings können Sie Ihre Anwendung mit der älteren <xref:System.Net.Http.HttpClientHandler>-Klasse durch Aufrufen der <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>-Methode konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="1a65d-236">However, you can configure your application to use the older <xref:System.Net.Http.HttpClientHandler> class by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method:</span></span>

```csharp
AppContext.SetSwitch("System.Net.Http.UseSocketsHttpHandler", false);
```

```vb
AppContext.SetSwitch("System.Net.Http.UseSocketsHttpHandler", False)
```

<span data-ttu-id="1a65d-237">Statt auf <xref:System.Net.Http.SocketsHttpHandler> basierender Socketimplementierungen können Sie auch eine Umgebungsvariable verwenden.</span><span class="sxs-lookup"><span data-stu-id="1a65d-237">You can also use an environment variable to opt out of using sockets implementations based on <xref:System.Net.Http.SocketsHttpHandler>.</span></span> <span data-ttu-id="1a65d-238">Legen Sie dazu für `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` entweder `false` oder 0 (null) fest.</span><span class="sxs-lookup"><span data-stu-id="1a65d-238">To do this, set the `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` to either `false` or 0.</span></span>

<span data-ttu-id="1a65d-239">Unter Windows können Sie auch <xref:System.Net.Http.WinHttpHandler?displayProperty=nameWithType> verwenden, was von einer nativen Implementierung abhängt, oder die <xref:System.Net.Http.SocketsHttpHandler>-Klasse durch Übergabe einer Instanz der Klasse an den <xref:System.Net.Http.HttpClient>-Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="1a65d-239">On Windows, you can also choose to use <xref:System.Net.Http.WinHttpHandler?displayProperty=nameWithType>, which relies on a native implementation, or the <xref:System.Net.Http.SocketsHttpHandler> class by passing an instance of the class to the <xref:System.Net.Http.HttpClient> constructor.</span></span>

<span data-ttu-id="1a65d-240">Auf Linux und macOS können Sie <xref:System.Net.Http.HttpClient> nur pro Prozess konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1a65d-240">On Linux and macOS, you can only configure <xref:System.Net.Http.HttpClient> on a per-process basis.</span></span> <span data-ttu-id="1a65d-241">Unter Linux müssen Sie [libcurl](https://curl.haxx.se/libcurl/) bereitstellen, wenn Sie die alte <xref:System.Net.Http.HttpClient>-Implementierung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="1a65d-241">On Linux, you need to deploy [libcurl](https://curl.haxx.se/libcurl/) if you want to use the old <xref:System.Net.Http.HttpClient> implementation.</span></span> <span data-ttu-id="1a65d-242">(Wird mit .NET Core 2.0 installiert.)</span><span class="sxs-lookup"><span data-stu-id="1a65d-242">(It is installed with .NET Core 2.0.)</span></span>

### <a name="breaking-changes"></a><span data-ttu-id="1a65d-243">Breaking Changes</span><span class="sxs-lookup"><span data-stu-id="1a65d-243">Breaking changes</span></span>

<span data-ttu-id="1a65d-244">Informationen zu Breaking Changes finden Sie unter [Breaking Changes für die Migration von Version 2.0 zu 2.1](../compatibility/2.0-2.1.md).</span><span class="sxs-lookup"><span data-stu-id="1a65d-244">For information about breaking changes, see [Breaking changes for migration from version 2.0 to 2.1](../compatibility/2.0-2.1.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1a65d-245">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a65d-245">See also</span></span>

- [<span data-ttu-id="1a65d-246">Neuigkeiten in .NET Core</span><span class="sxs-lookup"><span data-stu-id="1a65d-246">What's new in .NET Core</span></span>](index.md)
- [<span data-ttu-id="1a65d-247">Neue Features in EF Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1a65d-247">New features in EF Core 2.1</span></span>](/ef/core/what-is-new/ef-core-2.1)
- [<span data-ttu-id="1a65d-248">Neuerungen in ASP.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1a65d-248">What's new in ASP.NET Core 2.1</span></span>](/aspnet/core/aspnetcore-2.1)
