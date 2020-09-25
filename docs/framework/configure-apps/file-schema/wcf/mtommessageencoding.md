---
title: <mtomMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: 76b83381849b8519c1b758ef52c6d5c3f682f9b7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204631"
---
# \<mtomMessageEncoding>

<span data-ttu-id="e9a51-101">Gibt die Codierungs- und Nachrichtenversionierung an, die für SOAP MTOM-basierte (Message Transmission Optimization Mechanism) Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e9a51-101">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mtomMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="e9a51-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9a51-102">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding maxBufferSize="Integer"
                     maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing1/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9a51-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e9a51-103">Attributes and Elements</span></span>  

 <span data-ttu-id="e9a51-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e9a51-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9a51-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="e9a51-105">Attributes</span></span>  
  
|<span data-ttu-id="e9a51-106">attribute</span><span class="sxs-lookup"><span data-stu-id="e9a51-106">Attribute</span></span>|<span data-ttu-id="e9a51-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9a51-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e9a51-108">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="e9a51-108">maxBufferSize</span></span>|<span data-ttu-id="e9a51-109">Eine ganze Zahl, die die maximale Größe des Puffers angibt.</span><span class="sxs-lookup"><span data-stu-id="e9a51-109">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="e9a51-110">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="e9a51-110">maxReadPoolSize</span></span>|<span data-ttu-id="e9a51-111">Eine ganze Zahl, die bestimmt, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="e9a51-111">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="e9a51-112">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="e9a51-112">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="e9a51-113">Der Standardwert ist 64.</span><span class="sxs-lookup"><span data-stu-id="e9a51-113">The default is 64.</span></span>|  
|<span data-ttu-id="e9a51-114">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="e9a51-114">maxWritePoolSize</span></span>|<span data-ttu-id="e9a51-115">Eine ganze Zahl, die bestimmt, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="e9a51-115">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="e9a51-116">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="e9a51-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="e9a51-117">Der Standardwert ist 16.</span><span class="sxs-lookup"><span data-stu-id="e9a51-117">The default is 16.</span></span>|  
|<span data-ttu-id="e9a51-118">messageVersion</span><span class="sxs-lookup"><span data-stu-id="e9a51-118">messageVersion</span></span>|<span data-ttu-id="e9a51-119">Gibt die SOAP-Version der Nachrichten an, die mithilfe der Bindung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="e9a51-119">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="e9a51-120">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="e9a51-120">Valid values are</span></span><br /><br /> <span data-ttu-id="e9a51-121">- Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="e9a51-121">-   Soap11Addressing1</span></span><br /><span data-ttu-id="e9a51-122">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="e9a51-122">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="e9a51-123">Der Standardwert ist Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="e9a51-123">The default is Soap12Addressing10.</span></span> <span data-ttu-id="e9a51-124">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="e9a51-124">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="e9a51-125">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="e9a51-125">writeEncoding</span></span>|<span data-ttu-id="e9a51-126">Gibt die Zeichensatzcodierung an, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e9a51-126">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="e9a51-127">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="e9a51-127">Valid values are</span></span><br /><br /> <span data-ttu-id="e9a51-128">-UnicodeFffeTextEncoding: Unicode bigEndian-Codierung</span><span class="sxs-lookup"><span data-stu-id="e9a51-128">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="e9a51-129">-Utf16TextEncoding: Unicode-Codierung</span><span class="sxs-lookup"><span data-stu-id="e9a51-129">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="e9a51-130">-Utf8TextEncoding: 8-Bit-Codierung</span><span class="sxs-lookup"><span data-stu-id="e9a51-130">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="e9a51-131">Der Standardwert ist Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="e9a51-131">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="e9a51-132">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="e9a51-132">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9a51-133">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e9a51-133">Child Elements</span></span>  
  
|<span data-ttu-id="e9a51-134">Element</span><span class="sxs-lookup"><span data-stu-id="e9a51-134">Element</span></span>|<span data-ttu-id="e9a51-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9a51-135">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="e9a51-136">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="e9a51-136">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="e9a51-137">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="e9a51-137">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e9a51-138">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e9a51-138">Parent Elements</span></span>  
  
|<span data-ttu-id="e9a51-139">Element</span><span class="sxs-lookup"><span data-stu-id="e9a51-139">Element</span></span>|<span data-ttu-id="e9a51-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9a51-140">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="e9a51-141">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="e9a51-141">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9a51-142">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e9a51-142">Remarks</span></span>  

 <span data-ttu-id="e9a51-143">Beim Codieren wird eine Nachricht in eine Bytefolge transformiert.</span><span class="sxs-lookup"><span data-stu-id="e9a51-143">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="e9a51-144">Beim Decodieren wird dieser Prozess umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="e9a51-144">Decoding is the reverse process.</span></span> <span data-ttu-id="e9a51-145">Windows Communication Foundation (WCF) enthält drei Typen für die Codierung von SOAP-Nachrichten: Text, binär und Message Transmission Optimization Mechanism (MTOM).</span><span class="sxs-lookup"><span data-stu-id="e9a51-145">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="e9a51-146">Das `MtomMessageEncoding`-Element gibt die Zeichencodierung und die für Nachrichten mit MTOM-Verschlüsselung (Message Transmission Optimization Mechanism) verwendete Nachrichtenversion und andere Einstellungen an.</span><span class="sxs-lookup"><span data-stu-id="e9a51-146">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="e9a51-147">MTOM ist eine effiziente Technologie zum Übertragen von Binärdaten in WCF-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="e9a51-147">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="e9a51-148">Der MTOM-Encoder versucht, einen Ausgleich zwischen Effizienz und Interoperabilität zu schaffen.</span><span class="sxs-lookup"><span data-stu-id="e9a51-148">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="e9a51-149">Die MTOM-Verschlüsselung überträgt die meisten XML-Daten in Textform, optimiert aber große Binärdatenblöcke durch Übertragung ohne Konvertierung in ihr base64-verschlüsseltes Format.</span><span class="sxs-lookup"><span data-stu-id="e9a51-149">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9a51-150">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e9a51-150">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap11Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="e9a51-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e9a51-151">See also</span></span>

- <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
- [<span data-ttu-id="e9a51-152">Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="e9a51-152">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="e9a51-153">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="e9a51-153">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="e9a51-154">Bindungen</span><span class="sxs-lookup"><span data-stu-id="e9a51-154">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e9a51-155">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="e9a51-155">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e9a51-156">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="e9a51-156">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
