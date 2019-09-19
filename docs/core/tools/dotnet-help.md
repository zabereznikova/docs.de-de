---
title: Befehl „dotnet help“
description: Der Befehl „dotnet help“ zeigt ausführlichere Onlinedokumentation für den angegebenen Befehl.
ms.date: 08/08/2019
ms.openlocfilehash: e76f858f2529afc50646473f1aab9d52730cff16
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70990464"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="1d942-103">dotnet help reference</span><span class="sxs-lookup"><span data-stu-id="1d942-103">dotnet help reference</span></span>

<span data-ttu-id="1d942-104">**Dieser Artikel gilt für: ✓** .NET Core 2.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="1d942-104">**This article applies to: ✓** .NET Core 2.0 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]
-->

## <a name="name"></a><span data-ttu-id="1d942-105">name</span><span class="sxs-lookup"><span data-stu-id="1d942-105">Name</span></span>

<span data-ttu-id="1d942-106">`dotnet help`: zeigt ausführlichere Onlinedokumentation für den angegebenen Befehl.</span><span class="sxs-lookup"><span data-stu-id="1d942-106">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1d942-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="1d942-107">Synopsis</span></span>

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="1d942-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d942-108">Description</span></span>

<span data-ttu-id="1d942-109">Der Befehl `dotnet help` öffnet die Referenzseite mit ausführlicheren Informationen zum angegebenen Befehl auf docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1d942-109">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="1d942-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="1d942-110">Arguments</span></span>

* **`COMMAND_NAME`**

  <span data-ttu-id="1d942-111">Der Name des .NET Core-CLI-Befehls.</span><span class="sxs-lookup"><span data-stu-id="1d942-111">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="1d942-112">Eine Liste der zulässigen CLI-Befehle finden Sie unter [CLI-Befehle](index.md#cli-commands).</span><span class="sxs-lookup"><span data-stu-id="1d942-112">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="1d942-113">Optionen</span><span class="sxs-lookup"><span data-stu-id="1d942-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="1d942-114">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="1d942-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="1d942-115">Beispiele</span><span class="sxs-lookup"><span data-stu-id="1d942-115">Examples</span></span>

* <span data-ttu-id="1d942-116">Öffnet die Dokumentationsseite für den [dotnet new](dotnet-new.md)-Befehl:</span><span class="sxs-lookup"><span data-stu-id="1d942-116">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```console
  dotnet help new
  ```
