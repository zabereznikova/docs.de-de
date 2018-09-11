---
title: '&lt;mtomMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: 380aa162d2bb55ac968bdd057a4bb45b2ea6abfe
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2018
ms.locfileid: "44365123"
---
# <a name="ltmtommessageencodinggt"></a><span data-ttu-id="23225-102">&lt;mtomMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="23225-102">&lt;mtomMessageEncoding&gt;</span></span>
<span data-ttu-id="23225-103">Gibt die Codierungs- und Nachrichtenversionierung an, die für SOAP MTOM-basierte (Message Transmission Optimization Mechanism) Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="23225-103">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
 <span data-ttu-id="23225-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="23225-104">\<system.serviceModel></span></span>  
<span data-ttu-id="23225-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="23225-105">\<bindings></span></span>  
<span data-ttu-id="23225-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="23225-106">\<customBinding></span></span>  
<span data-ttu-id="23225-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="23225-107">\<binding></span></span>  
<span data-ttu-id="23225-108">\<MtomMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="23225-108">\<mtomMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23225-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="23225-109">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding   
   maxBufferSize="Integer"  
      maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
   messageVersion="Soap11Addressing1/Soap12Addressing10"  
      writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23225-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="23225-110">Attributes and Elements</span></span>  
 <span data-ttu-id="23225-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="23225-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23225-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="23225-112">Attributes</span></span>  
  
|<span data-ttu-id="23225-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="23225-113">Attribute</span></span>|<span data-ttu-id="23225-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23225-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="23225-115">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="23225-115">maxBufferSize</span></span>|<span data-ttu-id="23225-116">Eine ganze Zahl, die die maximale Größe des Puffers angibt.</span><span class="sxs-lookup"><span data-stu-id="23225-116">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="23225-117">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="23225-117">maxReadPoolSize</span></span>|<span data-ttu-id="23225-118">Eine ganze Zahl, die bestimmt, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="23225-118">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="23225-119">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="23225-119">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="23225-120">Der Standard ist 64.</span><span class="sxs-lookup"><span data-stu-id="23225-120">The default is 64.</span></span>|  
|<span data-ttu-id="23225-121">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="23225-121">maxWritePoolSize</span></span>|<span data-ttu-id="23225-122">Eine ganze Zahl, die bestimmt, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="23225-122">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="23225-123">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="23225-123">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="23225-124">Der Standard ist 16.</span><span class="sxs-lookup"><span data-stu-id="23225-124">The default is 16.</span></span>|  
|<span data-ttu-id="23225-125">messageVersion</span><span class="sxs-lookup"><span data-stu-id="23225-125">messageVersion</span></span>|<span data-ttu-id="23225-126">Gibt die SOAP-Version der Nachrichten an, die mithilfe der Bindung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="23225-126">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="23225-127">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="23225-127">Valid values are</span></span><br /><br /> <span data-ttu-id="23225-128">-Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="23225-128">-   Soap11Addressing1</span></span><br /><span data-ttu-id="23225-129">-Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="23225-129">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="23225-130">Der Standardwert ist Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="23225-130">The default is Soap12Addressing10.</span></span> <span data-ttu-id="23225-131">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="23225-131">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="23225-132">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="23225-132">writeEncoding</span></span>|<span data-ttu-id="23225-133">Gibt die Zeichensatzcodierung an, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="23225-133">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="23225-134">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="23225-134">Valid values are</span></span><br /><br /> <span data-ttu-id="23225-135">-UnicodeFffeTextEncoding: Unicode BigEndian-Codierung</span><span class="sxs-lookup"><span data-stu-id="23225-135">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="23225-136">-Utf16TextEncoding: Unicode-Codierung</span><span class="sxs-lookup"><span data-stu-id="23225-136">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="23225-137">-Utf8TextEncoding: 8-Bit-Codierung</span><span class="sxs-lookup"><span data-stu-id="23225-137">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="23225-138">Der Standardwert ist Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="23225-138">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="23225-139">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="23225-139">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="23225-140">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="23225-140">Child Elements</span></span>  
  
|<span data-ttu-id="23225-141">Element</span><span class="sxs-lookup"><span data-stu-id="23225-141">Element</span></span>|<span data-ttu-id="23225-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23225-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="23225-143">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="23225-143">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="23225-144">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="23225-144">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="23225-145">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="23225-145">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="23225-146">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="23225-146">Parent Elements</span></span>  
  
|<span data-ttu-id="23225-147">Element</span><span class="sxs-lookup"><span data-stu-id="23225-147">Element</span></span>|<span data-ttu-id="23225-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23225-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="23225-149">\<binding></span><span class="sxs-lookup"><span data-stu-id="23225-149">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="23225-150">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="23225-150">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23225-151">Hinweise</span><span class="sxs-lookup"><span data-stu-id="23225-151">Remarks</span></span>  
 <span data-ttu-id="23225-152">Beim Codieren wird eine Nachricht in eine Bytefolge transformiert.</span><span class="sxs-lookup"><span data-stu-id="23225-152">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="23225-153">Beim Decodieren wird dieser Prozess umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="23225-153">Decoding is the reverse process.</span></span> <span data-ttu-id="23225-154">Windows Communication Foundation (WCF) enthält drei Typen für die Codierung von SOAP-Nachrichten: Text, binär und Message Transmission Optimization Mechanism (MTOM).</span><span class="sxs-lookup"><span data-stu-id="23225-154">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="23225-155">Das `MtomMessageEncoding`-Element gibt die Zeichencodierung und die für Nachrichten mit MTOM-Verschlüsselung (Message Transmission Optimization Mechanism) verwendete Nachrichtenversion und andere Einstellungen an.</span><span class="sxs-lookup"><span data-stu-id="23225-155">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="23225-156">MTOM ist eine effiziente Technologie zum Übertragen von Binärdaten in WCF-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="23225-156">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="23225-157">Der MTOM-Encoder versucht, einen Ausgleich zwischen Effizienz und Interoperabilität zu schaffen.</span><span class="sxs-lookup"><span data-stu-id="23225-157">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="23225-158">Die MTOM-Verschlüsselung überträgt die meisten XML-Daten in Textform, optimiert aber große Binärdatenblöcke durch Übertragung ohne Konvertierung in ihr base64-verschlüsseltes Format.</span><span class="sxs-lookup"><span data-stu-id="23225-158">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23225-159">Beispiel</span><span class="sxs-lookup"><span data-stu-id="23225-159">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"  
    maxWritePoolSize="2132"  
    messageVersion="Soap11Addressing10"  
    textEncoding="utf-8" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="23225-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23225-160">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>  
 [<span data-ttu-id="23225-161">Nachrichtencodierung</span><span class="sxs-lookup"><span data-stu-id="23225-161">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="23225-162">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="23225-162">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="23225-163">Bindungen</span><span class="sxs-lookup"><span data-stu-id="23225-163">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="23225-164">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="23225-164">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="23225-165">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="23225-165">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="23225-166">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="23225-166">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
