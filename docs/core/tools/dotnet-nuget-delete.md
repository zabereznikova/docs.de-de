---
title: Befehl „dotnet nuget delete“
description: Der Befehl „dotnet nuget delete“ löscht ein Paket vom Server oder hebt dessen Auflistung auf.
author: karann-msft
ms.date: 12/04/2018
ms.openlocfilehash: 827d295d7a52b6c9c82adbcf3d25281bd1cc98fd
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168311"
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="f7b36-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="f7b36-103">dotnet nuget delete</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="f7b36-104">Name</span><span class="sxs-lookup"><span data-stu-id="f7b36-104">Name</span></span>

<span data-ttu-id="f7b36-105">`dotnet nuget delete` – Löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="f7b36-105">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f7b36-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="f7b36-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="f7b36-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="f7b36-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [--interactive] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f7b36-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f7b36-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="f7b36-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f7b36-109">Description</span></span>

<span data-ttu-id="f7b36-110">Der `dotnet nuget delete`-Befehl löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="f7b36-110">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="f7b36-111">Für [nuget.org](https://www.nuget.org/) wird die Auflistung des Pakets aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="f7b36-111">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="f7b36-112">Argumente</span><span class="sxs-lookup"><span data-stu-id="f7b36-112">Arguments</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="f7b36-113">Name/ID des zu löschenden Pakets.</span><span class="sxs-lookup"><span data-stu-id="f7b36-113">Name/ID of the package to delete.</span></span>

* **`PACKAGE_VERSION`**

  <span data-ttu-id="f7b36-114">Version des zu löschenden Pakets.</span><span class="sxs-lookup"><span data-stu-id="f7b36-114">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="f7b36-115">Optionen</span><span class="sxs-lookup"><span data-stu-id="f7b36-115">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="f7b36-116">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="f7b36-116">.NET Core 2.x</span></span>](#tab/netcore2x)

* **`--force-english-output`**

  <span data-ttu-id="f7b36-117">Erzwingt die Ausführung der Anwendung mithilfe einer invarianten Kultur, die auf Englisch basiert.</span><span class="sxs-lookup"><span data-stu-id="f7b36-117">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="f7b36-118">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="f7b36-118">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="f7b36-119">Ermöglicht, den Befehl zu blockieren, und fordert für Vorgänge wie z.B. die Authentifizierung eine manuelle Aktion.</span><span class="sxs-lookup"><span data-stu-id="f7b36-119">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="f7b36-120">Die Option ist seit dem .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f7b36-120">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="f7b36-121">Der API-Schlüssel für den Server.</span><span class="sxs-lookup"><span data-stu-id="f7b36-121">The API key for the server.</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="f7b36-122">Fügt „api/v2/package“ nicht der Quell-URL an.</span><span class="sxs-lookup"><span data-stu-id="f7b36-122">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="f7b36-123">Die Option ist seit dem .NET Core 2.1 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f7b36-123">Option available since .NET Core 2.1 SDK.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="f7b36-124">Fordert nicht zu Eingaben oder Bestätigungen des Benutzers auf.</span><span class="sxs-lookup"><span data-stu-id="f7b36-124">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="f7b36-125">Gibt die Server-URL an.</span><span class="sxs-lookup"><span data-stu-id="f7b36-125">Specifies the server URL.</span></span> <span data-ttu-id="f7b36-126">Unterstützte URLs für „nuget.org“ sind u.a. `https://www.nuget.org`, `https://www.nuget.org/api/v3` und `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="f7b36-126">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="f7b36-127">Ersetzen Sie für private Feeds den Hostnamen (z.B. `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="f7b36-127">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f7b36-128">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f7b36-128">.NET Core 1.x</span></span>](#tab/netcore1x)

* **`--force-english-output`**

  <span data-ttu-id="f7b36-129">Erzwingt die Ausführung der Anwendung mithilfe einer invarianten Kultur, die auf Englisch basiert.</span><span class="sxs-lookup"><span data-stu-id="f7b36-129">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="f7b36-130">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="f7b36-130">Prints out a short help for the command.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="f7b36-131">Der API-Schlüssel für den Server.</span><span class="sxs-lookup"><span data-stu-id="f7b36-131">The API key for the server.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="f7b36-132">Fordert nicht zu Eingaben oder Bestätigungen des Benutzers auf.</span><span class="sxs-lookup"><span data-stu-id="f7b36-132">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="f7b36-133">Gibt die Server-URL an.</span><span class="sxs-lookup"><span data-stu-id="f7b36-133">Specifies the server URL.</span></span> <span data-ttu-id="f7b36-134">Unterstützte URLs für „nuget.org“ sind u.a. `https://www.nuget.org`, `https://www.nuget.org/api/v3` und `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="f7b36-134">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="f7b36-135">Ersetzen Sie für private Feeds den Hostnamen (z.B. `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="f7b36-135">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

---

## <a name="examples"></a><span data-ttu-id="f7b36-136">Beispiele</span><span class="sxs-lookup"><span data-stu-id="f7b36-136">Examples</span></span>

* <span data-ttu-id="f7b36-137">Löscht Version 1.0 des Pakets `Microsoft.AspNetCore.Mvc`:</span><span class="sxs-lookup"><span data-stu-id="f7b36-137">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* <span data-ttu-id="f7b36-138">Löscht Version 1.0 des Pakets `Microsoft.AspNetCore.Mvc`, wobei der Benutzer nicht zur Eingabe von Anmeldeinformationen oder zu anderen Eingaben aufgefordert wird:</span><span class="sxs-lookup"><span data-stu-id="f7b36-138">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```