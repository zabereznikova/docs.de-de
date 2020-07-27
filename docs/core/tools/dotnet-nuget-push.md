---
title: Befehl „dotnet nuget push“
description: Der dotnet nuget push-Befehl überträgt ein Paket auf den Server und veröffentlicht es.
author: karann-msft
ms.date: 02/14/2020
ms.openlocfilehash: 608cd05d94dd6b5cdc53d582cfaa0407f011ff37
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925513"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="c4f35-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="c4f35-103">dotnet nuget push</span></span>

<span data-ttu-id="c4f35-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="c4f35-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="c4f35-105">name</span><span class="sxs-lookup"><span data-stu-id="c4f35-105">Name</span></span>

<span data-ttu-id="c4f35-106">`dotnet nuget push` – Überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="c4f35-106">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c4f35-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c4f35-107">Synopsis</span></span>

```dotnetcli
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output]
    [--interactive] [-k|--api-key <API_KEY>] [-n|--no-symbols true]
    [--no-service-endpoint] [-s|--source <SOURCE>] [--skip-duplicate]
    [-sk|--symbol-api-key <API_KEY>] [-ss|--symbol-source <SOURCE>]
    [-t|--timeout <TIMEOUT>]

dotnet nuget push -h|--help
```

## <a name="description"></a><span data-ttu-id="c4f35-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c4f35-108">Description</span></span>

<span data-ttu-id="c4f35-109">Der `dotnet nuget push`-Befehl überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="c4f35-109">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="c4f35-110">Der Pushbefehl verwendet Details zum Server und den Anmeldeinformationen aus der NuGet-Konfigurationsdatei oder der Kette von Konfigurationsdateien des Systems.</span><span class="sxs-lookup"><span data-stu-id="c4f35-110">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="c4f35-111">Weitere Informationen zu Konfigurationsdateien finden Sie unter [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Konfigurieren des Verhaltens von NuGet).</span><span class="sxs-lookup"><span data-stu-id="c4f35-111">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="c4f35-112">Die NuGet-Standardkonfiguration wird abgerufen, indem *%AppData%\NuGet\NuGet.config* (Windows) oder *$HOME/.local/share* (Linux/macOS) geladen wird. Anschließend wird eine beliebige Datei *nuget.config* oder *.nuget\nuget.config* geladen (beginnend mit dem Stamm des Laufwerks und endend im aktuellen Verzeichnis).</span><span class="sxs-lookup"><span data-stu-id="c4f35-112">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

<span data-ttu-id="c4f35-113">Der Befehl pusht ein vorhandenes Paket.</span><span class="sxs-lookup"><span data-stu-id="c4f35-113">The command pushes an existing package.</span></span> <span data-ttu-id="c4f35-114">Es wird kein Paket erstellt.</span><span class="sxs-lookup"><span data-stu-id="c4f35-114">It doesn't create a package.</span></span> <span data-ttu-id="c4f35-115">Verwenden Sie [`dotnet pack`](dotnet-pack.md), um ein Paket zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c4f35-115">To create a package, use [`dotnet pack`](dotnet-pack.md).</span></span>

## <a name="arguments"></a><span data-ttu-id="c4f35-116">Argumente</span><span class="sxs-lookup"><span data-stu-id="c4f35-116">Arguments</span></span>

- **`ROOT`**

  <span data-ttu-id="c4f35-117">Gibt den Dateipfad des Pakets an, das per Push übertragen werden soll.</span><span class="sxs-lookup"><span data-stu-id="c4f35-117">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="c4f35-118">Optionen</span><span class="sxs-lookup"><span data-stu-id="c4f35-118">Options</span></span>

- **`-d|--disable-buffering`**

  <span data-ttu-id="c4f35-119">Deaktiviert die Pufferung bei Übertragungen an HTTP(S)-Server, um die Speicherauslastung zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="c4f35-119">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

- **`--force-english-output`**

  <span data-ttu-id="c4f35-120">Erzwingt die Ausführung der Anwendung mithilfe einer invarianten Kultur, die auf Englisch basiert.</span><span class="sxs-lookup"><span data-stu-id="c4f35-120">Forces the application to run using an invariant, English-based culture.</span></span>

- **`-h|--help`**

  <span data-ttu-id="c4f35-121">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="c4f35-121">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="c4f35-122">Ermöglicht, den Befehl zu blockieren, und fordert für Vorgänge wie z.B. die Authentifizierung eine manuelle Aktion.</span><span class="sxs-lookup"><span data-stu-id="c4f35-122">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="c4f35-123">Die Option ist seit dem .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c4f35-123">Option available since .NET Core 2.2 SDK.</span></span>

- **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="c4f35-124">Der API-Schlüssel für den Server.</span><span class="sxs-lookup"><span data-stu-id="c4f35-124">The API key for the server.</span></span>

- **`-n|--no-symbols true`**

  <span data-ttu-id="c4f35-125">Überträgt keine Symbole (selbst wenn vorhanden).</span><span class="sxs-lookup"><span data-stu-id="c4f35-125">Doesn't push symbols (even if present).</span></span>

- **`--no-service-endpoint`**

  <span data-ttu-id="c4f35-126">Fügt „api/v2/package“ nicht der Quell-URL an.</span><span class="sxs-lookup"><span data-stu-id="c4f35-126">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="c4f35-127">Die Option ist seit dem .NET Core 2.1 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c4f35-127">Option available since .NET Core 2.1 SDK.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="c4f35-128">Gibt die Server-URL an.</span><span class="sxs-lookup"><span data-stu-id="c4f35-128">Specifies the server URL.</span></span> <span data-ttu-id="c4f35-129">Diese Option ist erforderlich, es sei denn, der `DefaultPushSource`-Konfigurationswert wurde in der NuGet-Konfigurationsdatei festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c4f35-129">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

- **`--skip-duplicate`**

  <span data-ttu-id="c4f35-130">Wenn Sie mehrere Pakete per Push an einen HTTP(S)-Server senden, werden alle Antworten des Typs „409 (Konflikt)“ als Warnung behandelt, sodass der Pushvorgang fortgesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c4f35-130">When pushing multiple packages to an HTTP(S) server, treats any 409 Conflict response as a warning so that the push can continue.</span></span> <span data-ttu-id="c4f35-131">Verfügbar seit .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="c4f35-131">Available since .NET Core 3.1 SDK.</span></span>

- **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="c4f35-132">Der API-Schlüssel für den Symbolserver.</span><span class="sxs-lookup"><span data-stu-id="c4f35-132">The API key for the symbol server.</span></span>

- **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="c4f35-133">Gibt die Symbolserver-URL an.</span><span class="sxs-lookup"><span data-stu-id="c4f35-133">Specifies the symbol server URL.</span></span>

- **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="c4f35-134">Gibt das Timeout für die Übertragung auf einen Server in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="c4f35-134">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="c4f35-135">Der Standardwert ist 300 Sekunden (5 Minuten).</span><span class="sxs-lookup"><span data-stu-id="c4f35-135">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="c4f35-136">Wenn 0 (null Sekunden) angegeben wird, gilt der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="c4f35-136">Specifying 0 (zero seconds) applies the default value.</span></span>

## <a name="examples"></a><span data-ttu-id="c4f35-137">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c4f35-137">Examples</span></span>

- <span data-ttu-id="c4f35-138">Pusht *foo.nupkg* an die Standardpushquelle und gibt einen API-Schlüssel an:</span><span class="sxs-lookup"><span data-stu-id="c4f35-138">Push *foo.nupkg* to the default push source, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

- <span data-ttu-id="c4f35-139">Überträgt *foo.nupkg* an den offiziellen NuGet-Server und gibt einen API-Schlüssel an:</span><span class="sxs-lookup"><span data-stu-id="c4f35-139">Push *foo.nupkg* to the official NuGet server, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://api.nuget.org/v3/index.json
  ```
  
  * <span data-ttu-id="c4f35-140">Überträgt *foo.nupkg* an die benutzerdefinierte Pushquelle `https://customsource` und gibt einen API-Schlüssel an:</span><span class="sxs-lookup"><span data-stu-id="c4f35-140">Push *foo.nupkg* to the custom push source `https://customsource`, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

- <span data-ttu-id="c4f35-141">Pusht *foo.nupkg* an die Standardpushquelle:</span><span class="sxs-lookup"><span data-stu-id="c4f35-141">Push *foo.nupkg* to the default push source:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg
  ```

- <span data-ttu-id="c4f35-142">Pusht *foo.symbols.nupkg* an die Standardsymbolquelle:</span><span class="sxs-lookup"><span data-stu-id="c4f35-142">Push *foo.symbols.nupkg* to the default symbols source:</span></span>

  ```dotnetcli
  dotnet nuget push foo.symbols.nupkg
  ```

- <span data-ttu-id="c4f35-143">Pusht *foo.nupkg* an die Standardpushquelle und gibt ein Timeout von 360 Sekunden an:</span><span class="sxs-lookup"><span data-stu-id="c4f35-143">Push *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg --timeout 360
  ```

- <span data-ttu-id="c4f35-144">Pusht alle *NUPKG*-Dateien im aktuellen Verzeichnis an die Standardpushquelle:</span><span class="sxs-lookup"><span data-stu-id="c4f35-144">Push all *.nupkg* files in the current directory to the default push source:</span></span>

  ```dotnetcli
  dotnet nuget push *.nupkg
  ```

  > [!NOTE]
  > <span data-ttu-id="c4f35-145">Wenn dieser Befehl nicht funktioniert, kann dies an einem Fehler aus früheren Versionen des SDK liegen (.NET Core 2.1 SDK und frühere Versionen).</span><span class="sxs-lookup"><span data-stu-id="c4f35-145">If this command doesn't work, it might be due to a bug that existed in older versions of the SDK (.NET Core 2.1 SDK and earlier versions).</span></span>
  > <span data-ttu-id="c4f35-146">Führen Sie ein Upgrade für das SDK durch, oder führen Sie stattdessen den folgenden Befehl aus, um diesen Fehler zu beheben: `dotnet nuget push **/*.nupkg`.</span><span class="sxs-lookup"><span data-stu-id="c4f35-146">To fix this, upgrade your SDK version or run the following command instead: `dotnet nuget push **/*.nupkg`</span></span>

- <span data-ttu-id="c4f35-147">Pusht alle *NUPKG*-Dateien, auch wenn eine Antwort des Typs „409 (Konflikt)“ von einem HTTP(S)-Server zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="c4f35-147">Push all *.nupkg* files even if a 409 Conflict response is returned by an HTTP(S) server:</span></span>

  ```dotnetcli
  dotnet nuget push *.nupkg --skip-duplicate
  ```

- <span data-ttu-id="c4f35-148">Pushen Sie alle *NUPKG*-Dateien im aktuellen Verzeichnis an ein lokales Feedverzeichnis:</span><span class="sxs-lookup"><span data-stu-id="c4f35-148">Push all *.nupkg* files in the current directory to a local feed directory:</span></span>

  ```dotnetcli
  dotnet nuget push *.nupkg -s c:\mydir
  ```

  <span data-ttu-id="c4f35-149">Dieser Befehl speichert Pakete nicht in einer hierarchischen Ordnerstruktur, um die Leistung zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="c4f35-149">This command doesn't store packages in a hierarchical folder structure, which is recommended to optimize performance.</span></span> <span data-ttu-id="c4f35-150">Weitere Informationen finden Sie im Artikel zu [lokalen Feeds](/nuget/hosting-packages/local-feeds).</span><span class="sxs-lookup"><span data-stu-id="c4f35-150">For more information, see [Local feeds](/nuget/hosting-packages/local-feeds).</span></span>  
