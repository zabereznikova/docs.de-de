---
title: Übersicht über ListView
description: Erfahren Sie mehr über das Windows Presentation Foundation ListView-Steuerelement, das die Infrastruktur zum Anzeigen von Datenelementen in verschiedenen Layouts oder Ansichten bereitstellt.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ListView
- ListView controls [WPF], about ListView control
ms.assetid: 989e12b0-260e-4570-95c6-489284003ce2
ms.openlocfilehash: 419c6216f0af696ec71e7607c79c2db637caa785
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164559"
---
# <a name="listview-overview"></a>Übersicht über ListView
Das- <xref:System.Windows.Controls.ListView> Steuerelement stellt die Infrastruktur bereit, um einen Satz von Datenelementen in verschiedenen Layouts oder Sichten anzuzeigen. Benutzer können damit z.B. die Datenelemente in einer Tabelle anzeigen und die Spalten sortieren.  

<a name="WhatisaListView"></a>
## <a name="what-is-a-listview"></a>Was ist ein ListView-Steuerelement?  
 Das- <xref:System.Windows.Controls.ListView> Steuerelement ist ein <xref:System.Windows.Controls.ItemsControl> , das von abgeleitet wird <xref:System.Windows.Controls.ListBox> . In der Regel sind die Elemente Mitglieder einer Datensammlung und werden als- <xref:System.Windows.Controls.ListViewItem> Objekte dargestellt. Ein <xref:System.Windows.Controls.ListViewItem> ist ein <xref:System.Windows.Controls.ContentControl> und kann nur ein einzelnes untergeordnetes Element enthalten. Dieses untergeordnete Element kann jedoch ein beliebiges visuelles Element sein.  
  
<a name="DefiningaListViewView"></a>
## <a name="defining-a-view-mode-for-a-listview"></a>Definieren eines Anzeigemodus für ein ListView-Steuerelement  
 Wenn Sie einen Ansichtsmodus für den Inhalt eines Steuer Elements angeben möchten <xref:System.Windows.Controls.ListView> , legen Sie die- <xref:System.Windows.Controls.ListView.View%2A> Eigenschaft fest. Ein Ansichtsmodus, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] der bereitstellt <xref:System.Windows.Controls.GridView> , ist, wodurch eine Auflistung von Datenelementen in einer Tabelle angezeigt wird, die über anpassbare Spalten verfügt.  
  
 Im folgenden Beispiel wird gezeigt, wie ein- <xref:System.Windows.Controls.GridView> Steuerelement für ein Steuerelement definiert wird <xref:System.Windows.Controls.ListView> , das Mitarbeiter Informationen anzeigt.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 Die folgende Abbildung zeigt, wie die Daten aus dem vorherigen Beispiel angezeigt werden.  
  
 ![Screenshot, der eine ListView mit GridView-Ausgabe zeigt.](./media/gridview-overview/listview-gridview-output.jpg)  
  
 Sie können einen benutzerdefinierten Ansichtsmodus erstellen, indem Sie eine Klasse definieren, die von der-Klasse erbt <xref:System.Windows.Controls.ViewBase> . Die- <xref:System.Windows.Controls.ViewBase> Klasse stellt die Infrastruktur bereit, die Sie zum Erstellen einer benutzerdefinierten Ansicht benötigen. Weitere Informationen dazu, wie Sie eine benutzerdefinierte Ansicht erstellen, finden Sie unter [Erstellen eines benutzerdefinierten Ansichtsmodus für eine ListView](how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="BindingDatatoaListView"></a>
## <a name="binding-data-to-a-listview"></a>Binden von Daten an ein ListView-Steuerelement  
 Verwenden <xref:System.Windows.Controls.ItemsControl.Items%2A> Sie die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaften und, um Elemente für ein Steuerelement anzugeben <xref:System.Windows.Controls.ListView> . Im folgenden Beispiel wird die- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft auf eine Datensammlung mit dem Namen festgelegt `EmployeeInfoDataSource` .  
  
 [!code-xaml[ListViewCode#ItemsSource](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#itemssource)]  
  
 In einem <xref:System.Windows.Controls.GridView> werden- <xref:System.Windows.Controls.GridViewColumn> Objekte an angegebene Datenfelder gebunden. Im folgenden Beispiel wird ein- <xref:System.Windows.Controls.GridViewColumn> Objekt an ein Datenfeld gebunden, indem <xref:System.Windows.Data.Binding> für die-Eigenschaft angegeben wird <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> .  
  
 [!code-csharp[ListViewCode#GridViewColumnProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml.cs#gridviewcolumnproperties)]
 [!code-vb[ListViewCode#GridViewColumnProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCode/visualbasic/window1.xaml.vb#gridviewcolumnproperties)]
 [!code-xaml[ListViewCode#GridViewColumnProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#gridviewcolumnproperties)]  
  
 Sie können auch <xref:System.Windows.Data.Binding> als Teil einer <xref:System.Windows.DataTemplate> Definition angeben, mit der Sie die Zellen in einer Spalte formatieren. Im folgenden Beispiel wird die, die <xref:System.Windows.DataTemplate> mit einem identifiziert wird, für ein-Wert fest <xref:System.Windows.ResourceKey> gelegt <xref:System.Windows.Data.Binding> <xref:System.Windows.Controls.GridViewColumn> . Beachten Sie, dass in diesem Beispiel nicht definiert ist, <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> da dies die durch angegebene Bindung überschreibt <xref:System.Windows.DataTemplate> .  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
<a name="StylingaListView"></a>
## <a name="styling-a-listview-that-implements-a-gridview"></a>Formatieren eines ListView-Steuerelements, das eine GridView implementiert  
 Das- <xref:System.Windows.Controls.ListView> Steuerelement enthält- <xref:System.Windows.Controls.ListViewItem> Objekte, die die angezeigten Datenelemente darstellen. Mit den folgenden Eigenschaften können Sie den Inhalt und das Format von Datenelementen definieren:  
  
- Verwenden Sie auf dem <xref:System.Windows.Controls.ListView> -Steuerelement die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> Eigenschaften, und <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> .  
  
- Verwenden Sie auf dem <xref:System.Windows.Controls.ListViewItem> -Steuerelement die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> Eigenschaften und.  
  
 Um Ausrichtungs Probleme zwischen Zellen in einem zu vermeiden <xref:System.Windows.Controls.GridView> , verwenden Sie nicht, <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> um Eigenschaften festzulegen oder Inhalt hinzuzufügen, der sich auf die Breite eines Elements in einem auswirkt <xref:System.Windows.Controls.ListView> . Beispielsweise kann ein Ausrichtungs Problem auftreten, wenn Sie die- <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft in der festlegen <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> . Zum Angeben von Eigenschaften oder zum Definieren von Inhalten, die sich auf die Breite von Elementen in einem auswirken <xref:System.Windows.Controls.GridView> , verwenden Sie die Eigenschaften der <xref:System.Windows.Controls.GridView> -Klasse und der zugehörigen Klassen, z <xref:System.Windows.Controls.GridViewColumn> . b..  
  
 Weitere Informationen zur Verwendung von <xref:System.Windows.Controls.GridView> und der unterstützenden Klassen finden Sie unter [Übersicht über GridView](gridview-overview.md).  
  
 Wenn Sie ein <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> -Steuerelement für ein Steuerelement definieren <xref:System.Windows.Controls.ListView> und auch einen definieren <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> , müssen Sie ein-Element <xref:System.Windows.Controls.ContentPresenter> in den-Stil einschließen, damit das <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> ordnungsgemäß funktioniert.  
  
 Verwenden Sie die-Eigenschaft und die-Eigenschaft nicht <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> für <xref:System.Windows.Controls.ListView> Inhalte, die mit einem angezeigt werden <xref:System.Windows.Controls.GridView> . Um die Ausrichtung des Inhalts in einer Spalte einer anzugeben <xref:System.Windows.Controls.GridView> , definieren Sie eine <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> .  
  
<a name="UsingtheSameViewMoreThanOnce"></a>
## <a name="sharing-the-same-view-mode"></a>Gemeinsame Nutzung des gleichen Anzeigemodus  
 Zwei-Steuer <xref:System.Windows.Controls.ListView> Elemente können nicht denselben Ansichtsmodus gleichzeitig verwenden. Wenn Sie versuchen, denselben Ansichtsmodus mit mehr als einem Steuerelement zu verwenden <xref:System.Windows.Controls.ListView> , tritt eine Ausnahme auf.  
  
 Um einen Ansichtsmodus anzugeben, der gleichzeitig von mehr als einem verwendet werden kann <xref:System.Windows.Controls.ListView> , verwenden Sie Vorlagen oder Stile.
  
<a name="CreatingaCustomView"></a>
## <a name="creating-a-custom-view-mode"></a>Erstellen eines benutzerdefinierten Ansichtsmodus  
 Angepasste Sichten wie <xref:System.Windows.Controls.GridView> werden von der <xref:System.Windows.Controls.ViewBase> abstrakten-Klasse abgeleitet, die Tools zum Anzeigen von Datenelementen bereitstellt, die als-Objekte dargestellt werden <xref:System.Windows.Controls.ListViewItem> .
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Controls.GridView>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.ListViewItem>
- <xref:System.Windows.Data.Binding>
- [Übersicht über GridView](gridview-overview.md)
- [Artikel zu Vorgehensweisen](listview-how-to-topics.md)
- [Steuerelemente](../advanced/optimizing-performance-controls.md)
