---
title: Übersicht über Expander-Steuerelemente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Expander
- Expander control [WPF], about Expander control
ms.assetid: 877bf425-0e54-49ec-8fd2-13a211377abb
ms.openlocfilehash: 892d972a5704d50e91d04e05d6fdea7180a3155d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187111"
---
# <a name="expander-overview"></a>Übersicht über Expander-Steuerelemente
Ein <xref:System.Windows.Controls.Expander> Steuerelement bietet eine Möglichkeit, Inhalte in einem erweiterbaren Bereich bereitzustellen, der einem Fenster ähnelt und einen Header enthält.  

<a name="CreatinganExpanderinXAML"></a>
## <a name="creating-a-simple-expander"></a>Erstellen einer einfachen Expanders  
 Das folgende Beispiel zeigt, <xref:System.Windows.Controls.Expander> wie Sie ein einfaches Steuerelement erstellen. In diesem <xref:System.Windows.Controls.Expander> Beispiel wird ein erstellt, das wie die vorherige Abbildung aussieht.  
  
 [!code-xaml[ExpanderExample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderExample/CSharp/Page1.xaml#2)]  
  
 Der <xref:System.Windows.Controls.ContentControl.Content%2A> <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> und <xref:System.Windows.Controls.Expander> eines kann auch komplexe <xref:System.Windows.Controls.RadioButton> Inhalte <xref:System.Windows.Controls.Image> enthalten, z. B. und Objekte.  
  
<a name="SettingtheDirectionoftheExpandingWindow"></a>
## <a name="setting-the-direction-of-the-expanding-content-area"></a>Festlegen der Erweiterungsrichtung des Inhaltsbereichs  
 Sie können den Inhaltsbereich <xref:System.Windows.Controls.Expander> eines Steuerelements so einstellen,<xref:System.Windows.Controls.ExpandDirection.Down> <xref:System.Windows.Controls.ExpandDirection.Up>dass <xref:System.Windows.Controls.ExpandDirection.Left>er <xref:System.Windows.Controls.ExpandDirection.Right>mithilfe der <xref:System.Windows.Controls.ExpandDirection> Eigenschaft in eine von vier Richtungen ( , , , oder ) erweitert wird. Wenn der Inhaltsbereich reduziert wird, werden nur die <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> und ihre Umschaltfläche angezeigt. Ein <xref:System.Windows.Controls.Button> Steuerelement, das einen Richtungspfeil anzeigt, wird als Umschaltfläche verwendet, um den Inhaltsbereich zu erweitern oder zu reduzieren. Beim Erweitern <xref:System.Windows.Controls.Expander> versucht der, den gesamten Inhalt in einem fensterartigen Bereich anzuzeigen.  
  
<a name="SettingSizeDimensionsonanExpanderinaPanel"></a>
## <a name="controlling-the-size-of-an-expander-in-a-panel"></a>Steuerung der Größe eines Expanders in einem Panel  
 Wenn <xref:System.Windows.Controls.Expander> sich ein Steuerelement in einem Layoutsteuerelement befindet, <xref:System.Windows.Controls.Panel>das von erbt, <xref:System.Windows.Controls.Expander.ExpandDirection%2A> z. <xref:System.Windows.Controls.ExpandDirection.Down> <xref:System.Windows.Controls.StackPanel>B. , geben Sie keine <xref:System.Windows.FrameworkElement.Height%2A> auf der <xref:System.Windows.Controls.Expander> , wenn die Eigenschaft auf oder <xref:System.Windows.Controls.ExpandDirection.Up>festgelegt ist. Geben Sie auch <xref:System.Windows.FrameworkElement.Width%2A> keine <xref:System.Windows.Controls.Expander> auf <xref:System.Windows.Controls.Expander.ExpandDirection%2A> der an, <xref:System.Windows.Controls.ExpandDirection.Left> <xref:System.Windows.Controls.ExpandDirection.Right>wenn die Eigenschaft auf oder festgelegt ist.  
  
 Wenn Sie eine Größenbemaßung für ein <xref:System.Windows.Controls.Expander> Steuerelement in der <xref:System.Windows.Controls.Expander> Richtung festlegen, in der der erweiterte Inhalt angezeigt wird, übernimmt der die Kontrolle über den Bereich, der vom Inhalt verwendet wird, und zeigt einen Rahmen um ihn herum an. Der Rahmen wird auch angezeigt, wenn der Inhalt reduziert ist. Um die Größe des erweiterten Inhaltsbereichs festzulegen, legen <xref:System.Windows.Controls.Expander>Sie Größendimensionen für den Inhalt <xref:System.Windows.Controls.ScrollViewer> des fest, oder legen Sie, wenn Sie einen Bildlauf benötigen, für die, die den Inhalt umschließt.  
  
 Wenn <xref:System.Windows.Controls.Expander> ein Steuerelement das letzte <xref:System.Windows.Controls.DockPanel> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Element in <xref:System.Windows.Controls.Expander> einem ist, werden <xref:System.Windows.Controls.DockPanel>die Bemaßungen automatisch auf den verbleibenden Bereich des festgelegt. Um dieses Standardverhalten zu <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> verhindern, <xref:System.Windows.Controls.DockPanel> legen `false`Sie die Eigenschaft <xref:System.Windows.Controls.Expander> für das Objekt <xref:System.Windows.Controls.DockPanel>auf , oder stellen Sie sicher, dass das nicht das letzte Element in einem ist.  
  
<a name="CreatingScrollableContent"></a>
## <a name="creating-scrollable-content"></a>Erstellen vom bildlauffähigem Inhalt  
 Wenn der Inhalt für die Größe des Inhaltsbereichs zu groß <xref:System.Windows.Controls.Expander> ist, <xref:System.Windows.Controls.ScrollViewer> können Sie den Inhalt eines in a umschließen, um scrollbaren Inhalt bereitzustellen. Das <xref:System.Windows.Controls.Expander> Steuerelement bietet nicht automatisch Bildlauffunktion. Die folgende Abbildung <xref:System.Windows.Controls.Expander> zeigt ein <xref:System.Windows.Controls.ScrollViewer> Steuerelement, das ein Steuerelement enthält.  
  
 **Expander-Steuerelement in einem ScrollViewer**  
  
 ![Screenshot, der einen Expander mit ScrollBar zeigt.](./media/expander-overview/expander-scrollbar-control.jpg)  
  
 Wenn Sie <xref:System.Windows.Controls.Expander> ein Steuerelement <xref:System.Windows.Controls.ScrollViewer>in <xref:System.Windows.Controls.ScrollViewer> einem platzieren, legen Sie die <xref:System.Windows.Controls.Expander> Dimensionseigenschaft fest, <xref:System.Windows.Controls.Expander> die der Richtung entspricht, in der der Inhalt der Größe des Inhaltsbereichs entspricht. Wenn Sie z. <xref:System.Windows.Controls.Expander.ExpandDirection%2A> B. <xref:System.Windows.Controls.Expander> die <xref:System.Windows.Controls.ExpandDirection.Down> Eigenschaft auf "to" <xref:System.Windows.FrameworkElement.Height%2A> festlegen (der Inhaltsbereich wird geöffnet), legen Sie die Eigenschaft für das <xref:System.Windows.Controls.ScrollViewer> Steuerelement auf die erforderliche Höhe für den Inhaltsbereich fest. Wenn Sie stattdessen die Höhenbemaßung <xref:System.Windows.Controls.ScrollViewer> für den Inhalt selbst festlegen, erkennt diese Einstellung nicht und bietet daher keinen scrollbaren Inhalt.  
  
 Das folgende Beispiel zeigt, <xref:System.Windows.Controls.Expander> wie Sie ein Steuerelement <xref:System.Windows.Controls.ScrollViewer> erstellen, das über komplexen Inhalt verfügt und ein Steuerelement enthält. In diesem <xref:System.Windows.Controls.Expander> Beispiel wird eine wie die Abbildung am Anfang dieses Abschnitts erstellt.  
  
 [!code-csharp[ExpanderRichContent#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ExpanderRichContent#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpanderRichContent/VisualBasic/Window1.xaml.vb#1)]
 [!code-xaml[ExpanderRichContent#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#1)]  
  
<a name="UsingtheAlignmentProperties"></a>
## <a name="using-the-alignment-properties"></a>Verwenden der Ausrichtungseigenschaften  
 Sie können Inhalte ausrichten, indem Sie die <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> und <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> Eigenschaften für das <xref:System.Windows.Controls.Expander> Steuerelement festlegen. Wenn Sie diese Eigenschaften festlegen, wird die Ausrichtung sowohl auf den Header, als auch auf den erweiterten Inhalt angewendet.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Controls.Expander>
- <xref:System.Windows.Controls.ExpandDirection>
- [How-to-Themen](expander-how-to-topics.md)
