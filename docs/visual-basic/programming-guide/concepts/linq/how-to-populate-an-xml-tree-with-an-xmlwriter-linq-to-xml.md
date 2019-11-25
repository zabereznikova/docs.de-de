---
title: 'Gewusst wie: Füllen einer XML-Struktur mit einem XmlWriter (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 5792a0eb-94ee-440d-b601-58cca8c0ee0b
ms.openlocfilehash: ec44f6e21453a1333f842030bae0c4f80dedb9c3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333770"
---
# <a name="how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml-visual-basic"></a><span data-ttu-id="d5c3a-102">How to: Populate an XML Tree with an XmlWriter (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5c3a-102">How to: Populate an XML Tree with an XmlWriter (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="d5c3a-103">Eine Möglichkeit, eine XML-Struktur aufzufüllen, besteht darin, mit <xref:System.Xml.Linq.XContainer.CreateWriter%2A> einen <xref:System.Xml.XmlWriter> zu erstellen und dann in den <xref:System.Xml.XmlWriter> zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="d5c3a-103">One way to populate an XML tree is to use <xref:System.Xml.Linq.XContainer.CreateWriter%2A> to create an <xref:System.Xml.XmlWriter>, and then write to the <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="d5c3a-104">Die XML-Struktur wird mit allen Knoten aufgefüllt, die in den <xref:System.Xml.XmlWriter> geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="d5c3a-104">The XML tree is populated with all nodes that are written to the <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="d5c3a-105">Diese Methode kommt in der Regel zum Einsatz, wenn Sie [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] mit einer anderen Klasse verwenden, die davon ausgeht, dass sie in einen <xref:System.Xml.XmlWriter>, z.B. <xref:System.Xml.Xsl.XslCompiledTransform>, schreibt.</span><span class="sxs-lookup"><span data-stu-id="d5c3a-105">You would typically use this method when you use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] with another class that expects to write to an <xref:System.Xml.XmlWriter>, such as <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5c3a-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d5c3a-106">Example</span></span>  
 <span data-ttu-id="d5c3a-107"><xref:System.Xml.Linq.XContainer.CreateWriter%2A> kann beispielsweise verwendet werden, wenn eine XSLT-Transformation aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="d5c3a-107">One possible use for <xref:System.Xml.Linq.XContainer.CreateWriter%2A> is when invoking an XSLT transformation.</span></span> <span data-ttu-id="d5c3a-108">In diesem Beispiel wird zunächst eine XML-Struktur erstellt, aus der dann ein <xref:System.Xml.XmlReader> erstellt wird. Anschließend wird ein neues Dokument angelegt und dann für das Schreiben in das neue Dokument ein <xref:System.Xml.XmlWriter> erstellt.</span><span class="sxs-lookup"><span data-stu-id="d5c3a-108">This example creates an XML tree, creates an <xref:System.Xml.XmlReader> from the XML tree, creates a new document, and then creates an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="d5c3a-109">Nachfolgend wird die XSLT-Transformation aufgerufen, wobei <xref:System.Xml.XmlReader> und <xref:System.Xml.XmlWriter> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d5c3a-109">It then invokes the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="d5c3a-110">Nach erfolgreichem Abschluss der Transformation wird die neue XML-Struktur mit den Ergebnissen der Transformation aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="d5c3a-110">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
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
  
 <span data-ttu-id="d5c3a-111">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="d5c3a-111">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d5c3a-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5c3a-112">See also</span></span>

- <xref:System.Xml.Linq.XContainer.CreateWriter%2A>
- <xref:System.Xml.XmlWriter>
- <xref:System.Xml.Xsl.XslCompiledTransform>
- [<span data-ttu-id="d5c3a-113">Creating XML Trees (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5c3a-113">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
