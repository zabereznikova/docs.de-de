---
title: 'Gewusst wie: Bereitstellen von Daten, um diese in XAML zu binden'
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: 91e89dbf36024c31f4afcd9b6d956944baf13576
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174185"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="8b8d5-102">Gewusst wie: Bereitstellen von Daten, um diese in XAML zu binden</span><span class="sxs-lookup"><span data-stu-id="8b8d5-102">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="8b8d5-103">In diesem Thema werden verschiedene Möglichkeiten erläutert, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]wie Sie Daten für die Bindung in verfügbar machen können, je nach den Anforderungen Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="8b8d5-103">This topic discusses various ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b8d5-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8b8d5-104">Example</span></span>  
 <span data-ttu-id="8b8d5-105">Wenn Sie über ein CLR-Objekt (Common Language Runtime) verfügen, an das Sie von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]binden möchten, können Sie `x:Key`das Objekt als Bindung verfügbar machen, wenn Sie es als Ressource definieren und ihm eine geben.</span><span class="sxs-lookup"><span data-stu-id="8b8d5-105">If you have a common language runtime (CLR) object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="8b8d5-106">Im folgenden Beispiel haben `Person` Sie ein Objekt `PersonName`mit einer Zeichenfolgeneigenschaft mit dem Namen .</span><span class="sxs-lookup"><span data-stu-id="8b8d5-106">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="8b8d5-107">Das `Person` Objekt (in der angezeigten `<src>` Hervorgehobenen Zeile, die `SDKSample`das Element enthält) wird im Namespace namens definiert.</span><span class="sxs-lookup"><span data-stu-id="8b8d5-107">The `Person` object (in the line shown highlighted that contains the `<src>` element) is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="8b8d5-108">Sie können das <xref:System.Windows.Controls.TextBlock> Steuerelement dann [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]an das Objekt in `<TextBlock>` binden, wie die hervorgehobene Zeile zeigt, die das Element enthält.</span><span class="sxs-lookup"><span data-stu-id="8b8d5-108">You can then bind the <xref:System.Windows.Controls.TextBlock> control to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as the highlighted line that contains the `<TextBlock>` element shows.</span></span>
  
 <span data-ttu-id="8b8d5-109">Alternativ können Sie die <xref:System.Windows.Data.ObjectDataProvider> Klasse verwenden, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8b8d5-109">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example:</span></span>  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 <span data-ttu-id="8b8d5-110">Sie definieren die Bindung auf die gleiche Weise, wie die hervorgehobene Zeile, die das `<TextBlock>` Element enthält, zeigt.</span><span class="sxs-lookup"><span data-stu-id="8b8d5-110">You define the binding the same way, as the highlighted line that contains the `<TextBlock>` element shows.</span></span>  
  
 <span data-ttu-id="8b8d5-111">In diesem speziellen Beispiel ist das Ergebnis <xref:System.Windows.Controls.TextBlock> das gleiche: `Joe`Sie haben eine mit dem Textinhalt .</span><span class="sxs-lookup"><span data-stu-id="8b8d5-111">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="8b8d5-112">Die <xref:System.Windows.Data.ObjectDataProvider> Klasse stellt jedoch Funktionen bereit, z. B. die Möglichkeit, an das Ergebnis einer Methode zu binden.</span><span class="sxs-lookup"><span data-stu-id="8b8d5-112">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="8b8d5-113">Sie können die <xref:System.Windows.Data.ObjectDataProvider> Klasse verwenden, wenn Sie die darin vorgesehene Funktionalität benötigen.</span><span class="sxs-lookup"><span data-stu-id="8b8d5-113">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="8b8d5-114">Wenn Sie jedoch an ein Objekt binden, das bereits erstellt `DataContext` wurde, müssen Sie den in-Code festlegen, wie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="8b8d5-114">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="8b8d5-115">Informationen zum Zugriff auf <xref:System.Windows.Data.XmlDataProvider> XML-Daten für die Bindung mithilfe der Klasse finden Sie unter [Binden an XML-Daten mithilfe eines XMLDataProvider und XPath-Abfragen](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span><span class="sxs-lookup"><span data-stu-id="8b8d5-115">To access XML data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="8b8d5-116">Informationen zum Zugriff auf <xref:System.Windows.Data.ObjectDataProvider> XML-Daten für die Bindung mithilfe der Klasse finden Sie unter [Binden an XDocument, XElement oder LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span><span class="sxs-lookup"><span data-stu-id="8b8d5-116">To access XML data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="8b8d5-117">Weitere Informationen zu vielen Möglichkeiten, wie Sie die Daten angeben können, an die Sie binden, finden Sie unter [Angeben der Bindungsquelle](how-to-specify-the-binding-source.md).</span><span class="sxs-lookup"><span data-stu-id="8b8d5-117">For information about many ways you can specify the data you are binding to, see [Specify the Binding Source](how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="8b8d5-118">Informationen dazu, an welche Datentypen Sie binden können oder wie Sie Ihre eigenen CLR-Objekte (Common Language Runtime) zur Bindung implementieren können, finden Sie unter [Übersicht über Bindungsquellen](binding-sources-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8b8d5-118">For information about what types of data you can bind to or how to implement your own common language runtime (CLR) objects for binding, see [Binding Sources Overview](binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b8d5-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8b8d5-119">See also</span></span>

- [<span data-ttu-id="8b8d5-120">Datenbindung sübersicht</span><span class="sxs-lookup"><span data-stu-id="8b8d5-120">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="8b8d5-121">How-to-Themen</span><span class="sxs-lookup"><span data-stu-id="8b8d5-121">How-to Topics</span></span>](data-binding-how-to-topics.md)
