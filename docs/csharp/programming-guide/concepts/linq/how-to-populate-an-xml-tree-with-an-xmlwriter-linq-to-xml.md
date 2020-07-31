---
title: 'Vorgehensweise: Auffüllen einer XML-Struktur mit einem XmlWriter (LINQ to XML) (C#)'
description: Hier erfahren Sie, wie Sie einen XML-Baum mit CreateWriter mit Daten füllen, um eine XmlWriter-Klasse zu erstellen, und anschließend in LINQ to XML in C# in die XmlWriter-Klasse schreiben.
ms.date: 07/20/2015
ms.assetid: cd5674d1-5c54-4efc-ba68-e23b2875295f
ms.openlocfilehash: 9639c5947583bccf4f8ba427fc8611e181ef1536
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104793"
---
# <a name="how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml-c"></a><span data-ttu-id="81231-103">Vorgehensweise: Auffüllen einer XML-Struktur mit einem XmlWriter (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="81231-103">How to populate an XML tree with an XmlWriter (LINQ to XML) (C#)</span></span>
<span data-ttu-id="81231-104">Eine Möglichkeit, eine XML-Struktur aufzufüllen, besteht darin, mit <xref:System.Xml.Linq.XContainer.CreateWriter%2A> einen <xref:System.Xml.XmlWriter> zu erstellen und dann in den <xref:System.Xml.XmlWriter> zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="81231-104">One way to populate an XML tree is to use <xref:System.Xml.Linq.XContainer.CreateWriter%2A> to create an <xref:System.Xml.XmlWriter>, and then write to the <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="81231-105">Die XML-Struktur wird mit allen Knoten aufgefüllt, die in den <xref:System.Xml.XmlWriter> geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="81231-105">The XML tree is populated with all nodes that are written to the <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="81231-106">Diese Methode kommt in der Regel zum Einsatz, wenn Sie [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] mit einer anderen Klasse verwenden, die davon ausgeht, dass sie in einen <xref:System.Xml.XmlWriter>, z.B. <xref:System.Xml.Xsl.XslCompiledTransform>, schreibt.</span><span class="sxs-lookup"><span data-stu-id="81231-106">You would typically use this method when you use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] with another class that expects to write to an <xref:System.Xml.XmlWriter>, such as <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81231-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="81231-107">Example</span></span>  
 <span data-ttu-id="81231-108"><xref:System.Xml.Linq.XContainer.CreateWriter%2A> kann beispielsweise verwendet werden, wenn eine XSLT-Transformation aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="81231-108">One possible use for <xref:System.Xml.Linq.XContainer.CreateWriter%2A> is when invoking an XSLT transformation.</span></span> <span data-ttu-id="81231-109">In diesem Beispiel wird zunächst eine XML-Struktur erstellt, aus der dann ein <xref:System.Xml.XmlReader> erstellt wird. Anschließend wird ein neues Dokument angelegt und dann für das Schreiben in das neue Dokument ein <xref:System.Xml.XmlWriter> erstellt.</span><span class="sxs-lookup"><span data-stu-id="81231-109">This example creates an XML tree, creates an <xref:System.Xml.XmlReader> from the XML tree, creates a new document, and then creates an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="81231-110">Nachfolgend wird die XSLT-Transformation aufgerufen, wobei <xref:System.Xml.XmlReader> und <xref:System.Xml.XmlWriter> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="81231-110">It then invokes the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="81231-111">Nach erfolgreichem Abschluss der Transformation wird die neue XML-Struktur mit den Ergebnissen der Transformation aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="81231-111">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
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
using (XmlWriter writer = newTree.CreateWriter())  
{  
    // Load the style sheet.  
    XslCompiledTransform xslt = new XslCompiledTransform();  
    xslt.Load(XmlReader.Create(new StringReader(xslMarkup)));  
  
    // Execute the transformation and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer);  
}  
  
Console.WriteLine(newTree);  
```  
  
 <span data-ttu-id="81231-112">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="81231-112">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="81231-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81231-113">See also</span></span>

- <xref:System.Xml.Linq.XContainer.CreateWriter%2A>
- <xref:System.Xml.XmlWriter>
- <xref:System.Xml.Xsl.XslCompiledTransform>
- [<span data-ttu-id="81231-114">Creating XML Trees (C#) (Erstellen von XML-Strukturen (C#))</span><span class="sxs-lookup"><span data-stu-id="81231-114">Creating XML Trees (C#)</span></span>](./linq-to-xml-overview.md)
