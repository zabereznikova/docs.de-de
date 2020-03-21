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
ms.openlocfilehash: 2f336d1eb8dcdfec3c3c8059ba865147c6b6c825
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187518"
---
# <a name="listview-overview"></a>Übersicht über ListView
Das <xref:System.Windows.Controls.ListView> Steuerelement stellt die Infrastruktur zum Anzeigen einer Gruppe von Datenelementen in verschiedenen Layouts oder Ansichten bereit. Benutzer können damit z.B. die Datenelemente in einer Tabelle anzeigen und die Spalten sortieren.  

<a name="WhatisaListView"></a>
## <a name="what-is-a-listview"></a>Was ist ein ListView-Steuerelement?  
 Das <xref:System.Windows.Controls.ListView> Steuerelement <xref:System.Windows.Controls.ItemsControl> ist ein, <xref:System.Windows.Controls.ListBox>das von abgeleitet wird. In der Regel sind seine Elemente Mitglieder <xref:System.Windows.Controls.ListViewItem> einer Datensammlung und werden als Objekte dargestellt. A <xref:System.Windows.Controls.ListViewItem> ist <xref:System.Windows.Controls.ContentControl> ein und kann nur ein einzelnes untergeordnetes Element enthalten. Dieses untergeordnete Element kann jedoch ein beliebiges visuelles Element sein.  
  
<a name="DefiningaListViewView"></a>
## <a name="defining-a-view-mode-for-a-listview"></a>Definieren eines Anzeigemodus für ein ListView-Steuerelement  
 Um einen Ansichtsmodus für <xref:System.Windows.Controls.ListView> den Inhalt eines <xref:System.Windows.Controls.ListView.View%2A> Steuerelements anzugeben, legen Sie die Eigenschaft fest. Ein Ansichtsmodus, der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bereitstellt, ist <xref:System.Windows.Controls.GridView>, der eine Sammlung von Datenelementen in einer Tabelle mit anpassbaren Spalten anzeigt.  
  
 Das folgende Beispiel zeigt, <xref:System.Windows.Controls.GridView> wie <xref:System.Windows.Controls.ListView> sie eine für ein Steuerelement definieren, das Mitarbeiterinformationen anzeigt.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 Die folgende Abbildung zeigt, wie die Daten aus dem vorherigen Beispiel angezeigt werden.  
  
 ![Screenshot, der eine ListView mit GridView-Ausgabe zeigt.](./media/gridview-overview/listview-gridview-output.jpg)  
  
 Sie können einen benutzerdefinierten Ansichtsmodus erstellen, indem <xref:System.Windows.Controls.ViewBase> Sie eine Klasse definieren, die von der Klasse erbt. Die <xref:System.Windows.Controls.ViewBase> Klasse stellt die Infrastruktur bereit, die Sie zum Erstellen einer benutzerdefinierten Ansicht benötigen. Weitere Informationen dazu, wie Sie eine benutzerdefinierte Ansicht erstellen, finden Sie unter [Erstellen eines benutzerdefinierten Ansichtsmodus für eine ListView](how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="BindingDatatoaListView"></a>
## <a name="binding-data-to-a-listview"></a>Binden von Daten an ein ListView-Steuerelement  
 Verwenden <xref:System.Windows.Controls.ItemsControl.Items%2A> Sie <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> die und Eigenschaften, um Elemente für ein <xref:System.Windows.Controls.ListView> Steuerelement anzugeben. Im folgenden Beispiel <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> wird die Eigenschaft auf `EmployeeInfoDataSource`eine Datensammlung festgelegt, die als aufgerufen wird.  
  
 [!code-xaml[ListViewCode#ItemsSource](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#itemssource)]  
  
 In <xref:System.Windows.Controls.GridView>einem <xref:System.Windows.Controls.GridViewColumn> binden Objekte an angegebene Datenfelder. Im folgenden Beispiel <xref:System.Windows.Controls.GridViewColumn> wird ein Objekt an ein <xref:System.Windows.Data.Binding> Datenfeld gebunden, indem ein für die <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> Eigenschaft angegeben wird.  
  
 [!code-csharp[ListViewCode#GridViewColumnProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml.cs#gridviewcolumnproperties)]
 [!code-vb[ListViewCode#GridViewColumnProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCode/visualbasic/window1.xaml.vb#gridviewcolumnproperties)]
 [!code-xaml[ListViewCode#GridViewColumnProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#gridviewcolumnproperties)]  
  
 Sie können auch <xref:System.Windows.Data.Binding> eine als <xref:System.Windows.DataTemplate> Teil einer Definition angeben, die Sie zum Formatieren der Zellen in einer Spalte verwenden. Im folgenden Beispiel <xref:System.Windows.DataTemplate> legt das, <xref:System.Windows.ResourceKey> das <xref:System.Windows.Data.Binding> mit <xref:System.Windows.Controls.GridViewColumn>einem identifiziert wird, die für eine fest. Beachten Sie, dass in <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> diesem Beispiel die nicht definiert <xref:System.Windows.DataTemplate>wird, da dadurch die von angegebene Bindung überschrieben wird.  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
<a name="StylingaListView"></a>
## <a name="styling-a-listview-that-implements-a-gridview"></a>Formatieren eines ListView-Steuerelements, das eine GridView implementiert  
 Das <xref:System.Windows.Controls.ListView> Steuerelement <xref:System.Windows.Controls.ListViewItem> enthält Objekte, die die angezeigten Datenelemente darstellen. Mit den folgenden Eigenschaften können Sie den Inhalt und das Format von Datenelementen definieren:  
  
- Verwenden <xref:System.Windows.Controls.ListView> Sie für <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>das <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>Steuerelement <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> die , und die Eigenschaften.  
  
- Verwenden <xref:System.Windows.Controls.ListViewItem> Sie für <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> das <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> Steuerelement die und-Eigenschaften.  
  
 Um Ausrichtungsprobleme zwischen <xref:System.Windows.Controls.GridView>Zellen in einem <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> zu vermeiden, verwenden Sie die nicht, <xref:System.Windows.Controls.ListView>um Eigenschaften festzulegen oder Inhalt hinzuzufügen, der sich auf die Breite eines Elements in einem auswirkt. Beispielsweise kann ein Ausrichtungsproblem auftreten, <xref:System.Windows.FrameworkElement.Margin%2A> wenn <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>Sie die Eigenschaft im festlegen. Um Eigenschaften anzugeben oder Inhalt zu definieren, <xref:System.Windows.Controls.GridView>der sich auf <xref:System.Windows.Controls.GridView> die Breite von Elementen <xref:System.Windows.Controls.GridViewColumn>in einem auswirkt, verwenden Sie die Eigenschaften der Klasse und der zugehörigen Klassen, z. B. .  
  
 Weitere Informationen zur Verwendung <xref:System.Windows.Controls.GridView> und der unterstützenden Klassen finden Sie unter [GridView Overview](gridview-overview.md).  
  
 Wenn Sie <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> eine <xref:System.Windows.Controls.ListView> für ein Steuerelement <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>und auch <xref:System.Windows.Controls.ContentPresenter> eine definieren, müssen <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Sie eine in den Stil einschließen, damit die ordnungsgemäß funktioniert.  
  
 Verwenden Sie <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> die <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> und <xref:System.Windows.Controls.ListView> Eigenschaften nicht für <xref:System.Windows.Controls.GridView>Inhalte, die mithilfe einer angezeigt werden. Um die Ausrichtung des Inhalts in <xref:System.Windows.Controls.GridView>einer <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>Spalte eines anzugeben, definieren Sie eine .  
  
<a name="UsingtheSameViewMoreThanOnce"></a>
## <a name="sharing-the-same-view-mode"></a>Gemeinsame Nutzung des gleichen Anzeigemodus  
 Zwei <xref:System.Windows.Controls.ListView> Steuerelemente können nicht gleichzeitig denselben Ansichtsmodus verwenden. Wenn Sie versuchen, denselben Ansichtsmodus <xref:System.Windows.Controls.ListView> mit mehr als einem Steuerelement zu verwenden, tritt eine Ausnahme auf.  
  
 Um einen Ansichtsmodus anzugeben, der gleichzeitig <xref:System.Windows.Controls.ListView>von mehreren verwendet werden kann, verwenden Sie Vorlagen oder Stile.
  
<a name="CreatingaCustomView"></a>
## <a name="creating-a-custom-view-mode"></a>Erstellen eines benutzerdefinierten Ansichtsmodus  
 Benutzerdefinierte <xref:System.Windows.Controls.GridView> Ansichten wie <xref:System.Windows.Controls.ViewBase> werden von der abstrakten Klasse abgeleitet, die <xref:System.Windows.Controls.ListViewItem> die Werkzeuge zum Anzeigen von Datenelementen bereitstellt, die als Objekte dargestellt werden.
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Controls.GridView>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.ListViewItem>
- <xref:System.Windows.Data.Binding>
- [Übersicht über GridView](gridview-overview.md)
- [How-to-Themen](listview-how-to-topics.md)
- [Kontrollen](../advanced/optimizing-performance-controls.md)
