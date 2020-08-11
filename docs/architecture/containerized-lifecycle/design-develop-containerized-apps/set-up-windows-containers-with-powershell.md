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
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="1437a-103">Verwenden von Windows PowerShell-Befehlen in einer DockerFile-Datei zum Einrichten von Windows-Containern (auf Docker-Standard basierend)</span><span class="sxs-lookup"><span data-stu-id="1437a-103">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="1437a-104">Mit [Windows-Containern](/virtualization/windowscontainers/about/index) können Sie Ihre vorhandenen Windows-Anwendungen in Docker-Images konvertieren und diese mit den gleichen Tools wie den Rest des Docker-Ökosystems bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1437a-104">With [Windows Containers](/virtualization/windowscontainers/about/index), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="1437a-105">Um Windows-Container zu verwenden, müssen Sie lediglich PowerShell-Befehle in die DockerFile-Datei schreiben, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1437a-105">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```Dockerfile
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="1437a-106">In diesem Fall verwenden wir Windows PowerShell, um ein Windows Server Core-Basisimage sowie IIS zu installieren.</span><span class="sxs-lookup"><span data-stu-id="1437a-106">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="1437a-107">In ähnlicher Weise können Sie auch Windows PowerShell-Befehle verwenden, um zusätzliche Komponenten wie das herkömmliche ASP.NET 4.x, .NET 4.6 oder andere Windows-Software einzurichten, wie hier zu sehen:</span><span class="sxs-lookup"><span data-stu-id="1437a-107">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET 4.6 or any other Windows software, as shown here:</span></span>

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
><span data-ttu-id="1437a-108">[Zurück](visual-studio-tools-for-docker.md)
>[Weiter](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="1437a-108">[Previous](visual-studio-tools-for-docker.md)
[Next](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)</span></span>
