---
title: Übersicht über ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ListView
- ListView controls [WPF], about ListView control
ms.assetid: 989e12b0-260e-4570-95c6-489284003ce2
ms.openlocfilehash: 5a7e640b7398c2034933688ea6356ef14692f8f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557380"
---
# <a name="listview-overview"></a>Übersicht über ListView
Die <xref:System.Windows.Controls.ListView> Steuerelement stellt die Infrastruktur, um eine Reihe von Datenelementen in verschiedenen Layouts oder Ansichten anzuzeigen. Benutzer können damit z.B. die Datenelemente in einer Tabelle anzeigen und die Spalten sortieren.  
  
  
<a name="WhatisaListView"></a>   
## <a name="what-is-a-listview"></a>Was ist ein ListView-Steuerelement?  
 Die <xref:System.Windows.Controls.ListView> -Steuerelement ist ein <xref:System.Windows.Controls.ItemsControl> , stammt aus <xref:System.Windows.Controls.ListBox>. In der Regel enthaltenen Elemente sind Elemente einer Datensammlung und werden als dargestellt <xref:System.Windows.Controls.ListViewItem> Objekte. Ein <xref:System.Windows.Controls.ListViewItem> ist eine <xref:System.Windows.Controls.ContentControl> und kann nur ein einzelnes untergeordnetes Element enthalten. Dieses untergeordnete Element kann jedoch ein beliebiges visuelles Element sein.  
  
<a name="DefiningaListViewView"></a>   
## <a name="defining-a-view-mode-for-a-listview"></a>Definieren eines Anzeigemodus für ein ListView-Steuerelement  
 An einen Anzeigemodus für den Inhalt einer <xref:System.Windows.Controls.ListView> -Steuerelements legen Sie die <xref:System.Windows.Controls.ListView.View%2A> Eigenschaft. Eine Ansichtsmodus, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet ist <xref:System.Windows.Controls.GridView>, woraufhin eine Auflistung von Datenelementen in einer Tabelle, die anpassbare Spalten aufweist.  
  
 Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.GridView> für eine <xref:System.Windows.Controls.ListView> Steuerelement, das Informationen zu Mitarbeitern anzeigt.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 Die folgende Abbildung zeigt, wie die Daten aus dem vorherigen Beispiel angezeigt werden.  
  
 ![ListView with GridView output](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")  
  
 Sie können einen benutzerdefinierten Ansichtsmodus erstellen, durch die Definition einer Klasse, die von erben die <xref:System.Windows.Controls.ViewBase> Klasse. Die <xref:System.Windows.Controls.ViewBase> Klasse bietet die Infrastruktur, die Sie benötigen, um eine benutzerdefinierte Ansicht zu erstellen. Weitere Informationen dazu, wie Sie eine benutzerdefinierte Ansicht erstellen, finden Sie unter [Erstellen eines benutzerdefinierten Ansichtsmodus für eine ListView](../../../../docs/framework/wpf/controls/how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="BindingDatatoaListView"></a>   
## <a name="binding-data-to-a-listview"></a>Binden von Daten an ein ListView-Steuerelement  
 Verwenden der <xref:System.Windows.Controls.ItemsControl.Items%2A> und <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaften zur Angabe der Elemente für eine <xref:System.Windows.Controls.ListView> Steuerelement. Im folgenden Beispiel wird die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft für eine Datensammlung, die aufgerufen wird `EmployeeInfoDataSource`.  
  
 [!code-xaml[ListViewCode#ItemsSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#itemssource)]  
  
 In einem <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridViewColumn> Binden von Objekten angegebenen Datenfeldern. Im folgenden Beispiel bindet ein <xref:System.Windows.Controls.GridViewColumn> Objekt für ein Datenfeld durch Angabe einer <xref:System.Windows.Data.Binding> für die <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> Eigenschaft.  
  
 [!code-csharp[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml.cs#gridviewcolumnproperties)]
 [!code-vb[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCode/visualbasic/window1.xaml.vb#gridviewcolumnproperties)]
 [!code-xaml[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#gridviewcolumnproperties)]  
  
 Sie können auch angeben einer <xref:System.Windows.Data.Binding> als Teil einer <xref:System.Windows.DataTemplate> Definition, mit denen Sie die Zellen in einer Spalte zu formatieren. Im folgenden Beispiel die <xref:System.Windows.DataTemplate> identifiziert, die mit einer <xref:System.Windows.ResourceKey> legt die <xref:System.Windows.Data.Binding> für eine <xref:System.Windows.Controls.GridViewColumn>. Beachten Sie, die in diesem Beispiel nicht definiert die <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> , da dadurch so die Bindung überschreibt, die von angegeben wird <xref:System.Windows.DataTemplate>.  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
<a name="StylingaListView"></a>   
## <a name="styling-a-listview-that-implements-a-gridview"></a>Formatieren eines ListView-Steuerelements, das eine GridView implementiert  
 Die <xref:System.Windows.Controls.ListView> Steuerelement enthält <xref:System.Windows.Controls.ListViewItem> Objekte, die die Datenelemente darstellen, die angezeigt werden. Mit den folgenden Eigenschaften können Sie den Inhalt und das Format von Datenelementen definieren:  
  
-   Auf der <xref:System.Windows.Controls.ListView> steuern, verwenden Sie die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>, und <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> Eigenschaften.  
  
-   Auf der <xref:System.Windows.Controls.ListViewItem> steuern, verwenden Sie die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> und <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> Eigenschaften.  
  
 Zur Vermeidung von Ausrichtungsprobleme zwischen den Zellen in einer <xref:System.Windows.Controls.GridView>, verwenden Sie nicht die <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> Festlegen von Eigenschaften oder Hinzufügen von Inhalt, der die Breite eines Elements in wirkt sich auf eine <xref:System.Windows.Controls.ListView>. Ein Ausrichtungsproblem kann beispielsweise auftreten, wenn Sie festlegen, die <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft in der <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>. Geben Sie Eigenschaften oder definieren Inhalt, der die Breite der Elemente in wirkt sich auf eine <xref:System.Windows.Controls.GridView>, mit den Eigenschaften des der <xref:System.Windows.Controls.GridView> Klasse und seinen verwandten Klassen können z. B. <xref:System.Windows.Controls.GridViewColumn>.  
  
 Weitere Informationen zur Verwendung von <xref:System.Windows.Controls.GridView> und unterstützenden Klassen, finden Sie unter [GridView Overview](../../../../docs/framework/wpf/controls/gridview-overview.md).  
  
 Wenn Sie definieren eine <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> für eine <xref:System.Windows.Controls.ListView> steuern und definieren Sie auch eine <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, müssen Sie auch eine <xref:System.Windows.Controls.ContentPresenter> im Stil Reihenfolge für die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> ordnungsgemäß funktioniert.  
  
 Verwenden Sie nicht die <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> und <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> Eigenschaften für <xref:System.Windows.Controls.ListView> mit angezeigten Inhalt eine <xref:System.Windows.Controls.GridView>. An die Ausrichtung von Inhalt in einer Spalte mit einem <xref:System.Windows.Controls.GridView>, definieren eine <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>.  
  
<a name="UsingtheSameViewMoreThanOnce"></a>   
## <a name="sharing-the-same-view-mode"></a>Gemeinsame Nutzung des gleichen Anzeigemodus  
 Zwei <xref:System.Windows.Controls.ListView> Steuerelemente können nicht den gleichen Ansichtsmodus gleichzeitig gemeinsam verwenden. Wenn Sie versuchen, verwenden Sie die gleichen Ansichtsmodus mit mehr als einem <xref:System.Windows.Controls.ListView> zu steuern, eine Ausnahme auftritt.  
  
 Um einen Ansichtsmodus anzugeben, die gleichzeitig von mehreren verwendet werden können <xref:System.Windows.Controls.ListView>, verwenden Sie Vorlagen oder Stile. Ein Beispiel zum Definieren von Ansichten als <xref:System.Windows.FrameworkElement.Resources%2A>, finden Sie unter [ListView mit mehreren Ansichten Beispiel](http://go.microsoft.com/fwlink/?LinkID=160013).  
  
<a name="CreatingaCustomView"></a>   
## <a name="creating-a-custom-view-mode"></a>Erstellen eines benutzerdefinierten Ansichtsmodus  
 Benutzerdefinierte Ansichten wie <xref:System.Windows.Controls.GridView> abgeleitet sind die <xref:System.Windows.Controls.ViewBase> abstrakte Klasse, die gehören Tools, um die Datenelemente anzuzeigen, die als Werte dargestellt werden <xref:System.Windows.Controls.ListViewItem> Objekte.  
  
 Ein Beispiel für einen benutzerdefinierten Ansichtsmodus finden Sie unter [Beispiel für eine ListView mit mehreren Ansichten](http://go.microsoft.com/fwlink/?LinkID=160013).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.GridView>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.ListViewItem>  
 <xref:System.Windows.Data.Binding>  
 [Übersicht über GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Steuerelemente](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
