---
title: Befehl „dotnet build-server“
description: Der Befehl „dotnet build-server“ interagiert mit Servern, die durch einen Build gestartet werden.
ms.date: 04/24/2019
ms.openlocfilehash: 89d1aba104e2cb07b46766a3768eed68d85a7aa7
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117765"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="18657-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="18657-103">dotnet build-server</span></span>

<span data-ttu-id="18657-104">**Dieser Artikel gilt für: ✓**.NET Core 2.1 SDK und spätere Versionen</span><span class="sxs-lookup"><span data-stu-id="18657-104">**This article applies to: ✓** .NET Core 2.1 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a><span data-ttu-id="18657-105">NAME</span><span class="sxs-lookup"><span data-stu-id="18657-105">Name</span></span>

<span data-ttu-id="18657-106">`dotnet build-server`: Interagiert mit Servern, die von einem Build gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="18657-106">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="18657-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="18657-107">Synopsis</span></span>

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="18657-108">Befehle</span><span class="sxs-lookup"><span data-stu-id="18657-108">Commands</span></span>

* **`shutdown`**

  <span data-ttu-id="18657-109">Fährt Buildserver herunter, die über dotnet gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="18657-109">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="18657-110">Standardmäßig werden alle Server heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="18657-110">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="18657-111">Optionen</span><span class="sxs-lookup"><span data-stu-id="18657-111">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="18657-112">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="18657-112">Prints out a short help for the command.</span></span>

* **`--msbuild`**

  <span data-ttu-id="18657-113">Fährt den MSBuild-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="18657-113">Shuts down the MSBuild build server.</span></span>

* **`--razor`**

  <span data-ttu-id="18657-114">Fährt den Razor-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="18657-114">Shuts down the Razor build server.</span></span>

* **`--vbcscompiler`**

  <span data-ttu-id="18657-115">Fährt den VB/C#-Compiler-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="18657-115">Shuts down the VB/C# compiler build server.</span></span>
