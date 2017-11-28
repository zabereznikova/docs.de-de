---
title: "dotnet nuget delete-Befehl – .NET Core-CLI"
description: "Der dotnet-nuget-delete-Befehl löscht ein Paket vom Server oder hebt dessen Auflistung auf."
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 65fe52f07ed823b4f7518c5b1f2da1f7a61b0371
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="a94ef-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="a94ef-103">dotnet nuget delete</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="a94ef-104">Name</span><span class="sxs-lookup"><span data-stu-id="a94ef-104">Name</span></span>

<span data-ttu-id="a94ef-105">`dotnet nuget delete` – Löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="a94ef-105">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a94ef-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="a94ef-106">Synopsis</span></span>

`dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [-s|--source] [--non-interactive] [-k|--api-key] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="a94ef-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a94ef-107">Description</span></span>

<span data-ttu-id="a94ef-108">Der `dotnet nuget delete`-Befehl löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="a94ef-108">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="a94ef-109">Für [nuget.org](https://www.nuget.org/) wird die Auflistung des Pakets aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="a94ef-109">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="a94ef-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="a94ef-110">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="a94ef-111">Zu löschendes Paket.</span><span class="sxs-lookup"><span data-stu-id="a94ef-111">Package to delete.</span></span>

`PACKAGE_VERSION`

<span data-ttu-id="a94ef-112">Version des zu löschenden Pakets.</span><span class="sxs-lookup"><span data-stu-id="a94ef-112">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="a94ef-113">Optionen</span><span class="sxs-lookup"><span data-stu-id="a94ef-113">Options</span></span>

`-h|--help`

<span data-ttu-id="a94ef-114">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="a94ef-114">Prints out a short help for the command.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="a94ef-115">Gibt die Server-URL an.</span><span class="sxs-lookup"><span data-stu-id="a94ef-115">Specifies the server URL.</span></span> <span data-ttu-id="a94ef-116">Unterstützte URLs für „nuget.org“ sind u.a. `http://www.nuget.org`, `http://www.nuget.org/api/v3` und `http://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="a94ef-116">Supported URLs for nuget.org include `http://www.nuget.org`, `http://www.nuget.org/api/v3`, and `http://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="a94ef-117">Ersetzen Sie für private Feeds den Hostnamen (z.B. `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="a94ef-117">For private feeds, substitute the host name (for example, `%hostname%/api/v3`).</span></span>

`--non-interactive`

<span data-ttu-id="a94ef-118">Fordert nicht zu Eingaben oder Bestätigungen des Benutzers auf.</span><span class="sxs-lookup"><span data-stu-id="a94ef-118">Doesn't prompt for user input or confirmations.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="a94ef-119">Der API-Schlüssel für den Server.</span><span class="sxs-lookup"><span data-stu-id="a94ef-119">The API key for the server.</span></span>

`--force-english-output`

<span data-ttu-id="a94ef-120">Erzwingt, dass die Befehlszeilenausgabe auf Englisch ist.</span><span class="sxs-lookup"><span data-stu-id="a94ef-120">Forces command-line output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="a94ef-121">Beispiele</span><span class="sxs-lookup"><span data-stu-id="a94ef-121">Examples</span></span>

<span data-ttu-id="a94ef-122">Löscht Version 1.0 des Pakets `Microsoft.AspNetCore.Mvc`:</span><span class="sxs-lookup"><span data-stu-id="a94ef-122">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0` 

<span data-ttu-id="a94ef-123">Löscht Version 1.0 des Pakets `Microsoft.AspNetCore.Mvc`, wobei der Benutzer nicht zur Eingabe von Anmeldeinformationen oder zu anderen Eingaben aufgefordert wird:</span><span class="sxs-lookup"><span data-stu-id="a94ef-123">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`