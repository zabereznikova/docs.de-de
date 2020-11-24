---
title: XPathDocument-Eingaben in "XslTransform"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7d1bbe8b-ed43-4e62-a5ba-d602d244f4ae
ms.openlocfilehash: d9291ff4010e04bf94a216f099ea80f8a3e2de12
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821722"
---
# <a name="xpathdocument-input-to-xsltransform"></a><span data-ttu-id="ce1c6-102">XPathDocument-Eingaben in "XslTransform"</span><span class="sxs-lookup"><span data-stu-id="ce1c6-102">XPathDocument Input to XslTransform</span></span>
<span data-ttu-id="ce1c6-103">Das <xref:System.Xml.XPath.XPathDocument> ist ein schreibgeschützter Zwischenspeicher für die Verarbeitung von Dokumenten mit <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="ce1c6-103">The <xref:System.Xml.XPath.XPathDocument> is a read-only cache, for processing documents with <xref:System.Xml.Xsl.XslTransform>.</span></span> <span data-ttu-id="ce1c6-104">Seine Struktur ähnelt der des XML-Dokumentobjektmodells (Document Object Model – DOM), es ist jedoch ideal geeignet für die XSLT-Verarbeitung (Extensible Stylesheet Language for Transformations) und das XPath-Datenmodell (XML Path Language) unter Verwendung der XPath-Optimierungsfunktionen für den <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="ce1c6-104">It is structurally similar to the XML Document Object Model (DOM), but it is highly optimized for Extensible Stylesheet Language for Transformations (XSLT) processing and the XML Path Language (XPath) data model using the XPath optimization functions on the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ce1c6-105">Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in .NET Framework 2.0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="ce1c6-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="ce1c6-106">Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse können Sie XSLT-Transformationen (Extensible Stylesheet Language for Transformations) vornehmen.</span><span class="sxs-lookup"><span data-stu-id="ce1c6-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="ce1c6-107">Weitere Informationen finden Sie unter [Verwenden der XslCompiledTransform-Klasse](using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform-Klasse](migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="ce1c6-107">See [Using the XslCompiledTransform Class](using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="ce1c6-108">m folgenden Codebeispiel wird ein <xref:System.Xml.XPath.XPathDocument> als Eingabe für eine Transformation erstellt.</span><span class="sxs-lookup"><span data-stu-id="ce1c6-108">The following code sample creates an <xref:System.Xml.XPath.XPathDocument> as input to a transform.</span></span>  
  
```vb  
Dim xslt as XslTransform = new XslTransform()  
Xslt.Load(someStylesheet)  
Dim doc as XPathDocument = New XPathDocument("books.xml")  
Dim fs as StringWriter = new StringWriter()  
Xslt.Transform(doc, Nothing, fs, Nothing);  
```  
  
```csharp  
XslTransform xslt = new XslTransform();  
Xslt.Load(someStylesheet);  
XPathDocument doc = XPathDocument("books.xml");  
StringWriter fs = new StringWriter();  
Xslt.Transform(doc, null, fs, null);  
```  
  
## <a name="see-also"></a><span data-ttu-id="ce1c6-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce1c6-109">See also</span></span>

- [<span data-ttu-id="ce1c6-110">Implementierung des XSLT-Prozessors durch die XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="ce1c6-110">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)
