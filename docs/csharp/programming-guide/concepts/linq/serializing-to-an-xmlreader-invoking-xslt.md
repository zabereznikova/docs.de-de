---
title: Serialisieren in einen XmlReader (XSLT aufrufen) (C#)
description: Erfahren Sie, wie Sie CreateReader verwenden, um einen XmlReader in C# zu erstellen. Das Modul, das aus diesem XmlReader liest, liest die Knoten aus der XML-Struktur und verarbeitet sie.
ms.date: 07/20/2015
ms.assetid: 4cc3ee03-ef4c-429b-a408-fedd10b728cd
ms.openlocfilehash: aa5a232c74c5314cb7f1cf03c2a8875ca1cd04df
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302411"
---
# <a name="serializing-to-an-xmlreader-invoking-xslt-c"></a><span data-ttu-id="882dd-104">Serialisieren in einen XmlReader (XSLT aufrufen) (C#)</span><span class="sxs-lookup"><span data-stu-id="882dd-104">Serializing to an XmlReader (Invoking XSLT) (C#)</span></span>
<span data-ttu-id="882dd-105">Wenn Sie die <xref:System.Xml?displayProperty=nameWithType>-Interoperabilitätsfunktionen von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] verwenden, können Sie <xref:System.Xml.Linq.XNode.CreateReader%2A> verwenden, um einen <xref:System.Xml.XmlReader> zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="882dd-105">When you use the <xref:System.Xml?displayProperty=nameWithType> interoperability capabilities of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can use <xref:System.Xml.Linq.XNode.CreateReader%2A> to create an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="882dd-106">Das Modul, das aus diesem <xref:System.Xml.XmlReader> liest, liest die Knoten aus der XML-Struktur und verarbeitet sie entsprechend.</span><span class="sxs-lookup"><span data-stu-id="882dd-106">The module that reads from this <xref:System.Xml.XmlReader> reads the nodes from the XML tree and processes them accordingly.</span></span>  
  
## <a name="invoking-an-xslt-transformation"></a><span data-ttu-id="882dd-107">Aufrufen einer XSLT-Transformation</span><span class="sxs-lookup"><span data-stu-id="882dd-107">Invoking an XSLT Transformation</span></span>  
 <span data-ttu-id="882dd-108">Diese Methode kann z. B. zum Aufrufen einer XSLT-Transformation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="882dd-108">One possible use for this method is when invoking an XSLT transformation.</span></span> <span data-ttu-id="882dd-109">Sie können eine XML-Struktur erstellen, einen <xref:System.Xml.XmlReader> aus der XML-Struktur erstellen, ein neues Dokument erstellen und dann einen <xref:System.Xml.XmlWriter> zum Schreiben in das neue Dokument erstellen.</span><span class="sxs-lookup"><span data-stu-id="882dd-109">You can create an XML tree, create an <xref:System.Xml.XmlReader> from the XML tree, create a new document, and then create an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="882dd-110">Anschließend können Sie die XSLT-Transformation starten, indem Sie <xref:System.Xml.XmlReader> und <xref:System.Xml.XmlWriter> übergeben.</span><span class="sxs-lookup"><span data-stu-id="882dd-110">Then, you can invoke the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="882dd-111">Nach erfolgreichem Abschluss der Transformation wird die neue XML-Struktur mit den Ergebnissen der Transformation aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="882dd-111">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
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
  
    // Execute the transformation and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer);  
}  
  
Console.WriteLine(newTree);  
```  
  
 <span data-ttu-id="882dd-112">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="882dd-112">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="882dd-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="882dd-113">See also</span></span>

- [<span data-ttu-id="882dd-114">Serialisieren von XML-Strukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="882dd-114">Serializing XML Trees (C#)</span></span>](serializing-to-files-textwriters-and-xmlwriters.md)
