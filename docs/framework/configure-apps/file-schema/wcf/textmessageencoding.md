---
title: '&lt;textMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: 0ee50a4b5adeede2dd531ba734ac9fb420f3b713
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150239"
---
# <a name="lttextmessageencodinggt"></a><span data-ttu-id="c7bb8-102">&lt;textMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="c7bb8-102">&lt;textMessageEncoding&gt;</span></span>
<span data-ttu-id="c7bb8-103">Gibt die Zeichencodierung und die für textbasierte XML-Nachrichten verwendete Nachrichtenversionierung an.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-103">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
 <span data-ttu-id="c7bb8-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c7bb8-104">\<system.serviceModel></span></span>  
<span data-ttu-id="c7bb8-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="c7bb8-105">\<bindings></span></span>  
<span data-ttu-id="c7bb8-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c7bb8-106">\<customBinding></span></span>  
<span data-ttu-id="c7bb8-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="c7bb8-107">\<binding></span></span>  
<span data-ttu-id="c7bb8-108">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="c7bb8-108">\<textMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7bb8-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7bb8-109">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c7bb8-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c7bb8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c7bb8-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c7bb8-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="c7bb8-112">Attributes</span></span>  
  
|<span data-ttu-id="c7bb8-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="c7bb8-113">Attribute</span></span>|<span data-ttu-id="c7bb8-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7bb8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c7bb8-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="c7bb8-115">maxReadPoolSize</span></span>|<span data-ttu-id="c7bb8-116">Eine ganze Zahl, die bestimmt, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-116">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="c7bb8-117">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="c7bb8-118">Der Standard ist 64.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-118">The default is 64.</span></span>|  
|<span data-ttu-id="c7bb8-119">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="c7bb8-119">maxWritePoolSize</span></span>|<span data-ttu-id="c7bb8-120">Eine ganze Zahl, die bestimmt, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-120">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="c7bb8-121">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-121">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="c7bb8-122">Der Standard ist 16.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-122">The default is 16.</span></span>|  
|<span data-ttu-id="c7bb8-123">messageVersion</span><span class="sxs-lookup"><span data-stu-id="c7bb8-123">messageVersion</span></span>|<span data-ttu-id="c7bb8-124">Gibt die SOAP-Version der Nachrichten an, die mithilfe der Bindung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-124">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="c7bb8-125">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="c7bb8-125">Valid values are</span></span><br /><br /> <span data-ttu-id="c7bb8-126">-Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="c7bb8-126">-   Soap11Addressing10</span></span><br /><span data-ttu-id="c7bb8-127">-Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="c7bb8-127">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="c7bb8-128">Der Standardwert ist Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-128">The default is Soap12Addressing10.</span></span> <span data-ttu-id="c7bb8-129">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-129">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="c7bb8-130">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="c7bb8-130">writeEncoding</span></span>|<span data-ttu-id="c7bb8-131">Gibt die Zeichensatzcodierung an, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-131">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="c7bb8-132">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="c7bb8-132">Valid values are</span></span><br /><br /> <span data-ttu-id="c7bb8-133">-UnicodeFffeTextEncoding: Unicode-BigEndian-Codierung</span><span class="sxs-lookup"><span data-stu-id="c7bb8-133">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="c7bb8-134">-Utf16TextEncoding: Unicode-Codierung</span><span class="sxs-lookup"><span data-stu-id="c7bb8-134">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="c7bb8-135">-Utf8TextEncoding: 8-Bit-Codierung</span><span class="sxs-lookup"><span data-stu-id="c7bb8-135">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="c7bb8-136">Der Standardwert ist Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-136">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="c7bb8-137">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-137">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c7bb8-138">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c7bb8-138">Child Elements</span></span>  
  
|<span data-ttu-id="c7bb8-139">Element</span><span class="sxs-lookup"><span data-stu-id="c7bb8-139">Element</span></span>|<span data-ttu-id="c7bb8-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7bb8-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c7bb8-141">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="c7bb8-141">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="c7bb8-142">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-142">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="c7bb8-143">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-143">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c7bb8-144">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c7bb8-144">Parent Elements</span></span>  
  
|<span data-ttu-id="c7bb8-145">Element</span><span class="sxs-lookup"><span data-stu-id="c7bb8-145">Element</span></span>|<span data-ttu-id="c7bb8-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7bb8-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c7bb8-147">\<binding></span><span class="sxs-lookup"><span data-stu-id="c7bb8-147">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="c7bb8-148">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-148">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7bb8-149">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c7bb8-149">Remarks</span></span>  
 <span data-ttu-id="c7bb8-150">Beim Codieren wird eine Nachricht in eine Bytefolge transformiert.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-150">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="c7bb8-151">Beim Decodieren wird dieser Prozess umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-151">Decoding is the reverse process.</span></span> <span data-ttu-id="c7bb8-152">Windows Communication Foundation (WCF) enthält drei Typen für die Codierung von SOAP-Nachrichten: Text, Binär und Message Transmission Optimization Mechanism (MTOM).</span><span class="sxs-lookup"><span data-stu-id="c7bb8-152">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="c7bb8-153">Die vom `textMessageEncoding`-Element dargestellte Textcodierung ist am besten für die Interoperabilität geeignet, jedoch der am wenigsten effektive Encoder für XML-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-153">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="c7bb8-154">Der Textencoder erstellt textbasierte Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-154">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="c7bb8-155">Von diesem Encoder erzeugte Nachrichten sind für die WS-\*-basierte Interoperabilität geeignet.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-155">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="c7bb8-156">Der Webdienst oder Webdienstclient kann im Allgemeinen Text-XML verstehen.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-156">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="c7bb8-157">Das Übertragen großer Binärdatenblöcke als Text ist allerdings die am wenigsten effiziente Methode zum Verschlüsseln von XML-Meldungen.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-157">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7bb8-158">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c7bb8-158">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="c7bb8-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7bb8-159">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
 [<span data-ttu-id="c7bb8-160">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="c7bb8-160">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="c7bb8-161">Nachrichtencodierung</span><span class="sxs-lookup"><span data-stu-id="c7bb8-161">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="c7bb8-162">Bindungen</span><span class="sxs-lookup"><span data-stu-id="c7bb8-162">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="c7bb8-163">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="c7bb8-163">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="c7bb8-164">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="c7bb8-164">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="c7bb8-165">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c7bb8-165">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
