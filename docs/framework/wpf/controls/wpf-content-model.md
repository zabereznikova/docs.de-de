---
title: Inhaltsmodell
ms.date: 03/30/2017
helpviewer_keywords:
- UIElement class [WPF], displaying content
- content model [WPF], controls
- controls [WPF], displaying text
- content display [WPF], controls
- controls [WPF], formatting text
- displaying content [WPF]
- arbitrary content classes [WPF], content model
- ContentControl class [WPF], displaying content
ms.assetid: 214da5ef-547a-4cf8-9b07-4aa8a0e52cdd
ms.openlocfilehash: a84ab2e66b4e373591fc9365b1c17d0bb0c66713
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738284"
---
# <a name="wpf-content-model"></a>WPF-Inhaltsmodell
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ist eine Präsentationsplattform, die viele Steuerelemente und steuerelementähnliche Typen bereitstellt, deren Hauptaufgabe in der Anzeige unterschiedlicher Inhaltstypen besteht. Um zu bestimmen, welches Steuerelement verwendet oder von welchem Steuerelement abgeleitet werden soll, sollten Sie mit den Objektarten vertraut sein, die ein bestimmtes Steuerelement am besten anzeigen können.  
  
 In diesem Thema wird das Inhaltsmodell für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelemente und steuerelementähnliche Typen zusammengefasst. Das Inhaltsmodell beschreibt, welche Inhalte in einem Steuerelement verwendet werden können. In diesem Thema werden ebenfalls die Inhaltseigenschaften für jedes Inhaltsmodell aufgezählt. Eine Inhaltseigenschaft ist eine Eigenschaft, die zum Speichern des Inhalts des Objekts verwendet wird.  

<a name="classes_that_contain_arbitrary_content"></a>   
## <a name="classes-that-contain-arbitrary-content"></a>Klassen mit beliebigem Inhalt  
 Einige Steuerelemente können ein Objekt beliebiger Typen enthalten, z. b. eine Zeichenfolge, ein <xref:System.DateTime> Objekt oder einen <xref:System.Windows.UIElement>, bei dem es sich um einen Container für zusätzliche Elemente handelt. Beispielsweise kann ein <xref:System.Windows.Controls.Button> ein Bild und Text enthalten. oder ein <xref:System.Windows.Controls.CheckBox> kann den Wert <xref:System.DateTime.Now%2A?displayProperty=nameWithType>enthalten.  
  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gibt es vier Klassen, die beliebigen Inhalt enthalten. In der folgenden Tabelle werden die-Klassen aufgelistet, die von <xref:System.Windows.Controls.Control>erben.  
  
|Klassen mit beliebigem Inhalt|Inhalt|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|Ein einzelnes beliebiges Objekt|  
|<xref:System.Windows.Controls.HeaderedContentControl>|Ein Header und ein einzelnes Element, die beide beliebige Objekte sind|  
|<xref:System.Windows.Controls.ItemsControl>|Eine Auflistung beliebiger Objekte|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|Ein Header und eine Auflistung von Elementen, die alle beliebige Objekte sind|  
  
 Steuerelemente, die von diesen Klassen erben, können dieselbe Art von Inhalt enthalten und den Inhalt auf die gleiche Weise behandeln. Die folgende Abbildung zeigt ein Steuerelement aus jedem Inhalts Modell, das ein Bild und Text enthält:  
  
 ![Screenshot, der vier verschiedene Steuerelemente anzeigt, eine aus den einzelnen Inhalts Modellen.](./media/wpf-content-model/control-content-model-image-text.png)  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a>Steuerelemente mit einem einzelnen beliebigen Objekt  
 Die <xref:System.Windows.Controls.ContentControl>-Klasse enthält einen einzelnen Teil des beliebigen Inhalts. Die Inhalts Eigenschaft ist <xref:System.Windows.Controls.ContentControl.Content%2A>. Die folgenden Steuerelemente erben von <xref:System.Windows.Controls.ContentControl> und verwenden dessen Inhalts Modell:  
  
- <xref:System.Windows.Controls.Button>  
  
- <xref:System.Windows.Controls.Primitives.ButtonBase>  
  
- <xref:System.Windows.Controls.CheckBox>  
  
- <xref:System.Windows.Controls.ComboBoxItem>  
  
- <xref:System.Windows.Controls.ContentControl>  
  
- <xref:System.Windows.Controls.Frame>  
  
- <xref:System.Windows.Controls.GridViewColumnHeader>  
  
- <xref:System.Windows.Controls.GroupItem>  
  
- <xref:System.Windows.Controls.Label>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Navigation.NavigationWindow>  
  
- <xref:System.Windows.Controls.RadioButton>  
  
- <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
- <xref:System.Windows.Controls.ScrollViewer>  
  
- <xref:System.Windows.Controls.Primitives.StatusBarItem>  
  
- <xref:System.Windows.Controls.Primitives.ToggleButton>  
  
- <xref:System.Windows.Controls.ToolTip>  
  
- <xref:System.Windows.Controls.UserControl>  
  
- <xref:System.Windows.Window>  
  
 Die folgende Abbildung zeigt vier Schaltflächen, deren <xref:System.Windows.Controls.ContentControl.Content%2A> auf eine Zeichenfolge, ein <xref:System.DateTime> Objekt, eine <xref:System.Windows.Shapes.Rectangle>und eine <xref:System.Windows.Controls.Panel>, die eine <xref:System.Windows.Shapes.Ellipse> und eine <xref:System.Windows.Controls.TextBlock>enthält:  
  
 ![Screenshot, der vier Schaltflächen mit unterschiedlichen Inhaltstypen anzeigt](./media/wpf-content-model/control-content-model-buttons.png)  
  
 Ein Beispiel zum Festlegen der <xref:System.Windows.Controls.ContentControl.Content%2A>-Eigenschaft finden Sie unter <xref:System.Windows.Controls.ContentControl>.  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a>Steuerelemente mit einem Header und einzelnen beliebigen Objekt  
 Die <xref:System.Windows.Controls.HeaderedContentControl>-Klasse erbt von <xref:System.Windows.Controls.ContentControl> und zeigt Inhalt mit einem Header an. Er erbt die Content-Eigenschaft (<xref:System.Windows.Controls.ContentControl.Content%2A>) von <xref:System.Windows.Controls.ContentControl> und definiert die <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>-Eigenschaft, die vom Typ <xref:System.Object>ist. Daher können beide ein beliebiges Objekt sein.  
  
 Die folgenden Steuerelemente erben von <xref:System.Windows.Controls.HeaderedContentControl> und verwenden dessen Inhalts Modell:  
  
- <xref:System.Windows.Controls.Expander>  
  
- <xref:System.Windows.Controls.GroupBox>  
  
- <xref:System.Windows.Controls.TabItem>  
  
 Die folgende Abbildung zeigt zwei <xref:System.Windows.Controls.TabItem> Objekte. Der erste <xref:System.Windows.Controls.TabItem> verfügt über <xref:System.Windows.UIElement> Objekte als <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> und <xref:System.Windows.Controls.ContentControl.Content%2A>. Der <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> wird auf einen <xref:System.Windows.Controls.StackPanel> festgelegt, der eine <xref:System.Windows.Shapes.Ellipse> und eine <xref:System.Windows.Controls.TextBlock>enthält. Der <xref:System.Windows.Controls.ContentControl.Content%2A> wird auf einen <xref:System.Windows.Controls.StackPanel> festgelegt, der einen <xref:System.Windows.Controls.TextBlock> und einen <xref:System.Windows.Controls.Label>enthält. Der zweite <xref:System.Windows.Controls.TabItem> enthält eine Zeichenfolge in der <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> und eine <xref:System.Windows.Controls.TextBlock> in der <xref:System.Windows.Controls.ContentControl.Content%2A>.  
  
 ![TabControl, das unterschiedliche Typen in der Header-Eigenschaft verwendet.](./media/wpf-content-model/control-content-model-tab.png)  
  
 Ein Beispiel zum Erstellen von <xref:System.Windows.Controls.TabItem> Objekten finden Sie unter <xref:System.Windows.Controls.HeaderedContentControl>.  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a>Steuerelemente mit einer Auflistung von beliebigen Objekten  
 Die <xref:System.Windows.Controls.ItemsControl>-Klasse erbt von <xref:System.Windows.Controls.Control> und kann mehrere Elemente enthalten, wie z. b. Zeichen folgen, Objekte oder andere Elemente. Die Inhalts Eigenschaften sind <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> und <xref:System.Windows.Controls.ItemsControl.Items%2A>. <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> wird in der Regel verwendet, um die <xref:System.Windows.Controls.ItemsControl> mit einer Datensammlung aufzufüllen. Wenn Sie keine Auflistung zum Auffüllen des <xref:System.Windows.Controls.ItemsControl>verwenden möchten, können Sie mithilfe der Eigenschaft <xref:System.Windows.Controls.ItemsControl.Items%2A> Elemente hinzufügen.  
  
 Die folgenden Steuerelemente erben von <xref:System.Windows.Controls.ItemsControl> und verwenden dessen Inhalts Modell:  
  
- <xref:System.Windows.Controls.Menu>  
  
- <xref:System.Windows.Controls.Primitives.MenuBase>  
  
- <xref:System.Windows.Controls.ContextMenu>  
  
- <xref:System.Windows.Controls.ComboBox>  
  
- <xref:System.Windows.Controls.ItemsControl>  
  
- <xref:System.Windows.Controls.ListBox>  
  
- <xref:System.Windows.Controls.ListView>  
  
- <xref:System.Windows.Controls.TabControl>  
  
- <xref:System.Windows.Controls.TreeView>  
  
- <xref:System.Windows.Controls.Primitives.Selector>  
  
- <xref:System.Windows.Controls.Primitives.StatusBar>  
  
 Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.ListBox>, die diese Elementtypen enthält:  
  
- Eine Zeichenfolge.  
  
- Ein <xref:System.DateTime> -Objekt.  
  
- Ein <xref:System.Windows.UIElement>.  
  
- Eine <xref:System.Windows.Controls.Panel>, die eine <xref:System.Windows.Shapes.Ellipse> und eine <xref:System.Windows.Controls.TextBlock>enthält.  
  
 ![Screenshot, der ein ListBox mit vier Inhaltstypen anzeigt](./media/wpf-content-model/control-content-model-listbox.png)  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a>Steuerelemente mit einem Header und einer Auflistung von beliebigen Objekten  
 Die <xref:System.Windows.Controls.HeaderedItemsControl>-Klasse erbt von <xref:System.Windows.Controls.ItemsControl> und kann mehrere Elemente, wie z. b. Zeichen folgen, Objekte oder andere Elemente, und einen Header enthalten. Er erbt die <xref:System.Windows.Controls.ItemsControl> Inhalts Eigenschaften, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>und <xref:System.Windows.Controls.ItemsControl.Items%2A>und definiert die <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Eigenschaft, die ein beliebiges Objekt sein kann.  
  
 Die folgenden Steuerelemente erben von <xref:System.Windows.Controls.HeaderedItemsControl> und verwenden dessen Inhalts Modell:  
  
- <xref:System.Windows.Controls.MenuItem>  
  
- <xref:System.Windows.Controls.ToolBar>  
  
- <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>   
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a>Klassen mit einer Auflistung von UIElement-Objekten  
 Die <xref:System.Windows.Controls.Panel>-Klasse positioniert und ordnet untergeordnete <xref:System.Windows.UIElement>-Objekte an. Die Inhalts Eigenschaft ist <xref:System.Windows.Controls.Panel.Children%2A>.  
  
 Die folgenden Klassen erben von der <xref:System.Windows.Controls.Panel>-Klasse und verwenden Ihr Inhalts Modell:  
  
- <xref:System.Windows.Controls.Canvas>  
  
- <xref:System.Windows.Controls.DockPanel>  
  
- <xref:System.Windows.Controls.Grid>  
  
- <xref:System.Windows.Controls.Primitives.TabPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
  
- <xref:System.Windows.Controls.Primitives.UniformGrid>  
  
- <xref:System.Windows.Controls.StackPanel>  
  
- <xref:System.Windows.Controls.VirtualizingPanel>  
  
- <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
- <xref:System.Windows.Controls.WrapPanel>  
  
 Weitere Informationen finden Sie unter [Übersicht über Panel-Elemente](panels-overview.md).  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>   
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a>Klassen, die sich auf die Anzeige eines UIElement-Objekts auswirken  
 Die <xref:System.Windows.Controls.Decorator>-Klasse wendet visuelle Effekte auf oder um ein einzelnes untergeordnetes <xref:System.Windows.UIElement>an. Die Inhalts Eigenschaft ist <xref:System.Windows.Controls.Decorator.Child%2A>. Die folgenden Klassen erben von <xref:System.Windows.Controls.Decorator> und verwenden dessen Inhalts Modell:  
  
- <xref:System.Windows.Documents.AdornerDecorator>  
  
- <xref:System.Windows.Controls.Border>  
  
- <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
- <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
- <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
- <xref:System.Windows.Controls.InkPresenter>  
  
- <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
- <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
- <xref:System.Windows.Controls.Viewbox>  
  
 Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.TextBox>, die ein <xref:System.Windows.Controls.Border> um Sie herum enthält (ist).  
  
 ![TextBox mit schwarzem Rahmen](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")  
Textfeld mit einem Rahmen  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>   
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a>Klassen, die visuelles Feedback zu einem UIElement bereitstellen  
 Die <xref:System.Windows.Documents.Adorner>-Klasse stellt einem Benutzer visuelle Hinweise bereit. Verwenden Sie z. b. eine <xref:System.Windows.Documents.Adorner>, um Elementen funktionale Handles hinzuzufügen oder Zustandsinformationen über ein Steuerelement bereitzustellen. Die <xref:System.Windows.Documents.Adorner>-Klasse stellt ein Framework bereit, sodass Sie Ihre eigenen Adorner erstellen können. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt keine implementierten Adorner bereit. Weitere Informationen finden Sie unter [Übersicht über Adorner](adorners-overview.md).  
  
<a name="classes_that_enable_users_to_enter_text"></a>   
## <a name="classes-that-enable-users-to-enter-text"></a>Klassen, mit denen Benutzer Text eingeben können  
 WPF bietet drei primäre Steuerelemente, mit denen Benutzer Text eingeben können. Jedes Steuerelement zeigt den Text unterschiedlich an. Die folgende Tabelle enthält diese drei textbezogene Steuerelemente, ihre Funktionen bei der Textanzeige und ihre Eigenschaften, die den Text des Steuerelements enthalten.  
  
|Control|Text wird angezeigt als|Inhaltseigenschaft|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|Nur-Text|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|Formatierter Text|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|Ausgeblendeter Text (Zeichen werden maskiert)|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>   
## <a name="classes-that-display-your-text"></a>Klassen, die Ihren Text anzeigen  
 Es können mehrere Klassen verwendet werden, um einfachen oder formatierten Text anzuzeigen. Sie können <xref:System.Windows.Controls.TextBlock> verwenden, um kleine Textmengen anzuzeigen. Wenn Sie große Mengen an Text anzeigen möchten, verwenden Sie die Steuerelemente <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>oder <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
 Der <xref:System.Windows.Controls.TextBlock> verfügt über zwei Inhalts Eigenschaften: <xref:System.Windows.Controls.TextBlock.Text%2A> und <xref:System.Windows.Controls.TextBlock.Inlines%2A>. Wenn Sie Text anzeigen möchten, der eine konsistente Formatierung verwendet, ist die <xref:System.Windows.Controls.TextBlock.Text%2A>-Eigenschaft oft die beste Wahl. Wenn Sie eine andere Formatierung im gesamten Text verwenden möchten, verwenden Sie die <xref:System.Windows.Controls.TextBlock.Inlines%2A>-Eigenschaft. Die <xref:System.Windows.Controls.TextBlock.Inlines%2A>-Eigenschaft ist eine Auflistung von <xref:System.Windows.Documents.Inline>-Objekten, die angeben, wie Text formatiert werden soll.  
  
 In der folgenden Tabelle wird die Content-Eigenschaft für die Klassen <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>und <xref:System.Windows.Controls.FlowDocumentScrollViewer> aufgelistet.  
  
|Control|Inhaltseigenschaft|Inhaltseigenschaftstyp|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|Dokument|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|Dokument|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|Dokument|<xref:System.Windows.Documents.FlowDocument>|  
  
 Der <xref:System.Windows.Documents.FlowDocument> implementiert die <xref:System.Windows.Documents.IDocumentPaginatorSource>-Schnittstelle. Daher können alle drei Klassen eine <xref:System.Windows.Documents.FlowDocument> als Inhalt annehmen.  
  
<a name="classes_that_format_text"></a>   
## <a name="classes-that-format-your-text"></a>Klassen, die den Text formatieren  
 mit <xref:System.Windows.Documents.TextElement> und den zugehörigen Klassen können Sie Text formatieren. <xref:System.Windows.Documents.TextElement> Objekte enthalten und formatieren Text in <xref:System.Windows.Controls.TextBlock>-und <xref:System.Windows.Documents.FlowDocument>-Objekten. Die beiden primären Typen von <xref:System.Windows.Documents.TextElement> Objekten sind <xref:System.Windows.Documents.Block> Elemente und <xref:System.Windows.Documents.Inline> Elemente. Ein <xref:System.Windows.Documents.Block> Element stellt einen TextBlock dar, z. b. einen Absatz oder eine Liste. Ein <xref:System.Windows.Documents.Inline>-Element stellt einen Teil des Texts in einem-Block dar. Viele <xref:System.Windows.Documents.Inline> Klassen geben die Formatierung für den Text an, auf den Sie angewendet werden. Jede <xref:System.Windows.Documents.TextElement> verfügt über ein eigenes Inhalts Modell. Weitere Informationen finden Sie unter [Übersicht über das TextElement-Inhaltsmodell](../advanced/textelement-content-model-overview.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Erweitert](../advanced/index.md)
