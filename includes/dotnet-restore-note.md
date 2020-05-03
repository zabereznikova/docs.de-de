---
ms.openlocfilehash: e140b375f4f289df895052aa093f03f381d62488
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102740"
---
Sie müssen [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) nicht ausführen, da der Befehl implizit von allen Befehlen ausgeführt wird, die eine Wiederherstellung erfordern. Zu diesen zählen z. B. `dotnet new`, `dotnet build`, `dotnet run`, `dotnet test`, `dotnet publish` und `dotnet pack`. Verwenden Sie die Option `--no-restore`, um die implizite Wiederherstellung zu deaktivieren.

In bestimmten Fällen eignet sich der `dotnet restore`-Befehl dennoch. Dies ist etwa bei Szenarios der Fall, in denen die explizite Wiederherstellung sinnvoll ist. Beispiele hierfür sind [Continuous Integration-Builds in Azure DevOps Services](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) oder Buildsysteme, die den Zeitpunkt für die Wiederherstellung explizit steuern müssen.

Informationen zum Verwalten von NuGet-Feeds finden Sie in der [`dotnet restore`Dokumentation](../docs/core/tools/dotnet-restore.md).
