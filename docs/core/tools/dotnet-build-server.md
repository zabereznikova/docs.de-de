---
title: Befehl „dotnet build-server“
description: Der Befehl „dotnet build-server“ interagiert mit Servern, die durch einen Build gestartet werden.
ms.date: 04/24/2019
ms.openlocfilehash: e77a4d9f49f555ac847bb13380380599eef881b1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734376"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="3f2ca-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="3f2ca-103">dotnet build-server</span></span>

<span data-ttu-id="3f2ca-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="3f2ca-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a><span data-ttu-id="3f2ca-105">name</span><span class="sxs-lookup"><span data-stu-id="3f2ca-105">Name</span></span>

<span data-ttu-id="3f2ca-106">`dotnet build-server`: Interagiert mit Servern, die von einem Build gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="3f2ca-106">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3f2ca-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="3f2ca-107">Synopsis</span></span>

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="3f2ca-108">Befehle</span><span class="sxs-lookup"><span data-stu-id="3f2ca-108">Commands</span></span>

- **`shutdown`**

  <span data-ttu-id="3f2ca-109">Fährt Buildserver herunter, die über dotnet gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="3f2ca-109">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="3f2ca-110">Standardmäßig werden alle Server heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="3f2ca-110">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="3f2ca-111">Optionen</span><span class="sxs-lookup"><span data-stu-id="3f2ca-111">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="3f2ca-112">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="3f2ca-112">Prints out a short help for the command.</span></span>

- **`--msbuild`**

  <span data-ttu-id="3f2ca-113">Fährt den MSBuild-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="3f2ca-113">Shuts down the MSBuild build server.</span></span>

- **`--razor`**

  <span data-ttu-id="3f2ca-114">Fährt den Razor-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="3f2ca-114">Shuts down the Razor build server.</span></span>

- **`--vbcscompiler`**

  <span data-ttu-id="3f2ca-115">Fährt den VB/C#-Compiler-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="3f2ca-115">Shuts down the VB/C# compiler build server.</span></span>
