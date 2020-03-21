---
title: Übersicht über TreeView
ms.date: 03/30/2017
helpviewer_keywords:
- expanding node [WPF]
- TreeView control [WPF], about TreeView control
- Control class [WPF], TreeView
ms.assetid: 62212512-5a5c-4864-949e-b6a6a3a52c02
ms.openlocfilehash: 267e870e13d26439e4fbcbba3c5741ff84cabe3c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187371"
---
# <a name="treeview-overview"></a>Übersicht über TreeView
Das <xref:System.Windows.Controls.TreeView> Steuerelement bietet eine Möglichkeit, Informationen in einer hierarchischen Struktur mithilfe von zusammenklappbaren Knoten anzuzeigen. In diesem <xref:System.Windows.Controls.TreeView> Thema <xref:System.Windows.Controls.TreeViewItem> werden die und die Steuerelemente vorgestellt und einfache Beispiele für deren Verwendung vorgestellt.  

<a name="Simple_TreeView_Control"></a>
## <a name="what-is-a-treeview"></a>Was versteht man unter einem TreeView-Steuerelement?  
 <xref:System.Windows.Controls.TreeView>ist <xref:System.Windows.Controls.ItemsControl> ein, das die <xref:System.Windows.Controls.TreeViewItem> Elemente mithilfe von Steuerelementen verschachtelt. Im folgenden Beispiel <xref:System.Windows.Controls.TreeView>wird eine erstellt.  
  
 [!code-xaml[TreeViewSnips#EmbeddedTVIs](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#embeddedtvis)]  
  
<a name="Creating_a_TreeView"></a>
## <a name="creating-a-treeview"></a>Erstellen eines TreeView-Steuerelements  
 Das <xref:System.Windows.Controls.TreeView> Steuerelement enthält <xref:System.Windows.Controls.TreeViewItem> eine Hierarchie von Steuerelementen. Ein <xref:System.Windows.Controls.TreeViewItem> Steuerelement <xref:System.Windows.Controls.HeaderedItemsControl> ist ein <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Steuerelement, das eine und eine <xref:System.Windows.Controls.ItemsControl.Items%2A> Auflistung hat.  
  
 Wenn Sie eine <xref:System.Windows.Controls.TreeView> mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]definieren, können <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Sie explizit <xref:System.Windows.Controls.TreeViewItem> den Inhalt eines Steuerelements und die Elemente definieren, aus denen die Auflistung besteht. Die vorstehende Abbildung veranschaulicht diese Methode.  
  
 Sie können auch <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> eine als Datenquelle angeben <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> und dann <xref:System.Windows.Controls.TreeViewItem> a angeben und den Inhalt definieren.  
  
 Um das Layout <xref:System.Windows.Controls.TreeViewItem> eines Steuerelements zu <xref:System.Windows.HierarchicalDataTemplate> definieren, können Sie auch Objekte verwenden. Weitere Informationen und ein Beispiel dazu finden Sie unter [Use SelectedValue, SelectedValuePath, and SelectedItem (Verwenden von SelectedValue, SelectedValuePath und SelectedItem)](how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md)  
  
 Wenn ein Element <xref:System.Windows.Controls.TreeViewItem> kein Steuerelement ist, wird <xref:System.Windows.Controls.TreeViewItem> es automatisch <xref:System.Windows.Controls.TreeView> von einem Steuerelement eingeschlossen, wenn das Steuerelement angezeigt wird.  
  
<a name="Expanding_and_Collapsing_a_TreeViewItem"></a>
## <a name="expanding-and-collapsing-a-treeviewitem"></a>Erweitern und Reduzieren von TreeViewItem-Steuerelementen  
 Wenn der Benutzer <xref:System.Windows.Controls.TreeViewItem>eine <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> erweitert, ist `true`die Eigenschaft auf festgelegt. Sie können auch eine <xref:System.Windows.Controls.TreeViewItem> ohne direkte Benutzeraktion <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> erweitern `true` oder reduzieren, `false` indem Sie die Eigenschaft auf (erweitern) oder (reduzieren) festlegen. Wenn sich diese <xref:System.Windows.Controls.TreeViewItem.Expanded> Eigenschaft <xref:System.Windows.Controls.TreeViewItem.Collapsed> ändert, tritt ein oder ein Ereignis auf.  
  
 Wenn <xref:System.Windows.FrameworkElement.BringIntoView%2A> die Methode für <xref:System.Windows.Controls.TreeViewItem> ein <xref:System.Windows.Controls.TreeViewItem> Steuerelement aufgerufen <xref:System.Windows.Controls.TreeViewItem> wird, werden die und ihre übergeordneten Steuerelemente erweitert. Wenn <xref:System.Windows.Controls.TreeViewItem> a nicht oder teilweise <xref:System.Windows.Controls.TreeView> sichtbar ist, werden die Bildlaufrollen angezeigt, um sie sichtbar zu machen.  
  
<a name="TreeViewItem_Selection"></a>
## <a name="treeviewitem-selection"></a>Auswählen eines TreeViewItem-Steuerelements  
 Wenn ein Benutzer <xref:System.Windows.Controls.TreeViewItem> auf ein Steuerelement <xref:System.Windows.Controls.TreeViewItem.Selected> klickt, um <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> es auszuwählen, tritt das Ereignis auf, und seine Eigenschaft ist auf `true`festgelegt. Der <xref:System.Windows.Controls.TreeViewItem> wird <xref:System.Windows.Controls.TreeView.SelectedItem%2A> auch <xref:System.Windows.Controls.TreeView> zum Steuerelement. Umgekehrt tritt die Auswahl von <xref:System.Windows.Controls.TreeViewItem> einem <xref:System.Windows.Controls.TreeViewItem.Unselected> Steuerelement aus, <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> und seine `false`Eigenschaft wird auf festgelegt.  
  
 Die <xref:System.Windows.Controls.TreeView.SelectedItem%2A> Eigenschaft <xref:System.Windows.Controls.TreeView> auf dem Steuerelement ist eine schreibgeschützte Eigenschaft. Daher können Sie es nicht explizit festlegen. Die <xref:System.Windows.Controls.TreeView.SelectedItem%2A> Eigenschaft wird festgelegt, wenn <xref:System.Windows.Controls.TreeViewItem> der Benutzer <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> auf ein `true` Steuerelement <xref:System.Windows.Controls.TreeViewItem> klickt oder wenn die Eigenschaft auf das Steuerelement festgelegt ist.  
  
 Verwenden <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> Sie die <xref:System.Windows.Controls.TreeView.SelectedValue%2A> Eigenschaft, <xref:System.Windows.Controls.TreeView.SelectedItem%2A>um eine von anzugeben. Weitere Informationen finden Sie unter [Use SelectedValue, SelectedValuePath, and SelectedItem (Verwenden von SelectedValue, SelectedValuePath und SelectedItem)](how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md)  
  
 Sie können einen Ereignishandler <xref:System.Windows.Controls.TreeView.SelectedItemChanged> für das Ereignis registrieren, um zu bestimmen, wann sich eine ausgewählte <xref:System.Windows.Controls.TreeViewItem> Änderung ändert. Der, <xref:System.Windows.RoutedPropertyChangedEventArgs%601> der dem Ereignishandler zur <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A>Verfügung gestellt wird, gibt <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>die an, d. h. die vorherige Auswahl, und die , die die aktuelle Auswahl ist. Es kann kein Wert `null` sein, wenn die Anwendung oder der Benutzer keine vorherige oder aktuelle Auswahl getroffen hat.  
  
<a name="TreeView_Style"></a>
## <a name="treeview-style"></a>TreeView-Format  
 Der Standardstil <xref:System.Windows.Controls.TreeView> für ein Steuerelement <xref:System.Windows.Controls.StackPanel> platziert es <xref:System.Windows.Controls.ScrollViewer> in einem Objekt, das ein Steuerelement enthält. Wenn Sie <xref:System.Windows.FrameworkElement.Width%2A> die <xref:System.Windows.FrameworkElement.Height%2A> und <xref:System.Windows.Controls.TreeView>Eigenschaften für eine festlegen, <xref:System.Windows.Controls.StackPanel> werden diese <xref:System.Windows.Controls.TreeView>Werte verwendet, um die Größe des Objekts zu ändern, das die anzeigt. Wenn der anzuzeigende Inhalt größer als <xref:System.Windows.Controls.ScrollViewer> der Anzeigebereich ist, wird <xref:System.Windows.Controls.TreeView> automatisch ein Anzeige angezeigt, damit der Benutzer durch den Inhalt scrollen kann.  
  
 Um die Darstellung <xref:System.Windows.Controls.TreeViewItem> eines Steuerelements <xref:System.Windows.FrameworkElement.Style%2A> anzupassen, <xref:System.Windows.Style>legen Sie die Eigenschaft auf eine benutzerdefinierte fest.  
  
 Das folgende Beispiel zeigt, <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Controls.Control.FontSize%2A> wie die <xref:System.Windows.Controls.TreeViewItem> und-Eigenschaftswerte für ein Steuerelement mithilfe einer <xref:System.Windows.FrameworkElement.Style%2A>festgelegt werden.  
  
 [!code-xaml[TreeViewSimple#8](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#8)]  
  
<a name="Adding_Images_and_oOther_Content_to_TreeView_Items"></a>
## <a name="adding-images-and-other-content-to-treeview-items"></a>Hinzufügen von Bildern und anderen Inhalten zu TreeView-Elementen  
 Sie können mehr als ein <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Objekt <xref:System.Windows.Controls.TreeViewItem>in den Inhalt einer einschließen. Um mehrere Objekte <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> in den Inhalt einzuschließen, schließen <xref:System.Windows.Controls.Panel> Sie <xref:System.Windows.Controls.StackPanel>die Objekte in ein Layoutsteuerelement ein, z. B. ein oder .  
  
 Das folgende Beispiel zeigt, <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> wie <xref:System.Windows.Controls.TreeViewItem> sie <xref:System.Windows.Controls.CheckBox> <xref:System.Windows.Controls.TextBlock> die von a als <xref:System.Windows.Controls.DockPanel> definieren und die beide in einem Steuerelement eingeschlossen sind.  
  
 [!code-xaml[TreeViewSnips#TVIHeader](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#tviheader)]  
  
 Das folgende Beispiel zeigt, <xref:System.Windows.DataTemplate> wie <xref:System.Windows.Controls.Image> eine <xref:System.Windows.Controls.TextBlock> definiert wird, die <xref:System.Windows.Controls.DockPanel> ein und eine enthält, die in einem Steuerelement eingeschlossen sind. Sie können <xref:System.Windows.DataTemplate> eine verwenden, <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> um <xref:System.Windows.Controls.TreeViewItem>die <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> oder für eine festzulegen.  
  
 [!code-xaml[TreeViewDataBinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewDataBinding/CSharp/Window1.xaml#6)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [How-to-Themen](treeview-how-to-topics.md)
- [WPF-Inhaltsmodell](wpf-content-model.md)
