---
title: XmlDocument-Eingaben in "XslTransform"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 97115892-410a-4657-ab47-1e14dfba73f8
ms.openlocfilehash: c7819c3cb6b1430dcdb8a78c43f7138f64e691a8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709841"
---
# <a name="xmldocument-input-to-xsltransform"></a><span data-ttu-id="38860-102">XmlDocument-Eingaben in "XslTransform"</span><span class="sxs-lookup"><span data-stu-id="38860-102">XmlDocument Input to XslTransform</span></span>
<span data-ttu-id="38860-103">Die <xref:System.Xml.XmlDocument>-Klasse stellt Bearbeitungsfunktionen für ein XML-Dokument zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="38860-103">The <xref:System.Xml.XmlDocument> class provides editing capabilities for an XML document.</span></span> <span data-ttu-id="38860-104">Wenn XML vor dem Senden an die <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode bearbeitet oder geändert werden muss, laden Sie das XML-Dokument zum Bearbeiten in ein <xref:System.Xml.XmlDocument>-Dokument und senden Sie es an <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="38860-104">If the XML needs to be edited or modified before being sent to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method, load the XML into an <xref:System.Xml.XmlDocument>, edit it, and send it in to the <xref:System.Xml.Xsl.XslTransform>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="38860-105">Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in .NET Framework 2.0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="38860-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="38860-106">Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse können Sie XSLT-Transformationen (Extensible Stylesheet Language for Transformations) vornehmen.</span><span class="sxs-lookup"><span data-stu-id="38860-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="38860-107">Weitere Informationen finden Sie unter [Verwenden der XslCompiledTransform-Klasse](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform-Klasse](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="38860-107">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="38860-108">Das <xref:System.Xml.XmlDocument> implementiert die <xref:System.Xml.XPath.IXPathNavigable>-Schnittstelle, damit das Dokument nach dem Bearbeiten an die <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode übergeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="38860-108">The <xref:System.Xml.XmlDocument> implements the <xref:System.Xml.XPath.IXPathNavigable> interface, so the document can be passed to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method after editing.</span></span>  
  
 <span data-ttu-id="38860-109">Aufgrund der Bearbeitungsfunktionen des <xref:System.Xml.XmlDocument> beansprucht die Verwendung der <xref:System.Xml.XmlDocument>-Klasse als Eingabe für eine Transformation mehr Zeit als die Verwendung eines <xref:System.Xml.XPath.XPathDocument> für XSLT-Transformationen, da das <xref:System.Xml.XPath.XPathDocument> aufgrund der internen Speicherung für XPath-Abfragen (XML Path Language) optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="38860-109">Due to the editing capability of the <xref:System.Xml.XmlDocument>, using the <xref:System.Xml.XmlDocument> class as input to a transformation is slower than using an <xref:System.Xml.XPath.XPathDocument> for the Extensible Stylesheet Language for Transformations (XSLT) transformations, as the <xref:System.Xml.XPath.XPathDocument> is optimized for XML Path Language (XPath) queries due to the internal storage.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38860-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="38860-110">Example</span></span>  
 <span data-ttu-id="38860-111">Im folgenden Codebeispiel wird veranschaulicht, wie für <xref:System.Xml.XmlDocument> ein <xref:System.Xml.Xsl.XslTransform> bereitgestellt werden kann, ohne dass die Ausgabe an einen <xref:System.Xml.XmlReader> gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="38860-111">The following code example shows how an <xref:System.Xml.XmlDocument> can be supplied to the <xref:System.Xml.Xsl.XslTransform>, with the output sent to an <xref:System.Xml.XmlReader>.</span></span>  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.Load("books.xml")  
Dim trans As XslTransform = new XslTransform()  
trans.Load("book.xsl")  
Dim rdr As XmlReader = trans.Transform(doc, Nothing, Nothing)  
while (rdr.Read())  
end while  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.Load("books.xml");  
XslTransform trans = new XslTransform();  
trans.Load("book.xsl");  
XmlReader rdr = trans.Transform(doc, null, null);  
while (rdr.Read()) {}  
```  
  
## <a name="see-also"></a><span data-ttu-id="38860-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38860-112">See also</span></span>

- <xref:System.Xml.XmlDocument>
- [<span data-ttu-id="38860-113">XSLT-Transformationen mit der XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="38860-113">XSLT Transformations with the XslTransform Class</span></span>](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)
- [<span data-ttu-id="38860-114">Implementierung des XSLT-Prozessors durch die XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="38860-114">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
- [<span data-ttu-id="38860-115">„XPathNavigator“ in Transformationen</span><span class="sxs-lookup"><span data-stu-id="38860-115">XPathNavigator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)
- [<span data-ttu-id="38860-116">„XPathNodeIterator“ in Transformationen</span><span class="sxs-lookup"><span data-stu-id="38860-116">XPathNodeIterator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)
- [<span data-ttu-id="38860-117">XPathDocument-Eingaben in XslTransform</span><span class="sxs-lookup"><span data-stu-id="38860-117">XPathDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)
- [<span data-ttu-id="38860-118">XmlDataDocument-Eingaben in „XslTransform“</span><span class="sxs-lookup"><span data-stu-id="38860-118">XmlDataDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)
