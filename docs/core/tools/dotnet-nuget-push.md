---
title: dotnet nuget push-Befehl – .NET Core-CLI
description: Der dotnet nuget push-Befehl überträgt ein Paket auf den Server und veröffentlicht es.
author: karann-msft
ms.date: 12/04/2018
ms.openlocfilehash: 090dbfbe3db83b2bb234867aed295ac416b27865
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143060"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="0d968-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="0d968-103">dotnet nuget push</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="0d968-104">name</span><span class="sxs-lookup"><span data-stu-id="0d968-104">Name</span></span>

<span data-ttu-id="0d968-105">`dotnet nuget push` – Überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="0d968-105">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0d968-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="0d968-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="0d968-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="0d968-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [--interactive] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0d968-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0d968-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="0d968-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0d968-109">Description</span></span>

<span data-ttu-id="0d968-110">Der `dotnet nuget push`-Befehl überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="0d968-110">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="0d968-111">Der Pushbefehl verwendet Details zum Server und den Anmeldeinformationen aus der NuGet-Konfigurationsdatei oder der Kette von Konfigurationsdateien des Systems.</span><span class="sxs-lookup"><span data-stu-id="0d968-111">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="0d968-112">Weitere Informationen zu Konfigurationsdateien finden Sie unter [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Konfigurieren des Verhaltens von NuGet).</span><span class="sxs-lookup"><span data-stu-id="0d968-112">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="0d968-113">Die NuGet-Standardkonfiguration wird abgerufen, indem *%AppData%\NuGet\NuGet.config* (Windows) oder *$HOME/.local/share* (Linux/macOS) geladen wird. Anschließend wird eine beliebige Datei *nuget.config* oder *.nuget\nuget.config* geladen (beginnend mit dem Stamm des Laufwerks und endend im aktuellen Verzeichnis).</span><span class="sxs-lookup"><span data-stu-id="0d968-113">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="0d968-114">Argumente</span><span class="sxs-lookup"><span data-stu-id="0d968-114">Arguments</span></span>

* **`ROOT`**

  <span data-ttu-id="0d968-115">Gibt den Dateipfad des Pakets an, das per Push übertragen werden soll.</span><span class="sxs-lookup"><span data-stu-id="0d968-115">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="0d968-116">Optionen</span><span class="sxs-lookup"><span data-stu-id="0d968-116">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="0d968-117">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="0d968-117">.NET Core 2.x</span></span>](#tab/netcore2x)

* **`-d|--disable-buffering`**

  <span data-ttu-id="0d968-118">Deaktiviert die Pufferung bei Übertragungen an HTTP(S)-Server, um die Speicherauslastung zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="0d968-118">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

* **`--force-english-output`**

  <span data-ttu-id="0d968-119">Erzwingt die Ausführung der Anwendung mithilfe einer invarianten Kultur, die auf Englisch basiert.</span><span class="sxs-lookup"><span data-stu-id="0d968-119">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

<span data-ttu-id="0d968-120">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="0d968-120">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="0d968-121">Ermöglicht, den Befehl zu blockieren, und fordert für Vorgänge wie z.B. die Authentifizierung eine manuelle Aktion.</span><span class="sxs-lookup"><span data-stu-id="0d968-121">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="0d968-122">Die Option ist seit dem .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0d968-122">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="0d968-123">Der API-Schlüssel für den Server.</span><span class="sxs-lookup"><span data-stu-id="0d968-123">The API key for the server.</span></span>

* **`-n|--no-symbols`**

  <span data-ttu-id="0d968-124">Überträgt keine Symbole (selbst wenn vorhanden).</span><span class="sxs-lookup"><span data-stu-id="0d968-124">Doesn't push symbols (even if present).</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="0d968-125">Fügt „api/v2/package“ nicht der Quell-URL an.</span><span class="sxs-lookup"><span data-stu-id="0d968-125">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="0d968-126">Die Option ist seit dem .NET Core 2.1 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0d968-126">Option available since .NET Core 2.1 SDK.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="0d968-127">Gibt die Server-URL an.</span><span class="sxs-lookup"><span data-stu-id="0d968-127">Specifies the server URL.</span></span> <span data-ttu-id="0d968-128">Diese Option ist erforderlich, es sei denn, der `DefaultPushSource`-Konfigurationswert wurde in der NuGet-Konfigurationsdatei festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0d968-128">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

* **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="0d968-129">Der API-Schlüssel für den Symbolserver.</span><span class="sxs-lookup"><span data-stu-id="0d968-129">The API key for the symbol server.</span></span>

* **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="0d968-130">Gibt die Symbolserver-URL an.</span><span class="sxs-lookup"><span data-stu-id="0d968-130">Specifies the symbol server URL.</span></span>

* **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="0d968-131">Gibt das Timeout für die Übertragung auf einen Server in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="0d968-131">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="0d968-132">Der Standardwert ist 300 Sekunden (5 Minuten).</span><span class="sxs-lookup"><span data-stu-id="0d968-132">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="0d968-133">Wenn 0 (null Sekunden) angegeben wird, gilt der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="0d968-133">Specifying 0 (zero seconds) applies the default value.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0d968-134">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0d968-134">.NET Core 1.x</span></span>](#tab/netcore1x)

* **`-d|--disable-buffering`**

  <span data-ttu-id="0d968-135">Deaktiviert die Pufferung bei Übertragungen an HTTP(S)-Server, um die Speicherauslastung zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="0d968-135">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

* **`--force-english-output`**

  <span data-ttu-id="0d968-136">Erzwingt die Ausführung der Anwendung mithilfe einer invarianten Kultur, die auf Englisch basiert.</span><span class="sxs-lookup"><span data-stu-id="0d968-136">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="0d968-137">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="0d968-137">Prints out a short help for the command.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="0d968-138">Der API-Schlüssel für den Server.</span><span class="sxs-lookup"><span data-stu-id="0d968-138">The API key for the server.</span></span>

* **`-n|--no-symbols`**

  <span data-ttu-id="0d968-139">Überträgt keine Symbole (selbst wenn vorhanden).</span><span class="sxs-lookup"><span data-stu-id="0d968-139">Doesn't push symbols (even if present).</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="0d968-140">Gibt die Server-URL an.</span><span class="sxs-lookup"><span data-stu-id="0d968-140">Specifies the server URL.</span></span> <span data-ttu-id="0d968-141">Diese Option ist erforderlich, es sei denn, der `DefaultPushSource`-Konfigurationswert wurde in der NuGet-Konfigurationsdatei festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0d968-141">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

* **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="0d968-142">Der API-Schlüssel für den Symbolserver.</span><span class="sxs-lookup"><span data-stu-id="0d968-142">The API key for the symbol server.</span></span>

* **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="0d968-143">Gibt die Symbolserver-URL an.</span><span class="sxs-lookup"><span data-stu-id="0d968-143">Specifies the symbol server URL.</span></span>

* **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="0d968-144">Gibt das Timeout für die Übertragung auf einen Server in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="0d968-144">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="0d968-145">Der Standardwert ist 300 Sekunden (5 Minuten).</span><span class="sxs-lookup"><span data-stu-id="0d968-145">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="0d968-146">Wenn 0 (null Sekunden) angegeben wird, gilt der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="0d968-146">Specifying 0 (zero seconds) applies the default value.</span></span>

---

## <a name="examples"></a><span data-ttu-id="0d968-147">Beispiele</span><span class="sxs-lookup"><span data-stu-id="0d968-147">Examples</span></span>

* <span data-ttu-id="0d968-148">Überträgt *foo.nupkg* an die Standardpushquelle und gibt einen API-Schlüssel an:</span><span class="sxs-lookup"><span data-stu-id="0d968-148">Pushes *foo.nupkg* to the default push source, specifying an API key:</span></span>

  ```console
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

* <span data-ttu-id="0d968-149">Überträgt *foo.nupkg* an die benutzerdefinierte Pushquelle `https://customsource` und gibt einen API-Schlüssel an:</span><span class="sxs-lookup"><span data-stu-id="0d968-149">Push *foo.nupkg* to the custom push source `https://customsource`, specifying an API key:</span></span>

  ```console
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

* <span data-ttu-id="0d968-150">Überträgt *foo.nupkg* an die standardmäßige Pushquelle:</span><span class="sxs-lookup"><span data-stu-id="0d968-150">Pushes *foo.nupkg* to the default push source:</span></span>

  ```console
  dotnet nuget push foo.nupkg
  ```

* <span data-ttu-id="0d968-151">Überträgt *foo.symbols.nupkg* an die standardmäßige Symbolquelle:</span><span class="sxs-lookup"><span data-stu-id="0d968-151">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

  ```console
  dotnet nuget push foo.symbols.nupkg
  ```

* <span data-ttu-id="0d968-152">Überträgt *foo.nupkg* an die Standardpushquelle und gibt ein Timeout von 360 Sekunden an:</span><span class="sxs-lookup"><span data-stu-id="0d968-152">Pushes *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

  ```console
  dotnet nuget push foo.nupkg --timeout 360
  ```

* <span data-ttu-id="0d968-153">Überträgt alle *NUPKG*-Dateien im aktuellen Verzeichnis an die standardmäßige Pushquelle:</span><span class="sxs-lookup"><span data-stu-id="0d968-153">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

  ```console
  dotnet nuget push *.nupkg
  ```