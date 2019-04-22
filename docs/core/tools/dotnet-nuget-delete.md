---
title: Befehl „dotnet nuget delete“
description: Der dotnet-nuget-delete-Befehl löscht ein Paket vom Server oder hebt dessen Auflistung auf.
author: karann-msft
ms.date: 12/04/2018
ms.openlocfilehash: a657fa273ca6b5229a1713fbcaf003217a59fd7f
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612627"
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="fd465-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="fd465-103">dotnet nuget delete</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="fd465-104">name</span><span class="sxs-lookup"><span data-stu-id="fd465-104">Name</span></span>

<span data-ttu-id="fd465-105">`dotnet nuget delete` – Löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="fd465-105">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="fd465-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="fd465-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="fd465-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="fd465-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [--interactive] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="fd465-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="fd465-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="fd465-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd465-109">Description</span></span>

<span data-ttu-id="fd465-110">Der `dotnet nuget delete`-Befehl löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="fd465-110">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="fd465-111">Für [nuget.org](https://www.nuget.org/) wird die Auflistung des Pakets aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="fd465-111">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="fd465-112">Argumente</span><span class="sxs-lookup"><span data-stu-id="fd465-112">Arguments</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="fd465-113">Name/ID des zu löschenden Pakets.</span><span class="sxs-lookup"><span data-stu-id="fd465-113">Name/ID of the package to delete.</span></span>

* **`PACKAGE_VERSION`**

  <span data-ttu-id="fd465-114">Version des zu löschenden Pakets.</span><span class="sxs-lookup"><span data-stu-id="fd465-114">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="fd465-115">Optionen</span><span class="sxs-lookup"><span data-stu-id="fd465-115">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="fd465-116">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="fd465-116">.NET Core 2.x</span></span>](#tab/netcore2x)

* **`--force-english-output`**

  <span data-ttu-id="fd465-117">Erzwingt die Ausführung der Anwendung mithilfe einer invarianten Kultur, die auf Englisch basiert.</span><span class="sxs-lookup"><span data-stu-id="fd465-117">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="fd465-118">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="fd465-118">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="fd465-119">Ermöglicht, den Befehl zu blockieren, und fordert für Vorgänge wie z.B. die Authentifizierung eine manuelle Aktion.</span><span class="sxs-lookup"><span data-stu-id="fd465-119">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="fd465-120">Die Option ist seit dem .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fd465-120">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="fd465-121">Der API-Schlüssel für den Server.</span><span class="sxs-lookup"><span data-stu-id="fd465-121">The API key for the server.</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="fd465-122">Fügt „api/v2/package“ nicht der Quell-URL an.</span><span class="sxs-lookup"><span data-stu-id="fd465-122">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="fd465-123">Die Option ist seit dem .NET Core 2.1 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fd465-123">Option available since .NET Core 2.1 SDK.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="fd465-124">Fordert nicht zu Eingaben oder Bestätigungen des Benutzers auf.</span><span class="sxs-lookup"><span data-stu-id="fd465-124">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="fd465-125">Gibt die Server-URL an.</span><span class="sxs-lookup"><span data-stu-id="fd465-125">Specifies the server URL.</span></span> <span data-ttu-id="fd465-126">Unterstützte URLs für „nuget.org“ sind u.a. `https://www.nuget.org`, `https://www.nuget.org/api/v3` und `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="fd465-126">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="fd465-127">Ersetzen Sie für private Feeds den Hostnamen (z.B. `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="fd465-127">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="fd465-128">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="fd465-128">.NET Core 1.x</span></span>](#tab/netcore1x)

* **`--force-english-output`**

  <span data-ttu-id="fd465-129">Erzwingt die Ausführung der Anwendung mithilfe einer invarianten Kultur, die auf Englisch basiert.</span><span class="sxs-lookup"><span data-stu-id="fd465-129">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="fd465-130">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="fd465-130">Prints out a short help for the command.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="fd465-131">Der API-Schlüssel für den Server.</span><span class="sxs-lookup"><span data-stu-id="fd465-131">The API key for the server.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="fd465-132">Fordert nicht zu Eingaben oder Bestätigungen des Benutzers auf.</span><span class="sxs-lookup"><span data-stu-id="fd465-132">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="fd465-133">Gibt die Server-URL an.</span><span class="sxs-lookup"><span data-stu-id="fd465-133">Specifies the server URL.</span></span> <span data-ttu-id="fd465-134">Unterstützte URLs für „nuget.org“ sind u.a. `https://www.nuget.org`, `https://www.nuget.org/api/v3` und `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="fd465-134">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="fd465-135">Ersetzen Sie für private Feeds den Hostnamen (z.B. `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="fd465-135">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

---

## <a name="examples"></a><span data-ttu-id="fd465-136">Beispiele</span><span class="sxs-lookup"><span data-stu-id="fd465-136">Examples</span></span>

* <span data-ttu-id="fd465-137">Löscht Version 1.0 des Pakets `Microsoft.AspNetCore.Mvc`:</span><span class="sxs-lookup"><span data-stu-id="fd465-137">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* <span data-ttu-id="fd465-138">Löscht Version 1.0 des Pakets `Microsoft.AspNetCore.Mvc`, wobei der Benutzer nicht zur Eingabe von Anmeldeinformationen oder zu anderen Eingaben aufgefordert wird:</span><span class="sxs-lookup"><span data-stu-id="fd465-138">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```