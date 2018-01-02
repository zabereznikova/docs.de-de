---
title: '&lt;binaryMessageEncoding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 503c0edf3a21b3fb0f57b5199aa2a1a17df4222d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltbinarymessageencodinggt"></a><span data-ttu-id="934bf-102">&lt;binaryMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="934bf-102">&lt;binaryMessageEncoding&gt;</span></span>
<span data-ttu-id="934bf-103">Definiert einen Binärnachrichtenencoder, der die Windows Communication Foundation (WCF)-Nachrichten bei der Übertragung im Binärformat verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="934bf-103">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
 <span data-ttu-id="934bf-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="934bf-104">\<system.serviceModel></span></span>  
<span data-ttu-id="934bf-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="934bf-105">\<bindings></span></span>  
<span data-ttu-id="934bf-106">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="934bf-106">\<customBinding></span></span>  
<span data-ttu-id="934bf-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="934bf-107">\<binding></span></span>  
<span data-ttu-id="934bf-108">\<BinaryMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="934bf-108">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="934bf-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="934bf-109">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding   
      maxReadPoolSize="Integer"  
   maxSessionSize="Integer"   
   maxWritePoolSize="Integer"   messageVersion="Soap11Addressing10/Soap12Addressing10" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="934bf-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="934bf-110">Attributes and Elements</span></span>  
 <span data-ttu-id="934bf-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="934bf-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="934bf-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="934bf-112">Attributes</span></span>  
  
|<span data-ttu-id="934bf-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="934bf-113">Attribute</span></span>|<span data-ttu-id="934bf-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="934bf-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="934bf-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="934bf-115">maxReadPoolSize</span></span>|<span data-ttu-id="934bf-116">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="934bf-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="934bf-117">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="934bf-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="934bf-118">Der Standard ist 64.</span><span class="sxs-lookup"><span data-stu-id="934bf-118">The default is 64.</span></span>|  
|<span data-ttu-id="934bf-119">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="934bf-119">maxSessionSize</span></span>|<span data-ttu-id="934bf-120">Eine positive ganze Zahl, die die Größe des Puffers in Bytes festlegt, der zum Verschlüsseln von Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="934bf-120">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="934bf-121">Eine größerer Puffer erhöht die Codierungsgeschwindigkeit auf Kosten der Größe des Workingsets.</span><span class="sxs-lookup"><span data-stu-id="934bf-121">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="934bf-122">Der Standard ist 2048.</span><span class="sxs-lookup"><span data-stu-id="934bf-122">The default is 2048.</span></span>|  
|<span data-ttu-id="934bf-123">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="934bf-123">maxWritePoolSize</span></span>|<span data-ttu-id="934bf-124">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="934bf-124">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="934bf-125">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="934bf-125">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="934bf-126">Der Standard ist 16.</span><span class="sxs-lookup"><span data-stu-id="934bf-126">The default is 16.</span></span>|  
|<span data-ttu-id="934bf-127">messageVersion</span><span class="sxs-lookup"><span data-stu-id="934bf-127">messageVersion</span></span>|<span data-ttu-id="934bf-128">Gibt die Versionen der SOAP-Nachricht und WS-Adressierung an, die verwendet oder erwartet werden.</span><span class="sxs-lookup"><span data-stu-id="934bf-128">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="934bf-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="934bf-129">Child Elements</span></span>  
  
|<span data-ttu-id="934bf-130">Element</span><span class="sxs-lookup"><span data-stu-id="934bf-130">Element</span></span>|<span data-ttu-id="934bf-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="934bf-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="934bf-132">\<ReaderQuotas ></span><span class="sxs-lookup"><span data-stu-id="934bf-132">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="934bf-133">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="934bf-133">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="934bf-134">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="934bf-134">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="934bf-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="934bf-135">Parent Elements</span></span>  
  
|<span data-ttu-id="934bf-136">Element</span><span class="sxs-lookup"><span data-stu-id="934bf-136">Element</span></span>|<span data-ttu-id="934bf-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="934bf-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="934bf-138">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="934bf-138">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="934bf-139">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="934bf-139">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="934bf-140">Hinweise</span><span class="sxs-lookup"><span data-stu-id="934bf-140">Remarks</span></span>  
 <span data-ttu-id="934bf-141">Beim Codieren wird eine Nachricht in eine Bytefolge transformiert.</span><span class="sxs-lookup"><span data-stu-id="934bf-141">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="934bf-142">Beim Decodieren wird dieser Prozess umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="934bf-142">Decoding is the reverse process.</span></span> <span data-ttu-id="934bf-143">Windows Communication Foundation (WCF) enthält drei Typen für die Codierung von SOAP-Nachrichten: Text, binär und Message Transmission Optimization Mechanism (MTOM).</span><span class="sxs-lookup"><span data-stu-id="934bf-143">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="934bf-144">Das `binaryMessageEncoding`-Element gibt das .NET Binary-Format für XML an und bietet Optionen zum Festlegen der Zeichencodierung und der zu verwendenden SOAP- und WS-Adressierungsversion.</span><span class="sxs-lookup"><span data-stu-id="934bf-144">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="934bf-145">Der Binärnachrichtenencoder verschlüsselt die Windows Communication Foundation (WCF)-Nachrichten bei der Übertragung im Binärformat.</span><span class="sxs-lookup"><span data-stu-id="934bf-145">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="934bf-146">Diese Verschlüsselung resultiert zwar in einer schnellen Nachrichtenübertragung, die auf den WS-*-Standards basierende Interoperabilität geht aber verloren.</span><span class="sxs-lookup"><span data-stu-id="934bf-146">While this encoding results in very fast transmission of messages, interoperability based on the WS-* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="934bf-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="934bf-147">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"  
   maxWritePoolSize="2132"  
   maxSessionSize="3141" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="934bf-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="934bf-148">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
 [<span data-ttu-id="934bf-149">Nachrichtencodierung</span><span class="sxs-lookup"><span data-stu-id="934bf-149">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="934bf-150">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="934bf-150">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="934bf-151">Bindungen</span><span class="sxs-lookup"><span data-stu-id="934bf-151">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="934bf-152">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="934bf-152">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="934bf-153">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="934bf-153">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="934bf-154">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="934bf-154">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
