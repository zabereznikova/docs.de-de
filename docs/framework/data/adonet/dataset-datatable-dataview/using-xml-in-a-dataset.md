---
title: Verwenden von XML in einem "DataSet"
ms.date: 03/30/2017
ms.assetid: 35138159-e199-49ec-baf7-1ec6777e171e
ms.openlocfilehash: e133da727887271af3bc5330a5779df4af58a37e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201186"
---
# <a name="using-xml-in-a-dataset"></a>Verwenden von XML in einem "DataSet"

Mit ADO.NET können Sie ein <xref:System.Data.DataSet> über einen XML-Stream oder ein XML-Dokument füllen. Die können den XML-Stream oder das XML-Dokument verwenden, um das <xref:System.Data.DataSet> mit Daten oder Schemainformationen oder mit beidem zu versorgen. Die vom XML-Stream oder vom XML-Dokument bereitgestellten Daten können mit vorhandenen Daten oder Schemainformationen kombiniert werden, die bereits im <xref:System.Data.DataSet> enthalten sind.  
  
 ADO.NET ermöglicht auch das Erstellen einer XML-Darstellung eines <xref:System.Data.DataSet> mit oder ohne zugehöriges Schema, damit das <xref:System.Data.DataSet> über HTTP übertragen und von anderen Anwendungen oder XML-fähigen Plattformen verwendet werden kann. Bei einer XML-Darstellung eines <xref:System.Data.DataSet> werden die Daten im XML-Format geschrieben, und das Schema wird, sofern es sich um ein Inlineschema handelt, mit XSD (XML Schema Definition Language) geschrieben. XML und das XML-Schema stellen ein komfortables Format zum Übertragen des <xref:System.Data.DataSet>-Inhalts an und von Remoteclients bereit.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [DiffGrams](diffgrams.md)  
 Bietet Einzelheiten zum DiffGram, einem XML-Format, das zum Lesen und Schreiben des Inhalts eines <xref:System.Data.DataSet> verwendet wird.  
  
 [Laden eines "DataSets" aus XML](loading-a-dataset-from-xml.md)  
 Beschreibt verschiedene Möglichkeiten beim Füllen eines <xref:System.Data.DataSet> mit einem XML-Dokument.  
  
 [Schreiben von DataSet-Inhalten als XML-Daten](writing-dataset-contents-as-xml-data.md)  
 Erläutert, wie der Inhalt eines <xref:System.Data.DataSet> als XML-Daten generiert wird und welche XML-Formatoptionen verwendet werden können.  
  
 [Laden von DataSet-Schemainformationen aus XML](loading-dataset-schema-information-from-xml.md)  
 Erläutert die <xref:System.Data.DataSet>-Methoden, die zum Laden des Schemas eines <xref:System.Data.DataSet> aus einem XML-Dokument verwendet werden.  
  
 [Schreiben von DataSet-Schemainformationen als XSD](writing-dataset-schema-information-as-xsd.md)  
 Erläutert, wie ein XML-Schema verwendet und aus einem <xref:System.Data.DataSet> generiert wird.  
  
 [DataSet- und XmlDataDocument-Synchronisierung](dataset-and-xmldatadocument-synchronization.md)  
 Erläutert die Möglichkeiten, die in .NET Framework für den synchronen Zugriff auf relationale und hierarchische Darstellungen eines einzigen Datensatzes zur Verfügung stehen. Darüber hinaus wird gezeigt, wie eine synchrone Beziehung zwischen einem <xref:System.Data.DataSet> und einem <xref:System.Xml.XmlDataDocument> erstellt werden kann.  
  
 [Verschachteln von "DataRelations"](nesting-datarelations.md)  
 Erläutert die Bedeutung geschachtelter <xref:System.Data.DataRelation>-Objekte beim Darstellen des Inhalts eines <xref:System.Data.DataSet> als XML-Daten und beschreibt deren Erstellung.  
  
 [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Beschreibt die relationale Struktur bzw. das Schema eines <xref:System.Data.DataSet>, das aus einem XML-Schema erstellt wird.  
  
 [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema](inferring-dataset-relational-structure-from-xml.md)  
 Beschreibt die resultierende relationale Struktur bzw. das Schema eines <xref:System.Data.DataSet>, das beim Herleiten aus XML-Elementen erstellt wird.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

 [Übersicht über ADO.NET](../ado-net-overview.md)  
 Beschreibt die ADO.NET-Architektur und -Komponenten und wie diese dazu verwendet werden, auf vorhandene Datenquellen zuzugreifen sowie Anwendungsdaten zu verwalten.  
  
## <a name="see-also"></a>Weitere Informationen

- ["DataSets", "DataTables" und "DataViews"](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
