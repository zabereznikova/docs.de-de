---
title: <mtomMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: be0a11c71083c713042ab572cb78fbae27d52912
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277692"
---
# <a name="mtommessageencoding"></a><span data-ttu-id="463d6-101">\<mtomMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="463d6-101">\<mtomMessageEncoding></span></span>
<span data-ttu-id="463d6-102">Gibt die Codierungs- und Nachrichtenversionierung an, die für SOAP MTOM-basierte (Message Transmission Optimization Mechanism) Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="463d6-102">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
 <span data-ttu-id="463d6-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="463d6-103">\<system.serviceModel></span></span>  
<span data-ttu-id="463d6-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="463d6-104">\<bindings></span></span>  
<span data-ttu-id="463d6-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="463d6-105">\<customBinding></span></span>  
<span data-ttu-id="463d6-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="463d6-106">\<binding></span></span>  
<span data-ttu-id="463d6-107">\<mtomMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="463d6-107">\<mtomMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="463d6-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="463d6-108">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding maxBufferSize="Integer"
                     maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing1/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="463d6-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="463d6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="463d6-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="463d6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="463d6-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="463d6-111">Attributes</span></span>  
  
|<span data-ttu-id="463d6-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="463d6-112">Attribute</span></span>|<span data-ttu-id="463d6-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="463d6-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="463d6-114">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="463d6-114">maxBufferSize</span></span>|<span data-ttu-id="463d6-115">Eine ganze Zahl, die die maximale Größe des Puffers angibt.</span><span class="sxs-lookup"><span data-stu-id="463d6-115">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="463d6-116">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="463d6-116">maxReadPoolSize</span></span>|<span data-ttu-id="463d6-117">Eine ganze Zahl, die bestimmt, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="463d6-117">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="463d6-118">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="463d6-118">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="463d6-119">Der Standard ist 64.</span><span class="sxs-lookup"><span data-stu-id="463d6-119">The default is 64.</span></span>|  
|<span data-ttu-id="463d6-120">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="463d6-120">maxWritePoolSize</span></span>|<span data-ttu-id="463d6-121">Eine ganze Zahl, die bestimmt, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="463d6-121">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="463d6-122">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="463d6-122">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="463d6-123">Der Standard ist 16.</span><span class="sxs-lookup"><span data-stu-id="463d6-123">The default is 16.</span></span>|  
|<span data-ttu-id="463d6-124">messageVersion</span><span class="sxs-lookup"><span data-stu-id="463d6-124">messageVersion</span></span>|<span data-ttu-id="463d6-125">Gibt die SOAP-Version der Nachrichten an, die mithilfe der Bindung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="463d6-125">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="463d6-126">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="463d6-126">Valid values are</span></span><br /><br /> <span data-ttu-id="463d6-127">-Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="463d6-127">-   Soap11Addressing1</span></span><br /><span data-ttu-id="463d6-128">-Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="463d6-128">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="463d6-129">Der Standardwert ist Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="463d6-129">The default is Soap12Addressing10.</span></span> <span data-ttu-id="463d6-130">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="463d6-130">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="463d6-131">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="463d6-131">writeEncoding</span></span>|<span data-ttu-id="463d6-132">Gibt die Zeichensatzcodierung an, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="463d6-132">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="463d6-133">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="463d6-133">Valid values are</span></span><br /><br /> <span data-ttu-id="463d6-134">-   UnicodeFffeTextEncoding: Unicode-BigEndian-Codierung</span><span class="sxs-lookup"><span data-stu-id="463d6-134">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="463d6-135">-Utf16TextEncoding: Unicode-Codierung</span><span class="sxs-lookup"><span data-stu-id="463d6-135">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="463d6-136">-   Utf8TextEncoding: 8-Bit-Codierung</span><span class="sxs-lookup"><span data-stu-id="463d6-136">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="463d6-137">Der Standardwert ist Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="463d6-137">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="463d6-138">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="463d6-138">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="463d6-139">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="463d6-139">Child Elements</span></span>  
  
|<span data-ttu-id="463d6-140">Element</span><span class="sxs-lookup"><span data-stu-id="463d6-140">Element</span></span>|<span data-ttu-id="463d6-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="463d6-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="463d6-142">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="463d6-142">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="463d6-143">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="463d6-143">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="463d6-144">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="463d6-144">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="463d6-145">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="463d6-145">Parent Elements</span></span>  
  
|<span data-ttu-id="463d6-146">Element</span><span class="sxs-lookup"><span data-stu-id="463d6-146">Element</span></span>|<span data-ttu-id="463d6-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="463d6-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="463d6-148">\<binding></span><span class="sxs-lookup"><span data-stu-id="463d6-148">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="463d6-149">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="463d6-149">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="463d6-150">Hinweise</span><span class="sxs-lookup"><span data-stu-id="463d6-150">Remarks</span></span>  
 <span data-ttu-id="463d6-151">Beim Codieren wird eine Nachricht in eine Bytefolge transformiert.</span><span class="sxs-lookup"><span data-stu-id="463d6-151">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="463d6-152">Beim Decodieren wird dieser Prozess umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="463d6-152">Decoding is the reverse process.</span></span> <span data-ttu-id="463d6-153">Windows Communication Foundation (WCF) enthält drei Typen für die Codierung von SOAP-Nachrichten: Text, Binär und Message Transmission Optimization Mechanism (MTOM).</span><span class="sxs-lookup"><span data-stu-id="463d6-153">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="463d6-154">Das `MtomMessageEncoding`-Element gibt die Zeichencodierung und die für Nachrichten mit MTOM-Verschlüsselung (Message Transmission Optimization Mechanism) verwendete Nachrichtenversion und andere Einstellungen an.</span><span class="sxs-lookup"><span data-stu-id="463d6-154">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="463d6-155">MTOM ist eine effiziente Technologie zum Übertragen von Binärdaten in WCF-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="463d6-155">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="463d6-156">Der MTOM-Encoder versucht, einen Ausgleich zwischen Effizienz und Interoperabilität zu schaffen.</span><span class="sxs-lookup"><span data-stu-id="463d6-156">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="463d6-157">Die MTOM-Verschlüsselung überträgt die meisten XML-Daten in Textform, optimiert aber große Binärdatenblöcke durch Übertragung ohne Konvertierung in ihr base64-verschlüsseltes Format.</span><span class="sxs-lookup"><span data-stu-id="463d6-157">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="463d6-158">Beispiel</span><span class="sxs-lookup"><span data-stu-id="463d6-158">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap11Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="463d6-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="463d6-159">See also</span></span>
- <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
- [<span data-ttu-id="463d6-160">Nachrichtencodierung</span><span class="sxs-lookup"><span data-stu-id="463d6-160">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="463d6-161">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="463d6-161">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="463d6-162">Bindungen</span><span class="sxs-lookup"><span data-stu-id="463d6-162">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="463d6-163">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="463d6-163">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="463d6-164">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="463d6-164">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="463d6-165">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="463d6-165">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
