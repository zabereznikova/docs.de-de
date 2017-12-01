---
title: Welche Ziel mit .NET Container des Betriebssystems
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Welche Ziel mit .NET Container des Betriebssystems"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 828ccb5e7a76f9419e80793b6cb3a6ba24f358cf
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="what-os-to-target-with-net-containers"></a>Welche Ziel mit .NET Container des Betriebssystems

Angesichts die Vielfalt von Docker und die Unterschiede zwischen .NET Framework und .NET Core unterstützten Betriebssysteme, sollten Sie auf einem bestimmten Betriebssystem und bestimmten Versionen, je nachdem das Framework verwendeten abzielen. 

Für Windows können Sie Windows Server Core oder Windows Nano Server verwenden. Diese Windows-Versionen bieten unterschiedliche Eigenschaften (IIS unter Windows Server Core im Vergleich zu einem selbst gehosteten Webserver wie Kestrel in Nano Server), die jeweils möglicherweise von .NET Framework oder .NET Core benötigt wird. 

Für Linux sind-Distributionen mehrere verfügbar und in der offiziellen .NET Docker-Images (z. B. Debian) unterstützten.

In Abbildung 3 – 1 sehen Sie die mögliche Version des Betriebssystems abhängig von der .NET Framework verwendet.

![](./media/image1.png)

**Abbildung 3 minus 1.** Abhängig von Versionen von .NET Framework als Ziel-Betriebssysteme

Sie können auch Ihr eigenes Image von Docker in Fällen erstellen, eine andere Linux-Distribution verwendet werden soll, oder ein Bild mit Versionen, die nicht von Microsoft bereitgestellt werden soll. Sie können z. B. ein Image erstellen, mit ASP.NET Core auf herkömmliche .NET Framework und Windows Server Core eine nicht damit üblichen Szenario für Docker ist ausgeführt wird.

Wenn Sie die Dockerfile-Datei den Namen des Abbilds hinzugefügt haben, können Sie auswählen, das Betriebssystem und Version je nach Tag, das Sie, das wie in den folgenden Beispielen verwenden:

-   Microsoft /**Dotnet:2.0.0-Runtime-Jessie**

        .NET Core 2.0 runtime-only on Linux

-   Microsoft /**Dotnet:2.0.0-Runtime-Nanoserver-1709** 

        .NET Core 2.0 runtime-only on Windows Nano Server (Windows Server 2016 Fall Creators Update version 1709)

-   Microsoft /**Aspnetcore:2.0**
    
        .NET Core 2.0 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.
        The aspnetcore image has a few optimizations for ASP.NET Core. 





>[!div class="step-by-step"]
[Vorherigen] (Container-Framework-Choice-factors.md) [weiter] (offiziellen-Net-Docker-images.md)
