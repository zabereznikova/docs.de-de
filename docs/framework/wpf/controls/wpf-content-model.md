---
title: WPF-Inhaltsmodell
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
ms.openlocfilehash: 652a8b831d29c8da8dc651558351a5bd4ff5ce84
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665160"
---
# <a name="wpf-content-model"></a>WPF-Inhaltsmodell
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ist eine Präsentationsplattform, die viele Steuerelemente und steuerelementähnliche Typen bereitstellt, deren Hauptaufgabe in der Anzeige unterschiedlicher Inhaltstypen besteht. Um zu bestimmen, welches Steuerelement verwendet oder von welchem Steuerelement abgeleitet werden soll, sollten Sie mit den Objektarten vertraut sein, die ein bestimmtes Steuerelement am besten anzeigen können.  
  
 In diesem Thema wird das Inhaltsmodell für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelemente und steuerelementähnliche Typen zusammengefasst. Das Inhaltsmodell beschreibt, welche Inhalte in einem Steuerelement verwendet werden können. In diesem Thema werden ebenfalls die Inhaltseigenschaften für jedes Inhaltsmodell aufgezählt. Eine Inhaltseigenschaft ist eine Eigenschaft, die zum Speichern des Inhalts des Objekts verwendet wird.  

<a name="classes_that_contain_arbitrary_content"></a>   
## <a name="classes-that-contain-arbitrary-content"></a>Klassen mit beliebigem Inhalt  
 Einige Steuerelemente können ein Objekt eines beliebigen Typs, z. B. eine Zeichenfolge, enthalten eine <xref:System.DateTime> Objekt oder ein <xref:System.Windows.UIElement> , einen Container für zusätzliche Elemente. Z. B. eine <xref:System.Windows.Controls.Button> kann ein Bild und Text enthalten oder ein <xref:System.Windows.Controls.CheckBox> darf den Wert des <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.  
  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gibt es vier Klassen, die beliebigen Inhalt enthalten. Die folgende Tabelle enthält die Klassen, die von erben <xref:System.Windows.Controls.Control>.  
  
|Klassen mit beliebigem Inhalt|Content|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|Ein einzelnes beliebiges Objekt|  
|<xref:System.Windows.Controls.HeaderedContentControl>|Ein Header und ein einzelnes Element, die beide beliebige Objekte sind|  
|<xref:System.Windows.Controls.ItemsControl>|Eine Auflistung beliebiger Objekte|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|Ein Header und eine Auflistung von Elementen, die alle beliebige Objekte sind|  
  
 Steuerelemente, die von diesen Klassen erben, können dieselbe Art von Inhalt enthalten und den Inhalt auf die gleiche Weise behandeln. Die folgende Abbildung zeigt ein Steuerelement aus den einzelnen Inhaltsmodellen, das ein Bild enthält und Text:  
  
 ![Screenshot mit vier verschiedene Steuerelemente, die von jedes Inhaltsmodell aufgezählt.](./media/wpf-content-model/control-content-model-image-text.png)  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a>Steuerelemente mit einem einzelnen beliebigen Objekt  
 Die <xref:System.Windows.Controls.ContentControl> Klasse enthält nur ein beliebiges Inhaltselement. Die Inhaltseigenschaft ist <xref:System.Windows.Controls.ContentControl.Content%2A>. Die folgenden Steuerelemente erben von <xref:System.Windows.Controls.ContentControl> und verwenden dessen Inhaltsmodell:  
  
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
  
 Die folgende Abbildung zeigt vier Schaltflächen, deren <xref:System.Windows.Controls.ContentControl.Content%2A> festgelegt ist, in eine Zeichenfolge, ein <xref:System.DateTime> Objekt eine <xref:System.Windows.Shapes.Rectangle>, und ein <xref:System.Windows.Controls.Panel> , enthält ein <xref:System.Windows.Shapes.Ellipse> und ein <xref:System.Windows.Controls.TextBlock>:  
  
 ![Screenshot mit vier Schaltflächen mit unterschiedlichen Inhaltstypen.](./media/wpf-content-model/control-content-model-buttons.png)  
  
 Ein Beispiel zum Festlegen der <xref:System.Windows.Controls.ContentControl.Content%2A> -Eigenschaft finden Sie unter <xref:System.Windows.Controls.ContentControl>.  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a>Steuerelemente mit einem Header und einzelnen beliebigen Objekt  
 Die <xref:System.Windows.Controls.HeaderedContentControl> Klasse erbt von <xref:System.Windows.Controls.ContentControl> und zeigt den Inhalt mit einem Header an. Es erbt die Inhaltseigenschaft, <xref:System.Windows.Controls.ContentControl.Content%2A>, von <xref:System.Windows.Controls.ContentControl> und definiert die <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> Eigenschaft vom Typ <xref:System.Object>daher beide können ein beliebiges Objekt sein.  
  
 Die folgenden Steuerelemente erben von <xref:System.Windows.Controls.HeaderedContentControl> und verwenden dessen Inhaltsmodell:  
  
- <xref:System.Windows.Controls.Expander>  
  
- <xref:System.Windows.Controls.GroupBox>  
  
- <xref:System.Windows.Controls.TabItem>  
  
 Die folgende Abbildung zeigt zwei <xref:System.Windows.Controls.TabItem> Objekte. Die erste <xref:System.Windows.Controls.TabItem> hat <xref:System.Windows.UIElement> Objekte als die <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> und <xref:System.Windows.Controls.ContentControl.Content%2A>. Die <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> nastaven NA hodnotu eine <xref:System.Windows.Controls.StackPanel> , enthält ein <xref:System.Windows.Shapes.Ellipse> und <xref:System.Windows.Controls.TextBlock>. Die <xref:System.Windows.Controls.ContentControl.Content%2A> nastaven NA hodnotu eine <xref:System.Windows.Controls.StackPanel> , enthält eine <xref:System.Windows.Controls.TextBlock> und <xref:System.Windows.Controls.Label>. Die zweite <xref:System.Windows.Controls.TabItem> hat eine Zeichenfolge die <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> und <xref:System.Windows.Controls.TextBlock> in die <xref:System.Windows.Controls.ContentControl.Content%2A>.  
  
 ![TabControl-Komponente, die verschiedene Arten in die Header-Eigenschaft verwendet.](./media/wpf-content-model/control-content-model-tab.png)  
  
 Ein Beispiel zum Erstellen von <xref:System.Windows.Controls.TabItem> Objekten finden Sie <xref:System.Windows.Controls.HeaderedContentControl>.  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a>Steuerelemente mit einer Auflistung von beliebigen Objekten  
 Die <xref:System.Windows.Controls.ItemsControl> Klasse erbt von <xref:System.Windows.Controls.Control> und kann mehrere Elemente, z. B. Zeichenfolgen, Objekte oder andere Elemente enthalten. Die Inhaltseigenschaften sind <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> und <xref:System.Windows.Controls.ItemsControl.Items%2A>. <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> dient normalerweise zum Auffüllen der <xref:System.Windows.Controls.ItemsControl> mit einer datenauflistung. Wenn Sie nicht, verwenden Sie eine Auflistung zum Auffüllen möchten der <xref:System.Windows.Controls.ItemsControl>, Sie können Elemente hinzufügen, mit der <xref:System.Windows.Controls.ItemsControl.Items%2A> Eigenschaft.  
  
 Die folgenden Steuerelemente erben von <xref:System.Windows.Controls.ItemsControl> und verwenden dessen Inhaltsmodell:  
  
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
  
 Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.ListBox> , enthält die folgenden Elementtypen:  
  
- Eine Zeichenfolge.  
  
- Ein <xref:System.DateTime>-Objekt.  
  
- Ein <xref:System.Windows.UIElement>.  
  
- Ein <xref:System.Windows.Controls.Panel> , enthält ein <xref:System.Windows.Shapes.Ellipse> und <xref:System.Windows.Controls.TextBlock>.  
  
 ![Screenshot mit einer ListBox mit vier Inhaltstypen.](./media/wpf-content-model/control-content-model-listbox.png)  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a>Steuerelemente mit einem Header und einer Auflistung von beliebigen Objekten  
 Die <xref:System.Windows.Controls.HeaderedItemsControl> Klasse erbt von <xref:System.Windows.Controls.ItemsControl> und kann mehrere Elemente, z. B. Zeichenfolgen, Objekte oder andere Elemente und einen Header enthalten. Es erbt die <xref:System.Windows.Controls.ItemsControl> -Inhaltseigenschaften, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, und <xref:System.Windows.Controls.ItemsControl.Items%2A>, und definiert die <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> -Eigenschaft, die ein beliebiges Objekt sein kann.  
  
 Die folgenden Steuerelemente erben von <xref:System.Windows.Controls.HeaderedItemsControl> und verwenden dessen Inhaltsmodell:  
  
- <xref:System.Windows.Controls.MenuItem>  
  
- <xref:System.Windows.Controls.ToolBar>  
  
- <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>   
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a>Klassen mit einer Auflistung von UIElement-Objekten  
 Die <xref:System.Windows.Controls.Panel> -Klasse positioniert und ordnet untergeordnete <xref:System.Windows.UIElement> Objekte. Die Inhaltseigenschaft ist <xref:System.Windows.Controls.Panel.Children%2A>.  
  
 Die folgenden Klassen erben von der <xref:System.Windows.Controls.Panel> Klasse, und verwenden dessen Inhaltsmodell:  
  
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
 Die <xref:System.Windows.Controls.Decorator> -Klasse wendet visuelle Effekte auf oder um ein einzelnes untergeordnetes Element <xref:System.Windows.UIElement>. Die Inhaltseigenschaft ist <xref:System.Windows.Controls.Decorator.Child%2A>. Die folgenden Klassen erben von <xref:System.Windows.Controls.Decorator> und verwenden dessen Inhaltsmodell:  
  
- <xref:System.Windows.Documents.AdornerDecorator>  
  
- <xref:System.Windows.Controls.Border>  
  
- <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
- <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
- <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
- <xref:System.Windows.Controls.InkPresenter>  
  
- <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
- <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
- <xref:System.Windows.Controls.Viewbox>  
  
 Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.TextBox> aufweist (versehen mit) eine <xref:System.Windows.Controls.Border> darum.  
  
 ![TextBox mit schwarzem Rahmen](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")  
Textfeld mit einem Rahmen  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>   
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a>Klassen, die visuelles Feedback zu einem UIElement bereitstellen  
 Die <xref:System.Windows.Documents.Adorner> -Klasse stellt visuelle Hinweise zu einem Benutzer. Verwenden Sie z. B. eine <xref:System.Windows.Documents.Adorner> um Elementen funktionale Handles hinzuzufügen oder Zustandsinformationen über Steuerelemente bereitzustellen. Die <xref:System.Windows.Documents.Adorner> Klasse stellt ein Framework bereit, sodass Sie eigene Adorner erstellen können. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt keine implementierten Adorner bereit. Weitere Informationen finden Sie unter [Übersicht über Adorner](adorners-overview.md).  
  
<a name="classes_that_enable_users_to_enter_text"></a>   
## <a name="classes-that-enable-users-to-enter-text"></a>Klassen, mit denen Benutzer Text eingeben können  
 WPF bietet drei primäre Steuerelemente, mit denen Benutzer Text eingeben können. Jedes Steuerelement zeigt den Text unterschiedlich an. Die folgende Tabelle enthält diese drei textbezogene Steuerelemente, ihre Funktionen bei der Textanzeige und ihre Eigenschaften, die den Text des Steuerelements enthalten.  
  
|Steuerelement|Text wird angezeigt als|Inhaltseigenschaft|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|Nur-Text|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|Formatierter Text|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|Ausgeblendeter Text (Zeichen werden maskiert)|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>   
## <a name="classes-that-display-your-text"></a>Klassen, die Ihren Text anzeigen  
 Es können mehrere Klassen verwendet werden, um einfachen oder formatierten Text anzuzeigen. Sie können <xref:System.Windows.Controls.TextBlock> um kleine Mengen an Text anzuzeigen. Wenn Sie große Textmengen anzeigen möchten, verwenden Sie die <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, oder <xref:System.Windows.Controls.FlowDocumentScrollViewer> Steuerelemente.  
  
 Die <xref:System.Windows.Controls.TextBlock> verfügt über zwei Inhaltseigenschaften: <xref:System.Windows.Controls.TextBlock.Text%2A> und <xref:System.Windows.Controls.TextBlock.Inlines%2A>. Wenn Sie möchten, um Text anzuzeigen, die konsistente Formatierung, verwendet der <xref:System.Windows.Controls.TextBlock.Text%2A> Eigenschaft ist häufig die beste Wahl. Wenn Sie im gesamten Text eine andere Formatierung verwenden möchten, verwenden Sie die <xref:System.Windows.Controls.TextBlock.Inlines%2A> Eigenschaft. Die <xref:System.Windows.Controls.TextBlock.Inlines%2A> Eigenschaft ist eine Sammlung von <xref:System.Windows.Documents.Inline> -Objekte, die Formatierung von Text anzugeben.  
  
 Die folgende Tabelle listet die Inhaltseigenschaft für <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, und <xref:System.Windows.Controls.FlowDocumentScrollViewer> Klassen.  
  
|Steuerelement|Inhaltseigenschaft|Inhaltseigenschaftstyp|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|Dokument|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|Dokument|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|Dokument|<xref:System.Windows.Documents.FlowDocument>|  
  
 Die <xref:System.Windows.Documents.FlowDocument> implementiert die <xref:System.Windows.Documents.IDocumentPaginatorSource> Schnittstelle; deshalb können alle drei Klassen durchführen einer <xref:System.Windows.Documents.FlowDocument> als Inhalt.  
  
<a name="classes_that_format_text"></a>   
## <a name="classes-that-format-your-text"></a>Klassen, die den Text formatieren  
 <xref:System.Windows.Documents.TextElement> und den zugehörigen Klassen können Sie Text formatieren. <xref:System.Windows.Documents.TextElement> -Objekte enthalten, und Formatieren von Text in <xref:System.Windows.Controls.TextBlock> und <xref:System.Windows.Documents.FlowDocument> Objekte. Die zwei primären Typen von <xref:System.Windows.Documents.TextElement> Objekte sind <xref:System.Windows.Documents.Block> Elemente und <xref:System.Windows.Documents.Inline> Elemente. Ein <xref:System.Windows.Documents.Block> -Element stellt einen Textblock, z. B. einen Absatz oder eine Liste dar. Ein <xref:System.Windows.Documents.Inline> -Element stellt einen Teil des Texts in einem Block dar. Viele <xref:System.Windows.Documents.Inline> -Klassen geben die Formatierung für den Text, der auf dem sie angewendet werden. Jede <xref:System.Windows.Documents.TextElement> verfügt über ein eigenes Inhaltsmodell. Weitere Informationen finden Sie unter [Übersicht über das TextElement-Inhaltsmodell](../advanced/textelement-content-model-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- [Erweitert](../advanced/index.md)
