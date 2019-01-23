---
title: Import und Export von Schemas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, schema import and export
- XsdDataContractExporter class
- XsdDataContractImporter class
ms.assetid: 0da32b50-ccd9-463a-844c-7fe803d3bf44
ms.openlocfilehash: 0529f112192fa64746d8c6dc7a49433b33bafbf5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527717"
---
# <a name="schema-import-and-export"></a>Import und Export von Schemas
Windows Communication Foundation (WCF) umfasst eine neue Serialisierungs-Engine, die <xref:System.Runtime.Serialization.DataContractSerializer>. `DataContractSerializer` übersetzt zwischen [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Objekten und XML (in beide Richtungen). Zusätzlich zum Serialisierungsprogramm selbst enthält WCF zugeordneten Schema-Import / Export-Mechanismen Schema. *Schema* ist eine formale, genaue und maschinenlesbare Beschreibung der Form des XML-Codes, die das Serialisierungsprogramm erstellt oder auf das Deserialisierungsprogramm zugreifen kann. WCF verwendet die World Wide Web Consortium (W3C) XML-Schemadefinitionssprache (XSD) als schemadarstellung, die mit zahlreichen Plattformen von Drittanbietern weitgehend interoperabel ist.  
  
 Die Schemaimportkomponente <xref:System.Runtime.Serialization.XsdDataContractImporter> generiert anhand eines XSD-Schemadokuments [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Klassen (normalerweise Datenvertragsklassen), sodass die serialisierten Formen dem angegebenen Schema entsprechen.  
  
 Das folgende Schemafragment:  
  
 [!code-csharp[c_SchemaImportExport#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#8)]
 [!code-vb[c_SchemaImportExport#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#8)]  
  
 generiert beispielsweise den folgenden Typ (zugunsten einer besseren Lesbarkeit leicht vereinfacht).  
  
 [!code-csharp[c_SchemaImportExport#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#1)]
 [!code-vb[c_SchemaImportExport#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#1)]  
  
 Beachten Sie, dass der generierte Typ mehreren empfohlenen Vorgehensweisen für Datenverträge folgt (finden Sie im [Best Practices: Versionsverwaltung von Datenverträgen](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)):  
  
-   Der Typ implementiert die <xref:System.Runtime.Serialization.IExtensibleDataObject>-Schnittstelle. Weitere Informationen finden Sie unter [Aufwärtskompatible Datenverträge](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).  
  
-   Datenmember werden als öffentliche Eigenschaften implementiert, die private Felder umschließen.  
  
-   Die Klasse ist eine partielle Klasse, und Hinzufügungen können vorgenommen werden, ohne generierten Code zu ändern.  
  
 Mit <xref:System.Runtime.Serialization.XsdDataContractExporter> können Sie umgekehrt verfahren und anhand von Typen, die mit `DataContractSerializer` serialisierbar sind, ein XSD-Schemadokument generieren.  
  
## <a name="fidelity-is-not-guaranteed"></a>Keine Garantie für die Originaltreue  
 Bei einem Roundtrip wird keine Garantie für die Originaltreue von Schemas oder Typen übernommen. (Ein *Roundtrip* Mittel zum Importieren eines Schemas zum Erstellen einer Reihe von Klassen und zum export des Ergebnisses zum Erstellen eines Schemas.) Das gleiche Schema wird möglicherweise nicht zurückgegeben. Auch bei der Umkehrung des Prozesses ist eine Beibehaltung der Originaltreue nicht garantiert. (Exportieren Sie einen Typ, um sein Schema zu generieren, und importieren Sie den Typ dann wieder zurück. Es ist unwahrscheinlich, dass der gleiche Typ zurückgegeben wird.)  
  
## <a name="supported-types"></a>Unterstützte Typen  
 Das Datenvertragsmodell unterstützt nur eine beschränkte Teilmenge des WC3-Schemas. Jedes Schema, das dieser Teilmenge nicht entspricht, verursacht während des Importprozesses eine Ausnahme. Es gibt beispielsweise keine Möglichkeit festzulegen, dass ein Datenmember eines Datenvertrags als XML-Attribut serialisiert werden soll. Schemas, die XML-Attribute erfordern, werden daher nicht unterstützt und verursachen beim Import Ausnahmen, da es nicht möglich ist, einen Datenvertrag mit der richtigen XML-Projektion zu generieren.  
  
 Das folgende Schemafragment kann z. B. nicht mit den Standardimporteinstellungen importiert werden.  
  
 [!code-xml[c_SchemaImportExport#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#9)]  
  
 Weitere Informationen finden Sie unter [Datenvertrags-Schemareferenz](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md). Wenn ein Schema den Datenvertragsregeln nicht entspricht, verwenden Sie eine andere Serialisierungs-Engine. <xref:System.Xml.Serialization.XmlSerializer> verwendet z. B. einen eigenen separaten Schemaimportmechanismus. Außerdem gibt es einen speziellen Importmodus, der die Bandbreite unterstützter Schemata erweitert. Weitere Informationen finden Sie im Abschnitt zum Generieren von <xref:System.Xml.Serialization.IXmlSerializable> Typen im [Importieren von Schemas zum Generieren von Klassen](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md).  
  
 `XsdDataContractExporter` unterstützt alle [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Typen, die mit `DataContractSerializer` serialisiert werden können. Weitere Informationen finden Sie unter [Types Supported by the Data Contract Serializer](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md). Beachten Sie, dass mit `XsdDataContractExporter` generierte Schemas normalerweise gültige Daten sind, die von `XsdDataContractImporter` verwendet werden können (sofern <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> nicht zur Anpassung des Schemas verwendet wird).  
  
 Weitere Informationen zur Verwendung der <xref:System.Runtime.Serialization.XsdDataContractImporter>, finden Sie unter [Importieren von Schemas zum Generieren von Klassen](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md).  
  
 Weitere Informationen zur Verwendung der <xref:System.Runtime.Serialization.XsdDataContractExporter>, finden Sie unter [Exportieren von Schemas aus Klassen](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.XsdDataContractImporter>
- <xref:System.Runtime.Serialization.XsdDataContractExporter>
- [Importieren von Schemas zum Generieren von Klassen](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md)
- [Exportieren von Schemas aus Klassen](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md)
