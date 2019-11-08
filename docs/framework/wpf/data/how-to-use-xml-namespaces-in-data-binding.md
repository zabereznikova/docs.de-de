---
title: 'Gewusst wie: Verwenden von XML-Namespaces bei der Datenbindung'
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: f6e6e042fa5583fcf91bd15c524537490fb6670c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740574"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="612a6-102">Gewusst wie: Verwenden von XML-Namespaces bei der Datenbindung</span><span class="sxs-lookup"><span data-stu-id="612a6-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="612a6-103">Beispiel</span><span class="sxs-lookup"><span data-stu-id="612a6-103">Example</span></span>
 <span data-ttu-id="612a6-104">In diesem Beispiel wird gezeigt, wie in der XML-Bindungs Quelle angegebene Namespaces behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="612a6-104">This example shows how to handle namespaces specified in your XML binding source.</span></span>

 <span data-ttu-id="612a6-105">Wenn die XML-Daten die folgende XML-Namespace Definition haben:</span><span class="sxs-lookup"><span data-stu-id="612a6-105">If your XML data has the following XML namespace definition:</span></span>

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 <span data-ttu-id="612a6-106">Sie können das <xref:System.Windows.Data.XmlNamespaceMapping>-Element verwenden, um den Namespace einem <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>zuzuordnen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="612a6-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="612a6-107">Anschließend können Sie den <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> verwenden, um auf den XML-Namespace zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="612a6-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the XML namespace.</span></span> <span data-ttu-id="612a6-108">Der <xref:System.Windows.Controls.ListBox> in diesem Beispiel zeigt den *Titel* und *DC: Date* der einzelnen *Elemente*an.</span><span class="sxs-lookup"><span data-stu-id="612a6-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 <span data-ttu-id="612a6-109">Beachten Sie, dass die <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, die Sie angeben, nicht mit der in der XML-Quelle verwendeten identisch sein muss. Wenn das Präfix in der XML-Quelle geändert wird, funktioniert Ihre Zuordnung weiterhin.</span><span class="sxs-lookup"><span data-stu-id="612a6-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the XML source; if the prefix changes in the XML source your mapping still works.</span></span>

 <span data-ttu-id="612a6-110">In diesem speziellen Beispiel stammen die XML-Daten aus einem Webdienst, aber das <xref:System.Windows.Data.XmlNamespaceMapping>-Element funktioniert auch mit XML-Inline Daten oder XML-Daten in einer eingebetteten Datei.</span><span class="sxs-lookup"><span data-stu-id="612a6-110">In this particular example, the XML data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline XML or XML data in an embedded file.</span></span>

## <a name="see-also"></a><span data-ttu-id="612a6-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="612a6-111">See also</span></span>

- [<span data-ttu-id="612a6-112">Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen</span><span class="sxs-lookup"><span data-stu-id="612a6-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="612a6-113">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="612a6-113">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="612a6-114">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="612a6-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
