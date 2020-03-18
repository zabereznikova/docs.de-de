---
title: Befehl „dotnet build-server“
description: Der Befehl „dotnet build-server“ interagiert mit Servern, die durch einen Build gestartet werden.
ms.date: 02/14/2020
ms.openlocfilehash: a6a9cd6de66371caef66d1101b3f844dffc771ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503780"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="761e7-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="761e7-103">dotnet build-server</span></span>

<span data-ttu-id="761e7-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="761e7-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="761e7-105">Name</span><span class="sxs-lookup"><span data-stu-id="761e7-105">Name</span></span>

<span data-ttu-id="761e7-106">`dotnet build-server`: Interagiert mit Servern, die von einem Build gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="761e7-106">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="761e7-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="761e7-107">Synopsis</span></span>

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="761e7-108">Befehle</span><span class="sxs-lookup"><span data-stu-id="761e7-108">Commands</span></span>

- **`shutdown`**

  <span data-ttu-id="761e7-109">Fährt Buildserver herunter, die über dotnet gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="761e7-109">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="761e7-110">Standardmäßig werden alle Server heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="761e7-110">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="761e7-111">Optionen</span><span class="sxs-lookup"><span data-stu-id="761e7-111">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="761e7-112">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="761e7-112">Prints out a short help for the command.</span></span>

- **`--msbuild`**

  <span data-ttu-id="761e7-113">Fährt den MSBuild-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="761e7-113">Shuts down the MSBuild build server.</span></span>

- **`--razor`**

  <span data-ttu-id="761e7-114">Fährt den Razor-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="761e7-114">Shuts down the Razor build server.</span></span>

- **`--vbcscompiler`**

  <span data-ttu-id="761e7-115">Fährt den VB/C#-Compiler-Buildserver herunter.</span><span class="sxs-lookup"><span data-stu-id="761e7-115">Shuts down the VB/C# compiler build server.</span></span>
