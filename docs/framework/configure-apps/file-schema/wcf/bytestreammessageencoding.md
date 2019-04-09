---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: ce9f282ea1101befe3bf99762efa61e9b47b74cf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109901"
---
# <a name="bytestreammessageencoding"></a><span data-ttu-id="d8960-101">\<byteStreamMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="d8960-101">\<byteStreamMessageEncoding></span></span>
<span data-ttu-id="d8960-102">Gibt die Nachrichtencodierung als Datenstrom von Bytes an, mit der Option zur Angabe der Zeichencodierung.</span><span class="sxs-lookup"><span data-stu-id="d8960-102">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="d8960-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d8960-103">\<system.serviceModel></span></span>  
<span data-ttu-id="d8960-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d8960-104">\<bindings></span></span>  
<span data-ttu-id="d8960-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d8960-105">\<customBinding></span></span>  
<span data-ttu-id="d8960-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="d8960-106">\<binding></span></span>  
<span data-ttu-id="d8960-107">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="d8960-107">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8960-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="d8960-108">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8960-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d8960-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d8960-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d8960-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8960-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="d8960-111">Attributes</span></span>  
  
|<span data-ttu-id="d8960-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="d8960-112">Attribute</span></span>|<span data-ttu-id="d8960-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d8960-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d8960-114">messageVersion</span><span class="sxs-lookup"><span data-stu-id="d8960-114">messageVersion</span></span>|<span data-ttu-id="d8960-115">Gibt die SOAP-Version der Nachrichten an, die mithilfe der Bindung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="d8960-115">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="d8960-116">Diese Eigenschaft kann nur auf den Nachrichtenversionswert von <xref:System.ServiceModel.Channels.MessageVersion.None%2A> festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="d8960-116">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="d8960-117">Der Bytedatenstromnachrichtenencoder unterstützt keine anderen Nachrichtenversionen.</span><span class="sxs-lookup"><span data-stu-id="d8960-117">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="d8960-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="d8960-118">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d8960-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d8960-119">Child Elements</span></span>  
  
|<span data-ttu-id="d8960-120">Element</span><span class="sxs-lookup"><span data-stu-id="d8960-120">Element</span></span>|<span data-ttu-id="d8960-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d8960-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8960-122">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="d8960-122">\<readerQuotas></span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="d8960-123">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="d8960-123">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="d8960-124">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="d8960-124">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d8960-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d8960-125">Parent Elements</span></span>  
  
|<span data-ttu-id="d8960-126">Element</span><span class="sxs-lookup"><span data-stu-id="d8960-126">Element</span></span>|<span data-ttu-id="d8960-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d8960-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8960-128">\<binding></span><span class="sxs-lookup"><span data-stu-id="d8960-128">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="d8960-129">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="d8960-129">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8960-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8960-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="d8960-131">Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="d8960-131">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="d8960-132">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="d8960-132">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="d8960-133">Bindungen</span><span class="sxs-lookup"><span data-stu-id="d8960-133">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="d8960-134">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="d8960-134">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d8960-135">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="d8960-135">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="d8960-136">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d8960-136">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
