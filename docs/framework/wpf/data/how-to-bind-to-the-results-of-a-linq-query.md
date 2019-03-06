---
title: 'Vorgehensweise: Binden an die Ergebnisse einer LINQ-Abfrage'
ms.date: 03/30/2017
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
ms.openlocfilehash: 9be0f95824c97456b50996f9cd6f010442b523f2
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355947"
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a><span data-ttu-id="8f86f-102">Vorgehensweise: Binden an die Ergebnisse einer LINQ-Abfrage</span><span class="sxs-lookup"><span data-stu-id="8f86f-102">How to: Bind to the Results of a LINQ Query</span></span>
<span data-ttu-id="8f86f-103">Dieses Beispiel zeigt, wie Sie eine LINQ-Abfrage ausführen und dann Binden an die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="8f86f-103">This example demonstrates how to run a LINQ query and then bind to the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f86f-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f86f-104">Example</span></span>  
 <span data-ttu-id="8f86f-105">Das folgende Beispiel erstellt zwei Listenfelder.</span><span class="sxs-lookup"><span data-stu-id="8f86f-105">The following example creates two list boxes.</span></span> <span data-ttu-id="8f86f-106">Das erste Listenfeld enthält drei Listenelemente.</span><span class="sxs-lookup"><span data-stu-id="8f86f-106">The first list box contains three list items.</span></span>  
  
 [!code-xaml[LinqExample#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="8f86f-107">Das erste Listenfeld ein Element auswählen, wird der folgende Ereignishandler aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8f86f-107">Selecting an item from the first list box invokes the following event handler.</span></span> <span data-ttu-id="8f86f-108">In diesem Beispiel `Tasks` ist eine Sammlung von `Task` Objekte.</span><span class="sxs-lookup"><span data-stu-id="8f86f-108">In this example, `Tasks` is a collection of `Task` objects.</span></span> <span data-ttu-id="8f86f-109">Die `Task` -Klasse verfügt über eine Eigenschaft namens `Priority`.</span><span class="sxs-lookup"><span data-stu-id="8f86f-109">The `Task` class has a property named `Priority`.</span></span> <span data-ttu-id="8f86f-110">Dieser Ereignishandler ausgeführt wird, eine LINQ-Abfrage, die die Auflistung der zurückgibt `Task` Objekte, die den ausgewählten Priority-Wert und legt dann fest, dass die <xref:System.Windows.FrameworkElement.DataContext%2A>:</span><span class="sxs-lookup"><span data-stu-id="8f86f-110">This event handler runs a LINQ query that returns the collection of `Task` objects that have the selected priority value, and then sets that as the <xref:System.Windows.FrameworkElement.DataContext%2A>:</span></span>  
  
 [!code-csharp[LinqExample#Using](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]  
[!code-csharp[LinqExample#Tasks](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]  
[!code-csharp[LinqExample#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]  
  
 <span data-ttu-id="8f86f-111">Das zweite Listenfeld wird eine Bindung an die Sammlung erstellt, da die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Wert wird festgelegt, um `{Binding}`.</span><span class="sxs-lookup"><span data-stu-id="8f86f-111">The second list box binds to that collection because its <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> value is set to `{Binding}`.</span></span> <span data-ttu-id="8f86f-112">Daher wird die zurückgegebene Auflistung (basierend auf den `myTaskTemplate` <xref:System.Windows.DataTemplate>).</span><span class="sxs-lookup"><span data-stu-id="8f86f-112">As a result, it displays the returned collection (based on the `myTaskTemplate`<xref:System.Windows.DataTemplate>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f86f-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f86f-113">See also</span></span>
- [<span data-ttu-id="8f86f-114">Bereitstellen von Daten für die Bindung in XAML</span><span class="sxs-lookup"><span data-stu-id="8f86f-114">Make Data Available for Binding in XAML</span></span>](how-to-make-data-available-for-binding-in-xaml.md)
- [<span data-ttu-id="8f86f-115">Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl</span><span class="sxs-lookup"><span data-stu-id="8f86f-115">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="8f86f-116">Neues in WPF Version 4.5</span><span class="sxs-lookup"><span data-stu-id="8f86f-116">What's New in WPF Version 4.5</span></span>](../getting-started/whats-new.md)
- [<span data-ttu-id="8f86f-117">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="8f86f-117">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="8f86f-118">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="8f86f-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
