---
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: faad93554954accd341a1fc2262251fbda61910c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254534"
---
# <a name="binarymessageencoding"></a><span data-ttu-id="ea68c-101">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="ea68c-101">\<binaryMessageEncoding></span></span>
<span data-ttu-id="ea68c-102">Definiert einen Binärnachrichtenencoder, der die Windows Communication Foundation (WCF)-Nachrichten bei der Übertragung im Binärformat verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="ea68c-102">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
 <span data-ttu-id="ea68c-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ea68c-103">\<system.serviceModel></span></span>  
<span data-ttu-id="ea68c-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="ea68c-104">\<bindings></span></span>  
<span data-ttu-id="ea68c-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ea68c-105">\<customBinding></span></span>  
<span data-ttu-id="ea68c-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="ea68c-106">\<binding></span></span>  
<span data-ttu-id="ea68c-107">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="ea68c-107">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea68c-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea68c-108">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea68c-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ea68c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ea68c-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ea68c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea68c-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="ea68c-111">Attributes</span></span>  
  
|<span data-ttu-id="ea68c-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="ea68c-112">Attribute</span></span>|<span data-ttu-id="ea68c-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea68c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ea68c-114">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="ea68c-114">maxReadPoolSize</span></span>|<span data-ttu-id="ea68c-115">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="ea68c-115">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="ea68c-116">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="ea68c-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="ea68c-117">Der Standard ist 64.</span><span class="sxs-lookup"><span data-stu-id="ea68c-117">The default is 64.</span></span>|  
|<span data-ttu-id="ea68c-118">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="ea68c-118">maxSessionSize</span></span>|<span data-ttu-id="ea68c-119">Eine positive ganze Zahl, die die Größe des Puffers in Bytes festlegt, der zum Verschlüsseln von Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ea68c-119">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="ea68c-120">Eine größerer Puffer erhöht die Codierungsgeschwindigkeit auf Kosten der Größe des Workingsets.</span><span class="sxs-lookup"><span data-stu-id="ea68c-120">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="ea68c-121">Der Standard ist 2048.</span><span class="sxs-lookup"><span data-stu-id="ea68c-121">The default is 2048.</span></span>|  
|<span data-ttu-id="ea68c-122">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="ea68c-122">maxWritePoolSize</span></span>|<span data-ttu-id="ea68c-123">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="ea68c-123">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="ea68c-124">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="ea68c-124">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="ea68c-125">Der Standard ist 16.</span><span class="sxs-lookup"><span data-stu-id="ea68c-125">The default is 16.</span></span>|  
|<span data-ttu-id="ea68c-126">messageVersion</span><span class="sxs-lookup"><span data-stu-id="ea68c-126">messageVersion</span></span>|<span data-ttu-id="ea68c-127">Gibt die Versionen der SOAP-Nachricht und WS-Adressierung an, die verwendet oder erwartet werden.</span><span class="sxs-lookup"><span data-stu-id="ea68c-127">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea68c-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ea68c-128">Child Elements</span></span>  
  
|<span data-ttu-id="ea68c-129">Element</span><span class="sxs-lookup"><span data-stu-id="ea68c-129">Element</span></span>|<span data-ttu-id="ea68c-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea68c-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea68c-131">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="ea68c-131">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="ea68c-132">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="ea68c-132">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="ea68c-133">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="ea68c-133">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ea68c-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ea68c-134">Parent Elements</span></span>  
  
|<span data-ttu-id="ea68c-135">Element</span><span class="sxs-lookup"><span data-stu-id="ea68c-135">Element</span></span>|<span data-ttu-id="ea68c-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea68c-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea68c-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="ea68c-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="ea68c-138">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="ea68c-138">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea68c-139">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ea68c-139">Remarks</span></span>  
 <span data-ttu-id="ea68c-140">Beim Codieren wird eine Nachricht in eine Bytefolge transformiert.</span><span class="sxs-lookup"><span data-stu-id="ea68c-140">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="ea68c-141">Beim Decodieren wird dieser Prozess umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="ea68c-141">Decoding is the reverse process.</span></span> <span data-ttu-id="ea68c-142">Windows Communication Foundation (WCF) enthält drei Typen für die Codierung von SOAP-Nachrichten: Text, Binär und Message Transmission Optimization Mechanism (MTOM).</span><span class="sxs-lookup"><span data-stu-id="ea68c-142">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="ea68c-143">Das `binaryMessageEncoding`-Element gibt das .NET Binary-Format für XML an und bietet Optionen zum Festlegen der Zeichencodierung und der zu verwendenden SOAP- und WS-Adressierungsversion.</span><span class="sxs-lookup"><span data-stu-id="ea68c-143">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="ea68c-144">Der Binärnachrichtenencoder verschlüsselt die Windows Communication Foundation (WCF)-Nachrichten bei der Übertragung im Binärformat.</span><span class="sxs-lookup"><span data-stu-id="ea68c-144">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="ea68c-145">Diese Verschlüsselung resultiert zwar in einer schnellen Nachrichtenübertragung, die auf den WS-\*-Standards basierende Interoperabilität geht aber verloren.</span><span class="sxs-lookup"><span data-stu-id="ea68c-145">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea68c-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ea68c-146">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="ea68c-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea68c-147">See also</span></span>
- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [<span data-ttu-id="ea68c-148">Nachrichtencodierung</span><span class="sxs-lookup"><span data-stu-id="ea68c-148">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="ea68c-149">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="ea68c-149">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="ea68c-150">Bindungen</span><span class="sxs-lookup"><span data-stu-id="ea68c-150">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="ea68c-151">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="ea68c-151">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ea68c-152">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="ea68c-152">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="ea68c-153">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ea68c-153">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
