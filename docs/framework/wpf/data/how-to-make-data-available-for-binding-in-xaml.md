---
title: 'Gewusst wie: Bereitstellen von Daten, um diese in XAML zu binden'
description: Entdecken Sie die verschiedenen Möglichkeiten, wie Sie Daten gemäß den Anforderungen Ihrer Anwendung in Windows Presentation Foundation (WPF) verfügbar machen können.
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: 16618ce8b19f5dd5854c4d126e7fc455f0428a28
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620793"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="8a885-103">Gewusst wie: Bereitstellen von Daten, um diese in XAML zu binden</span><span class="sxs-lookup"><span data-stu-id="8a885-103">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="8a885-104">In diesem Thema werden verschiedene Möglichkeiten erläutert, wie Sie Daten für die Bindung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] abhängig von den Anforderungen Ihrer Anwendung zur Verfügung stellen können.</span><span class="sxs-lookup"><span data-stu-id="8a885-104">This topic discusses various ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a885-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8a885-105">Example</span></span>  
 <span data-ttu-id="8a885-106">Wenn Sie über ein Common Language Runtime (CLR)-Objekt verfügen, an das Sie eine Bindung [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] herstellen möchten, können Sie das Objekt auf eine Weise für die Bindung zur Verfügung stellen, indem Sie es als Ressource definieren und ihm ein-Objekt geben `x:Key` .</span><span class="sxs-lookup"><span data-stu-id="8a885-106">If you have a common language runtime (CLR) object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="8a885-107">Im folgenden Beispiel verfügen Sie über ein- `Person` Objekt mit der Zeichen folgen Eigenschaft `PersonName` .</span><span class="sxs-lookup"><span data-stu-id="8a885-107">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="8a885-108">Das- `Person` Objekt (in der markierten Zeile, die das- `<src>` Element enthält) ist im-Namespace mit dem Namen definiert `SDKSample` .</span><span class="sxs-lookup"><span data-stu-id="8a885-108">The `Person` object (in the line shown highlighted that contains the `<src>` element) is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="8a885-109">Anschließend können Sie das <xref:System.Windows.Controls.TextBlock> Steuerelement an das-Objekt in binden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , wie die markierte Zeile, die das-Element enthält, `<TextBlock>` anzeigt.</span><span class="sxs-lookup"><span data-stu-id="8a885-109">You can then bind the <xref:System.Windows.Controls.TextBlock> control to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as the highlighted line that contains the `<TextBlock>` element shows.</span></span>
  
 <span data-ttu-id="8a885-110">Alternativ können Sie die- <xref:System.Windows.Data.ObjectDataProvider> Klasse verwenden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="8a885-110">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example:</span></span>  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 <span data-ttu-id="8a885-111">Die Bindung wird auf die gleiche Weise definiert, wie die markierte Zeile, die das-Element enthält, `<TextBlock>` anzeigt.</span><span class="sxs-lookup"><span data-stu-id="8a885-111">You define the binding the same way, as the highlighted line that contains the `<TextBlock>` element shows.</span></span>  
  
 <span data-ttu-id="8a885-112">In diesem speziellen Beispiel ist das Ergebnis identisch: Sie verfügen über eine <xref:System.Windows.Controls.TextBlock> mit dem Text Inhalt `Joe` .</span><span class="sxs-lookup"><span data-stu-id="8a885-112">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="8a885-113">Die- <xref:System.Windows.Data.ObjectDataProvider> Klasse stellt jedoch Funktionen bereit, z. b. die Möglichkeit, eine Bindung an das Ergebnis einer Methode herzustellen.</span><span class="sxs-lookup"><span data-stu-id="8a885-113">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="8a885-114">Sie können die-Klasse verwenden, <xref:System.Windows.Data.ObjectDataProvider> Wenn Sie die von ihr bereitgestellte Funktionalität benötigen.</span><span class="sxs-lookup"><span data-stu-id="8a885-114">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="8a885-115">Wenn Sie jedoch an ein Objekt binden, das bereits erstellt wurde, müssen Sie `DataContext` im Code festlegen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="8a885-115">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="8a885-116">Informationen zum Zugreifen auf XML-Daten für die Bindung mithilfe der <xref:System.Windows.Data.XmlDataProvider> -Klasse finden Sie unter [binden an XML-Daten mithilfe von XmlDataProvider-und XPath-Abfragen](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span><span class="sxs-lookup"><span data-stu-id="8a885-116">To access XML data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="8a885-117">Informationen zum Zugreifen auf XML-Daten für die Bindung mithilfe der- <xref:System.Windows.Data.ObjectDataProvider> Klasse finden Sie unter [binden an XDocument, XElement oder LINQ für XML Query Ergebnisse](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span><span class="sxs-lookup"><span data-stu-id="8a885-117">To access XML data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="8a885-118">Informationen zu vielen Möglichkeiten, wie Sie die Daten angeben können, an die die Bindung erfolgen soll, finden Sie unter [angeben der Bindungs Quelle](how-to-specify-the-binding-source.md).</span><span class="sxs-lookup"><span data-stu-id="8a885-118">For information about many ways you can specify the data you are binding to, see [Specify the Binding Source](how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="8a885-119">Informationen zu den Datentypen, an die Sie binden können, oder zum Implementieren eigener Common Language Runtime (CLR)-Objekte für die Bindung finden Sie unter [Übersicht über Bindungs Quellen](binding-sources-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8a885-119">For information about what types of data you can bind to or how to implement your own common language runtime (CLR) objects for binding, see [Binding Sources Overview](binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a885-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8a885-120">See also</span></span>

- [<span data-ttu-id="8a885-121">Übersicht über die Datenbindung</span><span class="sxs-lookup"><span data-stu-id="8a885-121">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="8a885-122">Artikel zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="8a885-122">How-to Topics</span></span>](data-binding-how-to-topics.md)
