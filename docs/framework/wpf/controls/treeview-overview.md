---
title: "&#220;bersicht &#252;ber TreeView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Control-Klasse, TreeView"
  - "Erweitern eines Knotens"
  - "TreeView-Steuerelement, Informationen über das TreeView-Steuerelement"
ms.assetid: 62212512-5a5c-4864-949e-b6a6a3a52c02
caps.latest.revision: 33
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 32
---
# &#220;bersicht &#252;ber TreeView
Das <xref:System.Windows.Controls.TreeView>\-Steuerelement bietet eine Möglichkeit, Informationen in einer hierarchischen Struktur durch das Verwenden von reduzierbaren Knoten anzuzeigen.  In diesem Thema werden die Steuerelemente <xref:System.Windows.Controls.TreeView> und <xref:System.Windows.Controls.TreeViewItem> eingeführt. Außerdem sind einfache Beispiele für ihre Verwendung enthalten.  
  
   
  
<a name="Simple_TreeView_Control"></a>   
## Was ist ein TreeView?  
 <xref:System.Windows.Controls.TreeView> ist ein <xref:System.Windows.Controls.ItemsControl>, das die Elemente mithilfe von <xref:System.Windows.Controls.TreeViewItem>\-Steuerelementen schachtelt.  Im folgenden Beispiel wird ein <xref:System.Windows.Controls.TreeView>\-Steuerelement erstellt.  
  
 [!code-xml[TreeViewSnips#EmbeddedTVIs](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#embeddedtvis)]  
  
<a name="Creating_a_TreeView"></a>   
## Erstellen eines TreeView  
 Das <xref:System.Windows.Controls.TreeView>\-Steuerelement enthält eine Hierarchie von <xref:System.Windows.Controls.TreeViewItem>\-Steuerelementen.  Ein <xref:System.Windows.Controls.TreeViewItem>\-Steuerelement ist ein <xref:System.Windows.Controls.HeaderedItemsControl>, das über einen <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> und eine <xref:System.Windows.Controls.ItemsControl.Items%2A>\-Auflistung verfügt.  
  
 Wenn Sie ein <xref:System.Windows.Controls.TreeView> mithilfe von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] definieren, können Sie den <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>\-Inhalt eines <xref:System.Windows.Controls.TreeViewItem>\-Steuerelements und die Elemente, aus denen die zugehörige Auflistung besteht, explizit festlegen.  Die vorherige Darstellung veranschaulicht diese Methode.  
  
 Sie können ebenfalls eine <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> als Datenquelle angeben und dann ein <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> und ein <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> angeben, um den <xref:System.Windows.Controls.TreeViewItem>\-Inhalt zu definieren.  
  
 Zum Definieren des Layouts eines <xref:System.Windows.Controls.TreeViewItem>\-Steuerelements können Sie auch <xref:System.Windows.HierarchicalDataTemplate>\-Objekte verwenden.  Weitere Informationen und ein Beispiel finden Sie unter [Verwendung von SelectedValue, SelectedValuePath und SelectedItem](../../../../docs/framework/wpf/controls/how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).  
  
 Wenn ein Element kein <xref:System.Windows.Controls.TreeViewItem>\-Steuerelement ist, wird es automatisch von einem <xref:System.Windows.Controls.TreeViewItem>\-Steuerelement eingeschlossen, wenn das <xref:System.Windows.Controls.TreeView>\-Steuerelement angezeigt wird.  
  
<a name="Expanding_and_Collapsing_a_TreeViewItem"></a>   
## Erweitern und Reduzieren eines TreeViewItem  
 Wenn der Benutzer ein <xref:System.Windows.Controls.TreeViewItem> erweitert, wird die <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A>\-Eigenschaft auf `true` festgelegt.  Sie können ein <xref:System.Windows.Controls.TreeViewItem> auch ohne direkte Benutzeraktion erweitern oder reduzieren, indem Sie die <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A>\-Eigenschaft auf `true` \(erweitern\) oder `false` \(reduzieren\) festlegen.  Wenn sich diese Eigenschaft ändert, tritt ein <xref:System.Windows.Controls.TreeViewItem.Expanded>\-Ereignis oder ein <xref:System.Windows.Controls.TreeViewItem.Collapsed>\-Ereignis auf.  
  
 Wenn die <xref:System.Windows.FrameworkElement.BringIntoView%2A>\-Methode für ein <xref:System.Windows.Controls.TreeViewItem>\-Steuerelement aufgerufen wird, werden das <xref:System.Windows.Controls.TreeViewItem>\-Steuerelement und dessen übergeordnete <xref:System.Windows.Controls.TreeViewItem>\-Steuerelemente erweitert.  Wenn ein <xref:System.Windows.Controls.TreeViewItem> nicht sichtbar oder nur teilweise sichtbar ist, führt das <xref:System.Windows.Controls.TreeView>\-Steuerelement einen Bildlauf durch, um es sichtbar zu machen.  
  
<a name="TreeViewItem_Selection"></a>   
## TreeViewItem\-Auswahl  
 Wenn ein Benutzer auf ein <xref:System.Windows.Controls.TreeViewItem>\-Steuerelement klickt, um es auszuwählen, wird das <xref:System.Windows.Controls.TreeViewItem.Selected>\-Ereignis ausgelöst und seine <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A>\-Eigenschaft auf `true` festgelegt.  Das <xref:System.Windows.Controls.TreeViewItem> wird außerdem zum <xref:System.Windows.Controls.TreeView.SelectedItem%2A> des <xref:System.Windows.Controls.TreeView>\-Steuerelements.  Ändert sich die Auswahl von einem <xref:System.Windows.Controls.TreeViewItem>\-Steuerelement, wird umgekehrt sein <xref:System.Windows.Controls.TreeViewItem.Unselected>\-Ereignis ausgelöst und seine <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A>\-Eigenschaft auf `false` festgelegt.  
  
 Die <xref:System.Windows.Controls.TreeView.SelectedItem%2A>\-Eigenschaft des <xref:System.Windows.Controls.TreeView>\-Steuerelements ist eine schreibgeschützte Eigenschaft. Daher können Sie sie nicht explizit festlegen.  Die <xref:System.Windows.Controls.TreeView.SelectedItem%2A>\-Eigenschaft wird festgelegt, wenn der Benutzer auf ein <xref:System.Windows.Controls.TreeViewItem>\-Steuerelement klickt oder die <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A>\-Eigenschaft auf `true` für das <xref:System.Windows.Controls.TreeViewItem>\-Steuerelement festgelegt wird.  
  
 MIt der <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A>\-Eigenschaft können Sie eine <xref:System.Windows.Controls.TreeView.SelectedValue%2A>\-Eigenschaft von <xref:System.Windows.Controls.TreeView.SelectedItem%2A> angeben.  Weitere Informationen finden Sie unter [Verwendung von SelectedValue, SelectedValuePath und SelectedItem](../../../../docs/framework/wpf/controls/how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).  
  
 Sie können für das <xref:System.Windows.Controls.TreeView.SelectedItemChanged>\-Ereignis einen Ereignishandler registrieren, um festzustellen, wann sich ein <xref:System.Windows.Controls.TreeViewItem> ändert.  Die <xref:System.Windows.RoutedPropertyChangedEventArgs%601>, die an den Ereignishandler übergeben werden, geben den Wert <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A>, bei dem es sich um die vorherige Auswahl handelt, und den Wert <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A> an, bei dem es sich um die aktuelle Auswahl handelt.  Beide können den Wert `null` enthalten, wenn der Benutzer bisher keine Auswahl vorgenommen hat.  
  
<a name="TreeView_Style"></a>   
## TreeView\-Stil  
 Standardmäßig wird ein <xref:System.Windows.Controls.TreeView>\-Steuerelement in einem <xref:System.Windows.Controls.StackPanel>\-Objekt platziert, das ein <xref:System.Windows.Controls.ScrollViewer>\-Steuerelement enthält.  Wenn Sie die Eigenschaften <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> für ein <xref:System.Windows.Controls.TreeView>\-Steuerelement festlegen, wird das <xref:System.Windows.Controls.StackPanel>\-Objekt, das das <xref:System.Windows.Controls.TreeView>\-Steuerelement anzeigt, anhand dieser Werte dimensioniert.  Wenn der anzuzeigende Inhalt größer als der Anzeigebereich ist, wird automatisch ein <xref:System.Windows.Controls.ScrollViewer>\-Steuerelement angezeigt, sodass der Benutzer einen Bildlauf durch den Inhalt des <xref:System.Windows.Controls.TreeView>\-Steuerelements durchführen kann.  
  
 Um die Darstellung eines <xref:System.Windows.Controls.TreeViewItem>\-Steuerelements anzupassen, legen Sie die <xref:System.Windows.FrameworkElement.Style%2A>\-Eigenschaft auf einen benutzerdefinierten <xref:System.Windows.Style> fest.  
  
 Das folgende Beispiel zeigt, wie die Eigenschaftswerte <xref:System.Windows.Controls.Control.Foreground%2A> und <xref:System.Windows.Controls.Control.FontSize%2A> für ein <xref:System.Windows.Controls.TreeViewItem>\-Steuerelement mithilfe eines <xref:System.Windows.FrameworkElement.Style%2A> festgelegt werden.  
  
 [!code-xml[TreeViewSimple#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#8)]  
  
<a name="Adding_Images_and_oOther_Content_to_TreeView_Items"></a>   
## Hinzufügen von Bildern und anderen Inhalten zu TreeView\-Elementen  
 Sie können mehr als ein Objekt in den <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>\-Inhalt eines <xref:System.Windows.Controls.TreeViewItem>\-Steuerelements einschließen.  Um mehrere Objekte in den <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>\-Inhalt aufzunehmen, umschließen Sie die Objekte mit einem Layoutsteuerelement, wie beispielsweise <xref:System.Windows.Controls.Panel> oder <xref:System.Windows.Controls.StackPanel>.  
  
 Das folgende Beispiel zeigt, wie der <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> eines <xref:System.Windows.Controls.TreeViewItem> als <xref:System.Windows.Controls.CheckBox> und <xref:System.Windows.Controls.TextBlock> definiert wird, die beide von einem <xref:System.Windows.Controls.DockPanel>\-Steuerelement umschlossen werden.  
  
 [!code-xml[TreeViewSnips#TVIHeader](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#tviheader)]  
  
 Das folgende Beispiel zeigt, wie ein <xref:System.Windows.DataTemplate> definiert wird, das ein <xref:System.Windows.Controls.Image> und ein <xref:System.Windows.Controls.TextBlock> enthält, die von einem <xref:System.Windows.Controls.DockPanel>\-Steuerelement umschlossen werden.  Sie können ein <xref:System.Windows.DataTemplate> verwenden, um das <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> oder das <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> für ein <xref:System.Windows.Controls.TreeViewItem> festzulegen.  
  
 [!code-xml[TreeViewDataBinding#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewDataBinding/CSharp/Window1.xaml#6)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.TreeView>   
 <xref:System.Windows.Controls.TreeViewItem>   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)   
 [WPF\-Inhaltsmodell](../../../../docs/framework/wpf/controls/wpf-content-model.md)