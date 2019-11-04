---
title: 'Gewusst wie: Erzeugen eines Werts auf Grundlage einer Liste gebundener Elemente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
ms.openlocfilehash: da183a34eb85de54b1e3f54f8d14c09e25640165
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459691"
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a><span data-ttu-id="99c8b-102">Gewusst wie: Erzeugen eines Werts auf Grundlage einer Liste gebundener Elemente</span><span class="sxs-lookup"><span data-stu-id="99c8b-102">How to: Produce a Value Based on a List of Bound Items</span></span>
<span data-ttu-id="99c8b-103">mit <xref:System.Windows.Data.MultiBinding> können Sie eine Bindungs Ziel Eigenschaft an eine Liste von Quell Eigenschaften binden und dann die Logik anwenden, um einen Wert mit den angegebenen Eingaben zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="99c8b-103"><xref:System.Windows.Data.MultiBinding> allows you to bind a binding target property to a list of source properties and then apply logic to produce a value with the given inputs.</span></span> <span data-ttu-id="99c8b-104">In diesem Beispiel wird die Verwendung <xref:System.Windows.Data.MultiBinding>veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="99c8b-104">This example demonstrates how to use <xref:System.Windows.Data.MultiBinding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99c8b-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="99c8b-105">Example</span></span>  
 <span data-ttu-id="99c8b-106">Im folgenden Beispiel verweist `NameListData` auf eine Auflistung von `PersonName`-Objekten, bei denen es sich um Objekte handelt, die zwei Eigenschaften enthalten, `firstName` und `lastName`.</span><span class="sxs-lookup"><span data-stu-id="99c8b-106">In the following example, `NameListData` refers to a collection of `PersonName` objects, which are objects that contain two properties, `firstName` and `lastName`.</span></span> <span data-ttu-id="99c8b-107">Im folgenden Beispiel wird eine <xref:System.Windows.Controls.TextBlock> erstellt, die zuerst den vor-und Nachnamen einer Person mit dem Nachnamen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="99c8b-107">The following example produces a <xref:System.Windows.Controls.TextBlock> that shows the first and last names of a person with the last name first.</span></span>  
  
 [!code-xaml[MultiBinding#Resources1](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 <span data-ttu-id="99c8b-108">Um zu verstehen, wie das Format „Nachname-Vorname“ erzeugt wird, betrachten Sie zunächst die Implementierung von `NameConverter`:</span><span class="sxs-lookup"><span data-stu-id="99c8b-108">To understand how the last-name-first format is produced, let's take a look at the implementation of the `NameConverter`:</span></span>  
  
 [!code-csharp[MultiBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 <span data-ttu-id="99c8b-109">`NameConverter` implementiert die <xref:System.Windows.Data.IMultiValueConverter>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="99c8b-109">`NameConverter` implements the <xref:System.Windows.Data.IMultiValueConverter> interface.</span></span> <span data-ttu-id="99c8b-110">`NameConverter` übernimmt die Werte aus den einzelnen Bindungen und speichert sie im Werteobjektarray.</span><span class="sxs-lookup"><span data-stu-id="99c8b-110">`NameConverter` takes the values from the individual bindings and stores them in the values object array.</span></span> <span data-ttu-id="99c8b-111">Die Reihenfolge, in der die <xref:System.Windows.Data.Binding> Elemente unter dem <xref:System.Windows.Data.MultiBinding>-Element angezeigt werden, ist die Reihenfolge, in der diese Werte im Array gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="99c8b-111">The order in which the <xref:System.Windows.Data.Binding> elements appear under the <xref:System.Windows.Data.MultiBinding> element is the order in which those values are stored in the array.</span></span> <span data-ttu-id="99c8b-112">Auf den Wert des <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> Attributs wird durch das Parameter-Argument der <xref:System.Windows.Data.MultiBinding.Converter%2A>-Methode verwiesen, die einen Schalter für den-Parameter ausführt, um zu bestimmen, wie der Name formatiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="99c8b-112">The value of the <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> attribute is referenced by the parameter argument of the <xref:System.Windows.Data.MultiBinding.Converter%2A> method, which performs a switch on the parameter to determine how to format the name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99c8b-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99c8b-113">See also</span></span>

- [<span data-ttu-id="99c8b-114">Konvertieren von gebundenen Daten</span><span class="sxs-lookup"><span data-stu-id="99c8b-114">Convert Bound Data</span></span>](how-to-convert-bound-data.md)
- [<span data-ttu-id="99c8b-115">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="99c8b-115">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="99c8b-116">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="99c8b-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
