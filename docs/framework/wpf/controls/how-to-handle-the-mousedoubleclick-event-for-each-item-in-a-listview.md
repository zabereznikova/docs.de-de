---
title: 'Vorgehensweise: Behandeln des MouseDoubleClick-Ereignisses für die einzelnen ListView-Elemente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 7e51c810a2e1e4bf4157aa1311255c5547021b60
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962067"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>Vorgehensweise: Behandeln des MouseDoubleClick-Ereignisses für die einzelnen ListView-Elemente
Um ein Ereignis für ein Element in einem <xref:System.Windows.Controls.ListView>zu behandeln, müssen Sie jedem <xref:System.Windows.Controls.ListViewItem>einen Ereignishandler hinzufügen. Wenn ein <xref:System.Windows.Controls.ListView> an eine Datenquelle gebunden ist, erstellen Sie nicht explizit eine <xref:System.Windows.Controls.ListViewItem>, aber Sie können das-Ereignis für <xref:System.Windows.EventSetter> jedes Element behandeln, indem Sie ein einem Stil von <xref:System.Windows.Controls.ListViewItem>hinzufügen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Daten gebundenes <xref:System.Windows.Controls.ListView> erstellt und ein <xref:System.Windows.Style> erstellt, um jedem <xref:System.Windows.Controls.ListViewItem>einen Ereignishandler hinzuzufügen.  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Im folgenden Beispiel wird das <xref:System.Windows.Controls.Control.MouseDoubleClick> -Ereignis behandelt.  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> Obwohl es am häufigsten ist, <xref:System.Windows.Controls.ListView> ein an eine Datenquelle zu binden, können Sie einen-Stil verwenden, um jedem <xref:System.Windows.Controls.ListViewItem> in einer nicht Daten gebundenen <xref:System.Windows.Controls.ListView> einen Ereignishandler hinzuzufügen, unabhängig davon, ob Sie <xref:System.Windows.Controls.ListViewItem>explizit ein erstellen.  Weitere Informationen zu explizit und implizit erstellten <xref:System.Windows.Controls.ListViewItem> Steuerelementen finden <xref:System.Windows.Controls.ItemsControl>Sie unter.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XmlElement>
- [Übersicht zur Datenbindung](../data/data-binding-overview.md)
- [Erstellen von Formaten und Vorlagen](styling-and-templating.md)
- [Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Übersicht über ListView](listview-overview.md)
