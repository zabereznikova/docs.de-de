---
title: 'Vorgehensweise: Transformieren eines Knotenfragments'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 73a6c582-b9d7-4fa7-9a05-6d931e1f3de8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eb258b61664e1fdbf6604afdf69074c48cf5bda4
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44187610"
---
# <a name="how-to-transform-a-node-fragment"></a><span data-ttu-id="540df-102">Vorgehensweise: Transformieren eines Knotenfragments</span><span class="sxs-lookup"><span data-stu-id="540df-102">How to: Transform a Node Fragment</span></span>
<span data-ttu-id="540df-103">Wenn Sie in einem <xref:System.Xml.XmlDocument>-Objekt oder einem <xref:System.Xml.XPath.XPathDocument>-Objekt enthaltene Daten transformieren, gelten die XSLT-Transformationen für das vollständige Dokument.</span><span class="sxs-lookup"><span data-stu-id="540df-103">When you transform data contained in an <xref:System.Xml.XmlDocument> or <xref:System.Xml.XPath.XPathDocument> object the XSLT transformations apply to a document as a whole.</span></span> <span data-ttu-id="540df-104">Wenn Sie einen anderen Knoten als den Stammknoten des Dokuments übergeben, wird dadurch nicht verhindert, dass im Transformationsprozess auf alle Knoten im geladenen Dokument zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="540df-104">In other words, if you pass in a node other than the document root node, this does not prevent the transformation process from accessing all nodes in the loaded document.</span></span> <span data-ttu-id="540df-105">Zum Transformieren eines Knotenfragments müssen Sie ein separates Objekt erstellen, das nur das Knotenfragment enthält, und dieses Objekt an die <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>-Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="540df-105">To transform a node fragment, you must create a separate object containing just the node fragment, and pass that object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="540df-106">Verfahren</span><span class="sxs-lookup"><span data-stu-id="540df-106">Procedures</span></span>  
  
#### <a name="to-transform-a-node-fragment"></a><span data-ttu-id="540df-107">So transformieren Sie ein Knotenfragment</span><span class="sxs-lookup"><span data-stu-id="540df-107">To transform a node fragment</span></span>  
  
1.  <span data-ttu-id="540df-108">Erstellen Sie ein Objekt, das das Quelldokument enthält.</span><span class="sxs-lookup"><span data-stu-id="540df-108">Create an object containing the source document.</span></span>  
  
2.  <span data-ttu-id="540df-109">Suchen Sie das Knotenfragment, das Sie transformieren möchten.</span><span class="sxs-lookup"><span data-stu-id="540df-109">Locate the node fragment you wish to transform.</span></span>  
  
3.  <span data-ttu-id="540df-110">Erstellen Sie ein separates Objekt, das nur das Knotenfragment enthält.</span><span class="sxs-lookup"><span data-stu-id="540df-110">Create separate object with just the node fragment.</span></span>  
  
4.  <span data-ttu-id="540df-111">Übergeben Sie das Knotenfragment an die <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="540df-111">Pass the node fragment to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="540df-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="540df-112">Example</span></span>  
 <span data-ttu-id="540df-113">Im folgenden Beispiel wird ein Knotenfragment transformiert und die Ergebnisse werden auf der Konsole ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="540df-113">The following example transforms a node fragment and outputs the results to the console.</span></span>  
  
 [!code-csharp[XSLT_NodeFrag#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_NodeFrag/CS/xslt_frag.cs#1)]
 [!code-vb[XSLT_NodeFrag#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_NodeFrag/VB/xslt_frag.vb#1)]  
  
### <a name="input"></a><span data-ttu-id="540df-114">Eingabe</span><span class="sxs-lookup"><span data-stu-id="540df-114">Input</span></span>  
  
##### <a name="booksxml"></a><span data-ttu-id="540df-115">books.xml</span><span class="sxs-lookup"><span data-stu-id="540df-115">books.xml</span></span>  
 [!code-xml[XML_Core_Files#1](../../../../samples/snippets/xml/VS_Snippets_Data/XML_Core_Files/XML/books.xml#1)]  
  
##### <a name="singlexsl"></a><span data-ttu-id="540df-116">single.xsl</span><span class="sxs-lookup"><span data-stu-id="540df-116">single.xsl</span></span>  
 [!code-xml[XSLT_NodeFrag#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_NodeFrag/XML/single.xsl#2)]  
  
### <a name="output"></a><span data-ttu-id="540df-117">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="540df-117">Output</span></span>  
 <span data-ttu-id="540df-118">Der Buchtitel lautet "Ein sehr vertrauenswürdiger Herr".</span><span class="sxs-lookup"><span data-stu-id="540df-118">Book title is The Confidence Man.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="540df-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="540df-119">See also</span></span>

- [<span data-ttu-id="540df-120">Verwenden der XslCompiledTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="540df-120">Using the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)
