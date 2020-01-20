---
title: Installieren des ML.NET-Befehlszeilenschnittstellen-Tools (CLI)
description: Erfahren Sie, wie Sie das ML.NET-CLI-Tool (Command-Line Interface, Befehlszeilenschnittstelle) installieren, aktualisieren, herabstufen und deinstallieren.
ms.date: 12/18/2019
ms.openlocfilehash: 350122f2d2d2f03484ab6e272b482adf2094495c
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75739968"
---
# <a name="how-to-install-the-mlnet-command-line-interface-cli-tool"></a><span data-ttu-id="6f37f-103">Installieren des ML.NET-Befehlszeilenschnittstellen-Tools (CLI)</span><span class="sxs-lookup"><span data-stu-id="6f37f-103">How to install the ML.NET Command-Line Interface (CLI) tool</span></span>

<span data-ttu-id="6f37f-104">Erfahren Sie, wie Sie die ML.NET-CLI (Befehlszeilenschnittstelle) unter Windows, Mac oder Linux installieren.</span><span class="sxs-lookup"><span data-stu-id="6f37f-104">Learn how to install the ML.NET CLI (command-line interface) on Windows, Mac, or Linux.</span></span>

<span data-ttu-id="6f37f-105">Die ML.NET-CLI generiert qualitativ hochwertige ML.NET-Modelle und Quellcode mithilfe von automatisiertem Machine Learning (AutoML) und einem Trainingsdataset.</span><span class="sxs-lookup"><span data-stu-id="6f37f-105">The ML.NET CLI generates good quality ML.NET models and source code using automated machine learning (AutoML) and a training dataset.</span></span>

> [!NOTE]
> <span data-ttu-id="6f37f-106">Dieses Thema bezieht sich auf die ML.NET-CLI und ML.NET AutoML, die derzeit als Vorschau verfügbar sind, und das Material kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6f37f-106">This topic refers to ML.NET CLI and ML.NET AutoML, which are currently in Preview, and material may be subject to change.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="6f37f-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6f37f-107">Pre-requisites</span></span>

- [<span data-ttu-id="6f37f-108">.NET Core 2.2 SDK</span><span class="sxs-lookup"><span data-stu-id="6f37f-108">.NET Core 2.2 SDK</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)

- <span data-ttu-id="6f37f-109">(Optional) [Visual Studio 2017 oder 2019](https://visualstudio.microsoft.com/vs/)</span><span class="sxs-lookup"><span data-stu-id="6f37f-109">(Optional) [Visual Studio 2017 or 2019](https://visualstudio.microsoft.com/vs/)</span></span>

<span data-ttu-id="6f37f-110">Sie können die generierten C#-Codeprojekte mit Visual Studio durch Drücken der Taste `F5` oder mit dem Befehl `dotnet run` ausführen (.NET Core-CLI).</span><span class="sxs-lookup"><span data-stu-id="6f37f-110">You can run the generated C# code projects with Visual Studio by pressing the `F5` key or with `dotnet run` (.NET Core CLI).</span></span>

<span data-ttu-id="6f37f-111">Hinweis: Wenn nach der Installation von [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.2) der Befehl `dotnet tool` nicht funktioniert, melden Sie sich von Windows ab und erneut wieder an.</span><span class="sxs-lookup"><span data-stu-id="6f37f-111">Note: If after installing [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.2) the `dotnet tool` command is not working, sign out from Windows and sign in again.</span></span>

## <a name="install"></a><span data-ttu-id="6f37f-112">Installieren</span><span class="sxs-lookup"><span data-stu-id="6f37f-112">Install</span></span>

<span data-ttu-id="6f37f-113">Die ML.NET-CLI wird wie jedes andere globale .NET-Tool installiert.</span><span class="sxs-lookup"><span data-stu-id="6f37f-113">The ML.NET CLI is installed like any other dotnet Global Tool.</span></span> <span data-ttu-id="6f37f-114">Sie verwenden den .NET Core-CLI-Befehl `dotnet tool install`.</span><span class="sxs-lookup"><span data-stu-id="6f37f-114">You use the `dotnet tool install` .NET Core CLI command.</span></span>

<span data-ttu-id="6f37f-115">Im folgenden Beispiel wird gezeigt, wie eine ML.NET-CLI im standardmäßigen NuGet-Feedspeicherort installiert wird:</span><span class="sxs-lookup"><span data-stu-id="6f37f-115">The following example shows how to install the ML.NET CLI in the default NuGet feed location:</span></span>

```dotnetcli
dotnet tool install -g mlnet
```

<span data-ttu-id="6f37f-116">Wenn das Tool nicht installiert werden kann (d.h. wenn es im standardmäßigen NuGet-Feed nicht verfügbar ist), werden Fehlermeldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6f37f-116">If the tool can't be installed (that is, if it is not available at the default NuGet feed), error messages are displayed.</span></span> <span data-ttu-id="6f37f-117">Stellen Sie sicher, dass die erwarteten Feeds überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="6f37f-117">Check that the feeds you expected are being checked.</span></span>

<span data-ttu-id="6f37f-118">Wenn die Installation erfolgreich abgeschlossen wurde, wird eine Meldung angezeigt, die den Befehl zum Aufrufen des Tools und die installierte Version ähnlich wie im folgenden Beispiel anzeigt:</span><span class="sxs-lookup"><span data-stu-id="6f37f-118">If installation is successful, a message is displayed showing the command used to call the tool and the version installed, similar to the following example:</span></span>

```console
You can invoke the tool using the following command: mlnet
Tool 'mlnet' (version 'X.X.X') was successfully installed.
```

<span data-ttu-id="6f37f-119">Sie können bestätigen, dass die Installation erfolgreich war, indem Sie den folgenden Befehl eingeben:</span><span class="sxs-lookup"><span data-stu-id="6f37f-119">You can confirm the installation was successful by typing the following command:</span></span>

```console
mlnet
```

<span data-ttu-id="6f37f-120">Es sollte die Hilfe zu den verfügbaren Befehlen für das mlnet-Tool angezeigt werden, wie z.B. den Befehl „auto-train“.</span><span class="sxs-lookup"><span data-stu-id="6f37f-120">You should see the help for available commands for the mlnet tool such as the 'auto-train' command.</span></span>

## <a name="install-a-specific-release-version"></a><span data-ttu-id="6f37f-121">Installieren einer bestimmten Releaseversion</span><span class="sxs-lookup"><span data-stu-id="6f37f-121">Install a specific release version</span></span>

<span data-ttu-id="6f37f-122">Wenn Sie versuchen, eine Vorabversion oder eine spezifische Version des Tools zu installieren, können Sie das [Framework](../../standard/frameworks.md) im folgenden Format angeben:</span><span class="sxs-lookup"><span data-stu-id="6f37f-122">If you're trying to install a pre-release version or a specific version of the tool, you can specify the [framework](../../standard/frameworks.md) using the following format:</span></span>

```dotnetcli
dotnet tool install -g mlnet --framework <FRAMEWORK>
```

<span data-ttu-id="6f37f-123">Sie können auch überprüfen, ob das Paket ordnungsgemäß installiert ist, indem Sie den folgenden Befehl eingeben:</span><span class="sxs-lookup"><span data-stu-id="6f37f-123">You can also check if the package is properly installed by typing the following command:</span></span>

```dotnetcli
dotnet tool list -g
```

## <a name="uninstall-the-cli-package"></a><span data-ttu-id="6f37f-124">Deinstallieren des CLI-Pakets</span><span class="sxs-lookup"><span data-stu-id="6f37f-124">Uninstall the CLI package</span></span>

<span data-ttu-id="6f37f-125">Geben Sie den folgenden Befehl ein, um das Paket über Ihren lokalen Computer zu deinstallieren:</span><span class="sxs-lookup"><span data-stu-id="6f37f-125">Type the following command to uninstall the package from your local machine:</span></span>

```dotnetcli
dotnet tool uninstall mlnet -g
```

## <a name="update-the-cli-package"></a><span data-ttu-id="6f37f-126">Aktualisieren des CLI-Pakets</span><span class="sxs-lookup"><span data-stu-id="6f37f-126">Update the CLI package</span></span>

<span data-ttu-id="6f37f-127">Geben Sie den folgenden Befehl ein, um das Paket über Ihren lokalen Computer zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="6f37f-127">Type the following command to update the package from your local machine:</span></span>

```dotnetcli
dotnet tool update -g mlnet
```

## <a name="set-up-cli-suggestions-tab-based-auto-completion"></a><span data-ttu-id="6f37f-128">Einrichten der CLI-Empfehlungen (tabellarische automatische Vervollständigung)</span><span class="sxs-lookup"><span data-stu-id="6f37f-128">Set up CLI suggestions (tab-based auto-completion)</span></span>

<span data-ttu-id="6f37f-129">Da die ML.NET-CLI auf `System.CommandLine` basiert, ist die Unterstützung für die tabellarische automatische Vervollständigung integriert.</span><span class="sxs-lookup"><span data-stu-id="6f37f-129">Since the ML.NET CLI is based on `System.CommandLine`, it has built-in support for tab completion.</span></span>

<span data-ttu-id="6f37f-130">Ein Beispiel für die Funktionsweise der tabellarischen automatischen Vervollständigung sehen Sie in der folgenden Animation:</span><span class="sxs-lookup"><span data-stu-id="6f37f-130">An example of how tab auto completion works is shown in the following animation:</span></span>

![Bild](./media/cli-tab-completion.gif)

<span data-ttu-id="6f37f-132">Die tabellarische automatische Vervollständigung (Parameterempfehlungen) funktioniert für *Windows PowerShell* und *macOS/Linux-Bash* aber nicht unter *Windows-CMD*.</span><span class="sxs-lookup"><span data-stu-id="6f37f-132">'Tab-based auto-completion' (parameter suggestions) works on *Windows PowerShell* and *macOS/Linux bash* but it won't work on *Windows CMD*.</span></span>

<span data-ttu-id="6f37f-133">Um die Funktion zu aktivieren, muss der Endbenutzer in der aktuellen Vorschauversion einmal pro Shell einige Schritte ausführen, wie nachfolgend beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6f37f-133">To enable it, in the current preview version, the end user has to take a few steps once per shell, outlined below.</span></span> <span data-ttu-id="6f37f-134">Danach funktionieren Vervollständigungen für alle Anwendungen, die mit `System.CommandLine` geschrieben wurden, wie z.B. ML.NET-CLI.</span><span class="sxs-lookup"><span data-stu-id="6f37f-134">Once this is done, completions will work for all apps written using `System.CommandLine` such as the ML.NET CLI.</span></span>

<span data-ttu-id="6f37f-135">Auf dem Computer, auf dem Sie die Vervollständigung aktivieren möchten, müssen Sie zwei Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="6f37f-135">On the machine where you'd like to enable completion, you'll need to do two things.</span></span>

1. <span data-ttu-id="6f37f-136">Installieren Sie das globale `dotnet-suggest`-Tool, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="6f37f-136">Install the `dotnet-suggest` global tool by running the following command:</span></span>

    ```dotnetcli
    dotnet tool install dotnet-suggest -g
    ```

2. <span data-ttu-id="6f37f-137">Fügen Sie das entsprechende Shim-Skript zu Ihrem Shell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="6f37f-137">Add the appropriate shim script to your shell profile.</span></span> <span data-ttu-id="6f37f-138">Möglicherweise müssen Sie eine Shell-Profildatei erstellen.</span><span class="sxs-lookup"><span data-stu-id="6f37f-138">You may have to create a shell profile file.</span></span> <span data-ttu-id="6f37f-139">Das Shim-Skript leitet Vervollständigungsanforderungen von Ihrer Shell an das `dotnet-suggest`-Tool weiter, das an die entsprechende `System.CommandLine`-basierte Anwendung delegiert.</span><span class="sxs-lookup"><span data-stu-id="6f37f-139">The shim script will forward completion requests from your shell to the `dotnet-suggest` tool, which delegates to the appropriate `System.CommandLine`-based app.</span></span>

    - <span data-ttu-id="6f37f-140">Fügen Sie für Bash den Inhalt von [dotnet-suggest-shim.bash](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.bash) zu `~/.bash_profile` hinzu.</span><span class="sxs-lookup"><span data-stu-id="6f37f-140">For bash, add the contents of [dotnet-suggest-shim.bash](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.bash) to `~/.bash_profile`.</span></span>

    - <span data-ttu-id="6f37f-141">Fügen Sie für PowerShell den Inhalt von [dotnet-suggest-shim.ps1](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.ps1) zu Ihrem PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="6f37f-141">For PowerShell, add the contents of [dotnet-suggest-shim.ps1](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.ps1) to your PowerShell profile.</span></span> <span data-ttu-id="6f37f-142">Den erwarteten Pfad zu Ihrem PowerShell-Profil finden Sie, indem Sie den folgenden Befehl in Ihrer Konsole ausführen:</span><span class="sxs-lookup"><span data-stu-id="6f37f-142">You can find the expected path to your PowerShell profile by running the following command in your console:</span></span>

    ```console
    echo $profile
    ```

<span data-ttu-id="6f37f-143">(Für die anderen Shells können Sie nach einem [Problem](https://github.com/dotnet/System.CommandLine/issues)[suchen](https://github.com/dotnet/System.CommandLine/issues?q=is%3Aissue+is%3Aopen+label%3A%22shell+suggestion%22) oder ein neues erstellen.)</span><span class="sxs-lookup"><span data-stu-id="6f37f-143">(For other shells, [look for](https://github.com/dotnet/System.CommandLine/issues?q=is%3Aissue+is%3Aopen+label%3A%22shell+suggestion%22) or open an [issue](https://github.com/dotnet/System.CommandLine/issues).)</span></span>

## <a name="installation-directory"></a><span data-ttu-id="6f37f-144">Installationsverzeichnis</span><span class="sxs-lookup"><span data-stu-id="6f37f-144">Installation directory</span></span>

<span data-ttu-id="6f37f-145">Die ML.NET-CLI kann im Standardverzeichnis oder an einem spezifischen Speicherort installiert werden.</span><span class="sxs-lookup"><span data-stu-id="6f37f-145">The ML.NET CLI can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="6f37f-146">Die Standardverzeichnisse sind:</span><span class="sxs-lookup"><span data-stu-id="6f37f-146">The default directories are:</span></span>

| <span data-ttu-id="6f37f-147">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="6f37f-147">OS</span></span>          | <span data-ttu-id="6f37f-148">Pfad</span><span class="sxs-lookup"><span data-stu-id="6f37f-148">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="6f37f-149">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="6f37f-149">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="6f37f-150">Windows</span><span class="sxs-lookup"><span data-stu-id="6f37f-150">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="6f37f-151">Diese Speicherorte werden dem Pfad des Benutzers hinzugefügt, wenn das SDK zum ersten Mal ausgeführt wird, damit dort installierte globale Tools direkt aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="6f37f-151">These locations are added to the user's path when the SDK is first run, so Global Tools installed there can be called directly.</span></span>

<span data-ttu-id="6f37f-152">Beachten Sie, dass die globalen Tools benutzerspezifisch gespeichert werden und nicht global auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="6f37f-152">Note: the Global Tools are user-specific, not machine global.</span></span> <span data-ttu-id="6f37f-153">Deshalb können Sie kein globales Tool installieren, das für alle Benutzer auf dem Computer verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="6f37f-153">Being user-specific means you cannot install a Global Tool that is available to all users of the machine.</span></span> <span data-ttu-id="6f37f-154">Das Tool ist nur für jedes Benutzerprofil verfügbar, auf denen das Tool installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="6f37f-154">The tool is only available for each user profile where the tool was installed.</span></span>

<span data-ttu-id="6f37f-155">Globale Tools können auch in einem spezifischen Verzeichnis installiert werden.</span><span class="sxs-lookup"><span data-stu-id="6f37f-155">Global Tools can also be installed in a specific directory.</span></span> <span data-ttu-id="6f37f-156">Wenn sie in einem spezifischen Verzeichnis installiert werden, muss der Benutzer sicherstellen, dass der Befehl verfügbar ist, indem das Verzeichnis in den Pfad eingefügt, der Befehl mit dem angegebenen Verzeichnis aufgerufen oder das Tool aus dem angegebenen Verzeichnis aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="6f37f-156">When installed in a specific directory, the user must ensure the command is available, by including that directory in the path, by calling the command with the directory specified, or calling the tool from within the specified directory.</span></span>
<span data-ttu-id="6f37f-157">In diesem Fall fügt die .NET Core-CLI diesen Speicherort nicht automatisch der Umgebungsvariable „PATH“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="6f37f-157">In this case, the .NET Core CLI doesn't add this location automatically to the PATH environment variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f37f-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f37f-158">See also</span></span>

- [<span data-ttu-id="6f37f-159">Übersicht über die ML.NET-CLI</span><span class="sxs-lookup"><span data-stu-id="6f37f-159">ML.NET CLI overview</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="6f37f-160">Tutorial: Stimmungsanalyse über die ML.NET-CLI</span><span class="sxs-lookup"><span data-stu-id="6f37f-160">Tutorial: Analyze sentiment with the ML.NET CLI</span></span>](../tutorials/sentiment-analysis-cli.md)
- [<span data-ttu-id="6f37f-161">Referenzhandbuch für den „auto-train“-Befehl in der ML.NET-CLI</span><span class="sxs-lookup"><span data-stu-id="6f37f-161">ML.NET CLI auto-train command reference guide</span></span>](../reference/ml-net-cli-reference.md)
- [<span data-ttu-id="6f37f-162">Telemetrie in der ML.NET-CLI</span><span class="sxs-lookup"><span data-stu-id="6f37f-162">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)
