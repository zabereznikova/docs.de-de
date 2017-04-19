---
title: "&#220;bersicht &#252;ber ListView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Steuerelemente, ListView"
  - "ListView-Steuerelemente [WPF], Informationen über das ListView-Steuerelement"
ms.assetid: 989e12b0-260e-4570-95c6-489284003ce2
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# &#220;bersicht &#252;ber ListView
Das <xref:System.Windows.Controls.ListView>\-Steuerelement stellt die Infrastruktur zum Anzeigen eines Satzes von Datenelementen in verschiedenen Layouts oder Ansichten bereit.  Dies ist beispielsweise hilfreich, um Datenelemente in einer Tabelle anzuzeigen und Spalten zu sortieren.  
  
   
  
<a name="WhatisaListView"></a>   
## Was ist eine ListView?  
 Das <xref:System.Windows.Controls.ListView>\-Steuerelement ist ein <xref:System.Windows.Controls.ItemsControl>, das von <xref:System.Windows.Controls.ListBox> abgeleitet wird.  Normalerweise sind seine Elemente Teile einer Datensammlung und werden als <xref:System.Windows.Controls.ListViewItem>\-Objekte dargestellt.  Ein <xref:System.Windows.Controls.ListViewItem> ist ein <xref:System.Windows.Controls.ContentControl> und kann nur ein einzelnes untergeordnetes Element enthalten.  Das untergeordnete Element kann jedoch ein beliebiges visuelles Element sein.  
  
<a name="DefiningaListViewView"></a>   
## Definieren eines Anzeigemodus für eine ListView  
 Um einen Anzeigemodus für den Inhalt eines <xref:System.Windows.Controls.ListView>\-Steuerelements anzugeben, legen Sie die <xref:System.Windows.Controls.ListView.View%2A>\-Eigenschaft fest.  Ein von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bereitgestellter Ansichtsmodus ist <xref:System.Windows.Controls.GridView>, in dem eine Sammlung von Datenelementen in einer Tabelle mit anpassbaren Spalten angezeigt wird.  
  
 Das folgende Beispiel zeigt, wie eine <xref:System.Windows.Controls.GridView> für ein <xref:System.Windows.Controls.ListView>\-Steuerelement definiert wird, das Mitarbeiterinformationen anzeigt.  
  
 [!code-xml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 In der folgenden Abbildung ist dargestellt, wie die Daten des vorherigen Beispiels angezeigt werden.  
  
 ![ListView mit GridView&#45;Ausgabe](../../../../docs/framework/wpf/controls/media/listviewgridview.png "ListViewGridView")  
  
 Sie können einen benutzerdefinierten Ansichtsmodus erstellen, indem Sie eine Klasse definieren, die von der <xref:System.Windows.Controls.ViewBase>\-Klasse erbt.  Die <xref:System.Windows.Controls.ViewBase>\-Klasse stellt die Infrastruktur bereit, die Sie benötigen, um eine benutzerdefinierte Ansicht zu erstellen.  Weitere Informationen zum Erstellen einer benutzerdefinierten Ansicht finden Sie unter [Erstellen eines benutzerdefinierten Ansichtsmodus für eine ListView](../../../../docs/framework/wpf/controls/how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="BindingDatatoaListView"></a>   
## Binden von Daten an eine ListView  
 Verwenden Sie die <xref:System.Windows.Controls.ItemsControl.Items%2A>\-Eigenschaft und die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>\-Eigenschaft, um Elemente für ein <xref:System.Windows.Controls.ListView>\-Steuerelement anzugeben.  Im folgenden Beispiel wird die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>\-Eigenschaft auf die Datensammlung `EmployeeInfoDataSource` festgelegt.  
  
 [!code-xml[ListViewCode#ItemsSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#itemssource)]  
  
 In einer <xref:System.Windows.Controls.GridView> werden <xref:System.Windows.Controls.GridViewColumn>\-Objekte an angegebene Datenfelder gebunden.  Im folgenden Beispiel wird ein <xref:System.Windows.Controls.GridViewColumn>\-Objekt an ein Datenfeld gebunden, indem eine <xref:System.Windows.Data.Binding> für die <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>\-Eigenschaft angegeben wird.  
  
 [!code-csharp[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml.cs#gridviewcolumnproperties)]
 [!code-vb[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCode/visualbasic/window1.xaml.vb#gridviewcolumnproperties)]
 [!code-xml[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#gridviewcolumnproperties)]  
  
 Sie können auch eine <xref:System.Windows.Data.Binding> als Teil einer <xref:System.Windows.DataTemplate>\-Definition angeben, die Sie verwenden, um die Zellen in einer Spalte zu formatieren.  Im folgenden Beispiel setzt die <xref:System.Windows.DataTemplate>, die mit einem <xref:System.Windows.ResourceKey> identifiziert wird, die <xref:System.Windows.Data.Binding> für eine <xref:System.Windows.Controls.GridViewColumn>.  Beachten Sie, dass dieses Beispiel keine <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> definiert, da ein solches Vorgehen die mit <xref:System.Windows.DataTemplate> angegebene Bindung überschreibt.  
  
 [!code-xml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 [!code-xml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
<a name="StylingaListView"></a>   
## Formatieren einer ListView, die eine GridView implementiert  
 Das <xref:System.Windows.Controls.ListView>\-Steuerelement enthält <xref:System.Windows.Controls.ListViewItem>\-Objekte, die die angezeigten Datenelemente darstellen.  Mit den folgenden Eigenschaften können Sie den Inhalt und das Format von Datenelementen definieren:  
  
-   Verwenden Sie für das <xref:System.Windows.Controls.ListView>\-Steuerelement die Eigenschaften <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> und <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>.  
  
-   Verwenden Sie für das <xref:System.Windows.Controls.ListViewItem>\-Steuerelement die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>\-Eigenschaft und die <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>\-Eigenschaft.  
  
 Um in einer <xref:System.Windows.Controls.GridView> Ausrichtungsprobleme zwischen Zellen zu verhindern, sollten Sie keinen <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> verwenden, um Eigenschaften festzulegen oder Inhalte hinzuzufügen, die die Breite eines Elements in einer <xref:System.Windows.Controls.ListView> beeinflussen.  Beispielsweise kann ein Ausrichtungsproblem auftreten, wenn Sie die <xref:System.Windows.FrameworkElement.Margin%2A>\-Eigenschaft im <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> festlegen.  Um Eigenschaften anzugeben oder Inhalte zu definieren, die die Breite von Elementen in einer <xref:System.Windows.Controls.GridView> beeinflussen, verwenden Sie die Eigenschaften der <xref:System.Windows.Controls.GridView>\-Klasse und verwandter Klassen wie <xref:System.Windows.Controls.GridViewColumn>.  
  
 Weitere Informationen zur Verwendung von <xref:System.Windows.Controls.GridView> und den unterstützenden Klassen finden Sie unter [Übersicht über GridView](../../../../docs/framework/wpf/controls/gridview-overview.md).  
  
 Wenn Sie einen <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> für ein <xref:System.Windows.Controls.ListView>\-Steuerelement definieren und außerdem eine <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> definieren, müssen Sie im Stil einen <xref:System.Windows.Controls.ContentPresenter> angeben, damit die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> ordnungsgemäß funktioniert.  
  
 Verwenden Sie nicht die <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>\-Eigenschaft und die <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A>\-Eigenschaft für <xref:System.Windows.Controls.ListView>\-Inhalte, die mit einer <xref:System.Windows.Controls.GridView> angezeigt werden.  Um die Ausrichtung der Spalteninhalte einer <xref:System.Windows.Controls.GridView> anzugeben, definieren Sie eine <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>.  
  
<a name="UsingtheSameViewMoreThanOnce"></a>   
## Gemeinsames Verwenden des gleichen Anzeigemodus  
 Der gleiche Anzeigemodus kann von zwei <xref:System.Windows.Controls.ListView>\-Steuerelementen nicht gleichzeitig gemeinsam verwendet werden.  Wenn Sie den gleichen Anzeigemodus mit mehreren <xref:System.Windows.Controls.ListView>\-Steuerelementen verwenden, wird eine Ausnahme ausgelöst.  
  
 Verwenden Sie Vorlagen oder Stile, um einen Anzeigemodus anzugeben, der gleichzeitig von mehr als einer <xref:System.Windows.Controls.ListView> verwendet werden kann.  Ein Beispiel zum Definieren von Ansichten als <xref:System.Windows.FrameworkElement.Resources%2A> finden Sie unter [Beispiel für eine ListView mit mehreren Ansichten](http://go.microsoft.com/fwlink/?LinkID=160013).  
  
<a name="CreatingaCustomView"></a>   
## Erstellen eines benutzerdefinierten Ansichtsmodus  
 Benutzerdefinierte Ansichten wie <xref:System.Windows.Controls.GridView> werden von der abstrakten <xref:System.Windows.Controls.ViewBase>\-Klasse abgeleitet, die die Werkzeuge zum Anzeigen von Datenelementen bereitstellt, die als <xref:System.Windows.Controls.ListViewItem>\-Objekte dargestellt werden.  
  
 Ein Beispiel für einen benutzerdefinierten Ansichtsmodus finden Sie unter [Beispiel für eine ListView mit mehreren Ansichten](http://go.microsoft.com/fwlink/?LinkID=160013).  
  
## Siehe auch  
 <xref:System.Windows.Controls.GridView>   
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.ListViewItem>   
 <xref:System.Windows.Data.Binding>   
 [Übersicht über GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [Steuerelemente](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)