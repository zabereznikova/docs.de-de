---
title: Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen
ms.date: 03/30/2017
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
ms.openlocfilehash: a2b28b0dcb2e2858c7328854650667f51e83166a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185287"
---
# <a name="mapping-xml-schema-xsd-constraints-to-dataset-constraints"></a>Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen

Die XSD-Sprache (XML Schema Definition Language) ermöglicht Einschränkungen, die Sie für die Elemente und Attribute angeben können, die durch XSD definiert werden. Beim Zuordnen eines XML-Schemas zu einem relationalen Schema in einem <xref:System.Data.DataSet> werden XML-Schema Einschränkungen den entsprechenden relationalen Einschränkungen für die Tabellen und Spalten im **DataSet**zugeordnet.  
  
 In diesem Abschnitt wird die Zuordnung der folgenden XML-Schemaeinschränkungen behandelt:  
  
- Die Eindeutigkeits Einschränkung, die mit dem **Unique** -Element angegeben wird.  
  
- Die Schlüssel Einschränkung, die mit dem **Key** -Element angegeben wird.  
  
- Die keyref-Einschränkung, die mit dem **keyref** -Element angegeben wird.  
  
 Mit einer Einschränkung für ein Element oder Attribut geben Sie bestimmte Beschränkungen für den Wert des Elements in einer beliebigen Instanz des Dokuments an. Eine Schlüssel Einschränkung für ein untergeordnetes **CustomerID-** Element eines **Customer** -Elements im Schema gibt beispielsweise an, dass die Werte des untergeordneten **CustomerID-** Elements in jeder Dokument Instanz eindeutig sein müssen und dass NULL-Werte nicht zulässig sind.  
  
 Einschränkungen können auch zwischen Elementen und Attributen in einem Dokument angegeben werden, um eine Beziehung innerhalb des Dokuments zu erstellen. Die key-Einschränkung und die keyref-Einschränkung werden im Schema verwendet, um Einschränkungen innerhalb des Dokuments anzugeben, die zu einer Beziehung zwischen Dokumentelementen und Attributen führen.  
  
 Der Zuordnungsprozess konvertiert diese Schema Einschränkungen in entsprechende Einschränkungen für die Tabellen, die innerhalb des **DataSets**erstellt werden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Zuordnen von eindeutigen XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen](map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Beschreibt die XML-Schema Elemente, die verwendet werden, um UNIQUE-Einschränkungen in einem **DataSet**zu erstellen.  
  
 [Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen](map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Beschreibt die XML-Schema Elemente, mit denen Schlüssel Einschränkungen (Unique-Einschränkungen, bei denen NULL-Werte nicht zulässig sind) in einem **DataSet**erstellt werden.  
  
 [Zuordnen von keyref-XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen](map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Beschreibt die XML-Schema Elemente, die verwendet werden, um keyref-Einschränkungen (Foreign Key) in einem **DataSet**zu erstellen.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

 [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Beschreibt die relationale Struktur bzw. das Schema eines **DataSets** , das aus einem XSD-Schema erstellt wird.  
  
 [Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)  
 Beschreibt die XML-Schema Elemente, die verwendet werden, um Beziehungen zwischen Tabellen Spalten in einem **DataSet**zu erstellen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über ADO.NET](../ado-net-overview.md)
