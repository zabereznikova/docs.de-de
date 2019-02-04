---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: c8dfd6824877d6f9e5b089a538cce35ffe51320b
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2019
ms.locfileid: "55674281"
---
# <a name="bytestreammessageencoding"></a><span data-ttu-id="b2152-101">\<byteStreamMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="b2152-101">\<byteStreamMessageEncoding></span></span>
<span data-ttu-id="b2152-102">Gibt die Nachrichtencodierung als Datenstrom von Bytes an, mit der Option zur Angabe der Zeichencodierung.</span><span class="sxs-lookup"><span data-stu-id="b2152-102">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="b2152-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b2152-103">\<system.serviceModel></span></span>  
<span data-ttu-id="b2152-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b2152-104">\<bindings></span></span>  
<span data-ttu-id="b2152-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b2152-105">\<customBinding></span></span>  
<span data-ttu-id="b2152-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="b2152-106">\<binding></span></span>  
<span data-ttu-id="b2152-107">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="b2152-107">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2152-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2152-108">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2152-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b2152-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b2152-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b2152-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2152-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="b2152-111">Attributes</span></span>  
  
|<span data-ttu-id="b2152-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="b2152-112">Attribute</span></span>|<span data-ttu-id="b2152-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2152-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b2152-114">messageVersion</span><span class="sxs-lookup"><span data-stu-id="b2152-114">messageVersion</span></span>|<span data-ttu-id="b2152-115">Gibt die SOAP-Version der Nachrichten an, die mithilfe der Bindung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="b2152-115">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="b2152-116">Diese Eigenschaft kann nur auf den Nachrichtenversionswert von <xref:System.ServiceModel.Channels.MessageVersion.None%2A> festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b2152-116">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="b2152-117">Der Bytedatenstromnachrichtenencoder unterstützt keine anderen Nachrichtenversionen.</span><span class="sxs-lookup"><span data-stu-id="b2152-117">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="b2152-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="b2152-118">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2152-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b2152-119">Child Elements</span></span>  
  
|<span data-ttu-id="b2152-120">Element</span><span class="sxs-lookup"><span data-stu-id="b2152-120">Element</span></span>|<span data-ttu-id="b2152-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2152-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b2152-122">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b2152-122">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="b2152-123">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="b2152-123">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="b2152-124">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="b2152-124">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b2152-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b2152-125">Parent Elements</span></span>  
  
|<span data-ttu-id="b2152-126">Element</span><span class="sxs-lookup"><span data-stu-id="b2152-126">Element</span></span>|<span data-ttu-id="b2152-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2152-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2152-128">\<binding></span><span class="sxs-lookup"><span data-stu-id="b2152-128">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="b2152-129">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="b2152-129">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b2152-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2152-130">See also</span></span>
- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="b2152-131">Nachrichtencodierung</span><span class="sxs-lookup"><span data-stu-id="b2152-131">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="b2152-132">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="b2152-132">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="b2152-133">Bindungen</span><span class="sxs-lookup"><span data-stu-id="b2152-133">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="b2152-134">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="b2152-134">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b2152-135">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="b2152-135">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="b2152-136">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b2152-136">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
