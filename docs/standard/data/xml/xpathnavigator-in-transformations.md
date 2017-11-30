---
title: "„XPathNavigator“ in Transformationen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 118f97d1-7110-4d1b-b0bd-4143252c0bb0
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 09f89708607ada18181bc6605994c7908e1dd14b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="xpathnavigator-in-transformations"></a><span data-ttu-id="32ac9-102">„XPathNavigator“ in Transformationen</span><span class="sxs-lookup"><span data-stu-id="32ac9-102">XPathNavigator in Transformations</span></span>
<span data-ttu-id="32ac9-103">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse ermöglicht zufälligen schreibgeschützten Datenzugriff und ist als Eingabe für XSLT (Extensible Stylesheet Language for Transformations).</span><span class="sxs-lookup"><span data-stu-id="32ac9-103">The <xref:System.Xml.XPath.XPathNavigator> class provides read-only random access to data and is designed for use as an input to Extensible Stylesheet Language for Transformations (XSLT).</span></span> <span data-ttu-id="32ac9-104">Sie ist im <xref:System.Xml.XPath.XPathDocument>, im <xref:System.Xml.XmlDataDocument> und im <xref:System.Xml.XmlDocument> implementiert.</span><span class="sxs-lookup"><span data-stu-id="32ac9-104">It is implemented on the <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDataDocument>, and <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="32ac9-105">Der <xref:System.Xml.XPath.XPathNavigator> basiert auf dem W3C-Datenmodell (World Wide Web Consortium) wie in Abschnitt 5 der XPath-Empfehlung (XML Path Language) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="32ac9-105">The <xref:System.Xml.XPath.XPathNavigator> is based upon the World Wide Web Consortium (W3C) Data Model as described in section 5 of the XML Path Language (XPath) recommendation.</span></span>  
  
 <span data-ttu-id="32ac9-106">Der <xref:System.Xml.XPath.XPathNavigator> definiert ein Modell eines Cursors für einen beliebigen Datenspeicher und ermöglicht schnelle schreibgeschützte XPath-Abfragen für einen beliebigen Datenspeicher.</span><span class="sxs-lookup"><span data-stu-id="32ac9-106">The <xref:System.Xml.XPath.XPathNavigator> defines a cursor model over any store and provides fast, read-only XPath queries over any data store.</span></span> <span data-ttu-id="32ac9-107">Der <xref:System.Xml.XPath.XPathNavigator> ist auch die Klasse, die zum Durchlaufen von Ereignisstrukturfragmenten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="32ac9-107">The <xref:System.Xml.XPath.XPathNavigator> is also the class to use for iterating over result tree fragments.</span></span>  
  
 <span data-ttu-id="32ac9-108">Mithilfe der API können Sie Informationen aus dem aktuellen Knoten in dem Speicher abrufen und zu verbundenen Knoten wechseln.</span><span class="sxs-lookup"><span data-stu-id="32ac9-108">The API enables you to get information from the current node in the store and move to connected nodes.</span></span> <span data-ttu-id="32ac9-109">Die <xref:System.Xml.XPath.XPathNavigator> ist ein Cursormodell, das Durchlaufen eines Speichers mithilfe einer Reihe von Durchlauf ausführt **verschieben** Methoden.</span><span class="sxs-lookup"><span data-stu-id="32ac9-109">The <xref:System.Xml.XPath.XPathNavigator> is a cursor style model that performs traversal over a store using a set of **Move** methods.</span></span> <span data-ttu-id="32ac9-110">Der <xref:System.Xml.XPath.XPathNavigator> ist immer auf einem Knoten positioniert.</span><span class="sxs-lookup"><span data-stu-id="32ac9-110">The <xref:System.Xml.XPath.XPathNavigator> is always positioned on a node.</span></span> <span data-ttu-id="32ac9-111">Alle **verschieben** Methode bewirkt, dass ein Fehler auftritt, die die <xref:System.Xml.XPath.XPathNavigator> unverändert.</span><span class="sxs-lookup"><span data-stu-id="32ac9-111">Any **Move** method that fails leaves the <xref:System.Xml.XPath.XPathNavigator> unchanged.</span></span>  
  
 <span data-ttu-id="32ac9-112">Der <xref:System.Xml.XPath.XPathNavigator> ist die Klasse, die zum Durchlaufen von Ereignisstrukturfragmenten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="32ac9-112">The <xref:System.Xml.XPath.XPathNavigator> is the class to use for iterating over result tree fragments.</span></span> <span data-ttu-id="32ac9-113">Im folgenden Codebeispiel wird ein Ergebnisstrukturfragment in einem Stylesheet erstellt. Dabei wird die Funktion mit dem Parameter `fragment` aufgerufen, der XML enthält.</span><span class="sxs-lookup"><span data-stu-id="32ac9-113">The following code sample creates a result tree fragment within a style sheet by calling the function with the parameter, `fragment`, which contains XML.</span></span>  
  
## <a name="testxsl"></a><span data-ttu-id="32ac9-114">test.xsl</span><span class="sxs-lookup"><span data-stu-id="32ac9-114">test.xsl</span></span>  
  
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
  
## <a name="testxml"></a><span data-ttu-id="32ac9-115">test.xml</span><span class="sxs-lookup"><span data-stu-id="32ac9-115">test.xml</span></span>  
  
```xml  
<root>Some text</root>  
```  
  
 <span data-ttu-id="32ac9-116">Der folgende code verwendet die **test.xsl** Stylesheet und **test.xml** Eingabedaten.</span><span class="sxs-lookup"><span data-stu-id="32ac9-116">The following code uses the **test.xsl** style sheet and **test.xml** input data.</span></span>  
  
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
  
## <a name="output"></a><span data-ttu-id="32ac9-117">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="32ac9-117">Output</span></span>  
 <span data-ttu-id="32ac9-118">Das Ergebnis der Transformation befindet sich in der Datei **out.xml**:</span><span class="sxs-lookup"><span data-stu-id="32ac9-118">The result of the transformation is found in the file **out.xml**:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>Joe  
```  
  
## <a name="see-also"></a><span data-ttu-id="32ac9-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32ac9-119">See Also</span></span>  
 [<span data-ttu-id="32ac9-120">XslTransform-Klasse implementiert die XSLT-Prozessor</span><span class="sxs-lookup"><span data-stu-id="32ac9-120">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
