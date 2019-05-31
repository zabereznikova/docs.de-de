---
title: Befehl „dotnet build-server“
description: Der Befehl „dotnet build-server“ interagiert mit Servern, die durch einen Build gestartet werden.
ms.date: 04/24/2019
ms.openlocfilehash: fa663bc045e8abfc3375a0226be7d16331b49740
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632099"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="7c0ef-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="7c0ef-103">dotnet build-server</span></span>

<span data-ttu-id="7c0ef-104">**Dieser Artikel gilt für: ✓**.NET Core 2.1 SDK und spätere Versionen</span><span class="sxs-lookup"><span data-stu-id="7c0ef-104">**This article applies to: ✓** .NET Core 2.1 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a><span data-ttu-id="7c0ef-105">name</span><span class="sxs-lookup"><span data-stu-id="7c0ef-105">Name</span></span>

<span data-ttu-id="7c0ef-106">`dotnet build-server`: Interagiert mit Servern, die von einem Build gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="7c0ef-106">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7c0ef-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="7c0ef-107">Synopsis</span></span>

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="7c0ef-108">Befehle</span><span class="sxs-lookup"><span data-stu-id="7c0ef-108">Commands</span></span>

* **`shutdown`**

  <span data-ttu-id="7c0ef-109">Fährt Buildserver herunter, die über dotnet gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="7c0ef-109">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="7c0ef-110">Standardmäßig werden alle Server heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="7c0ef-110">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="7c0ef-111">Optionen</span><span class="sxs-lookup"><span data-stu-id="7c0ef-111">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="7c0ef-112">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="7c0ef-112">Prints out a short help for the command.</span></span>

* **`--msbuild`**

  <span data-ttu-id="7c0ef-113">Fährt den MSBuild-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="7c0ef-113">Shuts down the MSBuild build server.</span></span>

* **`--razor`**

  <span data-ttu-id="7c0ef-114">Fährt den Razor-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="7c0ef-114">Shuts down the Razor build server.</span></span>

* **`--vbcscompiler`**

  <span data-ttu-id="7c0ef-115">Fährt den VB/C#-Compiler-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="7c0ef-115">Shuts down the VB/C# compiler build server.</span></span>
