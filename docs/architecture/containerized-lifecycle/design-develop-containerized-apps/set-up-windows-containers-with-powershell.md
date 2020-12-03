---
title: Verwenden von Windows PowerShell-Befehlen in einer DockerFile-Datei zum Einrichten von Windows-Containern (auf Docker-Standard basierend)
description: Erfahren Sie, wie Sie PowerShell beim Arbeiten mit Docker in Windows-Containern verwenden.
ms.date: 08/06/2020
ms.openlocfilehash: d65538c821a848d83915e715ee3a02990b40e836
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681248"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="c6cbd-103">Verwenden von Windows PowerShell-Befehlen in einer DockerFile-Datei zum Einrichten von Windows-Containern (auf Docker-Standard basierend)</span><span class="sxs-lookup"><span data-stu-id="c6cbd-103">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="c6cbd-104">Mit [Windows-Containern](/virtualization/windowscontainers/about/index) können Sie Ihre vorhandenen Windows-Anwendungen in Docker-Images konvertieren und diese mit den gleichen Tools wie den Rest des Docker-Ökosystems bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c6cbd-104">With [Windows Containers](/virtualization/windowscontainers/about/index), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="c6cbd-105">Um Windows-Container zu verwenden, müssen Sie lediglich PowerShell-Befehle in die DockerFile-Datei schreiben, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="c6cbd-105">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```dockerfile
FROM mcr.microsoft.com/windows/servercore:ltsc2019
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="c6cbd-106">In diesem Fall verwenden wir Windows PowerShell, um ein Windows Server Core-Basisimage sowie IIS zu installieren.</span><span class="sxs-lookup"><span data-stu-id="c6cbd-106">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="c6cbd-107">Auf ähnliche Weise können Sie auch mithilfe von Windows PowerShell-Befehlen wie hier zu sehen zusätzliche Komponenten wie herkömmliche Instanzen von ASP.NET 4.x und .NET Framework 4.6 oder eine beliebige andere Windows-Software einrichten:</span><span class="sxs-lookup"><span data-stu-id="c6cbd-107">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET Framework 4.6 or any other Windows software, as shown here:</span></span>

```dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
><span data-ttu-id="c6cbd-108">[Zurück](visual-studio-tools-for-docker.md)
>[Weiter](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="c6cbd-108">[Previous](visual-studio-tools-for-docker.md)
[Next](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)</span></span>
