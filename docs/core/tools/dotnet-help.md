---
title: dotnet help-Befehl – .NET Core-CLI
description: Der Befehl „dotnet help“ zeigt ausführlichere Onlinedokumentation für den angegebenen Befehl.
author: mairaw
ms.author: mairaw
ms.date: 08/17/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 189eeea87babbce16751c5875f62c990ebecc10a
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="cc5e9-103">dotnet help reference</span><span class="sxs-lookup"><span data-stu-id="cc5e9-103">dotnet help reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a><span data-ttu-id="cc5e9-104">name</span><span class="sxs-lookup"><span data-stu-id="cc5e9-104">Name</span></span>

<span data-ttu-id="cc5e9-105">`dotnet help`: zeigt ausführlichere Onlinedokumentation für den angegebenen Befehl.</span><span class="sxs-lookup"><span data-stu-id="cc5e9-105">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cc5e9-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="cc5e9-106">Synopsis</span></span>

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="cc5e9-107">description</span><span class="sxs-lookup"><span data-stu-id="cc5e9-107">Description</span></span>

<span data-ttu-id="cc5e9-108">Der Befehl `dotnet help` öffnet die Referenzseite mit ausführlicheren Informationen zum angegebenen Befehl auf docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="cc5e9-108">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="cc5e9-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="cc5e9-109">Arguments</span></span>

`COMMAND_NAME`

<span data-ttu-id="cc5e9-110">Der Name des .NET Core-CLI-Befehls.</span><span class="sxs-lookup"><span data-stu-id="cc5e9-110">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="cc5e9-111">Eine Liste der zulässigen CLI-Befehle finden Sie unter [CLI-Befehle](index.md#cli-commands).</span><span class="sxs-lookup"><span data-stu-id="cc5e9-111">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="cc5e9-112">Optionen</span><span class="sxs-lookup"><span data-stu-id="cc5e9-112">Options</span></span>

`-h|--help`

<span data-ttu-id="cc5e9-113">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="cc5e9-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="cc5e9-114">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cc5e9-114">Examples</span></span>

<span data-ttu-id="cc5e9-115">Öffnet die Dokumentationsseite für den [dotnet new](dotnet-new.md)-Befehl:</span><span class="sxs-lookup"><span data-stu-id="cc5e9-115">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

`dotnet help new`
