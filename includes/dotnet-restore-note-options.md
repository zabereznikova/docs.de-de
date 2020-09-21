---
ms.openlocfilehash: 19002cce40fdc929716a761a5e01303be4decb35
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537826"
---
Sie müssen [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) nicht ausführen, da der Befehl implizit von allen Befehlen ausgeführt wird, die eine Wiederherstellung erfordern. Zu diesen zählen z. B. `dotnet new`, `dotnet build`, `dotnet run`, `dotnet test`, `dotnet publish` und `dotnet pack`. Verwenden Sie die Option `--no-restore`, um die implizite Wiederherstellung zu deaktivieren.

In bestimmten Fällen eignet sich der `dotnet restore`-Befehl dennoch. Dies ist etwa bei Szenarios der Fall, in denen die explizite Wiederherstellung sinnvoll ist. Beispiele hierfür sind [Continuous Integration-Builds in Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) oder Buildsysteme, die den Zeitpunkt für die Wiederherstellung explizit steuern müssen.

Informationen zum Verwalten von NuGet-Feeds finden Sie in der [`dotnet restore`Dokumentation](../docs/core/tools/dotnet-restore.md).

Dieser Befehl unterstützt die `dotnet restore`-Optionen, wenn sie in der Langform (z. B. `--source`) übergeben werden. Optionen in Kurzform wie z.B. `-s` werden nicht unterstützt.
