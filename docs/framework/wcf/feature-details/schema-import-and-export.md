---
title: "Import und Export von Schemas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF, Import und Export von Schemas"
  - "XsdDataContractExporter-Klasse"
  - "XsdDataContractImporter-Klasse"
ms.assetid: 0da32b50-ccd9-463a-844c-7fe803d3bf44
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Import und Export von Schemas
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]enthält ein neues Serialisierungsmodul, das <xref:System.Runtime.Serialization.DataContractSerializer>. `DataContractSerializer` übersetzt zwischen [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Objekten und XML (in beide Richtungen). Zusätzlich zum Serialisierungsprogramm umfasst [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zugeordnete Mechanismen zum Schemaimport und -export. *Schema* ist eine formale, genaue und maschinenlesbare Beschreibung der XML-Form, die die Serialisierung erstellt oder die das Deserialisierungsprogramm zugreifen kann. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet die vom World Wide Web Consortium (W3C) definierte Sprache XML Schema Definition (XSD) zur Schemadarstellung. Diese Sprache ist mit zahlreichen Plattformen von Drittanbietern weitgehend interoperabel.  
  
 Die schemaimportkomponente <xref:System.Runtime.Serialization.XsdDataContractImporter>, anhand eines XSD-Schemadokuments und generiert [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Klassen (normalerweise datenvertragsklassen), dass die serialisierten Formen dem angegebenen Schema entsprechen.  
  
 Das folgende Schemafragment:  
  
 [!code-csharp[c_SchemaImportExport#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#8)]
 [!code-vb[c_SchemaImportExport#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#8)]  
  
 generiert beispielsweise den folgenden Typ (zugunsten einer besseren Lesbarkeit leicht vereinfacht).  
  
 [!code-csharp[c_SchemaImportExport#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#1)]
 [!code-vb[c_SchemaImportExport#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#1)]  
  
 Beachten Sie, dass der generierte Typ mehreren empfohlenen Vorgehensweisen für Datenverträge folgt (finden Sie in [Best Practices: Datenvertragsversionsverwaltung](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)):  
  
-   Der Typ implementiert die <xref:System.Runtime.Serialization.IExtensibleDataObject> Schnittstelle. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Aufwärtskompatible Datenverträge](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).  
  
-   Datenmember werden als öffentliche Eigenschaften implementiert, die private Felder umschließen.  
  
-   Die Klasse ist eine partielle Klasse, und Hinzufügungen können vorgenommen werden, ohne generierten Code zu ändern.  
  
 Die <xref:System.Runtime.Serialization.XsdDataContractExporter> ermöglicht es Ihnen, den umgekehrten Vorgang – anhand von Typen, die serialisierbar sind mit den `DataContractSerializer` und generieren Sie ein XSD-Schema-Dokument.  
  
## <a name="fidelity-is-not-guaranteed"></a>Keine Garantie für die Originaltreue  
 Bei einem Roundtrip wird keine Garantie für die Originaltreue von Schemas oder Typen übernommen. (Ein *Roundtrip* import ein Schemas zum Erstellen einer Reihe von Klassen und export des Ergebnisses zum Erstellen eines Schemas bezeichnet.) Das gleiche Schema wird möglicherweise nicht zurückgegeben. Auch bei der Umkehrung des Prozesses ist eine Beibehaltung der Originaltreue nicht garantiert. (Exportieren Sie einen Typ, um sein Schema zu generieren, und importieren Sie den Typ dann wieder zurück. Es ist unwahrscheinlich, dass der gleiche Typ zurückgegeben wird.)  
  
## <a name="supported-types"></a>Unterstützte Typen  
 Das Datenvertragsmodell unterstützt nur eine beschränkte Teilmenge des WC3-Schemas. Jedes Schema, das dieser Teilmenge nicht entspricht, verursacht während des Importprozesses eine Ausnahme. Es gibt beispielsweise keine Möglichkeit festzulegen, dass ein Datenmember eines Datenvertrags als XML-Attribut serialisiert werden soll. Schemas, die XML-Attribute erfordern, werden daher nicht unterstützt und verursachen beim Import Ausnahmen, da es nicht möglich ist, einen Datenvertrag mit der richtigen XML-Projektion zu generieren.  
  
 Das folgende Schemafragment kann z. B. nicht mit den Standardimporteinstellungen importiert werden.  
  
 [!code[c_SchemaImportExport#9](../../../../samples/snippets/common/VS_Snippets_CFX/c_schemaimportexport/common/source.config#9)]  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Datenvertrags-Schemareferenz](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md). Wenn ein Schema den Datenvertragsregeln nicht entspricht, verwenden Sie ein anderes Serialisierungsmodul. Zum Beispiel die <xref:System.Xml.Serialization.XmlSerializer> einen eigenen separaten schemaimportmechanismus. Außerdem gibt es einen speziellen Importmodus, der die Bandbreite unterstützter Schemata erweitert. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]im Abschnitt zum Generieren von <xref:System.Xml.Serialization.IXmlSerializable> Typen in [Importieren von Schemas zum Generieren von Klassen](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md).  
  
 `XsdDataContractExporter` unterstützt alle [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Typen, die mit `DataContractSerializer` serialisiert werden können. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Vom Datenvertragsserialisierer unterstützte Typen](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md). Beachten Sie dieses Schema generiert, mit der `XsdDataContractExporter` normalerweise gültige Daten, die `XsdDataContractImporter` können (es sei denn, die <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> wird verwendet, um das Schema anpassen).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Mithilfe der <xref:System.Runtime.Serialization.XsdDataContractImporter>, finden Sie unter [Importieren von Schemas zum Generieren von Klassen](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Mithilfe der <xref:System.Runtime.Serialization.XsdDataContractExporter>, finden Sie unter [Exportieren von Schemas aus Klassen](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 <xref:System.Runtime.Serialization.XsdDataContractImporter>   
 <xref:System.Runtime.Serialization.XsdDataContractExporter>   
 [Importieren von Schemas zum Generieren von Klassen](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md)   
 [Exportieren von Schemas aus Klassen](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md)