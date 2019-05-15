---
title: Verwenden von Windows PowerShell-Befehle in einer dockerfile-Datei zum Einrichten der Windows-Container (Docker-standard basierend)
description: Erfahren Sie, wie Sie PowerShell verwenden, bei der Arbeit mit Docker in Windows-Containern
ms.date: 02/15/2019
ms.openlocfilehash: e91d278aef1365a111e8d67ff04092dfc6a44185
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641585"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a>Verwenden von Windows PowerShell-Befehle in einer dockerfile-Datei zum Einrichten der Windows-Container (Docker-standard basierend)

Mit [Windows-Containern](/virtualization/windowscontainers/about/index), Sie können Ihre vorhandenen Windows-Anwendungen zu Docker-Images zu konvertieren und diese mit den gleichen Tools wie der Rest des Docker-Ökosystems bereitstellen.

Um Windows-Container verwenden, müssen Sie nur Windows PowerShell-Befehle in der dockerfile-Datei zu schreiben, wie im folgenden Beispiel gezeigt:

```Dockerfile
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

In diesem Fall verwenden wir Windows PowerShell, um zu einem Windows Server Core-Basisimage sowie die IIS installieren.

Auf ähnliche Weise, außerdem können Windows PowerShell-Befehle zum Einrichten von zusätzlicher Komponenten wie herkömmliche ASP.NET 4.x und .NET 4.6 oder andere Windows-Software, wie hier gezeigt:

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
>[Zurück](visual-studio-tools-for-docker.md)
>[Weiter](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)
