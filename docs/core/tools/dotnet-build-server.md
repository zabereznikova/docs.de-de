---
title: '.NET Core-CLI-Befehl: dotnet build-server'
description: Der Befehl „dotnet build-server“ interagiert mit Servern, die durch einen Build gestartet werden.
ms.date: 12/04/2018
ms.openlocfilehash: 2746ade12cc819089258483e84a8c0f02a64c755
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53125677"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="40c82-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="40c82-103">dotnet build-server</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="40c82-104">name</span><span class="sxs-lookup"><span data-stu-id="40c82-104">Name</span></span>

<span data-ttu-id="40c82-105">`dotnet build-server`: Interagiert mit Servern, die von einem Build gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="40c82-105">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="40c82-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="40c82-106">Synopsis</span></span>

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="40c82-107">Befehle</span><span class="sxs-lookup"><span data-stu-id="40c82-107">Commands</span></span>

* **`shutdown`**

  <span data-ttu-id="40c82-108">Fährt Buildserver herunter, die über dotnet gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="40c82-108">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="40c82-109">Standardmäßig werden alle Server heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="40c82-109">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="40c82-110">Optionen</span><span class="sxs-lookup"><span data-stu-id="40c82-110">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="40c82-111">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="40c82-111">Prints out a short help for the command.</span></span>

* **`--msbuild`**

  <span data-ttu-id="40c82-112">Fährt den MSBuild-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="40c82-112">Shuts down the MSBuild build server.</span></span>

* **`--razor`**

  <span data-ttu-id="40c82-113">Fährt den Razor-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="40c82-113">Shuts down the Razor build server.</span></span>

* **`--vbcscompiler`**

  <span data-ttu-id="40c82-114">Fährt den VB/C#-Compiler-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="40c82-114">Shuts down the VB/C# compiler build server.</span></span>