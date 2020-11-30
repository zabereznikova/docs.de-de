---
title: "\"XPathNavigator\" in Transformationen"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 118f97d1-7110-4d1b-b0bd-4143252c0bb0
ms.openlocfilehash: 935f0b2263fbf909decee354b0109d16d82a06e0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720853"
---
# <a name="xpathnavigator-in-transformations"></a>"XPathNavigator" in Transformationen

Die <xref:System.Xml.XPath.XPathNavigator>-Klasse ermöglicht zufälligen schreibgeschützten Datenzugriff und ist als Eingabe für XSLT (Extensible Stylesheet Language for Transformations). Sie ist im <xref:System.Xml.XPath.XPathDocument>, im <xref:System.Xml.XmlDataDocument> und im <xref:System.Xml.XmlDocument> implementiert. Der <xref:System.Xml.XPath.XPathNavigator> basiert auf dem W3C-Datenmodell (World Wide Web Consortium) wie in Abschnitt 5 der XPath-Empfehlung (XML Path Language) beschrieben.  
  
 Der <xref:System.Xml.XPath.XPathNavigator> definiert ein Modell eines Cursors für einen beliebigen Datenspeicher und ermöglicht schnelle schreibgeschützte XPath-Abfragen für einen beliebigen Datenspeicher. Der <xref:System.Xml.XPath.XPathNavigator> ist auch die Klasse, die zum Durchlaufen von Ereignisstrukturfragmenten verwendet wird.  
  
 Mithilfe der API können Sie Informationen aus dem aktuellen Knoten in dem Speicher abrufen und zu verbundenen Knoten wechseln. Der <xref:System.Xml.XPath.XPathNavigator> ist ein Cursorstilmodell, bei dem das Durchlaufen eines Speichers mithilfe einer Gruppe von **Move**-Methoden durchgeführt wird. Der <xref:System.Xml.XPath.XPathNavigator> ist immer auf einem Knoten positioniert. Bei einem fehlerhaften Aufruf einer **Move**-Methode wird der <xref:System.Xml.XPath.XPathNavigator> nicht geändert.  
  
 Der <xref:System.Xml.XPath.XPathNavigator> ist die Klasse, die zum Durchlaufen von Ereignisstrukturfragmenten verwendet wird. Im folgenden Codebeispiel wird ein Ergebnisstrukturfragment in einem Stylesheet erstellt. Dabei wird die Funktion mit dem Parameter `fragment` aufgerufen, der XML enthält.  
  
## <a name="testxsl"></a>test.xsl  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
                xmlns:msxsl ="urn:schemas-microsoft-com:xslt"  
                xmlns:user="http://www.adventure-works.com"  
                version="1.0">  
  
<xsl:variable name="fragment">  
    <authorlist>  
       <author>Joe</author>  
    </authorlist>  
</xsl:variable>  
  
<msxsl:script language="C#" implements-prefix="user">  
<![CDATA[  
   string NodeFragment(XPathNavigator nav)  
   {  
      if (nav.HasChildren)  
        return nav.Value;  
      else  
        return "";  
   }  
]]>  
</msxsl:script>  
  
<xsl:template match="/">  
     <xsl:value-of select="user:NodeFragment($fragment)"/>  
</xsl:template>  
  
</xsl:stylesheet>  
```  
  
## <a name="testxml"></a>test.xml  
  
```xml  
<root>Some text</root>  
```  
  
 Im folgenden Code werden das **test.xsl**-Stylesheet und die **test.xml**-Eingabedaten verwendet.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.Xsl  
Imports System.Xml.XPath  
Imports System.Text  
Public Class sample  
  
    Public Shared Sub Main()  
        Dim xslt As New XslTransform()  
        xslt.Load("test.xsl")  
  
        Dim xd As New XPathDocument("test.xml")  
  
        Dim strmTemp = New FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite)  
        xslt.Transform(xd, Nothing, strmTemp, Nothing)  
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
        XslTransform xslt = new XslTransform();  
        xslt.Load("test.xsl");  
  
        XPathDocument xd = new XPathDocument("test.xml");  
  
        Stream strmTemp = new FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite);  
        xslt.Transform(xd, null, strmTemp, null);  
    }  
}  
```  
  
## <a name="output"></a>Output  

 Das Ergebnis der Transformation befindet sich in der Datei **out.xml**:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>Joe  
```  
  
## <a name="see-also"></a>Siehe auch

- [Implementierung des XSLT-Prozessors durch die XslTransform-Klasse](xsltransform-class-implements-the-xslt-processor.md)
