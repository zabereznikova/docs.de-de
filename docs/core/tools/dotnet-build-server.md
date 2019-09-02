---
title: Befehl „dotnet build-server“
description: Der Befehl „dotnet build-server“ interagiert mit Servern, die durch einen Build gestartet werden.
ms.date: 04/24/2019
ms.openlocfilehash: b2dfd5f317466f18d9246bd1fb281a92c42f6d9d
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2019
ms.locfileid: "70168108"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="740e2-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="740e2-103">dotnet build-server</span></span>

<span data-ttu-id="740e2-104">**Dieser Artikel gilt für: ✓**.NET Core 2.1 SDK und spätere Versionen</span><span class="sxs-lookup"><span data-stu-id="740e2-104">**This article applies to: ✓** .NET Core 2.1 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a><span data-ttu-id="740e2-105">name</span><span class="sxs-lookup"><span data-stu-id="740e2-105">Name</span></span>

<span data-ttu-id="740e2-106">`dotnet build-server`: Interagiert mit Servern, die von einem Build gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="740e2-106">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="740e2-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="740e2-107">Synopsis</span></span>

```console
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="740e2-108">Befehle</span><span class="sxs-lookup"><span data-stu-id="740e2-108">Commands</span></span>

* **`shutdown`**

  <span data-ttu-id="740e2-109">Fährt Buildserver herunter, die über dotnet gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="740e2-109">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="740e2-110">Standardmäßig werden alle Server heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="740e2-110">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="740e2-111">Optionen</span><span class="sxs-lookup"><span data-stu-id="740e2-111">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="740e2-112">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="740e2-112">Prints out a short help for the command.</span></span>

* **`--msbuild`**

  <span data-ttu-id="740e2-113">Fährt den MSBuild-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="740e2-113">Shuts down the MSBuild build server.</span></span>

* **`--razor`**

  <span data-ttu-id="740e2-114">Fährt den Razor-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="740e2-114">Shuts down the Razor build server.</span></span>

* **`--vbcscompiler`**

  <span data-ttu-id="740e2-115">Fährt den VB/C#-Compiler-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="740e2-115">Shuts down the VB/C# compiler build server.</span></span>
