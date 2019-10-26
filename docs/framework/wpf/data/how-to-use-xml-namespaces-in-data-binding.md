---
title: 'Gewusst wie: Verwenden von XML-Namespaces bei der Datenbindung'
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: 9d8ddc5445bac28c68cd6cc99acf3313613a8c7f
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2019
ms.locfileid: "72919669"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="2b076-102">Gewusst wie: Verwenden von XML-Namespaces bei der Datenbindung</span><span class="sxs-lookup"><span data-stu-id="2b076-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="2b076-103">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2b076-103">Example</span></span>
 <span data-ttu-id="2b076-104">Dieses Beispiel zeigt, wie in der [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]-Bindungsquelle angegebene Namespaces behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="2b076-104">This example shows how to handle namespaces specified in your [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] binding source.</span></span>

 <span data-ttu-id="2b076-105">Wenn Ihre [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Daten die folgende [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Namespace-Definition haben:</span><span class="sxs-lookup"><span data-stu-id="2b076-105">If your [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data has the following [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace definition:</span></span>

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 <span data-ttu-id="2b076-106">Sie können das <xref:System.Windows.Data.XmlNamespaceMapping>-Element verwenden, um den Namespace einem <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>zuzuordnen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="2b076-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="2b076-107">Anschließend können Sie den <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> verwenden, um auf den [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Namespace zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="2b076-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace.</span></span> <span data-ttu-id="2b076-108">Der <xref:System.Windows.Controls.ListBox> in diesem Beispiel zeigt den *Titel* und *DC: Date* der einzelnen *Elemente*an.</span><span class="sxs-lookup"><span data-stu-id="2b076-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 <span data-ttu-id="2b076-109">Beachten Sie, dass der <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, den Sie angeben, nicht mit dem in der [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Quelle verwendeten identisch sein muss. Wenn das Präfix in der [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Quelle geändert wird, funktioniert Ihre Zuordnung weiterhin.</span><span class="sxs-lookup"><span data-stu-id="2b076-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source; if the prefix changes in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source your mapping still works.</span></span>

 <span data-ttu-id="2b076-110">In diesem Beispiel stammen die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten von einem Webdienst, aber das <xref:System.Windows.Data.XmlNamespaceMapping> Element funktioniert auch mit Inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] oder [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten in einer eingebetteten Datei.</span><span class="sxs-lookup"><span data-stu-id="2b076-110">In this particular example, the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] or [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data in an embedded file.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b076-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b076-111">See also</span></span>

- [<span data-ttu-id="2b076-112">Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen</span><span class="sxs-lookup"><span data-stu-id="2b076-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="2b076-113">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="2b076-113">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="2b076-114">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="2b076-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
