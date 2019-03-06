---
title: Übersicht über TreeView
ms.date: 03/30/2017
helpviewer_keywords:
- expanding node [WPF]
- TreeView control [WPF], about TreeView control
- Control class [WPF], TreeView
ms.assetid: 62212512-5a5c-4864-949e-b6a6a3a52c02
ms.openlocfilehash: 5758aead9811cdbaf7f61bbd710092f6b4474ad8
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369629"
---
# <a name="treeview-overview"></a>Übersicht über TreeView
Die <xref:System.Windows.Controls.TreeView> -Steuerelement bietet eine Möglichkeit zum Anzeigen von Informationen in einer hierarchischen Struktur mit reduzierbaren Knoten. In diesem Thema werden die <xref:System.Windows.Controls.TreeView> und <xref:System.Windows.Controls.TreeViewItem> steuert und enthält einfache Beispiele für deren Verwendung.  
  
  
<a name="Simple_TreeView_Control"></a>   
## <a name="what-is-a-treeview"></a>Was versteht man unter einem TreeView-Steuerelement?  
 <xref:System.Windows.Controls.TreeView> ist ein <xref:System.Windows.Controls.ItemsControl> , die die Elemente mithilfe von schachtelt <xref:System.Windows.Controls.TreeViewItem> Steuerelemente. Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.TreeView>.  
  
 [!code-xaml[TreeViewSnips#EmbeddedTVIs](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#embeddedtvis)]  
  
<a name="Creating_a_TreeView"></a>   
## <a name="creating-a-treeview"></a>Erstellen eines TreeView-Steuerelements  
 Die <xref:System.Windows.Controls.TreeView> Steuerelement enthält eine Hierarchie von <xref:System.Windows.Controls.TreeViewItem> Steuerelemente. Ein <xref:System.Windows.Controls.TreeViewItem> Steuerelement ist ein <xref:System.Windows.Controls.HeaderedItemsControl> , bei dem ein <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> und <xref:System.Windows.Controls.ItemsControl.Items%2A> Auflistung.  
  
 Definieren eine <xref:System.Windows.Controls.TreeView> mithilfe [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], können Sie explizit definieren die <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Inhalt eine <xref:System.Windows.Controls.TreeViewItem> -Steuerelement und die Elemente, aus denen die Auflistung besteht. Die vorstehende Abbildung veranschaulicht diese Methode.  
  
 Sie können auch angeben einer <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> als Daten Datenquelle, und geben Sie dann eine <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> und <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> definieren die <xref:System.Windows.Controls.TreeViewItem> Inhalt.  
  
 Zum Definieren des Layouts einer <xref:System.Windows.Controls.TreeViewItem> -Steuerelement, können Sie auch <xref:System.Windows.HierarchicalDataTemplate> Objekte. Weitere Informationen und ein Beispiel dazu finden Sie unter [Use SelectedValue, SelectedValuePath, and SelectedItem (Verwenden von SelectedValue, SelectedValuePath und SelectedItem)](how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md)  
  
 Ein Element ist keiner <xref:System.Windows.Controls.TreeViewItem> -Steuerelement, es ist automatisch eingeschlossen, indem eine <xref:System.Windows.Controls.TreeViewItem> steuern, wann die <xref:System.Windows.Controls.TreeView> -Steuerelements angezeigt wird.  
  
<a name="Expanding_and_Collapsing_a_TreeViewItem"></a>   
## <a name="expanding-and-collapsing-a-treeviewitem"></a>Erweitern und Reduzieren von TreeViewItem-Steuerelementen  
 Wenn der Benutzer erweitert eine <xref:System.Windows.Controls.TreeViewItem>, <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> -Eigenschaftensatz auf `true`. Sie können auch erweitern oder reduzieren eine <xref:System.Windows.Controls.TreeViewItem> ohne direkte nutzeraktion durch Festlegen der <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> Eigenschaft `true` (erweitern) oder `false` (reduzieren). Wenn diese Eigenschaft ändert, ein <xref:System.Windows.Controls.TreeViewItem.Expanded> oder <xref:System.Windows.Controls.TreeViewItem.Collapsed> Ereignis auftritt.  
  
 Bei der <xref:System.Windows.FrameworkElement.BringIntoView%2A> Methode wird aufgerufen, auf eine <xref:System.Windows.Controls.TreeViewItem> -Steuerelement, die <xref:System.Windows.Controls.TreeViewItem> und seinem übergeordneten Element <xref:System.Windows.Controls.TreeViewItem> kontrollmöglichkeiten erweitern können. Wenn eine <xref:System.Windows.Controls.TreeViewItem> ist nicht vollständig oder teilweise sichtbar ist, die <xref:System.Windows.Controls.TreeView> führt einen Bildlauf durch, um es sichtbar zu machen.  
  
<a name="TreeViewItem_Selection"></a>   
## <a name="treeviewitem-selection"></a>Auswählen eines TreeViewItem-Steuerelements  
 Wenn ein Benutzer klickt ein <xref:System.Windows.Controls.TreeViewItem> -Steuerelement, aus der <xref:System.Windows.Controls.TreeViewItem.Selected> Ereignis auftritt, und die zugehörige <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> -Eigenschaftensatz auf `true`. Die <xref:System.Windows.Controls.TreeViewItem> wird die <xref:System.Windows.Controls.TreeView.SelectedItem%2A> von der <xref:System.Windows.Controls.TreeView> Steuerelement. Umgekehrt, wenn die Auswahl von geändert wird eine <xref:System.Windows.Controls.TreeViewItem> -Steuerelement, dessen <xref:System.Windows.Controls.TreeViewItem.Unselected> Ereignis tritt auf, und die zugehörige <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> -Eigenschaftensatz auf `false`.  
  
 Die <xref:System.Windows.Controls.TreeView.SelectedItem%2A> Eigenschaft für die <xref:System.Windows.Controls.TreeView> Steuerelement ist eine schreibgeschützte Eigenschaft; daher Sie nicht explizit festlegen. Die <xref:System.Windows.Controls.TreeView.SelectedItem%2A> Eigenschaft festgelegt ist, klickt der Benutzer auf eine <xref:System.Windows.Controls.TreeViewItem> Steuerelement oder wenn der <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> -Eigenschaftensatz auf `true` auf die <xref:System.Windows.Controls.TreeViewItem> Steuerelement.  
  
 Verwenden der <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> -Eigenschaft an eine <xref:System.Windows.Controls.TreeView.SelectedValue%2A> von eine <xref:System.Windows.Controls.TreeView.SelectedItem%2A>. Weitere Informationen finden Sie unter [Use SelectedValue, SelectedValuePath, and SelectedItem (Verwenden von SelectedValue, SelectedValuePath und SelectedItem)](how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md)  
  
 Sie registrieren einen Ereignishandler, auf die <xref:System.Windows.Controls.TreeView.SelectedItemChanged> Ereignis, um zu ermitteln, wann sich ein <xref:System.Windows.Controls.TreeViewItem> Änderungen. Die <xref:System.Windows.RoutedPropertyChangedEventArgs%601> , die auf das Ereignis-Handler legt dient der <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A>, d.h., dass die vorherige Auswahl, und die <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>, dies ist die aktuelle Auswahl. Es kann kein Wert `null` sein, wenn die Anwendung oder der Benutzer keine vorherige oder aktuelle Auswahl getroffen hat.  
  
<a name="TreeView_Style"></a>   
## <a name="treeview-style"></a>TreeView-Format  
 Das Standardformat für eine <xref:System.Windows.Controls.TreeView> -Steuerelement platziert es innerhalb einer <xref:System.Windows.Controls.StackPanel> -Objekt, enthält eine <xref:System.Windows.Controls.ScrollViewer> Steuerelement. Beim Festlegen der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften für eine <xref:System.Windows.Controls.TreeView>, diese Werte werden verwendet, um die Größe der <xref:System.Windows.Controls.StackPanel> -Objekt, das zeigt die <xref:System.Windows.Controls.TreeView>. Wenn der anzuzeigende Inhalt größer als der Darstellungsbereich ist eine <xref:System.Windows.Controls.ScrollViewer> automatisch angezeigt, damit der Benutzer durch Scrollen kann, die <xref:System.Windows.Controls.TreeView> Inhalt.  
  
 Anpassen die Darstellung von einem <xref:System.Windows.Controls.TreeViewItem> steuern, legen Sie die <xref:System.Windows.FrameworkElement.Style%2A> Eigenschaft, um eine benutzerdefinierte <xref:System.Windows.Style>.  
  
 Das folgende Beispiel zeigt, wie Sie festlegen der <xref:System.Windows.Controls.Control.Foreground%2A> und <xref:System.Windows.Controls.Control.FontSize%2A> Eigenschaftswerte für eine <xref:System.Windows.Controls.TreeViewItem> -Steuerelement unter Verwendung einer <xref:System.Windows.FrameworkElement.Style%2A>.  
  
 [!code-xaml[TreeViewSimple#8](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#8)]  
  
<a name="Adding_Images_and_oOther_Content_to_TreeView_Items"></a>   
## <a name="adding-images-and-other-content-to-treeview-items"></a>Hinzufügen von Bildern und anderen Inhalten zu TreeView-Elementen  
 Sie können mehr als ein Objekt im einschließen der <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Inhalt eine <xref:System.Windows.Controls.TreeViewItem>. Einschließen von mehreren Objekten in <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Inhalt, fügen Sie die Objekte in ein Layoutsteuerelement, wie z. B. eine <xref:System.Windows.Controls.Panel> oder <xref:System.Windows.Controls.StackPanel>.  
  
 Das folgende Beispiel zeigt, wie Sie definieren die <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> von einer <xref:System.Windows.Controls.TreeViewItem> als eine <xref:System.Windows.Controls.CheckBox> und <xref:System.Windows.Controls.TextBlock> , dass beide in eingeschlossen sind ein <xref:System.Windows.Controls.DockPanel> Steuerelement.  
  
 [!code-xaml[TreeViewSnips#TVIHeader](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#tviheader)]  
  
 Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.DataTemplate> , enthält ein <xref:System.Windows.Controls.Image> und <xref:System.Windows.Controls.TextBlock> , die in eingeschlossen sind ein <xref:System.Windows.Controls.DockPanel> Steuerelement. Können Sie eine <xref:System.Windows.DataTemplate> Festlegen der <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> oder <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> für eine <xref:System.Windows.Controls.TreeViewItem>.  
  
 [!code-xaml[TreeViewDataBinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewDataBinding/CSharp/Window1.xaml#6)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [Themen zu Vorgehensweisen](treeview-how-to-topics.md)
- [WPF-Inhaltsmodell](wpf-content-model.md)
