---
title: "Gewusst wie: Behandeln des MouseDoubleClick-Ereignisses für die einzelnen ListView-Einträge"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 53c40e9e3b02bdf33a073a93d28b619e399e375f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>Gewusst wie: Behandeln des MouseDoubleClick-Ereignisses für die einzelnen ListView-Einträge
Für die Ereignisbehandlung für ein Element in einem <xref:System.Windows.Controls.ListView>, müssen Sie einen Ereignishandler hinzuzufügen <xref:System.Windows.Controls.ListViewItem>. Wenn eine <xref:System.Windows.Controls.ListView> gebunden ist Sie nicht explizit erstellen, mit einer Datenquelle eine <xref:System.Windows.Controls.ListViewItem>, aber Sie können das Ereignis für jedes Element durch Hinzufügen von behandeln ein <xref:System.Windows.EventSetter> einen Stil der eine <xref:System.Windows.Controls.ListViewItem>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt ein datengebundenes <xref:System.Windows.Controls.ListView> und erstellt eine <xref:System.Windows.Style> um einen Ereignishandler hinzuzufügen <xref:System.Windows.Controls.ListViewItem>.  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Das folgende Beispiel verarbeitet die <xref:System.Windows.Controls.Control.MouseDoubleClick> Ereignis.  
  
 [!code-csharp[ListViewHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  Obwohl es am häufigsten verwendeten gebunden ist, eine <xref:System.Windows.Controls.ListView> mit einer Datenquelle können Sie einen Stil verwenden, um einen Ereignishandler hinzuzufügen <xref:System.Windows.Controls.ListViewItem> in einer nicht-Data-Bound <xref:System.Windows.Controls.ListView> unabhängig davon, ob Sie explizit erstellen eine <xref:System.Windows.Controls.ListViewItem>.  Weitere Informationen zu explizit und implizit erstellten <xref:System.Windows.Controls.ListViewItem> -Steuerelemente finden Sie unter <xref:System.Windows.Controls.ItemsControl>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.XmlElement>  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)
