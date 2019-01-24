---
title: Das XML Schema Definition-Tool und die XML-Serialisierung
ms.date: 03/30/2017
helpviewer_keywords:
- Xsd.exe
- XML serialization, XML Schema Definition tool
- XML Schema Definition tool
- serialization, XML Schema Definition tool
ms.assetid: 3c03f855-f931-47ff-bbc6-50c0367a16e4
ms.openlocfilehash: abd96b7fab18b0fac18a2da791e5da8015d481c9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623806"
---
# <a name="the-xml-schema-definition-tool-and-xml-serialization"></a>Das XML Schema Definition-Tool und die XML-Serialisierung
Das XML Schema Definition-Tool ([XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)) wird zusammen mit den .NET Framework-Tools als Bestandteil des Windows® Software Development Kit (SDK) installiert. Das Tool ist hauptsächlich für zwei Zwecke vorgesehen:  
  
-   Um C#- oder Visual Basic-Klassendateien zu erzeugen, die einem bestimmten XML-Schemadefinitionssprache (XSD-)-Schema. Das Tool übernimmt ein XML-Schema als Argument und gibt eine Datei mit einer Gruppe von Klassen aus, die dem Schema entsprechen, wenn sie mit <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden. Weitere Informationen zur Verwendung mit dem Tool zum Generieren von Klassen, die einem bestimmten Schema entsprechen, finden Sie unter [Vorgehensweise: Verwenden Sie die XML-Schema Definition-Tool Klassen und XML-Schemadokumente generieren](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).  
  
-   So generieren Sie ein XML-Schemadokument aus einer DLL-Datei oder EXE-Datei Um das Schema einer Gruppe von Dateien darzustellen, die Sie erstellt haben oder die mit Attributen verändert wurde, übergeben Sie dem Tool die DLL- oder EXE-Datei als Argument, um das XML-Schema zu generieren. Informationen dazu, wie Sie das Tool zu verwenden, um ein XML-Schemadokument aus einer Reihe von Klassen zu generieren, finden Sie unter [Vorgehensweise: Verwenden Sie die XML-Schema Definition-Tool Klassen und XML-Schemadokumente generieren](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).  
  
 Weitere Informationen zu diesem und anderen Tools finden Sie unter [Tools](../../../docs/framework/tools/index.md). Informationen zu den Optionen in diesem Tool finden Sie unter [XML Schema Definition-Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Data.DataSet>
- [Einführung in die XML-Serialisierung](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [XML Schema Definition-Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [Vorgehensweise: Serialisieren eines Objekts](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [Vorgehensweise: Deserialisieren eines Objekts](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
- [Vorgehensweise: Verwenden Sie die XML-Schema Definition-Tool Klassen und XML-Schemadokumente generieren](../../../docs/standard/serialization/xml-schema-def-tool-gen.md)
- [Bindungsunterstützung für XML-Schema in .NET Framework](https://msdn.microsoft.com/library/8f0619dd-f1fc-4895-ae21-6d45d0382cc1)
