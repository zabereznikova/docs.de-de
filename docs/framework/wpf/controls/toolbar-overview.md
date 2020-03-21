---
title: Übersicht überToolBar
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ToolBar
- ToolBar control [WPF]
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
ms.openlocfilehash: b5498b8b88c7403ffe51256a57544261de3ace08
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186613"
---
# <a name="toolbar-overview"></a>Übersicht überToolBar
<xref:System.Windows.Controls.ToolBar>Steuerelemente sind Container für eine Gruppe von Befehlen oder Steuerelementen, die in der Regel in ihrer Funktion verknüpft sind. A <xref:System.Windows.Controls.ToolBar> enthält normalerweise Schaltflächen, die Befehle aufrufen.  

<a name="ToolBarControl"></a>
## <a name="toolbar-control"></a>ToolBar-Steuerelement  
 Das <xref:System.Windows.Controls.ToolBar> Steuerelement nimmt seinen Namen von der bar-ähnlichen Anordnung von Schaltflächen oder anderen Steuerelementen in einer einzelnen Zeile oder Spalte an. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.ToolBar> Steuerelemente bieten einen Überlaufmechanismus, der alle Elemente, die <xref:System.Windows.Controls.ToolBar> nicht auf natürliche Weise in eine Größenbeschränkung passen, in einen speziellen Überlaufbereich platziert. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> Außerdem werden Steuerelemente in <xref:System.Windows.Controls.ToolBarTray> der Regel mit dem zugehörigen Steuerelement verwendet, das ein spezielles Layoutverhalten sowie Unterstützung für die vom Benutzer initiierte Größen- und Anordnung von Symbolleisten bietet.  
  
<a name="Creating_ToolBars"></a>
## <a name="specifying-the-position-of-toolbars-in-a-toolbartray"></a>Festlegen der Position von ToolBars in einem ToolBarTray  
 Verwenden <xref:System.Windows.Controls.ToolBar.Band%2A> Sie <xref:System.Windows.Controls.ToolBar.BandIndex%2A> die und-Eigenschaften, um die <xref:System.Windows.Controls.ToolBar> im zu <xref:System.Windows.Controls.ToolBarTray>positionieren. <xref:System.Windows.Controls.ToolBar.Band%2A>gibt die Position <xref:System.Windows.Controls.ToolBar> an, an <xref:System.Windows.Controls.ToolBarTray>der der innerhalb des übergeordneten Elements platziert wird. <xref:System.Windows.Controls.ToolBar.BandIndex%2A>gibt die Reihenfolge <xref:System.Windows.Controls.ToolBar> an, in der der innerhalb seines Bandes platziert wird. Das folgende Beispiel zeigt, wie <xref:System.Windows.Controls.ToolBar> Diese <xref:System.Windows.Controls.ToolBarTray>Eigenschaft zum Platzieren von Steuerelementen in einer platziert wird.  
  
 [!code-xaml[ToolBarExample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>
## <a name="toolbars-with-overflow-items"></a>ToolBars mit Überlaufelementen  
 Häufig <xref:System.Windows.Controls.ToolBar> enthalten Steuerelemente mehr Elemente, als in die Größe der Symbolleiste passen. In diesem Fall <xref:System.Windows.Controls.ToolBar> wird eine Überlaufschaltfläche angezeigt. Um die Überlaufelemente anzuzeigen, klickt ein Benutzer auf die Schaltfläche Überlauf, <xref:System.Windows.Controls.ToolBar>und die Elemente werden in einem Popup-Fenster unter der angezeigt. Die folgende Grafik <xref:System.Windows.Controls.ToolBar> zeigt eine mit Überlaufelementen:  
  
 ![Screenshot, der eine Symbolleiste mit Überlaufelementen zeigt.](./media/toolbar-overview/toolbar-overflow-items.png)  
  
 Sie können angeben, wann ein Element auf einer Symbolleiste <xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=nameWithType> auf dem <xref:System.Windows.Controls.OverflowMode.Always?displayProperty=nameWithType> <xref:System.Windows.Controls.OverflowMode.Never?displayProperty=nameWithType>Überlaufbereich platziert wird, indem Sie die angefügte Eigenschaft auf , oder <xref:System.Windows.Controls.OverflowMode.AsNeeded?displayProperty=nameWithType>festlegen. Das folgende Beispiel gibt an, dass die letzten vier Schaltflächen auf der Symbolleiste sich immer im Überlaufpanel befinden soll.  
  
 [!code-xaml[ToolBarExample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 Die <xref:System.Windows.Controls.ToolBar> verwendet <xref:System.Windows.Controls.Primitives.ToolBarPanel> a <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> und <xref:System.Windows.Controls.ControlTemplate>a in seiner .  Der <xref:System.Windows.Controls.Primitives.ToolBarPanel> ist für das Layout der Elemente auf der Symbolleiste verantwortlich.  Der <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> ist für das Layout der Elemente verantwortlich, die nicht in die <xref:System.Windows.Controls.ToolBar>passen. Ein Beispiel für <xref:System.Windows.Controls.ControlTemplate> ein <xref:System.Windows.Controls.ToolBar>für , siehe  
  
 [ToolBar-Stile und Vorlagen](toolbar-styles-and-templates.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Controls.Primitives.ToolBarPanel>
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>
- [Formatieren von Steuerelementen in einer Symbolleiste](how-to-style-controls-on-a-toolbar.md)
- [Beispiel für WPF-Steuerelementsammlungen](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
