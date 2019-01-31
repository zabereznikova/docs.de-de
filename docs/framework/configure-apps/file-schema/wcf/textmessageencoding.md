---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: c9f8347b4ee5f8fdbcf5c65c9a38b171ea6309de
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289600"
---
# <a name="textmessageencoding"></a><span data-ttu-id="d221f-101">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="d221f-101">\<textMessageEncoding></span></span>
<span data-ttu-id="d221f-102">Gibt die Zeichencodierung und die für textbasierte XML-Nachrichten verwendete Nachrichtenversionierung an.</span><span class="sxs-lookup"><span data-stu-id="d221f-102">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
 <span data-ttu-id="d221f-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d221f-103">\<system.serviceModel></span></span>  
<span data-ttu-id="d221f-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d221f-104">\<bindings></span></span>  
<span data-ttu-id="d221f-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d221f-105">\<customBinding></span></span>  
<span data-ttu-id="d221f-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="d221f-106">\<binding></span></span>  
<span data-ttu-id="d221f-107">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="d221f-107">\<textMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d221f-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="d221f-108">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d221f-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d221f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d221f-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d221f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d221f-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="d221f-111">Attributes</span></span>  
  
|<span data-ttu-id="d221f-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="d221f-112">Attribute</span></span>|<span data-ttu-id="d221f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d221f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d221f-114">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="d221f-114">maxReadPoolSize</span></span>|<span data-ttu-id="d221f-115">Eine ganze Zahl, die bestimmt, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="d221f-115">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="d221f-116">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="d221f-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="d221f-117">Der Standard ist 64.</span><span class="sxs-lookup"><span data-stu-id="d221f-117">The default is 64.</span></span>|  
|<span data-ttu-id="d221f-118">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="d221f-118">maxWritePoolSize</span></span>|<span data-ttu-id="d221f-119">Eine ganze Zahl, die bestimmt, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="d221f-119">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="d221f-120">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="d221f-120">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="d221f-121">Der Standard ist 16.</span><span class="sxs-lookup"><span data-stu-id="d221f-121">The default is 16.</span></span>|  
|<span data-ttu-id="d221f-122">messageVersion</span><span class="sxs-lookup"><span data-stu-id="d221f-122">messageVersion</span></span>|<span data-ttu-id="d221f-123">Gibt die SOAP-Version der Nachrichten an, die mithilfe der Bindung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="d221f-123">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="d221f-124">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="d221f-124">Valid values are</span></span><br /><br /> <span data-ttu-id="d221f-125">-Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="d221f-125">-   Soap11Addressing10</span></span><br /><span data-ttu-id="d221f-126">-Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="d221f-126">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="d221f-127">Der Standardwert ist Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="d221f-127">The default is Soap12Addressing10.</span></span> <span data-ttu-id="d221f-128">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="d221f-128">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="d221f-129">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="d221f-129">writeEncoding</span></span>|<span data-ttu-id="d221f-130">Gibt die Zeichensatzcodierung an, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d221f-130">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="d221f-131">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="d221f-131">Valid values are</span></span><br /><br /> <span data-ttu-id="d221f-132">-   UnicodeFffeTextEncoding: Unicode-BigEndian-Codierung</span><span class="sxs-lookup"><span data-stu-id="d221f-132">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="d221f-133">-Utf16TextEncoding: Unicode-Codierung</span><span class="sxs-lookup"><span data-stu-id="d221f-133">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="d221f-134">-   Utf8TextEncoding: 8-Bit-Codierung</span><span class="sxs-lookup"><span data-stu-id="d221f-134">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="d221f-135">Der Standardwert ist Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="d221f-135">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="d221f-136">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="d221f-136">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d221f-137">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d221f-137">Child Elements</span></span>  
  
|<span data-ttu-id="d221f-138">Element</span><span class="sxs-lookup"><span data-stu-id="d221f-138">Element</span></span>|<span data-ttu-id="d221f-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d221f-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d221f-140">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="d221f-140">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="d221f-141">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="d221f-141">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="d221f-142">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="d221f-142">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d221f-143">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d221f-143">Parent Elements</span></span>  
  
|<span data-ttu-id="d221f-144">Element</span><span class="sxs-lookup"><span data-stu-id="d221f-144">Element</span></span>|<span data-ttu-id="d221f-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d221f-145">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d221f-146">\<binding></span><span class="sxs-lookup"><span data-stu-id="d221f-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="d221f-147">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="d221f-147">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d221f-148">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d221f-148">Remarks</span></span>  
 <span data-ttu-id="d221f-149">Beim Codieren wird eine Nachricht in eine Bytefolge transformiert.</span><span class="sxs-lookup"><span data-stu-id="d221f-149">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="d221f-150">Beim Decodieren wird dieser Prozess umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="d221f-150">Decoding is the reverse process.</span></span> <span data-ttu-id="d221f-151">Windows Communication Foundation (WCF) enthält drei Typen für die Codierung von SOAP-Nachrichten: Text, Binär und Message Transmission Optimization Mechanism (MTOM).</span><span class="sxs-lookup"><span data-stu-id="d221f-151">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="d221f-152">Die vom `textMessageEncoding`-Element dargestellte Textcodierung ist am besten für die Interoperabilität geeignet, jedoch der am wenigsten effektive Encoder für XML-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="d221f-152">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="d221f-153">Der Textencoder erstellt textbasierte Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="d221f-153">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="d221f-154">Von diesem Encoder erzeugte Nachrichten sind für die WS-\*-basierte Interoperabilität geeignet.</span><span class="sxs-lookup"><span data-stu-id="d221f-154">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="d221f-155">Der Webdienst oder Webdienstclient kann im Allgemeinen Text-XML verstehen.</span><span class="sxs-lookup"><span data-stu-id="d221f-155">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="d221f-156">Das Übertragen großer Binärdatenblöcke als Text ist allerdings die am wenigsten effiziente Methode zum Verschlüsseln von XML-Meldungen.</span><span class="sxs-lookup"><span data-stu-id="d221f-156">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d221f-157">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d221f-157">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="d221f-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d221f-158">See also</span></span>
- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="d221f-159">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="d221f-159">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="d221f-160">Nachrichtencodierung</span><span class="sxs-lookup"><span data-stu-id="d221f-160">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="d221f-161">Bindungen</span><span class="sxs-lookup"><span data-stu-id="d221f-161">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="d221f-162">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="d221f-162">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d221f-163">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="d221f-163">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="d221f-164">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d221f-164">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
