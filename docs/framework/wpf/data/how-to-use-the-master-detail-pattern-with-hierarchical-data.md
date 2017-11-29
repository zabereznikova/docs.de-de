---
title: 'Gewusst wie: Verwenden des Master/Detail-Musters mit hierarchischen Daten'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bb546a3429012a49ee7652a3470460935fc76d70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a><span data-ttu-id="0d9c4-102">Gewusst wie: Verwenden des Master/Detail-Musters mit hierarchischen Daten</span><span class="sxs-lookup"><span data-stu-id="0d9c4-102">How to: Use the Master-Detail Pattern with Hierarchical Data</span></span>
<span data-ttu-id="0d9c4-103">In diesem Beispiel wird gezeigt, wie das Master / Detail-Szenario implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="0d9c4-103">This example shows how to implement the master-detail scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d9c4-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0d9c4-104">Example</span></span>  
 <span data-ttu-id="0d9c4-105">In diesem Beispiel `LeagueList` ist eine Sammlung von `Leagues`.</span><span class="sxs-lookup"><span data-stu-id="0d9c4-105">In this example, `LeagueList` is a collection of `Leagues`.</span></span> <span data-ttu-id="0d9c4-106">Jede `League` verfügt über eine `Name` und eine Auflistung von `Divisions`, und jede `Division` hat einen Namen und eine Auflistung von `Teams`.</span><span class="sxs-lookup"><span data-stu-id="0d9c4-106">Each `League` has a `Name` and a collection of `Divisions`, and each `Division` has a name and a collection of `Teams`.</span></span> <span data-ttu-id="0d9c4-107">Jede `Team` hat einen Teamnamen ein.</span><span class="sxs-lookup"><span data-stu-id="0d9c4-107">Each `Team` has a team name.</span></span>  
  
 [!code-xaml[MasterDetail#HowTo1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 <span data-ttu-id="0d9c4-108">Im Folgenden finden Sie ein Bildschirmfoto des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="0d9c4-108">The following is a screenshot of the example.</span></span> <span data-ttu-id="0d9c4-109">Die `Divisions` <xref:System.Windows.Controls.ListBox> verfolgt automatisch die Auswahlmöglichkeiten in den `Leagues` <xref:System.Windows.Controls.ListBox> und zeigt entsprechende Daten.</span><span class="sxs-lookup"><span data-stu-id="0d9c4-109">The `Divisions` <xref:System.Windows.Controls.ListBox> automatically tracks selections in the `Leagues` <xref:System.Windows.Controls.ListBox> and display the corresponding data.</span></span> <span data-ttu-id="0d9c4-110">Die `Teams` <xref:System.Windows.Controls.ListBox> verfolgt die Auswahlmöglichkeiten in den anderen beiden <xref:System.Windows.Controls.ListBox> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="0d9c4-110">The `Teams` <xref:System.Windows.Controls.ListBox> tracks selections in the other two <xref:System.Windows.Controls.ListBox> controls.</span></span>  
  
 <span data-ttu-id="0d9c4-111">![Master &#45; Detail-Beispiel](../../../../docs/framework/wpf/data/media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")</span><span class="sxs-lookup"><span data-stu-id="0d9c4-111">![Master&#45;detail example](../../../../docs/framework/wpf/data/media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")</span></span>  
  
 <span data-ttu-id="0d9c4-112">Die zwei Punkte zu beachten in diesem Beispiel sind:</span><span class="sxs-lookup"><span data-stu-id="0d9c4-112">The two things to notice in this example are:</span></span>  
  
1.  <span data-ttu-id="0d9c4-113">Die drei <xref:System.Windows.Controls.ListBox> Steuerelemente mit der gleichen Quelle zu binden.</span><span class="sxs-lookup"><span data-stu-id="0d9c4-113">The three <xref:System.Windows.Controls.ListBox> controls bind to the same source.</span></span> <span data-ttu-id="0d9c4-114">Festlegen der <xref:System.Windows.Data.Binding.Path%2A> -Eigenschaft der Bindung, um anzugeben, welche Stufe von Daten soll die <xref:System.Windows.Controls.ListBox> angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0d9c4-114">You set the <xref:System.Windows.Data.Binding.Path%2A> property of the binding to specify which level of data you want the <xref:System.Windows.Controls.ListBox> to display.</span></span>  
  
2.  <span data-ttu-id="0d9c4-115">Müssen Sie festlegen der <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> Eigenschaft `true` auf die <xref:System.Windows.Controls.ListBox> Steuerelemente, von denen die Auswahl, die Sie verfolgen.</span><span class="sxs-lookup"><span data-stu-id="0d9c4-115">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` on the <xref:System.Windows.Controls.ListBox> controls of which the selection you are tracking.</span></span> <span data-ttu-id="0d9c4-116">Durch Festlegen dieser Eigenschaft wird sichergestellt, dass das ausgewählte Element immer, als festgelegt ist die <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="0d9c4-116">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="0d9c4-117">Auch wenn die <xref:System.Windows.Controls.ListBox> ruft es Daten aus einer <xref:System.Windows.Data.CollectionViewSource>, es Auswahl und Währung automatisch synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="0d9c4-117">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="0d9c4-118">Das Verfahren unterscheidet sich geringfügig bei Verwendung von [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten.</span><span class="sxs-lookup"><span data-stu-id="0d9c4-118">The technique is slightly different when you are using [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span> <span data-ttu-id="0d9c4-119">Ein Beispiel finden Sie unter [verwenden das Master / Detail-Musters mit hierarchischen XML-Daten](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="0d9c4-119">For an example, see [Use the Master-Detail Pattern with Hierarchical XML Data](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d9c4-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d9c4-120">See Also</span></span>  
 <xref:System.Windows.HierarchicalDataTemplate>  
 [<span data-ttu-id="0d9c4-121">Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl</span><span class="sxs-lookup"><span data-stu-id="0d9c4-121">Bind to a Collection and Display Information Based on Selection</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)  
 [<span data-ttu-id="0d9c4-122">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="0d9c4-122">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="0d9c4-123">Übersicht über Datenvorlagen</span><span class="sxs-lookup"><span data-stu-id="0d9c4-123">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [<span data-ttu-id="0d9c4-124">Themen zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="0d9c4-124">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
