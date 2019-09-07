---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: 1494cee0e412bebc6637ad73354f7c91dc636e15
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399435"
---
# <a name="textmessageencoding"></a><span data-ttu-id="c77fc-101">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="c77fc-101">\<textMessageEncoding></span></span>
<span data-ttu-id="c77fc-102">Gibt die Zeichencodierung und die für textbasierte XML-Nachrichten verwendete Nachrichtenversionierung an.</span><span class="sxs-lookup"><span data-stu-id="c77fc-102">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
<span data-ttu-id="c77fc-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c77fc-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c77fc-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c77fc-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c77fc-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="c77fc-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="c77fc-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding->** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="c77fc-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="c77fc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="c77fc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="c77fc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<textMessageEncoding->**</span><span class="sxs-lookup"><span data-stu-id="c77fc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<textMessageEncoding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c77fc-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="c77fc-109">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c77fc-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c77fc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c77fc-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c77fc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c77fc-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="c77fc-112">Attributes</span></span>  
  
|<span data-ttu-id="c77fc-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="c77fc-113">Attribute</span></span>|<span data-ttu-id="c77fc-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c77fc-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c77fc-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="c77fc-115">maxReadPoolSize</span></span>|<span data-ttu-id="c77fc-116">Eine ganze Zahl, die bestimmt, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="c77fc-116">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="c77fc-117">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="c77fc-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="c77fc-118">Der Standard ist 64.</span><span class="sxs-lookup"><span data-stu-id="c77fc-118">The default is 64.</span></span>|  
|<span data-ttu-id="c77fc-119">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="c77fc-119">maxWritePoolSize</span></span>|<span data-ttu-id="c77fc-120">Eine ganze Zahl, die bestimmt, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="c77fc-120">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="c77fc-121">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="c77fc-121">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="c77fc-122">Der Standardwert ist 16.</span><span class="sxs-lookup"><span data-stu-id="c77fc-122">The default is 16.</span></span>|  
|<span data-ttu-id="c77fc-123">messageVersion</span><span class="sxs-lookup"><span data-stu-id="c77fc-123">messageVersion</span></span>|<span data-ttu-id="c77fc-124">Gibt die SOAP-Version der Nachrichten an, die mithilfe der Bindung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="c77fc-124">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="c77fc-125">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="c77fc-125">Valid values are</span></span><br /><br /> <span data-ttu-id="c77fc-126">- Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="c77fc-126">-   Soap11Addressing10</span></span><br /><span data-ttu-id="c77fc-127">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="c77fc-127">-   Soap12Addressing10</span></span><br /><span data-ttu-id="c77fc-128">- Soap11</span><span class="sxs-lookup"><span data-stu-id="c77fc-128">-   Soap11</span></span><br /><span data-ttu-id="c77fc-129">- Soap12</span><span class="sxs-lookup"><span data-stu-id="c77fc-129">-  Soap12</span></span><br /><br /><span data-ttu-id="c77fc-130">Der Standardwert ist Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="c77fc-130">The default is Soap12Addressing10.</span></span> <span data-ttu-id="c77fc-131">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="c77fc-131">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="c77fc-132">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="c77fc-132">writeEncoding</span></span>|<span data-ttu-id="c77fc-133">Gibt die Zeichensatzcodierung an, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c77fc-133">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="c77fc-134">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="c77fc-134">Valid values are</span></span><br /><br /> <span data-ttu-id="c77fc-135">UnicodeFffeTextEncoding Unicode bigEndian-Codierung</span><span class="sxs-lookup"><span data-stu-id="c77fc-135">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="c77fc-136">Utf16TextEncoding Unicode-Codierung</span><span class="sxs-lookup"><span data-stu-id="c77fc-136">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="c77fc-137">Utf8TextEncoding 8-Bit-Codierung</span><span class="sxs-lookup"><span data-stu-id="c77fc-137">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="c77fc-138">Der Standardwert ist Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="c77fc-138">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="c77fc-139">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="c77fc-139">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c77fc-140">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c77fc-140">Child Elements</span></span>  
  
|<span data-ttu-id="c77fc-141">Element</span><span class="sxs-lookup"><span data-stu-id="c77fc-141">Element</span></span>|<span data-ttu-id="c77fc-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c77fc-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c77fc-143">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c77fc-143">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="c77fc-144">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="c77fc-144">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="c77fc-145">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="c77fc-145">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c77fc-146">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c77fc-146">Parent Elements</span></span>  
  
|<span data-ttu-id="c77fc-147">Element</span><span class="sxs-lookup"><span data-stu-id="c77fc-147">Element</span></span>|<span data-ttu-id="c77fc-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c77fc-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c77fc-149">\<binding></span><span class="sxs-lookup"><span data-stu-id="c77fc-149">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="c77fc-150">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="c77fc-150">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c77fc-151">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c77fc-151">Remarks</span></span>  
 <span data-ttu-id="c77fc-152">Beim Codieren wird eine Nachricht in eine Bytefolge transformiert.</span><span class="sxs-lookup"><span data-stu-id="c77fc-152">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="c77fc-153">Beim Decodieren wird dieser Prozess umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="c77fc-153">Decoding is the reverse process.</span></span> <span data-ttu-id="c77fc-154">Windows Communication Foundation (WCF) umfasst drei Codierungs Typen für SOAP-Nachrichten: Text, Binär und MTOM (Message Transmission Optimization Mechanism).</span><span class="sxs-lookup"><span data-stu-id="c77fc-154">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="c77fc-155">Die vom `textMessageEncoding`-Element dargestellte Textcodierung ist am besten für die Interoperabilität geeignet, jedoch der am wenigsten effektive Encoder für XML-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="c77fc-155">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="c77fc-156">Der Textencoder erstellt textbasierte Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="c77fc-156">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="c77fc-157">Von diesem Encoder erzeugte Nachrichten sind für die WS-\*-basierte Interoperabilität geeignet.</span><span class="sxs-lookup"><span data-stu-id="c77fc-157">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="c77fc-158">Der Webdienst oder Webdienstclient kann im Allgemeinen Text-XML verstehen.</span><span class="sxs-lookup"><span data-stu-id="c77fc-158">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="c77fc-159">Das Übertragen großer Binärdatenblöcke als Text ist allerdings die am wenigsten effiziente Methode zum Verschlüsseln von XML-Meldungen.</span><span class="sxs-lookup"><span data-stu-id="c77fc-159">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c77fc-160">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c77fc-160">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="c77fc-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c77fc-161">See also</span></span>

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="c77fc-162">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="c77fc-162">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="c77fc-163">Nachrichtencodierung</span><span class="sxs-lookup"><span data-stu-id="c77fc-163">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="c77fc-164">Bindungen</span><span class="sxs-lookup"><span data-stu-id="c77fc-164">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c77fc-165">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="c77fc-165">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c77fc-166">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="c77fc-166">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="c77fc-167">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c77fc-167">\<customBinding></span></span>](custombinding.md)
