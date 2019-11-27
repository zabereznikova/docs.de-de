---
title: Serialisieren in einen XmlReader (XSLT aufrufen)
ms.date: 07/20/2015
ms.assetid: 8b64f95a-e8f6-40f7-99f9-a8002c63af96
ms.openlocfilehash: 39ecbc1851764d221ac99c3e47c26bcbe84c9e46
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349352"
---
# <a name="serializing-to-an-xmlreader-invoking-xslt-visual-basic"></a><span data-ttu-id="33c43-102">Serialisieren in einen XmlReader (XSLT aufrufen) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33c43-102">Serializing to an XmlReader (Invoking XSLT) (Visual Basic)</span></span>
<span data-ttu-id="33c43-103">Wenn Sie die <xref:System.Xml?displayProperty=nameWithType>-Interoperabilitätsfunktionen von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] verwenden, können Sie <xref:System.Xml.Linq.XNode.CreateReader%2A> verwenden, um einen <xref:System.Xml.XmlReader> zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="33c43-103">When you use the <xref:System.Xml?displayProperty=nameWithType> interoperability capabilities of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can use <xref:System.Xml.Linq.XNode.CreateReader%2A> to create an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="33c43-104">Das Modul, das aus diesem <xref:System.Xml.XmlReader> liest, liest die Knoten aus der XML-Struktur und verarbeitet sie entsprechend.</span><span class="sxs-lookup"><span data-stu-id="33c43-104">The module that reads from this <xref:System.Xml.XmlReader> reads the nodes from the XML tree and processes them accordingly.</span></span>  
  
## <a name="invoking-an-xslt-transformation"></a><span data-ttu-id="33c43-105">Aufrufen einer XSLT-Transformation</span><span class="sxs-lookup"><span data-stu-id="33c43-105">Invoking an XSLT Transformation</span></span>  
 <span data-ttu-id="33c43-106">Diese Methode kann z. B. zum Aufrufen einer XSLT-Transformation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="33c43-106">One possible use for this method is when invoking an XSLT transformation.</span></span> <span data-ttu-id="33c43-107">Sie können eine XML-Struktur erstellen, einen <xref:System.Xml.XmlReader> aus der XML-Struktur erstellen, ein neues Dokument erstellen und dann einen <xref:System.Xml.XmlWriter> zum Schreiben in das neue Dokument erstellen.</span><span class="sxs-lookup"><span data-stu-id="33c43-107">You can create an XML tree, create an <xref:System.Xml.XmlReader> from the XML tree, create a new document, and then create an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="33c43-108">Anschließend können Sie die XSLT-Transformation starten, indem Sie <xref:System.Xml.XmlReader> und <xref:System.Xml.XmlWriter> übergeben.</span><span class="sxs-lookup"><span data-stu-id="33c43-108">Then, you can invoke the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="33c43-109">Nach erfolgreichem Abschluss der Transformation wird die neue XML-Struktur mit den Ergebnissen der Transformation aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="33c43-109">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
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
  
 <span data-ttu-id="33c43-110">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="33c43-110">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="33c43-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33c43-111">See also</span></span>

- [<span data-ttu-id="33c43-112">Serialisieren von XML-Strukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33c43-112">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
