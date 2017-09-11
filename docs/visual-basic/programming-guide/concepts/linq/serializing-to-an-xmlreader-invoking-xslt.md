---
title: Serialisieren in einen XmlReader (XSLT aufrufen) (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 8b64f95a-e8f6-40f7-99f9-a8002c63af96
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7e1af87fceb9f3f7eae6af6f917037ba80908827
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="serializing-to-an-xmlreader-invoking-xslt-visual-basic"></a><span data-ttu-id="38e4c-102">Serialisieren in einen XmlReader (XSLT aufrufen) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38e4c-102">Serializing to an XmlReader (Invoking XSLT) (Visual Basic)</span></span>
<span data-ttu-id="38e4c-103">Bei Verwendung der <xref:System.Xml?displayProperty=fullName>interoperabilitätsmöglichkeiten [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], können Sie <xref:System.Xml.Linq.XNode.CreateReader%2A>zum Erstellen einer <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> </xref:System.Xml.Linq.XNode.CreateReader%2A> </xref:System.Xml?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="38e4c-103">When you use the <xref:System.Xml?displayProperty=fullName> interoperability capabilities of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], you can use <xref:System.Xml.Linq.XNode.CreateReader%2A> to create an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="38e4c-104">Das Modul, das von diesem liest <xref:System.Xml.XmlReader>liest die Knoten aus der XML-Struktur und verarbeitet sie entsprechend.</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="38e4c-104">The module that reads from this <xref:System.Xml.XmlReader> reads the nodes from the XML tree and processes them accordingly.</span></span>  
  
## <a name="invoking-an-xslt-transformation"></a><span data-ttu-id="38e4c-105">Aufrufen einer XSLT-Transformation</span><span class="sxs-lookup"><span data-stu-id="38e4c-105">Invoking an XSLT Transformation</span></span>  
 <span data-ttu-id="38e4c-106">Diese Methode kann z. B. zum Aufrufen einer XSLT-Transformation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="38e4c-106">One possible use for this method is when invoking an XSLT transformation.</span></span> <span data-ttu-id="38e4c-107">Sie können eine XML-Struktur erstellen, erstellen Sie eine <xref:System.Xml.XmlReader>aus der XML-Struktur ein neues Dokument erstellen, und erstellen Sie dann eine <xref:System.Xml.XmlWriter>zum Schreiben in das neue Dokument.</xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="38e4c-107">You can create an XML tree, create an <xref:System.Xml.XmlReader> from the XML tree, create a new document, and then create an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="38e4c-108">Anschließend können Sie die XSLT-Transformation übergeben <xref:System.Xml.XmlReader>und <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="38e4c-108">Then, you can invoke the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="38e4c-109">Nach erfolgreichem Abschluss der Transformation wird die neue XML-Struktur mit den Ergebnissen der Transformation aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="38e4c-109">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
```vb  
Dim xslMarkup As XDocument = _  
    <?xml version='1.0'?>  
    <xsl:stylesheet xmlns:xsl='http://www.w3.org/1999/XSL/Transform' version='1.0'>  
        <xsl:template match='/Parent'>  
            <Root>  
                <C1>  
                    <xsl:value-of select='Child1'/>  
                </C1>  
                <C2>  
                    <xsl:value-of select='Child2'/>  
                </C2>  
            </Root>  
        </xsl:template>  
    </xsl:stylesheet>  
  
Dim xmlTree As XDocument = _  
    <?xml version='1.0'?>  
    <Parent>  
        <Child1>Child1 data</Child1>  
        <Child2>Child2 data</Child2>  
    </Parent>  
  
Dim newTree As XDocument = New XDocument()  
Using writer As XmlWriter = newTree.CreateWriter()  
    ' Load the style sheet.  
    Dim xslt As XslCompiledTransform = New XslCompiledTransform()  
    xslt.Load(xslMarkup.CreateReader())  
  
    ' Execute the transformation and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer)  
End Using  
  
Console.WriteLine(newTree)  
```  
  
 <span data-ttu-id="38e4c-110">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="38e4c-110">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="38e4c-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38e4c-111">See Also</span></span>  
 [<span data-ttu-id="38e4c-112">Serialisieren von XML-Strukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38e4c-112">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
