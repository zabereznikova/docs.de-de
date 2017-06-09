---
title: "Optimieren der Leistung: Vorteile der Hardware nutzen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Renderingebenen für Grafiken"
  - "Grafiken, Leistung"
  - "Grafiken, Renderingebenen"
  - "Hardwarerenderingpipeline"
  - "Renderingebenen"
  - "Softwarerenderingpipeline"
ms.assetid: bfb89bae-7aab-4cac-a26c-a956eda8fce2
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Optimieren der Leistung: Vorteile der Hardware nutzen
Die interne Architektur von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügt über zwei Renderingpipelines, Hardware und Software.  Dieses Thema enthält Informationen über diese Renderingpipelines, die Sie bei den Entscheidungen hinsichtlich Leistungsoptimierungen Ihrer Anwendungen unterstützen.  
  
## Hardwarerenderingpipeline  
 Einer der wichtigsten Faktoren bei der Bestimmung der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Leistung besteht darin, dass sie renderinggebunden ist \- je mehr Pixel gerendert werden müssen, desto höher sind die Kosten für die Leistung.  Je mehr Rendering jedoch an die [!INCLUDE[TLA#tla_gpu](../../../../includes/tlasharptla-gpu-md.md)] übergeben werden kann, desto mehr Leistungsvorteile sind möglich.  Die Hardwarerenderingpipeline der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung kann in vollem Umfang die Vorteile der [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)]\- Funktionen für Hardware nutzen, die mindestens [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] Version 7.0 unterstützt.  Weitere Optimierungen lassen sich bei Hardware erzielen, die [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)], Version 7.0, und PixelShader 2.0\+\-Funktionen unterstützt.  
  
## Softwarerenderingpipeline  
 Die Softwarerenderingpipeline von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist vollständig CPU\-gebunden.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nutzt die Vorteile der SSE\- und SSE2\-Anweisungssets der CPU, um eine optimierte und mit allen Funktionen ausgestattete Rasterisierungsfunktion zu implementieren.  Wenn beliebige Anwendungsfunktionalität nicht mit der Hardwarerenderingpipeline gerendert werden kann, kann nahtlos auf die Software zurückgegriffen werden.  
  
 Das größte Leistungsproblem, das beim Rendern im Softwaremodus auftreten kann, betrifft die Füllrate, die als Anzahl der Pixel definiert ist, die gerendert werden.  Wenn Sie Bedenken hinsichtlich der Leistung im Softwarerenderingmodus haben, minimieren Sie die Häufigkeit, mit der ein Pixel neu gezeichnet wird.  Beispielsweise werden bei einer Anwendung mit einem blauen Hintergrund, die dann ein leicht transparentes Bild auf diesem Hintergrund rendert, alle Pixel der Anwendung zweimal gerendert.  Deshalb nimmt das Rendern der Anwendung inklusive Bild doppelt soviel Zeit in Anspruch wie das alleinige Rendern des blauen Hintergrunds.  
  
### Renderingebenen für Grafiken  
 Möglicherweise ist es sehr schwierig, die Hardwarekonfiguration vorherzusagen, auf der die Anwendung ausgeführt wird.  Sie sollten jedoch einen Entwurf in Betracht ziehen, der es der Anwendung ermöglicht, bei der Ausführung auf unterschiedlicher Hardware nahtlos zwischen den Features zu wechseln. Auf diese Weise können die Vorteile der jeweiligen Hardwarekonfiguration vollständig genutzt werden.  
  
 Zu diesem Zweck stellt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Funktionalität bereit, um die Grafikfähigkeit eines Systems zur Laufzeit zu bestimmen.  Die Grafikfähigkeit wird durch die Kategorisierung der Videokarte als eine der drei Ebenen der Renderingfähigkeit bestimmt.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] macht eine [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] verfügbar, mit der eine Anwendung die Ebene der Renderingfähigkeit abfragen kann.  Je nach der von der Hardware unterstützten Renderingebene kann die Anwendung zur Laufzeit dann verschiedenen Codepfaden folgen.  
  
 Folgende Features der Grafikhardware wirken sich besonders stark auf die Renderingebenen aus:  
  
-   **Video\-RAM**: Der Umfang des Video\-Arbeitsspeichers der Grafikhardware bestimmt die Größe und Anzahl der Puffer, die für die Zusammensetzung von Grafiken verwendet werden können.  
  
-   **Pixelshader**: Ein Pixelshader ist eine Grafikverarbeitungsfunktion, die Effekte auf der Basis einzelner Pixel berechnet.  Je nach Auflösung der angezeigten Grafiken müssen möglicherweise für jeden angezeigten Frame mehrere Millionen Pixel verarbeitet werden.  
  
-   **Vertexshader**: Ein Vertexshader ist eine Grafikverarbeitungsfunktion, die mathematische Operationen für die Vertexdaten des Objekts ausführt.  
  
-   **Unterstützung von Mehrfachtexturen**: Hierbei handelt es sich um die Fähigkeit, während eines Blendingvorgangs mehrere unterschiedliche Texturen auf ein 3D\-Grafikobjekt anzuwenden.  Der Grad der Unterstützung von Mehrfachtexturen hängt von der Anzahl der Mehrfachtextureinheiten in der Grafikhardware ab.  
  
 Mithilfe der Features Pixelshader, Vertexshader und Mehrfachtextur werden bestimmte [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]\-Versionsebenen definiert, mit denen wiederum die unterschiedlichen Renderingebenen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] definiert werden.  
  
 Die Features der Grafikhardware bestimmen die Renderingfähigkeit einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung.  Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-System definiert drei Renderingebenen:  
  
-   **Renderingebene 0 \(null\)** Keine Grafikhardwarebeschleunigung.  Die [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]\-Versionsebene liegt in einer niedrigeren Version als 7.0 vor.  
  
-   **Renderingebene 1** Eingeschränkte Grafikhardwarebeschleunigung.  Die [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]\-Versionsebene liegt in mindestens Version 7.0 und einer **niedrigeren** Version als 9.0 vor.  
  
-   **Renderingebene 2** Die meisten Grafikfeatures verwenden die Grafikhardwarebeschleunigung.  Die [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]\-Versionsebene liegt mindestens in Version 9.0 vor.  
  
 Weitere Informationen über die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Renderingebenen finden Sie unter [Renderingebenen für Grafiken](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
## Siehe auch  
 [Optimieren der WPF\-Anwendungsleistung](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [Planen der Anwendungsleistung](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [Layout und Entwurf](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [2D\-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Projektverhalten](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [Anwendungsressourcen](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Datenbindung](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Weitere Leistungsempfehlungen](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)