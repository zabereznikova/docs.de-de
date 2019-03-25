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
ms.openlocfilehash: 29003779825b92402fa12b810c1a099731ac8af6
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58409457"
---
# <a name="expander-overview"></a>Übersicht über Expander-Steuerelemente
Ein <xref:System.Windows.Controls.Expander> -Steuerelement bietet eine Möglichkeit zum Bereitstellen von Inhalt in einem erweiterbaren Bereich, der einem Fenster ähnelt und einen Header enthält.  
  
  
<a name="CreatinganExpanderinXAML"></a>   
## <a name="creating-a-simple-expander"></a>Erstellen einer einfachen Expanders  
 Das folgende Beispiel zeigt, wie zum Erstellen eines einfachen <xref:System.Windows.Controls.Expander> Steuerelement. In diesem Beispiel wird ein <xref:System.Windows.Controls.Expander> sieht in der vorherige Abbildung.  
  
 [!code-xaml[ExpanderExample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderExample/CSharp/Page1.xaml#2)]  
  
 Die <xref:System.Windows.Controls.ContentControl.Content%2A> und <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> von einem <xref:System.Windows.Controls.Expander> können auch komplexe Inhalte aufweisen, z. B. <xref:System.Windows.Controls.RadioButton> und <xref:System.Windows.Controls.Image> Objekte.  
  
<a name="SettingtheDirectionoftheExpandingWindow"></a>   
## <a name="setting-the-direction-of-the-expanding-content-area"></a>Festlegen der Erweiterungsrichtung des Inhaltsbereichs  
 Sie können festlegen, den Inhaltsbereich ein <xref:System.Windows.Controls.Expander> Steuerelement erweitern in eine von vier Richtungen (<xref:System.Windows.Controls.ExpandDirection.Down>, <xref:System.Windows.Controls.ExpandDirection.Up>, <xref:System.Windows.Controls.ExpandDirection.Left>, oder <xref:System.Windows.Controls.ExpandDirection.Right>) mithilfe der <xref:System.Windows.Controls.ExpandDirection> Eigenschaft. Wenn der Inhaltsbereich reduziert ist, werden nur die <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> und entsprechenden Umschaltfläche angezeigt. Ein <xref:System.Windows.Controls.Button> -Steuerelement, das ein Richtungspfeil dargestellt wird als eine Umschaltfläche zum Erweitern oder reduzieren den Inhaltsbereich verwendet. Wenn die Kategorie erweitert ist, die <xref:System.Windows.Controls.Expander> versucht, den gesamten Inhalt in einem Fenster-ähnlichen Bereich anzuzeigen.  
  
<a name="SettingSizeDimensionsonanExpanderinaPanel"></a>   
## <a name="controlling-the-size-of-an-expander-in-a-panel"></a>Steuerung der Größe eines Expanders in einem Panel  
 Wenn ein <xref:System.Windows.Controls.Expander> Steuerelement befindet sich innerhalb eines Layout-Steuerelements, die von erbt <xref:System.Windows.Controls.Panel>, wie z. B. <xref:System.Windows.Controls.StackPanel>, geben Sie keine <xref:System.Windows.FrameworkElement.Height%2A> auf die <xref:System.Windows.Controls.Expander> bei der <xref:System.Windows.Controls.Expander.ExpandDirection%2A> -Eigenschaftensatz auf <xref:System.Windows.Controls.ExpandDirection.Down> oder <xref:System.Windows.Controls.ExpandDirection.Up>. Auf ähnliche Weise Geben Sie keine <xref:System.Windows.FrameworkElement.Width%2A> auf die <xref:System.Windows.Controls.Expander> bei der <xref:System.Windows.Controls.Expander.ExpandDirection%2A> -Eigenschaftensatz auf <xref:System.Windows.Controls.ExpandDirection.Left> oder <xref:System.Windows.Controls.ExpandDirection.Right>.  
  
 Wenn Sie eine Größendimension festlegen, auf eine <xref:System.Windows.Controls.Expander> -Steuerelement in die Richtung an, dass der erweiterte Inhalt angezeigt wird, die <xref:System.Windows.Controls.Expander> übernimmt die Steuerung des Bereichs, der durch den Inhalt und zeigt einen Rahmen. Der Rahmen wird auch angezeigt, wenn der Inhalt reduziert ist. Um die Größe des erweiterten Inhaltsbereichs festzulegen, legen Sie Größendimensionen für den Inhalt der <xref:System.Windows.Controls.Expander>, oder wenn Sie möchten die Bildlauf-Funktion, auf die <xref:System.Windows.Controls.ScrollViewer> , das den Inhalt einschließt.  
  
 Beim ein <xref:System.Windows.Controls.Expander> Steuerelement ist das letzte Element in eine <xref:System.Windows.Controls.DockPanel>, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] legt automatisch die <xref:System.Windows.Controls.Expander> Dimensionen aus, die gleich des verbleibenden Bereichs von der <xref:System.Windows.Controls.DockPanel>. Um dieses Standardverhalten zu verhindern, legen die <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> Eigenschaft für die <xref:System.Windows.Controls.DockPanel> -Objekt `false`, oder stellen Sie sicher, dass die <xref:System.Windows.Controls.Expander> ist nicht das letzte Element in einer <xref:System.Windows.Controls.DockPanel>.  
  
<a name="CreatingScrollableContent"></a>   
## <a name="creating-scrollable-content"></a>Erstellen vom bildlauffähigem Inhalt  
 Wenn der Inhalt für die Größe des Inhaltsbereichs zu groß ist, können Sie den Inhalt des umschließen einer <xref:System.Windows.Controls.Expander> in einer <xref:System.Windows.Controls.ScrollViewer> um bildlauffähigem Inhalt bereitzustellen. Die <xref:System.Windows.Controls.Expander> Steuerelement stellt die Bildlauf-Funktion nicht automatisch bereit. Die folgende Abbildung zeigt ein <xref:System.Windows.Controls.Expander> -Steuerelement, enthält eine <xref:System.Windows.Controls.ScrollViewer> Steuerelement.  
  
 **Expander-Steuerelement in einem ScrollViewer**  
  
 ![Screenshot mit einem Expander mit ScrollBar.](./media/expander-overview/expander-scrollbar-control.jpg)  
  
 Beim Platzieren ein <xref:System.Windows.Controls.Expander> steuern, eine <xref:System.Windows.Controls.ScrollViewer>, legen die <xref:System.Windows.Controls.ScrollViewer> -Dimensionseigenschaft, der die Richtung, in denen entspricht der <xref:System.Windows.Controls.Expander> Inhalt wird geöffnet, auf die Größe des der <xref:System.Windows.Controls.Expander> Inhaltsbereich. Wenn Sie festlegen, z. B. die <xref:System.Windows.Controls.Expander.ExpandDirection%2A> Eigenschaft der <xref:System.Windows.Controls.Expander> zu <xref:System.Windows.Controls.ExpandDirection.Down> (der Inhaltsbereich wird nach unten), Festlegen der <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaft der <xref:System.Windows.Controls.ScrollViewer> Steuerelement, die für den Inhaltsbereich erforderliche Höhe. Wenn Sie die Höhendimension stattdessen für den Inhalt selbst festlegen <xref:System.Windows.Controls.ScrollViewer> erkennt diese Einstellung nicht und ist daher kein bildlauffähiger Inhalt bereitgestellt.  
  
 Das folgende Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.Expander> Steuerelement mit komplexen Inhalt enthält, die eine <xref:System.Windows.Controls.ScrollViewer> Steuerelement. In diesem Beispiel wird ein <xref:System.Windows.Controls.Expander> , die in der Abbildung am Anfang dieses Abschnitts entspricht.  
  
 [!code-csharp[ExpanderRichContent#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ExpanderRichContent#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpanderRichContent/VisualBasic/Window1.xaml.vb#1)]
 [!code-xaml[ExpanderRichContent#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#1)]  
  
<a name="UsingtheAlignmentProperties"></a>   
## <a name="using-the-alignment-properties"></a>Verwenden der Ausrichtungseigenschaften  
 Sie können Inhalte ausrichten, durch Festlegen der <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> und <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> Eigenschaften für die <xref:System.Windows.Controls.Expander> Steuerelement. Wenn Sie diese Eigenschaften festlegen, wird die Ausrichtung sowohl auf den Header, als auch auf den erweiterten Inhalt angewendet.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.Expander>
- <xref:System.Windows.Controls.ExpandDirection>
- [Themen zu Vorgehensweisen](expander-how-to-topics.md)
