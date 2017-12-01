---
title: "XSLT-Transformationen über unterschiedliche Speicher"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 369850e9-004a-45d2-b5c3-5060d9135adb
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b909b754c1d0d3007e06cd04376413d02cbc2f76
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="xslt-transformations-over-different-stores"></a>XSLT-Transformationen über unterschiedliche Speicher
> [!NOTE]
>  Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] veraltet. Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse können Sie XSLT-Transformationen (Extensible Stylesheet Language for Transformations) vornehmen. Finden Sie unter [mithilfe der Klasse "XslCompiledTransform"](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform-Klasse](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) für Weitere Informationen.  
  
 Die ADO.NET- und die XML-Klassen in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] stellen ein vereinheitlichtes Programmiermodell für den Zugriff auf Daten bereit. Diese Daten werden sowohl in Form von XML-Daten, d. h. Text mit Tags als Trennzeichen, als auch in Form von relationalen Daten dargestellt, d. h. Tabellen mit Zeilen und Spalten. XML liest in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] XML-Daten aus einem beliebigen Datenstream in DOM-Knotenstrukturen (Dokumentobjektmodell) ein, wo programmgesteuert auf Daten zugegriffen werden kann, während ADO.NET die Möglichkeiten für den Zugriff auf relationale Daten in einem <xref:System.Data.DataSet>-Objekt und die Bearbeitung dieser Daten bereitstellt.  
  
 Das XML-DOM ermöglicht Zugriff auf Daten in XML-Dokumenten und stellt zusätzliche Klassen zum Lesen, Schreiben und Navigieren in XML-Dokumenten bereit. Diese Klassen werden im <xref:System.Xml>-Namespace unterstützt, wodurch ebenfalls das XML-DOM mit den Datenzugriffsdiensten von ADO.NET zusammengeführt wird. <xref:System.Xml.XmlDataDocument> ermöglicht den relationalen Zugriff auf die Daten. Das <xref:System.Xml.XmlDataDocument> ordnet XML den relationalen Daten in einem ADO.NET-<xref:System.Data.DataSet> zu. [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-basierte Anwendungen können die Klassen im <xref:System.Xml>-Namespace verwenden, um sowohl auf XML-Dokumente als auch auf relationale Daten im <xref:System.Xml.XmlDataDocument> zuzugreifen und diese zu bearbeiten. Diese Implementierung unterstützt Architekturen mit n Ebenen für das Erfassen und Verteilen von Daten. Weitere Informationen finden Sie unter [XML-Integration mit relationalen Daten und ADO.NET](../../../../docs/standard/data/xml/xml-integration-with-relational-data-and-adonet.md).  
  
## <a name="see-also"></a>Siehe auch  
 [XslTransform-Klasse implementiert die XSLT-Prozessor](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
