---
title: '.NET Core-CLI-Befehl: dotnet build-server'
description: Der Befehl „dotnet build-server“ interagiert mit Servern, die durch einen Build gestartet werden.
author: mairaw
ms.author: mairaw
ms.date: 07/02/2018
ms.openlocfilehash: 1c59c85f246b79c7e2552f704db5b4f076f9b502
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404332"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="b63be-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="b63be-103">dotnet build-server</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="b63be-104">name</span><span class="sxs-lookup"><span data-stu-id="b63be-104">Name</span></span>

<span data-ttu-id="b63be-105">`dotnet build-server`: Interagiert mit Servern, die von einem Build gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="b63be-105">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b63be-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="b63be-106">Synopsis</span></span>

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="b63be-107">Befehle</span><span class="sxs-lookup"><span data-stu-id="b63be-107">Commands</span></span>

`shutdown`

<span data-ttu-id="b63be-108">Fährt Buildserver herunter, die über dotnet gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="b63be-108">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="b63be-109">Standardmäßig werden alle Server heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="b63be-109">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="b63be-110">Optionen</span><span class="sxs-lookup"><span data-stu-id="b63be-110">Options</span></span>

`-h|--help`

<span data-ttu-id="b63be-111">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="b63be-111">Prints out a short help for the command.</span></span>

`--msbuild`

<span data-ttu-id="b63be-112">Fährt den MSBuild-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="b63be-112">Shuts down the MSBuild build server.</span></span>

`--razor`

<span data-ttu-id="b63be-113">Fährt den Razor-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="b63be-113">Shuts down the Razor build server.</span></span>

`--vbcscompiler`

<span data-ttu-id="b63be-114">Fährt den VB/C#-Compiler-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="b63be-114">Shuts down the VB/C# compiler build server.</span></span>
