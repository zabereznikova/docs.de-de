---
title: Übersicht über TreeView
description: Erfahren Sie, wie das Windows Presentation Foundation TreeView-Steuerelement mithilfe von Knoten, einschließlich einfacher Beispiele, Informationen in einer hierarchischen Struktur anzeigt.
ms.date: 03/30/2017
helpviewer_keywords:
- expanding node [WPF]
- TreeView control [WPF], about TreeView control
- Control class [WPF], TreeView
ms.assetid: 62212512-5a5c-4864-949e-b6a6a3a52c02
ms.openlocfilehash: 6ef77febdd3facb7c7e1af566841c2a1aeaff810
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164541"
---
# <a name="treeview-overview"></a>Übersicht über TreeView
Das- <xref:System.Windows.Controls.TreeView> Steuerelement bietet eine Möglichkeit, Informationen in einer hierarchischen Struktur mithilfe von redusible-Knoten anzuzeigen. In diesem Thema <xref:System.Windows.Controls.TreeView> werden die-und-Steuer <xref:System.Windows.Controls.TreeViewItem> Elemente vorgestellt und einfache Beispiele für deren Verwendung bereitstellt.  

<a name="Simple_TreeView_Control"></a>
## <a name="what-is-a-treeview"></a>Was versteht man unter einem TreeView-Steuerelement?  
 <xref:System.Windows.Controls.TreeView>ist eine <xref:System.Windows.Controls.ItemsControl> , die die Elemente mithilfe von-Steuerelementen schachtelt <xref:System.Windows.Controls.TreeViewItem> . Im folgenden Beispiel wird ein erstellt <xref:System.Windows.Controls.TreeView> .  
  
 [!code-xaml[TreeViewSnips#EmbeddedTVIs](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#embeddedtvis)]  
  
<a name="Creating_a_TreeView"></a>
## <a name="creating-a-treeview"></a>Erstellen eines TreeView-Steuerelements  
 Das- <xref:System.Windows.Controls.TreeView> Steuerelement enthält eine Hierarchie von Steuer <xref:System.Windows.Controls.TreeViewItem> Elementen. Ein <xref:System.Windows.Controls.TreeViewItem> -Steuerelement ist ein <xref:System.Windows.Controls.HeaderedItemsControl> , das eine <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> und eine-Auflistung aufweist <xref:System.Windows.Controls.ItemsControl.Items%2A> .  
  
 Wenn Sie mit definieren <xref:System.Windows.Controls.TreeView> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , können Sie den <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Inhalt eines <xref:System.Windows.Controls.TreeViewItem> Steuer Elements und die Elemente, aus denen seine Auflistung besteht, explizit definieren. Die vorstehende Abbildung veranschaulicht diese Methode.  
  
 Sie können auch <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> als Datenquelle angeben und dann einen <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> und angeben <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> , um den Inhalt zu definieren <xref:System.Windows.Controls.TreeViewItem> .  
  
 Um das Layout eines Steuer Elements zu definieren <xref:System.Windows.Controls.TreeViewItem> , können Sie auch- <xref:System.Windows.HierarchicalDataTemplate> Objekte verwenden. Weitere Informationen und ein Beispiel dazu finden Sie unter [Use SelectedValue, SelectedValuePath, and SelectedItem (Verwenden von SelectedValue, SelectedValuePath und SelectedItem)](how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md)  
  
 Wenn ein Element kein Steuerelement ist <xref:System.Windows.Controls.TreeViewItem> , wird es automatisch von einem-Steuerelement eingeschlossen, <xref:System.Windows.Controls.TreeViewItem> Wenn das <xref:System.Windows.Controls.TreeView> Steuerelement angezeigt wird.  
  
<a name="Expanding_and_Collapsing_a_TreeViewItem"></a>
## <a name="expanding-and-collapsing-a-treeviewitem"></a>Erweitern und Reduzieren von TreeViewItem-Steuerelementen  
 Wenn der Benutzer eine erweitert <xref:System.Windows.Controls.TreeViewItem> , wird die- <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> Eigenschaft auf festgelegt `true` . Sie können auch eine <xref:System.Windows.Controls.TreeViewItem> ohne direkte Benutzeraktion erweitern oder reduzieren, indem Sie die- <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> Eigenschaft auf `true` (Expand) oder `false` (Collapse) festlegen. Wenn diese Eigenschaft geändert wird, <xref:System.Windows.Controls.TreeViewItem.Expanded> tritt ein-oder- <xref:System.Windows.Controls.TreeViewItem.Collapsed> Ereignis auf.  
  
 Wenn die <xref:System.Windows.FrameworkElement.BringIntoView%2A> -Methode für ein-Steuerelement aufgerufen wird <xref:System.Windows.Controls.TreeViewItem> , werden die <xref:System.Windows.Controls.TreeViewItem> und deren übergeordnete Steuer <xref:System.Windows.Controls.TreeViewItem> Elemente erweitert. Wenn ein <xref:System.Windows.Controls.TreeViewItem> nicht sichtbar oder teilweise sichtbar ist, wird der scrollvorgang durchgeführt, <xref:System.Windows.Controls.TreeView> um ihn sichtbar zu machen.  
  
<a name="TreeViewItem_Selection"></a>
## <a name="treeviewitem-selection"></a>Auswählen eines TreeViewItem-Steuerelements  
 Wenn ein Benutzer auf ein Steuerelement klickt, <xref:System.Windows.Controls.TreeViewItem> um es auszuwählen, <xref:System.Windows.Controls.TreeViewItem.Selected> tritt das-Ereignis auf, und seine- <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> Eigenschaft wird auf festgelegt `true` . Der <xref:System.Windows.Controls.TreeViewItem> wird auch der <xref:System.Windows.Controls.TreeView.SelectedItem%2A> des <xref:System.Windows.Controls.TreeView> Steuer Elements. Umgekehrt, wenn sich die Auswahl von einem-Steuerelement ändert <xref:System.Windows.Controls.TreeViewItem> , <xref:System.Windows.Controls.TreeViewItem.Unselected> tritt das-Ereignis auf, und die- <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> Eigenschaft wird auf festgelegt `false` .  
  
 Die <xref:System.Windows.Controls.TreeView.SelectedItem%2A> -Eigenschaft für das- <xref:System.Windows.Controls.TreeView> Steuerelement ist eine schreibgeschützte Eigenschaft und kann daher nicht explizit festgelegt werden. Die- <xref:System.Windows.Controls.TreeView.SelectedItem%2A> Eigenschaft wird festgelegt, wenn der Benutzer auf ein-Steuerelement klickt <xref:System.Windows.Controls.TreeViewItem> oder wenn die- <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> Eigenschaft für das Steuerelement auf festgelegt ist `true` <xref:System.Windows.Controls.TreeViewItem> .  
  
 Verwenden Sie die- <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> Eigenschaft, um ein-Objekt anzugeben <xref:System.Windows.Controls.TreeView.SelectedValue%2A> <xref:System.Windows.Controls.TreeView.SelectedItem%2A> . Weitere Informationen finden Sie unter [Use SelectedValue, SelectedValuePath, and SelectedItem (Verwenden von SelectedValue, SelectedValuePath und SelectedItem)](how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md)  
  
 Sie können einen Ereignishandler für das <xref:System.Windows.Controls.TreeView.SelectedItemChanged> Ereignis registrieren, um zu bestimmen, wann eine ausgewählte <xref:System.Windows.Controls.TreeViewItem> geändert wird. Der, der <xref:System.Windows.RoutedPropertyChangedEventArgs%601> für den-Ereignishandler bereitgestellt wird, gibt das an, bei dem es sich um <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A> die vorherige Auswahl handelt, und die <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A> , die die aktuelle Auswahl ist. Es kann kein Wert `null` sein, wenn die Anwendung oder der Benutzer keine vorherige oder aktuelle Auswahl getroffen hat.  
  
<a name="TreeView_Style"></a>
## <a name="treeview-style"></a>TreeView-Format  
 Der Standardstil für ein <xref:System.Windows.Controls.TreeView> Steuerelement platziert es in einem- <xref:System.Windows.Controls.StackPanel> Objekt, das ein-Steuerelement enthält <xref:System.Windows.Controls.ScrollViewer> . Wenn Sie die <xref:System.Windows.FrameworkElement.Width%2A> -Eigenschaft und die-Eigenschaft <xref:System.Windows.FrameworkElement.Height%2A> für einen festlegen <xref:System.Windows.Controls.TreeView> , werden diese Werte verwendet, um das Objekt zu verkleinern, das <xref:System.Windows.Controls.StackPanel> anzeigt <xref:System.Windows.Controls.TreeView> . Wenn der anzuzeigende Inhalt größer als der Anzeigebereich ist, wird <xref:System.Windows.Controls.ScrollViewer> automatisch angezeigt, sodass der Benutzer einen Bildlauf durch den Inhalt durchführen kann <xref:System.Windows.Controls.TreeView> .  
  
 Um die Darstellung eines Steuer Elements anzupassen <xref:System.Windows.Controls.TreeViewItem> , legen Sie die- <xref:System.Windows.FrameworkElement.Style%2A> Eigenschaft auf eine benutzerdefinierte fest <xref:System.Windows.Style> .  
  
 Im folgenden Beispiel wird gezeigt, wie die <xref:System.Windows.Controls.Control.Foreground%2A> -und- <xref:System.Windows.Controls.Control.FontSize%2A> Eigenschaftswerte für ein- <xref:System.Windows.Controls.TreeViewItem> Steuerelement mithilfe von festgelegt werden <xref:System.Windows.FrameworkElement.Style%2A> .  
  
 [!code-xaml[TreeViewSimple#8](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#8)]  
  
<a name="Adding_Images_and_oOther_Content_to_TreeView_Items"></a>
## <a name="adding-images-and-other-content-to-treeview-items"></a>Hinzufügen von Bildern und anderen Inhalten zu TreeView-Elementen  
 Sie können mehr als ein Objekt in den <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Inhalt eines einschließen <xref:System.Windows.Controls.TreeViewItem> . Wenn Sie mehrere Objekte in <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> den Inhalt einschließen möchten, schließen Sie die Objekte in ein Layoutsteuerelement ein, z <xref:System.Windows.Controls.Panel> <xref:System.Windows.Controls.StackPanel> . b. oder.  
  
 Im folgenden Beispiel wird gezeigt, wie die <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> eines <xref:System.Windows.Controls.TreeViewItem> als <xref:System.Windows.Controls.CheckBox> und <xref:System.Windows.Controls.TextBlock> in einem-Steuerelement definiert werden <xref:System.Windows.Controls.DockPanel> .  
  
 [!code-xaml[TreeViewSnips#TVIHeader](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#tviheader)]  
  
 Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.DataTemplate> -Element definiert wird, das eine <xref:System.Windows.Controls.Image> und eine enthält <xref:System.Windows.Controls.TextBlock> , die in einem-Steuerelement eingeschlossen sind <xref:System.Windows.Controls.DockPanel> . Sie können einen verwenden <xref:System.Windows.DataTemplate> , um das <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> oder <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> für ein festzulegen <xref:System.Windows.Controls.TreeViewItem> .  
  
 [!code-xaml[TreeViewDataBinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewDataBinding/CSharp/Window1.xaml#6)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [Artikel zu Vorgehensweisen](treeview-how-to-topics.md)
- [WPF-Inhaltsmodell](wpf-content-model.md)
