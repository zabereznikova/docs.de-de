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
ms.openlocfilehash: 7acf5a3f48ac4987037873c63111d988ec3a4979
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629651"
---
# <a name="optimizing-performance-taking-advantage-of-hardware"></a>Optimieren der Leistung: Nutzen der Vorteile der Hardware
Die interne Architektur von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] umfasst zwei Renderingpipelines: Hardware und Software. Dieses Thema enthält Informationen zu diesen Renderingpipelines, die Ihnen helfen, Entscheidungen über Leistungsoptimierungen Ihrer Anwendungen zu treffen.  
  
## <a name="hardware-rendering-pipeline"></a>Hardwarrenderpipeline  
 Einer der wichtigsten Faktoren bei der Bestimmung [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] der Leistung besteht darin, dass er an das Rendering gebunden ist – abhängig von mehr Pixeln müssen Sie die Leistungseinbußen erhöhen. Wenn Sie jedoch mehr Rendering in die [!INCLUDE[TLA#tla_gpu](../../../../includes/tlasharptla-gpu-md.md)]auslagern können, desto mehr Leistungsvorteile können Sie erzielen. Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungs Hardware-Renderingpipeline nutzt die Vorteile der Microsoft DirectX-Features auf Hardware, die mindestens die Microsoft DirectX-Version 7,0 unterstützt. Weitere Optimierungen können von Hardware erzielt werden, die die Features Microsoft DirectX, Version 7,0 und PixelShader 2.0 + unterstützt.  
  
## <a name="software-rendering-pipeline"></a>Software Rendering-Pipeline  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Software Rendering-Pipeline ist vollständig CPU-gebunden. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]nutzt die SSE-und SSE2-Anweisungs Sätze in der CPU, um einen optimierten, voll funktionsfähigen Software-Rasterizer zu implementieren. Ein Fallback auf Software ist nahtlos, wenn die Anwendungs Funktionalität nicht mithilfe der Hardware-Renderingpipeline gerendert werden kann.  
  
 Das größte Leistungsproblem, das beim Rendern im Software Modus auftritt, bezieht sich auf die Füllrate, die als die Anzahl der Pixel definiert ist, die Sie rendern. Wenn Sie sich Gedanken über die Leistung im Softwarerendering-Modus machen, versuchen Sie, die Anzahl der Neuerstellung eines Pixels zu minimieren. Wenn Sie z. b. eine Anwendung mit einem blauen Hintergrund haben, die dann ein leicht transparentes Bild darüber rendert, werden Sie alle Pixel in der Anwendung zweimal rendern. Folglich dauert es doppelt so lange, bis die Anwendung mit dem Bild gerengt wird, als wenn Sie nur den blauen Hintergrund haben.  
  
### <a name="graphics-rendering-tiers"></a>Renderingebenen für Grafiken  
 Es kann sehr schwierig sein, die Hardwarekonfiguration vorherzusagen, auf der Ihre Anwendung ausgeführt wird. Möglicherweise möchten Sie jedoch ein Design in Erwägung ziehen, das es Ihrer Anwendung ermöglicht, Features bei der Ausführung auf einer anderen Hardware nahtlos zu wechseln, damit Sie die verschiedenen Hardware Konfigurationen voll ausschöpfen können.  
  
 Um dies zu erreichen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , stellt die Funktionalität bereit, um die Grafik Funktion eines Systems zur Laufzeit zu bestimmen. Die Grafik Funktion wird bestimmt, indem die Grafikkarte als eine von drei renderingfunktionsstufen kategorisiert wird. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]macht eine API verfügbar, die einer Anwendung das Abfragen der renderingfunktionsebene ermöglicht. Abhängig von der von der Hardware unterstützten Renderingebene kann die Anwendung dann unterschiedliche Codepfade zur Laufzeit verwenden.  
  
 Die Funktionen der Grafikhardware, die sich am stärksten auf die Renderingebenen auswirken, sind:  
  
- **Video-RAM**: Die Videospeichermenge der Grafikhardware bestimmt die Größe und Anzahl der Puffer, die für die Zusammensetzung von Grafiken verwendet werden kann.  
  
- **Pixel-Shader**: Ein Pixel-Shader ist eine Grafikprozessorfunktion, die Auswirkungen auf eine Pro-Pixel-Basis berechnet. Abhängig von der Auflösung der angezeigten Grafiken kann es mehrere Millionen Pixel geben, die für jeden Frame des Displays verarbeitet werden müssen.  
  
- **Vertex-Shader**: Ein Vertex-Shader ist eine Grafikprozessorfunktion, die mathematische Operationen für die Vertexdaten des Objekts ausführt.  
  
- **Multitexturunterstützung**: Bei Multitexturunterstützung handelt es sich um die Möglichkeit, zwei oder mehr unterschiedliche Texturen während eines Mischvorgangs für ein 3D-Grafikobjekt anzuwenden. Der Grad der Multitexturunterstützung wird durch die Anzahl der Multitextureinheiten in der Grafikhardware bestimmt.  
  
 Die Pixel-Shader-, Vertex-Shader-und Multitextur-Funktionen werden verwendet, um bestimmte DirectX-Versions Ebenen zu definieren, die wiederum zum Definieren der verschiedenen renderingstufen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]verwendet werden.  
  
 Die Funktionen der Grafikhardware bestimmen die Renderingfunktion einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung. Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-System definiert drei Renderingebenen:  
  
- **Renderingebene 0**: Keine Beschleunigung der Grafikhardware. Die DirectX-Versions Ebene ist kleiner als Version 7,0.  
  
- **Renderingebene 1** Beschleunigung der Teil Grafikhardware. Die DirectX-Versions Ebene ist größer als oder gleich Version 7,0 und **kleiner** als Version 9,0.  
  
- **Renderingebene 2**: Die meisten Grafikfunktionen verwenden die Beschleunigung der Grafikhardware. Die DirectX-Versions Ebene ist größer als oder gleich Version 9,0.  
  
 Weitere Informationen zu [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] renderingstufen finden Sie unter Renderingebenen für [Grafiken](graphics-rendering-tiers.md).  
  
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
