---
title: dotnet nuget delete-Befehl – .NET Core-CLI
description: Der dotnet-nuget-delete-Befehl löscht ein Paket vom Server oder hebt dessen Auflistung auf.
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 1e81501d526ae92336b808f98c7c192b55e89f98
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="2b9da-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="2b9da-103">dotnet nuget delete</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="2b9da-104">name</span><span class="sxs-lookup"><span data-stu-id="2b9da-104">Name</span></span>

<span data-ttu-id="2b9da-105">`dotnet nuget delete` – Löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="2b9da-105">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2b9da-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="2b9da-106">Synopsis</span></span>

`dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [-s|--source] [--non-interactive] [-k|--api-key] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="2b9da-107">description</span><span class="sxs-lookup"><span data-stu-id="2b9da-107">Description</span></span>

<span data-ttu-id="2b9da-108">Der `dotnet nuget delete`-Befehl löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="2b9da-108">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="2b9da-109">Für [nuget.org](https://www.nuget.org/) wird die Auflistung des Pakets aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="2b9da-109">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="2b9da-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="2b9da-110">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="2b9da-111">Zu löschendes Paket.</span><span class="sxs-lookup"><span data-stu-id="2b9da-111">Package to delete.</span></span>

`PACKAGE_VERSION`

<span data-ttu-id="2b9da-112">Version des zu löschenden Pakets.</span><span class="sxs-lookup"><span data-stu-id="2b9da-112">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="2b9da-113">Optionen</span><span class="sxs-lookup"><span data-stu-id="2b9da-113">Options</span></span>

`-h|--help`

<span data-ttu-id="2b9da-114">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="2b9da-114">Prints out a short help for the command.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="2b9da-115">Gibt die Server-URL an.</span><span class="sxs-lookup"><span data-stu-id="2b9da-115">Specifies the server URL.</span></span> <span data-ttu-id="2b9da-116">Unterstützte URLs für „nuget.org“ sind u.a. `http://www.nuget.org`, `http://www.nuget.org/api/v3` und `http://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="2b9da-116">Supported URLs for nuget.org include `http://www.nuget.org`, `http://www.nuget.org/api/v3`, and `http://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="2b9da-117">Ersetzen Sie für private Feeds den Hostnamen (z.B. `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="2b9da-117">For private feeds, substitute the host name (for example, `%hostname%/api/v3`).</span></span>

`--non-interactive`

<span data-ttu-id="2b9da-118">Fordert nicht zu Eingaben oder Bestätigungen des Benutzers auf.</span><span class="sxs-lookup"><span data-stu-id="2b9da-118">Doesn't prompt for user input or confirmations.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="2b9da-119">Der API-Schlüssel für den Server.</span><span class="sxs-lookup"><span data-stu-id="2b9da-119">The API key for the server.</span></span>

`--force-english-output`

<span data-ttu-id="2b9da-120">Erzwingt, dass die Befehlszeilenausgabe auf Englisch ist.</span><span class="sxs-lookup"><span data-stu-id="2b9da-120">Forces command-line output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="2b9da-121">Beispiele</span><span class="sxs-lookup"><span data-stu-id="2b9da-121">Examples</span></span>

<span data-ttu-id="2b9da-122">Löscht Version 1.0 des Pakets `Microsoft.AspNetCore.Mvc`:</span><span class="sxs-lookup"><span data-stu-id="2b9da-122">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0` 

<span data-ttu-id="2b9da-123">Löscht Version 1.0 des Pakets `Microsoft.AspNetCore.Mvc`, wobei der Benutzer nicht zur Eingabe von Anmeldeinformationen oder zu anderen Eingaben aufgefordert wird:</span><span class="sxs-lookup"><span data-stu-id="2b9da-123">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`