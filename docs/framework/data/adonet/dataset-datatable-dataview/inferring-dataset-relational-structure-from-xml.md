---
title: Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema
ms.date: 03/30/2017
ms.assetid: cd2f41c6-6785-420e-aa43-3ceb0bdccdce
ms.openlocfilehash: 9b1932807058777a532457c99efc49f3ddfdf4ae
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204801"
---
# <a name="inferring-dataset-relational-structure-from-xml"></a>Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema
Die relationale Struktur bzw. das Schema eines <xref:System.Data.DataSet> besteht aus Tabellen, Spalten, Einschränkungen und Beziehungen. Beim Laden eines <xref:System.Data.DataSet> aus XML kann das Schema vordefiniert sein oder explizit bzw. durch Rückschluss aus dem geladenen XML erstellt werden. Weitere Informationen zum Laden des Schemas und Inhalts eines <xref:System.Data.DataSet> aus XML finden Sie unter [Laden eines Datasets aus](loading-a-dataset-from-xml.md) XML und [Laden von DataSet-Schema Informationen aus XML](loading-dataset-schema-information-from-xml.md).  
  
 Wenn das Schema eines <xref:System.Data.DataSet> aus XML erstellt wird, ist die bevorzugte Methode das explizite Angeben des Schemas mithilfe der XML-Schema Definitions Sprache (XSD) (wie unter Ableiten der [relationalen DataSet-Struktur aus einem XML-Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)) oder der XML-Data Reduced (XDR). Falls in XML kein XML-Schema oder XDR-Schema verfügbar ist, kann das Schema des <xref:System.Data.DataSet> aus der Struktur der XML-Elemente und -Attribute hergeleitet werden.  
  
 In diesem Abschnitt werden anhand von XML-Elementen und -Attributen, ihrer Struktur und dem daraus hergeleiteten <xref:System.Data.DataSet>-Schema die Herleitungsregeln für <xref:System.Data.DataSet>-Schemata erläutert.  
  
 Nicht alle in einem XML-Dokument vorhandenen Attribute sollten in den Rückschlussprozess einbezogen werden. Namespace-qualifizierte Attribute enthalten häufig Metadaten, die zwar für das XML-Dokument wichtig sind, nicht jedoch für das <xref:System.Data.DataSet>-Schema. Mithilfe von <xref:System.Data.DataSet.InferXmlSchema%2A> legen Sie fest, dass bestimmte Namespaces beim Rückschlussprozess ignoriert werden. Weitere Informationen finden Sie unter [Laden von DataSet-Schema Informationen aus XML](loading-dataset-schema-information-from-xml.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Zusammenfassung des Rückschlussprozesses von DataSet-Schemas](summary-of-the-dataset-schema-inference-process.md)  
 Enthält eine Zusammenfassung der Regeln zur Herleitung des Schemas eines <xref:System.Data.DataSet> aus XML.  
  
 [Ableiten von Tabellen](inferring-tables.md)  
 Beschreibt die XML-Elemente, die als Tabellen in einem <xref:System.Data.DataSet> hergeleitet werden.  
  
 [Ableiten von Spalten](inferring-columns.md)  
 Beschreibt die XML-Elemente und -Attribute, die als Tabellenspalten hergeleitet werden.  
  
 [Ableiten von Beziehungen](inferring-relationships.md)  
 Beschreibt das <xref:System.Data.DataRelation>-Objekt und das <xref:System.Data.ForeignKeyConstraint>-Objekt, die beide für geschachtelte, hergeleitete Tabellen erstellt werden.  
  
 [Ableiten von Elementtext](inferring-element-text.md)  
 Beschreibt die für den Text in XML-Elementen erstellten Spalten und erläutert, wann der Text in XML-Elementen ignoriert wird.  
  
 [Rückschlusseinschränkungen](inference-limitations.md)  
 Behandelt die Einschränkungen der Schemaherleitung.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md)  
 Beschreibt die Interaktion zwischen dem <xref:System.Data.DataSet>-Objekt und XML-Daten.  
  
 [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Beschreibt die relationale Struktur bzw. das Schema eines <xref:System.Data.DataSet>, das aus einem XSD-Schema (XML Schema Definition Language) erstellt wird.  
  
 [Übersicht über ADO.NET](../ado-net-overview.md)  
 Beschreibt die ADO.NET-Architektur und -Komponenten und wie diese verwendet werden, um auf vorhandene Datenquellen zuzugreifen und Anwendungsdaten zu verwalten.  
  
## <a name="see-also"></a>Siehe auch

- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
