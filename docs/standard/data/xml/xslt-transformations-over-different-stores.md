---
title: XSLT-Transformationen über unterschiedliche Speicher
ms.date: 03/30/2017
ms.assetid: 369850e9-004a-45d2-b5c3-5060d9135adb
ms.openlocfilehash: 15fcf7f3dcf3165b7b88ad01d63aa27873bf5d8d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685096"
---
# <a name="xslt-transformations-over-different-stores"></a>XSLT-Transformationen über unterschiedliche Speicher

> [!NOTE]
> Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in .NET Framework 2.0 veraltet. Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse können Sie XSLT-Transformationen (Extensible Stylesheet Language for Transformations) vornehmen. Weitere Informationen finden Sie unter [Verwenden der XslCompiledTransform-Klasse](using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform-Klasse](migrating-from-the-xsltransform-class.md).  
  
 Die ADO.NET- und die XML-Klassen in .NET Framework stellen ein vereinheitlichtes Programmiermodell für den Zugriff auf Daten bereit. Diese Daten werden sowohl in Form von XML-Daten, d. h. Text mit Tags als Trennzeichen, als auch in Form von relationalen Daten dargestellt, d. h. Tabellen mit Zeilen und Spalten. Der XML-Code in .NET Framework liest XML-Daten aus einem beliebigen Datenstrom in DOM-Knotenstrukturen (Dokumentobjektmodell) ein, wobei programmgesteuert auf Daten zugegriffen werden kann, während ADO.NET die Möglichkeiten für den Zugriff auf relationale Daten in einem <xref:System.Data.DataSet>-Objekt und die Bearbeitung dieser Daten bereitstellt.  
  
 Das XML-DOM ermöglicht Zugriff auf Daten in XML-Dokumenten und stellt zusätzliche Klassen zum Lesen, Schreiben und Navigieren in XML-Dokumenten bereit. Diese Klassen werden im <xref:System.Xml>-Namespace unterstützt, wodurch ebenfalls das XML-DOM mit den Datenzugriffsdiensten von ADO.NET zusammengeführt wird. <xref:System.Xml.XmlDataDocument> ermöglicht den relationalen Zugriff auf die Daten. Das <xref:System.Xml.XmlDataDocument> ordnet XML den relationalen Daten in einem ADO.NET-<xref:System.Data.DataSet> zu. .NET Framework-basierte Anwendungen können die Klassen im <xref:System.Xml>-Namespace verwenden, um sowohl auf XML-Dokumente als auch auf relationale Daten in <xref:System.Xml.XmlDataDocument> zuzugreifen und diese zu bearbeiten. Diese Implementierung unterstützt Architekturen mit n Ebenen für das Erfassen und Verteilen von Daten. Weitere Informationen finden Sie unter [XML-Integration mit relationalen Daten und ADO.NET](xml-integration-with-relational-data-and-adonet.md).  
  
## <a name="see-also"></a>Siehe auch

- [Implementierung des XSLT-Prozessors durch die XslTransform-Klasse](xsltransform-class-implements-the-xslt-processor.md)
