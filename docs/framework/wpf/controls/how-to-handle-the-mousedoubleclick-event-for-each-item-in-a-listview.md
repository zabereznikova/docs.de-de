---
title: 'Gewusst wie: Behandeln des MouseDoubleClick-Ereignisses für die einzelnen ListView-Einträge'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 25308ee87fb387787e20c8a8887ae8e4e60742b9
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460233"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>Gewusst wie: Behandeln des MouseDoubleClick-Ereignisses für die einzelnen ListView-Einträge
Um ein Ereignis für ein Element in einem <xref:System.Windows.Controls.ListView>zu behandeln, müssen Sie jedem <xref:System.Windows.Controls.ListViewItem>einen Ereignishandler hinzufügen. Wenn eine <xref:System.Windows.Controls.ListView> an eine Datenquelle gebunden ist, erstellen Sie nicht explizit eine <xref:System.Windows.Controls.ListViewItem>, aber Sie können das Ereignis für jedes Element behandeln, indem Sie einem Stil einer <xref:System.Windows.Controls.ListViewItem>eine <xref:System.Windows.EventSetter> hinzufügen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Daten gebundenes <xref:System.Windows.Controls.ListView> erstellt und ein <xref:System.Windows.Style> erstellt, um jedem <xref:System.Windows.Controls.ListViewItem>einen Ereignishandler hinzuzufügen.  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Im folgenden Beispiel wird das <xref:System.Windows.Controls.Control.MouseDoubleClick>-Ereignis behandelt.  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> Obwohl es am häufigsten ist, eine <xref:System.Windows.Controls.ListView> an eine Datenquelle zu binden, können Sie einen-Stil verwenden, um jedem <xref:System.Windows.Controls.ListViewItem> in einem nicht Daten gebundenen <xref:System.Windows.Controls.ListView> einen Ereignishandler hinzuzufügen, unabhängig davon, ob Sie explizit eine <xref:System.Windows.Controls.ListViewItem>erstellen.  Weitere Informationen zu explizit und implizit erstellten <xref:System.Windows.Controls.ListViewItem> Steuerelementen finden Sie unter <xref:System.Windows.Controls.ItemsControl>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XmlElement>
- [Übersicht zur Datenbindung](../data/data-binding-overview.md)
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Übersicht über ListView](listview-overview.md)
