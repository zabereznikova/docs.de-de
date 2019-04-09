---
title: 'Optimieren der Leistung: Nutzen der Vorteile der Hardware'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], performance
- hardware rendering pipeline [WPF]
- rendering tiers [WPF]
- graphics rendering tiers [WPF]
- graphics [WPF], rendering tiers
- software rendering pipeline [WPF]
ms.assetid: bfb89bae-7aab-4cac-a26c-a956eda8fce2
ms.openlocfilehash: 683804acf43065543fa5d4ffb1a5ecf7e5b4c49a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163175"
---
# <a name="optimizing-performance-taking-advantage-of-hardware"></a>Optimieren der Leistung: Nutzen der Vorteile der Hardware
Die interne Architektur des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügt über zwei Renderingpipelines, Hardware und Software. Dieses Thema enthält Informationen über diese Renderingpipelines, die Ihnen bei Ihren Entscheidungen zur leistungsoptimierung von Anwendungen helfen.  
  
## <a name="hardware-rendering-pipeline"></a>Hardwarerenderingpipeline  
 Einer der wichtigsten Faktoren bei der Bestimmung [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Leistung besteht darin, dass es renderbegrenzung – je mehr Pixel, die Sie gerendert werden, desto größer sind die Kosten für die Leistung müssen. Allerdings können mehr, der rendering verlagert werden, um die [!INCLUDE[TLA#tla_gpu](../../../../includes/tlasharptla-gpu-md.md)], die weitere Leistungsvorteile erhalten Sie. Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Hardwarerenderingpipeline Anwendung nutzt [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] Funktionen auf Hardware, die mindestens unterstützt [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] Version 7.0. Weitere Optimierungen gewonnen werden können, von der Hardware, die unterstützt [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] , Version 7.0 und PixelShader 2.0 +-Funktionen.  
  
## <a name="software-rendering-pipeline"></a>Softwarerenderingpipeline  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Softwarerenderingpipeline ist vollständig CPU-gebunden. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nutzt die SSE- und SSE2-Anweisung wird in der CPU auf eine optimierte, voll ausgestattete Softwarerasterisierungsfunktion implementieren. Fallback auf die Software ist ein nahtlos jedes Mal, die Funktionalität der Anwendung nicht die Hardwarerenderingpipeline gerendert werden kann.  
  
 Die größten Leistungsprobleme treten Sie beim Rendern im Softwaremodus zusammenhängt Füllrate, die als die Anzahl der Pixel definiert ist, die gerendert werden. Wenn Sie über die Leistung in Softwarerenderingmodus Bedenken haben, versuchen Sie, wie oft zu minimieren, die eine Pixel neu gezeichnet wird. Z. B. wenn sich eine Anwendung mit einem blauen Hintergrund, die dann ein etwas transparentes Bild darüber gerendert wird, werden Sie alle Pixel in der Anwendung zweimal gerendert. Daher dauert zweimal so lange, um die Anwendung mit dem Image, als wenn Sie nur die blauen Hintergrund zu rendern.  
  
### <a name="graphics-rendering-tiers"></a>Renderingebenen für Grafiken  
 Es kann sehr schwierig sein, die Hardwarekonfiguration vorherzusagen, die Ihre Anwendung ausgeführt wird. Möglicherweise möchten jedoch einen Entwurf zu berücksichtigen, der können Ihre Anwendung nahtlos Features wechseln, wenn Sie auf andere Hardware ausgeführt, sodass sie alle Vorteile der einzelnen Konfigurationen anderer Hardware nutzen kann.  
  
 Um dies zu erreichen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet Funktionen, um die Grafik-Funktion von einem System zur Laufzeit zu bestimmen. Grafikfunktionen wird durch die Kategorisierung der Videokarte als eine der drei Ebenen der Funktion bestimmt. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Stellt eine [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] , mit der eine Anwendung die Renderingebene für die Funktion Abfragen können. Ihre Anwendung kann dann unterschiedliche Codepfade zur Laufzeit abhängig von der von der Hardware unterstützten Renderingebene ausführen.  
  
 Die Funktionen der Grafikhardware, die sich am stärksten auf die Renderingebenen auswirken, sind:  
  
-   **Video-RAM**: Die Videospeichermenge der Grafikhardware bestimmt die Größe und Anzahl der Puffer, die für die Zusammensetzung von Grafiken verwendet werden kann.  
  
-   **Pixel-Shader**: Ein Pixel-Shader ist eine Grafikprozessorfunktion, die Auswirkungen auf eine Pro-Pixel-Basis berechnet. Abhängig von der Auflösung der angezeigten Grafiken kann es mehrere Millionen Pixel geben, die für jeden Frame des Displays verarbeitet werden müssen.  
  
-   **Vertex-Shader**: Ein Vertex-Shader ist eine Grafikprozessorfunktion, die mathematische Operationen für die Vertexdaten des Objekts ausführt.  
  
-   **Multitexturunterstützung**: Bei Multitexturunterstützung handelt es sich um die Möglichkeit, zwei oder mehr unterschiedliche Texturen während eines Mischvorgangs für ein 3D-Grafikobjekt anzuwenden. Der Grad der Multitexturunterstützung wird durch die Anzahl der Multitextureinheiten in der Grafikhardware bestimmt.  
  
 Die Pixel-Shader, Vertex-Shader und multitextur-Features werden verwendet, um bestimmte definieren [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] Versionsebenen, die wiederum verwendet werden, definieren Sie die unterschiedlichen Ebenen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Die Funktionen der Grafikhardware bestimmen die Renderingfunktion einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung. Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-System definiert drei Renderingebenen:  
  
-   **Renderingebene 0**: Keine Beschleunigung der Grafikhardware. Die [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] -Versionsebene ist kleiner als die Version 7.0.  
  
-   **Renderingebene 1** Beschleunigung der partiellen Grafikhardware. Die [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] -Versionsebene ist größer als oder gleich 7.0 verwenden, und **weniger** als die Version 9.0.  
  
-   **Renderingebene 2**: Die meisten Grafikfunktionen verwenden die Beschleunigung der Grafikhardware. Die [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]-Versionsebene ist größer als oder gleich der Version 9.0.  
  
 Weitere Informationen zu [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Renderingebenen finden Sie [Renderingebenen für Grafiken](graphics-rendering-tiers.md).  
  
## <a name="see-also"></a>Siehe auch

- [Optimieren der WPF-Anwendungsleistung](optimizing-wpf-application-performance.md)
- [Planen der Anwendungsleistung](planning-for-application-performance.md)
- [Layout und Entwurf](optimizing-performance-layout-and-design.md)
- [2D-Grafiken und Bildverarbeitung](optimizing-performance-2d-graphics-and-imaging.md)
- [Objektverhalten](optimizing-performance-object-behavior.md)
- [Anwendungsressourcen](optimizing-performance-application-resources.md)
- [Text](optimizing-performance-text.md)
- [Datenbindung](optimizing-performance-data-binding.md)
- [Weitere Leistungsempfehlungen](optimizing-performance-other-recommendations.md)
