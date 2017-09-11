---
title: "Vorgehensweise: Füllen eines XML-Baums mit einem XmlWriter (LINQ to XML) (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: cd5674d1-5c54-4efc-ba68-e23b2875295f
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9d74e6bd3d8454f5ed37fa8d190beb0c44399fa7
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml-c"></a><span data-ttu-id="008a0-102">Vorgehensweise: Füllen eines XML-Baums mit einem XmlWriter (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="008a0-102">How to: Populate an XML Tree with an XmlWriter (LINQ to XML) (C#)</span></span>
<span data-ttu-id="008a0-103">Eine Möglichkeit, eine XML-Struktur aufzufüllen, besteht darin, mit <xref:System.Xml.Linq.XContainer.CreateWriter%2A> einen <xref:System.Xml.XmlWriter> zu erstellen und dann in den <xref:System.Xml.XmlWriter> zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="008a0-103">One way to populate an XML tree is to use <xref:System.Xml.Linq.XContainer.CreateWriter%2A> to create an <xref:System.Xml.XmlWriter>, and then write to the <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="008a0-104">Die XML-Struktur wird mit allen Knoten aufgefüllt, die in den <xref:System.Xml.XmlWriter> geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="008a0-104">The XML tree is populated with all nodes that are written to the <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="008a0-105">Diese Methode kommt in der Regel zum Einsatz, wenn Sie [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] mit einer anderen Klasse verwenden, die davon ausgeht, dass sie in einen <xref:System.Xml.XmlWriter>, z.B. <xref:System.Xml.Xsl.XslCompiledTransform>, schreibt.</span><span class="sxs-lookup"><span data-stu-id="008a0-105">You would typically use this method when you use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] with another class that expects to write to an <xref:System.Xml.XmlWriter>, such as <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="008a0-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="008a0-106">Example</span></span>  
 <span data-ttu-id="008a0-107"><xref:System.Xml.Linq.XContainer.CreateWriter%2A> kann beispielsweise verwendet werden, wenn eine XSLT-Transformation aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="008a0-107">One possible use for <xref:System.Xml.Linq.XContainer.CreateWriter%2A> is when invoking an XSLT transformation.</span></span> <span data-ttu-id="008a0-108">In diesem Beispiel wird zunächst eine XML-Struktur erstellt, aus der dann ein <xref:System.Xml.XmlReader> erstellt wird. Anschließend wird ein neues Dokument angelegt und dann für das Schreiben in das neue Dokument ein <xref:System.Xml.XmlWriter> erstellt.</span><span class="sxs-lookup"><span data-stu-id="008a0-108">This example creates an XML tree, creates an <xref:System.Xml.XmlReader> from the XML tree, creates a new document, and then creates an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="008a0-109">Nachfolgend wird die XSLT-Transformation aufgerufen, wobei <xref:System.Xml.XmlReader> und <xref:System.Xml.XmlWriter> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="008a0-109">It then invokes the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="008a0-110">Nach erfolgreichem Abschluss der Transformation wird die neue XML-Struktur mit den Ergebnissen der Transformation aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="008a0-110">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
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
  
 <span data-ttu-id="008a0-111">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="008a0-111">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="008a0-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="008a0-112">See Also</span></span>  
 <span data-ttu-id="008a0-113"><xref:System.Xml.Linq.XContainer.CreateWriter%2A></span><span class="sxs-lookup"><span data-stu-id="008a0-113"><xref:System.Xml.Linq.XContainer.CreateWriter%2A></span></span>   
 <span data-ttu-id="008a0-114"><xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="008a0-114"><xref:System.Xml.XmlWriter></span></span>   
 <span data-ttu-id="008a0-115"><xref:System.Xml.Xsl.XslCompiledTransform></span><span class="sxs-lookup"><span data-stu-id="008a0-115"><xref:System.Xml.Xsl.XslCompiledTransform></span></span>   
 [<span data-ttu-id="008a0-116">Creating XML Trees (C#) (Erstellen von XML-Strukturen (C#))</span><span class="sxs-lookup"><span data-stu-id="008a0-116">Creating XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)

