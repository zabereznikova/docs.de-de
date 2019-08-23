---
title: <mtomMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: 70a124fda5bc0e52e1271716f7e2166b7717b49a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933185"
---
# <a name="mtommessageencoding"></a><span data-ttu-id="eb3d8-101">\<mtomMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="eb3d8-101">\<mtomMessageEncoding></span></span>
<span data-ttu-id="eb3d8-102">Gibt die Codierungs- und Nachrichtenversionierung an, die für SOAP MTOM-basierte (Message Transmission Optimization Mechanism) Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-102">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
 <span data-ttu-id="eb3d8-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="eb3d8-103">\<system.serviceModel></span></span>  
<span data-ttu-id="eb3d8-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="eb3d8-104">\<bindings></span></span>  
<span data-ttu-id="eb3d8-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="eb3d8-105">\<customBinding></span></span>  
<span data-ttu-id="eb3d8-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="eb3d8-106">\<binding></span></span>  
<span data-ttu-id="eb3d8-107">\<mtomMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="eb3d8-107">\<mtomMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb3d8-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb3d8-108">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding maxBufferSize="Integer"
                     maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing1/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb3d8-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="eb3d8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="eb3d8-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb3d8-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="eb3d8-111">Attributes</span></span>  
  
|<span data-ttu-id="eb3d8-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="eb3d8-112">Attribute</span></span>|<span data-ttu-id="eb3d8-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb3d8-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eb3d8-114">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="eb3d8-114">maxBufferSize</span></span>|<span data-ttu-id="eb3d8-115">Eine ganze Zahl, die die maximale Größe des Puffers angibt.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-115">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="eb3d8-116">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="eb3d8-116">maxReadPoolSize</span></span>|<span data-ttu-id="eb3d8-117">Eine ganze Zahl, die bestimmt, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-117">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="eb3d8-118">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-118">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="eb3d8-119">Der Standard ist 64.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-119">The default is 64.</span></span>|  
|<span data-ttu-id="eb3d8-120">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="eb3d8-120">maxWritePoolSize</span></span>|<span data-ttu-id="eb3d8-121">Eine ganze Zahl, die bestimmt, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-121">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="eb3d8-122">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-122">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="eb3d8-123">Der Standardwert ist 16.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-123">The default is 16.</span></span>|  
|<span data-ttu-id="eb3d8-124">messageVersion</span><span class="sxs-lookup"><span data-stu-id="eb3d8-124">messageVersion</span></span>|<span data-ttu-id="eb3d8-125">Gibt die SOAP-Version der Nachrichten an, die mithilfe der Bindung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-125">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="eb3d8-126">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="eb3d8-126">Valid values are</span></span><br /><br /> <span data-ttu-id="eb3d8-127">- Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="eb3d8-127">-   Soap11Addressing1</span></span><br /><span data-ttu-id="eb3d8-128">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="eb3d8-128">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="eb3d8-129">Der Standardwert ist Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-129">The default is Soap12Addressing10.</span></span> <span data-ttu-id="eb3d8-130">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-130">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="eb3d8-131">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="eb3d8-131">writeEncoding</span></span>|<span data-ttu-id="eb3d8-132">Gibt die Zeichensatzcodierung an, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-132">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="eb3d8-133">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="eb3d8-133">Valid values are</span></span><br /><br /> <span data-ttu-id="eb3d8-134">UnicodeFffeTextEncoding Unicode bigEndian-Codierung</span><span class="sxs-lookup"><span data-stu-id="eb3d8-134">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="eb3d8-135">Utf16TextEncoding Unicode-Codierung</span><span class="sxs-lookup"><span data-stu-id="eb3d8-135">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="eb3d8-136">Utf8TextEncoding 8-Bit-Codierung</span><span class="sxs-lookup"><span data-stu-id="eb3d8-136">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="eb3d8-137">Der Standardwert ist Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-137">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="eb3d8-138">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-138">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb3d8-139">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eb3d8-139">Child Elements</span></span>  
  
|<span data-ttu-id="eb3d8-140">Element</span><span class="sxs-lookup"><span data-stu-id="eb3d8-140">Element</span></span>|<span data-ttu-id="eb3d8-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb3d8-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eb3d8-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eb3d8-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="eb3d8-143">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-143">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="eb3d8-144">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-144">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eb3d8-145">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eb3d8-145">Parent Elements</span></span>  
  
|<span data-ttu-id="eb3d8-146">Element</span><span class="sxs-lookup"><span data-stu-id="eb3d8-146">Element</span></span>|<span data-ttu-id="eb3d8-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb3d8-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb3d8-148">\<binding></span><span class="sxs-lookup"><span data-stu-id="eb3d8-148">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="eb3d8-149">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-149">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb3d8-150">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eb3d8-150">Remarks</span></span>  
 <span data-ttu-id="eb3d8-151">Beim Codieren wird eine Nachricht in eine Bytefolge transformiert.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-151">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="eb3d8-152">Beim Decodieren wird dieser Prozess umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-152">Decoding is the reverse process.</span></span> <span data-ttu-id="eb3d8-153">Windows Communication Foundation (WCF) umfasst drei Codierungs Typen für SOAP-Nachrichten: Text, Binär und MTOM (Message Transmission Optimization Mechanism).</span><span class="sxs-lookup"><span data-stu-id="eb3d8-153">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="eb3d8-154">Das `MtomMessageEncoding`-Element gibt die Zeichencodierung und die für Nachrichten mit MTOM-Verschlüsselung (Message Transmission Optimization Mechanism) verwendete Nachrichtenversion und andere Einstellungen an.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-154">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="eb3d8-155">MTOM ist eine effiziente Technologie zum Übertragen von Binärdaten in WCF-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-155">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="eb3d8-156">Der MTOM-Encoder versucht, einen Ausgleich zwischen Effizienz und Interoperabilität zu schaffen.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-156">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="eb3d8-157">Die MTOM-Verschlüsselung überträgt die meisten XML-Daten in Textform, optimiert aber große Binärdatenblöcke durch Übertragung ohne Konvertierung in ihr base64-verschlüsseltes Format.</span><span class="sxs-lookup"><span data-stu-id="eb3d8-157">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb3d8-158">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eb3d8-158">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap11Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="eb3d8-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb3d8-159">See also</span></span>

- <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
- [<span data-ttu-id="eb3d8-160">Nachrichtencodierung</span><span class="sxs-lookup"><span data-stu-id="eb3d8-160">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="eb3d8-161">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="eb3d8-161">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="eb3d8-162">Bindungen</span><span class="sxs-lookup"><span data-stu-id="eb3d8-162">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="eb3d8-163">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="eb3d8-163">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="eb3d8-164">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="eb3d8-164">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="eb3d8-165">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="eb3d8-165">\<customBinding></span></span>](custombinding.md)
