---
title: "dotnet-nuget-push-Befehl – .NET Core-CLI"
description: "Der dotnet-nuget-push-Befehl überträgt ein Paket auf den Server und veröffentlicht es."
keywords: dotnet-nuget-push, CLI, CLI-Befehl, .NET Core
author: karann-msft
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: f54d9adf-94f8-41cc-bb52-42f7ca3be6ff
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 83da967d9d7432fcb422b88344ff597d45fc9e85
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-nuget-push"></a><span data-ttu-id="6965c-104">dotnet-nuget push</span><span class="sxs-lookup"><span data-stu-id="6965c-104">dotnet-nuget push</span></span>

## <a name="name"></a><span data-ttu-id="6965c-105">Name</span><span class="sxs-lookup"><span data-stu-id="6965c-105">Name</span></span>

<span data-ttu-id="6965c-106">`dotnet-nuget push` – Überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="6965c-106">`dotnet-nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6965c-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="6965c-107">Synopsis</span></span>

`dotnet nuget push [<ROOT>] [-s|--source] [-ss|--symbol-source] [-t|--timeout] [-k|--api-key] [-sk|--symbol-api-key] [-d|--disable-buffering] [-n|--no-symbols] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="6965c-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6965c-108">Description</span></span>

<span data-ttu-id="6965c-109">Der `dotnet nuget push`-Befehl überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="6965c-109">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="6965c-110">Der Pushbefehl verwendet Details zum Server und den Anmeldeinformationen aus der NuGet-Konfigurationsdatei oder der Kette von Konfigurationsdateien des Systems.</span><span class="sxs-lookup"><span data-stu-id="6965c-110">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="6965c-111">Weitere Informationen zu Konfigurationsdateien finden Sie unter [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Konfigurieren des Verhaltens von NuGet).</span><span class="sxs-lookup"><span data-stu-id="6965c-111">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="6965c-112">Die NuGet-Standardkonfiguration wird abgerufen, indem *%AppData%\NuGet\NuGet.config* (Windows) oder *$HOME/.local/share* (Linux/macOS) geladen wird. Anschließend wird eine beliebige Datei *nuget.config* oder *.nuget\nuget.config* geladen (beginnend mit dem Stamm des Laufwerks und endend im aktuellen Verzeichnis).</span><span class="sxs-lookup"><span data-stu-id="6965c-112">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="6965c-113">Argumente</span><span class="sxs-lookup"><span data-stu-id="6965c-113">Arguments</span></span>

`ROOT`

<span data-ttu-id="6965c-114">Geben Sie den Pfad des Pakets und den API-Schlüssel an, um das Paket an den Server zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="6965c-114">Specify the path to the package and your API key to push the package to the server.</span></span>

## <a name="options"></a><span data-ttu-id="6965c-115">Optionen</span><span class="sxs-lookup"><span data-stu-id="6965c-115">Options</span></span>

`-h|--help`

<span data-ttu-id="6965c-116">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="6965c-116">Prints out a short help for the command.</span></span>  

`-s|--source <SOURCE>`

<span data-ttu-id="6965c-117">Gibt die Server-URL an.</span><span class="sxs-lookup"><span data-stu-id="6965c-117">Specifies the server URL.</span></span> <span data-ttu-id="6965c-118">Diese Option ist erforderlich, es sei denn, der `DefaultPushSource`-Konfigurationswert wurde in der NuGet-Konfigurationsdatei festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6965c-118">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`--symbols-source <SOURCE>`

<span data-ttu-id="6965c-119">Gibt die Symbolserver-URL an.</span><span class="sxs-lookup"><span data-stu-id="6965c-119">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="6965c-120">Gibt das Timeout für die Übertragung auf einen Server in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="6965c-120">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="6965c-121">Der Standardwert ist 300 Sekunden (5 Minuten).</span><span class="sxs-lookup"><span data-stu-id="6965c-121">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="6965c-122">Wenn 0 (null Sekunden) angegeben wird, gilt der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="6965c-122">Specifying 0 (zero seconds) applies the default value.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="6965c-123">Der API-Schlüssel für den Server.</span><span class="sxs-lookup"><span data-stu-id="6965c-123">The API key for the server.</span></span>

`--symbol-api-key <API_KEY>`

<span data-ttu-id="6965c-124">Der API-Schlüssel für den Symbolserver.</span><span class="sxs-lookup"><span data-stu-id="6965c-124">The API key for the symbol server.</span></span>

`-d|--disable-buffering`

<span data-ttu-id="6965c-125">Deaktiviert die Pufferung bei Übertragungen an HTTP(S)-Server, um die Speicherauslastung zu verringern.</span><span class="sxs-lookup"><span data-stu-id="6965c-125">Disables buffering when pushing to an HTTP(S) server to decrease memory usage.</span></span>

`-n|--no-symbols`

<span data-ttu-id="6965c-126">Überträgt keine Symbole (selbst wenn vorhanden).</span><span class="sxs-lookup"><span data-stu-id="6965c-126">Doesn't push symbols (even if present).</span></span>

`--force-english-output`

<span data-ttu-id="6965c-127">Erzwingt, dass alle protokollierten Ausgaben auf Englisch sein müssen.</span><span class="sxs-lookup"><span data-stu-id="6965c-127">Forces all logged output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="6965c-128">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6965c-128">Examples</span></span>

<span data-ttu-id="6965c-129">Überträgt *foo.nupkg* an die standardmäßige Pushquelle und stellt einen API-Schlüssel bereit:</span><span class="sxs-lookup"><span data-stu-id="6965c-129">Pushes *foo.nupkg* to the default push source, providing an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

<span data-ttu-id="6965c-130">Überträgt *foo.nupkg* an die benutzerdefinierte Pushquelle `http://customsource` und stellt einen API-Schlüssel bereit:</span><span class="sxs-lookup"><span data-stu-id="6965c-130">Push *foo.nupkg* to the custom push source `http://customsource`, providing an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s http://customsource/` 

<span data-ttu-id="6965c-131">Überträgt *foo.nupkg* an die standardmäßige Pushquelle:</span><span class="sxs-lookup"><span data-stu-id="6965c-131">Pushes *foo.nupkg* to the default push source:</span></span>

`dotnet nuget push foo.nupkg` 

<span data-ttu-id="6965c-132">Überträgt *foo.symbols.nupkg* an die standardmäßige Symbolquelle:</span><span class="sxs-lookup"><span data-stu-id="6965c-132">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

`dotnet nuget push foo.symbols.nupkg`

<span data-ttu-id="6965c-133">Überträgt *foo.nupkg* an die standardmäßige Pushquelle und gibt ein Timeout von 360 Sekunden an:</span><span class="sxs-lookup"><span data-stu-id="6965c-133">Pushes *foo.nupkg* to the default push source, specifying a 360 second timeout:</span></span>

`dotnet nuget push foo.nupkg --timeout 360`

<span data-ttu-id="6965c-134">Überträgt alle *NUPKG*-Dateien im aktuellen Verzeichnis an die standardmäßige Pushquelle:</span><span class="sxs-lookup"><span data-stu-id="6965c-134">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

`dotnet nuget push *.nupkg`

<span data-ttu-id="6965c-135">Überträgt alle *NUPKG*-Dateien im aktuellen Verzeichnis an die standardmäßige Pushquelle und gibt die benutzerdefinierte Konfigurationsdatei *./config/My.Config* an:</span><span class="sxs-lookup"><span data-stu-id="6965c-135">Pushes all *.nupkg* files in the current directory to the default push source, specifying a custom config file *./config/My.Config*:</span></span>

`dotnet nuget push *.nupkg --config-file ./config/My.Config`

<span data-ttu-id="6965c-136">Überträgt alle *NUPKG*-Dateien im aktuellen Verzeichnis mit maximaler Ausführlichkeit an die standardmäßige Pushquelle:</span><span class="sxs-lookup"><span data-stu-id="6965c-136">Push all *.nupkg* files in the current directory to the default push source with maximum verbosity:</span></span>

`dotnet nuget push *.nupkg --verbosity detailed`

