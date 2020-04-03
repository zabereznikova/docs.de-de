---
title: Befehl „dotnet nuget add source“
description: Mit dem Befehl „dotnet nuget add source“ wird eine neue Paketquelle zu Ihren NuGet-Konfigurationsdateien hinzugefügt.
ms.date: 03/20/2020
ms.openlocfilehash: c1e398699c7482a69b750cde718e6f9178b5c4bd
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148489"
---
# <a name="dotnet-nuget-add-source"></a><span data-ttu-id="43798-103">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="43798-103">dotnet nuget add source</span></span>

<span data-ttu-id="43798-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.1.200 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="43798-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="43798-105">name</span><span class="sxs-lookup"><span data-stu-id="43798-105">Name</span></span>

<span data-ttu-id="43798-106">`dotnet nuget add source`: Hinzufügen einer NuGet-Quelle.</span><span class="sxs-lookup"><span data-stu-id="43798-106">`dotnet nuget add source` - Add a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="43798-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="43798-107">Synopsis</span></span>

```dotnetcli
dotnet nuget add source <PACKAGE_SOURCE_PATH> [--name] [--username]
    [--password] [--store-password-in-clear-text] [--valid-authentication-types]
    [--configfile]
dotnet nuget add source [-h|--help]
```

## <a name="description"></a><span data-ttu-id="43798-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="43798-108">Description</span></span>

<span data-ttu-id="43798-109">Mit dem Befehl `dotnet nuget add source` wird eine neue Paketquelle zu Ihren NuGet-Konfigurationsdateien hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="43798-109">The `dotnet nuget add source` command adds a new package source to your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="43798-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="43798-110">Arguments</span></span>

- **`PACKAGE_SOURCE_PATH`**

  <span data-ttu-id="43798-111">Pfad zur Paketquelle.</span><span class="sxs-lookup"><span data-stu-id="43798-111">Path to the package source.</span></span>

## <a name="options"></a><span data-ttu-id="43798-112">Optionen</span><span class="sxs-lookup"><span data-stu-id="43798-112">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="43798-113">Die NuGet-Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="43798-113">The NuGet configuration file.</span></span> <span data-ttu-id="43798-114">Sofern angegeben, werden nur die Einstellungen aus dieser Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="43798-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="43798-115">Falls nicht angegeben, wird die Hierarchie der Konfigurationsdateien aus dem aktuellen Verzeichnis verwendet.</span><span class="sxs-lookup"><span data-stu-id="43798-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="43798-116">Weitere Informationen finden Sie unter [Gängige NuGet-Konfigurationen](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="43798-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`-n|--name`**

  <span data-ttu-id="43798-117">Name der Quelle.</span><span class="sxs-lookup"><span data-stu-id="43798-117">Name of the source.</span></span>

- **`-p|--password`**

  <span data-ttu-id="43798-118">Das bei der Verbindungsherstellung mit einer authentifizierten Quelle zu verwendende Kennwort.</span><span class="sxs-lookup"><span data-stu-id="43798-118">Password to be used when connecting to an authenticated source.</span></span>

- **`--store-password-in-clear-text`**

  <span data-ttu-id="43798-119">Ermöglicht das Speichern von Anmeldeinformationen für portierbare Paketquellen durch Deaktivieren der Kennwortverschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="43798-119">Enables storing portable package source credentials by disabling password encryption.</span></span>

- **`-u|--username`**

  <span data-ttu-id="43798-120">Der bei der Verbindungsherstellung mit einer authentifizierten Quelle zu verwendende Benutzername.</span><span class="sxs-lookup"><span data-stu-id="43798-120">Username to be used when connecting to an authenticated source.</span></span>

- **`--valid-authentication-types`**

  <span data-ttu-id="43798-121">Durch Trennzeichen getrennte Liste mit gültigen Authentifizierungstypen für diese Quelle.</span><span class="sxs-lookup"><span data-stu-id="43798-121">Comma-separated list of valid authentication types for this source.</span></span> <span data-ttu-id="43798-122">Legen Sie diese Option auf `basic` fest, wenn der Server NTLM oder eine Aushandlung ankündigt und Ihre Anmeldedaten über den Basismechanismus gesendet werden müssen, z. B. bei Verwendung eines persönlichen Zugriffstokens (PAT) mit einer lokalen Azure DevOps Server-Instanz.</span><span class="sxs-lookup"><span data-stu-id="43798-122">Set this to `basic` if the server advertises NTLM or Negotiate and your credentials must be sent using the Basic mechanism, for instance when using a PAT with on-premises Azure DevOps Server.</span></span> <span data-ttu-id="43798-123">Andere gültige Werte sind `negotiate`, `kerberos`, `ntlm` und `digest`, aber diese Werte sind wahrscheinlich nicht sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="43798-123">Other valid values include `negotiate`, `kerberos`, `ntlm`, and `digest`, but these values are unlikely to be useful.</span></span>

## <a name="examples"></a><span data-ttu-id="43798-124">Beispiele</span><span class="sxs-lookup"><span data-stu-id="43798-124">Examples</span></span>

- <span data-ttu-id="43798-125">`nuget.org` als Quelle hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="43798-125">Add `nuget.org` as a source:</span></span>

  ```dotnetcli
  dotnet nuget add source https://api.nuget.org/v3/index.json -n nuget.org
  ```

- <span data-ttu-id="43798-126">`c:\packages` als lokale Quelle hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="43798-126">Add `c:\packages` as a local source:</span></span>

  ```dotnetcli
  dotnet nuget add source c:\packages
  ```

- <span data-ttu-id="43798-127">Hinzufügen einer Quelle, die eine Authentifizierung erfordert:</span><span class="sxs-lookup"><span data-stu-id="43798-127">Add a source that needs authentication:</span></span>

  ```dotnetcli
  dotnet nuget add source https://someServer/myTeam -n myTeam -u myUsername -p myPassword --store-password-in-clear-text
  ```

- <span data-ttu-id="43798-128">Hinzufügen einer Quelle, die eine Authentifizierung erfordert (und anschließende Installation eines Anmeldeinformationsanbieters):</span><span class="sxs-lookup"><span data-stu-id="43798-128">Add a source that needs authentication (then go install credential provider):</span></span>

  ```dotnetcli
  dotnet nuget add source https://azureartifacts.microsoft.com/myTeam -n myTeam
  ```

## <a name="see-also"></a><span data-ttu-id="43798-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43798-129">See also</span></span>

- [<span data-ttu-id="43798-130">Paketquellenabschnitte in NuGet.config-Dateien</span><span class="sxs-lookup"><span data-stu-id="43798-130">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="43798-131">Befehl „sources“ (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="43798-131">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
