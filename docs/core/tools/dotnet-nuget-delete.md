---
title: "dotnet-nuget-delete-Befehl – .NET Core-CLI"
description: "Der dotnet-nuget-delete-Befehl löscht ein Paket vom Server oder hebt dessen Auflistung auf."
keywords: dotnet-nuget-delete, CLI, CLI-Befehl, .NET Core
author: karann-msft
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 6ddffde4-c789-4e90-990e-d35f6a6565d4
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ce6886f2f4cc8cc633cfc61215fe17550f746c91
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-nuget-delete"></a><span data-ttu-id="c6d5d-104">dotnet-nuget delete</span><span class="sxs-lookup"><span data-stu-id="c6d5d-104">dotnet-nuget delete</span></span>

## <a name="name"></a><span data-ttu-id="c6d5d-105">Name</span><span class="sxs-lookup"><span data-stu-id="c6d5d-105">Name</span></span>

<span data-ttu-id="c6d5d-106">`dotnet-nuget-delete` – Löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="c6d5d-106">`dotnet-nuget-delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c6d5d-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c6d5d-107">Synopsis</span></span>

`dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [-s|--source] [--non-interactive] [-k|--api-key] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="c6d5d-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c6d5d-108">Description</span></span>

<span data-ttu-id="c6d5d-109">Der `dotnet nuget delete`-Befehl löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="c6d5d-109">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="c6d5d-110">Für [nuget.org](https://www.nuget.org/) wird die Auflistung des Pakets aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="c6d5d-110">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="c6d5d-111">Argumente</span><span class="sxs-lookup"><span data-stu-id="c6d5d-111">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="c6d5d-112">Zu löschendes Paket.</span><span class="sxs-lookup"><span data-stu-id="c6d5d-112">Package to delete.</span></span>

`PACKAGE_VERSION`

<span data-ttu-id="c6d5d-113">Version des zu löschenden Pakets.</span><span class="sxs-lookup"><span data-stu-id="c6d5d-113">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="c6d5d-114">Optionen</span><span class="sxs-lookup"><span data-stu-id="c6d5d-114">Options</span></span>

`-h|--help`

<span data-ttu-id="c6d5d-115">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="c6d5d-115">Prints out a short help for the command.</span></span>  

`-s|--source <SOURCE>`

<span data-ttu-id="c6d5d-116">Gibt die Server-URL an.</span><span class="sxs-lookup"><span data-stu-id="c6d5d-116">Specifies the server URL.</span></span> <span data-ttu-id="c6d5d-117">Unterstützte URLs für „nuget.org“ sind u.a. `http://www.nuget.org`, `http://www.nuget.org/api/v3` und `http://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="c6d5d-117">Supported URLs for nuget.org include `http://www.nuget.org`, `http://www.nuget.org/api/v3`, and `http://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="c6d5d-118">Ersetzen Sie für private Feeds den Hostnamen (z.B. `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="c6d5d-118">For private feeds, substitute the host name (for example, `%hostname%/api/v3`).</span></span>

`--non-interactive`

<span data-ttu-id="c6d5d-119">Fordert nicht zu Eingaben oder Bestätigungen des Benutzers auf.</span><span class="sxs-lookup"><span data-stu-id="c6d5d-119">Doesn't prompt for user input or confirmations.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="c6d5d-120">Der API-Schlüssel für den Server.</span><span class="sxs-lookup"><span data-stu-id="c6d5d-120">The API key for the server.</span></span>

`--force-english-output`

<span data-ttu-id="c6d5d-121">Erzwingt, dass die Befehlszeilenausgabe auf Englisch ist.</span><span class="sxs-lookup"><span data-stu-id="c6d5d-121">Forces command-line output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="c6d5d-122">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c6d5d-122">Examples</span></span>

<span data-ttu-id="c6d5d-123">Löscht Version 1.0 des Pakets `Microsoft.AspNetCore.Mvc`:</span><span class="sxs-lookup"><span data-stu-id="c6d5d-123">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0` 

<span data-ttu-id="c6d5d-124">Löscht Version 1.0 des Pakets `Microsoft.AspNetCore.Mvc`, wobei der Benutzer nicht zur Eingabe von Anmeldeinformationen oder zu anderen Eingaben aufgefordert wird:</span><span class="sxs-lookup"><span data-stu-id="c6d5d-124">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`

