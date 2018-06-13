---
title: 'Gewusst wie: Verwenden von XML-Namespaces bei der Datenbindung'
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: 483b59bb7cea25617c832b96690f742b8b64b3e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556899"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="b9599-102">Gewusst wie: Verwenden von XML-Namespaces bei der Datenbindung</span><span class="sxs-lookup"><span data-stu-id="b9599-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="b9599-103">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9599-103">Example</span></span>  
 <span data-ttu-id="b9599-104">Dieses Beispiel zeigt, wie in der [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]-Bindungsquelle angegebene Namespaces behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="b9599-104">This example shows how to handle namespaces specified in your [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] binding source.</span></span>  
  
 <span data-ttu-id="b9599-105">Wenn Ihre [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Daten die folgende [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Namespace-Definition haben:</span><span class="sxs-lookup"><span data-stu-id="b9599-105">If your [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data has the following [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace definition:</span></span>  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 <span data-ttu-id="b9599-106">Können Sie die <xref:System.Windows.Data.XmlNamespaceMapping> Element zuordnen den Namespace, der eine <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, wie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="b9599-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="b9599-107">Anschließend können Sie die <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> zum Verweisen auf die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Namespace.</span><span class="sxs-lookup"><span data-stu-id="b9599-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace.</span></span> <span data-ttu-id="b9599-108">Die <xref:System.Windows.Controls.ListBox> in diesem Beispiel zeigt die *Titel* und *DC: Date* jedes *Element*.</span><span class="sxs-lookup"><span data-stu-id="b9599-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>  
  
 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]  
  
 <span data-ttu-id="b9599-109">Beachten Sie, dass die <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> Sie angeben, müssen nicht übereinstimmen verwendet der [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Quelle; Wenn das Präfix in geändert wird. die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Quelle, die die Zuordnung weiterhin funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b9599-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source; if the prefix changes in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source your mapping still works.</span></span>  
  
 <span data-ttu-id="b9599-110">In diesem speziellen Beispiel der [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten stammen aus einem Webdienst, aber die <xref:System.Windows.Data.XmlNamespaceMapping> Element funktioniert auch mit Inline- [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] oder [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten in einer eingebetteten Datei.</span><span class="sxs-lookup"><span data-stu-id="b9599-110">In this particular example, the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] or [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data in an embedded file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9599-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9599-111">See Also</span></span>  
 [<span data-ttu-id="b9599-112">Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen</span><span class="sxs-lookup"><span data-stu-id="b9599-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [<span data-ttu-id="b9599-113">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="b9599-113">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="b9599-114">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="b9599-114">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
