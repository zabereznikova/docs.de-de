---
title: Mit .NET-Containern angezieltes Betriebssystem
description: ".NET-Microservicesarchitektur für .NET-Containeranwendungen | Mit .NET-Containern angezieltes Betriebssystem"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ef7a21efa23be3a5181f08066a093abbb915c20f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="what-os-to-target-with-net-containers"></a>Mit .NET-Containern angezieltes Betriebssystem

Durch die Vielzahl der von Docker unterstützten Betriebssysteme und die Unterschiede zwischen .NET Framework und .NET Core sollten Sie abhängig von dem Framework, das Sie verwenden, ein bestimmtes Betriebssystem und bestimmte Versionen anzielen. 

Für Windows können Sie Windows Server Core oder Windows Nano Server verwenden. Diese Windows-Versionen bieten unterschiedliche Eigenschaften (IIS in Windows Server Core im Vergleich zu einem selbstgehosteten Webserver wie Kestrel in Nano Server), die jeweils für .NET Framework oder .NET Core erforderlich sind. 

Für Linux sind mehrere Distributionen (z.B. Debian) verfügbar und werden in offiziellen .NET Docker-Images unterstützt.

In Abbildung 3-1 wird die mögliche Betriebssystemversion in Abhängigkeit vom verwendeten .NET Framework dargestellt.

![](./media/image1.png)

**Abbildung 3-1.** In Abhängigkeit der Version von .NET Framework anzuzielende Betriebssysteme

Sie können ebenfalls Ihr eigenes Docker-Image erstellen, wenn Sie eine andere Linux-Distribution verwenden oder wenn Sie ein Image mit nicht von Microsoft bereitgestellten Versionen verwenden möchten. Sie könnten beispielsweise ein Image erstellen, bei dem ASP.NET Core unter dem herkömmlichen .NET Framework und Windows Server Core ausgeführt wird. Dabei handelt es sich um ein für Docker ungewöhnliches Szenario.

Wenn Sie den Namen des Images zu Ihrer Dockerfile-Datei hinzufügen, können Sie das Betriebssystem und die Version wie in den folgenden Beispielen dargestellt in Abhängigkeit vom verwendeten Tag auswählen:

-   microsoft/**dotnet:2.0.0-runtime-jessie**

        .NET Core 2.0 runtime-only on Linux

-   microsoft/**dotnet:2.0.0-runtime-nanoserver-1709** 

        .NET Core 2.0 runtime-only on Windows Nano Server (Windows Server 2016 Fall Creators Update version 1709)

-   microsoft/**aspnetcore:2.0**
    
        .NET Core 2.0 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.
        The aspnetcore image has a few optimizations for ASP.NET Core. 





>[!div class="step-by-step"]
[Zurück] (container-framework-choice-factors.md) [Weiter] (official-net-docker-images.md)
