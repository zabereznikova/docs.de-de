---
title: Mit .NET-Containern angezieltes Betriebssystem
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Mit .NET-Containern angezieltes Betriebssystem
ms.date: 01/07/2019
ms.openlocfilehash: dcf91f5ab808a8704201979f6bab1140c3343bce
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736909"
---
# <a name="what-os-to-target-with-net-containers"></a>Mit .NET-Containern angezieltes Betriebssystem

Durch die Vielzahl der von Docker unterstützten Betriebssysteme und die Unterschiede zwischen .NET Framework und .NET Core sollten Sie abhängig von dem Framework, das Sie verwenden, ein bestimmtes Betriebssystem und bestimmte Versionen anzielen.

Für Windows können Sie Windows Server Core oder Windows Nano Server verwenden. Diese Windows-Versionen bieten unterschiedliche Eigenschaften (IIS in Windows Server Core im Vergleich zu einem selbstgehosteten Webserver wie Kestrel in Nano Server), die jeweils für .NET Framework oder .NET Core erforderlich sind.

Für Linux sind mehrere Distributionen (z.B. Debian) verfügbar und werden in offiziellen .NET Docker-Images unterstützt.

In Abbildung 3-1 wird die mögliche Betriebssystemversion in Abhängigkeit vom verwendeten .NET Framework dargestellt.

![Diagramm, das zeigt, welches Betriebssystem mit welchen .NET-Containern zu verwenden ist.](./media/net-container-os-targets/targeting-operating-systems.png)

**Abbildung 3-1.** In Abhängigkeit der Version von .NET Framework anzuzielende Betriebssysteme

Bei der Bereitstellung von .NET Framework-Legacyanwendungen muss auf Windows Server Core abgezielt werden, das mit Legacyanwendungen und IIS kompatibel ist, aber ein größeres Image aufweist. Bei der Bereitstellung von .NET Core-Anwendungen kann Windows Nano Server als Zielplattform verwendet werden, das für die Cloud optimiert ist, Kestrel verwendet, kleiner ist und schneller startet. Auch Linux ist als Zielplattform geeignet; Debian, Alpine und andere werden unterstützt. Verwendet ebenfalls Kestrel, ist kleiner und startet schneller.

Sie können ebenfalls Ihr eigenes Docker-Image erstellen, wenn Sie eine andere Linux-Distribution verwenden oder wenn Sie ein Image mit nicht von Microsoft bereitgestellten Versionen verwenden möchten. Sie könnten beispielsweise ein Image erstellen, bei dem ASP.NET Core unter dem herkömmlichen .NET Framework und Windows Server Core ausgeführt wird. Dabei handelt es sich um ein für Docker ungewöhnliches Szenario.

> [!IMPORTANT]
> Wenn Sie Windows Server Core-Images verwenden, stellen Sie möglicherweise fest, dass im Vergleich zu vollständigen Windows-Images einige DLLs fehlen. Sie können dieses Problem möglicherweise beheben, indem Sie ein benutzerdefiniertes Server Core-Image erstellen und die fehlenden Dateien zum Zeitpunkt der Imageerstellung hinzufügen, wie in diesem [GitHub-Kommentar](https://github.com/microsoft/dotnet-framework-docker/issues/299#issuecomment-511537448) beschrieben.

Wenn Sie den Namen des Images zu Ihrer Dockerfile-Datei hinzufügen, können Sie das Betriebssystem und die Version wie in den folgenden Beispielen dargestellt in Abhängigkeit vom verwendeten Tag auswählen:

| Bild | Kommentare |
|-------|----------|
| mcr.microsoft.com/dotnet/core/runtime:2.2 | Mehrere .NET Core 2.2-Architekturen: Unterstützt Linux und Windows Nano Server, abhängig vom Docker-Host. |
| mcr.microsoft.com/dotnet/core/aspnet:2.2 | Mehrere ASP.NET Core 2.2-Architekturen: Unterstützt Linux und Windows Nano Server, abhängig vom Docker-Host. <br/> Das aspnetcore-Image enthält einige Optimierungen für ASP.NET Core. |
| mcr.microsoft.com/dotnet/core/aspnet:2.2-alpine | Unter Linux Alpine-Distribution nur .NET Core 2.2-Runtime |
| mcr.microsoft.com/dotnet/core/aspnet:2.2-nanoserver-1803 | Unter Windows Nano Server (Windows Server, Version 1803) nur .NET Core 2.2-Runtime |

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **BitmapDecoder schlägt fehl, weil „WindowsCodecsExt.dll“ fehlt (GitHub-Issue)**  
  <https://github.com/microsoft/dotnet-framework-docker/issues/299>

> [!div class="step-by-step"]
> [Zurück](container-framework-choice-factors.md)
> [Weiter](official-net-docker-images.md)
