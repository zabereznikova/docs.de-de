---
title: 'Gewusst wie: Mit dem XML Schema Definition-Tool Klassen und XML-Schemadokumente generieren'
ms.date: 03/30/2017
helpviewer_keywords:
- generating XML classes using XML Schema Definition tool
- generating XML Schema Document using XML Schema Definition tool
- XML Schema Definition tool, using to generate classes that conform to specific schema
- XML Schema Definition tool, using to generate XML Schema Document
ms.assetid: 51f0edc3-993d-4051-b7f2-77753694d3d1
ms.openlocfilehash: 9b2cd67a1c4f30e6fe246124be5b8f7081c539a6
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71392865"
---
# <a name="how-to-use-the-xml-schema-definition-tool-to-generate-classes-and-xml-schema-documents"></a><span data-ttu-id="512f7-102">Gewusst wie: Mit dem XML Schema Definition-Tool Klassen und XML-Schemadokumente generieren</span><span class="sxs-lookup"><span data-stu-id="512f7-102">How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents</span></span>
<span data-ttu-id="512f7-103">Mit dem XML-Schema Definition-Tool (Xsd.exe) können Sie ein XML-Schema generieren, das eine Klasse beschreibt, oder die Klasse generieren, die durch ein XML-Schema definiert wird.</span><span class="sxs-lookup"><span data-stu-id="512f7-103">The XML Schema Definition tool (Xsd.exe) allows you to generate an XML schema that describes a class or to generate the class defined by an XML schema.</span></span> <span data-ttu-id="512f7-104">Die folgenden Verfahren zeigen, wie diese Vorgänge ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="512f7-104">The following procedures show how to perform these operations.</span></span>  
  
### <a name="to-generate-classes-that-conform-to-a-specific-schema"></a><span data-ttu-id="512f7-105">So generieren Sie Klassen, die einem bestimmten Schema entsprechen</span><span class="sxs-lookup"><span data-stu-id="512f7-105">To generate classes that conform to a specific schema</span></span>  
  
1. <span data-ttu-id="512f7-106">Öffnen Sie eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="512f7-106">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="512f7-107">Übergeben Sie dem XML Schema Definition-Tool das XML-Schema als Argument. Dieses Tool erzeugt eine Gruppe von Klassen, die dem XML-Schema genau entsprechen, zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="512f7-107">Pass the XML Schema as an argument to the XML Schema Definition tool, which creates a set of classes that are precisely matched to the XML Schema, for example:</span></span>  
  
    ```console  
    xsd mySchema.xsd  
    ```  
  
     <span data-ttu-id="512f7-108">Das Tool kann nur Schemas verarbeiten, die auf die World Wide Web Consortium-XML-Spezifikation vom 16. März 2001 verweisen.</span><span class="sxs-lookup"><span data-stu-id="512f7-108">The tool can only process schemas that reference the World Wide Web Consortium XML specification of March 16, 2001.</span></span> <span data-ttu-id="512f7-109">Anders ausgedrückt: der XML-Schema Namespace muss wie im folgenden Beispiel "http://www.w3.org/2001/XMLSchema" lauten.</span><span class="sxs-lookup"><span data-stu-id="512f7-109">In other words, the XML Schema namespace must be "http://www.w3.org/2001/XMLSchema" as shown in the following example.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <xs:schema attributeFormDefault="qualified" elementFormDefault="qualified" targetNamespace="" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    ```  
  
3. <span data-ttu-id="512f7-110">Ändern Sie die Klassen bei Bedarf mit Methoden, Eigenschaften oder Feldern.</span><span class="sxs-lookup"><span data-stu-id="512f7-110">Modify the classes with methods, properties, or fields, as necessary.</span></span> <span data-ttu-id="512f7-111">Weitere Informationen zum Ändern einer Klasse mithilfe von Attributen finden Sie unter [Steuern der XML-Serialisierung mit Attributen](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md) und [Attribute zur Steuerung der Serialisierung von codiertem SOAP](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="512f7-111">For more information about modifying a class with attributes, see [Controlling XML Serialization Using Attributes](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md) and [Attributes That Control Encoded SOAP Serialization](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span></span>  
  
 <span data-ttu-id="512f7-112">Es ist oft sinnvoll, das Schema des XML-Streams zu überprüfen, der bei der Serialisierung von Instanzen der Klasse (oder Klassen) generiert wird.</span><span class="sxs-lookup"><span data-stu-id="512f7-112">It is often useful to examine the schema of the XML stream that is generated when instances of a class (or classes) are serialized.</span></span> <span data-ttu-id="512f7-113">Sie veröffentlichen möglicherweise ein Schema, damit es andere Benutzer verwenden können, oder Sie vergleichen es mit einem Schema, mit dem Sie Konformität zu erreichen versuchen.</span><span class="sxs-lookup"><span data-stu-id="512f7-113">For example, you might publish your schema for others to use, or you might compare it to a schema with which you are trying to achieve conformity.</span></span>  
  
#### <a name="to-generate-an-xml-schema-document-from-a-set-of-classes"></a><span data-ttu-id="512f7-114">So generieren Sie ein XML-Schemadokument aus einer Gruppe von Klassen</span><span class="sxs-lookup"><span data-stu-id="512f7-114">To generate an XML Schema document from a set of classes</span></span>  
  
1. <span data-ttu-id="512f7-115">Kompilieren Sie die Klasse oder die Klassen in eine DLL.</span><span class="sxs-lookup"><span data-stu-id="512f7-115">Compile the class or classes into a DLL.</span></span>  
  
2. <span data-ttu-id="512f7-116">Öffnen Sie eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="512f7-116">Open a command prompt.</span></span>  
  
3. <span data-ttu-id="512f7-117">Übergeben Sie die DLL als Argument an Xsd.exe. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="512f7-117">Pass the DLL as an argument to Xsd.exe, for example:</span></span>  
  
    ```console  
    xsd MyFile.dll  
    ```  
  
     <span data-ttu-id="512f7-118">Das Schema (oder die Schemas) wird/werden ausgegeben und mit Namen im Format "schema0.xsd" fortlaufend benannt.</span><span class="sxs-lookup"><span data-stu-id="512f7-118">The schema (or schemas) will be written, beginning with the name "schema0.xsd".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="512f7-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="512f7-119">See also</span></span>

- <xref:System.Data.DataSet>
- [<span data-ttu-id="512f7-120">Das XML Schema Definition-Tool und die XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="512f7-120">The XML Schema Definition Tool and XML Serialization</span></span>](../../../docs/standard/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)
- [<span data-ttu-id="512f7-121">Einführung in die XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="512f7-121">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="512f7-122">XML Schema Definition-Tool (Xsd.exe)</span><span class="sxs-lookup"><span data-stu-id="512f7-122">XML Schema Definition Tool (Xsd.exe)</span></span>](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="512f7-123">Vorgehensweise: Serialisieren eines Objekts</span><span class="sxs-lookup"><span data-stu-id="512f7-123">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [<span data-ttu-id="512f7-124">Vorgehensweise: Deserialisieren eines Objekts</span><span class="sxs-lookup"><span data-stu-id="512f7-124">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
