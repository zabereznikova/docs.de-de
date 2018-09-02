---
title: Übersicht überToolBar
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ToolBar
- ToolBar control [WPF]
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
ms.openlocfilehash: 816ac0d81ddcaa461a842c0f69fe5ed5b21a32d1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43466283"
---
# <a name="toolbar-overview"></a>Übersicht überToolBar
<xref:System.Windows.Controls.ToolBar> -Steuerelemente sind Container für eine Gruppe von Befehlen oder Steuerelementen, die in der Regel in ihren Funktionen miteinander verbunden sind. Ein <xref:System.Windows.Controls.ToolBar> enthält in der Regel Schaltflächen, die Befehle aufrufen.  
  
  
<a name="ToolBarControl"></a>   
## <a name="toolbar-control"></a>ToolBar-Steuerelement  
 Die <xref:System.Windows.Controls.ToolBar> -Steuerelement hat seinen Namen aus der Leiste Anordnung der Schaltflächen oder anderen Steuerelementen in einer einzelnen Zeile oder Spalte. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> Steuerelemente bieten einen Überlaufmechanismus, der alle Elemente platziert, die nicht auf natürliche Weise in eine größenbeschränkte passen <xref:System.Windows.Controls.ToolBar> in einen speziellen Überlaufbereich. Darüber hinaus [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> -Steuerelementen wird in der Regel mit den zugehörigen <xref:System.Windows.Controls.ToolBarTray> Steuerelement, das besonderes Layoutverhalten sowie Unterstützung für Benutzerinitiierte größenanpassung und Anordnung von Symbolleisten zu bereitstellt.  
  
<a name="Creating_ToolBars"></a>   
## <a name="specifying-the-position-of-toolbars-in-a-toolbartray"></a>Festlegen der Position von ToolBars in einem ToolBarTray  
 Verwenden der <xref:System.Windows.Controls.ToolBar.Band%2A> und <xref:System.Windows.Controls.ToolBar.BandIndex%2A> Eigenschaften zum Positionieren der <xref:System.Windows.Controls.ToolBar> in die <xref:System.Windows.Controls.ToolBarTray>. <xref:System.Windows.Controls.ToolBar.Band%2A> Gibt die Position in der die <xref:System.Windows.Controls.ToolBar> befindet sich innerhalb des übergeordneten <xref:System.Windows.Controls.ToolBarTray>. <xref:System.Windows.Controls.ToolBar.BandIndex%2A> Gibt an, in welcher Reihenfolge die <xref:System.Windows.Controls.ToolBar> innerhalb des Bands platziert wird. Das folgende Beispiel zeigt wie diese Eigenschaft verwenden, platzieren <xref:System.Windows.Controls.ToolBar> Steuerelemente innerhalb einer <xref:System.Windows.Controls.ToolBarTray>.  
  
 [!code-xaml[ToolBarExample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>   
## <a name="toolbars-with-overflow-items"></a>ToolBars mit Überlaufelementen  
 Häufig <xref:System.Windows.Controls.ToolBar> Steuerelemente enthalten mehr Elemente als in der Symbolleiste auf die Größe eingepasst werden kann. In diesem Fall die <xref:System.Windows.Controls.ToolBar> zeigt eine Schaltfläche "Überlauf". Um die Überlaufelemente anzuzeigen, klickt ein Benutzer auf die Schaltfläche "Überlauf", und die Elemente werden angezeigt, in einem Popupfenster unten die <xref:System.Windows.Controls.ToolBar>. Die folgende Grafik zeigt eine <xref:System.Windows.Controls.ToolBar> mit Überlaufelementen.  
  
 ![ToolBar mit Überlauf](../../../../docs/framework/wpf/controls/media/toolbarwithoverflowitem.png "ToolbarWithOverflowItem")  
ToolBar mit Überlaufelementen  
  
 Sie können angeben, wann ein Element in einer Symbolleiste durch Festlegen von in das überlaufpanel platziert wird die <xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=nameWithType> angefügte Eigenschaft zu <xref:System.Windows.Controls.OverflowMode.Always?displayProperty=nameWithType>, <xref:System.Windows.Controls.OverflowMode.Never?displayProperty=nameWithType>, oder <xref:System.Windows.Controls.OverflowMode.AsNeeded?displayProperty=nameWithType>. Das folgende Beispiel gibt an, dass die letzten vier Schaltflächen auf der Symbolleiste sich immer im Überlaufpanel befinden soll.  
  
 [!code-xaml[ToolBarExample#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 Die <xref:System.Windows.Controls.ToolBar> verwendet eine <xref:System.Windows.Controls.Primitives.ToolBarPanel> und <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> in seine <xref:System.Windows.Controls.ControlTemplate>.  Die <xref:System.Windows.Controls.Primitives.ToolBarPanel> ist verantwortlich für das Layout der Elemente auf der Symbolleiste.  Die <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> ist verantwortlich für das Layout der Elemente, die nicht auf passen die <xref:System.Windows.Controls.ToolBar>. Ein Beispiel für eine <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.ToolBar>, finden Sie unter  
  
 [ToolBar-Stile und -Vorlagen](../../../../docs/framework/wpf/controls/toolbar-styles-and-templates.md)  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
 <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
 [Formatieren von Steuerelementen in einer Symbolleiste](../../../../docs/framework/wpf/controls/how-to-style-controls-on-a-toolbar.md)  
 [Beispiel für WPF-Steuerelementsammlungen](https://go.microsoft.com/fwlink/?LinkID=160053)
