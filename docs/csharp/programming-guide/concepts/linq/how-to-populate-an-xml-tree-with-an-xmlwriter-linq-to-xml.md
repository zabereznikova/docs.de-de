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
# <a name="how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml-c"></a>Vorgehensweise: Auffüllen einer XML-Struktur mit einem XmlWriter (LINQ to XML) (C#)
Eine Möglichkeit, eine XML-Struktur aufzufüllen, besteht darin, mit <xref:System.Xml.Linq.XContainer.CreateWriter%2A> einen <xref:System.Xml.XmlWriter> zu erstellen und dann in den <xref:System.Xml.XmlWriter> zu schreiben. Die XML-Struktur wird mit allen Knoten aufgefüllt, die in den <xref:System.Xml.XmlWriter> geschrieben werden.  
  
 Diese Methode kommt in der Regel zum Einsatz, wenn Sie [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] mit einer anderen Klasse verwenden, die davon ausgeht, dass sie in einen <xref:System.Xml.XmlWriter>, z.B. <xref:System.Xml.Xsl.XslCompiledTransform>, schreibt.  
  
## <a name="example"></a>Beispiel  
 <xref:System.Xml.Linq.XContainer.CreateWriter%2A> kann beispielsweise verwendet werden, wenn eine XSLT-Transformation aufgerufen wird. In diesem Beispiel wird zunächst eine XML-Struktur erstellt, aus der dann ein <xref:System.Xml.XmlReader> erstellt wird. Anschließend wird ein neues Dokument angelegt und dann für das Schreiben in das neue Dokument ein <xref:System.Xml.XmlWriter> erstellt. Nachfolgend wird die XSLT-Transformation aufgerufen, wobei <xref:System.Xml.XmlReader> und <xref:System.Xml.XmlWriter> verwendet werden. Nach erfolgreichem Abschluss der Transformation wird die neue XML-Struktur mit den Ergebnissen der Transformation aufgefüllt.  
  
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

- <xref:System.Xml.Linq.XContainer.CreateWriter%2A>
- <xref:System.Xml.XmlWriter>
- <xref:System.Xml.Xsl.XslCompiledTransform>
- [Creating XML Trees (C#) (Erstellen von XML-Strukturen (C#))](./linq-to-xml-overview.md)
