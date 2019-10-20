---
title: Befehl „dotnet build-server“
description: Der Befehl „dotnet build-server“ interagiert mit Servern, die durch einen Build gestartet werden.
ms.date: 04/24/2019
ms.openlocfilehash: 1c6c6dcdb53d779426daf5daa470d2ad0470a7a1
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523014"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="a4ea8-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="a4ea8-103">dotnet build-server</span></span>

<span data-ttu-id="a4ea8-104">**Dieser Artikel gilt für: ✓**.NET Core 2.1 SDK und spätere Versionen</span><span class="sxs-lookup"><span data-stu-id="a4ea8-104">**This article applies to: ✓** .NET Core 2.1 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a><span data-ttu-id="a4ea8-105">name</span><span class="sxs-lookup"><span data-stu-id="a4ea8-105">Name</span></span>

<span data-ttu-id="a4ea8-106">`dotnet build-server`: Interagiert mit Servern, die von einem Build gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="a4ea8-106">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a4ea8-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="a4ea8-107">Synopsis</span></span>

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="a4ea8-108">Befehle</span><span class="sxs-lookup"><span data-stu-id="a4ea8-108">Commands</span></span>

- **`shutdown`**

  <span data-ttu-id="a4ea8-109">Fährt Buildserver herunter, die über dotnet gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="a4ea8-109">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="a4ea8-110">Standardmäßig werden alle Server heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="a4ea8-110">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="a4ea8-111">Optionen</span><span class="sxs-lookup"><span data-stu-id="a4ea8-111">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="a4ea8-112">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="a4ea8-112">Prints out a short help for the command.</span></span>

- **`--msbuild`**

  <span data-ttu-id="a4ea8-113">Fährt den MSBuild-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="a4ea8-113">Shuts down the MSBuild build server.</span></span>

- **`--razor`**

  <span data-ttu-id="a4ea8-114">Fährt den Razor-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="a4ea8-114">Shuts down the Razor build server.</span></span>

- **`--vbcscompiler`**

  <span data-ttu-id="a4ea8-115">Fährt den VB/C#-Compiler-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="a4ea8-115">Shuts down the VB/C# compiler build server.</span></span>
