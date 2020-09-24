---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: 159c581955336575af87a66a796cb78dd35d09c7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158655"
---
# \<textMessageEncoding>

<span data-ttu-id="5d3c0-101">Gibt die Zeichencodierung und die für textbasierte XML-Nachrichten verwendete Nachrichtenversionierung an.</span><span class="sxs-lookup"><span data-stu-id="5d3c0-101">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<textMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="5d3c0-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d3c0-102">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d3c0-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5d3c0-103">Attributes and Elements</span></span>  

 <span data-ttu-id="5d3c0-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5d3c0-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d3c0-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="5d3c0-105">Attributes</span></span>  
  
|<span data-ttu-id="5d3c0-106">attribute</span><span class="sxs-lookup"><span data-stu-id="5d3c0-106">Attribute</span></span>|<span data-ttu-id="5d3c0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d3c0-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5d3c0-108">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="5d3c0-108">maxReadPoolSize</span></span>|<span data-ttu-id="5d3c0-109">Eine ganze Zahl, die bestimmt, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="5d3c0-109">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="5d3c0-110">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="5d3c0-110">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="5d3c0-111">Der Standardwert ist 64.</span><span class="sxs-lookup"><span data-stu-id="5d3c0-111">The default is 64.</span></span>|  
|<span data-ttu-id="5d3c0-112">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="5d3c0-112">maxWritePoolSize</span></span>|<span data-ttu-id="5d3c0-113">Eine ganze Zahl, die bestimmt, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="5d3c0-113">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="5d3c0-114">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="5d3c0-114">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="5d3c0-115">Der Standardwert ist 16.</span><span class="sxs-lookup"><span data-stu-id="5d3c0-115">The default is 16.</span></span>|  
|<span data-ttu-id="5d3c0-116">messageVersion</span><span class="sxs-lookup"><span data-stu-id="5d3c0-116">messageVersion</span></span>|<span data-ttu-id="5d3c0-117">Gibt die SOAP-Version der Nachrichten an, die mithilfe der Bindung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="5d3c0-117">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="5d3c0-118">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="5d3c0-118">Valid values are</span></span><br /><br /> <span data-ttu-id="5d3c0-119">- Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="5d3c0-119">-   Soap11Addressing10</span></span><br /><span data-ttu-id="5d3c0-120">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="5d3c0-120">-   Soap12Addressing10</span></span><br /><span data-ttu-id="5d3c0-121">- Soap11</span><span class="sxs-lookup"><span data-stu-id="5d3c0-121">-   Soap11</span></span><br /><span data-ttu-id="5d3c0-122">- Soap12</span><span class="sxs-lookup"><span data-stu-id="5d3c0-122">-  Soap12</span></span><br /><br /><span data-ttu-id="5d3c0-123">Der Standardwert ist Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="5d3c0-123">The default is Soap12Addressing10.</span></span> <span data-ttu-id="5d3c0-124">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="5d3c0-124">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="5d3c0-125">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="5d3c0-125">writeEncoding</span></span>|<span data-ttu-id="5d3c0-126">Gibt die Zeichensatzcodierung an, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5d3c0-126">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="5d3c0-127">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="5d3c0-127">Valid values are</span></span><br /><br /> <span data-ttu-id="5d3c0-128">-UnicodeFffeTextEncoding: Unicode bigEndian-Codierung</span><span class="sxs-lookup"><span data-stu-id="5d3c0-128">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="5d3c0-129">-Utf16TextEncoding: Unicode-Codierung</span><span class="sxs-lookup"><span data-stu-id="5d3c0-129">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="5d3c0-130">-Utf8TextEncoding: 8-Bit-Codierung</span><span class="sxs-lookup"><span data-stu-id="5d3c0-130">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="5d3c0-131">Der Standardwert ist Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="5d3c0-131">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="5d3c0-132">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="5d3c0-132">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d3c0-133">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5d3c0-133">Child Elements</span></span>  
  
|<span data-ttu-id="5d3c0-134">Element</span><span class="sxs-lookup"><span data-stu-id="5d3c0-134">Element</span></span>|<span data-ttu-id="5d3c0-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d3c0-135">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="5d3c0-136">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="5d3c0-136">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="5d3c0-137">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="5d3c0-137">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5d3c0-138">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5d3c0-138">Parent Elements</span></span>  
  
|<span data-ttu-id="5d3c0-139">Element</span><span class="sxs-lookup"><span data-stu-id="5d3c0-139">Element</span></span>|<span data-ttu-id="5d3c0-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d3c0-140">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="5d3c0-141">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="5d3c0-141">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d3c0-142">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5d3c0-142">Remarks</span></span>  

 <span data-ttu-id="5d3c0-143">Beim Codieren wird eine Nachricht in eine Bytefolge transformiert.</span><span class="sxs-lookup"><span data-stu-id="5d3c0-143">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="5d3c0-144">Beim Decodieren wird dieser Prozess umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="5d3c0-144">Decoding is the reverse process.</span></span> <span data-ttu-id="5d3c0-145">Windows Communication Foundation (WCF) enthält drei Typen für die Codierung von SOAP-Nachrichten: Text, binär und Message Transmission Optimization Mechanism (MTOM).</span><span class="sxs-lookup"><span data-stu-id="5d3c0-145">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="5d3c0-146">Die vom `textMessageEncoding`-Element dargestellte Textcodierung ist am besten für die Interoperabilität geeignet, jedoch der am wenigsten effektive Encoder für XML-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="5d3c0-146">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="5d3c0-147">Der Textencoder erstellt textbasierte Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="5d3c0-147">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="5d3c0-148">Von diesem Encoder erzeugte Nachrichten sind für die WS-\*-basierte Interoperabilität geeignet.</span><span class="sxs-lookup"><span data-stu-id="5d3c0-148">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="5d3c0-149">Der Webdienst oder Webdienstclient kann im Allgemeinen Text-XML verstehen.</span><span class="sxs-lookup"><span data-stu-id="5d3c0-149">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="5d3c0-150">Das Übertragen großer Binärdatenblöcke als Text ist allerdings die am wenigsten effiziente Methode zum Verschlüsseln von XML-Meldungen.</span><span class="sxs-lookup"><span data-stu-id="5d3c0-150">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d3c0-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5d3c0-151">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="5d3c0-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5d3c0-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="5d3c0-153">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="5d3c0-153">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="5d3c0-154">Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="5d3c0-154">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="5d3c0-155">Bindungen</span><span class="sxs-lookup"><span data-stu-id="5d3c0-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5d3c0-156">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="5d3c0-156">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="5d3c0-157">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="5d3c0-157">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
