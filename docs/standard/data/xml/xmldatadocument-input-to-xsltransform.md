---
title: XmlDataDocument-Eingaben in "XslTransform"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0b536b6-cdb3-4a44-86c2-3b2ebc7bd4c9
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 813c240ca0115015158988e1226d25890cde6939
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="xmldatadocument-input-to-xsltransform"></a>XmlDataDocument-Eingaben in "XslTransform"
> [!NOTE]
>  Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] veraltet. Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse können Sie XSLT-Transformationen (Extensible Stylesheet Language for Transformations) vornehmen. Finden Sie unter [mithilfe der Klasse "XslCompiledTransform"](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform-Klasse](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) für Weitere Informationen.  
  
 
          [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] von Microsoft implementiert XML-DOMs (Document Object Models), um Zugriff auf Daten in XML-Dokumenten und zusätzliche Klassen zum Lesen und Schreiben von sowie zum Navigieren in XML-Dokumenten bereitzustellen. Die <xref:System.Xml.XmlDataDocument>, die sich in der <xref:System.Xml> Namespace bietet relationalen Zugriff auf Daten mit der Fähigkeit zur Synchronisierung mit relationalen Daten in der <xref:System.Data.DataSet>. Sie können strukturiertes XML durch die relationale Darstellung des <xref:System.Data.DataSet> gleichzeitig anzeigen und bearbeiten, oder Sie können teilstrukturiertes XML durch die DOM-Darstellung des <xref:System.Xml.XmlDataDocument> bearbeiten. Das <xref:System.Xml.XmlDataDocument> überschreitet daher die Grenzen von XML und relationalen Darstellungen.  
  
 Wenn Daten in einer relationalen Struktur gespeichert sind, und Sie diese Daten als Eingabe für eine XSLT-Transformation verwenden möchten, können Sie die relationalen Daten in ein <xref:System.Data.DataSet> laden und dem <xref:System.Xml.XmlDataDocument> zuordnen. Der <xref:System.Xml.XPath.XPathNavigator>, die Eingabe für <xref:System.Xml.Xsl.XslTransform>, wird durch die <xref:System.Xml.XmlDataDocument>-Schnittstelle für das <xref:System.Xml.XPath.IXPathNavigable> implementiert. Durch Annahme der relationalen Daten, das Laden in ein <xref:System.Data.DataSet> und die Synchronisierung im <xref:System.Xml.XmlDataDocument> können für relationale Daten XSLT-Transformationen ausgeführt werden.  
  
 Weitere Informationen zum Anwenden von einer Transformation für relationale Daten finden Sie unter [Anwenden einer XSLT-Transformation auf ein DataSet](../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.XmlDataDocument>  
 [DataSet- und XmlDataDocument-Synchronisierung](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)  
 [XSLT-Transformationen mit der XslTransform-Klasse](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 [XslTransform-Klasse implementiert die XSLT-Prozessor](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)  
 ["XPathNavigator" in Transformationen](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)  
 ["XPathNodeIterator" in Transformationen](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)  
 [XPathDocument-Eingaben in "XslTransform"](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)  
 [XmlDocument-Eingaben in "XslTransform"](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)
