---
title: Befehl „dotnet help“
description: Der Befehl „dotnet help“ zeigt ausführlichere Onlinedokumentation für den angegebenen Befehl.
ms.date: 12/04/2018
ms.openlocfilehash: 44274b698ed83bd3cdb58787f433eeb5c555bc6d
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168952"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="e5306-103">dotnet help reference</span><span class="sxs-lookup"><span data-stu-id="e5306-103">dotnet help reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a><span data-ttu-id="e5306-104">Name</span><span class="sxs-lookup"><span data-stu-id="e5306-104">Name</span></span>

<span data-ttu-id="e5306-105">`dotnet help`: zeigt ausführlichere Onlinedokumentation für den angegebenen Befehl.</span><span class="sxs-lookup"><span data-stu-id="e5306-105">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e5306-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="e5306-106">Synopsis</span></span>

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="e5306-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5306-107">Description</span></span>

<span data-ttu-id="e5306-108">Der Befehl `dotnet help` öffnet die Referenzseite mit ausführlicheren Informationen zum angegebenen Befehl auf docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e5306-108">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="e5306-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="e5306-109">Arguments</span></span>

* **`COMMAND_NAME`**

  <span data-ttu-id="e5306-110">Der Name des .NET Core-CLI-Befehls.</span><span class="sxs-lookup"><span data-stu-id="e5306-110">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="e5306-111">Eine Liste der zulässigen CLI-Befehle finden Sie unter [CLI-Befehle](index.md#cli-commands).</span><span class="sxs-lookup"><span data-stu-id="e5306-111">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="e5306-112">Optionen</span><span class="sxs-lookup"><span data-stu-id="e5306-112">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="e5306-113">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="e5306-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="e5306-114">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e5306-114">Examples</span></span>

* <span data-ttu-id="e5306-115">Öffnet die Dokumentationsseite für den [dotnet new](dotnet-new.md)-Befehl:</span><span class="sxs-lookup"><span data-stu-id="e5306-115">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```console
  dotnet help new
  ```