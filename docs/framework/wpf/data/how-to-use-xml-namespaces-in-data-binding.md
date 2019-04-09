---
title: 'Vorgehensweise: Verwenden von XML-Namespaces bei der Datenbindung'
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: 38bf6e8f88b0325193d49148cd6c33031f7b0a6d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149993"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="0807c-102">Vorgehensweise: Verwenden von XML-Namespaces bei der Datenbindung</span><span class="sxs-lookup"><span data-stu-id="0807c-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="0807c-103">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0807c-103">Example</span></span>  
 <span data-ttu-id="0807c-104">Dieses Beispiel zeigt, wie in der [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]-Bindungsquelle angegebene Namespaces behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="0807c-104">This example shows how to handle namespaces specified in your [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] binding source.</span></span>  
  
 <span data-ttu-id="0807c-105">Wenn Ihre [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Daten die folgende [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Namespace-Definition haben:</span><span class="sxs-lookup"><span data-stu-id="0807c-105">If your [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data has the following [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace definition:</span></span>  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 <span data-ttu-id="0807c-106">Können Sie die <xref:System.Windows.Data.XmlNamespaceMapping> -Element zuordnen den Namespace, der eine <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, wie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="0807c-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="0807c-107">Anschließend können Sie die <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> zum Verweisen auf die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Namespace.</span><span class="sxs-lookup"><span data-stu-id="0807c-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace.</span></span> <span data-ttu-id="0807c-108">Die <xref:System.Windows.Controls.ListBox> in diesem Beispiel zeigt die *Titel* und *DC: Date* aller *Element*.</span><span class="sxs-lookup"><span data-stu-id="0807c-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>  
  
 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]  
  
 <span data-ttu-id="0807c-109">Beachten Sie, dass die <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> Sie angeben, muss keine der im verwendeten übereinstimmen der [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Datenquellenobjekt; Wenn das Präfix in ändert sich die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Quelle, die die Zuordnung weiterhin funktioniert.</span><span class="sxs-lookup"><span data-stu-id="0807c-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source; if the prefix changes in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source your mapping still works.</span></span>  
  
 <span data-ttu-id="0807c-110">In diesem Beispiel ist die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten stammen aus einem Webdienst, aber die <xref:System.Windows.Data.XmlNamespaceMapping> Element funktioniert auch mit Inline- [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] oder [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten in einer eingebetteten Datei.</span><span class="sxs-lookup"><span data-stu-id="0807c-110">In this particular example, the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] or [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data in an embedded file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0807c-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0807c-111">See also</span></span>

- [<span data-ttu-id="0807c-112">Binden an XML-Daten mithilfe der XMLDataProvider-Klasse und mithilfe von XPath-Abfragen</span><span class="sxs-lookup"><span data-stu-id="0807c-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="0807c-113">Übersicht über die Datenbindung</span><span class="sxs-lookup"><span data-stu-id="0807c-113">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="0807c-114">Gewusst wie-Themen</span><span class="sxs-lookup"><span data-stu-id="0807c-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
