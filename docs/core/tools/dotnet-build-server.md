---
title: '.NET Core-CLI-Befehl: dotnet build-server'
description: Der Befehl „dotnet build-server“ interagiert mit Servern, die durch ein Build gestartet werden.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 929b8d74aa5f3f0ad73b108be8a5bf22f86e30d6
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696253"
---
# <a name="dotnet-build"></a><span data-ttu-id="1f0d3-103">dotnet-build</span><span class="sxs-lookup"><span data-stu-id="1f0d3-103">dotnet-build</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="1f0d3-104">name</span><span class="sxs-lookup"><span data-stu-id="1f0d3-104">Name</span></span>

<span data-ttu-id="1f0d3-105">`dotnet build-server`: Interagiert mit Servern, die von einem Build gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="1f0d3-105">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1f0d3-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="1f0d3-106">Synopsis</span></span>

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="1f0d3-107">Befehle</span><span class="sxs-lookup"><span data-stu-id="1f0d3-107">Commands</span></span>

`shutdown`

<span data-ttu-id="1f0d3-108">Fährt Buildserver herunter, die über dotnet gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="1f0d3-108">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="1f0d3-109">Standardmäßig werden alle Server heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="1f0d3-109">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="1f0d3-110">Optionen</span><span class="sxs-lookup"><span data-stu-id="1f0d3-110">Options</span></span>

`-h|--help`

<span data-ttu-id="1f0d3-111">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="1f0d3-111">Prints out a short help for the command.</span></span>

`--msbuild`

<span data-ttu-id="1f0d3-112">Fährt den MSBuild-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="1f0d3-112">Shuts down the MSBuild build server.</span></span>

`--razor`

<span data-ttu-id="1f0d3-113">Fährt den Razor-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="1f0d3-113">Shuts down the Razor build server.</span></span>

`--vbcscompiler`

<span data-ttu-id="1f0d3-114">Fährt den VB/C#-Compiler-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="1f0d3-114">Shuts down the VB/C# compiler build server.</span></span>
