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
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a><span data-ttu-id="ae617-102">Gewusst wie: Behandeln des MouseDoubleClick-Ereignisses für die einzelnen ListView-Einträge</span><span class="sxs-lookup"><span data-stu-id="ae617-102">How to: Handle the MouseDoubleClick Event for Each Item in a ListView</span></span>
<span data-ttu-id="ae617-103">Für die Ereignisbehandlung für ein Element in einem <xref:System.Windows.Controls.ListView>, müssen Sie einen Ereignishandler hinzuzufügen <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="ae617-103">To handle an event for an item in a <xref:System.Windows.Controls.ListView>, you need to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span> <span data-ttu-id="ae617-104">Wenn eine <xref:System.Windows.Controls.ListView> gebunden ist Sie nicht explizit erstellen, mit einer Datenquelle eine <xref:System.Windows.Controls.ListViewItem>, aber Sie können das Ereignis für jedes Element durch Hinzufügen von behandeln ein <xref:System.Windows.EventSetter> einen Stil der eine <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="ae617-104">When a <xref:System.Windows.Controls.ListView> is bound to a data source, you don't explicitly create a <xref:System.Windows.Controls.ListViewItem>, but you can handle the event for each item by adding an <xref:System.Windows.EventSetter> to a style of a <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae617-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ae617-105">Example</span></span>  
 <span data-ttu-id="ae617-106">Das folgende Beispiel erstellt ein datengebundenes <xref:System.Windows.Controls.ListView> und erstellt eine <xref:System.Windows.Style> um einen Ereignishandler hinzuzufügen <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="ae617-106">The following example creates a data-bound <xref:System.Windows.Controls.ListView> and creates a <xref:System.Windows.Style> to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="ae617-107">Das folgende Beispiel verarbeitet die <xref:System.Windows.Controls.Control.MouseDoubleClick> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="ae617-107">The following example handles the <xref:System.Windows.Controls.Control.MouseDoubleClick> event.</span></span>  
  
 [!code-csharp[ListViewHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  <span data-ttu-id="ae617-108">Obwohl es am häufigsten verwendeten gebunden ist, eine <xref:System.Windows.Controls.ListView> mit einer Datenquelle können Sie einen Stil verwenden, um einen Ereignishandler hinzuzufügen <xref:System.Windows.Controls.ListViewItem> in einer nicht-Data-Bound <xref:System.Windows.Controls.ListView> unabhängig davon, ob Sie explizit erstellen eine <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="ae617-108">Although it is most common to bind a <xref:System.Windows.Controls.ListView> to a data source, you can use a style to add an event handler to each <xref:System.Windows.Controls.ListViewItem> in a non-data-bound <xref:System.Windows.Controls.ListView> regardless of whether you explicitly create a <xref:System.Windows.Controls.ListViewItem>.</span></span>  <span data-ttu-id="ae617-109">Weitere Informationen zu explizit und implizit erstellten <xref:System.Windows.Controls.ListViewItem> -Steuerelemente finden Sie unter <xref:System.Windows.Controls.ItemsControl>.</span><span class="sxs-lookup"><span data-stu-id="ae617-109">For more information about explicitly and implicitly created <xref:System.Windows.Controls.ListViewItem> controls, see <xref:System.Windows.Controls.ItemsControl>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae617-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae617-110">See Also</span></span>  
 <xref:System.Xml.XmlElement>  
 [<span data-ttu-id="ae617-111">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="ae617-111">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="ae617-112">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="ae617-112">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="ae617-113">Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen</span><span class="sxs-lookup"><span data-stu-id="ae617-113">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [<span data-ttu-id="ae617-114">Übersicht über ListView</span><span class="sxs-lookup"><span data-stu-id="ae617-114">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)
