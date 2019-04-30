---
title: 'Vorgehensweise: Erzeugen eines Werts auf Grundlage einer Liste gebundener Elemente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
ms.openlocfilehash: c2ec5ff26c89649294df266e790445e5aa5d08ae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931389"
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a><span data-ttu-id="89835-102">Vorgehensweise: Erzeugen eines Werts auf Grundlage einer Liste gebundener Elemente</span><span class="sxs-lookup"><span data-stu-id="89835-102">How to: Produce a Value Based on a List of Bound Items</span></span>
<span data-ttu-id="89835-103"><xref:System.Windows.Data.MultiBinding> können Sie eine Eigenschaft eines Bindungsziels an eine Liste von Quelleigenschaften binden und anschließend Logik anwenden, um einen Wert mit den angegebenen Eingaben zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="89835-103"><xref:System.Windows.Data.MultiBinding> allows you to bind a binding target property to a list of source properties and then apply logic to produce a value with the given inputs.</span></span> <span data-ttu-id="89835-104">In diesem Beispiel wird veranschaulicht, wie <xref:System.Windows.Data.MultiBinding>.</span><span class="sxs-lookup"><span data-stu-id="89835-104">This example demonstrates how to use <xref:System.Windows.Data.MultiBinding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89835-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89835-105">Example</span></span>  
 <span data-ttu-id="89835-106">Im folgenden Beispiel verweist `NameListData` auf eine Auflistung von `PersonName`-Objekten, bei denen es sich um Objekte handelt, die zwei Eigenschaften enthalten, `firstName` und `lastName`.</span><span class="sxs-lookup"><span data-stu-id="89835-106">In the following example, `NameListData` refers to a collection of `PersonName` objects, which are objects that contain two properties, `firstName` and `lastName`.</span></span> <span data-ttu-id="89835-107">Im folgenden Beispiel wird eine <xref:System.Windows.Controls.TextBlock> , die die ersten und letzten Namen einer Person mit dem Nachnamen ersten zeigt.</span><span class="sxs-lookup"><span data-stu-id="89835-107">The following example produces a <xref:System.Windows.Controls.TextBlock> that shows the first and last names of a person with the last name first.</span></span>  
  
 [!code-xaml[MultiBinding#Resources1](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 <span data-ttu-id="89835-108">Um zu verstehen, wie das Format „Nachname-Vorname“ erzeugt wird, betrachten Sie zunächst die Implementierung von `NameConverter`:</span><span class="sxs-lookup"><span data-stu-id="89835-108">To understand how the last-name-first format is produced, let's take a look at the implementation of the `NameConverter`:</span></span>  
  
 [!code-csharp[MultiBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 <span data-ttu-id="89835-109">`NameConverter` implementiert die <xref:System.Windows.Data.IMultiValueConverter>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="89835-109">`NameConverter` implements the <xref:System.Windows.Data.IMultiValueConverter> interface.</span></span> <span data-ttu-id="89835-110">`NameConverter` übernimmt die Werte aus den einzelnen Bindungen und speichert sie im Werteobjektarray.</span><span class="sxs-lookup"><span data-stu-id="89835-110">`NameConverter` takes the values from the individual bindings and stores them in the values object array.</span></span> <span data-ttu-id="89835-111">Die Reihenfolge, in der <xref:System.Windows.Data.Binding> Elemente angezeigt werden, unter der <xref:System.Windows.Data.MultiBinding> Element ist die Reihenfolge, in dem diese Werte im Array gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="89835-111">The order in which the <xref:System.Windows.Data.Binding> elements appear under the <xref:System.Windows.Data.MultiBinding> element is the order in which those values are stored in the array.</span></span> <span data-ttu-id="89835-112">Der Wert des der <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> Parameterargument Attribut verweist die <xref:System.Windows.Data.MultiBinding.Converter%2A> -Methode, die mit einen Switch für den Parameter, um zu bestimmen, wie der Name formatiert ausführt.</span><span class="sxs-lookup"><span data-stu-id="89835-112">The value of the <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> attribute is referenced by the parameter argument of the <xref:System.Windows.Data.MultiBinding.Converter%2A> method, which performs a switch on the parameter to determine how to format the name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89835-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89835-113">See also</span></span>

- [<span data-ttu-id="89835-114">Konvertieren von gebundenen Daten</span><span class="sxs-lookup"><span data-stu-id="89835-114">Convert Bound Data</span></span>](how-to-convert-bound-data.md)
- [<span data-ttu-id="89835-115">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="89835-115">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="89835-116">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="89835-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
