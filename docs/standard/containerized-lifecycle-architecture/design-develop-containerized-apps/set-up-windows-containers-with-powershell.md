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
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a>Verwenden von Windows PowerShell-Befehle in einer dockerfile-Datei zum Einrichten der Windows-Container (Docker standard basierend)

Mit [Windows-Containern](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), können Sie Ihre vorhandenen Windows-Anwendungen zum Docker-Images zu konvertieren und mit den gleichen Tools wie der Rest des Docker-Ökosystem bereitstellen.

Um Windows-Container zu verwenden, müssen Sie nur Windows PowerShell-Befehle in die dockerfile-Datei zu schreiben, wie im folgenden Beispiel gezeigt:

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

Windows PowerShell verwenden wir in diesem Fall um ein Windows Server Core-Basis-Image sowie IIS zu installieren.

Auf ähnliche Weise, außerdem können Sie Windows PowerShell-Befehlen einrichten, zusätzliche Komponenten wie die herkömmlichen ASP.NET 4.x und .NET 4.6 oder andere Windows-Software, wie hier gezeigt:

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
[Zurück](visual-studio-tools-for-docker.md)
[Weiter](../docker-devops-workflow/index.md)
