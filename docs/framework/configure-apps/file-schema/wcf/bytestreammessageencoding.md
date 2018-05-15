---
title: '&lt;byteStreamMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: 3493588d4613131ad9526a8d26912ecdb601ea25
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltbytestreammessageencodinggt"></a><span data-ttu-id="f5048-102">&lt;byteStreamMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="f5048-102">&lt;byteStreamMessageEncoding&gt;</span></span>
<span data-ttu-id="f5048-103">Gibt die Nachrichtencodierung als Datenstrom von Bytes an, mit der Option zur Angabe der Zeichencodierung.</span><span class="sxs-lookup"><span data-stu-id="f5048-103">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="f5048-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f5048-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f5048-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="f5048-105">\<bindings></span></span>  
<span data-ttu-id="f5048-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f5048-106">\<customBinding></span></span>  
<span data-ttu-id="f5048-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="f5048-107">\<binding></span></span>  
<span data-ttu-id="f5048-108">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="f5048-108">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5048-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5048-109">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5048-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f5048-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f5048-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f5048-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5048-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="f5048-112">Attributes</span></span>  
  
|<span data-ttu-id="f5048-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="f5048-113">Attribute</span></span>|<span data-ttu-id="f5048-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f5048-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5048-115">messageVersion</span><span class="sxs-lookup"><span data-stu-id="f5048-115">messageVersion</span></span>|<span data-ttu-id="f5048-116">Gibt die SOAP-Version der Nachrichten an, die mithilfe der Bindung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="f5048-116">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="f5048-117">Diese Eigenschaft kann nur auf den Nachrichtenversionswert von <xref:System.ServiceModel.Channels.MessageVersion.None%2A> festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f5048-117">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="f5048-118">Der Bytedatenstromnachrichtenencoder unterstützt keine anderen Nachrichtenversionen.</span><span class="sxs-lookup"><span data-stu-id="f5048-118">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="f5048-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="f5048-119">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f5048-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f5048-120">Child Elements</span></span>  
  
|<span data-ttu-id="f5048-121">Element</span><span class="sxs-lookup"><span data-stu-id="f5048-121">Element</span></span>|<span data-ttu-id="f5048-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f5048-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5048-123">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="f5048-123">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="f5048-124">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="f5048-124">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="f5048-125">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="f5048-125">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f5048-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f5048-126">Parent Elements</span></span>  
  
|<span data-ttu-id="f5048-127">Element</span><span class="sxs-lookup"><span data-stu-id="f5048-127">Element</span></span>|<span data-ttu-id="f5048-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f5048-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5048-129">\<binding></span><span class="sxs-lookup"><span data-stu-id="f5048-129">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="f5048-130">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="f5048-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5048-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5048-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>  
 [<span data-ttu-id="f5048-132">Nachrichtencodierung</span><span class="sxs-lookup"><span data-stu-id="f5048-132">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="f5048-133">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="f5048-133">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="f5048-134">Bindungen</span><span class="sxs-lookup"><span data-stu-id="f5048-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="f5048-135">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="f5048-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="f5048-136">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="f5048-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="f5048-137">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f5048-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
