---
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: 4179d7ac1919610b0be131b079b28da0cd9cad75
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540294"
---
# \<binaryMessageEncoding>
<span data-ttu-id="22562-101">Definiert einen Binärnachrichtenencoder, der die Windows Communication Foundation (WCF)-Nachrichten bei der Übertragung im Binärformat verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="22562-101">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binaryMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="22562-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="22562-102">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22562-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="22562-103">Attributes and Elements</span></span>  
 <span data-ttu-id="22562-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="22562-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22562-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="22562-105">Attributes</span></span>  
  
|<span data-ttu-id="22562-106">attribute</span><span class="sxs-lookup"><span data-stu-id="22562-106">Attribute</span></span>|<span data-ttu-id="22562-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="22562-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="22562-108">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="22562-108">maxReadPoolSize</span></span>|<span data-ttu-id="22562-109">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="22562-109">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="22562-110">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="22562-110">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="22562-111">Der Standardwert ist 64.</span><span class="sxs-lookup"><span data-stu-id="22562-111">The default is 64.</span></span>|  
|<span data-ttu-id="22562-112">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="22562-112">maxSessionSize</span></span>|<span data-ttu-id="22562-113">Eine positive ganze Zahl, die die Größe des Puffers in Bytes festlegt, der zum Verschlüsseln von Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="22562-113">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="22562-114">Eine größerer Puffer erhöht die Codierungsgeschwindigkeit auf Kosten der Größe des Workingsets.</span><span class="sxs-lookup"><span data-stu-id="22562-114">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="22562-115">Der Standard ist 2048.</span><span class="sxs-lookup"><span data-stu-id="22562-115">The default is 2048.</span></span>|  
|<span data-ttu-id="22562-116">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="22562-116">maxWritePoolSize</span></span>|<span data-ttu-id="22562-117">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="22562-117">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="22562-118">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="22562-118">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="22562-119">Der Standardwert ist 16.</span><span class="sxs-lookup"><span data-stu-id="22562-119">The default is 16.</span></span>|  
|<span data-ttu-id="22562-120">messageVersion</span><span class="sxs-lookup"><span data-stu-id="22562-120">messageVersion</span></span>|<span data-ttu-id="22562-121">Gibt die Versionen der SOAP-Nachricht und WS-Adressierung an, die verwendet oder erwartet werden.</span><span class="sxs-lookup"><span data-stu-id="22562-121">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22562-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="22562-122">Child Elements</span></span>  
  
|<span data-ttu-id="22562-123">Element</span><span class="sxs-lookup"><span data-stu-id="22562-123">Element</span></span>|<span data-ttu-id="22562-124">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="22562-124">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="22562-125">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="22562-125">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="22562-126">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="22562-126">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="22562-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="22562-127">Parent Elements</span></span>  
  
|<span data-ttu-id="22562-128">Element</span><span class="sxs-lookup"><span data-stu-id="22562-128">Element</span></span>|<span data-ttu-id="22562-129">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="22562-129">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="22562-130">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="22562-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22562-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="22562-131">Remarks</span></span>  
 <span data-ttu-id="22562-132">Beim Codieren wird eine Nachricht in eine Bytefolge transformiert.</span><span class="sxs-lookup"><span data-stu-id="22562-132">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="22562-133">Beim Decodieren wird dieser Prozess umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="22562-133">Decoding is the reverse process.</span></span> <span data-ttu-id="22562-134">Windows Communication Foundation (WCF) enthält drei Typen für die Codierung von SOAP-Nachrichten: Text, binär und Message Transmission Optimization Mechanism (MTOM).</span><span class="sxs-lookup"><span data-stu-id="22562-134">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="22562-135">Das `binaryMessageEncoding`-Element gibt das .NET Binary-Format für XML an und bietet Optionen zum Festlegen der Zeichencodierung und der zu verwendenden SOAP- und WS-Adressierungsversion.</span><span class="sxs-lookup"><span data-stu-id="22562-135">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="22562-136">Der Binärnachrichtenencoder verschlüsselt die Windows Communication Foundation (WCF)-Nachrichten bei der Übertragung im Binärformat.</span><span class="sxs-lookup"><span data-stu-id="22562-136">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="22562-137">Diese Verschlüsselung resultiert zwar in einer schnellen Nachrichtenübertragung, die auf den WS-\*-Standards basierende Interoperabilität geht aber verloren.</span><span class="sxs-lookup"><span data-stu-id="22562-137">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22562-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="22562-138">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="22562-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22562-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [<span data-ttu-id="22562-140">Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="22562-140">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="22562-141">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="22562-141">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="22562-142">Bindungen</span><span class="sxs-lookup"><span data-stu-id="22562-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="22562-143">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="22562-143">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="22562-144">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="22562-144">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
