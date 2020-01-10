---
title: 'Vorgehensweise: Transformieren eines Knotenfragments'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 73a6c582-b9d7-4fa7-9a05-6d931e1f3de8
ms.openlocfilehash: 56e9ef6031a5736acfa066ed6c068f954bd5af8d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710816"
---
# <a name="how-to-transform-a-node-fragment"></a>Vorgehensweise: Transformieren eines Knotenfragments
Wenn Sie in einem <xref:System.Xml.XmlDocument>-Objekt oder einem <xref:System.Xml.XPath.XPathDocument>-Objekt enthaltene Daten transformieren, gelten die XSLT-Transformationen für das vollständige Dokument. Wenn Sie einen anderen Knoten als den Stammknoten des Dokuments übergeben, wird dadurch nicht verhindert, dass im Transformationsprozess auf alle Knoten im geladenen Dokument zugegriffen wird. Zum Transformieren eines Knotenfragments müssen Sie ein separates Objekt erstellen, das nur das Knotenfragment enthält, und dieses Objekt an die <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>-Methode übergeben.  
  
## <a name="procedures"></a>Verfahren  
  
#### <a name="to-transform-a-node-fragment"></a>So transformieren Sie ein Knotenfragment  
  
1. Erstellen Sie ein Objekt, das das Quelldokument enthält.  
  
2. Suchen Sie das Knotenfragment, das Sie transformieren möchten.  
  
3. Erstellen Sie ein separates Objekt, das nur das Knotenfragment enthält.  
  
4. Übergeben Sie das Knotenfragment an die <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>-Methode.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Knotenfragment transformiert und die Ergebnisse werden auf der Konsole ausgegeben.  
  
 [!code-csharp[XSLT_NodeFrag#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_NodeFrag/CS/xslt_frag.cs#1)]
 [!code-vb[XSLT_NodeFrag#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_NodeFrag/VB/xslt_frag.vb#1)]  
  
### <a name="input"></a>Input  
  
##### <a name="booksxml"></a>books.xml  
 [!code-xml[XML_Core_Files#1](../../../../samples/snippets/xml/VS_Snippets_Data/XML_Core_Files/XML/books.xml#1)]  
  
##### <a name="singlexsl"></a>single.xsl  
 [!code-xml[XSLT_NodeFrag#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_NodeFrag/XML/single.xsl#2)]  
  
### <a name="output"></a>Ausgabe  
 Der Buchtitel lautet "Ein sehr vertrauenswürdiger Herr".  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden der XslCompiledTransform-Klasse](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)
