---
ms.openlocfilehash: e140b375f4f289df895052aa093f03f381d62488
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102740"
---
<span data-ttu-id="26771-101">Sie müssen [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) nicht ausführen, da der Befehl implizit von allen Befehlen ausgeführt wird, die eine Wiederherstellung erfordern. Zu diesen zählen z. B. `dotnet new`, `dotnet build`, `dotnet run`, `dotnet test`, `dotnet publish` und `dotnet pack`.</span><span class="sxs-lookup"><span data-stu-id="26771-101">You don't have to run [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) because it's run implicitly by all commands that require a restore to occur, such as `dotnet new`, `dotnet build`, `dotnet run`, `dotnet test`, `dotnet publish`, and `dotnet pack`.</span></span> <span data-ttu-id="26771-102">Verwenden Sie die Option `--no-restore`, um die implizite Wiederherstellung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="26771-102">To disable implicit restore, use the `--no-restore` option.</span></span>

<span data-ttu-id="26771-103">In bestimmten Fällen eignet sich der `dotnet restore`-Befehl dennoch. Dies ist etwa bei Szenarios der Fall, in denen die explizite Wiederherstellung sinnvoll ist. Beispiele hierfür sind [Continuous Integration-Builds in Azure DevOps Services](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) oder Buildsysteme, die den Zeitpunkt für die Wiederherstellung explizit steuern müssen.</span><span class="sxs-lookup"><span data-stu-id="26771-103">The `dotnet restore` command is still useful in certain scenarios where explicitly restoring makes sense, such as [continuous integration builds in Azure DevOps Services](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) or in build systems that need to explicitly control when the restore occurs.</span></span>

<span data-ttu-id="26771-104">Informationen zum Verwalten von NuGet-Feeds finden Sie in der [`dotnet restore`Dokumentation](../docs/core/tools/dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="26771-104">For information about how to manage NuGet feeds, see the [`dotnet restore` documentation](../docs/core/tools/dotnet-restore.md).</span></span>
