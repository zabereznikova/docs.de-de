---
ms.openlocfilehash: 47811d3fab2e4fa531d383dfe818e3cac5613eb3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "72179982"
---
> [!NOTE]
> <span data-ttu-id="fc531-101">Ab .NET Core 2.0 müssen Sie [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) nicht mehr ausführen, da der Befehl implizit von allen Befehlen, z.B. `dotnet build` und `dotnet run`, ausgeführt wird, die eine Wiederherstellung erfordern.</span><span class="sxs-lookup"><span data-stu-id="fc531-101">Starting with .NET Core 2.0, you don't have to run [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) because it's run implicitly by all commands that require a restore to occur, such as `dotnet build` and `dotnet run`.</span></span> <span data-ttu-id="fc531-102">In bestimmten Fällen eignet sich der Befehl dennoch. Dies ist etwa bei Szenarios der Fall, in denen das Ausführen einer expliziten Wiederherstellung sinnvoll ist. Beispiele hierfür sind [Continuous Integration-Builds in Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) oder Buildsystemen, die den Zeitpunkt für die Wiederherstellung explizit festlegen müssen.</span><span class="sxs-lookup"><span data-stu-id="fc531-102">It's still a valid command in certain scenarios where doing an explicit restore makes sense, such as [continuous integration builds in Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) or in build systems that need to explicitly control the time at which the restore occurs.</span></span>
>
> <span data-ttu-id="fc531-103">Dieser Befehl unterstützt auch die `dotnet restore`-Optionen, wenn sie in der Langform übergeben werden (z.B. `--source`).</span><span class="sxs-lookup"><span data-stu-id="fc531-103">This command also supports the `dotnet restore` options when passed in the long form (for example, `--source`).</span></span> <span data-ttu-id="fc531-104">Optionen in Kurzform wie z.B. `-s` werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fc531-104">Short form options, such as `-s`, are not supported.</span></span>
