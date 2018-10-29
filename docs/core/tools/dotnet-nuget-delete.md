---
title: dotnet nuget delete-Befehl – .NET Core-CLI
description: Der dotnet-nuget-delete-Befehl löscht ein Paket vom Server oder hebt dessen Auflistung auf.
author: karann-msft
ms.author: mairaw
ms.date: 06/01/2018
ms.openlocfilehash: f4aa027a465c4adea1de13853063d03e8e295411
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180878"
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="87c5c-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="87c5c-103">dotnet nuget delete</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="87c5c-104">name</span><span class="sxs-lookup"><span data-stu-id="87c5c-104">Name</span></span>

<span data-ttu-id="87c5c-105">`dotnet nuget delete` – Löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="87c5c-105">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="87c5c-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="87c5c-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="87c5c-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="87c5c-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="87c5c-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="87c5c-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="87c5c-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="87c5c-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="87c5c-110">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="87c5c-110">Description</span></span>

<span data-ttu-id="87c5c-111">Der `dotnet nuget delete`-Befehl löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="87c5c-111">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="87c5c-112">Für [nuget.org](https://www.nuget.org/) wird die Auflistung des Pakets aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="87c5c-112">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="87c5c-113">Argumente</span><span class="sxs-lookup"><span data-stu-id="87c5c-113">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="87c5c-114">Name/ID des zu löschenden Pakets.</span><span class="sxs-lookup"><span data-stu-id="87c5c-114">Name/ID of the package to delete.</span></span>

`PACKAGE_VERSION`

<span data-ttu-id="87c5c-115">Version des zu löschenden Pakets.</span><span class="sxs-lookup"><span data-stu-id="87c5c-115">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="87c5c-116">Optionen</span><span class="sxs-lookup"><span data-stu-id="87c5c-116">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="87c5c-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="87c5c-117">.NET Core 2.1</span></span>](#tab/netcore21)

`--force-english-output`

 <span data-ttu-id="87c5c-118">Erzwingt die Ausführung der Anwendung mithilfe einer invarianten Kultur, die auf Englisch basiert.</span><span class="sxs-lookup"><span data-stu-id="87c5c-118">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="87c5c-119">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="87c5c-119">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="87c5c-120">Der API-Schlüssel für den Server.</span><span class="sxs-lookup"><span data-stu-id="87c5c-120">The API key for the server.</span></span>

<span data-ttu-id="87c5c-121">`--no-service-endpoint` fügt „api/v2/package“ nicht der Quell-URL an.fügen</span><span class="sxs-lookup"><span data-stu-id="87c5c-121">`--no-service-endpoint` Doesn't append "api/v2/package" to the source URL.</span></span>

`--non-interactive`

<span data-ttu-id="87c5c-122">Fordert nicht zu Eingaben oder Bestätigungen des Benutzers auf.</span><span class="sxs-lookup"><span data-stu-id="87c5c-122">Doesn't prompt for user input or confirmations.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="87c5c-123">Gibt die Server-URL an.</span><span class="sxs-lookup"><span data-stu-id="87c5c-123">Specifies the server URL.</span></span> <span data-ttu-id="87c5c-124">Unterstützte URLs für „nuget.org“ sind u.a. `https://www.nuget.org`, `https://www.nuget.org/api/v3` und `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="87c5c-124">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="87c5c-125">Ersetzen Sie für private Feeds den Hostnamen (z.B. `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="87c5c-125">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="87c5c-126">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="87c5c-126">.NET Core 2.0</span></span>](#tab/netcore20)

`--force-english-output`

 <span data-ttu-id="87c5c-127">Erzwingt die Ausführung der Anwendung mithilfe einer invarianten Kultur, die auf Englisch basiert.</span><span class="sxs-lookup"><span data-stu-id="87c5c-127">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="87c5c-128">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="87c5c-128">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="87c5c-129">Der API-Schlüssel für den Server.</span><span class="sxs-lookup"><span data-stu-id="87c5c-129">The API key for the server.</span></span>

`--non-interactive`

<span data-ttu-id="87c5c-130">Fordert nicht zu Eingaben oder Bestätigungen des Benutzers auf.</span><span class="sxs-lookup"><span data-stu-id="87c5c-130">Doesn't prompt for user input or confirmations.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="87c5c-131">Gibt die Server-URL an.</span><span class="sxs-lookup"><span data-stu-id="87c5c-131">Specifies the server URL.</span></span> <span data-ttu-id="87c5c-132">Unterstützte URLs für „nuget.org“ sind u.a. `https://www.nuget.org`, `https://www.nuget.org/api/v3` und `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="87c5c-132">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="87c5c-133">Ersetzen Sie für private Feeds den Hostnamen (z.B. `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="87c5c-133">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="87c5c-134">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="87c5c-134">.NET Core 1.x</span></span>](#tab/netcore1x)

`--force-english-output`

 <span data-ttu-id="87c5c-135">Erzwingt die Ausführung der Anwendung mithilfe einer invarianten Kultur, die auf Englisch basiert.</span><span class="sxs-lookup"><span data-stu-id="87c5c-135">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="87c5c-136">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="87c5c-136">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="87c5c-137">Der API-Schlüssel für den Server.</span><span class="sxs-lookup"><span data-stu-id="87c5c-137">The API key for the server.</span></span>

`--non-interactive`

<span data-ttu-id="87c5c-138">Fordert nicht zu Eingaben oder Bestätigungen des Benutzers auf.</span><span class="sxs-lookup"><span data-stu-id="87c5c-138">Doesn't prompt for user input or confirmations.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="87c5c-139">Gibt die Server-URL an.</span><span class="sxs-lookup"><span data-stu-id="87c5c-139">Specifies the server URL.</span></span> <span data-ttu-id="87c5c-140">Unterstützte URLs für „nuget.org“ sind u.a. `https://www.nuget.org`, `https://www.nuget.org/api/v3` und `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="87c5c-140">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="87c5c-141">Ersetzen Sie für private Feeds den Hostnamen (z.B. `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="87c5c-141">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

---

## <a name="examples"></a><span data-ttu-id="87c5c-142">Beispiele</span><span class="sxs-lookup"><span data-stu-id="87c5c-142">Examples</span></span>

<span data-ttu-id="87c5c-143">Löscht Version 1.0 des Pakets `Microsoft.AspNetCore.Mvc`:</span><span class="sxs-lookup"><span data-stu-id="87c5c-143">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0`

<span data-ttu-id="87c5c-144">Löscht Version 1.0 des Pakets `Microsoft.AspNetCore.Mvc`, wobei der Benutzer nicht zur Eingabe von Anmeldeinformationen oder zu anderen Eingaben aufgefordert wird:</span><span class="sxs-lookup"><span data-stu-id="87c5c-144">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`
