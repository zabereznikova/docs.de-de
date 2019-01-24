---
title: Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema
ms.date: 03/30/2017
ms.assetid: cd2f41c6-6785-420e-aa43-3ceb0bdccdce
ms.openlocfilehash: f5cbbcd148f13a630398e870124803d482f63698
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587647"
---
# <a name="inferring-dataset-relational-structure-from-xml"></a>Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema
Die relationale Struktur bzw. das Schema eines <xref:System.Data.DataSet> besteht aus Tabellen, Spalten, Einschränkungen und Beziehungen. Beim Laden eines <xref:System.Data.DataSet> aus XML kann das Schema vordefiniert sein oder explizit bzw. durch Rückschluss aus dem geladenen XML erstellt werden. Für Weitere Informationen zum Laden des Schemas und Inhalts von einem <xref:System.Data.DataSet> aus XML finden Sie unter [Laden eines Datasets aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) und [Laden von DataSet-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md).  
  
 Wenn das Schema der einen <xref:System.Data.DataSet> erstellt wird aus XML ist die bevorzugte Methode explizit das Schema, verwenden entweder die XML-Schemadefinitionssprache (XSD) angeben (siehe [ableiten relationalen DataSet-Struktur von XML-Schema (XSD) ](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)) oder die XML-Data Reduced (XDR). Falls in XML kein XML-Schema oder XDR-Schema verfügbar ist, kann das Schema des <xref:System.Data.DataSet> aus der Struktur der XML-Elemente und -Attribute hergeleitet werden.  
  
 In diesem Abschnitt werden anhand von XML-Elementen und -Attributen, ihrer Struktur und dem daraus hergeleiteten <xref:System.Data.DataSet>-Schema die Herleitungsregeln für <xref:System.Data.DataSet>-Schemata erläutert.  
  
 Nicht alle in einem XML-Dokument vorhandenen Attribute sollten in den Rückschlussprozess einbezogen werden. Namespace-qualifizierte Attribute enthalten häufig Metadaten, die zwar für das XML-Dokument wichtig sind, nicht jedoch für das <xref:System.Data.DataSet>-Schema. Mithilfe von <xref:System.Data.DataSet.InferXmlSchema%2A> legen Sie fest, dass bestimmte Namespaces beim Rückschlussprozess ignoriert werden. Weitere Informationen finden Sie unter [Laden von DataSet-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Zusammenfassung des Rückschlussprozesses von DataSet-Schemas](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/summary-of-the-dataset-schema-inference-process.md)  
 Enthält eine Zusammenfassung der Regeln zur Herleitung des Schemas eines <xref:System.Data.DataSet> aus XML.  
  
 [Ableiten von Tabellen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md)  
 Beschreibt die XML-Elemente, die als Tabellen in einem <xref:System.Data.DataSet> hergeleitet werden.  
  
 [Ableiten von Spalten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-columns.md)  
 Beschreibt die XML-Elemente und -Attribute, die als Tabellenspalten hergeleitet werden.  
  
 [Ableiten von Beziehungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-relationships.md)  
 Beschreibt das <xref:System.Data.DataRelation>-Objekt und das <xref:System.Data.ForeignKeyConstraint>-Objekt, die beide für geschachtelte, hergeleitete Tabellen erstellt werden.  
  
 [Ableiten von Elementtext](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-element-text.md)  
 Beschreibt die für den Text in XML-Elementen erstellten Spalten und erläutert, wann der Text in XML-Elementen ignoriert wird.  
  
 [Rückschlusseinschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inference-limitations.md)  
 Behandelt die Einschränkungen der Schemaherleitung.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Using XML in a DataSet (Verwenden von XML in einem DataSet)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Beschreibt die Interaktion zwischen dem <xref:System.Data.DataSet>-Objekt und XML-Daten.  
  
 [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Beschreibt die relationale Struktur bzw. das Schema eines <xref:System.Data.DataSet>, das aus einem XSD-Schema (XML Schema Definition Language) erstellt wird.  
  
 [Übersicht über ADO.NET](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 Beschreibt die ADO.NET-Architektur und -Komponenten und wie diese verwendet werden, um auf vorhandene Datenquellen zuzugreifen und Anwendungsdaten zu verwalten.  
  
## <a name="see-also"></a>Siehe auch
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
