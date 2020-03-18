---
ms.openlocfilehash: 47811d3fab2e4fa531d383dfe818e3cac5613eb3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "72179982"
---
> [!NOTE]
> Ab .NET Core 2.0 müssen Sie [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) nicht mehr ausführen, da der Befehl implizit von allen Befehlen, z.B. `dotnet build` und `dotnet run`, ausgeführt wird, die eine Wiederherstellung erfordern. In bestimmten Fällen eignet sich der Befehl dennoch. Dies ist etwa bei Szenarios der Fall, in denen das Ausführen einer expliziten Wiederherstellung sinnvoll ist. Beispiele hierfür sind [Continuous Integration-Builds in Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) oder Buildsystemen, die den Zeitpunkt für die Wiederherstellung explizit festlegen müssen.
>
> Dieser Befehl unterstützt auch die `dotnet restore`-Optionen, wenn sie in der Langform übergeben werden (z.B. `--source`). Optionen in Kurzform wie z.B. `-s` werden nicht unterstützt.
