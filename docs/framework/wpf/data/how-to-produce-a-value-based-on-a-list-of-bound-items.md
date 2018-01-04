---
title: 'Gewusst wie: Erzeugen eines Werts auf Grundlage einer Liste gebundener Elemente'
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
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c3987690a1acb180ee22fa02e399accd9c5d481d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a><span data-ttu-id="614ee-102">Gewusst wie: Erzeugen eines Werts auf Grundlage einer Liste gebundener Elemente</span><span class="sxs-lookup"><span data-stu-id="614ee-102">How to: Produce a Value Based on a List of Bound Items</span></span>
<span data-ttu-id="614ee-103"><xref:System.Windows.Data.MultiBinding>können Sie eine Bindungsziel-Eigenschaft auf eine Liste von Eigenschaften der Datenquelle zu binden und dann Logik anwenden, um einen Wert mit den angegebenen Eingaben zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="614ee-103"><xref:System.Windows.Data.MultiBinding> allows you to bind a binding target property to a list of source properties and then apply logic to produce a value with the given inputs.</span></span> <span data-ttu-id="614ee-104">In diesem Beispiel wird veranschaulicht, wie <xref:System.Windows.Data.MultiBinding>.</span><span class="sxs-lookup"><span data-stu-id="614ee-104">This example demonstrates how to use <xref:System.Windows.Data.MultiBinding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="614ee-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="614ee-105">Example</span></span>  
 <span data-ttu-id="614ee-106">Im folgenden Beispiel verweist `NameListData` auf eine Auflistung von `PersonName`-Objekten, bei denen es sich um Objekte handelt, die zwei Eigenschaften enthalten, `firstName` und `lastName`.</span><span class="sxs-lookup"><span data-stu-id="614ee-106">In the following example, `NameListData` refers to a collection of `PersonName` objects, which are objects that contain two properties, `firstName` and `lastName`.</span></span> <span data-ttu-id="614ee-107">Im folgenden Beispiel wird eine <xref:System.Windows.Controls.TextBlock> , die vor- und Nachnamen Namen einer Person mit den Nachnamen des ersten anzeigt.</span><span class="sxs-lookup"><span data-stu-id="614ee-107">The following example produces a <xref:System.Windows.Controls.TextBlock> that shows the first and last names of a person with the last name first.</span></span>  
  
 [!code-xaml[MultiBinding#Resources1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 <span data-ttu-id="614ee-108">Um zu verstehen, wie das Format „Nachname-Vorname“ erzeugt wird, betrachten Sie zunächst die Implementierung von `NameConverter`:</span><span class="sxs-lookup"><span data-stu-id="614ee-108">To understand how the last-name-first format is produced, let's take a look at the implementation of the `NameConverter`:</span></span>  
  
 [!code-csharp[MultiBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 <span data-ttu-id="614ee-109">`NameConverter` implementiert die <xref:System.Windows.Data.IMultiValueConverter>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="614ee-109">`NameConverter` implements the <xref:System.Windows.Data.IMultiValueConverter> interface.</span></span> <span data-ttu-id="614ee-110">`NameConverter` übernimmt die Werte aus den einzelnen Bindungen und speichert sie im Werteobjektarray.</span><span class="sxs-lookup"><span data-stu-id="614ee-110">`NameConverter` takes the values from the individual bindings and stores them in the values object array.</span></span> <span data-ttu-id="614ee-111">In welcher Reihenfolge die <xref:System.Windows.Data.Binding> Elemente angezeigt werden, unter der <xref:System.Windows.Data.MultiBinding> Element ist die Reihenfolge, in denen diese Werte im Array gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="614ee-111">The order in which the <xref:System.Windows.Data.Binding> elements appear under the <xref:System.Windows.Data.MultiBinding> element is the order in which those values are stored in the array.</span></span> <span data-ttu-id="614ee-112">Der Wert des der <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> Parameterargument Attribut verweist die <xref:System.Windows.Data.MultiBinding.Converter%2A> Methode, die einen Switch für den Parameter, um zu bestimmen, wie der Name formatiert ausführt.</span><span class="sxs-lookup"><span data-stu-id="614ee-112">The value of the <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> attribute is referenced by the parameter argument of the <xref:System.Windows.Data.MultiBinding.Converter%2A> method, which performs a switch on the parameter to determine how to format the name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="614ee-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="614ee-113">See Also</span></span>  
 [<span data-ttu-id="614ee-114">Konvertieren von gebundenen Daten</span><span class="sxs-lookup"><span data-stu-id="614ee-114">Convert Bound Data</span></span>](../../../../docs/framework/wpf/data/how-to-convert-bound-data.md)  
 [<span data-ttu-id="614ee-115">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="614ee-115">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="614ee-116">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="614ee-116">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
