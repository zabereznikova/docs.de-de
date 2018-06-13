---
title: Übersicht überToolBar
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ToolBar
- ToolBar control [WPF]
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
ms.openlocfilehash: 0c66867ce4d86a11424d7a7a859817d603b4227e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557393"
---
# <a name="toolbar-overview"></a>Übersicht überToolBar
<xref:System.Windows.Controls.ToolBar> -Steuerelemente sind Container für eine Gruppe von Befehlen oder Steuerelemente, die in der Regel in ihrer Funktion miteinander verbunden sind. Ein <xref:System.Windows.Controls.ToolBar> enthält in der Regel Schaltflächen, die Befehle aufrufen.  
  
  
<a name="ToolBarControl"></a>   
## <a name="toolbar-control"></a>ToolBar-Steuerelement  
 Die <xref:System.Windows.Controls.ToolBar> Steuerelement akzeptiert den Namen der Leiste-ähnliche Anordnung von Schaltflächen oder anderen Steuerelementen in einer einzelnen Zeile oder Spalte. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> -Steuerelemente bieten einen Überlaufmechanismus der alle Elemente platziert, die nicht natürlich in einer größenbeschränkten passen <xref:System.Windows.Controls.ToolBar> in einem speziellen Überlaufbereich. Darüber hinaus [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> -Steuerelementen wird in der Regel mit den zugehörigen <xref:System.Windows.Controls.ToolBarTray> Steuerelement, das spezielle Layoutverhalten sowie Unterstützung für das Ändern der Größe und Symbolleisten anordnen von Benutzern initiierte bereitstellt.  
  
<a name="Creating_ToolBars"></a>   
## <a name="specifying-the-position-of-toolbars-in-a-toolbartray"></a>Festlegen der Position von ToolBars in einem ToolBarTray  
 Verwenden der <xref:System.Windows.Controls.ToolBar.Band%2A> und <xref:System.Windows.Controls.ToolBar.BandIndex%2A> Eigenschaften zum Positionieren der <xref:System.Windows.Controls.ToolBar> in der <xref:System.Windows.Controls.ToolBarTray>. <xref:System.Windows.Controls.ToolBar.Band%2A> Gibt die Position in dem die <xref:System.Windows.Controls.ToolBar> befindet sich in seinem übergeordneten Element <xref:System.Windows.Controls.ToolBarTray>. <xref:System.Windows.Controls.ToolBar.BandIndex%2A> Gibt an, in welcher Reihenfolge die <xref:System.Windows.Controls.ToolBar> innerhalb des zugehörigen Bands platziert wird. Das folgende Beispiel zeigt wie diese Eigenschaft verwenden, platzieren <xref:System.Windows.Controls.ToolBar> Steuerelemente innerhalb einer <xref:System.Windows.Controls.ToolBarTray>.  
  
 [!code-xaml[ToolBarExample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>   
## <a name="toolbars-with-overflow-items"></a>ToolBars mit Überlaufelementen  
 Häufig <xref:System.Windows.Controls.ToolBar> Steuerelemente enthalten mehr Elemente als in der Symbolleiste Größe eingepasst werden kann. In diesem Fall die <xref:System.Windows.Controls.ToolBar> zeigt eine Schaltfläche "Überlauf". Um die Overflow-Elemente anzuzeigen, klickt ein Benutzer die dokumentüberlauf-Schaltfläche und die Elemente werden in einem Popupfenster unten dargestellt den <xref:System.Windows.Controls.ToolBar>. Die folgende Grafik zeigt eine <xref:System.Windows.Controls.ToolBar> mit Überlaufelementen.  
  
 ![ToolBar mit Überlauf](../../../../docs/framework/wpf/controls/media/toolbarwithoverflowitem.png "ToolbarWithOverflowItem")  
ToolBar mit Überlaufelementen  
  
 Sie können angeben, wann ein Element auf einer Symbolleiste Überlaufbereich durch Festlegen von platziert wird die <xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=nameWithType> angefügten Eigenschaft, um <xref:System.Windows.Controls.OverflowMode.Always?displayProperty=nameWithType>, <xref:System.Windows.Controls.OverflowMode.Never?displayProperty=nameWithType>, oder <xref:System.Windows.Controls.OverflowMode.AsNeeded?displayProperty=nameWithType>. Das folgende Beispiel gibt an, dass die letzten vier Schaltflächen auf der Symbolleiste sich immer im Überlaufpanel befinden soll.  
  
 [!code-xaml[ToolBarExample#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 Die <xref:System.Windows.Controls.ToolBar> verwendet eine <xref:System.Windows.Controls.Primitives.ToolBarPanel> und ein <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> in seiner <xref:System.Windows.Controls.ControlTemplate>.  Die <xref:System.Windows.Controls.Primitives.ToolBarPanel> ist verantwortlich für das Layout der Elemente auf der Symbolleiste.  Die <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> ist verantwortlich für das Layout der Elemente, die nicht auf passen die <xref:System.Windows.Controls.ToolBar>. Ein Beispiel für eine <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.ToolBar>, finden Sie unter  
  
 [ToolBar-Stile und -Vorlagen](../../../../docs/framework/wpf/controls/toolbar-styles-and-templates.md)  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
 <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
 [Formatieren von Steuerelementen in einer Symbolleiste](../../../../docs/framework/wpf/controls/how-to-style-controls-on-a-toolbar.md)  
 [Beispiel für WPF-Steuerelementsammlungen](http://go.microsoft.com/fwlink/?LinkID=160053)
