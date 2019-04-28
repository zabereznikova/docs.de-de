---
title: Verwenden von Windows PowerShell-Befehle in einer dockerfile-Datei zum Einrichten der Windows-Container (Docker-standard basierend)
description: Erfahren Sie, wie Sie PowerShell verwenden, bei der Arbeit mit Docker in Windows-Containern
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: d9c0bc28f62d44eb7471b99c63055ef43da12a69
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61644644"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="c1524-103">Verwenden von Windows PowerShell-Befehle in einer dockerfile-Datei zum Einrichten der Windows-Container (Docker-standard basierend)</span><span class="sxs-lookup"><span data-stu-id="c1524-103">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="c1524-104">Mit [Windows-Containern](/virtualization/windowscontainers/about/index), Sie können Ihre vorhandenen Windows-Anwendungen zu Docker-Images zu konvertieren und diese mit den gleichen Tools wie der Rest des Docker-Ökosystems bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c1524-104">With [Windows Containers](/virtualization/windowscontainers/about/index), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="c1524-105">Um Windows-Container verwenden, müssen Sie nur Windows PowerShell-Befehle in der dockerfile-Datei zu schreiben, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="c1524-105">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```Dockerfile
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="c1524-106">In diesem Fall verwenden wir Windows PowerShell, um zu einem Windows Server Core-Basisimage sowie die IIS installieren.</span><span class="sxs-lookup"><span data-stu-id="c1524-106">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="c1524-107">Auf ähnliche Weise, außerdem können Windows PowerShell-Befehle zum Einrichten von zusätzlicher Komponenten wie herkömmliche ASP.NET 4.x und .NET 4.6 oder andere Windows-Software, wie hier gezeigt:</span><span class="sxs-lookup"><span data-stu-id="c1524-107">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET 4.6 or any other Windows software, as shown here:</span></span>

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
><span data-ttu-id="c1524-108">[Zurück](visual-studio-tools-for-docker.md)
>[Weiter](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="c1524-108">[Previous](visual-studio-tools-for-docker.md)
[Next](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)</span></span>
