---
title: 'Optimieren der Leistung: Weitere Empfehlungen'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Terminal Services rendering [WPF]
- opacity [WPF]
- hit-test objects [WPF]
- ScrollBarVisibility enumeration [WPF]
- brushes [WPF], performance
ms.assetid: d028cc65-7e97-4a4f-9859-929734eaf40d
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: afe0e93706089e1893d46316b33c2568df83ffd3
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="optimizing-performance-other-recommendations"></a>Optimieren der Leistung: Weitere Empfehlungen
<a name="introduction"></a> Dieses Thema enthält Empfehlungen zur Leistung zusätzlich zu denen im Abschnitt [Optimierung der WPF-Anwendungsleistung](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md).  
  
 Dieses Thema enthält folgende Abschnitte:  
  
-   [Opacity bei Brush-Elementen im Vergleich zu Opacity bei Elementen](#Opacity)  
  
-   [Navigation zum Objekt](#Navigation_Objects)  
  
-   [Treffertests auf großen 3D-Oberflächen](#Hit_Testing)  
  
-   [CompositionTarget.Rendering-Ereignis](#CompositionTarget_Rendering_Event)  
  
-   [Vermeiden von ScrollBarVisibility=Auto](#Avoid_Using_ScrollBarVisibility)  
  
-   [Konfigurieren des Diensts für den Schriftartencache zur Reduzierung der Startzeit](#FontCache)  
  
<a name="Opacity"></a>   
## <a name="opacity-on-brushes-versus-opacity-on-elements"></a>Opacity bei Brush-Elementen im Vergleich zu Opacity bei Elementen  
 Bei Verwendung einer <xref:System.Windows.Media.Brush> festzulegende der <xref:System.Windows.Shapes.Shape.Fill%2A> oder <xref:System.Windows.Shapes.Shape.Stroke%2A> eines Elements, es ist besser, legen Sie die <xref:System.Windows.Media.Brush.Opacity%2A?displayProperty=nameWithType> statt den Wert des Elements <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft. Ändern eines Elements <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft kann dazu führen, dass [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine temporäre Oberfläche erstellen.  
  
<a name="Navigation_Objects"></a>   
## <a name="navigation-to-object"></a>Navigation zum Objekt  
 Die <xref:System.Windows.Navigation.NavigationWindow> Objekt abgeleitet <xref:System.Windows.Window> und erweitert sie Dank der Unterstützung Inhaltsnavigation in erster Linie durch aggregieren <xref:System.Windows.Navigation.NavigationService> und die Erfassung. Sie können den Clientbereich des aktualisieren <xref:System.Windows.Navigation.NavigationWindow> durch Angeben einer [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] oder ein Objekt. Im folgenden Beispiel werden beide Methoden veranschaulicht:  
  
 [!code-csharp[Performance#PerformanceSnippet14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/TestNavigation.xaml.cs#performancesnippet14)]
 [!code-vb[Performance#PerformanceSnippet14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/testnavigation.xaml.vb#performancesnippet14)]  
  
 Jedes <xref:System.Windows.Navigation.NavigationWindow> Objekt verfügt über eine Erfassung, durch den Navigationsverlauf des Benutzers in diesem Fenster aufgezeichnet. Die Erfassung dient unter anderem dazu, Benutzern die Rückverfolgung ihrer Schritte zu ermöglichen.  
  
 Wenn Sie mithilfe eines [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] navigieren, speichert die Erfassung nur den [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]-Verweis. Dies bedeutet, dass die Seite bei jedem weiteren Besuch dynamisch rekonstruiert wird, was je nach Komplexität der Seite sehr zeitaufwändig sein kann. In diesem Fall wird für die Erfassung wenig Speicher beansprucht, aber für das Wiederherstellen der Seite ist möglicherweise viel Zeit nötig.  
  
 Wenn Sie mithilfe eines Objekts navigieren, speichert die Erfassung die gesamte visuelle Struktur des Objekts. Dies bedeutet, dass die Seite bei jedem weiteren Besuch sofort gerendert wird, ohne dass sie rekonstruiert werden muss. In diesem Fall wird für die Erfassung viel Speicher beansprucht, aber für das Wiederherstellen der Seite ist wenig Zeit nötig.  
  
 Bei Verwendung der <xref:System.Windows.Navigation.NavigationWindow> -Objekt, müssen Sie Bedenken Auswirkungen auf die Leistung Ihrer Anwendung die Journaling-Unterstützung. Weitere Informationen finden Sie unter [Übersicht über die Navigation](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
<a name="Hit_Testing"></a>   
## <a name="hit-testing-on-large-3d-surfaces"></a>Treffertests auf großen 3D-Oberflächen  
 Treffertests auf großen 3D-Oberflächen sind in Bezug auf CPU-Auslastung ein sehr aufwändiger Vorgang. Dies gilt insbesondere, wenn die 3D-Oberfläche animiert wird. Wenn Sie keine Treffertests auf diesen Oberflächen benötigen, sollten Sie die Treffertests deaktivieren. Objekte, die von der abgeleiteten <xref:System.Windows.UIElement> kann Treffertests deaktivieren, indem Sie festlegen der <xref:System.Windows.UIElement.IsHitTestVisible%2A> Eigenschaft `false`.  
  
<a name="CompositionTarget_Rendering_Event"></a>   
## <a name="compositiontargetrendering-event"></a>CompositionTarget.Rendering-Ereignis  
 Die <xref:System.Windows.Media.CompositionTarget.Rendering?displayProperty=nameWithType> -Ereignisses bewirkt, dass [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fortlaufend animiert. Wenn Sie dieses Ereignis verwenden, sollten Sie es bei jeder Gelegenheit trennen.  
  
<a name="Avoid_Using_ScrollBarVisibility"></a>   
## <a name="avoid-using-scrollbarvisibilityauto"></a>Vermeiden von ScrollBarVisibility=Auto  
 Verwenden Sie nach Möglichkeit die <xref:System.Windows.Controls.ScrollBarVisibility.Auto?displayProperty=nameWithType> Wert für die `HorizontalScrollBarVisibility` und `VerticalScrollBarVisibility` Eigenschaften. Diese Eigenschaften werden für definiert <xref:System.Windows.Controls.RichTextBox>, <xref:System.Windows.Controls.ScrollViewer>, und <xref:System.Windows.Controls.TextBox> Objekte, und als eine angefügte Eigenschaft für die <xref:System.Windows.Controls.ListBox> Objekt. Legen Sie stattdessen <xref:System.Windows.Controls.ScrollBarVisibility> auf <xref:System.Windows.Controls.ScrollBarVisibility.Disabled>, <xref:System.Windows.Controls.ScrollBarVisibility.Hidden>, oder <xref:System.Windows.Controls.ScrollBarVisibility.Visible>.  
  
 Die <xref:System.Windows.Controls.ScrollBarVisibility.Auto> Wert ist für Fälle vorgesehen, Speicherplatz beschränkt ist und Bildlaufleisten nur bei Bedarf angezeigt werden soll. Beispielsweise ist es möglicherweise hilfreich, diese zu verwenden <xref:System.Windows.Controls.ScrollBarVisibility> Wert mit einer <xref:System.Windows.Controls.ListBox> 30 Elemente im Gegensatz zu einer <xref:System.Windows.Controls.TextBox> mit Hunderten von Textzeilen.  
  
<a name="FontCache"></a>   
## <a name="configure-font-cache-service-to-reduce-start-up-time"></a>Konfigurieren des Diensts für den Schriftartencache zur Reduzierung der Startzeit  
 Der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Dienst für den Schriftartencache stellt Schriftartdaten über [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen hinweg zur Verfügung. Die erste [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendung, die Sie ausführen, startet diesen Dienst, wenn er noch nicht ausgeführt wird. Bei Verwendung von [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)], Sie können den Dienst "Windows Presentation Foundation (WPF) Schriftart Cache 3.0.0.0" auf "Automatisch (Start durch verzögerte)" aus "Manuell" (Standard) festlegen, reduzieren Sie die anfängliche Startzeit des [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendungen.  
  
## <a name="see-also"></a>Siehe auch  
 [Planen der Anwendungsleistung](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [Vorteile der Hardware nutzen](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [Layout und Entwurf](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [2D-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Objektverhalten](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [Anwendungsressourcen](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Datenbindung](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [Tipps und Tricks zu Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)
