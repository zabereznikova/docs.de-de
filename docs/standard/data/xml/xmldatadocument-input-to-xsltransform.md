---
title: XmlDataDocument-Eingaben in "XslTransform"
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: a0b536b6-cdb3-4a44-86c2-3b2ebc7bd4c9
ms.openlocfilehash: 01c6ba8b14f8de167892ee9eeaff615f1f9ca37d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290265"
---
# <a name="xmldatadocument-input-to-xsltransform"></a>XmlDataDocument-Eingaben in "XslTransform"
> [!NOTE]
> Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in .NET Framework 2.0 veraltet. Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse können Sie XSLT-Transformationen (Extensible Stylesheet Language for Transformations) vornehmen. Weitere Informationen finden Sie unter [Verwenden der XslCompiledTransform-Klasse](using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform-Klasse](migrating-from-the-xsltransform-class.md).  
  
 Microsoft .NET Framework implementiert das XML-Dokumentobjektmodell (DOM), um Zugriff auf Daten in XML-Dokumenten und zusätzliche Klassen für Lese-, Schreib- und Navigationsvorgänge in XML-Dokumenten bereitzustellen. Das <xref:System.Xml.XmlDataDocument> im <xref:System.Xml>-Namespace bietet durch die Möglichkeit zur Synchronisierung mit relationalen Daten im <xref:System.Data.DataSet> relationalen Zugriff auf Daten. Sie können strukturiertes XML durch die relationale Darstellung des <xref:System.Data.DataSet> gleichzeitig anzeigen und bearbeiten, oder Sie können teilstrukturiertes XML durch die DOM-Darstellung des <xref:System.Xml.XmlDataDocument> bearbeiten. Das <xref:System.Xml.XmlDataDocument> überschreitet daher die Grenzen von XML und relationalen Darstellungen.  
  
 Wenn Daten in einer relationalen Struktur gespeichert sind, und Sie diese Daten als Eingabe für eine XSLT-Transformation verwenden möchten, können Sie die relationalen Daten in ein <xref:System.Data.DataSet> laden und dem <xref:System.Xml.XmlDataDocument> zuordnen. Der <xref:System.Xml.XPath.XPathNavigator>, die Eingabe für <xref:System.Xml.Xsl.XslTransform>, wird durch die <xref:System.Xml.XmlDataDocument>-Schnittstelle für das <xref:System.Xml.XPath.IXPathNavigable> implementiert. Durch Annahme der relationalen Daten, das Laden in ein <xref:System.Data.DataSet> und die Synchronisierung im <xref:System.Xml.XmlDataDocument> können für relationale Daten XSLT-Transformationen ausgeführt werden.  
  
 Weitere Informationen zur Anwendung einer Transformation für relationale Daten finden Sie unter [Anwenden einer XSLT-Transformation auf ein DataSet](../../../framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XmlDataDocument>
- [DataSet- und XmlDataDocument-Synchronisierung](../../../framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)
- [XSLT-Transformationen mit der XslTransform-Klasse](xslt-transformations-with-the-xsltransform-class.md)
- [Implementierung des XSLT-Prozessors durch die XslTransform-Klasse](xsltransform-class-implements-the-xslt-processor.md)
- [„XPathNavigator“ in Transformationen](xpathnavigator-in-transformations.md)
- [„XPathNodeIterator“ in Transformationen](xpathnodeiterator-in-transformations.md)
- [XPathDocument-Eingaben in XslTransform](xpathdocument-input-to-xsltransform.md)
- [XmlDocument-Eingaben in „XslTransform“](xmldocument-input-to-xsltransform.md)
