---
title: 'Optimieren der Leistung: Anwendungsressourcen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application resources [WPF], performance
- resources [WPF], performance
- static resources [WPF]
- sharing resources [WPF]
- brushes [WPF], performance
- sharing brushes without copying [WPF]
ms.assetid: 62b88488-c08e-4804-b7de-a1c34fbe929c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ac462f3b49788fd909f9d9f4fc785db74704ff6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="optimizing-performance-application-resources"></a>Optimieren der Leistung: Anwendungsressourcen
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ermöglicht Ihnen Anwendungsressourcen zu teilen, sodass Sie ein konsistentes Erscheinungsbild und Verhalten über Elemente mit ähnlichen Typs unterstützen können. Dieses Thema enthält einige Empfehlungen in diesem Bereich an, die Ihnen helfen kann die Leistung Ihrer Anwendungen verbessern.  
  
 Weitere Informationen zu Ressourcen finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
## <a name="sharing-resources"></a>Freigeben von Ressourcen  
 Wenn die Anwendung benutzerdefinierte Steuerelemente verwendet, und definiert die Ressourcen in einer <xref:System.Windows.ResourceDictionary> (oder Ressourcen für XAML-Knoten), es wird empfohlen, dass Sie entweder die Ressourcen zu definieren die <xref:System.Windows.Application> oder <xref:System.Windows.Window> -Objekt Ebene zu definieren oder diese in das Standarddesign für die Benutzerdefinierte Steuerelemente. Definieren von Ressourcen in eines benutzerdefinierten Steuerelements <xref:System.Windows.ResourceDictionary> erzwingt Auswirkungen auf die Leistung für jede Instanz des Steuerelements. Wenn Sie rechenintensive Pinselvorgänge, die als Teil der Ressourcendefinition eines benutzerdefinierten Steuerelements und viele Instanzen des benutzerdefinierten Steuerelements definiert haben, wird Arbeitssatz für die Anwendung z. B. erheblich verlängern.  
  
 Um diesen Punkt zu veranschaulichen, ist Folgendes zu berücksichtigen. Angenommen, Sie entwickeln eine Karte Spiel mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Für die meisten Kartenspiele benötigen Sie 52 Karten mit 52 verschiedenen Bildern. Ein Karte benutzerdefiniertes Steuerelement zu implementieren möchten, und Sie definieren 52 Pinsel (jeder ein Kartenbild darstellt), in den Ressourcen des benutzerdefinierten Kartensteuerelements. In der main-Anwendung erstellen Sie zunächst 52 Instanzen dieses benutzerdefinierte Karte-Steuerelements. Jede Instanz des benutzerdefinierten Kartensteuerelements generiert 52 Instanzen von <xref:System.Windows.Media.Brush> Objekte, die Sie insgesamt 52 * 52 erhalten <xref:System.Windows.Media.Brush> Objekte in der Anwendung. Durch Verschieben der Pinsel, der Karte benutzerdefiniertes Steuerelement Ressourcen, um die <xref:System.Windows.Application> oder <xref:System.Windows.Window> Objektebene oder definieren sie in das Standarddesign für das benutzerdefinierte Steuerelement den Arbeitssatz von der Anwendung zu reduzieren, da Sie jetzt 52 Pinsel freigeben 52 Instanzen des Kartensteuerelements.  
  
## <a name="sharing-a-brush-without-copying"></a>Freigeben eines Pinsels ohne kopieren  
 Wenn stehen Ihnen mehrere Elemente, die unter Verwendung des gleichen <xref:System.Windows.Media.Brush> Objekt, das den Pinsel als Ressource definieren und verweisen darauf, statt den Pinsel Inline in definieren [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]. Diese Methode erstellt eine Instanz und erneut verwendet, wohingegen Pinsel Inline im definieren [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] erstellt eine neue Instanz für jedes Element.  
  
 Das folgende Markupbeispiel veranschaulicht diesen Punkt:  
  
 [!code-xaml[Performance#PerformanceSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/BrushResource.xaml#performancesnippet7)]  
  
## <a name="use-static-resources-when-possible"></a>Verwenden Sie statische Ressourcen nach Möglichkeit  
 Eine statische Ressource stellt einen Wert für alle XAML-Property-Attribut bereit, indem ein Verweis auf eine bereits definierte Ressource gesucht. Suchverhalten für diese Ressource ist analog zur Kompilierzeit Suche.  
  
 Eine dynamische Ressource andererseits, erstellt einen temporären Ausdruck bei der ersten Kompilierung und somit Suche nach Ressourcen verzögern, bis der Wert für die angeforderte Ressource tatsächlich erforderlich, um ein Objekt zu erstellen ist. Suchverhalten für diese Ressource ist analog zur Laufzeit-Suche, Auswirkungen auf die Leistung gelten. Verwenden Sie statische Ressourcen möglichst in der Anwendung, mit der dynamischen Ressourcen nur bei Bedarf an.  
  
 Das folgende Markupbeispiel zeigt die Verwendung beider Typen von Ressourcen:  
  
 [!code-xaml[Performance#PerformanceSnippet8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/DynamicResource.xaml#performancesnippet8)]  
  
## <a name="see-also"></a>Siehe auch  
 [Optimieren der WPF-Anwendungsleistung](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [Planen der Anwendungsleistung](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [Vorteile der Hardware nutzen](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [Layout und Entwurf](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [2D-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Objektverhalten](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Datenbindung](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [Weitere Leistungsempfehlungen](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
