---
title: 'Gewusst wie: Verwenden des Master/Detail-Musters mit hierarchischen Daten'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: 2e7d9ceed3ab8385f07d87ecdb92c0a99d410b40
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459084"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a><span data-ttu-id="a2b72-102">Gewusst wie: Verwenden des Master/Detail-Musters mit hierarchischen Daten</span><span class="sxs-lookup"><span data-stu-id="a2b72-102">How to: Use the Master-Detail Pattern with Hierarchical Data</span></span>
<span data-ttu-id="a2b72-103">Dieses Beispiel zeigt, wie das Master/Detail-Szenario implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="a2b72-103">This example shows how to implement the master-detail scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2b72-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a2b72-104">Example</span></span>  
 <span data-ttu-id="a2b72-105">In diesem Beispiel ist `LeagueList` eine Auflistung von `Leagues`.</span><span class="sxs-lookup"><span data-stu-id="a2b72-105">In this example, `LeagueList` is a collection of `Leagues`.</span></span> <span data-ttu-id="a2b72-106">Jede `League` verfügt über eine `Name` und eine Auflistung von `Divisions`, und jede `Division` hat einen Namen und eine Auflistung `Teams`.</span><span class="sxs-lookup"><span data-stu-id="a2b72-106">Each `League` has a `Name` and a collection of `Divisions`, and each `Division` has a name and a collection of `Teams`.</span></span> <span data-ttu-id="a2b72-107">Jede `Team` hat einen Teamnamen.</span><span class="sxs-lookup"><span data-stu-id="a2b72-107">Each `Team` has a team name.</span></span>  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 <span data-ttu-id="a2b72-108">Im Folgenden finden Sie ein Bildschirmfoto des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="a2b72-108">The following is a screenshot of the example.</span></span> <span data-ttu-id="a2b72-109">Der `Divisions` <xref:System.Windows.Controls.ListBox> die Auswahl im `Leagues` <xref:System.Windows.Controls.ListBox> automatisch nachverfolgt, und die entsprechenden Daten werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a2b72-109">The `Divisions` <xref:System.Windows.Controls.ListBox> automatically tracks selections in the `Leagues` <xref:System.Windows.Controls.ListBox> and display the corresponding data.</span></span> <span data-ttu-id="a2b72-110">Der `Teams` <xref:System.Windows.Controls.ListBox> die Auswahl in den beiden anderen <xref:System.Windows.Controls.ListBox>-Steuerelementen nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="a2b72-110">The `Teams` <xref:System.Windows.Controls.ListBox> tracks selections in the other two <xref:System.Windows.Controls.ListBox> controls.</span></span>  
  
 ![Screenshot, der ein Beispiel&#45;für ein Master Detail Szenario anzeigt.](./media/how-to-use-the-master-detail-pattern-with-hierarchical-data/databinding-master-detail-scenario.png)  
  
 <span data-ttu-id="a2b72-112">In diesem Beispiel sind die folgenden zwei Punkte zu beachten:</span><span class="sxs-lookup"><span data-stu-id="a2b72-112">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="a2b72-113">Die drei <xref:System.Windows.Controls.ListBox>-Steuerelemente werden an dieselbe Quelle gebunden.</span><span class="sxs-lookup"><span data-stu-id="a2b72-113">The three <xref:System.Windows.Controls.ListBox> controls bind to the same source.</span></span> <span data-ttu-id="a2b72-114">Legen Sie die <xref:System.Windows.Data.Binding.Path%2A>-Eigenschaft der Bindung auf fest, um anzugeben, welche Datenebene für die <xref:System.Windows.Controls.ListBox> angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a2b72-114">You set the <xref:System.Windows.Data.Binding.Path%2A> property of the binding to specify which level of data you want the <xref:System.Windows.Controls.ListBox> to display.</span></span>  
  
2. <span data-ttu-id="a2b72-115">Sie müssen die <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A>-Eigenschaft auf `true` für die <xref:System.Windows.Controls.ListBox> Steuerelemente festlegen, deren Auswahl Sie nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="a2b72-115">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` on the <xref:System.Windows.Controls.ListBox> controls of which the selection you are tracking.</span></span> <span data-ttu-id="a2b72-116">Durch Festlegen dieser Eigenschaft wird sichergestellt, dass das ausgewählte Element immer als <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="a2b72-116">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="a2b72-117">Wenn das <xref:System.Windows.Controls.ListBox> die Daten aus einer <xref:System.Windows.Data.CollectionViewSource>abruft, werden die Auswahl und die Währung Alternativ automatisch synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="a2b72-117">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="a2b72-118">Das Verfahren unterscheidet sich geringfügig, wenn Sie [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="a2b72-118">The technique is slightly different when you are using [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span> <span data-ttu-id="a2b72-119">Ein Beispiel finden Sie unter [Verwenden des Master/Detail-Musters mit hierarchischen XML-Daten](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="a2b72-119">For an example, see [Use the Master-Detail Pattern with Hierarchical XML Data](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2b72-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2b72-120">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="a2b72-121">Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl</span><span class="sxs-lookup"><span data-stu-id="a2b72-121">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="a2b72-122">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="a2b72-122">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="a2b72-123">Übersicht über Datenvorlagen</span><span class="sxs-lookup"><span data-stu-id="a2b72-123">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="a2b72-124">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="a2b72-124">How-to Topics</span></span>](data-binding-how-to-topics.md)
