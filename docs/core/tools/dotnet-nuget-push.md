---
title: Befehl „dotnet nuget push“
description: Der dotnet nuget push-Befehl überträgt ein Paket auf den Server und veröffentlicht es.
author: karann-msft
ms.date: 12/04/2019
ms.openlocfilehash: a483c559dee8b4a82cc2c792f5c2c5e4a8ff3f87
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733109"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="bae44-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="bae44-103">dotnet nuget push</span></span>

<span data-ttu-id="bae44-104">**Dieser Artikel gilt für:** ✔️ .NET Core 1.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="bae44-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="bae44-105">name</span><span class="sxs-lookup"><span data-stu-id="bae44-105">Name</span></span>

<span data-ttu-id="bae44-106">`dotnet nuget push` – Überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="bae44-106">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="bae44-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="bae44-107">Synopsis</span></span>

```dotnetcli
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [--interactive] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [--skip-duplicate] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```

## <a name="description"></a><span data-ttu-id="bae44-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bae44-108">Description</span></span>

<span data-ttu-id="bae44-109">Der `dotnet nuget push`-Befehl überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="bae44-109">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="bae44-110">Der Pushbefehl verwendet Details zum Server und den Anmeldeinformationen aus der NuGet-Konfigurationsdatei oder der Kette von Konfigurationsdateien des Systems.</span><span class="sxs-lookup"><span data-stu-id="bae44-110">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="bae44-111">Weitere Informationen zu Konfigurationsdateien finden Sie unter [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Konfigurieren des Verhaltens von NuGet).</span><span class="sxs-lookup"><span data-stu-id="bae44-111">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="bae44-112">Die NuGet-Standardkonfiguration wird abgerufen, indem *%AppData%\NuGet\NuGet.config* (Windows) oder *$HOME/.local/share* (Linux/macOS) geladen wird. Anschließend wird eine beliebige Datei *nuget.config* oder *.nuget\nuget.config* geladen (beginnend mit dem Stamm des Laufwerks und endend im aktuellen Verzeichnis).</span><span class="sxs-lookup"><span data-stu-id="bae44-112">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="bae44-113">Argumente</span><span class="sxs-lookup"><span data-stu-id="bae44-113">Arguments</span></span>

* **`ROOT`**

  <span data-ttu-id="bae44-114">Gibt den Dateipfad des Pakets an, das per Push übertragen werden soll.</span><span class="sxs-lookup"><span data-stu-id="bae44-114">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="bae44-115">Optionen</span><span class="sxs-lookup"><span data-stu-id="bae44-115">Options</span></span>

* **`-d|--disable-buffering`**

  <span data-ttu-id="bae44-116">Deaktiviert die Pufferung bei Übertragungen an HTTP(S)-Server, um die Speicherauslastung zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="bae44-116">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

* **`--force-english-output`**

  <span data-ttu-id="bae44-117">Erzwingt die Ausführung der Anwendung mithilfe einer invarianten Kultur, die auf Englisch basiert.</span><span class="sxs-lookup"><span data-stu-id="bae44-117">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="bae44-118">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="bae44-118">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="bae44-119">Ermöglicht, den Befehl zu blockieren, und fordert für Vorgänge wie z.B. die Authentifizierung eine manuelle Aktion.</span><span class="sxs-lookup"><span data-stu-id="bae44-119">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="bae44-120">Die Option ist seit dem .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bae44-120">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="bae44-121">Der API-Schlüssel für den Server.</span><span class="sxs-lookup"><span data-stu-id="bae44-121">The API key for the server.</span></span>

* **`-n|--no-symbols`**

  <span data-ttu-id="bae44-122">Überträgt keine Symbole (selbst wenn vorhanden).</span><span class="sxs-lookup"><span data-stu-id="bae44-122">Doesn't push symbols (even if present).</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="bae44-123">Fügt „api/v2/package“ nicht der Quell-URL an.</span><span class="sxs-lookup"><span data-stu-id="bae44-123">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="bae44-124">Die Option ist seit dem .NET Core 2.1 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bae44-124">Option available since .NET Core 2.1 SDK.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="bae44-125">Gibt die Server-URL an.</span><span class="sxs-lookup"><span data-stu-id="bae44-125">Specifies the server URL.</span></span> <span data-ttu-id="bae44-126">Diese Option ist erforderlich, es sei denn, der `DefaultPushSource`-Konfigurationswert wurde in der NuGet-Konfigurationsdatei festgelegt.</span><span class="sxs-lookup"><span data-stu-id="bae44-126">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

* **`--skip-duplicate`**

  <span data-ttu-id="bae44-127">Wenn Sie mehrere Pakete per Push an einen HTTP(S)-Server senden, werden alle Antworten des Typs „409 (Konflikt)“ als Warnung behandelt, sodass der Pushvorgang fortgesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="bae44-127">When pushing multiple packages to an HTTP(S) server, treats any 409 Conflict response as a warning so that the push can continue.</span></span> <span data-ttu-id="bae44-128">Verfügbar seit .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="bae44-128">Available since .NET Core 3.1 SDK.</span></span>

* **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="bae44-129">Der API-Schlüssel für den Symbolserver.</span><span class="sxs-lookup"><span data-stu-id="bae44-129">The API key for the symbol server.</span></span>

* **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="bae44-130">Gibt die Symbolserver-URL an.</span><span class="sxs-lookup"><span data-stu-id="bae44-130">Specifies the symbol server URL.</span></span>

* **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="bae44-131">Gibt das Timeout für die Übertragung auf einen Server in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="bae44-131">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="bae44-132">Der Standardwert ist 300 Sekunden (5 Minuten).</span><span class="sxs-lookup"><span data-stu-id="bae44-132">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="bae44-133">Wenn 0 (null Sekunden) angegeben wird, gilt der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="bae44-133">Specifying 0 (zero seconds) applies the default value.</span></span>

## <a name="examples"></a><span data-ttu-id="bae44-134">Beispiele</span><span class="sxs-lookup"><span data-stu-id="bae44-134">Examples</span></span>

* <span data-ttu-id="bae44-135">Überträgt *foo.nupkg* an die Standardpushquelle und gibt einen API-Schlüssel an:</span><span class="sxs-lookup"><span data-stu-id="bae44-135">Pushes *foo.nupkg* to the default push source, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

* <span data-ttu-id="bae44-136">Überträgt *foo.nupkg* an die benutzerdefinierte Pushquelle `https://customsource` und gibt einen API-Schlüssel an:</span><span class="sxs-lookup"><span data-stu-id="bae44-136">Push *foo.nupkg* to the custom push source `https://customsource`, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

* <span data-ttu-id="bae44-137">Überträgt *foo.nupkg* an die standardmäßige Pushquelle:</span><span class="sxs-lookup"><span data-stu-id="bae44-137">Pushes *foo.nupkg* to the default push source:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg
  ```

* <span data-ttu-id="bae44-138">Überträgt *foo.symbols.nupkg* an die standardmäßige Symbolquelle:</span><span class="sxs-lookup"><span data-stu-id="bae44-138">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

  ```dotnetcli
  dotnet nuget push foo.symbols.nupkg
  ```

* <span data-ttu-id="bae44-139">Überträgt *foo.nupkg* an die Standardpushquelle und gibt ein Timeout von 360 Sekunden an:</span><span class="sxs-lookup"><span data-stu-id="bae44-139">Pushes *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg --timeout 360
  ```

* <span data-ttu-id="bae44-140">Überträgt alle *NUPKG*-Dateien im aktuellen Verzeichnis an die standardmäßige Pushquelle:</span><span class="sxs-lookup"><span data-stu-id="bae44-140">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

  ```dotnetcli
  dotnet nuget push *.nupkg
  ```

  > [!NOTE]
  > <span data-ttu-id="bae44-141">Wenn dieser Befehl nicht funktioniert, kann dies an einem Fehler aus früheren Versionen des SDK liegen (.NET Core 2.1 SDK und frühere Versionen).</span><span class="sxs-lookup"><span data-stu-id="bae44-141">If this command doesn't work, it might be due to a bug that existed in older versions of the SDK (.NET Core 2.1 SDK and earlier versions).</span></span>
  > <span data-ttu-id="bae44-142">Führen Sie ein Upgrade für das SDK durch, oder führen Sie stattdessen den folgenden Befehl aus, um diesen Fehler zu beheben: `dotnet nuget push **/*.nupkg`.</span><span class="sxs-lookup"><span data-stu-id="bae44-142">To fix this, upgrade your SDK version or run the following command instead: `dotnet nuget push **/*.nupkg`</span></span>

* <span data-ttu-id="bae44-143">Überträgt alle *.nupkg*-Dateien per Push, auch wenn eine Antwort des Typs „409 (Konflikt)“ von einem HTTP(S)-Server zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="bae44-143">Pushes all *.nupkg* files even if a 409 Conflict response is returned by an HTTP(S) server:</span></span>

  ```dotnetcli
  dotnet nuget push *.nupkg --skip-duplicate
  ```
