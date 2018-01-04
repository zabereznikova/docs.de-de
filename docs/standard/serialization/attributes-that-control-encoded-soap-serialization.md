---
title: Attribute zur Steuerung der Serialisierung von codiertem SOAP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- XML serialization, attributes
- attributes [.NET Framework], XML serialization
- serialization, attributes
ms.assetid: 93ee258c-9c0f-4a08-897c-c10db7a00f91
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ae3193a2f9ef01f8e7f71235f15ed070e84ec11c
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="attributes-that-control-encoded-soap-serialization"></a><span data-ttu-id="08ea0-102">Attribute zur Steuerung der Serialisierung von codiertem SOAP</span><span class="sxs-lookup"><span data-stu-id="08ea0-102">Attributes That Control Encoded SOAP Serialization</span></span> 
<span data-ttu-id="08ea0-103">Das vom World Wide Web Consortium (www.w3.org) herausgegebene Dokument mit dem Titel „Simple Object Access Protocol (SOAP) 1.1“ enthält einen optionalen Abschnitt (Abschnitt 5), in dem die Codierung von SOAP-Parametern beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="08ea0-103">The World Wide Web Consortium (www.w3.org) document named "Simple Object Access Protocol (SOAP) 1.1" contains an optional section (section 5) that describes how SOAP parameters can be encoded.</span></span> <span data-ttu-id="08ea0-104">Um dem Abschnitt 5 dieser Spezifikation zu entsprechen, müssen Sie spezielle Attribute verwenden, die im <xref:System.Xml.Serialization>-Namespace enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="08ea0-104">To conform to section 5 of the specification, you must use a special set of attributes found in the <xref:System.Xml.Serialization> namespace.</span></span> <span data-ttu-id="08ea0-105">Wenden Sie diese Attribute auf die entsprechenden Klassen und Member der Klassen an, und verwenden Sie dann <xref:System.Xml.Serialization.XmlSerializer>, um Instanzen dieser Klasse oder Klassen zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="08ea0-105">Apply those attributes as appropriate to classes and members of classes, and then use the <xref:System.Xml.Serialization.XmlSerializer> to serialize instances of the class or classes.</span></span>  
  
 <span data-ttu-id="08ea0-106">In der folgenden Tabelle sind die Attribute, ihr Anwendungsbereich und ihre Funktion aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="08ea0-106">The following table shows the attributes, where they can be applied, and what they do.</span></span> <span data-ttu-id="08ea0-107">Weitere Informationen zum Einsatz dieser Attribute zur Steuerung der XML-Serialisierung finden Sie unter [Vorgehensweise: Serialisieren eines Objekts als SOAP-codierter XML-Stream](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) und [Vorgehensweise: Überschreiben von codierter SOAP-XML-Serialisierung](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="08ea0-107">For more information about using these attributes to control XML serialization, see [How to: Serialize an Object as a SOAP-Encoded XML Stream](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) and [How to: Override Encoded SOAP XML Serialization](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md).</span></span>  
  
 <span data-ttu-id="08ea0-108">Weitere Informationen zu Attributen finden Sie unter [Attribute](../../../docs/standard/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="08ea0-108">For more information about attributes, see [Attributes](../../../docs/standard/attributes/index.md).</span></span>  
  
|<span data-ttu-id="08ea0-109">Attribut</span><span class="sxs-lookup"><span data-stu-id="08ea0-109">Attribute</span></span>|<span data-ttu-id="08ea0-110">Betrifft</span><span class="sxs-lookup"><span data-stu-id="08ea0-110">Applies to</span></span>|<span data-ttu-id="08ea0-111">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="08ea0-111">Specifies</span></span>|  
|---------------|----------------|---------------|  
|<xref:System.Xml.Serialization.SoapAttributeAttribute>|<span data-ttu-id="08ea0-112">Öffentliches Feld, Eigenschaft, Parameter oder Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="08ea0-112">Public field, property, parameter, or return value.</span></span>|<span data-ttu-id="08ea0-113">Der Klassenmember wird als XML-Attribut serialisiert.</span><span class="sxs-lookup"><span data-stu-id="08ea0-113">The class member will be serialized as an XML attribute.</span></span>|  
|<xref:System.Xml.Serialization.SoapElementAttribute>|<span data-ttu-id="08ea0-114">Öffentliches Feld, Eigenschaft, Parameter oder Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="08ea0-114">Public field, property, parameter, or return value.</span></span>|<span data-ttu-id="08ea0-115">Die Klasse wird als XML-Element serialisiert.</span><span class="sxs-lookup"><span data-stu-id="08ea0-115">The class will be serialized as an XML element.</span></span>|  
|<xref:System.Xml.Serialization.SoapEnumAttribute>|<span data-ttu-id="08ea0-116">Öffentliches Feld, das ein Enumerationsbezeichner ist.</span><span class="sxs-lookup"><span data-stu-id="08ea0-116">Public field that is an enumeration identifier.</span></span>|<span data-ttu-id="08ea0-117">Der Elementname eines Enumerationsmembers.</span><span class="sxs-lookup"><span data-stu-id="08ea0-117">The element name of an enumeration member.</span></span>|  
|<xref:System.Xml.Serialization.SoapIgnoreAttribute>|<span data-ttu-id="08ea0-118">Öffentliche Eigenschaften und Felder.</span><span class="sxs-lookup"><span data-stu-id="08ea0-118">Public properties and fields.</span></span>|<span data-ttu-id="08ea0-119">Die Eigenschaft oder das Feld wird beim Serialisieren der Klasse, in dem sie bzw. es enthalten ist, ignoriert.</span><span class="sxs-lookup"><span data-stu-id="08ea0-119">The property or field should be ignored when the containing class is serialized.</span></span>|  
|<xref:System.Xml.Serialization.SoapIncludeAttribute>|<span data-ttu-id="08ea0-120">Öffentliche abgeleitete Klassendeklarationen und öffentliche Methoden für WSDL-Dokumente (Web Services Description Language).</span><span class="sxs-lookup"><span data-stu-id="08ea0-120">Public-derived class declarations and public methods for Web Services Description Language (WSDL) documents.</span></span>|<span data-ttu-id="08ea0-121">Der Typ wird beim Generieren von Schemas eingeschlossen (und daher bei der Serialisierung erkannt).</span><span class="sxs-lookup"><span data-stu-id="08ea0-121">The type should be included when generating schemas (to be recognized when serialized).</span></span>|  
|<xref:System.Xml.Serialization.SoapTypeAttribute>|<span data-ttu-id="08ea0-122">Deklarationen öffentlicher Klassen.</span><span class="sxs-lookup"><span data-stu-id="08ea0-122">Public class declarations.</span></span>|<span data-ttu-id="08ea0-123">Die Klasse wird als XML-Typ serialisiert.</span><span class="sxs-lookup"><span data-stu-id="08ea0-123">The class should be serialized as an XML type.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08ea0-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08ea0-124">See Also</span></span>  
 [<span data-ttu-id="08ea0-125">XML- und SOAP-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="08ea0-125">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
 [<span data-ttu-id="08ea0-126">Vorgehensweise: Serialisieren eines Objekts als SOAP-codierter XML-Stream</span><span class="sxs-lookup"><span data-stu-id="08ea0-126">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)  
 [<span data-ttu-id="08ea0-127">Gewusst wie: Überschreiben von codierter SOAP-XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="08ea0-127">How to: Override Encoded SOAP XML Serialization</span></span>](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md)  
 [<span data-ttu-id="08ea0-128">Attribute</span><span class="sxs-lookup"><span data-stu-id="08ea0-128">Attributes</span></span>](../../../docs/standard/attributes/index.md)  
 <xref:System.Xml.Serialization.XmlSerializer>  
 [<span data-ttu-id="08ea0-129">Vorgehensweise: Serialisieren eines Objekts</span><span class="sxs-lookup"><span data-stu-id="08ea0-129">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)  
 [<span data-ttu-id="08ea0-130">Vorgehensweise: Deserialisieren eines Objekts</span><span class="sxs-lookup"><span data-stu-id="08ea0-130">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
