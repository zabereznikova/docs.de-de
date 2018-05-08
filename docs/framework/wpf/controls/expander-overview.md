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
ms.openlocfilehash: abcc7c48c602aee742959b39bb5244563eaf4d5d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="expander-overview"></a>Übersicht über Expander-Steuerelemente
Ein <xref:System.Windows.Controls.Expander> Steuerelement bietet eine Möglichkeit zum Bereitstellen von Inhalt in einem erweiterbaren Bereich, der einem Fenster ähnelt und einen Header enthält.  
  
  
<a name="CreatinganExpanderinXAML"></a>   
## <a name="creating-a-simple-expander"></a>Erstellen einer einfachen Expanders  
 Im folgende Beispiel veranschaulicht die Erstellung eines einfachen <xref:System.Windows.Controls.Expander> Steuerelement. In diesem Beispiel wird ein <xref:System.Windows.Controls.Expander> sieht in der vorherige Abbildung.  
  
 [!code-xaml[ExpanderExample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderExample/CSharp/Page1.xaml#2)]  
  
 Die <xref:System.Windows.Controls.ContentControl.Content%2A> und <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> von einer <xref:System.Windows.Controls.Expander> können auch keine komplexen Inhalt wie <xref:System.Windows.Controls.RadioButton> und <xref:System.Windows.Controls.Image> Objekte.  
  
<a name="SettingtheDirectionoftheExpandingWindow"></a>   
## <a name="setting-the-direction-of-the-expanding-content-area"></a>Festlegen der Erweiterungsrichtung des Inhaltsbereichs  
 Sie können festlegen, dass den Inhaltsbereich des ein <xref:System.Windows.Controls.Expander> Steuerelement in einem der vier Richtungen erweitern (<xref:System.Windows.Controls.ExpandDirection.Down>, <xref:System.Windows.Controls.ExpandDirection.Up>, <xref:System.Windows.Controls.ExpandDirection.Left>, oder <xref:System.Windows.Controls.ExpandDirection.Right>) mithilfe der <xref:System.Windows.Controls.ExpandDirection> Eigenschaft. Wenn der Inhaltsbereich reduziert ist, werden nur die <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> und entsprechende Umschaltfläche angezeigt. Ein <xref:System.Windows.Controls.Button> Steuerelement, das einen Pfeil zeigt dient als eine Umschaltfläche zum Erweitern oder Reduzieren des Inhaltsbereichs. Wenn die Kategorie erweitert ist, die <xref:System.Windows.Controls.Expander> versucht, alle ihre Inhalte in einem Fenster-ähnliche Bereich anzuzeigen.  
  
<a name="SettingSizeDimensionsonanExpanderinaPanel"></a>   
## <a name="controlling-the-size-of-an-expander-in-a-panel"></a>Steuerung der Größe eines Expanders in einem Panel  
 Wenn ein <xref:System.Windows.Controls.Expander> Steuerelement ist in einem Layoutsteuerelement, die von erben <xref:System.Windows.Controls.Panel>, wie z. B. <xref:System.Windows.Controls.StackPanel>, geben Sie keine <xref:System.Windows.FrameworkElement.Height%2A> auf der <xref:System.Windows.Controls.Expander> bei der <xref:System.Windows.Controls.Expander.ExpandDirection%2A> -Eigenschaftensatz auf <xref:System.Windows.Controls.ExpandDirection.Down> oder <xref:System.Windows.Controls.ExpandDirection.Up>. Auf ähnliche Weise Geben Sie kein <xref:System.Windows.FrameworkElement.Width%2A> auf die <xref:System.Windows.Controls.Expander> bei der <xref:System.Windows.Controls.Expander.ExpandDirection%2A> -Eigenschaftensatz auf <xref:System.Windows.Controls.ExpandDirection.Left> oder <xref:System.Windows.Controls.ExpandDirection.Right>.  
  
 Wenn Sie eine Größendimension festlegen, auf ein <xref:System.Windows.Controls.Expander> -Steuerelement in die Richtung an, dass der erweiterte Inhalt angezeigt wird, die <xref:System.Windows.Controls.Expander> übernimmt die Kontrolle des Bereichs, der anhand des Inhalts verwendet wird, und zeigt einen Rahmen. Der Rahmen wird auch angezeigt, wenn der Inhalt reduziert ist. Legen Sie zum Festlegen der Größe des erweiterten Inhaltsbereichs größenabmessungen für den Inhalt der <xref:System.Windows.Controls.Expander>, oder wenn Sie möchten Scrollen Fähigkeit, auf die <xref:System.Windows.Controls.ScrollViewer> , das den Inhalt einschließt.  
  
 Beim ein <xref:System.Windows.Controls.Expander> Steuerelement ist das letzte Element in eine <xref:System.Windows.Controls.DockPanel>, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] legt automatisch die <xref:System.Windows.Controls.Expander> Dimensionen so, dass den verbleibenden Bereich von der <xref:System.Windows.Controls.DockPanel>. Um dieses Standardverhalten zu verhindern, legen die <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> Eigenschaft auf die <xref:System.Windows.Controls.DockPanel> -Objekt `false`, oder stellen Sie sicher, dass die <xref:System.Windows.Controls.Expander> ist nicht das letzte Element in einer <xref:System.Windows.Controls.DockPanel>.  
  
<a name="CreatingScrollableContent"></a>   
## <a name="creating-scrollable-content"></a>Erstellen vom bildlauffähigem Inhalt  
 Wenn der Inhalt für die Größe des Inhaltsbereichs zu groß ist, können Sie den Inhalt des umschließen einer <xref:System.Windows.Controls.Expander> in eine <xref:System.Windows.Controls.ScrollViewer> um bildlauffähigem Inhalt bereitzustellen. Die <xref:System.Windows.Controls.Expander> Steuerelement stellt Bildlauffunktion nicht automatisch bereit. Die folgende Abbildung zeigt ein <xref:System.Windows.Controls.Expander> -Steuerelement, enthält eine <xref:System.Windows.Controls.ScrollViewer> Steuerelement.  
  
 **Expander-Steuerelement in einem ScrollViewer**  
  
 ![Expander mit einer ScrollBar](../../../../docs/framework/wpf/controls/media/expanderwithscrollbar.JPG "ExpanderWithScrollBar")  
  
 Beim Platzieren ein <xref:System.Windows.Controls.Expander> steuern, eine <xref:System.Windows.Controls.ScrollViewer>legen die <xref:System.Windows.Controls.ScrollViewer> -Dimensionseigenschaft, der die Richtung, in der entspricht der <xref:System.Windows.Controls.Expander> Inhalt wird geöffnet, auf die Größe des der <xref:System.Windows.Controls.Expander> Inhaltsbereich. Z. B., wenn Sie festlegen der <xref:System.Windows.Controls.Expander.ExpandDirection%2A> Eigenschaft auf die <xref:System.Windows.Controls.Expander> auf <xref:System.Windows.Controls.ExpandDirection.Down> (der Inhaltsbereich wird nach unten), Festlegen der <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaft auf die <xref:System.Windows.Controls.ScrollViewer> Steuerelement, um die erforderliche Höhe des Inhaltsbereichs. Wenn Sie stattdessen höhenabmessung des Inhalts selbst festlegen <xref:System.Windows.Controls.ScrollViewer> diese Einstellung nicht erkannt und daher keinen bildlauffähigem Inhalt.  
  
 Im folgende Beispiel wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Controls.Expander> Steuerelement mit komplexen Inhalt enthält, die eine <xref:System.Windows.Controls.ScrollViewer> Steuerelement. In diesem Beispiel wird eine <xref:System.Windows.Controls.Expander> , die wie in der Abbildung am Anfang dieses Abschnitts ist.  
  
 [!code-csharp[ExpanderRichContent#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ExpanderRichContent#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpanderRichContent/VisualBasic/Window1.xaml.vb#1)]
 [!code-xaml[ExpanderRichContent#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#1)]  
  
<a name="UsingtheAlignmentProperties"></a>   
## <a name="using-the-alignment-properties"></a>Verwenden der Ausrichtungseigenschaften  
 Ausrichten von Inhalt durch Festlegen der <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> und <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> Eigenschaften auf der <xref:System.Windows.Controls.Expander> Steuerelement. Wenn Sie diese Eigenschaften festlegen, wird die Ausrichtung sowohl auf den Header, als auch auf den erweiterten Inhalt angewendet.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Expander>  
 <xref:System.Windows.Controls.ExpandDirection>  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)
