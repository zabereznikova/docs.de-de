---
title: 'Gewusst wie: Behandeln des MouseDoubleClick-Ereignisses für die einzelnen ListView-Einträge'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 7bbc7bad36b3b1f2c92065e5f5699e5a86ac6189
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646110"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>Gewusst wie: Behandeln des MouseDoubleClick-Ereignisses für die einzelnen ListView-Einträge
Um ein Ereignis für ein <xref:System.Windows.Controls.ListView>Element in einem zu behandeln, müssen Sie jedem <xref:System.Windows.Controls.ListViewItem>einen Ereignishandler hinzufügen. Wenn <xref:System.Windows.Controls.ListView> a an eine Datenquelle gebunden ist, erstellen <xref:System.Windows.Controls.ListViewItem>Sie nicht explizit eine , aber <xref:System.Windows.EventSetter> Sie können das <xref:System.Windows.Controls.ListViewItem>Ereignis für jedes Element behandeln, indem Sie einem Stil einer hinzufügen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird <xref:System.Windows.Controls.ListView> eine datengebundene und erstellte erstellt, <xref:System.Windows.Style> um jedem <xref:System.Windows.Controls.ListViewItem>einen Ereignishandler hinzuzufügen.  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Im folgenden Beispiel <xref:System.Windows.Controls.Control.MouseDoubleClick> wird das Ereignis behandelt.  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> Obwohl es am häufigsten <xref:System.Windows.Controls.ListView> ist, eine an eine Datenquelle zu binden, können <xref:System.Windows.Controls.ListViewItem> Sie einen Stil <xref:System.Windows.Controls.ListView> verwenden, um jedem <xref:System.Windows.Controls.ListViewItem>Ereignishandler in einer nicht datengebundenen Datei einen Ereignishandler hinzuzufügen, unabhängig davon, ob Sie explizit eine erstellen.  Weitere Informationen zu explizit und <xref:System.Windows.Controls.ListViewItem> implizit <xref:System.Windows.Controls.ItemsControl>erstellten Steuerelementen finden Sie unter .  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XmlElement>
- [Datenbindung sübersicht](../../../desktop-wpf/data/data-binding-overview.md)
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Binden an XML-Daten mithilfe eines XMLDataProvider- und XPath-Abfragen](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Übersicht über ListView](listview-overview.md)
