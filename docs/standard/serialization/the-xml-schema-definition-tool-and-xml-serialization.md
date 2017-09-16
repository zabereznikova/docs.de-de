---
title: Das XML Schema Definition-Tool und die XML-Serialisierung
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
- Xsd.exe
- XML serialization, XML Schema Definition tool
- XML Schema Definition tool
- serialization, XML Schema Definition tool
ms.assetid: 3c03f855-f931-47ff-bbc6-50c0367a16e4
caps.latest.revision: 7
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 717bcb6f9f72a728d77e2847096ea558a9c50902
ms.openlocfilehash: c72269708526479d0e98cdfd694db57fe0d9e35e
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="the-xml-schema-definition-tool-and-xml-serialization"></a>Das XML Schema Definition-Tool und die XML-Serialisierung
Das XML Schema Definition-Tool ([XML Schema Definition-Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)) wird zusammen mit den .NET Framework-Tools als Bestandteil des Windows® Software Development Kit (SDK) installiert. Das Tool ist hauptsächlich für zwei Zwecke vorgesehen:  
  
-   Um C#- oder Visual Basic-Klassendateien zu erzeugen, die einem bestimmten XML-Schemadefinitionssprache (XSD-)-Schema. Das Tool übernimmt ein XML-Schema als Argument und gibt eine Datei mit einer Gruppe von Klassen aus, die dem Schema entsprechen, wenn sie mit <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden. Weitere Informationen dazu, wie mit diesem Tool Klassen erstellt werden, die einem bestimmten Schema entsprechen, finden Sie unter [Vorgehensweise: Mit dem XML Schema Definition-Tool Klassen und XML-Schemadokumente generieren](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).  
  
-   So generieren Sie ein XML-Schemadokument aus einer DLL-Datei oder EXE-Datei Um das Schema einer Gruppe von Dateien darzustellen, die Sie erstellt haben oder die mit Attributen verändert wurde, übergeben Sie dem Tool die DLL- oder EXE-Datei als Argument, um das XML-Schema zu generieren. Weitere Informationen dazu, wie mit diesem Tool ein XML-Schemadokument aus einer Gruppe von Klassen erzeugt wird, finden Sie unter [Vorgehensweise: Mit dem XML Schema Definition-Tool Klassen und XML-Schemadokumente generieren](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).  
  
 Weitere Informationen zu diesem und anderen Tools finden Sie unter [Tools](../../../docs/framework/tools/index.md). Informationen zu den Optionen in diesem Tool finden Sie unter [XML Schema Definition-Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Data.DataSet>   
 [Einführung in die XML-Serialisierung](../../../docs/standard/serialization/introducing-xml-serialization.md)   
 [XML Schema Definition-Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)   
 <xref:System.Xml.Serialization.XmlSerializer>   
 [Vorgehensweise: Serialisieren eines Objekts](../../../docs/standard/serialization/how-to-serialize-an-object.md)   
 [Vorgehensweise: Deserialisieren eines Objekts](../../../docs/standard/serialization/how-to-deserialize-an-object.md)   
 [Vorgehensweise: Mit dem XML Schema Definition-Tool Klassen und XML-Schemadokumente generieren](../../../docs/standard/serialization/xml-schema-def-tool-gen.md)   
 [Bindungsunterstützung für XML-Schema in .NET Framework](http://msdn.microsoft.com/en-us/8f0619dd-f1fc-4895-ae21-6d45d0382cc1)

