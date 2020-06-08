---
title: "\"XPathNavigator\" in Transformationen"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 118f97d1-7110-4d1b-b0bd-4143252c0bb0
ms.openlocfilehash: 59fb399d80e1d4d33d1a3c659d2ff74a37fd367d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84282817"
---
# <a name="xpathnavigator-in-transformations"></a><span data-ttu-id="d22b3-102">"XPathNavigator" in Transformationen</span><span class="sxs-lookup"><span data-stu-id="d22b3-102">XPathNavigator in Transformations</span></span>
<span data-ttu-id="d22b3-103">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse ermöglicht zufälligen schreibgeschützten Datenzugriff und ist als Eingabe für XSLT (Extensible Stylesheet Language for Transformations).</span><span class="sxs-lookup"><span data-stu-id="d22b3-103">The <xref:System.Xml.XPath.XPathNavigator> class provides read-only random access to data and is designed for use as an input to Extensible Stylesheet Language for Transformations (XSLT).</span></span> <span data-ttu-id="d22b3-104">Sie ist im <xref:System.Xml.XPath.XPathDocument>, im <xref:System.Xml.XmlDataDocument> und im <xref:System.Xml.XmlDocument> implementiert.</span><span class="sxs-lookup"><span data-stu-id="d22b3-104">It is implemented on the <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDataDocument>, and <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="d22b3-105">Der <xref:System.Xml.XPath.XPathNavigator> basiert auf dem W3C-Datenmodell (World Wide Web Consortium) wie in Abschnitt 5 der XPath-Empfehlung (XML Path Language) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d22b3-105">The <xref:System.Xml.XPath.XPathNavigator> is based upon the World Wide Web Consortium (W3C) Data Model as described in section 5 of the XML Path Language (XPath) recommendation.</span></span>  
  
 <span data-ttu-id="d22b3-106">Der <xref:System.Xml.XPath.XPathNavigator> definiert ein Modell eines Cursors für einen beliebigen Datenspeicher und ermöglicht schnelle schreibgeschützte XPath-Abfragen für einen beliebigen Datenspeicher.</span><span class="sxs-lookup"><span data-stu-id="d22b3-106">The <xref:System.Xml.XPath.XPathNavigator> defines a cursor model over any store and provides fast, read-only XPath queries over any data store.</span></span> <span data-ttu-id="d22b3-107">Der <xref:System.Xml.XPath.XPathNavigator> ist auch die Klasse, die zum Durchlaufen von Ereignisstrukturfragmenten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d22b3-107">The <xref:System.Xml.XPath.XPathNavigator> is also the class to use for iterating over result tree fragments.</span></span>  
  
 <span data-ttu-id="d22b3-108">Mithilfe der API können Sie Informationen aus dem aktuellen Knoten in dem Speicher abrufen und zu verbundenen Knoten wechseln.</span><span class="sxs-lookup"><span data-stu-id="d22b3-108">The API enables you to get information from the current node in the store and move to connected nodes.</span></span> <span data-ttu-id="d22b3-109">Der <xref:System.Xml.XPath.XPathNavigator> ist ein Cursorstilmodell, bei dem das Durchlaufen eines Speichers mithilfe einer Gruppe von **Move**-Methoden durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d22b3-109">The <xref:System.Xml.XPath.XPathNavigator> is a cursor style model that performs traversal over a store using a set of **Move** methods.</span></span> <span data-ttu-id="d22b3-110">Der <xref:System.Xml.XPath.XPathNavigator> ist immer auf einem Knoten positioniert.</span><span class="sxs-lookup"><span data-stu-id="d22b3-110">The <xref:System.Xml.XPath.XPathNavigator> is always positioned on a node.</span></span> <span data-ttu-id="d22b3-111">Bei einem fehlerhaften Aufruf einer **Move**-Methode wird der <xref:System.Xml.XPath.XPathNavigator> nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="d22b3-111">Any **Move** method that fails leaves the <xref:System.Xml.XPath.XPathNavigator> unchanged.</span></span>  
  
 <span data-ttu-id="d22b3-112">Der <xref:System.Xml.XPath.XPathNavigator> ist die Klasse, die zum Durchlaufen von Ereignisstrukturfragmenten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d22b3-112">The <xref:System.Xml.XPath.XPathNavigator> is the class to use for iterating over result tree fragments.</span></span> <span data-ttu-id="d22b3-113">Im folgenden Codebeispiel wird ein Ergebnisstrukturfragment in einem Stylesheet erstellt. Dabei wird die Funktion mit dem Parameter `fragment` aufgerufen, der XML enthält.</span><span class="sxs-lookup"><span data-stu-id="d22b3-113">The following code sample creates a result tree fragment within a style sheet by calling the function with the parameter, `fragment`, which contains XML.</span></span>  
  
## <a name="testxsl"></a><span data-ttu-id="d22b3-114">test.xsl</span><span class="sxs-lookup"><span data-stu-id="d22b3-114">test.xsl</span></span>  
  
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
  
## <a name="testxml"></a><span data-ttu-id="d22b3-115">test.xml</span><span class="sxs-lookup"><span data-stu-id="d22b3-115">test.xml</span></span>  
  
```xml  
<root>Some text</root>  
```  
  
 <span data-ttu-id="d22b3-116">Im folgenden Code werden das **test.xsl**-Stylesheet und die **test.xml**-Eingabedaten verwendet.</span><span class="sxs-lookup"><span data-stu-id="d22b3-116">The following code uses the **test.xsl** style sheet and **test.xml** input data.</span></span>  
  
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
  
## <a name="output"></a><span data-ttu-id="d22b3-117">Output</span><span class="sxs-lookup"><span data-stu-id="d22b3-117">Output</span></span>  
 <span data-ttu-id="d22b3-118">Das Ergebnis der Transformation befindet sich in der Datei **out.xml**:</span><span class="sxs-lookup"><span data-stu-id="d22b3-118">The result of the transformation is found in the file **out.xml**:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>Joe  
```  
  
## <a name="see-also"></a><span data-ttu-id="d22b3-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d22b3-119">See also</span></span>

- [<span data-ttu-id="d22b3-120">Implementierung des XSLT-Prozessors durch die XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="d22b3-120">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)
