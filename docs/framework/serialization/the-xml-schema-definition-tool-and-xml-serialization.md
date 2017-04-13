---
title: "Das XML Schema Definition-Tool und die XML-Serialisierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Xsd.exe"
  - "XML-Serialisierung, XML Schema Definition-Tool"
  - "XML Schema Definition-Tool"
  - "Serialisierung, XML Schema Definition-Tool"
ms.assetid: 3c03f855-f931-47ff-bbc6-50c0367a16e4
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Das XML Schema Definition-Tool und die XML-Serialisierung
Das XML Schema Definition\-Tool \([XML Schema Definition\-Tool \(Xsd.exe\)](../../../docs/framework/serialization/xml-schema-definition-tool-xsd-exe.md)\) wird zusammen mit den .NET Framework\-Tools als Bestandteil des Windows® Software Development Kit \(SDK\) installiert. Das Tool ist hauptsächlich für zwei Zwecke vorgesehen:  
  
-   Um C\#\- oder Visual Basic\-Klassendateien zu erstellen, die einer bestimmten XML\-Schema\-Definition \(XSD\) entsprechen. Das Tool übernimmt ein XML\-Schema als Argument und gibt eine Datei aus, die einige Klassen enthält, die dem Schema entsprechen, wenn die Klassen mit dem [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx) serialisiert wurden. Weitere Informationen dazu, wie mit diesem Tool Klassen erstellt werden, die einem bestimmten Schema entsprechen, finden Sie unter [Vorgehensweise: Mit dem XML Schema Definition\-Tool Klassen und XML\-Schemadokumente generieren](../../../docs/framework/serialization/xml-schema-def-tool-gen.md).  
  
-   So generieren Sie ein XML\-Schemadokument aus einer DLL\-Datei oder EXE\-Datei Um das Schema einer Gruppe von Dateien darzustellen, die Sie erstellt haben oder die mit Attributen verändert wurde, übergeben Sie dem Tool die DLL\- oder EXE\-Datei als Argument, um das XML\-Schema zu generieren. Weitere Informationen dazu, wie mit diesem Tool ein XML\-Schemadokument aus einer Gruppe von Klassen erzeugt wird, finden Sie unter [Vorgehensweise: Mit dem XML Schema Definition\-Tool Klassen und XML\-Schemadokumente generieren](../../../docs/framework/serialization/xml-schema-def-tool-gen.md).  
  
 Weitere Informationen zu diesem und anderen Tools finden Sie unter [Tools](../../../docs/framework/tools/index.md). Informationen zu den Optionen in diesem Tool finden Sie unter [XML Schema Definition\-Tool \(Xsd.exe\)](../../../docs/framework/serialization/xml-schema-definition-tool-xsd-exe.md).  
  
## Siehe auch  
 [Einführung in die XML\-Serialisierung](../../../docs/framework/serialization/introducing-xml-serialization.md)   
 [DataSet](frlrfSystemDataDataSetClassTopic)   
 [XML Schema Definition\-Tool \(Xsd.exe\)](../../../docs/framework/serialization/xml-schema-definition-tool-xsd-exe.md)   
 [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)   
 [Vorgehensweise: Serialisieren eines Objekts](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [Vorgehensweise: Deserialisieren eines Objekts](../../../docs/framework/serialization/how-to-deserialize-an-object.md)   
 [Vorgehensweise: Mit dem XML Schema Definition\-Tool Klassen und XML\-Schemadokumente generieren](../../../docs/framework/serialization/xml-schema-def-tool-gen.md)   
 [Bindungsunterstützung für XML\-Schema in .NET Framework](http://msdn.microsoft.com/de-de/8f0619dd-f1fc-4895-ae21-6d45d0382cc1)