---
title: 'Optimieren der Leistung: Anwendungsressourcen'
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF], performance
- resources [WPF], performance
- static resources [WPF]
- sharing resources [WPF]
- brushes [WPF], performance
- sharing brushes without copying [WPF]
ms.assetid: 62b88488-c08e-4804-b7de-a1c34fbe929c
ms.openlocfilehash: 362d0f0fd3282365e5e05dcd43c49a9fd2ddc9a7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62017942"
---
# <a name="optimizing-performance-application-resources"></a>Optimieren der Leistung: Anwendungsressourcen
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können Sie Ressourcen freigeben, sodass Sie ein konsistentes Erscheinungsbild und Verhalten für Elemente mit ähnlichen Typs unterstützen können. Dieses Thema enthält einige Empfehlungen in diesem Bereich, mit denen Sie können die Leistung Ihrer Anwendungen verbessern.  
  
 Weitere Informationen zu Ressourcen finden Sie unter [XAML-Ressourcen](xaml-resources.md).  
  
## <a name="sharing-resources"></a>Gemeinsame Nutzung von Ressourcen  
 Wenn die Anwendung benutzerdefinierte Steuerelemente verwendet und definiert die Ressourcen in eine <xref:System.Windows.ResourceDictionary> (oder XAML-Ressourcen-Knoten), es wird empfohlen, dass Sie entweder die Ressourcen definieren die <xref:System.Windows.Application> oder <xref:System.Windows.Window> Objekt auf, oder definieren sie in das Standarddesign für die Benutzerdefinierte Steuerelemente. Definieren von Ressourcen in eines benutzerdefinierten Steuerelements <xref:System.Windows.ResourceDictionary> erzwingt Auswirkungen auf die Leistung für jede Instanz des Steuerelements. Wenn Sie den für rechenintensive Pinselvorgänge, die als Teil der Ressourcendefinition ein benutzerdefiniertes Steuerelement und viele Instanzen des benutzerdefinierten Steuerelements definiert haben, wird z. B. Workingset der Anwendung erheblich erhöhen.  
  
 Um diesen Punkt verdeutlichen, Folgendes zu beachten. Angenommen, Sie entwickeln eine Karte Spiele mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Für die meisten Kartenspiele benötigen Sie die 52 Karten mit 52 verschiedenen Bildern. Sie entscheiden, um eine benutzerdefinierte Karten-Steuerelement zu implementieren, und definieren Sie 52 Pinsel (jeder ein Kartenbild darstellt) in den Ressourcen des benutzerdefinierten Kartensteuerelements. In der main-Anwendung erstellen Sie zunächst 52 Instanzen dieses benutzerdefinierte Steuerelement der Karte. Jede Instanz des benutzerdefinierten Kartensteuerelements generiert 52 Instanzen von <xref:System.Windows.Media.Brush> -Objekte, die Sie insgesamt 52 * 52 erhalten <xref:System.Windows.Media.Brush> Objekte in der Anwendung. Durch Verschieben der Pinsel aus die Karte benutzerdefiniertes Steuerelementressourcen, um die <xref:System.Windows.Application> oder <xref:System.Windows.Window> Objektebene, oder sie in das Standarddesign für das benutzerdefinierte Steuerelement, definieren Sie das Workingset der Anwendung zu reduzieren, da Sie jetzt die 52 Pinsel freigeben zwischen 52 Instanzen des Kartensteuerelements.  
  
## <a name="sharing-a-brush-without-copying"></a>Freigeben eines Pinsels ohne kopieren  
 Wenn Sie mehrere Elemente, die mit dem gleichen haben <xref:System.Windows.Media.Brush> Objekt, definieren Sie den Pinsel als Ressource und verweisen darauf, statt den Pinsel Inline in definieren [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]. Diese Methode eine Instanz zu erstellen und erneut verwendet, während das Definieren von Pinseln Inline in [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] erstellt eine neue Instanz für jedes Element.  
  
 Im folgenden Markupbeispiel verdeutlicht dies:  
  
 [!code-xaml[Performance#PerformanceSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/BrushResource.xaml#performancesnippet7)]  
  
## <a name="use-static-resources-when-possible"></a>Verwenden Sie statische Ressourcen, wenn möglich  
 Eine statische Ressource stellt einen Wert für ein beliebiges XAML, indem ein Verweis auf einen bereits definierten Ressource gesucht. Das Suchverhalten für diese Ressource ist analog zur Kompilierzeit-Suche.  
  
 Eine dynamische Ressource, auf der anderen Seite erstellt einen temporäre Ausdruck während der erstmaligen Kompilierung und Suche nach Ressourcen daher verzögert, bis der Wert für die angeforderte Ressource tatsächlich erforderlich ist, um ein Objekt zu erstellen ist. Das Suchverhalten für diese Ressource ist analog zur Laufzeit-Suche, die Auswirkungen auf die Leistung erzwingt. Verwenden Sie statische Ressourcen möglichst in Ihrer Anwendung, die mithilfe von dynamischer Ressourcen nur bei Bedarf.  
  
 Im folgenden Markupbeispiel wird gezeigt, die Verwendung beider Arten von Ressourcen:  
  
 [!code-xaml[Performance#PerformanceSnippet8](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/DynamicResource.xaml#performancesnippet8)]  
  
## <a name="see-also"></a>Siehe auch

- [Optimieren der WPF-Anwendungsleistung](optimizing-wpf-application-performance.md)
- [Planen der Anwendungsleistung](planning-for-application-performance.md)
- [Vorteile der Hardware nutzen](optimizing-performance-taking-advantage-of-hardware.md)
- [Layout und Entwurf](optimizing-performance-layout-and-design.md)
- [2D-Grafiken und Bildverarbeitung](optimizing-performance-2d-graphics-and-imaging.md)
- [Objektverhalten](optimizing-performance-object-behavior.md)
- [Text](optimizing-performance-text.md)
- [Datenbindung](optimizing-performance-data-binding.md)
- [Weitere Leistungsempfehlungen](optimizing-performance-other-recommendations.md)
