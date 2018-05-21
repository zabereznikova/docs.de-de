---
title: Verwenden von XSLT zum Transformieren eines XML-Baums (C#)
ms.date: 07/20/2015
ms.assetid: 373a2699-d4c5-471b-9bda-c1f0ab73b477
ms.openlocfilehash: 9667176243b0531ad4dafa874c57d01f09bd37e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-xslt-to-transform-an-xml-tree-c"></a><span data-ttu-id="5affe-102">Verwenden von XSLT zum Transformieren eines XML-Baums (C#)</span><span class="sxs-lookup"><span data-stu-id="5affe-102">Using XSLT to Transform an XML Tree (C#)</span></span>
<span data-ttu-id="5affe-103">Sie können eine XML-Struktur erstellen, einen <xref:System.Xml.XmlReader> aus der XML-Struktur erstellen, ein neues Dokument erstellen und dann einen <xref:System.Xml.XmlWriter> erstellen, der in das neue Dokument schreibt.</span><span class="sxs-lookup"><span data-stu-id="5affe-103">You can create an XML tree, create an <xref:System.Xml.XmlReader> from the XML tree, create a new document, and create an <xref:System.Xml.XmlWriter> that will write into the new document.</span></span> <span data-ttu-id="5affe-104">Anschließend können Sie die XSLT-Transformation aufrufen und den <xref:System.Xml.XmlReader> sowie den <xref:System.Xml.XmlWriter> an die Transformation übergeben.</span><span class="sxs-lookup"><span data-stu-id="5affe-104">Then, you can invoke the XSLT transformation, passing the <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter> to the transformation.</span></span> <span data-ttu-id="5affe-105">Nach erfolgreichem Abschluss der Transformation wird die neue XML-Struktur mit den Ergebnissen der Transformation aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="5affe-105">After the transformation successfully completes, the new XML tree is populated with the results of the transform.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5affe-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5affe-106">Example</span></span>  
  
```csharp  
string xslMarkup = @"<?xml version='1.0'?>  
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
</xsl:stylesheet>";  
  
XDocument xmlTree = new XDocument(  
    new XElement("Parent",  
        new XElement("Child1", "Child1 data"),  
        new XElement("Child2", "Child2 data")  
    )  
);  
  
XDocument newTree = new XDocument();  
using (XmlWriter writer = newTree.CreateWriter()) {  
    // Load the style sheet.  
    XslCompiledTransform xslt = new XslCompiledTransform();  
    xslt.Load(XmlReader.Create(new StringReader(xslMarkup)));  
  
    // Execute the transform and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer);  
}  
  
Console.WriteLine(newTree);  
```  
  
 <span data-ttu-id="5affe-107">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="5affe-107">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5affe-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5affe-108">See Also</span></span>  
 <xref:System.Xml.Linq.XContainer.CreateWriter%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XNode.CreateReader%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="5affe-109">Advanced LINQ to XML Programming (C#) (Erweiterte LINQ to XML-Programmierung (C#))</span><span class="sxs-lookup"><span data-stu-id="5affe-109">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
