---
title: "Zuordnen von XSD-Einschr&#228;nkungen (XML-Schema) zu DataSet-Einschr&#228;nkungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Zuordnen von XSD-Einschr&#228;nkungen (XML-Schema) zu DataSet-Einschr&#228;nkungen
Die XSD\-Sprache \(XML Schema Definition Language\) ermöglicht Einschränkungen, die Sie für die Elemente und Attribute angeben können, die durch XSD definiert werden.  Beim Zuordnen eines XML\-Schemas zu einem relationalen Schema in einem <xref:System.Data.DataSet> werden XML\-Schemaeinschränkungen den entsprechenden relationalen Einschränkungen in den Tabellen und Spalten innerhalb des **DataSet** zugeordnet.  
  
 In diesem Abschnitt wird die Zuordnung der folgenden XML\-Schemaeinschränkungen behandelt:  
  
-   Die Eindeutigkeitseinschränkung, die mit dem **unique**\-Element angegeben wird.  
  
-   Die Schlüsseleinschränkung, die mit dem **key**\-Element angegeben wird.  
  
-   Die keyref\-Einschränkung, die mit dem **keyref**\-Element angegeben wird.  
  
 Mit einer Einschränkung für ein Element oder Attribut geben Sie bestimmte Beschränkungen für den Wert des Elements in einer beliebigen Instanz des Dokuments an.  Eine Schlüsseleinschränkung gibt beispielsweise für ein untergeordnetes Element **CustomerID** eines **Customer**\-Elements in einem Schema an, dass die Werte des untergeordneten Elements **CustomerID** in jeder Dokumentinstanz eindeutig sein müssen und Nullwerte nicht erlaubt sind.  
  
 Einschränkungen können auch zwischen Elementen und Attributen in einem Dokument angegeben werden, um eine Beziehung innerhalb des Dokuments zu erstellen.  Die key\-Einschränkung und die keyref\-Einschränkung werden im Schema verwendet, um Einschränkungen innerhalb des Dokuments anzugeben, die zu einer Beziehung zwischen Dokumentelementen und Attributen führen.  
  
 Der Zuordnungsprozess konvertiert diese Schemaeinschränkungen in die entsprechenden Einschränkungen in Tabellen, die innerhalb des **DataSet** erstellt werden.  
  
## In diesem Abschnitt  
 [Zuordnen eindeutiger XSD\-Einschränkungen \(XML\-Schema\) zu 'DataSet'\-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Beschreibt die zum Erstellen von unique\-Einschränkungen in einem **DataSet** verwendeten XML\-Schemaelemente.  
  
 [Zuordnen von XSD\-Schlüsseleinschränkungen \(XML\-Schema\) zu 'DataSet'\-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Beschreibt die XML\-Schemaelemente, mit denen die key\-Einschränkungen \(unique\-Einschränkungen, bei denen Nullwerte nicht erlaubt sind\) in einem **DataSet** erstellt werden.  
  
 [Zuordnen von XSD\-'keyref'\-Schlüsseleinschränkungen \(XML\-Schema\) zu DataSet\-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Beschreibt die XML\-Schemaelemente, mit denen keyref\-Einschränkungen \(Fremdschlüssel\) in einem **DataSet** erstellt werden.  
  
## Verwandte Abschnitte  
 [Ableiten einer relationalen 'DataSet'\-Struktur aus einem XML\-Schema \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Beschreibt die relationale Struktur oder das Schema eines **DataSet**, das aus einem XSD\-Schema erstellt wird.  
  
 [Generieren von DataSet\-Beziehungen aus einem XML\-Schema \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 Beschreibt die zum Erstellen von Beziehungen zwischen Tabellenspalten in einem **DataSet** verwendeten XML\-Schemaelemente.  
  
## Siehe auch  
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)