---
title: Das XML Schema Definition-Tool und die XML-Serialisierung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Xsd.exe
- XML serialization, XML Schema Definition tool
- XML Schema Definition tool
- serialization, XML Schema Definition tool
ms.assetid: 3c03f855-f931-47ff-bbc6-50c0367a16e4
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 67451a30e5681718e5b9cdd07468ac5bf20322bc
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="the-xml-schema-definition-tool-and-xml-serialization"></a><span data-ttu-id="bb76d-102">Das XML Schema Definition-Tool und die XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="bb76d-102">The XML Schema Definition Tool and XML Serialization</span></span>
<span data-ttu-id="bb76d-103">Das XML Schema Definition-Tool ([XML Schema Definition-Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)) wird zusammen mit den .NET Framework-Tools als Bestandteil des Windows® Software Development Kit (SDK) installiert.</span><span class="sxs-lookup"><span data-stu-id="bb76d-103">The XML Schema Definition tool ([XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)) is installed along with the .NET Framework tools as part of the Windows® Software Development Kit (SDK).</span></span> <span data-ttu-id="bb76d-104">Das Tool ist hauptsächlich für zwei Zwecke vorgesehen:</span><span class="sxs-lookup"><span data-stu-id="bb76d-104">The tool is designed primarily for two purposes:</span></span>  
  
-   <span data-ttu-id="bb76d-105">Um C#- oder Visual Basic-Klassendateien zu erzeugen, die einem bestimmten XML-Schemadefinitionssprache (XSD-)-Schema.</span><span class="sxs-lookup"><span data-stu-id="bb76d-105">To generate either C# or Visual Basic class files that conform to a specific XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="bb76d-106">Das Tool übernimmt ein XML-Schema als Argument und gibt eine Datei mit einer Gruppe von Klassen aus, die dem Schema entsprechen, wenn sie mit <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="bb76d-106">The tool takes an XML Schema as an argument and outputs a file that contains a number of classes that, when serialized with the <xref:System.Xml.Serialization.XmlSerializer>, conform to the schema.</span></span> <span data-ttu-id="bb76d-107">Weitere Informationen dazu, wie mit diesem Tool Klassen erstellt werden, die einem bestimmten Schema entsprechen, finden Sie unter [Vorgehensweise: Mit dem XML Schema Definition-Tool Klassen und XML-Schemadokumente generieren](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).</span><span class="sxs-lookup"><span data-stu-id="bb76d-107">For information about how to use the tool to generate classes that conform to a specific schema, see [How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).</span></span>  
  
-   <span data-ttu-id="bb76d-108">So generieren Sie ein XML-Schemadokument aus einer DLL-Datei oder EXE-Datei</span><span class="sxs-lookup"><span data-stu-id="bb76d-108">To generate an XML Schema document from a .dll file or .exe file.</span></span> <span data-ttu-id="bb76d-109">Um das Schema einer Gruppe von Dateien darzustellen, die Sie erstellt haben oder die mit Attributen verändert wurde, übergeben Sie dem Tool die DLL- oder EXE-Datei als Argument, um das XML-Schema zu generieren.</span><span class="sxs-lookup"><span data-stu-id="bb76d-109">To see the schema of a set of files that you have either created or one that has been modified with attributes, pass the DLL or EXE as an argument to the tool to generate the XML schema.</span></span> <span data-ttu-id="bb76d-110">Weitere Informationen dazu, wie mit diesem Tool ein XML-Schemadokument aus einer Gruppe von Klassen erzeugt wird, finden Sie unter [Vorgehensweise: Mit dem XML Schema Definition-Tool Klassen und XML-Schemadokumente generieren](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).</span><span class="sxs-lookup"><span data-stu-id="bb76d-110">For information about how to use the tool to generate an XML Schema Document from a set of classes, see [How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).</span></span>  
  
 <span data-ttu-id="bb76d-111">Weitere Informationen zu diesem und anderen Tools finden Sie unter [Tools](../../../docs/framework/tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="bb76d-111">For more information about this tool and others, see [Tools](../../../docs/framework/tools/index.md).</span></span> <span data-ttu-id="bb76d-112">Informationen zu den Optionen in diesem Tool finden Sie unter [XML Schema Definition-Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).</span><span class="sxs-lookup"><span data-stu-id="bb76d-112">For information about the tool's options, see [XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb76d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb76d-113">See Also</span></span>  
 <xref:System.Data.DataSet>  
 [<span data-ttu-id="bb76d-114">Einführung in die XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="bb76d-114">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [<span data-ttu-id="bb76d-115">XML Schema Definition-Tool (Xsd.exe)</span><span class="sxs-lookup"><span data-stu-id="bb76d-115">XML Schema Definition Tool (Xsd.exe)</span></span>](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)  
 <xref:System.Xml.Serialization.XmlSerializer>  
 [<span data-ttu-id="bb76d-116">Vorgehensweise: Serialisieren eines Objekts</span><span class="sxs-lookup"><span data-stu-id="bb76d-116">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)  
 [<span data-ttu-id="bb76d-117">Vorgehensweise: Deserialisieren eines Objekts</span><span class="sxs-lookup"><span data-stu-id="bb76d-117">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)  
 [<span data-ttu-id="bb76d-118">Vorgehensweise: Mit dem XML Schema Definition-Tool Klassen und XML-Schemadokumente generieren</span><span class="sxs-lookup"><span data-stu-id="bb76d-118">How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents</span></span>](../../../docs/standard/serialization/xml-schema-def-tool-gen.md)  
 [<span data-ttu-id="bb76d-119">Bindungsunterstützung für XML-Schema in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bb76d-119">XML Schema Binding Support in the .NET Framework</span></span>](http://msdn.microsoft.com/en-us/8f0619dd-f1fc-4895-ae21-6d45d0382cc1)
