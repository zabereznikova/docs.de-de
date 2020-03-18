---
ms.openlocfilehash: 975edd1bda507b46da353db788d9730560f9b573
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "65632117"
---
> [!NOTE]
> <span data-ttu-id="d78f6-101">Ab .NET Core 2.0 SDK müssen Sie [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) nicht mehr ausführen, da der Befehl implizit von allen Befehlen, z.B. `dotnet new`, `dotnet build` und `dotnet run`, ausgeführt wird, die eine Wiederherstellung erfordern.</span><span class="sxs-lookup"><span data-stu-id="d78f6-101">Starting with .NET Core 2.0 SDK, you don't have to run [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) because it's run implicitly by all commands that require a restore to occur, such as `dotnet new`, `dotnet build` and `dotnet run`.</span></span>
> <span data-ttu-id="d78f6-102">In bestimmten Fällen eignet sich der Befehl dennoch. Dies ist etwa bei Szenarios der Fall, in denen das Ausführen einer expliziten Wiederherstellung sinnvoll ist. Beispiele hierfür sind [Continuous Integration-Builds in Azure DevOps Services](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) oder Buildsystemen, die den Zeitpunkt für die Wiederherstellung explizit festlegen müssen.</span><span class="sxs-lookup"><span data-stu-id="d78f6-102">It's still a valid command in certain scenarios where doing an explicit restore makes sense, such as [continuous integration builds in Azure DevOps Services](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) or in build systems that need to explicitly control the time at which the restore occurs.</span></span>
