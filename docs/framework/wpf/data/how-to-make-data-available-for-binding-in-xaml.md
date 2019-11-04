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
ms.openlocfilehash: 2bfd9809a6ad487a7e706366dc6bce8fe951c940
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459761"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="b2eac-102">Gewusst wie: Bereitstellen von Daten, um diese in XAML zu binden</span><span class="sxs-lookup"><span data-stu-id="b2eac-102">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="b2eac-103">In diesem Thema werden verschiedene Möglichkeiten erläutert, wie Sie Daten in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]für die Bindung zur Verfügung stellen können, je nach den Anforderungen Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b2eac-103">This topic discusses various ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2eac-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b2eac-104">Example</span></span>  
 <span data-ttu-id="b2eac-105">Wenn Sie über ein Common Language Runtime (CLR)-Objekt verfügen, an das Sie [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]binden möchten, können Sie das Objekt auf eine Weise für die Bindung zur Verfügung stellen, indem Sie es als Ressource definieren und ihm einen `x:Key`bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b2eac-105">If you have a common language runtime (CLR) object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="b2eac-106">Im folgenden Beispiel verfügen Sie über ein `Person`-Objekt mit einer Zeichen folgen Eigenschaft namens `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="b2eac-106">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="b2eac-107">Das `Person`-Objekt (in der markierten Zeile, das das `<src>`-Element enthält) ist im Namespace mit dem Namen `SDKSample`definiert.</span><span class="sxs-lookup"><span data-stu-id="b2eac-107">The `Person` object (in the line shown highlighted that contains the `<src>` element) is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="b2eac-108">Anschließend können Sie das <xref:System.Windows.Controls.TextBlock>-Steuerelement an das-Objekt in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]binden, wie die markierte Zeile, die das `<TextBlock>`-Element enthält, anzeigt.</span><span class="sxs-lookup"><span data-stu-id="b2eac-108">You can then bind the <xref:System.Windows.Controls.TextBlock> control to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as the highlighted line that contains the `<TextBlock>` element shows.</span></span> 
  
 <span data-ttu-id="b2eac-109">Alternativ können Sie die <xref:System.Windows.Data.ObjectDataProvider>-Klasse verwenden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="b2eac-109">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example:</span></span>  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 <span data-ttu-id="b2eac-110">Die Bindung wird auf die gleiche Weise definiert, wie die markierte Zeile, die das `<TextBlock>`-Element enthält.</span><span class="sxs-lookup"><span data-stu-id="b2eac-110">You define the binding the same way, as the highlighted line that contains the `<TextBlock>` element shows.</span></span>  
  
 <span data-ttu-id="b2eac-111">In diesem speziellen Beispiel ist das Ergebnis identisch: Sie verfügen über eine <xref:System.Windows.Controls.TextBlock> mit dem Text Inhalt `Joe`.</span><span class="sxs-lookup"><span data-stu-id="b2eac-111">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="b2eac-112">Die <xref:System.Windows.Data.ObjectDataProvider>-Klasse bietet jedoch Funktionen, wie z. b. die Möglichkeit, eine Bindung an das Ergebnis einer Methode herzustellen.</span><span class="sxs-lookup"><span data-stu-id="b2eac-112">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="b2eac-113">Sie können die <xref:System.Windows.Data.ObjectDataProvider>-Klasse verwenden, wenn Sie die von ihr bereitgestellte Funktionalität benötigen.</span><span class="sxs-lookup"><span data-stu-id="b2eac-113">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="b2eac-114">Wenn Sie jedoch an ein Objekt binden, das bereits erstellt wurde, müssen Sie die `DataContext` im Code festlegen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b2eac-114">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="b2eac-115">Informationen zum Zugreifen auf [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten für die Bindung mithilfe der <xref:System.Windows.Data.XmlDataProvider>-Klasse finden Sie unter [binden an XML-Daten mithilfe von XmlDataProvider und XPath-Abfragen](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span><span class="sxs-lookup"><span data-stu-id="b2eac-115">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="b2eac-116">Informationen zum Zugreifen auf [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten für die Bindung mithilfe der <xref:System.Windows.Data.ObjectDataProvider>-Klasse finden Sie unter [binden an XDocument, XElement oder LINQ für XML Query Ergebnisse](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span><span class="sxs-lookup"><span data-stu-id="b2eac-116">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="b2eac-117">Informationen zu vielen Möglichkeiten, wie Sie die Daten angeben können, an die die Bindung erfolgen soll, finden Sie unter [angeben der Bindungs Quelle](how-to-specify-the-binding-source.md).</span><span class="sxs-lookup"><span data-stu-id="b2eac-117">For information about many ways you can specify the data you are binding to, see [Specify the Binding Source](how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="b2eac-118">Informationen zu den Datentypen, an die Sie binden können, oder zum Implementieren eigener Common Language Runtime (CLR)-Objekte für die Bindung finden Sie unter [Übersicht über Bindungs Quellen](binding-sources-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b2eac-118">For information about what types of data you can bind to or how to implement your own common language runtime (CLR) objects for binding, see [Binding Sources Overview](binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2eac-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2eac-119">See also</span></span>

- [<span data-ttu-id="b2eac-120">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="b2eac-120">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="b2eac-121">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="b2eac-121">How-to Topics</span></span>](data-binding-how-to-topics.md)
