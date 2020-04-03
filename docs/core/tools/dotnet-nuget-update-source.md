---
title: Befehl „dotnet nuget update source“
description: Mit dem Befehl „dotnet nuget update source“ wird eine vorhandene Quelle in Ihren NuGet-Konfigurationsdateien aktualisiert.
ms.date: 03/20/2020
ms.openlocfilehash: 38335e07f91850756c7671413e1193c2578e7e7e
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148471"
---
# <a name="dotnet-nuget-update-source"></a><span data-ttu-id="8168c-103">dotnet nuget update source</span><span class="sxs-lookup"><span data-stu-id="8168c-103">dotnet nuget update source</span></span>

<span data-ttu-id="8168c-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.1.200 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="8168c-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="8168c-105">name</span><span class="sxs-lookup"><span data-stu-id="8168c-105">Name</span></span>

<span data-ttu-id="8168c-106">`dotnet nuget update source`: Aktualisieren einer NuGet-Quelle.</span><span class="sxs-lookup"><span data-stu-id="8168c-106">`dotnet nuget update source` - Update a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8168c-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="8168c-107">Synopsis</span></span>

```dotnetcli
dotnet nuget update source <NAME> [--source] [--username]
    [--password] [--store-password-in-clear-text] [--valid-authentication-types]
    [--configfile]
dotnet nuget update source [-h|--help]
```

## <a name="description"></a><span data-ttu-id="8168c-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8168c-108">Description</span></span>

<span data-ttu-id="8168c-109">Mit dem Befehl `dotnet nuget update source` wird eine vorhandene Quelle in Ihren NuGet-Konfigurationsdateien aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="8168c-109">The `dotnet nuget update source` command updates an existing source in your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="8168c-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="8168c-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="8168c-111">Name der Quelle.</span><span class="sxs-lookup"><span data-stu-id="8168c-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="8168c-112">Optionen</span><span class="sxs-lookup"><span data-stu-id="8168c-112">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="8168c-113">Die NuGet-Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="8168c-113">The NuGet configuration file.</span></span> <span data-ttu-id="8168c-114">Sofern angegeben, werden nur die Einstellungen aus dieser Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="8168c-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="8168c-115">Falls nicht angegeben, wird die Hierarchie der Konfigurationsdateien aus dem aktuellen Verzeichnis verwendet.</span><span class="sxs-lookup"><span data-stu-id="8168c-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="8168c-116">Weitere Informationen finden Sie unter [Gängige NuGet-Konfigurationen](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="8168c-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`-p|--password`**

  <span data-ttu-id="8168c-117">Das bei der Verbindungsherstellung mit einer authentifizierten Quelle zu verwendende Kennwort.</span><span class="sxs-lookup"><span data-stu-id="8168c-117">Password to be used when connecting to an authenticated source.</span></span>

- **`-s|--source`**

  <span data-ttu-id="8168c-118">Pfad zur Paketquelle.</span><span class="sxs-lookup"><span data-stu-id="8168c-118">Path to the package source.</span></span>

- **`--store-password-in-clear-text`**

  <span data-ttu-id="8168c-119">Ermöglicht das Speichern von Anmeldeinformationen für portierbare Paketquellen durch Deaktivieren der Kennwortverschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="8168c-119">Enables storing portable package source credentials by disabling password encryption.</span></span>

- **`-u|--username`**

  <span data-ttu-id="8168c-120">Der bei der Verbindungsherstellung mit einer authentifizierten Quelle zu verwendende Benutzername.</span><span class="sxs-lookup"><span data-stu-id="8168c-120">Username to be used when connecting to an authenticated source.</span></span>

- **`--valid-authentication-types`**

  <span data-ttu-id="8168c-121">Durch Trennzeichen getrennte Liste mit gültigen Authentifizierungstypen für diese Quelle.</span><span class="sxs-lookup"><span data-stu-id="8168c-121">Comma-separated list of valid authentication types for this source.</span></span> <span data-ttu-id="8168c-122">Legen Sie diese Option auf `basic` fest, wenn der Server NTLM oder eine Aushandlung ankündigt und Ihre Anmeldedaten über den Basismechanismus gesendet werden müssen, z. B. bei Verwendung eines persönlichen Zugriffstokens (PAT) mit einer lokalen Azure DevOps Server-Instanz.</span><span class="sxs-lookup"><span data-stu-id="8168c-122">Set this to `basic` if the server advertises NTLM or Negotiate and your credentials must be sent using the Basic mechanism, for instance when using a PAT with on-premises Azure DevOps Server.</span></span> <span data-ttu-id="8168c-123">Andere gültige Werte sind `negotiate`, `kerberos`, `ntlm` und `digest`, aber diese Werte sind wahrscheinlich nicht sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="8168c-123">Other valid values include `negotiate`, `kerberos`, `ntlm`, and `digest`, but these values are unlikely to be useful.</span></span>

## <a name="examples"></a><span data-ttu-id="8168c-124">Beispiele</span><span class="sxs-lookup"><span data-stu-id="8168c-124">Examples</span></span>

- <span data-ttu-id="8168c-125">Aktualisieren einer Quelle mit dem Namen `mySource`:</span><span class="sxs-lookup"><span data-stu-id="8168c-125">Update a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget update source mySource --source c:\packages
  ```

## <a name="see-also"></a><span data-ttu-id="8168c-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8168c-126">See also</span></span>

- [<span data-ttu-id="8168c-127">Paketquellenabschnitte in NuGet.config-Dateien</span><span class="sxs-lookup"><span data-stu-id="8168c-127">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="8168c-128">Befehl „sources“ (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="8168c-128">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
