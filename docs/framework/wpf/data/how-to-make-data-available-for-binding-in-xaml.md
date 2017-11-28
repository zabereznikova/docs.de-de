---
title: 'Gewusst wie: Bereitstellen von Daten, um diese in XAML zu binden'
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
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d734a7f17f8843ff284ac0854ac41d4a5b9f5584
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="23acd-102">Gewusst wie: Bereitstellen von Daten, um diese in XAML zu binden</span><span class="sxs-lookup"><span data-stu-id="23acd-102">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="23acd-103">In diesem Artikel werden die verschiedenen Möglichkeiten können Sie Daten verfügbar machen für die Bindung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], abhängig von den Anforderungen Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="23acd-103">This topic discusses the different ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23acd-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="23acd-104">Example</span></span>  
 <span data-ttu-id="23acd-105">Ist eine [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Objekt aus binden möchten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], eine Möglichkeit, Sie können das Objekt verfügbar machen, für die Bindung bezieht sich auf die als Ressource zu definieren, und weisen Sie ihm eine `x:Key`.</span><span class="sxs-lookup"><span data-stu-id="23acd-105">If you have a [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="23acd-106">Im folgenden Beispiel haben Sie eine `Person` Objekt mit der eine Zeichenfolgeneigenschaft, die mit dem Namen `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="23acd-106">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="23acd-107">Die `Person` Objekt ist im Namespace namens definiert `SDKSample`.</span><span class="sxs-lookup"><span data-stu-id="23acd-107">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#instantiation)]  
[!code-xaml[SimpleBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#2)]  
  
 <span data-ttu-id="23acd-108">Anschließend können Sie auf das Objekt im binden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="23acd-108">You can then bind to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as shown in the following example.</span></span>  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 <span data-ttu-id="23acd-109">Alternativ können Sie die <xref:System.Windows.Data.ObjectDataProvider> -Klasse, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="23acd-109">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example.</span></span>  
  
 [!code-xaml[SimpleBinding#ODPCP](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml#odpcp)]  
  
 <span data-ttu-id="23acd-110">Sie definieren die Bindung die gleiche Weise:</span><span class="sxs-lookup"><span data-stu-id="23acd-110">You define the binding the same way:</span></span>  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 <span data-ttu-id="23acd-111">In diesem speziellen Beispiel ist das Ergebnis identisch: Sie haben eine <xref:System.Windows.Controls.TextBlock> mit dem Textinhalt `Joe`.</span><span class="sxs-lookup"><span data-stu-id="23acd-111">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="23acd-112">Allerdings die <xref:System.Windows.Data.ObjectDataProvider> -Klasse bietet eine Funktionalität, z. B. die Fähigkeit, auf das Ergebnis einer Methode zu binden.</span><span class="sxs-lookup"><span data-stu-id="23acd-112">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="23acd-113">Sie können auch mithilfe der <xref:System.Windows.Data.ObjectDataProvider> Klasse, wenn Sie die Funktionalität benötigen.</span><span class="sxs-lookup"><span data-stu-id="23acd-113">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="23acd-114">Jedoch wenn Sie auf ein Objekt binden, der bereits erstellt wurde, müssen Sie legen die `DataContext` im Code, wie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="23acd-114">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="23acd-115">Für den Zugriff auf [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten für die Bindung unter Verwendung der <xref:System.Windows.Data.XmlDataProvider> Klasse, finden Sie unter [Binden mit XML-Daten mithilfe einer XMLDataProvider und XPath-Abfragen](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span><span class="sxs-lookup"><span data-stu-id="23acd-115">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="23acd-116">Für den Zugriff auf [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten für die Bindung unter Verwendung der <xref:System.Windows.Data.ObjectDataProvider> Klasse, finden Sie unter [binden, "XDocument" oder "XElement" mit LINQ für XML-Abfrageergebnissen](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span><span class="sxs-lookup"><span data-stu-id="23acd-116">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="23acd-117">Informationen über die verschiedenen Methoden können Sie angeben, die Daten, die Sie möchten binden, finden Sie unter [geben die Bindungsquelle](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md).</span><span class="sxs-lookup"><span data-stu-id="23acd-117">For information about the different ways you can specify the data you are binding to, see [Specify the Binding Source](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="23acd-118">Informationen zum welche Arten von Daten an Sie gebunden werden können, oder eine eigene Implementierung [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Objekte für die Bindung, finden Sie unter [Übersicht über Bindungsquellen](../../../../docs/framework/wpf/data/binding-sources-overview.md).</span><span class="sxs-lookup"><span data-stu-id="23acd-118">For information about what types of data you can bind to or how to implement your own [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] objects for binding, see [Binding Sources Overview](../../../../docs/framework/wpf/data/binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23acd-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23acd-119">See Also</span></span>  
 [<span data-ttu-id="23acd-120">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="23acd-120">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="23acd-121">Themen zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="23acd-121">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
