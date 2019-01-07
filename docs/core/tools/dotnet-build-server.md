---
title: Befehl „dotnet build-server“
description: Der Befehl „dotnet build-server“ interagiert mit Servern, die durch einen Build gestartet werden.
ms.date: 12/04/2018
ms.openlocfilehash: 7f78a0cae6e3297f3084754dc56b0da4eac38caf
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169656"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="f69e5-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="f69e5-103">dotnet build-server</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="f69e5-104">Name</span><span class="sxs-lookup"><span data-stu-id="f69e5-104">Name</span></span>

<span data-ttu-id="f69e5-105">`dotnet build-server`: Interagiert mit Servern, die von einem Build gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="f69e5-105">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f69e5-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="f69e5-106">Synopsis</span></span>

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="f69e5-107">Befehle</span><span class="sxs-lookup"><span data-stu-id="f69e5-107">Commands</span></span>

* **`shutdown`**

  <span data-ttu-id="f69e5-108">Fährt Buildserver herunter, die über dotnet gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="f69e5-108">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="f69e5-109">Standardmäßig werden alle Server heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="f69e5-109">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="f69e5-110">Optionen</span><span class="sxs-lookup"><span data-stu-id="f69e5-110">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="f69e5-111">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="f69e5-111">Prints out a short help for the command.</span></span>

* **`--msbuild`**

  <span data-ttu-id="f69e5-112">Fährt den MSBuild-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="f69e5-112">Shuts down the MSBuild build server.</span></span>

* **`--razor`**

  <span data-ttu-id="f69e5-113">Fährt den Razor-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="f69e5-113">Shuts down the Razor build server.</span></span>

* **`--vbcscompiler`**

  <span data-ttu-id="f69e5-114">Fährt den VB/C#-Compiler-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="f69e5-114">Shuts down the VB/C# compiler build server.</span></span>