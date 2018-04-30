---
title: Import und Export von Schemas
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, schema import and export
- XsdDataContractExporter class
- XsdDataContractImporter class
ms.assetid: 0da32b50-ccd9-463a-844c-7fe803d3bf44
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fe4ef5b17013bf1a9abf5fd1ca0807fe4d335df4
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="schema-import-and-export"></a>Import und Export von Schemas
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] umfasst ein neues Serialisierungsmodul, <xref:System.Runtime.Serialization.DataContractSerializer>. `DataContractSerializer` übersetzt zwischen [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Objekten und XML (in beide Richtungen). Zusätzlich zum Serialisierungsprogramm umfasst [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zugeordnete Mechanismen zum Schemaimport und -export. *Schema* ist eine formale, genaue und maschinenlesbare Beschreibung der Form des XML-Codes, die die Serialisierung erstellt oder auf die das Deserialisierungsprogramm zugreifen kann. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet die vom World Wide Web Consortium (W3C) definierte Sprache XML Schema Definition (XSD) zur Schemadarstellung. Diese Sprache ist mit zahlreichen Plattformen von Drittanbietern weitgehend interoperabel.  
  
 Die Schemaimportkomponente <xref:System.Runtime.Serialization.XsdDataContractImporter> generiert anhand eines XSD-Schemadokuments [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Klassen (normalerweise Datenvertragsklassen), sodass die serialisierten Formen dem angegebenen Schema entsprechen.  
  
 Das folgende Schemafragment:  
  
 [!code-csharp[c_SchemaImportExport#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#8)]
 [!code-vb[c_SchemaImportExport#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#8)]  
  
 generiert beispielsweise den folgenden Typ (zugunsten einer besseren Lesbarkeit leicht vereinfacht).  
  
 [!code-csharp[c_SchemaImportExport#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#1)]
 [!code-vb[c_SchemaImportExport#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#1)]  
  
 Beachten Sie, dass der generierte Typ mehreren empfohlenen Vorgehensweisen für Datenverträge folgt (gefunden [Vorgehensweisen: versionsverwaltung von Datenverträgen](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)):  
  
-   Der Typ implementiert die <xref:System.Runtime.Serialization.IExtensibleDataObject>-Schnittstelle. Weitere Informationen finden Sie unter [Aufwärtskompatible Datenverträge](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).  
  
-   Datenmember werden als öffentliche Eigenschaften implementiert, die private Felder umschließen.  
  
-   Die Klasse ist eine partielle Klasse, und Hinzufügungen können vorgenommen werden, ohne generierten Code zu ändern.  
  
 Mit <xref:System.Runtime.Serialization.XsdDataContractExporter> können Sie umgekehrt verfahren und anhand von Typen, die mit `DataContractSerializer` serialisierbar sind, ein XSD-Schemadokument generieren.  
  
## <a name="fidelity-is-not-guaranteed"></a>Keine Garantie für die Originaltreue  
 Bei einem Roundtrip wird keine Garantie für die Originaltreue von Schemas oder Typen übernommen. (Ein *Roundtrip-* wird der import eines Schemas zum Erstellen einer Gruppe von Klassen und export des Ergebnisses zum Erstellen eines Schemas bezeichnet.) Das gleiche Schema wird möglicherweise nicht zurückgegeben. Auch bei der Umkehrung des Prozesses ist eine Beibehaltung der Originaltreue nicht garantiert. (Exportieren Sie einen Typ, um sein Schema zu generieren, und importieren Sie den Typ dann wieder zurück. Es ist unwahrscheinlich, dass der gleiche Typ zurückgegeben wird.)  
  
## <a name="supported-types"></a>Unterstützte Typen  
 Das Datenvertragsmodell unterstützt nur eine beschränkte Teilmenge des WC3-Schemas. Jedes Schema, das dieser Teilmenge nicht entspricht, verursacht während des Importprozesses eine Ausnahme. Es gibt beispielsweise keine Möglichkeit festzulegen, dass ein Datenmember eines Datenvertrags als XML-Attribut serialisiert werden soll. Schemas, die XML-Attribute erfordern, werden daher nicht unterstützt und verursachen beim Import Ausnahmen, da es nicht möglich ist, einen Datenvertrag mit der richtigen XML-Projektion zu generieren.  
  
 Das folgende Schemafragment kann z. B. nicht mit den Standardimporteinstellungen importiert werden.  
  
 [!code-xml[c_SchemaImportExport#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#9)]  
  
 Weitere Informationen finden Sie unter [Datenvertrags-Schemareferenz](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md). Wenn ein Schema den Datenvertragsregeln nicht entspricht, verwenden Sie ein anderes Serialisierungsmodul. <xref:System.Xml.Serialization.XmlSerializer> verwendet z. B. einen eigenen separaten Schemaimportmechanismus. Außerdem gibt es einen speziellen Importmodus, der die Bandbreite unterstützter Schemata erweitert. Weitere Informationen finden Sie im Abschnitt zum Generieren von <xref:System.Xml.Serialization.IXmlSerializable> Typen im [Importieren von Schemas zum Generieren von Klassen](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md).  
  
 `XsdDataContractExporter` unterstützt alle [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Typen, die mit `DataContractSerializer` serialisiert werden können. Weitere Informationen finden Sie unter [Typen unterstützt, durch den Datenvertragsserialisierer](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md). Beachten Sie, dass mit `XsdDataContractExporter` generierte Schemas normalerweise gültige Daten sind, die von `XsdDataContractImporter` verwendet werden können (sofern <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> nicht zur Anpassung des Schemas verwendet wird).  
  
 Weitere Informationen zum Verwenden der <xref:System.Runtime.Serialization.XsdDataContractImporter>, finden Sie unter [Importieren von Schemas zum Generieren von Klassen](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md).  
  
 Weitere Informationen zum Verwenden der <xref:System.Runtime.Serialization.XsdDataContractExporter>, finden Sie unter [Exportieren von Schemas aus Klassen](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.Runtime.Serialization.XsdDataContractImporter>  
 <xref:System.Runtime.Serialization.XsdDataContractExporter>  
 [Importieren von Schemas zum Generieren von Klassen](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md)  
 [Exportieren von Schemas aus Klassen](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md)
