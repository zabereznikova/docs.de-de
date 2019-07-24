---
title: 'Vorgehensweise: Bereitstellen von Daten für die Bindung in XAML'
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: 3487a160cc49ab6b779a20157668915c2da33900
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401490"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="b998b-102">Vorgehensweise: Bereitstellen von Daten für die Bindung in XAML</span><span class="sxs-lookup"><span data-stu-id="b998b-102">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="b998b-103">In diesem Thema werden verschiedene Möglichkeiten erläutert, wie Sie Daten für die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]Bindung in abhängig von den Anforderungen Ihrer Anwendung zur Verfügung stellen können.</span><span class="sxs-lookup"><span data-stu-id="b998b-103">This topic discusses various ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b998b-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b998b-104">Example</span></span>  
 <span data-ttu-id="b998b-105">Wenn Sie über ein Common Language Runtime (CLR)-Objekt verfügen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], an das Sie eine Bindung herstellen möchten, können Sie das Objekt auf eine Weise für die Bindung zur Verfügung stellen, indem Sie es als Ressource definieren und ihm ein `x:Key`-Objekt geben.</span><span class="sxs-lookup"><span data-stu-id="b998b-105">If you have a common language runtime (CLR) object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="b998b-106">Im folgenden Beispiel verfügen Sie über ein `Person` -Objekt mit der Zeichen folgen `PersonName`Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b998b-106">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="b998b-107">Das `Person` -Objekt (in der markierten Zeile, die das `<src>` -Element enthält) ist im-Namespace `SDKSample`mit dem Namen definiert.</span><span class="sxs-lookup"><span data-stu-id="b998b-107">The `Person` object (in the line shown highlighted that contains the `<src>` element) is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="b998b-108">Anschließend können Sie das <xref:System.Windows.Controls.TextBlock> Steuerelement an das-Objekt in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]binden, wie die markierte Zeile, `<TextBlock>` die das-Element enthält, anzeigt.</span><span class="sxs-lookup"><span data-stu-id="b998b-108">You can then bind the <xref:System.Windows.Controls.TextBlock> control to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as the highlighted line that contains the `<TextBlock>` element shows.</span></span> 
  
 <span data-ttu-id="b998b-109">Alternativ können Sie die <xref:System.Windows.Data.ObjectDataProvider> -Klasse verwenden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="b998b-109">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example:</span></span>  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 <span data-ttu-id="b998b-110">Die Bindung wird auf die gleiche Weise definiert, wie die markierte Zeile, die `<TextBlock>` das-Element enthält, anzeigt.</span><span class="sxs-lookup"><span data-stu-id="b998b-110">You define the binding the same way, as the highlighted line that contains the `<TextBlock>` element shows.</span></span>  
  
 <span data-ttu-id="b998b-111">In diesem speziellen Beispiel ist das Ergebnis identisch: Sie verfügen über eine <xref:System.Windows.Controls.TextBlock> mit dem Text Inhalt. `Joe`</span><span class="sxs-lookup"><span data-stu-id="b998b-111">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="b998b-112">Die <xref:System.Windows.Data.ObjectDataProvider> -Klasse stellt jedoch Funktionen bereit, z. b. die Möglichkeit, eine Bindung an das Ergebnis einer Methode herzustellen.</span><span class="sxs-lookup"><span data-stu-id="b998b-112">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="b998b-113">Sie können die <xref:System.Windows.Data.ObjectDataProvider> -Klasse verwenden, wenn Sie die von ihr bereitgestellte Funktionalität benötigen.</span><span class="sxs-lookup"><span data-stu-id="b998b-113">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="b998b-114">Wenn Sie jedoch an ein Objekt binden, das bereits erstellt wurde, müssen Sie `DataContext` im Code festlegen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b998b-114">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="b998b-115">Informationen zum [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] zugreifen auf Daten für die <xref:System.Windows.Data.XmlDataProvider> Bindung mithilfe der-Klasse finden Sie unter [binden an XML-Daten mithilfe von XmlDataProvider-und XPath-Abfragen](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span><span class="sxs-lookup"><span data-stu-id="b998b-115">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="b998b-116">Informationen zum [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] zugreifen auf Daten für die <xref:System.Windows.Data.ObjectDataProvider> Bindung mithilfe der-Klasse finden Sie unter [binden an XDocument, XElement oder LINQ für XML Query Ergebnisse](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span><span class="sxs-lookup"><span data-stu-id="b998b-116">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="b998b-117">Informationen zu vielen Möglichkeiten, wie Sie die Daten angeben können, an die die Bindung erfolgen soll, finden Sie unter [angeben der Bindungs Quelle](how-to-specify-the-binding-source.md).</span><span class="sxs-lookup"><span data-stu-id="b998b-117">For information about many ways you can specify the data you are binding to, see [Specify the Binding Source](how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="b998b-118">Informationen zu den Datentypen, an die Sie binden können, oder zum Implementieren eigener Common Language Runtime (CLR)-Objekte für die Bindung finden Sie unter [Übersicht über Bindungs Quellen](binding-sources-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b998b-118">For information about what types of data you can bind to or how to implement your own common language runtime (CLR) objects for binding, see [Binding Sources Overview](binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b998b-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b998b-119">See also</span></span>

- [<span data-ttu-id="b998b-120">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="b998b-120">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="b998b-121">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="b998b-121">How-to Topics</span></span>](data-binding-how-to-topics.md)
