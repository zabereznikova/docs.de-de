---
title: "Optimieren der Leistung: Anwendungsressourcen | Microsoft Docs"
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
  - "Anwendungsressourcen, Leistung"
  - "Pinsel, Leistung"
  - "Ressourcen, Leistung"
  - "Freigeben von Pinseln ohne Kopieren"
  - "Gemeinsame Nutzung von Ressourcen"
  - "Statische Ressourcen"
ms.assetid: 62b88488-c08e-4804-b7de-a1c34fbe929c
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Optimieren der Leistung: Anwendungsressourcen
Mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können Sie Anwendungsressourcen freigeben, sodass Sie ein konsistentes Erscheinungsbild und Verhalten für alle Elemente eines ähnlichen Typs unterstützen können.  Dieses Thema stellt einige Empfehlungen in diesem Bereich bereit, die Ihnen eine Hilfestellung bei der Verbesserung der Leistung für Ihre Anwendungen bieten.  
  
 Weitere Informationen zu Ressourcen finden Sie unter [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
## Freigeben von Ressourcen  
 Wenn die Anwendung benutzerdefinierte Steuerelemente verwendet und Ressourcen in einem <xref:System.Windows.ResourceDictionary> \(oder XAML\-Ressourcenknoten\) definiert, wird empfohlen, die Ressourcen entweder auf der <xref:System.Windows.Application>\-Objektebene oder auf der <xref:System.Windows.Window>\-Objektebene zu definieren oder diese im Standarddesign für die benutzerdefinierten Steuerelemente zu definieren.  Eine Definition von Ressourcen im <xref:System.Windows.ResourceDictionary> eines benutzerdefinierten Steuerelements hat negative Auswirkungen auf die Leistung für jede Instanz dieses Steuerelements.  Wenn Sie beispielsweise leistungsintensive Pinselvorgänge als Teil der Ressourcendefinition eines benutzerdefinierten Steuerelements und vieler Instanzen des benutzerdefinierten Steuerelements definiert haben, wird das Workingset der Anwendung erheblich vergrößert.  
  
 Betrachten Sie zur Veranschaulichung dieses Punkts Folgendes.  Angenommen, Sie möchten mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ein Kartenspiel entwickeln.  Für die meisten Kartenspiele benötigen Sie 52 Karten mit 52 verschiedenen Bildern.  Sie entscheiden sich dafür, ein benutzerdefiniertes Kartensteuerelement zu implementieren, und Sie definieren 52 Pinsel \(von denen jeder ein Kartenbild darstellt\) in den Ressourcen des benutzerdefinierten Kartensteuerelements.  In der Hauptanwendung erstellen Sie 52 Instanzen dieses benutzerdefinierten Kartensteuerelements.  Jede Instanz des benutzerdefinierten Kartensteuerelements generiert 52 Instanzen von <xref:System.Windows.Media.Brush>\-Objekten, sodass Sie insgesamt 52 \* 52 <xref:System.Windows.Media.Brush>\-Objekte in der Anwendung erhalten.  Durch Verschieben der Pinsel aus den benutzerdefinierten Kartensteuerelementressourcen in die <xref:System.Windows.Application>\-Objektebene oder die <xref:System.Windows.Window>\-Objektebene, oder indem Sie diese im Standarddesign für das benutzerdefinierte Steuerelement definieren, verkleinern Sie das Workingset der Anwendung, da Sie jetzt 52 Pinsel innerhalb von 52 Instanzen des Kartensteuerelements freigeben.  
  
## Freigeben eines Pinsels ohne Kopieren  
 Wenn Sie über mehrere Elemente verfügen, die dasselbe <xref:System.Windows.Media.Brush>\-Objekt verwenden, definieren Sie den Pinsel als Ressource und verweisen darauf, statt den Pinsel inline in [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] zu definieren.  Diese Methode erstellt eine Instanz und verwendet diese erneut, während durch das Definieren von Pinseln inline in [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] für jedes Element eine neue Instanz erstellt wird.  
  
 Im folgenden Markupbeispiel wird dieser Punkt veranschaulicht:  
  
 [!code-xml[Performance#PerformanceSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/BrushResource.xaml#performancesnippet7)]  
  
## Verwenden von statischen Ressourcen, sofern möglich  
 Eine statische Ressource stellt einen Wert für ein beliebiges XAML\-Eigenschaftenattribut bereit, indem nach einem Verweis auf eine bereits definierte Ressource gesucht wird.  Das Suchverhalten für diese Ressource ist analog zur Suche nach der Kompilierungszeit.  
  
 Andererseits erstellt eine dynamische Ressource während der erstmaligen Kompilierung einen temporären Ausdruck und schiebt daher die Suche nach Ressourcen auf, bis der angeforderte Ressourcenwert tatsächlich erforderlich ist, um ein Objekt zu konstruieren.  Das Suchverhalten für diese Ressource ist analog zu Laufzeitsuche, die Auswirkungen auf die Leistung erzwingt.  Verwenden Sie möglichst immer statische Ressourcen in der Anwendung. Dynamische Ressourcen sollten Sie nur dann verwenden, wenn dies notwendig ist.  
  
 In dem folgenden Markupbeispiel wird die Verwendung beider Typen von Ressourcen veranschaulicht:  
  
 [!code-xml[Performance#PerformanceSnippet8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/DynamicResource.xaml#performancesnippet8)]  
  
## Siehe auch  
 [Optimieren der WPF\-Anwendungsleistung](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [Planen der Anwendungsleistung](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [Nutzen der Vorteile der Hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [Layout und Entwurf](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [2D\-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Projektverhalten](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Datenbindung](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Weitere Leistungsempfehlungen](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)