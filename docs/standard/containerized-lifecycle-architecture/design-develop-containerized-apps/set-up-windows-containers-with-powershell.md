---
title: Verwenden von Windows PowerShell-Befehle in einer dockerfile-Datei zum Einrichten der Windows-Container (Docker standard basierend)
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.openlocfilehash: d68378a12a16dd4072b381f00241e781b40c3e16
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105549"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="63f59-103">Verwenden von Windows PowerShell-Befehle in einer dockerfile-Datei zum Einrichten der Windows-Container (Docker standard basierend)</span><span class="sxs-lookup"><span data-stu-id="63f59-103">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="63f59-104">Mit [Windows-Containern](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), können Sie Ihre vorhandenen Windows-Anwendungen zum Docker-Images zu konvertieren und mit den gleichen Tools wie der Rest des Docker-Ökosystem bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="63f59-104">With [Windows Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="63f59-105">Um Windows-Container zu verwenden, müssen Sie nur Windows PowerShell-Befehle in die dockerfile-Datei zu schreiben, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="63f59-105">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="63f59-106">Windows PowerShell verwenden wir in diesem Fall um ein Windows Server Core-Basis-Image sowie IIS zu installieren.</span><span class="sxs-lookup"><span data-stu-id="63f59-106">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="63f59-107">Auf ähnliche Weise, außerdem können Sie Windows PowerShell-Befehlen einrichten, zusätzliche Komponenten wie die herkömmlichen ASP.NET 4.x und .NET 4.6 oder andere Windows-Software, wie hier gezeigt:</span><span class="sxs-lookup"><span data-stu-id="63f59-107">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET 4.6 or any other Windows software, as shown here:</span></span>

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
<span data-ttu-id="63f59-108">[Zurück](visual-studio-tools-for-docker.md)
[Weiter](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="63f59-108">[Previous](visual-studio-tools-for-docker.md)
[Next](../docker-devops-workflow/index.md)</span></span>
