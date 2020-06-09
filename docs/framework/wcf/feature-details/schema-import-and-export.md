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
ms.openlocfilehash: 942ade69d92d8a213f65a3a2e463b6924e2f986e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590214"
---
# <a name="schema-import-and-export"></a>Import und Export von Schemas
Windows Communication Foundation (WCF) umfasst ein neues Serialisierungsmodul, das <xref:System.Runtime.Serialization.DataContractSerializer> . Der `DataContractSerializer` übersetzt zwischen .NET Framework-Objekten und XML (in beide Richtungen). Zusätzlich zum Serialisierungsprogramm selbst enthält WCF zugehörige Schema Import-und Schema Export Mechanismen. *Schema* ist eine formale, genaue und maschinenlesbare Beschreibung der XML-Form, die vom Serialisierungsprogramm erzeugt wird oder auf die der Deserialisierer zugreifen kann. WCF verwendet die XML-Schema Definitions Sprache (XML Schema Definition Language, XSD) von World Wide Web Consortium (XML Schema Definition Language) als Schema Darstellung, die mit vielen Plattformen von Drittanbietern weitgehend interoperabel ist.  
  
 Die Schema Import Komponente <xref:System.Runtime.Serialization.XsdDataContractImporter> übernimmt ein XSD-Schema Dokument und generiert .NET Framework Klassen (normalerweise Daten Vertrags Klassen), sodass die serialisierten Formulare dem angegebenen Schema entsprechen.  
  
 Das folgende Schemafragment:  
  
 [!code-csharp[c_SchemaImportExport#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#8)]
 [!code-vb[c_SchemaImportExport#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#8)]  
  
 generiert beispielsweise den folgenden Typ (zugunsten einer besseren Lesbarkeit leicht vereinfacht).  
  
 [!code-csharp[c_SchemaImportExport#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#1)]
 [!code-vb[c_SchemaImportExport#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#1)]  
  
 Beachten Sie, dass der generierte Typ verschiedene bewährte Methoden für Datenverträge befolgt (finden Sie unter [bewährte Methoden: Data Contract Versioning](../best-practices-data-contract-versioning.md)):  
  
- Der Typ implementiert die <xref:System.Runtime.Serialization.IExtensibleDataObject>-Schnittstelle. Weitere Informationen finden Sie unter [Aufwärtskompatible Datenverträge](forward-compatible-data-contracts.md).  
  
- Datenmember werden als öffentliche Eigenschaften implementiert, die private Felder umschließen.  
  
- Die Klasse ist eine partielle Klasse, und Hinzufügungen können vorgenommen werden, ohne generierten Code zu ändern.  
  
 Mit <xref:System.Runtime.Serialization.XsdDataContractExporter> können Sie umgekehrt verfahren und anhand von Typen, die mit `DataContractSerializer` serialisierbar sind, ein XSD-Schemadokument generieren.  
  
## <a name="fidelity-is-not-guaranteed"></a>Keine Garantie für die Originaltreue  
 Bei einem Roundtrip wird keine Garantie für die Originaltreue von Schemas oder Typen übernommen. (Ein *Roundtrip* bedeutet, dass Sie ein Schema importieren, um einen Satz von Klassen zu erstellen, und das Ergebnis exportieren, um erneut ein Schema zu erstellen.) Das gleiche Schema kann nicht zurückgegeben werden. Auch bei der Umkehrung des Prozesses ist eine Beibehaltung der Originaltreue nicht garantiert. (Exportieren Sie einen Typ, um sein Schema zu generieren, und importieren Sie den Typ dann wieder zurück. Es ist unwahrscheinlich, dass der gleiche Typ zurückgegeben wird.)  
  
## <a name="supported-types"></a>Unterstützte Typen  
 Das Datenvertragsmodell unterstützt nur eine beschränkte Teilmenge des WC3-Schemas. Jedes Schema, das dieser Teilmenge nicht entspricht, verursacht während des Importprozesses eine Ausnahme. Es gibt beispielsweise keine Möglichkeit festzulegen, dass ein Datenmember eines Datenvertrags als XML-Attribut serialisiert werden soll. Schemas, die XML-Attribute erfordern, werden daher nicht unterstützt und verursachen beim Import Ausnahmen, da es nicht möglich ist, einen Datenvertrag mit der richtigen XML-Projektion zu generieren.  
  
 Das folgende Schemafragment kann z. B. nicht mit den Standardimporteinstellungen importiert werden.  
  
 [!code-xml[c_SchemaImportExport#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#9)]  
  
 Weitere Informationen finden Sie unter [Daten Vertrags Schema-Referenz](data-contract-schema-reference.md). Wenn ein Schema den Datenvertragsregeln nicht entspricht, verwenden Sie eine andere Serialisierungs-Engine. <xref:System.Xml.Serialization.XmlSerializer> verwendet z. B. einen eigenen separaten Schemaimportmechanismus. Außerdem gibt es einen speziellen Importmodus, durch den weitere Schemas unterstützt werden. Weitere Informationen finden Sie im Abschnitt über das Generieren von <xref:System.Xml.Serialization.IXmlSerializable> Typen in [Importieren von Schemas zum Generieren von Klassen](importing-schema-to-generate-classes.md).  
  
 `XsdDataContractExporter`Unterstützt alle .NET Framework Typen, die mit serialisiert werden können `DataContractSerializer` . Weitere Informationen finden Sie [unter vom Datenvertragsserialisierer unterstützte Typen](types-supported-by-the-data-contract-serializer.md). Beachten Sie, dass mit `XsdDataContractExporter` generierte Schemas normalerweise gültige Daten sind, die von `XsdDataContractImporter` verwendet werden können (sofern <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> nicht zur Anpassung des Schemas verwendet wird).  
  
 Weitere Informationen zum Verwenden von <xref:System.Runtime.Serialization.XsdDataContractImporter> finden Sie unter [Importieren von Schemas zum Generieren von Klassen](importing-schema-to-generate-classes.md).  
  
 Weitere Informationen zum verwenden <xref:System.Runtime.Serialization.XsdDataContractExporter> von finden Sie unter [Exportieren von Schemas aus Klassen](exporting-schemas-from-classes.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.XsdDataContractImporter>
- <xref:System.Runtime.Serialization.XsdDataContractExporter>
- [Importieren von Schemas zum Generieren von Klassen](importing-schema-to-generate-classes.md)
- [Exportieren von Schemas aus Klassen](exporting-schemas-from-classes.md)
