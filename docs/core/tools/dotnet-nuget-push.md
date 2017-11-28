---
title: "dotnet nuget push-Befehl – .NET Core-CLI"
description: "Der dotnet nuget push-Befehl überträgt ein Paket auf den Server und veröffentlicht es."
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 6721615e4df820ab50ea4f79fbba30daeffe8165
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="55491-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="55491-103">dotnet nuget push</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="55491-104">Name</span><span class="sxs-lookup"><span data-stu-id="55491-104">Name</span></span>

<span data-ttu-id="55491-105">`dotnet nuget push` – Überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="55491-105">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="55491-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="55491-106">Synopsis</span></span>

`dotnet nuget push [<ROOT>] [-s|--source] [-ss|--symbol-source] [-t|--timeout] [-k|--api-key] [-sk|--symbol-api-key] [-d|--disable-buffering] [-n|--no-symbols] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="55491-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55491-107">Description</span></span>

<span data-ttu-id="55491-108">Der `dotnet nuget push`-Befehl überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="55491-108">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="55491-109">Der Pushbefehl verwendet Details zum Server und den Anmeldeinformationen aus der NuGet-Konfigurationsdatei oder der Kette von Konfigurationsdateien des Systems.</span><span class="sxs-lookup"><span data-stu-id="55491-109">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="55491-110">Weitere Informationen zu Konfigurationsdateien finden Sie unter [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Konfigurieren des Verhaltens von NuGet).</span><span class="sxs-lookup"><span data-stu-id="55491-110">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="55491-111">Die NuGet-Standardkonfiguration wird abgerufen, indem *%AppData%\NuGet\NuGet.config* (Windows) oder *$HOME/.local/share* (Linux/macOS) geladen wird. Anschließend wird eine beliebige Datei *nuget.config* oder *.nuget\nuget.config* geladen (beginnend mit dem Stamm des Laufwerks und endend im aktuellen Verzeichnis).</span><span class="sxs-lookup"><span data-stu-id="55491-111">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="55491-112">Argumente</span><span class="sxs-lookup"><span data-stu-id="55491-112">Arguments</span></span>

`ROOT`

<span data-ttu-id="55491-113">Geben Sie den Pfad des Pakets und den API-Schlüssel an, um das Paket an den Server zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="55491-113">Specify the path to the package and your API key to push the package to the server.</span></span>

## <a name="options"></a><span data-ttu-id="55491-114">Optionen</span><span class="sxs-lookup"><span data-stu-id="55491-114">Options</span></span>

`-h|--help`

<span data-ttu-id="55491-115">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="55491-115">Prints out a short help for the command.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="55491-116">Gibt die Server-URL an.</span><span class="sxs-lookup"><span data-stu-id="55491-116">Specifies the server URL.</span></span> <span data-ttu-id="55491-117">Diese Option ist erforderlich, es sei denn, der `DefaultPushSource`-Konfigurationswert wurde in der NuGet-Konfigurationsdatei festgelegt.</span><span class="sxs-lookup"><span data-stu-id="55491-117">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`--symbols-source <SOURCE>`

<span data-ttu-id="55491-118">Gibt die Symbolserver-URL an.</span><span class="sxs-lookup"><span data-stu-id="55491-118">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="55491-119">Gibt das Timeout für die Übertragung auf einen Server in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="55491-119">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="55491-120">Der Standardwert ist 300 Sekunden (5 Minuten).</span><span class="sxs-lookup"><span data-stu-id="55491-120">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="55491-121">Wenn 0 (null Sekunden) angegeben wird, gilt der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="55491-121">Specifying 0 (zero seconds) applies the default value.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="55491-122">Der API-Schlüssel für den Server.</span><span class="sxs-lookup"><span data-stu-id="55491-122">The API key for the server.</span></span>

`--symbol-api-key <API_KEY>`

<span data-ttu-id="55491-123">Der API-Schlüssel für den Symbolserver.</span><span class="sxs-lookup"><span data-stu-id="55491-123">The API key for the symbol server.</span></span>

`-d|--disable-buffering`

<span data-ttu-id="55491-124">Deaktiviert die Pufferung bei Übertragungen an HTTP(S)-Server, um die Speicherauslastung zu verringern.</span><span class="sxs-lookup"><span data-stu-id="55491-124">Disables buffering when pushing to an HTTP(S) server to decrease memory usage.</span></span>

`-n|--no-symbols`

<span data-ttu-id="55491-125">Überträgt keine Symbole (selbst wenn vorhanden).</span><span class="sxs-lookup"><span data-stu-id="55491-125">Doesn't push symbols (even if present).</span></span>

`--force-english-output`

<span data-ttu-id="55491-126">Erzwingt, dass alle protokollierten Ausgaben auf Englisch sein müssen.</span><span class="sxs-lookup"><span data-stu-id="55491-126">Forces all logged output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="55491-127">Beispiele</span><span class="sxs-lookup"><span data-stu-id="55491-127">Examples</span></span>

<span data-ttu-id="55491-128">Überträgt *foo.nupkg* an die standardmäßige Pushquelle und stellt einen API-Schlüssel bereit:</span><span class="sxs-lookup"><span data-stu-id="55491-128">Pushes *foo.nupkg* to the default push source, providing an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

<span data-ttu-id="55491-129">Überträgt *foo.nupkg* an die benutzerdefinierte Pushquelle `http://customsource` und stellt einen API-Schlüssel bereit:</span><span class="sxs-lookup"><span data-stu-id="55491-129">Push *foo.nupkg* to the custom push source `http://customsource`, providing an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s http://customsource/`

<span data-ttu-id="55491-130">Überträgt *foo.nupkg* an die standardmäßige Pushquelle:</span><span class="sxs-lookup"><span data-stu-id="55491-130">Pushes *foo.nupkg* to the default push source:</span></span>

`dotnet nuget push foo.nupkg`

<span data-ttu-id="55491-131">Überträgt *foo.symbols.nupkg* an die standardmäßige Symbolquelle:</span><span class="sxs-lookup"><span data-stu-id="55491-131">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

`dotnet nuget push foo.symbols.nupkg`

<span data-ttu-id="55491-132">Überträgt *foo.nupkg* an die standardmäßige Pushquelle und gibt ein Timeout von 360 Sekunden an:</span><span class="sxs-lookup"><span data-stu-id="55491-132">Pushes *foo.nupkg* to the default push source, specifying a 360 second timeout:</span></span>

`dotnet nuget push foo.nupkg --timeout 360`

<span data-ttu-id="55491-133">Überträgt alle *NUPKG*-Dateien im aktuellen Verzeichnis an die standardmäßige Pushquelle:</span><span class="sxs-lookup"><span data-stu-id="55491-133">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

`dotnet nuget push *.nupkg`

<span data-ttu-id="55491-134">Überträgt alle *NUPKG*-Dateien im aktuellen Verzeichnis an die standardmäßige Pushquelle und gibt die benutzerdefinierte Konfigurationsdatei *./config/My.Config* an:</span><span class="sxs-lookup"><span data-stu-id="55491-134">Pushes all *.nupkg* files in the current directory to the default push source, specifying a custom config file *./config/My.Config*:</span></span>

`dotnet nuget push *.nupkg --config-file ./config/My.Config`

<span data-ttu-id="55491-135">Überträgt alle *NUPKG*-Dateien im aktuellen Verzeichnis mit maximaler Ausführlichkeit an die standardmäßige Pushquelle:</span><span class="sxs-lookup"><span data-stu-id="55491-135">Push all *.nupkg* files in the current directory to the default push source with maximum verbosity:</span></span>

`dotnet nuget push *.nupkg --verbosity detailed`
