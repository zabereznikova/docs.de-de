---
title: Befehl „dotnet help“
description: Der Befehl „dotnet help“ zeigt ausführlichere Onlinedokumentation für den angegebenen Befehl.
ms.date: 02/14/2020
ms.openlocfilehash: a59e74a318118b6fd39d1895df02d76daa6fc9e1
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463691"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="fd8ad-103">dotnet help reference</span><span class="sxs-lookup"><span data-stu-id="fd8ad-103">dotnet help reference</span></span>

<span data-ttu-id="fd8ad-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="fd8ad-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="fd8ad-105">Name</span><span class="sxs-lookup"><span data-stu-id="fd8ad-105">Name</span></span>

<span data-ttu-id="fd8ad-106">`dotnet help`: zeigt ausführlichere Onlinedokumentation für den angegebenen Befehl.</span><span class="sxs-lookup"><span data-stu-id="fd8ad-106">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="fd8ad-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="fd8ad-107">Synopsis</span></span>

```dotnetcli
dotnet help <COMMAND_NAME> [-h|--help]
```

## <a name="description"></a><span data-ttu-id="fd8ad-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd8ad-108">Description</span></span>

<span data-ttu-id="fd8ad-109">Der Befehl `dotnet help` öffnet die Referenzseite mit ausführlicheren Informationen zum angegebenen Befehl auf docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="fd8ad-109">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="fd8ad-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="fd8ad-110">Arguments</span></span>

- **`COMMAND_NAME`**

  <span data-ttu-id="fd8ad-111">Der Name des .NET Core-CLI-Befehls.</span><span class="sxs-lookup"><span data-stu-id="fd8ad-111">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="fd8ad-112">Eine Liste der zulässigen CLI-Befehle finden Sie unter [CLI-Befehle](index.md#cli-commands).</span><span class="sxs-lookup"><span data-stu-id="fd8ad-112">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="fd8ad-113">Optionen</span><span class="sxs-lookup"><span data-stu-id="fd8ad-113">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="fd8ad-114">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="fd8ad-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="fd8ad-115">Beispiele</span><span class="sxs-lookup"><span data-stu-id="fd8ad-115">Examples</span></span>

- <span data-ttu-id="fd8ad-116">Öffnet die Dokumentationsseite für den [dotnet new](dotnet-new.md)-Befehl:</span><span class="sxs-lookup"><span data-stu-id="fd8ad-116">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```dotnetcli
  dotnet help new
  ```
