---
title: 'Vorgehensweise: Gewusst wie: Ändern der horizontalen Ausrichtung einer Spalte in einem ListView-Element'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
ms.openlocfilehash: 616eae9d72517124b6757260e68e8745d12632ff
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355141"
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a>Vorgehensweise: Gewusst wie: Ändern der horizontalen Ausrichtung einer Spalte in einem ListView-Element
Standardmäßig wird der Inhalt jeder Spalte in einer <xref:System.Windows.Controls.ListViewItem> wird linksbündig ausgerichtet. Sie können die Ausrichtung der einzelnen Spalten ändern, durch die Bereitstellung einer <xref:System.Windows.DataTemplate> und Einstellung der <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> -Eigenschaft des Elements innerhalb der <xref:System.Windows.DataTemplate>. Dieses Thema wird gezeigt, wie eine <xref:System.Windows.Controls.ListView> richtet dessen Inhalt standardmäßig "und" Gewusst wie: Ändern Sie die Ausrichtung einer Spalte in eine <xref:System.Windows.Controls.ListView>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel die Daten in die `Title` und `ISBN` Spalten wird linksbündig ausgerichtet.  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 So ändern Sie die Ausrichtung des den `ISBN` Spalte müssen Sie angeben, dass die <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> Eigenschaft der einzelnen <xref:System.Windows.Controls.ListViewItem> ist <xref:System.Windows.HorizontalAlignment.Stretch>, sodass Elemente in jedem <xref:System.Windows.Controls.ListViewItem> können umfassen oder auf die gesamte Breite der einzelnen Spalten positioniert werden. Da die <xref:System.Windows.Controls.ListView> gebunden ist mit einer Datenquelle, müssen Sie einen Stil zu erstellen, der festlegt der <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>. Als Nächstes müssen Sie verwenden eine <xref:System.Windows.DataTemplate> zum Anzeigen des Inhalts statt der <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> Eigenschaft. Zum Anzeigen der `ISBN` jeder Vorlage, die <xref:System.Windows.DataTemplate> darf nur eine <xref:System.Windows.Controls.TextBlock> , bei dem die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> -Eigenschaft auf festgelegt <xref:System.Windows.HorizontalAlignment.Right>.  
  
 Das folgende Beispiel definiert das Format und <xref:System.Windows.DataTemplate> erforderlich, stellen die `ISBN` Spalte rechtsbündig ausgerichtet und Änderungen der <xref:System.Windows.Controls.GridViewColumn> zu verweisen die <xref:System.Windows.DataTemplate>.  
  
 [!code-xaml[ListViewHowTos#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht zur Datenbindung](../data/data-binding-overview.md)
- [Übersicht über Datenvorlagen](../data/data-templating-overview.md)
- [Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Übersicht über ListView](listview-overview.md)
