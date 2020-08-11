---
title: Verwenden von Windows PowerShell-Befehlen in einer DockerFile-Datei zum Einrichten von Windows-Containern (auf Docker-Standard basierend)
description: Erfahren Sie, wie Sie PowerShell beim Arbeiten mit Docker in Windows-Containern verwenden.
ms.date: 08/06/2020
ms.openlocfilehash: 4e7b9e7fedf11b97b3f468aef541bf72a4e88ebc
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "87915394"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a>Verwenden von Windows PowerShell-Befehlen in einer DockerFile-Datei zum Einrichten von Windows-Containern (auf Docker-Standard basierend)

Mit [Windows-Containern](/virtualization/windowscontainers/about/index) können Sie Ihre vorhandenen Windows-Anwendungen in Docker-Images konvertieren und diese mit den gleichen Tools wie den Rest des Docker-Ökosystems bereitstellen.

Um Windows-Container zu verwenden, müssen Sie lediglich PowerShell-Befehle in die DockerFile-Datei schreiben, wie im folgenden Beispiel gezeigt:

```Dockerfile
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

In diesem Fall verwenden wir Windows PowerShell, um ein Windows Server Core-Basisimage sowie IIS zu installieren.

In ähnlicher Weise können Sie auch Windows PowerShell-Befehle verwenden, um zusätzliche Komponenten wie das herkömmliche ASP.NET 4.x, .NET 4.6 oder andere Windows-Software einzurichten, wie hier zu sehen:

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
>[Zurück](visual-studio-tools-for-docker.md)
>[Weiter](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)
