---
title: 'Gewusst wie: Ändern der horizontalen Ausrichtung einer Spalte in einem ListView-Element'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
ms.openlocfilehash: 5447f1a73b008b2ed4f345eba00f4d631e11e257
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458603"
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a>Gewusst wie: Ändern der horizontalen Ausrichtung einer Spalte in einem ListView-Element
Standardmäßig wird der Inhalt der einzelnen Spalten in einem <xref:System.Windows.Controls.ListViewItem> linksbündig ausgerichtet. Sie können die Ausrichtung der einzelnen Spalten ändern, indem Sie eine <xref:System.Windows.DataTemplate> bereitstellen und die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>-Eigenschaft für das Element innerhalb der <xref:System.Windows.DataTemplate>festlegen. In diesem Thema wird gezeigt, wie ein <xref:System.Windows.Controls.ListView> seinen Inhalt standardmäßig anpasst und wie die Ausrichtung einer Spalte in einer <xref:System.Windows.Controls.ListView>geändert wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Daten in den Spalten `Title` und `ISBN` linksbündig ausgerichtet.  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Um die Ausrichtung der `ISBN` Spalte zu ändern, müssen Sie angeben, dass die <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>-Eigenschaft der einzelnen <xref:System.Windows.Controls.ListViewItem> <xref:System.Windows.HorizontalAlignment.Stretch>ist, damit die Elemente in den einzelnen <xref:System.Windows.Controls.ListViewItem> entlang der gesamten Breite jeder Spalte angeordnet werden können. Da der <xref:System.Windows.Controls.ListView> an eine Datenquelle gebunden ist, müssen Sie einen Stil erstellen, der die <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>festlegt. Als nächstes müssen Sie einen <xref:System.Windows.DataTemplate> verwenden, um den Inhalt anzuzeigen, anstatt die <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>-Eigenschaft zu verwenden. Um die `ISBN` der einzelnen Vorlagen anzuzeigen, kann die <xref:System.Windows.DataTemplate> nur einen <xref:System.Windows.Controls.TextBlock> enthalten, dessen <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>-Eigenschaft auf <xref:System.Windows.HorizontalAlignment.Right>festgelegt ist.  
  
 Im folgenden Beispiel werden der Stil und <xref:System.Windows.DataTemplate> definiert, die notwendig sind, um die `ISBN` Spalte rechtsbündig zu machen, und die <xref:System.Windows.Controls.GridViewColumn> so ändern, dass Sie auf die <xref:System.Windows.DataTemplate>verweist  
  
 [!code-xaml[ListViewHowTos#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Übersicht über Datenvorlagen](../data/data-templating-overview.md)
- [Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Übersicht über ListView](listview-overview.md)
