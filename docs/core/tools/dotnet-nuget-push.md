---
title: Befehl „dotnet nuget push“
description: Der dotnet nuget push-Befehl überträgt ein Paket auf den Server und veröffentlicht es.
author: karann-msft
ms.date: 02/14/2020
ms.openlocfilehash: 99e735f7bb18b7af1c12c3ef77fc150a19083542
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970654"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="0654c-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="0654c-103">dotnet nuget push</span></span>

<span data-ttu-id="0654c-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="0654c-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="0654c-105">name</span><span class="sxs-lookup"><span data-stu-id="0654c-105">Name</span></span>

<span data-ttu-id="0654c-106">`dotnet nuget push` – Überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="0654c-106">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0654c-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="0654c-107">Synopsis</span></span>

```dotnetcli
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output]
    [--interactive] [-k|--api-key <API_KEY>] [-n|--no-symbols true]
    [--no-service-endpoint] [-s|--source <SOURCE>] [--skip-duplicate]
    [-sk|--symbol-api-key <API_KEY>] [-ss|--symbol-source <SOURCE>]
    [-t|--timeout <TIMEOUT>]

dotnet nuget push -h|--help
```

## <a name="description"></a><span data-ttu-id="0654c-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0654c-108">Description</span></span>

<span data-ttu-id="0654c-109">Der `dotnet nuget push`-Befehl überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="0654c-109">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="0654c-110">Der Pushbefehl verwendet Details zum Server und den Anmeldeinformationen aus der NuGet-Konfigurationsdatei oder der Kette von Konfigurationsdateien des Systems.</span><span class="sxs-lookup"><span data-stu-id="0654c-110">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="0654c-111">Weitere Informationen zu Konfigurationsdateien finden Sie unter [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Konfigurieren des Verhaltens von NuGet).</span><span class="sxs-lookup"><span data-stu-id="0654c-111">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="0654c-112">Die NuGet-Standardkonfiguration wird abgerufen, indem *%AppData%\NuGet\NuGet.config* (Windows) oder *$HOME/.local/share* (Linux/macOS) geladen wird. Anschließend wird eine beliebige Datei *nuget.config* oder *.nuget\nuget.config* geladen (beginnend mit dem Stamm des Laufwerks und endend im aktuellen Verzeichnis).</span><span class="sxs-lookup"><span data-stu-id="0654c-112">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

<span data-ttu-id="0654c-113">Der Befehl pusht ein vorhandenes Paket.</span><span class="sxs-lookup"><span data-stu-id="0654c-113">The command pushes an existing package.</span></span> <span data-ttu-id="0654c-114">Es wird kein Paket erstellt.</span><span class="sxs-lookup"><span data-stu-id="0654c-114">It doesn't create a package.</span></span> <span data-ttu-id="0654c-115">Verwenden Sie [`dotnet pack`](dotnet-pack.md), um ein Paket zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0654c-115">To create a package, use [`dotnet pack`](dotnet-pack.md).</span></span>

## <a name="arguments"></a><span data-ttu-id="0654c-116">Argumente</span><span class="sxs-lookup"><span data-stu-id="0654c-116">Arguments</span></span>

- **`ROOT`**

  <span data-ttu-id="0654c-117">Gibt den Dateipfad des Pakets an, das per Push übertragen werden soll.</span><span class="sxs-lookup"><span data-stu-id="0654c-117">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="0654c-118">Optionen</span><span class="sxs-lookup"><span data-stu-id="0654c-118">Options</span></span>

- **`-d|--disable-buffering`**

  <span data-ttu-id="0654c-119">Deaktiviert die Pufferung bei Übertragungen an HTTP(S)-Server, um die Speicherauslastung zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="0654c-119">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

- **`--force-english-output`**

  <span data-ttu-id="0654c-120">Erzwingt die Ausführung der Anwendung mithilfe einer invarianten Kultur, die auf Englisch basiert.</span><span class="sxs-lookup"><span data-stu-id="0654c-120">Forces the application to run using an invariant, English-based culture.</span></span>

- **`-h|--help`**

  <span data-ttu-id="0654c-121">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="0654c-121">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="0654c-122">Ermöglicht, den Befehl zu blockieren, und fordert für Vorgänge wie z.B. die Authentifizierung eine manuelle Aktion.</span><span class="sxs-lookup"><span data-stu-id="0654c-122">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="0654c-123">Die Option ist seit dem .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0654c-123">Option available since .NET Core 2.2 SDK.</span></span>

- **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="0654c-124">Der API-Schlüssel für den Server.</span><span class="sxs-lookup"><span data-stu-id="0654c-124">The API key for the server.</span></span>

- **`-n|--no-symbols true`**

  <span data-ttu-id="0654c-125">Überträgt keine Symbole (selbst wenn vorhanden).</span><span class="sxs-lookup"><span data-stu-id="0654c-125">Doesn't push symbols (even if present).</span></span>

- **`--no-service-endpoint`**

  <span data-ttu-id="0654c-126">Fügt „api/v2/package“ nicht der Quell-URL an.</span><span class="sxs-lookup"><span data-stu-id="0654c-126">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="0654c-127">Die Option ist seit dem .NET Core 2.1 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0654c-127">Option available since .NET Core 2.1 SDK.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="0654c-128">Gibt die Server-URL an.</span><span class="sxs-lookup"><span data-stu-id="0654c-128">Specifies the server URL.</span></span> <span data-ttu-id="0654c-129">NuGet identifiziert eine UNC oder lokale Ordnerquelle und kopiert die Datei dorthin, anstatt sie mithilfe von HTTP zu pushen.</span><span class="sxs-lookup"><span data-stu-id="0654c-129">NuGet identifies a UNC or local folder source and simply copies the file there instead of pushing it using HTTP.</span></span>
  > [!IMPORTANT]
  > <span data-ttu-id="0654c-130">Ab NuGet 3.4.2 handelt es sich hierbei um einen obligatorischen Parameter, außer in der NuGet-Konfigurationsdatei wird ein `DefaultPushSource`-Wert angegeben.</span><span class="sxs-lookup"><span data-stu-id="0654c-130">Starting with NuGet 3.4.2, this is a mandatory parameter unless the NuGet config file specifies a `DefaultPushSource` value.</span></span> <span data-ttu-id="0654c-131">Weitere Informationen finden Sie unter [Konfigurieren des NuGet-Verhaltens](/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="0654c-131">For more information, see [Configuring NuGet behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`--skip-duplicate`**

  <span data-ttu-id="0654c-132">Wenn Sie mehrere Pakete per Push an einen HTTP(S)-Server senden, werden alle Antworten des Typs „409 (Konflikt)“ als Warnung behandelt, sodass der Pushvorgang fortgesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0654c-132">When pushing multiple packages to an HTTP(S) server, treats any 409 Conflict response as a warning so that the push can continue.</span></span> <span data-ttu-id="0654c-133">Verfügbar seit .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="0654c-133">Available since .NET Core 3.1 SDK.</span></span>

- **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="0654c-134">Der API-Schlüssel für den Symbolserver.</span><span class="sxs-lookup"><span data-stu-id="0654c-134">The API key for the symbol server.</span></span>

- **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="0654c-135">Gibt die Symbolserver-URL an.</span><span class="sxs-lookup"><span data-stu-id="0654c-135">Specifies the symbol server URL.</span></span>

- **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="0654c-136">Gibt das Timeout für die Übertragung auf einen Server in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="0654c-136">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="0654c-137">Der Standardwert ist 300 Sekunden (5 Minuten).</span><span class="sxs-lookup"><span data-stu-id="0654c-137">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="0654c-138">Wenn 0 (null Sekunden) angegeben wird, gilt der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="0654c-138">Specifying 0 (zero seconds) applies the default value.</span></span>

## <a name="examples"></a><span data-ttu-id="0654c-139">Beispiele</span><span class="sxs-lookup"><span data-stu-id="0654c-139">Examples</span></span>

- <span data-ttu-id="0654c-140">Pusht *foo.nupkg* mithilfe eines API-Schlüssels an die in der NuGet-Konfigurationsdatei angegebene Standardpushquelle:</span><span class="sxs-lookup"><span data-stu-id="0654c-140">Push *foo.nupkg* to the default push source specified in the NuGet config file, using an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

- <span data-ttu-id="0654c-141">Überträgt *foo.nupkg* an den offiziellen NuGet-Server und gibt einen API-Schlüssel an:</span><span class="sxs-lookup"><span data-stu-id="0654c-141">Push *foo.nupkg* to the official NuGet server, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://api.nuget.org/v3/index.json
  ```
  
  * <span data-ttu-id="0654c-142">Überträgt *foo.nupkg* an die benutzerdefinierte Pushquelle `https://customsource` und gibt einen API-Schlüssel an:</span><span class="sxs-lookup"><span data-stu-id="0654c-142">Push *foo.nupkg* to the custom push source `https://customsource`, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

- <span data-ttu-id="0654c-143">Pusht *foo.nupkg* an die in der NuGet-Konfigurationsdatei angegebene Standardpushquelle:</span><span class="sxs-lookup"><span data-stu-id="0654c-143">Push *foo.nupkg* to the default push source specified in the NuGet config file:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg
  ```

- <span data-ttu-id="0654c-144">Pusht *foo.symbols.nupkg* an die Standardsymbolquelle:</span><span class="sxs-lookup"><span data-stu-id="0654c-144">Push *foo.symbols.nupkg* to the default symbols source:</span></span>

  ```dotnetcli
  dotnet nuget push foo.symbols.nupkg
  ```

- <span data-ttu-id="0654c-145">Pusht *foo.nupkg* an die in der NuGet-Konfigurationsdatei angegebene Standardpushquelle, mit einem Timeout von 360 Sekunden:</span><span class="sxs-lookup"><span data-stu-id="0654c-145">Push *foo.nupkg* to the default push source specified in the NuGet config file, with a 360-second timeout:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg --timeout 360
  ```

- <span data-ttu-id="0654c-146">Pusht alle *NUPKG*-Dateien im aktuellen Verzeichnis an die in der NuGet-Konfigurationsdatei angegebene Standardpushquelle:</span><span class="sxs-lookup"><span data-stu-id="0654c-146">Push all *.nupkg* files in the current directory to the default push source specified in the NuGet config file:</span></span>

  ```dotnetcli
  dotnet nuget push "*.nupkg"
  ```

  > [!NOTE]
  > <span data-ttu-id="0654c-147">Wenn dieser Befehl nicht funktioniert, kann dies an einem Fehler aus früheren Versionen des SDK liegen (.NET Core 2.1 SDK und frühere Versionen).</span><span class="sxs-lookup"><span data-stu-id="0654c-147">If this command doesn't work, it might be due to a bug that existed in older versions of the SDK (.NET Core 2.1 SDK and earlier versions).</span></span>
  > <span data-ttu-id="0654c-148">Führen Sie ein Upgrade für das SDK durch, oder führen Sie stattdessen den folgenden Befehl aus, um diesen Fehler zu beheben: `dotnet nuget push "**/*.nupkg"`.</span><span class="sxs-lookup"><span data-stu-id="0654c-148">To fix this, upgrade your SDK version or run the following command instead: `dotnet nuget push "**/*.nupkg"`</span></span>
  
  > [!NOTE]
  > <span data-ttu-id="0654c-149">Die einschließenden Anführungszeichen sind für Shells wie Bash erforderlich, die Dateiglobbing ausführen.</span><span class="sxs-lookup"><span data-stu-id="0654c-149">The enclosing quotes are required for shells such as bash that perform file globbing.</span></span> <span data-ttu-id="0654c-150">Weitere Informationen finden Sie unter [NuGet/Home#4393](https://github.com/NuGet/Home/issues/4393#issuecomment-667618120).</span><span class="sxs-lookup"><span data-stu-id="0654c-150">For more information, see [NuGet/Home#4393](https://github.com/NuGet/Home/issues/4393#issuecomment-667618120).</span></span>

- <span data-ttu-id="0654c-151">Pushen Sie alle *.nupkg*-Dateien an die in der NuGet-Konfigurationsdateien angegebene Standardpushquelle, auch wenn von einem HTTP(S)-Server eine Antwort des Typs „409 (Konflikt)“ zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="0654c-151">Push all *.nupkg* files to the default push source specified in the NuGet config file, even if a 409 Conflict response is returned by an HTTP(S) server:</span></span>

  ```dotnetcli
  dotnet nuget push "*.nupkg" --skip-duplicate
  ```

- <span data-ttu-id="0654c-152">Pushen Sie alle *NUPKG*-Dateien im aktuellen Verzeichnis an ein lokales Feedverzeichnis:</span><span class="sxs-lookup"><span data-stu-id="0654c-152">Push all *.nupkg* files in the current directory to a local feed directory:</span></span>

  ```dotnetcli
  dotnet nuget push "*.nupkg" -s c:\mydir
  ```

  <span data-ttu-id="0654c-153">Dieser Befehl speichert Pakete nicht in einer hierarchischen Ordnerstruktur, um die Leistung zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="0654c-153">This command doesn't store packages in a hierarchical folder structure, which is recommended to optimize performance.</span></span> <span data-ttu-id="0654c-154">Weitere Informationen finden Sie im Artikel zu [lokalen Feeds](/nuget/hosting-packages/local-feeds).</span><span class="sxs-lookup"><span data-stu-id="0654c-154">For more information, see [Local feeds](/nuget/hosting-packages/local-feeds).</span></span>  
