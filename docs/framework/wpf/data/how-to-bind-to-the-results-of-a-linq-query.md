---
title: 'Gewusst wie: Binden an die Ergebnisse einer LINQ-Abfrage'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ad4969d80f7bd801ec738fa40e8b2d4ab9deefad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a><span data-ttu-id="31562-102">Gewusst wie: Binden an die Ergebnisse einer LINQ-Abfrage</span><span class="sxs-lookup"><span data-stu-id="31562-102">How to: Bind to the Results of a LINQ Query</span></span>
<span data-ttu-id="31562-103">In diesem Beispiel wird veranschaulicht, wie eine LINQ-Abfrage ausführen, und klicken Sie dann mit den Ergebnissen binden.</span><span class="sxs-lookup"><span data-stu-id="31562-103">This example demonstrates how to run a LINQ query and then bind to the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31562-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="31562-104">Example</span></span>  
 <span data-ttu-id="31562-105">Das folgende Beispiel erstellt zwei Listenfelder.</span><span class="sxs-lookup"><span data-stu-id="31562-105">The following example creates two list boxes.</span></span> <span data-ttu-id="31562-106">Die erste Listenfeld enthält drei Listenelemente.</span><span class="sxs-lookup"><span data-stu-id="31562-106">The first list box contains three list items.</span></span>  
  
 [!code-xaml[LinqExample#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="31562-107">Auswählen eines Elements in der ersten Liste wird der folgende Ereignishandler aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="31562-107">Selecting an item from the first list box invokes the following event handler.</span></span> <span data-ttu-id="31562-108">In diesem Beispiel `Tasks` ist eine Sammlung von `Task` Objekte.</span><span class="sxs-lookup"><span data-stu-id="31562-108">In this example, `Tasks` is a collection of `Task` objects.</span></span> <span data-ttu-id="31562-109">Die `Task` -Klasse verfügt über eine Eigenschaft namens `Priority`.</span><span class="sxs-lookup"><span data-stu-id="31562-109">The `Task` class has a property named `Priority`.</span></span> <span data-ttu-id="31562-110">Dieser Ereignishandler führt eine LINQ-Abfrage, die die Auflistung der zurückgibt `Task` Objekte, die den ausgewählten Priority-Wert und legt dann als die <xref:System.Windows.FrameworkElement.DataContext%2A>:</span><span class="sxs-lookup"><span data-stu-id="31562-110">This event handler runs a LINQ query that returns the collection of `Task` objects that have the selected priority value, and then sets that as the <xref:System.Windows.FrameworkElement.DataContext%2A>:</span></span>  
  
 [!code-csharp[LinqExample#Using](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]  
[!code-csharp[LinqExample#Tasks](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]  
[!code-csharp[LinqExample#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]  
  
 <span data-ttu-id="31562-111">Für diese Sammlung wird im zweiten Listenfeld gebunden, da seine <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Wert wird festgelegt, um `{Binding}`.</span><span class="sxs-lookup"><span data-stu-id="31562-111">The second list box binds to that collection because its <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> value is set to `{Binding}`.</span></span> <span data-ttu-id="31562-112">Daher wird die zurückgegebene Auflistung angezeigt (basierend auf den `myTaskTemplate` <xref:System.Windows.DataTemplate>).</span><span class="sxs-lookup"><span data-stu-id="31562-112">As a result, it displays the returned collection (based on the `myTaskTemplate`<xref:System.Windows.DataTemplate>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31562-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31562-113">See Also</span></span>  
 [<span data-ttu-id="31562-114">Bereitstellen von Daten für die Bindung in XAML</span><span class="sxs-lookup"><span data-stu-id="31562-114">Make Data Available for Binding in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)  
 [<span data-ttu-id="31562-115">Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl</span><span class="sxs-lookup"><span data-stu-id="31562-115">Bind to a Collection and Display Information Based on Selection</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)  
 [<span data-ttu-id="31562-116">Neues in WPF Version 4.5</span><span class="sxs-lookup"><span data-stu-id="31562-116">What's New in WPF Version 4.5</span></span>](../../../../docs/framework/wpf/getting-started/whats-new.md)  
 [<span data-ttu-id="31562-117">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="31562-117">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="31562-118">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="31562-118">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
