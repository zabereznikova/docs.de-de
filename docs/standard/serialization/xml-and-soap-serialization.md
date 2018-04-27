---
title: XML- und SOAP-Serialisierung
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
- serialization, about serialization
- XML serialization
- serialization
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8895a3ca460034cd963bc43e1f27535a51cf9356
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="xml-and-soap-serialization"></a><span data-ttu-id="d6c2c-102">XML- und SOAP-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="d6c2c-102">XML and SOAP Serialization</span></span>
<span data-ttu-id="d6c2c-103">Bei der XML-Serialisierung werden die öffentlichen Felder und Eigenschaften eines Objekts bzw. die Parameter und Rückgabewerte von Methoden in einen XML-Stream konvertiert (serialisiert), der einem bestimmtem XSD (XML Schema Definition)-Dokument entspricht.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-103">XML serialization converts (serializes) the public fields and properties of an object, or the parameters and return values of methods, into an XML stream that conforms to a specific XML Schema definition language (XSD) document.</span></span> <span data-ttu-id="d6c2c-104">Die XML-Serialisierung führt zu stark typisierten Klassen mit öffentlichen Eigenschaften und Feldern, die in ein serielles Format (hier XML) konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-104">XML serialization results in strongly typed classes with public properties and fields that are converted to a serial format (in this case, XML) for storage or transport.</span></span>  
  
 <span data-ttu-id="d6c2c-105">Weil XML ein offener Standard ist, kann der XML-Stream plattformunabhängig bei Bedarf von jeder Anwendung verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-105">Because XML is an open standard, the XML stream can be processed by any application, as needed, regardless of platform.</span></span> <span data-ttu-id="d6c2c-106">Beispielsweise verwenden mit ASP.NET erstellte Webdienste die <xref:System.Xml.Serialization.XmlSerializer>-Klasse zum Erstellen von XML-Sstreams, die zur Übermittlung von Daten zwischen XML-Webdienstanwendungen über das Internet oder ein Intranet dienen.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-106">For example, XML Web services created using ASP.NET use the <xref:System.Xml.Serialization.XmlSerializer> class to create XML streams that pass data between XML Web service applications throughout the Internet or on intranets.</span></span> <span data-ttu-id="d6c2c-107">Umgekehrt wird bei der Deserialisierung das Objekt aus einem XML-Stream rekonstruiert.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-107">Conversely, deserialization takes such an XML stream and reconstructs the object.</span></span>  
  
 <span data-ttu-id="d6c2c-108">Durch die XML-Serialisierung können auch Objekte in XML-Streams serialisiert werden, die der SOAP-Spezifikation entsprechen.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-108">XML serialization can also be used to serialize objects into XML streams that conform to the SOAP specification.</span></span> <span data-ttu-id="d6c2c-109">SOAP ist ein auf XML basierendes Protokoll, das speziell für die Weitergabe von Prozeduraufrufen unter Verwendung von XML entwickelt wurde.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-109">SOAP is a protocol based on XML, designed specifically to transport procedure calls using XML.</span></span>  
  
 <span data-ttu-id="d6c2c-110">Sie können mithilfe der <xref:System.Xml.Serialization.XmlSerializer>-Klasse Objekte serialisieren und deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-110">To serialize or deserialize objects, use the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span> <span data-ttu-id="d6c2c-111">Verwenden Sie das XML Schema Definition-Tool, um die zu serialisierenden Klassen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-111">To create the classes to be serialized, use the XML Schema Definition tool.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d6c2c-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d6c2c-112">In This Section</span></span>  
 [<span data-ttu-id="d6c2c-113">Einführung in die XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="d6c2c-113">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 <span data-ttu-id="d6c2c-114">Enthält eine allgemeine Definition der Serialisierung, insbesondere der XML-Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-114">Provides a general definition of serialization, particularly XML serialization.</span></span>  
  
 [<span data-ttu-id="d6c2c-115">Vorgehensweise: Serialisieren eines Objekts</span><span class="sxs-lookup"><span data-stu-id="d6c2c-115">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)  
 <span data-ttu-id="d6c2c-116">Stellt schrittweise Anweisungen zum Serialisieren eines Objekts bereit.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-116">Provides step-by-step instructions for serializing an object.</span></span>  
  
 [<span data-ttu-id="d6c2c-117">Vorgehensweise: Deserialisieren eines Objekts</span><span class="sxs-lookup"><span data-stu-id="d6c2c-117">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)  
 <span data-ttu-id="d6c2c-118">Stellt schrittweise Anweisungen zum Deserialisieren eines Objekts bereit.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-118">Provides step-by-step instructions for deserializing an object.</span></span>  
  
 [<span data-ttu-id="d6c2c-119">Beispiele für die XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="d6c2c-119">Examples of XML Serialization</span></span>](../../../docs/standard/serialization/examples-of-xml-serialization.md)  
 <span data-ttu-id="d6c2c-120">Enthält Beispiele, in denen die Grundlagen der XML-Serialisierung veranschaulicht werden.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-120">Provides examples that demonstrate the basics of XML serialization.</span></span>  
  
 [<span data-ttu-id="d6c2c-121">Das XML Schema Definition-Tool und die XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="d6c2c-121">The XML Schema Definition Tool and XML Serialization</span></span>](../../../docs/standard/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)  
 <span data-ttu-id="d6c2c-122">Beschreibt die Verwendung des XML-Schema Definition-Tools (Xsd.exe) zum Erstellen von Klassen, die einem bestimmten XSD-Schema (XML Schema Definition Language) angehören, oder zum Generieren eines XML-Schemas aus einer DLL-Datei.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-122">Describes how to use the XML Schema Definition tool to create classes that adhere to a particular XML Schema definition language (XSD) schema, or to generate an XML Schema from a .dll file.</span></span>  
  
 [<span data-ttu-id="d6c2c-123">Steuern der XML-Serialisierung mit Attributen</span><span class="sxs-lookup"><span data-stu-id="d6c2c-123">Controlling XML Serialization Using Attributes</span></span>](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)  
 <span data-ttu-id="d6c2c-124">Beschreibt, wie die Serialisierung durch die Verwendung von Attributen gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-124">Describes how to control serialization by using attributes.</span></span>  
  
 [<span data-ttu-id="d6c2c-125">Attribute zur Steuerung der XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="d6c2c-125">Attributes That Control XML Serialization</span></span>](../../../docs/standard/serialization/attributes-that-control-xml-serialization.md)  
 <span data-ttu-id="d6c2c-126">Listet die zur Steuerung der XML-Serialisierung verwendeten Attribute auf.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-126">Lists the attributes that are used to control XML serialization.</span></span>  
  
 [<span data-ttu-id="d6c2c-127">Vorgehensweise: Angeben eines alternativen Elementnamens für einen XML-Stream</span><span class="sxs-lookup"><span data-stu-id="d6c2c-127">How to: Specify an Alternate Element Name for an XML Stream</span></span>](../../../docs/standard/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)  
 <span data-ttu-id="d6c2c-128">Veranschaulicht anhand eines komplexen Szenarios die Generierung mehrerer XML-Streams durch außer Kraft setzen der Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-128">Presents an advanced scenario showing how to generate multiple XML streams by overriding the serialization.</span></span>  
  
 [<span data-ttu-id="d6c2c-129">Vorgehensweise: Steuern der Serialisierung abgeleiteter Klassen</span><span class="sxs-lookup"><span data-stu-id="d6c2c-129">How to: Control Serialization of Derived Classes</span></span>](../../../docs/standard/serialization/how-to-control-serialization-of-derived-classes.md)  
 <span data-ttu-id="d6c2c-130">Zeigt anhand eines Beispiels, wie sich die Serialisierung abgeleiteter Klassen steuern läst.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-130">Provides an example of how to control the serialization of derived classes.</span></span>  
  
 [<span data-ttu-id="d6c2c-131">Vorgehensweise: Qualifizieren von XML-Element- und XML-Attributnamen</span><span class="sxs-lookup"><span data-stu-id="d6c2c-131">How to: Qualify XML Element and XML Attribute Names</span></span>](../../../docs/standard/serialization/how-to-qualify-xml-element-and-xml-attribute-names.md)  
 <span data-ttu-id="d6c2c-132">Beschreibt, wie definiert und gesteuert werden kann, wie XML-Namespaces im XML-Stream verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-132">Describes how to define and control the way in which XML namespaces are used in the XML stream.</span></span>  
  
 [<span data-ttu-id="d6c2c-133">XML-Serialisierung mit XML-Webdiensten</span><span class="sxs-lookup"><span data-stu-id="d6c2c-133">XML Serialization with XML Web Services</span></span>](../../../docs/standard/serialization/xml-serialization-with-xml-web-services.md)  
 <span data-ttu-id="d6c2c-134">Erläutert die Verwendung der XML-Serialisierung in XML-Webdiensten.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-134">Explains how XML serialization is used in XML Web services.</span></span>  
  
 [<span data-ttu-id="d6c2c-135">Vorgehensweise: Serialisieren eines Objekts als SOAP-codierter XML-Stream</span><span class="sxs-lookup"><span data-stu-id="d6c2c-135">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)  
 <span data-ttu-id="d6c2c-136">Beschreibt die Verwendung der <xref:System.Xml.Serialization.XmlSerializer> -Klasse zur Erstellung der XML-Streams von codiertem SOAP, die Abschnitt 5 des vom World Wide Web Consortium (www.w3.org) herausgegebenen Dokuments mit dem Titel "Simple Object Access Protocol (SOAP) 1.1" entsprechen.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-136">Describes how to use the <xref:System.Xml.Serialization.XmlSerializer> class to create encoded SOAP XML streams that conform to section 5 of the World Wide Web Consortium (www.w3.org) document titled "Simple Object Access Protocol (SOAP) 1.1."</span></span>  
  
 [<span data-ttu-id="d6c2c-137">Gewusst wie: Überschreiben von codierter SOAP-XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="d6c2c-137">How to: Override Encoded SOAP XML Serialization</span></span>](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md)  
 <span data-ttu-id="d6c2c-138">Beschreibt, wie die XML-Serialisierung von Objekten als SOAP-Nachrichten außer Kraft gesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-138">Describes the process for overriding XML serialization of objects as SOAP messages.</span></span>  
  
 [<span data-ttu-id="d6c2c-139">Attribute zur Steuerung der Serialisierung von codiertem SOAP</span><span class="sxs-lookup"><span data-stu-id="d6c2c-139">Attributes That Control Encoded SOAP Serialization</span></span>](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)  
 <span data-ttu-id="d6c2c-140">Listet die Attribute auf, die zur Steuerung der Serialisierung von codiertem SOAP verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-140">Lists the attributes that are used to control SOAP-encoded serialization.</span></span>  
  
 [<span data-ttu-id="d6c2c-141">\<system.xml.serialization>-Element</span><span class="sxs-lookup"><span data-stu-id="d6c2c-141">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)  
 <span data-ttu-id="d6c2c-142">Das Konfigurationselement der obersten Ebene zur Steuerung der XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="d6c2c-142">The top-level configuration element for controlling XML serialization.</span></span>  
  
 [<span data-ttu-id="d6c2c-143">\<dateTimeSerialization>-Element</span><span class="sxs-lookup"><span data-stu-id="d6c2c-143">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)  
 <span data-ttu-id="d6c2c-144">Steuert den Serialisierungsmodus von <xref:System.DateTime>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-144">Controls the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 [<span data-ttu-id="d6c2c-145">\<schemaImporterExtensions>-Element</span><span class="sxs-lookup"><span data-stu-id="d6c2c-145">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)  
 <span data-ttu-id="d6c2c-146">Enthält Typen, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-146">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> class.</span></span>  
  
 [<span data-ttu-id="d6c2c-147">\<add>-Element für \<xmlSchemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="d6c2c-147">\<add> Element for \<xmlSchemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md)  
 <span data-ttu-id="d6c2c-148">Fügt Typen hinzu, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-148">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d6c2c-149">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="d6c2c-149">Related Sections</span></span>  
 [<span data-ttu-id="d6c2c-150">Advanced Development Technologies (Erweiterte Entwicklungstechnologien)</span><span class="sxs-lookup"><span data-stu-id="d6c2c-150">Advanced Development Technologies</span></span>](https://msdn.microsoft.com/library/c4a7e341-f0c6-4df4-a74f-223387ac6e4e)  
 <span data-ttu-id="d6c2c-151">Enthält Links zu weiteren Informationen über anspruchsvolle Aufgaben und Verfahren für die Entwicklung in .NET&#160;Framework.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-151">Provides links to more information on sophisticated development tasks and techniques in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="d6c2c-152">Mit ASP.NET- und XML-Webdienstclients erstellte XML-Webdienste</span><span class="sxs-lookup"><span data-stu-id="d6c2c-152">XML Web Services Created Using ASP.NET and XML Web Service Clients</span></span>](https://msdn.microsoft.com/library/1e64af78-d705-4384-b08d-591a45f4379c)  
 <span data-ttu-id="d6c2c-153">Stellt Themen bereit, in denen beschrieben und erklärt wird, wie XML-Webdienste mit ASP.NET programmiert werden.</span><span class="sxs-lookup"><span data-stu-id="d6c2c-153">Provides topics that describe and explain how to program XML Web services using ASP.NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6c2c-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6c2c-154">See Also</span></span>  
 [<span data-ttu-id="d6c2c-155">Binäre Serialisierung</span><span class="sxs-lookup"><span data-stu-id="d6c2c-155">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)
