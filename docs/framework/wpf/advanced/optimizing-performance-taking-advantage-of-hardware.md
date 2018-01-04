---
title: 'Optimieren der Leistung: Vorteile der Hardware nutzen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], performance
- hardware rendering pipeline [WPF]
- rendering tiers [WPF]
- graphics rendering tiers [WPF]
- graphics [WPF], rendering tiers
- software rendering pipeline [WPF]
ms.assetid: bfb89bae-7aab-4cac-a26c-a956eda8fce2
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 55c9482ecb540baab3ddd57ca9350fd7265ac251
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="optimizing-performance-taking-advantage-of-hardware"></a>Optimieren der Leistung: Vorteile der Hardware nutzen
Der internen Architektur von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügt über zwei Renderingpipelines, Hardware und Software. Dieses Thema enthält Informationen zu dieser Renderingpipelines, um Entscheidungen zur leistungsoptimierung von Anwendungen treffen zu können.  
  
## <a name="hardware-rendering-pipeline"></a>Hardwarerenderingpipeline  
 Eines der wichtigsten Faktoren bei der Ermittlung [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Leistung ist die renderbegrenzung – Sie gerendert werden, desto größere sind die Kosten für die Leistung müssen mehr Pixel. Allerdings mehr rendering auf ausgelagert werden können die [!INCLUDE[TLA#tla_gpu](../../../../includes/tlasharptla-gpu-md.md)], die weitere Leistungsvorteile, die Sie gewinnen können. Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Hardwarerenderingpipeline Anwendung nutzt [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] Features auf Hardware, die mindestens unterstützt [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] Version 7.0. Weitere Optimierungen gewonnen werden können, von der Hardware, die unterstützt [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] , Version 7.0 und PixelShader 2.0 +-Funktionen.  
  
## <a name="software-rendering-pipeline"></a>Softwarerenderingpipeline  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Softwarerenderingpipeline basiert vollständig auf CPU-gebunden. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]nutzt die SSE- und SSE2-Anweisung wird in der CPU auf eine optimierte und gleichberechtigt Rasterisierungsfunktion zu implementieren. Fallback auf Software ist eine nahtlose jedes Mal, wenn in der Anwendungsfunktion die Hardwarerenderingpipeline gerendert werden kann.  
  
 Das größte Leistungsproblem treten beim Rendern in Software-Modus verknüpft ist, Füllrate, definiert als die Anzahl der Pixel, die gerendert werden. Wenn Sie über die Leistung in Software-Renderingmodus Bedenken haben, versuchen Sie, wie oft zu minimieren, die eine Pixel neu gezeichnet wird. Z. B. Wenn Sie eine Anwendung mit einem blauen Hintergrund, dann über diese ein leicht transparentes Bild gerendert wird verfügen, werden Sie alle Pixel in der Anwendung zweimal gerendert. Folglich dauert zweimal es zulässig, die die Anwendung mit dem Bild, als wenn Sie nur die blauen Hintergrund gerendert.  
  
### <a name="graphics-rendering-tiers"></a>Renderingebenen für Grafiken  
 Es ist möglicherweise sehr schwierig, die Hardwarekonfiguration vorherzusagen, die die Anwendung ausgeführt wird. Möglicherweise möchten Sie jedoch, einen Entwurf zu berücksichtigen, der Ihre Anwendung nahtlos Funktionen wechseln, wenn auf andere Hardware ausgeführt, damit sie vollständige jede Konfiguration auf anderer Hardware nutzen kann.  
  
 Um dies zu erreichen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt Funktionen bereit, die Grafikfunktionen eines Systems zur Laufzeit zu bestimmen. Grafikfunktionen wird durch die Kategorisierung der Videokarte als eine der drei Ebenen der Funktion bestimmt. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]macht eine [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] , mit dessen Hilfe einer Anwendung für die Ebene der Funktion Abfragen. Die Anwendung kann dann unterschiedlichen Codepfaden zur Laufzeit je nach der Renderingebene, die von der Hardware unterstützt vornehmen.  
  
 Die Funktionen der Grafikhardware, die sich am stärksten auf die Renderingebenen auswirken, sind:  
  
-   **Video-RAM**: Die Videospeichermenge der Grafikhardware bestimmt die Größe und Anzahl der Puffer, die für die Zusammensetzung von Grafiken verwendet werden kann.  
  
-   **Pixel-Shader**: Ein Pixel-Shader ist eine Grafikprozessorfunktion, die Auswirkungen auf eine Pro-Pixel-Basis berechnet. Abhängig von der Auflösung der angezeigten Grafiken kann es mehrere Millionen Pixel geben, die für jeden Frame des Displays verarbeitet werden müssen.  
  
-   **Vertex-Shader**: Ein Vertex-Shader ist eine Grafikprozessorfunktion, die mathematische Operationen für die Vertexdaten des Objekts ausführt.  
  
-   **Multitexturunterstützung**: Bei Multitexturunterstützung handelt es sich um die Möglichkeit, zwei oder mehr unterschiedliche Texturen während eines Mischvorgangs für ein 3D-Grafikobjekt anzuwenden. Der Grad der Multitexturunterstützung wird durch die Anzahl der Multitextureinheiten in der Grafikhardware bestimmt.  
  
 Die Pixel-Shader, Vertex-Shader und Mehrfachtextur Funktionen werden verwendet, um bestimmte definieren [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] Versionsebenen, die wiederum verwendet werden, definieren Sie die unterschiedlichen Renderingebenen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Die Funktionen der Grafikhardware bestimmen die Renderingfunktion einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung. Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-System definiert drei Renderingebenen:  
  
-   **Renderingebene 0**: Keine Beschleunigung der Grafikhardware. Die [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] Versionsebene ist kleiner als die Version 7.0.  
  
-   **Rendern von Ebene-1** Hardwarebeschleunigung teilweise Grafiken. Die [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] Versionsebene ist größer als oder gleich 7.0 verwenden, und **kleinere** als Version 9.0.  
  
-   **Renderingebene 2**: Die meisten Grafikfunktionen verwenden die Beschleunigung der Grafikhardware. Die [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]-Versionsebene ist größer als oder gleich der Version 9.0.  
  
 Weitere Informationen zu [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Renderingebenen finden Sie unter [Renderingebenen für Grafiken](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Optimieren der WPF-Anwendungsleistung](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [Planen der Anwendungsleistung](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [Layout und Entwurf](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [2D-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Objektverhalten](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [Anwendungsressourcen](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Datenbindung](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [Weitere Leistungsempfehlungen](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
