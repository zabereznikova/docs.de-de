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
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709841"
---
# <a name="xmldocument-input-to-xsltransform"></a>XmlDocument-Eingaben in "XslTransform"
Die <xref:System.Xml.XmlDocument>-Klasse stellt Bearbeitungsfunktionen für ein XML-Dokument zur Verfügung. Wenn XML vor dem Senden an die <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode bearbeitet oder geändert werden muss, laden Sie das XML-Dokument zum Bearbeiten in ein <xref:System.Xml.XmlDocument>-Dokument und senden Sie es an <xref:System.Xml.Xsl.XslTransform>.  
  
> [!NOTE]
> Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in .NET Framework 2.0 veraltet. Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse können Sie XSLT-Transformationen (Extensible Stylesheet Language for Transformations) vornehmen. Weitere Informationen finden Sie unter [Verwenden der XslCompiledTransform-Klasse](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform-Klasse](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).  
  
 Das <xref:System.Xml.XmlDocument> implementiert die <xref:System.Xml.XPath.IXPathNavigable>-Schnittstelle, damit das Dokument nach dem Bearbeiten an die <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode übergeben werden kann.  
  
 Aufgrund der Bearbeitungsfunktionen des <xref:System.Xml.XmlDocument> beansprucht die Verwendung der <xref:System.Xml.XmlDocument>-Klasse als Eingabe für eine Transformation mehr Zeit als die Verwendung eines <xref:System.Xml.XPath.XPathDocument> für XSLT-Transformationen, da das <xref:System.Xml.XPath.XPathDocument> aufgrund der internen Speicherung für XPath-Abfragen (XML Path Language) optimiert ist.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie für <xref:System.Xml.XmlDocument> ein <xref:System.Xml.Xsl.XslTransform> bereitgestellt werden kann, ohne dass die Ausgabe an einen <xref:System.Xml.XmlReader> gesendet wird.  
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XmlDocument>
- [XSLT-Transformationen mit der XslTransform-Klasse](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)
- [Implementierung des XSLT-Prozessors durch die XslTransform-Klasse](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
- [„XPathNavigator“ in Transformationen](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)
- [„XPathNodeIterator“ in Transformationen](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)
- [XPathDocument-Eingaben in XslTransform](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)
- [XmlDataDocument-Eingaben in „XslTransform“](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)
