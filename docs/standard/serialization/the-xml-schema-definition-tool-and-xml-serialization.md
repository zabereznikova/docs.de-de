---
title: Das XML Schema Definition-Tool und die XML-Serialisierung
description: Das XML Schema Definition-Tool generiert C#- oder Visual Basic-Klassendateien für ein XSD-Schema und ein XML-Schema aus einer Bibliothek oder ausführbaren Datei.
ms.date: 03/30/2017
helpviewer_keywords:
- Xsd.exe
- XML serialization, XML Schema Definition tool
- XML Schema Definition tool
- serialization, XML Schema Definition tool
ms.assetid: 3c03f855-f931-47ff-bbc6-50c0367a16e4
ms.openlocfilehash: 6451f3b5f6e8ec2c1454e5cf7ffb95a96b620214
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554982"
---
# <a name="the-xml-schema-definition-tool-and-xml-serialization"></a><span data-ttu-id="1fb0a-103">Das XML Schema Definition-Tool und die XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="1fb0a-103">The XML Schema Definition Tool and XML Serialization</span></span>

<span data-ttu-id="1fb0a-104">Das XML Schema Definition-Tool ([XML Schema Definition-Tool (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md)) wird zusammen mit den .NET Framework-Tools als Bestandteil des Windows&reg; Software Development Kits (SDK) installiert.</span><span class="sxs-lookup"><span data-stu-id="1fb0a-104">The XML Schema Definition tool ([XML Schema Definition Tool (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md)) is installed along with the .NET Framework tools as part of the Windows&reg; Software Development Kit (SDK).</span></span> <span data-ttu-id="1fb0a-105">Das Tool ist hauptsächlich für zwei Zwecke vorgesehen:</span><span class="sxs-lookup"><span data-stu-id="1fb0a-105">The tool is designed primarily for two purposes:</span></span>  
  
- <span data-ttu-id="1fb0a-106">Um C#- oder Visual Basic-Klassendateien zu erstellen, die einer bestimmten XML-Schema-Definition (XSD) entsprechen.</span><span class="sxs-lookup"><span data-stu-id="1fb0a-106">To generate either C# or Visual Basic class files that conform to a specific XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="1fb0a-107">Das Tool übernimmt ein XML-Schema als Argument und gibt eine Datei mit einer Gruppe von Klassen aus, die dem Schema entsprechen, wenn sie mit <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="1fb0a-107">The tool takes an XML Schema as an argument and outputs a file that contains a number of classes that, when serialized with the <xref:System.Xml.Serialization.XmlSerializer>, conform to the schema.</span></span> <span data-ttu-id="1fb0a-108">Informationen dazu, wie mit diesem Tool Klassen erstellt werden, die einem bestimmten Schema entsprechen, finden Sie unter [Vorgehensweise: Generieren von Klassen und XML-Schemadokumenten mit dem XML Schema Definition-Tool](xml-schema-def-tool-gen.md).</span><span class="sxs-lookup"><span data-stu-id="1fb0a-108">For information about how to use the tool to generate classes that conform to a specific schema, see [How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents](xml-schema-def-tool-gen.md).</span></span>  
  
- <span data-ttu-id="1fb0a-109">So generieren Sie ein XML-Schemadokument aus einer DLL-Datei oder EXE-Datei</span><span class="sxs-lookup"><span data-stu-id="1fb0a-109">To generate an XML Schema document from a .dll file or .exe file.</span></span> <span data-ttu-id="1fb0a-110">Um das Schema einer Gruppe von Dateien darzustellen, die Sie erstellt haben oder die mit Attributen verändert wurde, übergeben Sie dem Tool die DLL- oder EXE-Datei als Argument, um das XML-Schema zu generieren.</span><span class="sxs-lookup"><span data-stu-id="1fb0a-110">To see the schema of a set of files that you have either created or one that has been modified with attributes, pass the DLL or EXE as an argument to the tool to generate the XML schema.</span></span> <span data-ttu-id="1fb0a-111">Informationen dazu, wie mit diesem Tool ein XML-Schemadokument aus einer Gruppe von Klassen erzeugt wird, finden Sie unter [Vorgehensweise: Generieren von Klassen und XML-Schemadokumenten mit dem XML Schema Definition-Tool](xml-schema-def-tool-gen.md).</span><span class="sxs-lookup"><span data-stu-id="1fb0a-111">For information about how to use the tool to generate an XML Schema Document from a set of classes, see [How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents](xml-schema-def-tool-gen.md).</span></span>  
  
<span data-ttu-id="1fb0a-112">Weitere Informationen zur Verwendung dieses Tools finden Sie unter [XML Schema Definition-Tool (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md).</span><span class="sxs-lookup"><span data-stu-id="1fb0a-112">For more information about using the tool, see [XML Schema Definition Tool (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fb0a-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1fb0a-113">See also</span></span>

- <xref:System.Data.DataSet>
- [<span data-ttu-id="1fb0a-114">Einführung in die XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="1fb0a-114">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- [<span data-ttu-id="1fb0a-115">XML Schema Definition-Tool (Xsd.exe)</span><span class="sxs-lookup"><span data-stu-id="1fb0a-115">XML Schema Definition Tool (Xsd.exe)</span></span>](xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- <span data-ttu-id="1fb0a-116">[How to: Serialisieren eines Objekts](how-to-serialize-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="1fb0a-116">[How to: Serialize an Object](how-to-serialize-an-object.md)</span></span>
- [<span data-ttu-id="1fb0a-117">How to: Deserialisieren eines Objekts</span><span class="sxs-lookup"><span data-stu-id="1fb0a-117">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)
- [<span data-ttu-id="1fb0a-118">How to: Generieren von Klassen und XML-Schemadokumenten mit dem XML Schema Definition-Tool</span><span class="sxs-lookup"><span data-stu-id="1fb0a-118">How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents</span></span>](xml-schema-def-tool-gen.md)
- <span data-ttu-id="1fb0a-119">[Bindungsunterstützung für XML-Schema](/previous-versions/dotnet/netframework-4.0/sh1e66zd(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1fb0a-119">[XML Schema Binding Support](/previous-versions/dotnet/netframework-4.0/sh1e66zd(v=vs.100))</span></span>
