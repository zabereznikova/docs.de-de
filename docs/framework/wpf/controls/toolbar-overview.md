---
title: Übersicht überToolBar
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ToolBar
- ToolBar control [WPF]
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
ms.openlocfilehash: 460d4420d5faf849a8d05a94e0170aea384f69b4
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452694"
---
# <a name="toolbar-overview"></a>Übersicht überToolBar
<xref:System.Windows.Controls.ToolBar> Steuerelemente sind Container für eine Gruppe von Befehlen oder Steuerelementen, die in der Regel in ihrer Funktion verknüpft sind. Ein <xref:System.Windows.Controls.ToolBar> enthält normalerweise Schaltflächen, die Befehle aufrufen.  

<a name="ToolBarControl"></a>   
## <a name="toolbar-control"></a>ToolBar-Steuerelement  
 Das <xref:System.Windows.Controls.ToolBar> Steuerelement übernimmt seinen Namen aus der Balken ähnlichen Anordnung von Schaltflächen oder anderen Steuerelementen in eine einzelne Zeile oder Spalte. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar>-Steuerelemente bieten einen Überlauf Mechanismus, bei dem alle Elemente, die nicht auf natürliche Weise innerhalb eines Größen eingeschränkten <xref:System.Windows.Controls.ToolBar> passen, in einen speziellen Überlauf Bereich eingefügt werden. Außerdem werden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar>-Steuerelemente in der Regel zusammen mit dem zugehörigen <xref:System.Windows.Controls.ToolBarTray> Steuerelement verwendet, das spezielles Layoutverhalten sowie Unterstützung für die vom Benutzer initiierte Größe und Anordnung von Symbolleisten bereitstellt.  
  
<a name="Creating_ToolBars"></a>   
## <a name="specifying-the-position-of-toolbars-in-a-toolbartray"></a>Festlegen der Position von ToolBars in einem ToolBarTray  
 Verwenden Sie die Eigenschaften <xref:System.Windows.Controls.ToolBar.Band%2A> und <xref:System.Windows.Controls.ToolBar.BandIndex%2A>, um die <xref:System.Windows.Controls.ToolBar> in der <xref:System.Windows.Controls.ToolBarTray>zu positionieren. <xref:System.Windows.Controls.ToolBar.Band%2A> gibt die Position an, an der die <xref:System.Windows.Controls.ToolBar> innerhalb der übergeordneten <xref:System.Windows.Controls.ToolBarTray>platziert wird. <xref:System.Windows.Controls.ToolBar.BandIndex%2A> gibt die Reihenfolge an, in der die <xref:System.Windows.Controls.ToolBar> in Ihrem Band platziert wird. Das folgende Beispiel zeigt, wie diese Eigenschaft verwendet wird, um <xref:System.Windows.Controls.ToolBar>-Steuerelemente in einer <xref:System.Windows.Controls.ToolBarTray>zu platzieren.  
  
 [!code-xaml[ToolBarExample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>   
## <a name="toolbars-with-overflow-items"></a>ToolBars mit Überlaufelementen  
 Häufig enthalten <xref:System.Windows.Controls.ToolBar> Steuerelemente mehr Elemente, als in die Größe der Symbolleiste passen. Wenn dies der Fall ist, zeigt der <xref:System.Windows.Controls.ToolBar> eine Überlauf Schaltfläche an. Um die Überlauf Elemente anzuzeigen, klickt ein Benutzer auf die Überlauf Schaltfläche, und die Elemente werden in einem Popup Fenster unterhalb des <xref:System.Windows.Controls.ToolBar>angezeigt. Die folgende Grafik zeigt eine <xref:System.Windows.Controls.ToolBar> mit Überlauf Elementen:  
  
 ![Screenshot, der eine Symbolleiste mit Überlauf Elementen anzeigt.](./media/toolbar-overview/toolbar-overflow-items.png)  
  
 Sie können angeben, wann ein Element auf einer Symbolleiste im Überlauf Bereich platziert wird, indem Sie die <xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=nameWithType> angefügte Eigenschaft auf <xref:System.Windows.Controls.OverflowMode.Always?displayProperty=nameWithType>, <xref:System.Windows.Controls.OverflowMode.Never?displayProperty=nameWithType>oder <xref:System.Windows.Controls.OverflowMode.AsNeeded?displayProperty=nameWithType>festlegen. Das folgende Beispiel gibt an, dass die letzten vier Schaltflächen auf der Symbolleiste sich immer im Überlaufpanel befinden soll.  
  
 [!code-xaml[ToolBarExample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 Die <xref:System.Windows.Controls.ToolBar> verwendet eine <xref:System.Windows.Controls.Primitives.ToolBarPanel> und eine <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> in der <xref:System.Windows.Controls.ControlTemplate>.  Der <xref:System.Windows.Controls.Primitives.ToolBarPanel> ist für das Layout der Elemente auf der Symbolleiste verantwortlich.  Der <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> ist für das Layout der Elemente verantwortlich, die nicht in die <xref:System.Windows.Controls.ToolBar>passen. Ein Beispiel für eine <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.ToolBar>finden Sie unter.  
  
 [ToolBar-Stile und -Vorlagen](toolbar-styles-and-templates.md)  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.Primitives.ToolBarPanel>
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>
- [Formatieren von Steuerelementen in einer Symbolleiste](how-to-style-controls-on-a-toolbar.md)
- [Beispiel für WPF-Steuerelementsammlungen](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
