---
title: Befehl „dotnet nuget delete“
description: Der dotnet-nuget-delete-Befehl löscht ein Paket vom Server oder hebt dessen Auflistung auf.
author: karann-msft
ms.date: 06/26/2019
ms.openlocfilehash: 0950f03c0986bde17ae3e2e7170d402ea8222853
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "76733121"
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="4a759-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="4a759-103">dotnet nuget delete</span></span>

<span data-ttu-id="4a759-104">**Dieser Artikel gilt für:** ✔️ .NET Core 1.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="4a759-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="4a759-105">Name</span><span class="sxs-lookup"><span data-stu-id="4a759-105">Name</span></span>

<span data-ttu-id="4a759-106">`dotnet nuget delete` – Löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="4a759-106">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4a759-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="4a759-107">Synopsis</span></span>

```dotnetcli
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [--interactive] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```

## <a name="description"></a><span data-ttu-id="4a759-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4a759-108">Description</span></span>

<span data-ttu-id="4a759-109">Der `dotnet nuget delete`-Befehl löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="4a759-109">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="4a759-110">Für [nuget.org](https://www.nuget.org/) wird die Auflistung des Pakets aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="4a759-110">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="4a759-111">Argumente</span><span class="sxs-lookup"><span data-stu-id="4a759-111">Arguments</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="4a759-112">Name/ID des zu löschenden Pakets.</span><span class="sxs-lookup"><span data-stu-id="4a759-112">Name/ID of the package to delete.</span></span>

* **`PACKAGE_VERSION`**

  <span data-ttu-id="4a759-113">Version des zu löschenden Pakets.</span><span class="sxs-lookup"><span data-stu-id="4a759-113">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="4a759-114">Optionen</span><span class="sxs-lookup"><span data-stu-id="4a759-114">Options</span></span>

* **`--force-english-output`**

  <span data-ttu-id="4a759-115">Erzwingt die Ausführung der Anwendung mithilfe einer invarianten Kultur, die auf Englisch basiert.</span><span class="sxs-lookup"><span data-stu-id="4a759-115">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="4a759-116">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="4a759-116">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="4a759-117">Ermöglicht, den Befehl zu blockieren, und fordert für Vorgänge wie z.B. die Authentifizierung eine manuelle Aktion.</span><span class="sxs-lookup"><span data-stu-id="4a759-117">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="4a759-118">Die Option ist seit dem .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4a759-118">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="4a759-119">Der API-Schlüssel für den Server.</span><span class="sxs-lookup"><span data-stu-id="4a759-119">The API key for the server.</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="4a759-120">Fügt „api/v2/package“ nicht der Quell-URL an.</span><span class="sxs-lookup"><span data-stu-id="4a759-120">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="4a759-121">Die Option ist seit dem .NET Core 2.1 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4a759-121">Option available since .NET Core 2.1 SDK.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="4a759-122">Fordert nicht zu Eingaben oder Bestätigungen des Benutzers auf.</span><span class="sxs-lookup"><span data-stu-id="4a759-122">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="4a759-123">Gibt die Server-URL an.</span><span class="sxs-lookup"><span data-stu-id="4a759-123">Specifies the server URL.</span></span> <span data-ttu-id="4a759-124">Unterstützte URLs für „nuget.org“ sind u.a. `https://www.nuget.org`, `https://www.nuget.org/api/v3` und `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="4a759-124">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="4a759-125">Ersetzen Sie für private Feeds den Hostnamen (z.B. `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="4a759-125">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

## <a name="examples"></a><span data-ttu-id="4a759-126">Beispiele</span><span class="sxs-lookup"><span data-stu-id="4a759-126">Examples</span></span>

* <span data-ttu-id="4a759-127">Löscht Version 1.0 des Pakets `Microsoft.AspNetCore.Mvc`:</span><span class="sxs-lookup"><span data-stu-id="4a759-127">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

  ```dotnetcli
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* <span data-ttu-id="4a759-128">Löscht Version 1.0 des Pakets `Microsoft.AspNetCore.Mvc`, wobei der Benutzer nicht zur Eingabe von Anmeldeinformationen oder zu anderen Eingaben aufgefordert wird:</span><span class="sxs-lookup"><span data-stu-id="4a759-128">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

  ```dotnetcli
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```
