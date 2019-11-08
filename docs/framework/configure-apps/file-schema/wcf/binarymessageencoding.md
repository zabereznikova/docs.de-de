---
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: afe0479d9cbf6d754b309c18e23d3a479870177c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739070"
---
# <a name="binarymessageencoding"></a><span data-ttu-id="e0141-101">\<binaryMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="e0141-101">\<binaryMessageEncoding></span></span>
<span data-ttu-id="e0141-102">Definiert einen Binärnachrichtenencoder, der die Windows Communication Foundation (WCF)-Nachrichten bei der Übertragung im Binärformat verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="e0141-102">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
<span data-ttu-id="e0141-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e0141-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e0141-104">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="e0141-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e0141-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="e0141-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="e0141-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="e0141-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="e0141-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="e0141-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="e0141-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<binaryMessageEncoding >**</span><span class="sxs-lookup"><span data-stu-id="e0141-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binaryMessageEncoding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0141-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0141-109">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0141-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e0141-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e0141-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e0141-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0141-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="e0141-112">Attributes</span></span>  
  
|<span data-ttu-id="e0141-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="e0141-113">Attribute</span></span>|<span data-ttu-id="e0141-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0141-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e0141-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="e0141-115">maxReadPoolSize</span></span>|<span data-ttu-id="e0141-116">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="e0141-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="e0141-117">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="e0141-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="e0141-118">Der Standard ist 64.</span><span class="sxs-lookup"><span data-stu-id="e0141-118">The default is 64.</span></span>|  
|<span data-ttu-id="e0141-119">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="e0141-119">maxSessionSize</span></span>|<span data-ttu-id="e0141-120">Eine positive ganze Zahl, die die Größe des Puffers in Bytes festlegt, der zum Verschlüsseln von Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e0141-120">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="e0141-121">Eine größerer Puffer erhöht die Codierungsgeschwindigkeit auf Kosten der Größe des Workingsets.</span><span class="sxs-lookup"><span data-stu-id="e0141-121">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="e0141-122">Der Standard ist 2048.</span><span class="sxs-lookup"><span data-stu-id="e0141-122">The default is 2048.</span></span>|  
|<span data-ttu-id="e0141-123">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="e0141-123">maxWritePoolSize</span></span>|<span data-ttu-id="e0141-124">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="e0141-124">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="e0141-125">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="e0141-125">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="e0141-126">Der Standard ist 16.</span><span class="sxs-lookup"><span data-stu-id="e0141-126">The default is 16.</span></span>|  
|<span data-ttu-id="e0141-127">messageVersion</span><span class="sxs-lookup"><span data-stu-id="e0141-127">messageVersion</span></span>|<span data-ttu-id="e0141-128">Gibt die Versionen der SOAP-Nachricht und WS-Adressierung an, die verwendet oder erwartet werden.</span><span class="sxs-lookup"><span data-stu-id="e0141-128">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e0141-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e0141-129">Child Elements</span></span>  
  
|<span data-ttu-id="e0141-130">Element</span><span class="sxs-lookup"><span data-stu-id="e0141-130">Element</span></span>|<span data-ttu-id="e0141-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0141-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e0141-132">[\<von Readerkontingenten >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e0141-132">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="e0141-133">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="e0141-133">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="e0141-134">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="e0141-134">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e0141-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e0141-135">Parent Elements</span></span>  
  
|<span data-ttu-id="e0141-136">Element</span><span class="sxs-lookup"><span data-stu-id="e0141-136">Element</span></span>|<span data-ttu-id="e0141-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0141-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e0141-138">\<binding ></span><span class="sxs-lookup"><span data-stu-id="e0141-138">\<binding></span></span>](bindings.md)|<span data-ttu-id="e0141-139">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="e0141-139">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0141-140">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e0141-140">Remarks</span></span>  
 <span data-ttu-id="e0141-141">Beim Codieren wird eine Nachricht in eine Bytefolge transformiert.</span><span class="sxs-lookup"><span data-stu-id="e0141-141">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="e0141-142">Beim Decodieren wird dieser Prozess umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="e0141-142">Decoding is the reverse process.</span></span> <span data-ttu-id="e0141-143">Windows Communication Foundation (WCF) enthält drei Typen für die Codierung von SOAP-Nachrichten: Text, binär und Message Transmission Optimization Mechanism (MTOM).</span><span class="sxs-lookup"><span data-stu-id="e0141-143">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="e0141-144">Das `binaryMessageEncoding`-Element gibt das .NET Binary-Format für XML an und bietet Optionen zum Festlegen der Zeichencodierung und der zu verwendenden SOAP- und WS-Adressierungsversion.</span><span class="sxs-lookup"><span data-stu-id="e0141-144">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="e0141-145">Der Binärnachrichtenencoder verschlüsselt die Windows Communication Foundation (WCF)-Nachrichten bei der Übertragung im Binärformat.</span><span class="sxs-lookup"><span data-stu-id="e0141-145">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="e0141-146">Diese Verschlüsselung resultiert zwar in einer schnellen Nachrichtenübertragung, die auf den WS-\*-Standards basierende Interoperabilität geht aber verloren.</span><span class="sxs-lookup"><span data-stu-id="e0141-146">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0141-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e0141-147">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="e0141-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0141-148">See also</span></span>

- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [<span data-ttu-id="e0141-149">Nachrichtencodierung</span><span class="sxs-lookup"><span data-stu-id="e0141-149">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="e0141-150">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="e0141-150">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="e0141-151">Bindungen</span><span class="sxs-lookup"><span data-stu-id="e0141-151">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e0141-152">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="e0141-152">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e0141-153">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="e0141-153">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="e0141-154">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="e0141-154">\<customBinding></span></span>](custombinding.md)
