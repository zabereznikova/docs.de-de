---
title: dotnet nuget push-Befehl – .NET Core-CLI
description: Der dotnet nuget push-Befehl überträgt ein Paket auf den Server und veröffentlicht es.
author: karann-msft
ms.author: mairaw
ms.date: 09/04/2018
ms.openlocfilehash: 23d27cef29008955850f9ed9f4a8baed9e7ad982
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2018
ms.locfileid: "45610001"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="489d7-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="489d7-103">dotnet nuget push</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="489d7-104">name</span><span class="sxs-lookup"><span data-stu-id="489d7-104">Name</span></span>

<span data-ttu-id="489d7-105">`dotnet nuget push` – Überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="489d7-105">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="489d7-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="489d7-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="489d7-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="489d7-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="489d7-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="489d7-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="489d7-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="489d7-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="489d7-110">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="489d7-110">Description</span></span>

<span data-ttu-id="489d7-111">Der `dotnet nuget push`-Befehl überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="489d7-111">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="489d7-112">Der Pushbefehl verwendet Details zum Server und den Anmeldeinformationen aus der NuGet-Konfigurationsdatei oder der Kette von Konfigurationsdateien des Systems.</span><span class="sxs-lookup"><span data-stu-id="489d7-112">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="489d7-113">Weitere Informationen zu Konfigurationsdateien finden Sie unter [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Konfigurieren des Verhaltens von NuGet).</span><span class="sxs-lookup"><span data-stu-id="489d7-113">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="489d7-114">Die NuGet-Standardkonfiguration wird abgerufen, indem *%AppData%\NuGet\NuGet.config* (Windows) oder *$HOME/.local/share* (Linux/macOS) geladen wird. Anschließend wird eine beliebige Datei *nuget.config* oder *.nuget\nuget.config* geladen (beginnend mit dem Stamm des Laufwerks und endend im aktuellen Verzeichnis).</span><span class="sxs-lookup"><span data-stu-id="489d7-114">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="489d7-115">Argumente</span><span class="sxs-lookup"><span data-stu-id="489d7-115">Arguments</span></span>

`ROOT`

<span data-ttu-id="489d7-116">Gibt den Dateipfad des Pakets an, das per Push übertragen werden soll.</span><span class="sxs-lookup"><span data-stu-id="489d7-116">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="489d7-117">Optionen</span><span class="sxs-lookup"><span data-stu-id="489d7-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="489d7-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="489d7-118">.NET Core 2.1</span></span>](#tab/netcore21)

`-d|--disable-buffering`

<span data-ttu-id="489d7-119">Deaktiviert die Pufferung bei Übertragungen an HTTP(S)-Server, um die Speicherauslastung zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="489d7-119">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

`--force-english-output`

<span data-ttu-id="489d7-120">Erzwingt die Ausführung der Anwendung mithilfe einer invarianten Kultur, die auf Englisch basiert.</span><span class="sxs-lookup"><span data-stu-id="489d7-120">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="489d7-121">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="489d7-121">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="489d7-122">Der API-Schlüssel für den Server.</span><span class="sxs-lookup"><span data-stu-id="489d7-122">The API key for the server.</span></span>

`-n|--no-symbols`

<span data-ttu-id="489d7-123">Überträgt keine Symbole (selbst wenn vorhanden).</span><span class="sxs-lookup"><span data-stu-id="489d7-123">Doesn't push symbols (even if present).</span></span>

`--no-service-endpoint`

<span data-ttu-id="489d7-124">Fügt „api/v2/package“ nicht der Quell-URL an.</span><span class="sxs-lookup"><span data-stu-id="489d7-124">Doesn't append "api/v2/package" to the source URL.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="489d7-125">Gibt die Server-URL an.</span><span class="sxs-lookup"><span data-stu-id="489d7-125">Specifies the server URL.</span></span> <span data-ttu-id="489d7-126">Diese Option ist erforderlich, es sei denn, der `DefaultPushSource`-Konfigurationswert wurde in der NuGet-Konfigurationsdatei festgelegt.</span><span class="sxs-lookup"><span data-stu-id="489d7-126">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`-sk|--symbol-api-key <API_KEY>`

<span data-ttu-id="489d7-127">Der API-Schlüssel für den Symbolserver.</span><span class="sxs-lookup"><span data-stu-id="489d7-127">The API key for the symbol server.</span></span>

`-ss|--symbol-source <SOURCE>`

<span data-ttu-id="489d7-128">Gibt die Symbolserver-URL an.</span><span class="sxs-lookup"><span data-stu-id="489d7-128">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="489d7-129">Gibt das Timeout für die Übertragung auf einen Server in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="489d7-129">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="489d7-130">Der Standardwert ist 300 Sekunden (5 Minuten).</span><span class="sxs-lookup"><span data-stu-id="489d7-130">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="489d7-131">Wenn 0 (null Sekunden) angegeben wird, gilt der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="489d7-131">Specifying 0 (zero seconds) applies the default value.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="489d7-132">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="489d7-132">.NET Core 2.0</span></span>](#tab/netcore20)

`-d|--disable-buffering`

<span data-ttu-id="489d7-133">Deaktiviert die Pufferung bei Übertragungen an HTTP(S)-Server, um die Speicherauslastung zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="489d7-133">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

`--force-english-output`

<span data-ttu-id="489d7-134">Erzwingt die Ausführung der Anwendung mithilfe einer invarianten Kultur, die auf Englisch basiert.</span><span class="sxs-lookup"><span data-stu-id="489d7-134">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="489d7-135">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="489d7-135">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="489d7-136">Der API-Schlüssel für den Server.</span><span class="sxs-lookup"><span data-stu-id="489d7-136">The API key for the server.</span></span>

`-n|--no-symbols`

<span data-ttu-id="489d7-137">Überträgt keine Symbole (selbst wenn vorhanden).</span><span class="sxs-lookup"><span data-stu-id="489d7-137">Doesn't push symbols (even if present).</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="489d7-138">Gibt die Server-URL an.</span><span class="sxs-lookup"><span data-stu-id="489d7-138">Specifies the server URL.</span></span> <span data-ttu-id="489d7-139">Diese Option ist erforderlich, es sei denn, der `DefaultPushSource`-Konfigurationswert wurde in der NuGet-Konfigurationsdatei festgelegt.</span><span class="sxs-lookup"><span data-stu-id="489d7-139">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`-sk|--symbol-api-key <API_KEY>`

<span data-ttu-id="489d7-140">Der API-Schlüssel für den Symbolserver.</span><span class="sxs-lookup"><span data-stu-id="489d7-140">The API key for the symbol server.</span></span>

`-ss|--symbol-source <SOURCE>`

<span data-ttu-id="489d7-141">Gibt die Symbolserver-URL an.</span><span class="sxs-lookup"><span data-stu-id="489d7-141">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="489d7-142">Gibt das Timeout für die Übertragung auf einen Server in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="489d7-142">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="489d7-143">Der Standardwert ist 300 Sekunden (5 Minuten).</span><span class="sxs-lookup"><span data-stu-id="489d7-143">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="489d7-144">Wenn 0 (null Sekunden) angegeben wird, gilt der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="489d7-144">Specifying 0 (zero seconds) applies the default value.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="489d7-145">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="489d7-145">.NET Core 1.x</span></span>](#tab/netcore1x)

`-d|--disable-buffering`

<span data-ttu-id="489d7-146">Deaktiviert die Pufferung bei Übertragungen an HTTP(S)-Server, um die Speicherauslastung zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="489d7-146">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

`--force-english-output`

<span data-ttu-id="489d7-147">Erzwingt die Ausführung der Anwendung mithilfe einer invarianten Kultur, die auf Englisch basiert.</span><span class="sxs-lookup"><span data-stu-id="489d7-147">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="489d7-148">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="489d7-148">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="489d7-149">Der API-Schlüssel für den Server.</span><span class="sxs-lookup"><span data-stu-id="489d7-149">The API key for the server.</span></span>

`-n|--no-symbols`

<span data-ttu-id="489d7-150">Überträgt keine Symbole (selbst wenn vorhanden).</span><span class="sxs-lookup"><span data-stu-id="489d7-150">Doesn't push symbols (even if present).</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="489d7-151">Gibt die Server-URL an.</span><span class="sxs-lookup"><span data-stu-id="489d7-151">Specifies the server URL.</span></span> <span data-ttu-id="489d7-152">Diese Option ist erforderlich, es sei denn, der `DefaultPushSource`-Konfigurationswert wurde in der NuGet-Konfigurationsdatei festgelegt.</span><span class="sxs-lookup"><span data-stu-id="489d7-152">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`-sk|--symbol-api-key <API_KEY>`

<span data-ttu-id="489d7-153">Der API-Schlüssel für den Symbolserver.</span><span class="sxs-lookup"><span data-stu-id="489d7-153">The API key for the symbol server.</span></span>

`-ss|--symbol-source <SOURCE>`

<span data-ttu-id="489d7-154">Gibt die Symbolserver-URL an.</span><span class="sxs-lookup"><span data-stu-id="489d7-154">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="489d7-155">Gibt das Timeout für die Übertragung auf einen Server in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="489d7-155">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="489d7-156">Der Standardwert ist 300 Sekunden (5 Minuten).</span><span class="sxs-lookup"><span data-stu-id="489d7-156">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="489d7-157">Wenn 0 (null Sekunden) angegeben wird, gilt der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="489d7-157">Specifying 0 (zero seconds) applies the default value.</span></span>

---

## <a name="examples"></a><span data-ttu-id="489d7-158">Beispiele</span><span class="sxs-lookup"><span data-stu-id="489d7-158">Examples</span></span>

<span data-ttu-id="489d7-159">Überträgt *foo.nupkg* an die Standardpushquelle und gibt einen API-Schlüssel an:</span><span class="sxs-lookup"><span data-stu-id="489d7-159">Pushes *foo.nupkg* to the default push source, specifying an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

<span data-ttu-id="489d7-160">Überträgt *foo.nupkg* an die benutzerdefinierte Pushquelle `http://customsource` und gibt einen API-Schlüssel an:</span><span class="sxs-lookup"><span data-stu-id="489d7-160">Push *foo.nupkg* to the custom push source `http://customsource`, specifying an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s http://customsource/`

<span data-ttu-id="489d7-161">Überträgt *foo.nupkg* an die standardmäßige Pushquelle:</span><span class="sxs-lookup"><span data-stu-id="489d7-161">Pushes *foo.nupkg* to the default push source:</span></span>

`dotnet nuget push foo.nupkg`

<span data-ttu-id="489d7-162">Überträgt *foo.symbols.nupkg* an die standardmäßige Symbolquelle:</span><span class="sxs-lookup"><span data-stu-id="489d7-162">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

`dotnet nuget push foo.symbols.nupkg`

<span data-ttu-id="489d7-163">Überträgt *foo.nupkg* an die Standardpushquelle und gibt ein Timeout von 360 Sekunden an:</span><span class="sxs-lookup"><span data-stu-id="489d7-163">Pushes *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

`dotnet nuget push foo.nupkg --timeout 360`

<span data-ttu-id="489d7-164">Überträgt alle *NUPKG*-Dateien im aktuellen Verzeichnis an die standardmäßige Pushquelle:</span><span class="sxs-lookup"><span data-stu-id="489d7-164">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

`dotnet nuget push *.nupkg`
