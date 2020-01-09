---
title: 'Optimieren der Leistung: Weitere Empfehlungen'
ms.date: 03/30/2017
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
ms.openlocfilehash: b6d99d90a3da232e1873ebe8433e01ceb2977de6
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636431"
---
# <a name="optimizing-performance-other-recommendations"></a>Optimieren der Leistung: Weitere Empfehlungen
<a name="introduction"></a> Dieses Thema enthält Empfehlungen zur Leistung zusätzlich zu denen im Abschnitt [Optimierung der WPF-Anwendungsleistung](optimizing-wpf-application-performance.md).  
  
 Dieses Thema enthält folgende Abschnitte:  
  
- [Opacity bei Brush-Elementen im Vergleich zu Opacity bei Elementen](#Opacity)  
  
- [Navigation zum Objekt](#Navigation_Objects)  
  
- [Treffertests auf großen 3D-Oberflächen](#Hit_Testing)  
  
- [CompositionTarget.Rendering-Ereignis](#CompositionTarget_Rendering_Event)  
  
- [Vermeiden von ScrollBarVisibility=Auto](#Avoid_Using_ScrollBarVisibility)  
  
- [Konfigurieren des Diensts für den Schriftartencache zur Reduzierung der Startzeit](#FontCache)  
  
<a name="Opacity"></a>   
## <a name="opacity-on-brushes-versus-opacity-on-elements"></a>Opacity bei Brush-Elementen im Vergleich zu Opacity bei Elementen  
 Wenn Sie ein <xref:System.Windows.Media.Brush> verwenden, um die <xref:System.Windows.Shapes.Shape.Fill%2A> oder <xref:System.Windows.Shapes.Shape.Stroke%2A> eines Elements festzulegen, ist es besser, den <xref:System.Windows.Media.Brush.Opacity%2A?displayProperty=nameWithType> Wert anstelle der <xref:System.Windows.UIElement.Opacity%2A>-Eigenschaft des Elements festzulegen. Das Ändern der <xref:System.Windows.UIElement.Opacity%2A>-Eigenschaft eines Elements kann dazu führen, dass [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine temporäre Oberfläche erstellt.  
  
<a name="Navigation_Objects"></a>   
## <a name="navigation-to-object"></a>Navigation zum Objekt  
 Das <xref:System.Windows.Navigation.NavigationWindow> Objekt wird von <xref:System.Windows.Window> abgeleitet und erweitert es durch die Unterstützung von Inhalts Navigation, primär durch das aggregierten <xref:System.Windows.Navigation.NavigationService> und das Journal. Sie können den Client Bereich von <xref:System.Windows.Navigation.NavigationWindow> aktualisieren, indem Sie entweder einen URI (Uniform Resource Identifier) oder ein Objekt angeben. Im folgenden Beispiel werden beide Methoden veranschaulicht:  
  
 [!code-csharp[Performance#PerformanceSnippet14](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/TestNavigation.xaml.cs#performancesnippet14)]
 [!code-vb[Performance#PerformanceSnippet14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/testnavigation.xaml.vb#performancesnippet14)]  
  
 Jedes <xref:System.Windows.Navigation.NavigationWindow> Objekt verfügt über ein Journal, das den Navigationsverlauf des Benutzers in diesem Fenster aufzeichnet. Die Erfassung dient unter anderem dazu, Benutzern die Rückverfolgung ihrer Schritte zu ermöglichen.  
  
 Wenn Sie mit einem URI (Uniform Resource Identifier) navigieren, speichert das Journal nur den URI-Verweis (Uniform Resource Identifier). Dies bedeutet, dass die Seite bei jedem weiteren Besuch dynamisch rekonstruiert wird, was je nach Komplexität der Seite sehr zeitaufwändig sein kann. In diesem Fall wird für die Erfassung wenig Speicher beansprucht, aber für das Wiederherstellen der Seite ist möglicherweise viel Zeit nötig.  
  
 Wenn Sie mithilfe eines Objekts navigieren, speichert die Erfassung die gesamte visuelle Struktur des Objekts. Dies bedeutet, dass die Seite bei jedem weiteren Besuch sofort gerendert wird, ohne dass sie rekonstruiert werden muss. In diesem Fall wird für die Erfassung viel Speicher beansprucht, aber für das Wiederherstellen der Seite ist wenig Zeit nötig.  
  
 Wenn Sie das <xref:System.Windows.Navigation.NavigationWindow>-Objekt verwenden, müssen Sie Bedenken, wie sich die Journalunterstützung auf die Leistung Ihrer Anwendung auswirkt. Weitere Informationen finden Sie unter [Übersicht über die Navigation](../app-development/navigation-overview.md).  
  
<a name="Hit_Testing"></a>   
## <a name="hit-testing-on-large-3d-surfaces"></a>Treffertests auf großen 3D-Oberflächen  
 Treffertests auf großen 3D-Oberflächen sind in Bezug auf CPU-Auslastung ein sehr aufwändiger Vorgang. Dies gilt insbesondere, wenn die 3D-Oberfläche animiert wird. Wenn Sie keine Treffertests auf diesen Oberflächen benötigen, sollten Sie die Treffertests deaktivieren. Objekte, die von <xref:System.Windows.UIElement> abgeleitet werden, können Treffer Tests deaktivieren, indem Sie die <xref:System.Windows.UIElement.IsHitTestVisible%2A>-Eigenschaft auf `false`festlegen.  
  
<a name="CompositionTarget_Rendering_Event"></a>   
## <a name="compositiontargetrendering-event"></a>CompositionTarget.Rendering-Ereignis  
 Das <xref:System.Windows.Media.CompositionTarget.Rendering?displayProperty=nameWithType> Ereignis bewirkt, dass [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fortlaufend animieren. Wenn Sie dieses Ereignis verwenden, sollten Sie es bei jeder Gelegenheit trennen.  
  
<a name="Avoid_Using_ScrollBarVisibility"></a>   
## <a name="avoid-using-scrollbarvisibilityauto"></a>Vermeiden von ScrollBarVisibility=Auto  
 Vermeiden Sie nach Möglichkeit den <xref:System.Windows.Controls.ScrollBarVisibility.Auto?displayProperty=nameWithType> Wert für die Eigenschaften `HorizontalScrollBarVisibility` und `VerticalScrollBarVisibility`. Diese Eigenschaften sind für <xref:System.Windows.Controls.RichTextBox>-, <xref:System.Windows.Controls.ScrollViewer>-und <xref:System.Windows.Controls.TextBox>-Objekte und als angefügte Eigenschaft für das <xref:System.Windows.Controls.ListBox> Objekt definiert. Legen Sie stattdessen <xref:System.Windows.Controls.ScrollBarVisibility> auf <xref:System.Windows.Controls.ScrollBarVisibility.Disabled>, <xref:System.Windows.Controls.ScrollBarVisibility.Hidden>oder <xref:System.Windows.Controls.ScrollBarVisibility.Visible>fest.  
  
 Der <xref:System.Windows.Controls.ScrollBarVisibility.Auto> Wert ist für Fälle bestimmt, in denen der Speicherplatz begrenzt ist und Bild Lauf leisten nur angezeigt werden sollen, wenn dies erforderlich ist. Beispielsweise kann es sinnvoll sein, diesen <xref:System.Windows.Controls.ScrollBarVisibility> Wert mit einer <xref:System.Windows.Controls.ListBox> von 30 Elementen zu verwenden, im Gegensatz zu einer <xref:System.Windows.Controls.TextBox> mit Hunderten von Textzeilen.  
  
<a name="FontCache"></a>   
## <a name="configure-font-cache-service-to-reduce-start-up-time"></a>Konfigurieren des Diensts für den Schriftartencache zur Reduzierung der Startzeit  
 Der WPF-Schriftart Cache Dienst teilt Schriftart Daten zwischen WPF-Anwendungen. Die erste WPF-Anwendung, die Sie ausführen, startet diesen Dienst, wenn der Dienst nicht bereits ausgeführt wird. Wenn Sie Windows Vista verwenden, können Sie den "Windows Presentation Foundation (WPF)-Schriftart Cache 3.0.0.0"-Dienst von "manuell" (Standardeinstellung) auf "automatisch (verzögerter Start)" festlegen, um die anfängliche Startzeit von WPF-Anwendungen zu verringern.  
  
## <a name="see-also"></a>Siehe auch

- [Planen der Anwendungsleistung](planning-for-application-performance.md)
- [Vorteile der Hardware nutzen](optimizing-performance-taking-advantage-of-hardware.md)
- [Layout und Entwurf](optimizing-performance-layout-and-design.md)
- [2D-Grafiken und Bildverarbeitung](optimizing-performance-2d-graphics-and-imaging.md)
- [Objektverhalten](optimizing-performance-object-behavior.md)
- [Anwendungsressourcen](optimizing-performance-application-resources.md)
- [Text](optimizing-performance-text.md)
- [Datenbindung](optimizing-performance-data-binding.md)
- [Tipps und Tricks zu Animationen](../graphics-multimedia/animation-tips-and-tricks.md)
