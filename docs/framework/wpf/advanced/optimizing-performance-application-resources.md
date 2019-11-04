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
ms.openlocfilehash: 59b124c28ade0a6c5119b651ff935d460bf4516d
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458557"
---
# <a name="optimizing-performance-application-resources"></a>Optimieren der Leistung: Anwendungsressourcen
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ermöglicht es Ihnen, Anwendungs Ressourcen freizugeben, damit Sie ein konsistentes Aussehen oder Verhalten über ähnlich typisierte Elemente hinweg unterstützen können. Dieses Thema enthält einige Empfehlungen in diesem Bereich, mit denen Sie die Leistung Ihrer Anwendungen verbessern können.  
  
 Weitere Informationen zu Ressourcen finden Sie unter [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
## <a name="sharing-resources"></a>Freigeben von Ressourcen  
 Wenn Ihre Anwendung benutzerdefinierte Steuerelemente verwendet und Ressourcen in einem <xref:System.Windows.ResourceDictionary> (oder XAML-Ressourcenknoten) definiert, empfiehlt es sich, die Ressourcen auf der <xref:System.Windows.Application>-oder <xref:System.Windows.Window> Objektebene zu definieren oder Sie im Standarddesign für die benutzerdefinierten Steuerelemente zu definieren. Durch das Definieren von Ressourcen in der <xref:System.Windows.ResourceDictionary> eines benutzerdefinierten Steuer Elements wird für jede Instanz dieses Steuer Elements eine Beeinträchtigung der Leistung erzwungen. Wenn Sie z. b. über Leistungs intensive Pinsel Vorgänge verfügen, die als Teil der Ressourcendefinition eines benutzerdefinierten Steuer Elements und zahlreichen Instanzen des benutzerdefinierten Steuer Elements definiert sind, erhöht sich der Arbeits Satz der Anwendung erheblich.  
  
 Um diesen Punkt zu veranschaulichen, sollten Sie Folgendes beachten: Nehmen wir an, Sie entwickeln ein Kartenspiel mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Bei den meisten Karten spielen benötigen Sie 52 Karten mit 52 unterschiedlichen Gesichtern. Sie beschließen, ein benutzerdefiniertes Karten Steuerelement zu implementieren, und Sie definieren 52 Pinsel (die jeweils ein Karten Gesicht darstellen) in den Ressourcen des benutzerdefinierten Karten Steuer Elements. In ihrer Hauptanwendung erstellen Sie anfänglich 52 Instanzen dieses kartenbenutzer definierten Steuer Elements. Jede Instanz des benutzerdefinierten Karten Steuer Elements generiert 52 Instanzen von <xref:System.Windows.Media.Brush> Objekten, sodass Sie insgesamt 52 * 52 <xref:System.Windows.Media.Brush> Objekte in Ihrer Anwendung erhalten. Wenn Sie die Pinsel aus den benutzerdefinierten Steuerelement Ressourcen der Karte auf die <xref:System.Windows.Application>-oder <xref:System.Windows.Window> Objektebene verschieben oder Sie im Standarddesign für das benutzerdefinierte Steuerelement definieren, verringern Sie das Workingset der Anwendung, da Sie nun die 52-Pinsel unter 52 freigeben. Instanzen des Karten Steuer Elements.  
  
## <a name="sharing-a-brush-without-copying"></a>Freigeben eines Pinsels ohne Kopieren  
 Wenn Sie über mehrere Elemente verfügen, die dasselbe <xref:System.Windows.Media.Brush> Objekt verwenden, definieren Sie den Pinsel als Ressource, und verweisen Sie darauf, anstatt den Pinsel Inline in XAML zu definieren. Diese Methode erstellt eine Instanz und verwendet Sie erneut, während die Definition von Pinseln inline in XAML eine neue-Instanz für jedes Element erstellt.  
  
 Das folgende Markup Beispiel veranschaulicht diesen Punkt:  
  
 [!code-xaml[Performance#PerformanceSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/BrushResource.xaml#performancesnippet7)]  
  
## <a name="use-static-resources-when-possible"></a>Verwenden Sie nach Möglichkeit statische Ressourcen.  
 Eine statische Ressource stellt einen Wert für jedes XAML-Eigenschafts Attribut bereit, indem Sie einen Verweis auf eine bereits definierte Ressource sucht. Das Suchverhalten für diese Ressource entspricht der Kompilierzeit Suche.  
  
 Eine dynamische Ressource erstellt hingegen während der anfänglichen Kompilierung einen temporären Ausdruck und verzögert so die Suche nach Ressourcen, bis der angeforderte Ressourcen Wert tatsächlich benötigt wird, um ein Objekt zu erstellen. Das Suchverhalten für diese Ressource entspricht der Lauf Zeit Suche, was zu Leistungseinbußen führt. Verwenden Sie nach Möglichkeit statische Ressourcen in Ihrer Anwendung, und verwenden Sie dynamische Ressourcen nur bei Bedarf.  
  
 Im folgenden Markup Beispiel wird die Verwendung beider Ressourcentypen veranschaulicht:  
  
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
