---
title: 'Vorgehensweise: Gewusst wie: Ändern der horizontalen Ausrichtung einer Spalte in einem ListView-Element'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
ms.openlocfilehash: 07d5fd0830f98032e76b963cb32b35fd18b50475
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54605224"
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a>Vorgehensweise: Gewusst wie: Ändern der horizontalen Ausrichtung einer Spalte in einem ListView-Element
Standardmäßig wird der Inhalt jeder Spalte in einer <xref:System.Windows.Controls.ListViewItem> wird linksbündig ausgerichtet. Sie können die Ausrichtung der einzelnen Spalten ändern, durch die Bereitstellung einer <xref:System.Windows.DataTemplate> und Einstellung der <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> -Eigenschaft des Elements innerhalb der <xref:System.Windows.DataTemplate>. Dieses Thema wird gezeigt, wie eine <xref:System.Windows.Controls.ListView> richtet dessen Inhalt standardmäßig "und" Gewusst wie: Ändern Sie die Ausrichtung einer Spalte in eine <xref:System.Windows.Controls.ListView>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel die Daten in die `Title` und `ISBN` Spalten wird linksbündig ausgerichtet.  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 So ändern Sie die Ausrichtung des den `ISBN` Spalte müssen Sie angeben, dass die <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> Eigenschaft der einzelnen <xref:System.Windows.Controls.ListViewItem> ist <xref:System.Windows.HorizontalAlignment.Stretch>, sodass Elemente in jedem <xref:System.Windows.Controls.ListViewItem> können umfassen oder auf die gesamte Breite der einzelnen Spalten positioniert werden. Da die <xref:System.Windows.Controls.ListView> gebunden ist mit einer Datenquelle, müssen Sie einen Stil zu erstellen, der festlegt der <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>. Als Nächstes müssen Sie verwenden eine <xref:System.Windows.DataTemplate> zum Anzeigen des Inhalts statt der <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> Eigenschaft. Zum Anzeigen der `ISBN` jeder Vorlage, die <xref:System.Windows.DataTemplate> darf nur eine <xref:System.Windows.Controls.TextBlock> , bei dem die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> -Eigenschaft auf festgelegt <xref:System.Windows.HorizontalAlignment.Right>.  
  
 Das folgende Beispiel definiert das Format und <xref:System.Windows.DataTemplate> erforderlich, stellen die `ISBN` Spalte rechtsbündig ausgerichtet und Änderungen der <xref:System.Windows.Controls.GridViewColumn> zu verweisen die <xref:System.Windows.DataTemplate>.  
  
 [!code-xaml[ListViewHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md)
- [Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)
