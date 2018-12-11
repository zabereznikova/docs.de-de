---
title: Verwenden von Windows PowerShell-Befehle in einer dockerfile-Datei zum Einrichten der Windows-Container (Docker-standard basierend)
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.openlocfilehash: 5e85beea0efbee6a2b6594e3a49d705505a36e1c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149392"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a>Verwenden von Windows PowerShell-Befehle in einer dockerfile-Datei zum Einrichten der Windows-Container (Docker-standard basierend)

Mit [Windows-Containern](/virtualization/windowscontainers/about/index), Sie können Ihre vorhandenen Windows-Anwendungen zu Docker-Images zu konvertieren und diese mit den gleichen Tools wie der Rest des Docker-Ökosystems bereitstellen.

Um Windows-Container verwenden, müssen Sie nur Windows PowerShell-Befehle in der dockerfile-Datei zu schreiben, wie im folgenden Beispiel gezeigt:

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

In diesem Fall verwenden wir Windows PowerShell, um zu einem Windows Server Core-Basisimage sowie die IIS installieren.

Auf ähnliche Weise, außerdem können Windows PowerShell-Befehle zum Einrichten von zusätzlicher Komponenten wie herkömmliche ASP.NET 4.x und .NET 4.6 oder andere Windows-Software, wie hier gezeigt:

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
>[Zurück](visual-studio-tools-for-docker.md)
>[Weiter](../docker-devops-workflow/index.md)
