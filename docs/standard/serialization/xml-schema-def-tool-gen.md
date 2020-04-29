---
title: 'Vorgehensweise: Generieren von Klassen und XML-Schemadokumenten mit dem XML Schema Definition-Tool'
ms.date: 03/30/2017
helpviewer_keywords:
- generating XML classes using XML Schema Definition tool
- generating XML Schema Document using XML Schema Definition tool
- XML Schema Definition tool, using to generate classes that conform to specific schema
- XML Schema Definition tool, using to generate XML Schema Document
ms.assetid: 51f0edc3-993d-4051-b7f2-77753694d3d1
ms.openlocfilehash: 2bbdced0f984b653a58afba9685683e8c0891271
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389803"
---
# <a name="how-to-use-the-xml-schema-definition-tool-to-generate-classes-and-xml-schema-documents"></a>Vorgehensweise: Generieren von Klassen und XML-Schemadokumenten mit dem XML Schema Definition-Tool
Mit dem XML-Schema Definition-Tool (Xsd.exe) können Sie ein XML-Schema generieren, das eine Klasse beschreibt, oder die Klasse generieren, die durch ein XML-Schema definiert wird. Die folgenden Verfahren zeigen, wie diese Vorgänge ausgeführt werden.

Das XML-Schemadefinitionstool (Xsd.exe) befindet sich in der Regel im folgenden Pfad:\
_C:\\Programme (x86)\\Microsoft SDKs\\Windows\\{Version}\\bin\\NETFX {Version} Tools\\_

### <a name="to-generate-classes-that-conform-to-a-specific-schema"></a>So generieren Sie Klassen, die einem bestimmten Schema entsprechen  
  
1. Öffnen Sie eine Eingabeaufforderung.  
  
2. Übergeben Sie dem XML Schema Definition-Tool das XML-Schema als Argument. Dieses Tool erzeugt eine Gruppe von Klassen, die dem XML-Schema genau entsprechen, zum Beispiel:  
  
    ```console  
    xsd mySchema.xsd  
    ```  
  
     Das Tool kann nur Schemas verarbeiten, die auf die World Wide Web Consortium-XML-Spezifikation vom 16. März 2001 verweisen. Das bedeutet, der XML-Schemanamespace muss „http://www.w3.org/2001/XMLSchema“ sein, wie im folgenden Beispiel gezeigt.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <xs:schema attributeFormDefault="qualified" elementFormDefault="qualified" targetNamespace="" xmlns:xs="http://www.w3.org/2001/XMLSchema" />  
    ```  
  
3. Ändern Sie die Klassen bei Bedarf mit Methoden, Eigenschaften oder Feldern. Weitere Informationen zum Ändern einer Klasse mithilfe von Attributen finden Sie unter [Steuern der XML-Serialisierung mit Attributen](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md) und [Attribute zur Steuerung der Serialisierung von codiertem SOAP](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).  
  
 Es ist oft sinnvoll, das Schema des XML-Streams zu überprüfen, der bei der Serialisierung von Instanzen der Klasse (oder Klassen) generiert wird. Sie veröffentlichen möglicherweise ein Schema, damit es andere Benutzer verwenden können, oder Sie vergleichen es mit einem Schema, mit dem Sie Konformität zu erreichen versuchen.  
  
#### <a name="to-generate-an-xml-schema-document-from-a-set-of-classes"></a>So generieren Sie ein XML-Schemadokument aus einer Gruppe von Klassen  
  
1. Kompilieren Sie die Klasse oder die Klassen in eine DLL.  
  
2. Öffnen Sie eine Eingabeaufforderung.  
  
3. Übergeben Sie die DLL als Argument an Xsd.exe. Beispiel:  
  
    ```console  
    xsd MyFile.dll  
    ```  
  
     Das Schema (oder die Schemas) wird/werden ausgegeben und mit Namen im Format "schema0.xsd" fortlaufend benannt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Data.DataSet>
- [Das XML Schema Definition-Tool und die XML-Serialisierung](../../../docs/standard/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)
- [Einführung in die XML-Serialisierung](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [XML Schema Definition-Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [How to: Serialisieren eines Objekts](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [How to: Deserialisieren eines Objekts](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
