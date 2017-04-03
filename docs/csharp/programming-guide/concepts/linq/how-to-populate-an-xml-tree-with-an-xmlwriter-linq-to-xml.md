---
title: "Vorgehensweise: Füllen eines XML-Baums mit einem XmlWriter (LINQ to XML) (C#) | Microsoft-Dokumentation"
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 225aa8a39a973ba8d4f199ccfce68e2dc16d8aa2
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml-c"></a>Vorgehensweise: Füllen eines XML-Baums mit einem XmlWriter (LINQ to XML) (C#)
Eine Möglichkeit zum Füllen eines XML-Baums besteht darin, <xref:System.Xml.Linq.XContainer.CreateWriter%2A> zu verwendet, um einen <xref:System.Xml.XmlWriter> zu erstellen, und dann in den <xref:System.Xml.XmlWriter> zu schreiben. Die XML-Struktur wird mit allen Knoten aufgefüllt, die in den <xref:System.Xml.XmlWriter> geschrieben werden.  
  
 Üblicherweise verwenden Sie diese Methode, wenn Sie [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] zusammen mit einer anderen Klasse verwenden, die erwartet, in einen <xref:System.Xml.XmlWriter> zu schreiben, wie etwa <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
## <a name="example"></a>Beispiel  
 Das Aufrufen einer XSL-Transformation ist ein möglicher Einsatz von <xref:System.Xml.Linq.XContainer.CreateWriter%2A>. In diesem Beispiel werden eine XML-Struktur, ein <xref:System.Xml.XmlReader> aus der XML-Struktur, ein neues Dokument und dann ein <xref:System.Xml.XmlWriter> zum Schreiben in das neue Dokument erstellt. Anschließend wird die XSLT-Transformation aufgerufen, wobei <xref:System.Xml.XmlReader> und <xref:System.Xml.XmlWriter> übergeben werden. Nach erfolgreichem Abschluss der Transformation wird die neue XML-Struktur mit den Ergebnissen der Transformation aufgefüllt.  
  
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
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XContainer.CreateWriter%2A>   
 <xref:System.Xml.XmlWriter>   
 <xref:System.Xml.Xsl.XslCompiledTransform>   
 [Erstellen von XML-Bäumen (C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)
