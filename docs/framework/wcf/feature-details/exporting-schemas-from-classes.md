---
title: Exportieren von Schemas aus Klassen
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, schema import and export
- schemas [WCF], exporting from classes
- schemas [WCF]
- XsdDataContractExporter class
- XsdDataContractImporter class
ms.assetid: bb57b962-70c1-45a9-93d5-e721e340a13f
ms.openlocfilehash: d356450af8ce6690e2142f3487e153bcde095324
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595517"
---
# <a name="exporting-schemas-from-classes"></a>Exportieren von Schemas aus Klassen
Verwenden Sie die <xref:System.Runtime.Serialization.XsdDataContractExporter> -Klasse, um XML-XSD-Schemas (Schema Definition Language) aus Klassen zu generieren, die im Datenvertragsmodell verwendet werden. In diesem Thema ist das Verfahren zum Erstellen von Schemas beschrieben.  
  
## <a name="the-export-process"></a>Der Exportprozess  
 Der Prozess zum Exportieren von Schemas beginnt mit einem oder mehreren Typen, und es wird ein <xref:System.Xml.Schema.XmlSchemaSet> erstellt, der die XML-Projektion dieser Typen beschreibt.  
  
 Der `XmlSchemaSet` ist Teil des Schema Objektmodells (SOM) des .NET Framework, das einen Satz von XSD-Schema Dokumenten darstellt. Um XSD-Dokumente aus einem `XmlSchemaSet`zu erstellen, verwenden Sie die Schemaauflistung aus der <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> -Eigenschaft der `XmlSchemaSet` -Klasse. Serialisieren Sie dann jedes <xref:System.Xml.Schema.XmlSchema> -Objekt mit dem <xref:System.Xml.Serialization.XmlSerializer>.  
  
#### <a name="to-export-schemas"></a>So exportieren Sie Schemas  
  
1. Erstellen Sie eine Instanz der <xref:System.Runtime.Serialization.XsdDataContractExporter>.  
  
2. Optional. Übergeben Sie im Konstruktor einen <xref:System.Xml.Schema.XmlSchemaSet> . In diesem Fall wird das während des Schemaexports generierte Schema dieser <xref:System.Xml.Schema.XmlSchemaSet> -Instanz hinzugefügt, anstatt mit einem leeren <xref:System.Xml.Schema.XmlSchemaSet>zu starten.  
  
3. Optional. Rufen Sie eine der <xref:System.Runtime.Serialization.XsdDataContractExporter.CanExport%2A> -Methoden auf. Die Methode bestimmt, ob der angegebene Typ exportiert werden kann. Die Methode verfügt über dieselben Überladungen wie die `Export` -Methode im nächsten Schritt.  
  
4. Rufen Sie eine der <xref:System.Runtime.Serialization.XsdDataContractExporter.Export%2A> -Methoden auf. Es sind drei Überladungen vorhanden, die einen <xref:System.Type>, eine <xref:System.Collections.Generic.List%601> mit `Type` -Objekten oder eine <xref:System.Collections.Generic.List%601> mit <xref:System.Reflection.Assembly> -Objekten erfordern. Im letzten Fall werden alle Typen in allen jeweiligen Assemblys exportiert.  
  
     Mehrere Aufrufe der `Export` -Methode führen dazu, dass mehrere Elemente demselben `XmlSchemaSet`hinzugefügt werden. Ein Typ wird nicht für den `XmlSchemaSet` generiert, wenn er darin bereits vorhanden ist. Aus diesem Grund ist das mehrfache Aufrufen von `Export` für denselben `XsdDataContractExporter` besser als das Erstellen mehrerer Instanzen der `XsdDataContractExporter` -Klasse. So wird vermieden, dass doppelte Schematypen generiert werden.  
  
    > [!NOTE]
    > Wenn beim Exportieren ein Fehler auftritt, befindet sich der `XmlSchemaSet` in einem unvorhersehbaren Zustand.  
  
5. Greifen Sie auf die <xref:System.Xml.Schema.XmlSchemaSet> mithilfe der <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas%2A> -Eigenschaft zu.  
  
## <a name="export-options"></a>Exportoptionen  
 Sie können die <xref:System.Runtime.Serialization.XsdDataContractExporter.Options%2A> -Eigenschaft des <xref:System.Runtime.Serialization.XsdDataContractExporter> auf eine Instanz der <xref:System.Runtime.Serialization.ExportOptions> -Klasse festlegen, um verschiedene Aspekte des Exportprozesses zu steuern. Dabei können Sie die folgenden Optionen festlegen:  
  
- <xref:System.Runtime.Serialization.ExportOptions.KnownTypes%2A>. Diese `Type` -Auflistung stellt die bekannten Typen für die zu exportierenden Typen dar. (Weitere Informationen finden Sie unter [Data Contract Known Types](data-contract-known-types.md).) Diese bekannten Typen werden bei jedem- `Export` Rückruf zusätzlich zu den Typen exportiert, die an die-Methode weitergegeben werden `Export` .  
  
- <xref:System.Runtime.Serialization.ExportOptions.DataContractSurrogate%2A>. Über diese Eigenschaft kann auch ein <xref:System.Runtime.Serialization.IDataContractSurrogate> -Element übergeben werden, das den Exportprozess anpasst. Weitere Informationen finden Sie unter [Data Contract Surrogates](../extending/data-contract-surrogates.md). Standardmäßig wird kein Ersatzzeichen verwendet.  
  
## <a name="helper-methods"></a>Hilfsmethoden  
 Zusätzlich zu seiner Hauptaufgabe, dem Exportieren des Schemas, bietet `XsdDataContractExporter` auch mehrere nützliche Hilfsmethoden, die Informationen zu Typen liefern. Dazu gehören:  
  
- <xref:System.Runtime.Serialization.XsdDataContractExporter.GetRootElementName%2A> -Methode. Diese Methode verwendet einen `Type` und gibt einen <xref:System.Xml.XmlQualifiedName> zurück, der den Stammelementnamen und den Namespace darstellt, der genutzt wird, wenn dieser Typ als Stammobjekt serialisiert wird.  
  
- <xref:System.Runtime.Serialization.XsdDataContractExporter.GetSchemaTypeName%2A> -Methode. Diese Methode verwendet einen `Type` und gibt einen <xref:System.Xml.XmlQualifiedName> zurück, der den Namen des XSD-Schematyps darstellt, der beim Exportieren dieses Typs genutzt wird. Für <xref:System.Xml.Serialization.IXmlSerializable> -Typen, die im Schema als anonyme Typen dargestellt werden, gibt diese Methode `null`zurück.  
  
- <xref:System.Runtime.Serialization.XsdDataContractExporter.GetSchemaType%2A> -Methode. Diese Methode funktioniert nur in Verbindung mit <xref:System.Xml.Serialization.IXmlSerializable> -Typen, die im Schema als anonyme Typen dargestellt werden, und gibt für alle anderen Typen `null` zurück. Für anonyme Typen gibt diese Methode einen <xref:System.Xml.Schema.XmlSchemaType> zurück, der einen bestimmten `Type`darstellt.  
  
 Exportoptionen wirken sich auf all diese Methoden aus.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.XsdDataContractImporter>
- <xref:System.Runtime.Serialization.XsdDataContractExporter>
- [Import und Export von Schemas](schema-import-and-export.md)
- [Importieren von Schemas zum Generieren von Klassen](importing-schema-to-generate-classes.md)
