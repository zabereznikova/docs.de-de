---
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: 9b6b74200c807e6523ed3f7250945040bd12658d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919792"
---
# <a name="binarymessageencoding"></a><span data-ttu-id="c6f27-101">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="c6f27-101">\<binaryMessageEncoding></span></span>
<span data-ttu-id="c6f27-102">Definiert einen Binärnachrichtenencoder, der die Windows Communication Foundation (WCF)-Nachrichten bei der Übertragung im Binärformat verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="c6f27-102">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
 <span data-ttu-id="c6f27-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c6f27-103">\<system.serviceModel></span></span>  
<span data-ttu-id="c6f27-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="c6f27-104">\<bindings></span></span>  
<span data-ttu-id="c6f27-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c6f27-105">\<customBinding></span></span>  
<span data-ttu-id="c6f27-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="c6f27-106">\<binding></span></span>  
<span data-ttu-id="c6f27-107">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="c6f27-107">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6f27-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6f27-108">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6f27-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c6f27-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c6f27-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c6f27-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6f27-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="c6f27-111">Attributes</span></span>  
  
|<span data-ttu-id="c6f27-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="c6f27-112">Attribute</span></span>|<span data-ttu-id="c6f27-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c6f27-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c6f27-114">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="c6f27-114">maxReadPoolSize</span></span>|<span data-ttu-id="c6f27-115">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="c6f27-115">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="c6f27-116">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="c6f27-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="c6f27-117">Der Standard ist 64.</span><span class="sxs-lookup"><span data-stu-id="c6f27-117">The default is 64.</span></span>|  
|<span data-ttu-id="c6f27-118">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="c6f27-118">maxSessionSize</span></span>|<span data-ttu-id="c6f27-119">Eine positive ganze Zahl, die die Größe des Puffers in Bytes festlegt, der zum Verschlüsseln von Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c6f27-119">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="c6f27-120">Eine größerer Puffer erhöht die Codierungsgeschwindigkeit auf Kosten der Größe des Workingsets.</span><span class="sxs-lookup"><span data-stu-id="c6f27-120">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="c6f27-121">Der Standard ist 2048.</span><span class="sxs-lookup"><span data-stu-id="c6f27-121">The default is 2048.</span></span>|  
|<span data-ttu-id="c6f27-122">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="c6f27-122">maxWritePoolSize</span></span>|<span data-ttu-id="c6f27-123">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="c6f27-123">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="c6f27-124">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="c6f27-124">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="c6f27-125">Der Standardwert ist 16.</span><span class="sxs-lookup"><span data-stu-id="c6f27-125">The default is 16.</span></span>|  
|<span data-ttu-id="c6f27-126">messageVersion</span><span class="sxs-lookup"><span data-stu-id="c6f27-126">messageVersion</span></span>|<span data-ttu-id="c6f27-127">Gibt die Versionen der SOAP-Nachricht und WS-Adressierung an, die verwendet oder erwartet werden.</span><span class="sxs-lookup"><span data-stu-id="c6f27-127">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c6f27-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c6f27-128">Child Elements</span></span>  
  
|<span data-ttu-id="c6f27-129">Element</span><span class="sxs-lookup"><span data-stu-id="c6f27-129">Element</span></span>|<span data-ttu-id="c6f27-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c6f27-130">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c6f27-131">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c6f27-131">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="c6f27-132">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="c6f27-132">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="c6f27-133">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="c6f27-133">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c6f27-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c6f27-134">Parent Elements</span></span>  
  
|<span data-ttu-id="c6f27-135">Element</span><span class="sxs-lookup"><span data-stu-id="c6f27-135">Element</span></span>|<span data-ttu-id="c6f27-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c6f27-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6f27-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="c6f27-137">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="c6f27-138">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="c6f27-138">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6f27-139">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c6f27-139">Remarks</span></span>  
 <span data-ttu-id="c6f27-140">Beim Codieren wird eine Nachricht in eine Bytefolge transformiert.</span><span class="sxs-lookup"><span data-stu-id="c6f27-140">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="c6f27-141">Beim Decodieren wird dieser Prozess umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="c6f27-141">Decoding is the reverse process.</span></span> <span data-ttu-id="c6f27-142">Windows Communication Foundation (WCF) umfasst drei Codierungs Typen für SOAP-Nachrichten: Text, Binär und MTOM (Message Transmission Optimization Mechanism).</span><span class="sxs-lookup"><span data-stu-id="c6f27-142">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="c6f27-143">Das `binaryMessageEncoding`-Element gibt das .NET Binary-Format für XML an und bietet Optionen zum Festlegen der Zeichencodierung und der zu verwendenden SOAP- und WS-Adressierungsversion.</span><span class="sxs-lookup"><span data-stu-id="c6f27-143">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="c6f27-144">Der Binärnachrichtenencoder verschlüsselt die Windows Communication Foundation (WCF)-Nachrichten bei der Übertragung im Binärformat.</span><span class="sxs-lookup"><span data-stu-id="c6f27-144">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="c6f27-145">Diese Verschlüsselung resultiert zwar in einer schnellen Nachrichtenübertragung, die auf den WS-\*-Standards basierende Interoperabilität geht aber verloren.</span><span class="sxs-lookup"><span data-stu-id="c6f27-145">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6f27-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c6f27-146">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="c6f27-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6f27-147">See also</span></span>

- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [<span data-ttu-id="c6f27-148">Nachrichtencodierung</span><span class="sxs-lookup"><span data-stu-id="c6f27-148">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="c6f27-149">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="c6f27-149">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="c6f27-150">Bindungen</span><span class="sxs-lookup"><span data-stu-id="c6f27-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c6f27-151">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="c6f27-151">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c6f27-152">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="c6f27-152">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="c6f27-153">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c6f27-153">\<customBinding></span></span>](custombinding.md)
