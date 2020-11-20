---
title: Befehl „dotnet help“
description: Der Befehl „dotnet help“ zeigt ausführlichere Onlinedokumentation für den angegebenen Befehl.
ms.date: 02/14/2020
ms.openlocfilehash: d583142edabb24df972bdf9a06dbfe04688f9d97
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634467"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="a59fa-103">dotnet help reference</span><span class="sxs-lookup"><span data-stu-id="a59fa-103">dotnet help reference</span></span>

<span data-ttu-id="a59fa-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="a59fa-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="a59fa-105">Name</span><span class="sxs-lookup"><span data-stu-id="a59fa-105">Name</span></span>

<span data-ttu-id="a59fa-106">`dotnet help`: zeigt ausführlichere Onlinedokumentation für den angegebenen Befehl.</span><span class="sxs-lookup"><span data-stu-id="a59fa-106">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a59fa-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="a59fa-107">Synopsis</span></span>

```dotnetcli
dotnet help <COMMAND_NAME> [-h|--help]
```

## <a name="description"></a><span data-ttu-id="a59fa-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a59fa-108">Description</span></span>

<span data-ttu-id="a59fa-109">Der Befehl `dotnet help` öffnet die Referenzseite mit ausführlicheren Informationen zum angegebenen Befehl auf docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="a59fa-109">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="a59fa-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="a59fa-110">Arguments</span></span>

- **`COMMAND_NAME`**

  <span data-ttu-id="a59fa-111">Der Name des .NET-CLI-Befehls.</span><span class="sxs-lookup"><span data-stu-id="a59fa-111">Name of the .NET CLI command.</span></span> <span data-ttu-id="a59fa-112">Eine Liste der zulässigen CLI-Befehle finden Sie unter [CLI-Befehle](index.md#cli-commands).</span><span class="sxs-lookup"><span data-stu-id="a59fa-112">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="a59fa-113">Optionen</span><span class="sxs-lookup"><span data-stu-id="a59fa-113">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="a59fa-114">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="a59fa-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="a59fa-115">Beispiele</span><span class="sxs-lookup"><span data-stu-id="a59fa-115">Examples</span></span>

- <span data-ttu-id="a59fa-116">Öffnet die Dokumentationsseite für den [dotnet new](dotnet-new.md)-Befehl:</span><span class="sxs-lookup"><span data-stu-id="a59fa-116">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```dotnetcli
  dotnet help new
  ```
