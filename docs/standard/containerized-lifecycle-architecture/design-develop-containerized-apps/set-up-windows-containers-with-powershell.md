---
title: Verwenden von Windows PowerShell-Befehle in einer dockerfile-Datei zum Einrichten der Windows-Container (Docker standard basierend)
description: Lebenszyklus von Datenvolumes Docker-Anwendung mit Microsoft-Webplattform und Tools
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.openlocfilehash: f7e92b0f1c749e2c00e3afc4ffcfc2fc88d7628f
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2017
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="63f36-104">Verwenden von Windows PowerShell-Befehle in einer dockerfile-Datei zum Einrichten der Windows-Container (Docker standard basierend)</span><span class="sxs-lookup"><span data-stu-id="63f36-104">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="63f36-105">Mit [Windows-Containern](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), können Sie Ihre vorhandenen Windows-Anwendungen zum Docker-Images zu konvertieren und mit den gleichen Tools wie der Rest des Docker-Ökosystem bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="63f36-105">With [Windows Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="63f36-106">Um Windows-Container zu verwenden, müssen Sie nur Windows PowerShell-Befehle in die dockerfile-Datei zu schreiben, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="63f36-106">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="63f36-107">Windows PowerShell verwenden wir in diesem Fall um ein Windows Server Core-Basis-Image sowie IIS zu installieren.</span><span class="sxs-lookup"><span data-stu-id="63f36-107">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="63f36-108">Auf ähnliche Weise, außerdem können Sie Windows PowerShell-Befehlen einrichten, zusätzliche Komponenten wie die herkömmlichen ASP.NET 4.x und .NET 4.6 oder andere Windows-Software, wie hier gezeigt:</span><span class="sxs-lookup"><span data-stu-id="63f36-108">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET 4.6 or any other Windows software, as shown here:</span></span>

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
<span data-ttu-id="63f36-109">[Vorherigen] (Visual-Studio-Tools-für-docker.md) [weiter] (.. /docker-DevOps-Workflow/Index.MD)</span><span class="sxs-lookup"><span data-stu-id="63f36-109">[Previous] (visual-studio-tools-for-docker.md) [Next] (../docker-devops-workflow/index.md)</span></span>
