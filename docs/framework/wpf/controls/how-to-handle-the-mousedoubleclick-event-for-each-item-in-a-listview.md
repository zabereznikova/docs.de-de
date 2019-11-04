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
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a><span data-ttu-id="edd43-102">Gewusst wie: Behandeln des MouseDoubleClick-Ereignisses für die einzelnen ListView-Einträge</span><span class="sxs-lookup"><span data-stu-id="edd43-102">How to: Handle the MouseDoubleClick Event for Each Item in a ListView</span></span>
<span data-ttu-id="edd43-103">Um ein Ereignis für ein Element in einem <xref:System.Windows.Controls.ListView>zu behandeln, müssen Sie jedem <xref:System.Windows.Controls.ListViewItem>einen Ereignishandler hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="edd43-103">To handle an event for an item in a <xref:System.Windows.Controls.ListView>, you need to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span> <span data-ttu-id="edd43-104">Wenn eine <xref:System.Windows.Controls.ListView> an eine Datenquelle gebunden ist, erstellen Sie nicht explizit eine <xref:System.Windows.Controls.ListViewItem>, aber Sie können das Ereignis für jedes Element behandeln, indem Sie einem Stil einer <xref:System.Windows.Controls.ListViewItem>eine <xref:System.Windows.EventSetter> hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="edd43-104">When a <xref:System.Windows.Controls.ListView> is bound to a data source, you don't explicitly create a <xref:System.Windows.Controls.ListViewItem>, but you can handle the event for each item by adding an <xref:System.Windows.EventSetter> to a style of a <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="edd43-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="edd43-105">Example</span></span>  
 <span data-ttu-id="edd43-106">Im folgenden Beispiel wird ein Daten gebundenes <xref:System.Windows.Controls.ListView> erstellt und ein <xref:System.Windows.Style> erstellt, um jedem <xref:System.Windows.Controls.ListViewItem>einen Ereignishandler hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="edd43-106">The following example creates a data-bound <xref:System.Windows.Controls.ListView> and creates a <xref:System.Windows.Style> to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="edd43-107">Im folgenden Beispiel wird das <xref:System.Windows.Controls.Control.MouseDoubleClick>-Ereignis behandelt.</span><span class="sxs-lookup"><span data-stu-id="edd43-107">The following example handles the <xref:System.Windows.Controls.Control.MouseDoubleClick> event.</span></span>  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> <span data-ttu-id="edd43-108">Obwohl es am häufigsten ist, eine <xref:System.Windows.Controls.ListView> an eine Datenquelle zu binden, können Sie einen-Stil verwenden, um jedem <xref:System.Windows.Controls.ListViewItem> in einem nicht Daten gebundenen <xref:System.Windows.Controls.ListView> einen Ereignishandler hinzuzufügen, unabhängig davon, ob Sie explizit eine <xref:System.Windows.Controls.ListViewItem>erstellen.</span><span class="sxs-lookup"><span data-stu-id="edd43-108">Although it is most common to bind a <xref:System.Windows.Controls.ListView> to a data source, you can use a style to add an event handler to each <xref:System.Windows.Controls.ListViewItem> in a non-data-bound <xref:System.Windows.Controls.ListView> regardless of whether you explicitly create a <xref:System.Windows.Controls.ListViewItem>.</span></span>  <span data-ttu-id="edd43-109">Weitere Informationen zu explizit und implizit erstellten <xref:System.Windows.Controls.ListViewItem> Steuerelementen finden Sie unter <xref:System.Windows.Controls.ItemsControl>.</span><span class="sxs-lookup"><span data-stu-id="edd43-109">For more information about explicitly and implicitly created <xref:System.Windows.Controls.ListViewItem> controls, see <xref:System.Windows.Controls.ItemsControl>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edd43-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="edd43-110">See also</span></span>

- <xref:System.Xml.XmlElement>
- [<span data-ttu-id="edd43-111">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="edd43-111">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="edd43-112">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="edd43-112">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="edd43-113">Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen</span><span class="sxs-lookup"><span data-stu-id="edd43-113">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="edd43-114">Übersicht über ListView</span><span class="sxs-lookup"><span data-stu-id="edd43-114">ListView Overview</span></span>](listview-overview.md)
