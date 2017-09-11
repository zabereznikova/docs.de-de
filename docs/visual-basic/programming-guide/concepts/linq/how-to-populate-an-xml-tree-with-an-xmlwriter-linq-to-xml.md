---
title: "Gewusst wie: Auffüllen einer XML-Struktur mit einem XmlWriter (LINQ to XML) (Visual Basic) | Microsoft-Dokumentation"
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
ms.assetid: 5792a0eb-94ee-440d-b601-58cca8c0ee0b
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
ms.openlocfilehash: af870389e34dd480e3db9a09bdffd2d3998747a1
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml-visual-basic"></a><span data-ttu-id="9c1dd-102">Gewusst wie: Auffüllen einer XML-Struktur mit einem XmlWriter (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c1dd-102">How to: Populate an XML Tree with an XmlWriter (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="9c1dd-103">Eine Möglichkeit, eine XML-Struktur aufzufüllen ist die Verwendung <xref:System.Xml.Linq.XContainer.CreateWriter%2A>zum Erstellen einer <xref:System.Xml.XmlWriter>, und Schreiben Sie dann mit dem <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.Xml.XmlWriter> </xref:System.Xml.Linq.XContainer.CreateWriter%2A></span><span class="sxs-lookup"><span data-stu-id="9c1dd-103">One way to populate an XML tree is to use <xref:System.Xml.Linq.XContainer.CreateWriter%2A> to create an <xref:System.Xml.XmlWriter>, and then write to the <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="9c1dd-104">Die XML-Struktur wird mit allen Knoten aufgefüllt, die mit dem <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> geschrieben werden</span><span class="sxs-lookup"><span data-stu-id="9c1dd-104">The XML tree is populated with all nodes that are written to the <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="9c1dd-105">Sie möchten in der Regel verwenden Sie diese Methode bei Verwendung von [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] mit einer anderen Klasse, die zum Schreiben in erwartet ein <xref:System.Xml.XmlWriter>, wie z. B. <xref:System.Xml.Xsl.XslCompiledTransform>.</xref:System.Xml.Xsl.XslCompiledTransform> </xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="9c1dd-105">You would typically use this method when you use [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] with another class that expects to write to an <xref:System.Xml.XmlWriter>, such as <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c1dd-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9c1dd-106">Example</span></span>  
 <span data-ttu-id="9c1dd-107">Eine Verwendungsmöglichkeit für <xref:System.Xml.Linq.XContainer.CreateWriter%2A>wird eine XSLT-Transformation aufrufen.</xref:System.Xml.Linq.XContainer.CreateWriter%2A></span><span class="sxs-lookup"><span data-stu-id="9c1dd-107">One possible use for <xref:System.Xml.Linq.XContainer.CreateWriter%2A> is when invoking an XSLT transformation.</span></span> <span data-ttu-id="9c1dd-108">In diesem Beispiel wird eine XML-Struktur erstellt, erstellt ein <xref:System.Xml.XmlReader>aus der XML-Struktur ein neues Dokument erstellt, und erstellt dann eine <xref:System.Xml.XmlWriter>, in das neue Dokument schreibt.</xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="9c1dd-108">This example creates an XML tree, creates an <xref:System.Xml.XmlReader> from the XML tree, creates a new document, and then creates an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="9c1dd-109">Anschließend ruft Sie die XSLT-Transformation übergeben <xref:System.Xml.XmlReader>und <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="9c1dd-109">It then invokes the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="9c1dd-110">Nach erfolgreichem Abschluss der Transformation wird die neue XML-Struktur mit den Ergebnissen der Transformation aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="9c1dd-110">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
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
  
 <span data-ttu-id="9c1dd-111">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="9c1dd-111">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9c1dd-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c1dd-112">See Also</span></span>  
 <span data-ttu-id="9c1dd-113"><xref:System.Xml.Linq.XContainer.CreateWriter%2A></xref:System.Xml.Linq.XContainer.CreateWriter%2A></span><span class="sxs-lookup"><span data-stu-id="9c1dd-113"><xref:System.Xml.Linq.XContainer.CreateWriter%2A></span></span>   
 <span data-ttu-id="9c1dd-114"><xref:System.Xml.XmlWriter></xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="9c1dd-114"><xref:System.Xml.XmlWriter></span></span>   
 <span data-ttu-id="9c1dd-115"><xref:System.Xml.Xsl.XslCompiledTransform></xref:System.Xml.Xsl.XslCompiledTransform></span><span class="sxs-lookup"><span data-stu-id="9c1dd-115"><xref:System.Xml.Xsl.XslCompiledTransform></span></span>   
<span data-ttu-id="9c1dd-116"> [Erstellen von XML-Strukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)</span><span class="sxs-lookup"><span data-stu-id="9c1dd-116"> [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)</span></span>
