---
title: 'Gewusst wie: Mit dem XML Schema Definition-Tool Klassen und XML-Schemadokumente generieren'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- generating XML classes using XML Schema Definition tool
- generating XML Schema Document using XML Schema Definition tool
- XML Schema Definition tool, using to generate classes that conform to specific schema
- XML Schema Definition tool, using to generate XML Schema Document
ms.assetid: 51f0edc3-993d-4051-b7f2-77753694d3d1
caps.latest.revision: 5
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 717bcb6f9f72a728d77e2847096ea558a9c50902
ms.openlocfilehash: 3d0d7a6fa5f8b6108567de02cfaec6f1fea71796
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-use-the-xml-schema-definition-tool-to-generate-classes-and-xml-schema-documents"></a>Gewusst wie: Mit dem XML Schema Definition-Tool Klassen und XML-Schemadokumente generieren
Mit dem XML-Schema Definition-Tool (Xsd.exe) können Sie ein XML-Schema generieren, das eine Klasse beschreibt, oder die Klasse generieren, die durch ein XML-Schema definiert wird. Die folgenden Verfahren zeigen, wie diese Vorgänge ausgeführt werden.  
  
### <a name="to-generate-classes-that-conform-to-a-specific-schema"></a>So generieren Sie Klassen, die einem bestimmten Schema entsprechen  
  
1.  Öffnen Sie eine Eingabeaufforderung.  
  
2.  Übergeben Sie dem XML Schema Definition-Tool das XML-Schema als Argument. Dieses Tool erzeugt eine Gruppe von Klassen, die dem XML-Schema genau entsprechen, zum Beispiel:  
  
    ```  
    xsd mySchema.xsd  
    ```  
  
     Das Tool kann nur Schemas verarbeiten, die auf die World Wide Web Consortium-XML-Spezifikation vom 16. März 2001 verweisen. Das bedeutet, der XML-Schemanamespace muss "http://www.w3.org/2001/XMLSchema" sein, wie im folgenden Beispiel dargestellt.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <xs:schema attributeFormDefault="qualified" elementFormDefault="qualified" targetNamespace="" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    ```  
  
3.  Ändern Sie die Klassen bei Bedarf mit Methoden, Eigenschaften oder Feldern. Weitere Informationen zum Ändern einer Klasse mithilfe von Attributen finden Sie unter [Steuern der XML-Serialisierung mit Attributen](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md) und [Attribute zur Steuerung der Serialisierung von codiertem SOAP](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).  
  
 Es ist oft sinnvoll, das Schema des XML-Streams zu überprüfen, der bei der Serialisierung von Instanzen der Klasse (oder Klassen) generiert wird. Sie veröffentlichen möglicherweise ein Schema, damit es andere Benutzer verwenden können, oder Sie vergleichen es mit einem Schema, mit dem Sie Konformität zu erreichen versuchen.  
  
#### <a name="to-generate-an-xml-schema-document-from-a-set-of-classes"></a>So generieren Sie ein XML-Schemadokument aus einer Gruppe von Klassen  
  
1.  Kompilieren Sie die Klasse oder die Klassen in eine DLL.  
  
2.  Öffnen Sie eine Eingabeaufforderung.  
  
3.  Übergeben Sie die DLL als Argument an Xsd.exe. Beispiel:  
  
    ```  
    xsd MyFile.dll  
    ```  
  
     Das Schema (oder die Schemas) wird/werden ausgegeben und mit Namen im Format "schema0.xsd" fortlaufend benannt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Data.DataSet>   
 [Das XML Schema Definition-Tool und die XML-Serialisierung](../../../docs/standard/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)   
 [Einführung in die XML-Serialisierung](../../../docs/standard/serialization/introducing-xml-serialization.md)   
 [XML Schema Definition-Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)   
 <xref:System.Xml.Serialization.XmlSerializer>   
 [Vorgehensweise: Serialisieren eines Objekts](../../../docs/standard/serialization/how-to-serialize-an-object.md)   
 [Vorgehensweise: Deserialisieren eines Objekts](../../../docs/standard/serialization/how-to-deserialize-an-object.md)

