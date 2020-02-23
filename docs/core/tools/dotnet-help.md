---
title: Befehl „dotnet help“
description: Der Befehl „dotnet help“ zeigt ausführlichere Onlinedokumentation für den angegebenen Befehl.
ms.date: 02/14/2020
ms.openlocfilehash: f5d9221ae18653451a3bf97dc82fae396ae4e288
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503725"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="541a2-103">dotnet help reference</span><span class="sxs-lookup"><span data-stu-id="541a2-103">dotnet help reference</span></span>

<span data-ttu-id="541a2-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="541a2-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="541a2-105">name</span><span class="sxs-lookup"><span data-stu-id="541a2-105">Name</span></span>

<span data-ttu-id="541a2-106">`dotnet help`: zeigt ausführlichere Onlinedokumentation für den angegebenen Befehl.</span><span class="sxs-lookup"><span data-stu-id="541a2-106">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="541a2-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="541a2-107">Synopsis</span></span>

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="541a2-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="541a2-108">Description</span></span>

<span data-ttu-id="541a2-109">Der Befehl `dotnet help` öffnet die Referenzseite mit ausführlicheren Informationen zum angegebenen Befehl auf docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="541a2-109">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="541a2-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="541a2-110">Arguments</span></span>

- **`COMMAND_NAME`**

  <span data-ttu-id="541a2-111">Der Name des .NET Core-CLI-Befehls.</span><span class="sxs-lookup"><span data-stu-id="541a2-111">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="541a2-112">Eine Liste der zulässigen CLI-Befehle finden Sie unter [CLI-Befehle](index.md#cli-commands).</span><span class="sxs-lookup"><span data-stu-id="541a2-112">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="541a2-113">Optionen</span><span class="sxs-lookup"><span data-stu-id="541a2-113">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="541a2-114">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="541a2-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="541a2-115">Beispiele</span><span class="sxs-lookup"><span data-stu-id="541a2-115">Examples</span></span>

- <span data-ttu-id="541a2-116">Öffnet die Dokumentationsseite für den [dotnet new](dotnet-new.md)-Befehl:</span><span class="sxs-lookup"><span data-stu-id="541a2-116">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```dotnetcli
  dotnet help new
  ```
