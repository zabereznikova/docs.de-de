---
title: Verwenden von Windows PowerShell-Befehlen in einer DockerFile-Datei zum Einrichten von Windows-Containern (auf Docker-Standard basierend)
description: Erfahren Sie, wie Sie PowerShell beim Arbeiten mit Docker in Windows-Containern verwenden.
ms.date: 02/15/2019
ms.openlocfilehash: e91d278aef1365a111e8d67ff04092dfc6a44185
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "68673577"
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
