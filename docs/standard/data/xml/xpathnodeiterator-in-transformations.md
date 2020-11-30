---
title: „XPathNodeIterator“ in Transformationen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2bc6ddc6-674a-4f75-b264-abc35e4e5857
ms.openlocfilehash: a1542c0800f9042e27a4b0806d717c58d7783c79
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720840"
---
# <a name="xpathnodeiterator-in-transformations"></a>„XPathNodeIterator“ in Transformationen

<xref:System.Xml.XPath.XPathNodeIterator> stellt Methoden zum Durchlaufen einer Knotengruppe dar, die als Ergebnis einer XPath-Abfrage (XML Path Language) oder als Konvertierung eines Ergebnisstrukturfragments mit der „node-set“-Methode in eine Knotengruppe erstellt wurde. Mit <xref:System.Xml.XPath.XPathNodeIterator> können die Knoten innerhalb dieser Knotengruppe durchlaufen werden. Nach dem Abrufen der Knotengruppe stellt die <xref:System.Xml.XPath.XPathNodeIterator>-Klasse einen schreibgeschützten vorwärtsgerichteten Cursor für die ausgewählte Knotengruppe bereit. Die Knotengruppe wird in der Dokumentreihenfolge erstellt, sodass beim Aufrufen dieser Methode mit dem nächsten Knoten in der Dokumentreihenfolge fortgefahren wird. <xref:System.Xml.XPath.XPathNodeIterator> erstellt keine Knotenstruktur aller Knoten im Satz. Stattdessen stellt er ein Fenster bereit, wodurch der zugrunde liegende Knoten, auf den er verweist, während der Bewegung durch die Struktur verfügbar gemacht wird. Mit den Methoden und Eigenschaften der <xref:System.Xml.XPath.XPathNodeIterator>-Klasse können Sie Informationen aus dem aktuellen Knoten abrufen. Eine Liste der verfügbaren Methoden und Eigenschaften finden Sie unter <xref:System.Windows.Forms.ToolBar>.  
  
 Da sich ein <xref:System.Xml.XPath.XPathNodeIterator> nur vorwärts durch eine Gruppe von Knoten bewegt, die aus einer XPath-Abfrage erstellt wurden, wird die <xref:System.Xml.XPath.XPathNodeIterator.MoveNext%2A>-Methode zum Durchlaufen verwendet. Der Rückgabetyp dieser Methode ist `Boolean`. Es wird `true` zurückgegeben, wenn zum nächsten ausgewählten Knoten gewechselt wird, und es wird `false` zurückgegeben, wenn kein ausgewählter Knoten mehr vorhanden ist. In der folgenden Liste werden die Eigenschaften aufgeführt, die verfügbar sind, wenn `true` zurückgegeben wird:  
  
- <xref:System.Xml.XPath.XPathNodeIterator.Current%2A>  
  
- <xref:System.Xml.XPath.XPathNodeIterator.CurrentPosition%2A>  
  
- <xref:System.Xml.XPath.XPathNodeIterator.Count%2A>  
  
 Nach der Erstellen einer Knotengruppe muss <xref:System.Xml.XPath.XPathNodeIterator.MoveNext%2A> aufgerufen werden, um den <xref:System.Xml.XPath.XPathNodeIterator> auf dem ersten Knoten der ausgewählten Gruppe zu positionieren. Dies ermöglicht die Verwendung einer while-Schleife.  
  
 Im folgenden Codebeispiel wird gezeigt, wie ein <xref:System.Xml.XPath.XPathNodeIterator> für eine <xref:System.Xml.Xsl.XslTransform> als Parameter in der <xref:System.Xml.Xsl.XsltArgumentList> übergeben wird. Die Eingabe im Code ist **books.xml**, und das Stylesheet ist **text.xsl**. Die Datei **test.xml** ist das <xref:System.Xml.XPath.XPathDocument>.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.Xsl  
Imports System.Xml.XPath  
Imports System.Text  
  
Public Class sample  
  
   Public Shared Sub Main()  
      Dim Doc As New XPathDocument("books.xml")  
      Dim nav As XPathNavigator = Doc.CreateNavigator()  
      Dim Iterator As XPathNodeIterator = nav.Select("/bookstore/book")  
  
      Dim arg As New XsltArgumentList()  
      arg.AddParam("param1", "", Iterator)  
  
      Dim xslt As New XslTransform()  
      xslt.Load("test.xsl")  
  
      Dim xd As New XPathDocument("test.xml")  
  
      Dim strmTemp = New FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite)  
      xslt.Transform(xd, arg, strmTemp, Nothing)  
   End Sub 'Main  
End Class 'sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.Xsl;  
using System.Xml.XPath;  
using System.Text;  
  
public class sample  
{  
    public static void Main()  
    {  
        XPathDocument Doc = new XPathDocument("books.xml");  
        XPathNavigator nav = Doc.CreateNavigator();  
        XPathNodeIterator Iterator = nav.Select("/bookstore/book");  
  
        XsltArgumentList arg = new XsltArgumentList();  
        arg.AddParam("param1", "", Iterator);  
  
        XslTransform xslt = new XslTransform();  
        xslt.Load("test.xsl");  
  
        XPathDocument xd = new XPathDocument("test.xml");  
  
        Stream strmTemp = new FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite);  
        xslt.Transform(xd, arg, strmTemp, null);  
    }  
}  
```  
  
## <a name="booksxml"></a>books.xml  
  
```xml  
<?xml version='1.0'?>  
<!-- This file represents a fragment of a book store inventory database. -->  
<bookstore specialty="novel">  
    <book style="autobiography">  
    <title>Seven Years in Trenton</title>  
        <author>  
            <first-name>Jay</first-name>  
            <last-name>Adams</last-name>  
            <award>Trenton Literary Review Honorable Mention</award>  
            <country>USA</country>  
        </author>  
        <price>12</price>  
    </book>  
    <book style="textbook">  
        <title>History of Trenton</title>  
        <author>  
            <first-name>Kim</first-name>  
            <last-name>Akers</last-name>  
            <publication>  
                Selected Short Stories of  
                <first-name>Scott</first-name>  
                <last-name>Bishop</last-name>  
                <country>US</country>  
            </publication>  
        </author>  
        <price>55</price>  
    </book>  
</bookstore>  
```  
  
## <a name="testxsl"></a>test.xsl  
  
```xml  
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
xmlns:msxsl="urn:schemas-microsoft-com:xslt" exclude-result-prefixes="msxsl">  
  
<xsl:output method="xml" indent="yes"/>  
<xsl:param name="param1"/>  
  
<xsl:template match="/">  
    <out>  
        <xsl:for-each select="$param1/title">  
            <title><xsl:value-of select="."/></title>  
        </xsl:for-each>  
    </out>  
</xsl:template>  
  
</xsl:stylesheet>  
```  
  
## <a name="testxml"></a>test.xml  
  
```xml  
<Title attr="Test">this is a test</Title>  
```  
  
## <a name="output-outxml"></a>Ausgabe (out.xml)  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<out>  
  <title>Seven Years in Trenton</title>  
  <title>History of Trenton</title>  
</out>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Implementierung des XSLT-Prozessors durch die XslTransform-Klasse](xsltransform-class-implements-the-xslt-processor.md)
