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
ms.openlocfilehash: 727331adb41251460209f157d1804ff455bcf473
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186300"
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
 Wenn Sie <xref:System.Windows.Media.Brush> eine zum <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Shape.Stroke%2A> Festlegen des oder eines Elements <xref:System.Windows.Media.Brush.Opacity%2A?displayProperty=nameWithType> verwenden, ist es besser, <xref:System.Windows.UIElement.Opacity%2A> den Wert festzulegen, anstatt die Eigenschaft des Elements festzulegen. Das Ändern der <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft eines [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elements kann dazu führen, dass eine temporäre Oberfläche erstellt wird.  
  
<a name="Navigation_Objects"></a>
## <a name="navigation-to-object"></a>Navigation zum Objekt  
 Das <xref:System.Windows.Navigation.NavigationWindow> Objekt leitet <xref:System.Windows.Window> es ab und erweitert es mit Unterstützung <xref:System.Windows.Navigation.NavigationService> für die Inhaltsnavigation, hauptsächlich durch Aggregieren und die Erfassung. Sie können den Clientbereich von <xref:System.Windows.Navigation.NavigationWindow> aktualisieren, indem Sie entweder einen einheitlichen Ressourcenbezeichner (URI) oder ein Objekt angeben. Im folgenden Beispiel werden beide Methoden veranschaulicht:  
  
 [!code-csharp[Performance#PerformanceSnippet14](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/TestNavigation.xaml.cs#performancesnippet14)]
 [!code-vb[Performance#PerformanceSnippet14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/testnavigation.xaml.vb#performancesnippet14)]  
  
 Jedes <xref:System.Windows.Navigation.NavigationWindow> Objekt verfügt über ein Journal, das den Navigationsverlauf des Benutzers in diesem Fenster aufzeichnet. Die Erfassung dient unter anderem dazu, Benutzern die Rückverfolgung ihrer Schritte zu ermöglichen.  
  
 Wenn Sie mit einem einheitlichen Ressourcenbezeichner (URI) navigieren, speichert das Journal nur den URI-Verweis (Uniform Resource Identifier). Dies bedeutet, dass die Seite bei jedem weiteren Besuch dynamisch rekonstruiert wird, was je nach Komplexität der Seite sehr zeitaufwändig sein kann. In diesem Fall wird für die Erfassung wenig Speicher beansprucht, aber für das Wiederherstellen der Seite ist möglicherweise viel Zeit nötig.  
  
 Wenn Sie mithilfe eines Objekts navigieren, speichert die Erfassung die gesamte visuelle Struktur des Objekts. Dies bedeutet, dass die Seite bei jedem weiteren Besuch sofort gerendert wird, ohne dass sie rekonstruiert werden muss. In diesem Fall wird für die Erfassung viel Speicher beansprucht, aber für das Wiederherstellen der Seite ist wenig Zeit nötig.  
  
 Wenn Sie <xref:System.Windows.Navigation.NavigationWindow> das Objekt verwenden, müssen Sie bedenken, wie sich die Journalunterstützung auf die Leistung Ihrer Anwendung auswirkt. Weitere Informationen finden Sie unter [Navigationsübersicht](../app-development/navigation-overview.md).  
  
<a name="Hit_Testing"></a>
## <a name="hit-testing-on-large-3d-surfaces"></a>Treffertests auf großen 3D-Oberflächen  
 Treffertests auf großen 3D-Oberflächen sind in Bezug auf CPU-Auslastung ein sehr aufwändiger Vorgang. Dies gilt insbesondere, wenn die 3D-Oberfläche animiert wird. Wenn Sie keine Treffertests auf diesen Oberflächen benötigen, sollten Sie die Treffertests deaktivieren. Objekte, die <xref:System.Windows.UIElement> von abgeleitet werden, <xref:System.Windows.UIElement.IsHitTestVisible%2A> können `false`Treffertests deaktivieren, indem die Eigenschaft auf .  
  
<a name="CompositionTarget_Rendering_Event"></a>
## <a name="compositiontargetrendering-event"></a>CompositionTarget.Rendering-Ereignis  
 Das <xref:System.Windows.Media.CompositionTarget.Rendering?displayProperty=nameWithType> Ereignis [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bewirkt, dass es kontinuierlich animiert wird. Wenn Sie dieses Ereignis verwenden, sollten Sie es bei jeder Gelegenheit trennen.  
  
<a name="Avoid_Using_ScrollBarVisibility"></a>
## <a name="avoid-using-scrollbarvisibilityauto"></a>Vermeiden von ScrollBarVisibility=Auto  
 Vermeiden Sie nach <xref:System.Windows.Controls.ScrollBarVisibility.Auto?displayProperty=nameWithType> Möglichkeit die `HorizontalScrollBarVisibility` `VerticalScrollBarVisibility` Verwendung des Werts für die und Eigenschaften. Diese Eigenschaften sind <xref:System.Windows.Controls.RichTextBox> <xref:System.Windows.Controls.ScrollViewer>für <xref:System.Windows.Controls.TextBox> , und Objekte sowie als <xref:System.Windows.Controls.ListBox> angefügte Eigenschaft für das Objekt definiert. Legen Sie <xref:System.Windows.Controls.ScrollBarVisibility> <xref:System.Windows.Controls.ScrollBarVisibility.Disabled>stattdessen <xref:System.Windows.Controls.ScrollBarVisibility.Hidden>auf <xref:System.Windows.Controls.ScrollBarVisibility.Visible>, oder fest.  
  
 Der <xref:System.Windows.Controls.ScrollBarVisibility.Auto> Wert ist für Fälle vorgesehen, in denen der Speicherplatz begrenzt ist und Bildlaufleisten nur bei Bedarf angezeigt werden sollten. Beispielsweise kann es nützlich sein, <xref:System.Windows.Controls.ScrollBarVisibility> diesen <xref:System.Windows.Controls.ListBox> Wert mit einem von <xref:System.Windows.Controls.TextBox> 30 Elementen im Gegensatz zu einem mit Hunderten von Textzeilen zu verwenden.  
  
<a name="FontCache"></a>
## <a name="configure-font-cache-service-to-reduce-start-up-time"></a>Konfigurieren des Diensts für den Schriftartencache zur Reduzierung der Startzeit  
 Der WPF-Schriftartcachedienst gibt Schriftartdaten zwischen WPF-Anwendungen auf. Die erste WPF-Anwendung, die Sie ausführen, startet diesen Dienst, wenn der Dienst noch nicht ausgeführt wird. Wenn Sie Windows Vista verwenden, können Sie den Dienst "Windows Presentation Foundation (WPF) Font Cache 3.0.0.0" von "Manuell" (Standardeinstellung) auf "Automatischer (verzögerter Start)" festlegen, um die anfängliche Startzeit von WPF-Anwendungen zu reduzieren.  
  
## <a name="see-also"></a>Weitere Informationen

- [Planen der Anwendungsleistung](planning-for-application-performance.md)
- [Vorteile der Hardware nutzen](optimizing-performance-taking-advantage-of-hardware.md)
- [Layout und Entwurf](optimizing-performance-layout-and-design.md)
- [2D-Grafiken und Bildverarbeitung](optimizing-performance-2d-graphics-and-imaging.md)
- [Objektverhalten](optimizing-performance-object-behavior.md)
- [Anwendungsressourcen](optimizing-performance-application-resources.md)
- [Text](optimizing-performance-text.md)
- [Datenbindung](optimizing-performance-data-binding.md)
- [Tipps und Tricks zu Animationen](../graphics-multimedia/animation-tips-and-tricks.md)
