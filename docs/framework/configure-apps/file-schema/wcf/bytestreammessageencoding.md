---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: b11f472c0e33003e50be4b45bb49196c64ecb70d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919720"
---
# <a name="bytestreammessageencoding"></a><span data-ttu-id="df292-101">\<byteStreamMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="df292-101">\<byteStreamMessageEncoding></span></span>
<span data-ttu-id="df292-102">Gibt die Nachrichtencodierung als Datenstrom von Bytes an, mit der Option zur Angabe der Zeichencodierung.</span><span class="sxs-lookup"><span data-stu-id="df292-102">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="df292-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="df292-103">\<system.serviceModel></span></span>  
<span data-ttu-id="df292-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="df292-104">\<bindings></span></span>  
<span data-ttu-id="df292-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="df292-105">\<customBinding></span></span>  
<span data-ttu-id="df292-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="df292-106">\<binding></span></span>  
<span data-ttu-id="df292-107">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="df292-107">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df292-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="df292-108">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df292-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="df292-109">Attributes and Elements</span></span>  
 <span data-ttu-id="df292-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="df292-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df292-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="df292-111">Attributes</span></span>  
  
|<span data-ttu-id="df292-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="df292-112">Attribute</span></span>|<span data-ttu-id="df292-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="df292-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="df292-114">messageVersion</span><span class="sxs-lookup"><span data-stu-id="df292-114">messageVersion</span></span>|<span data-ttu-id="df292-115">Gibt die SOAP-Version der Nachrichten an, die mithilfe der Bindung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="df292-115">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="df292-116">Diese Eigenschaft kann nur auf den Nachrichtenversionswert von <xref:System.ServiceModel.Channels.MessageVersion.None%2A> festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="df292-116">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="df292-117">Der Bytedatenstromnachrichtenencoder unterstützt keine anderen Nachrichtenversionen.</span><span class="sxs-lookup"><span data-stu-id="df292-117">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="df292-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="df292-118">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="df292-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="df292-119">Child Elements</span></span>  
  
|<span data-ttu-id="df292-120">Element</span><span class="sxs-lookup"><span data-stu-id="df292-120">Element</span></span>|<span data-ttu-id="df292-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="df292-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="df292-122">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="df292-122">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="df292-123">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="df292-123">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="df292-124">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="df292-124">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="df292-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="df292-125">Parent Elements</span></span>  
  
|<span data-ttu-id="df292-126">Element</span><span class="sxs-lookup"><span data-stu-id="df292-126">Element</span></span>|<span data-ttu-id="df292-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="df292-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df292-128">\<binding></span><span class="sxs-lookup"><span data-stu-id="df292-128">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="df292-129">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="df292-129">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df292-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df292-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="df292-131">Nachrichtencodierung</span><span class="sxs-lookup"><span data-stu-id="df292-131">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="df292-132">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="df292-132">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="df292-133">Bindungen</span><span class="sxs-lookup"><span data-stu-id="df292-133">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="df292-134">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="df292-134">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="df292-135">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="df292-135">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="df292-136">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="df292-136">\<customBinding></span></span>](custombinding.md)
