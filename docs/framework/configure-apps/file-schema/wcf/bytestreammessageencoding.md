---
title: '&lt;byteStreamMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: 4b031bfb0d0979dc99df13c104a712d6dd771e8a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43422973"
---
# <a name="ltbytestreammessageencodinggt"></a><span data-ttu-id="61d22-102">&lt;byteStreamMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="61d22-102">&lt;byteStreamMessageEncoding&gt;</span></span>
<span data-ttu-id="61d22-103">Gibt die Nachrichtencodierung als Datenstrom von Bytes an, mit der Option zur Angabe der Zeichencodierung.</span><span class="sxs-lookup"><span data-stu-id="61d22-103">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="61d22-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="61d22-104">\<system.serviceModel></span></span>  
<span data-ttu-id="61d22-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="61d22-105">\<bindings></span></span>  
<span data-ttu-id="61d22-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="61d22-106">\<customBinding></span></span>  
<span data-ttu-id="61d22-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="61d22-107">\<binding></span></span>  
<span data-ttu-id="61d22-108">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="61d22-108">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61d22-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="61d22-109">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61d22-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="61d22-110">Attributes and Elements</span></span>  
 <span data-ttu-id="61d22-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="61d22-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61d22-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="61d22-112">Attributes</span></span>  
  
|<span data-ttu-id="61d22-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="61d22-113">Attribute</span></span>|<span data-ttu-id="61d22-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61d22-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="61d22-115">messageVersion</span><span class="sxs-lookup"><span data-stu-id="61d22-115">messageVersion</span></span>|<span data-ttu-id="61d22-116">Gibt die SOAP-Version der Nachrichten an, die mithilfe der Bindung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="61d22-116">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="61d22-117">Diese Eigenschaft kann nur auf den Nachrichtenversionswert von <xref:System.ServiceModel.Channels.MessageVersion.None%2A> festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="61d22-117">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="61d22-118">Der Bytedatenstromnachrichtenencoder unterstützt keine anderen Nachrichtenversionen.</span><span class="sxs-lookup"><span data-stu-id="61d22-118">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="61d22-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="61d22-119">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="61d22-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="61d22-120">Child Elements</span></span>  
  
|<span data-ttu-id="61d22-121">Element</span><span class="sxs-lookup"><span data-stu-id="61d22-121">Element</span></span>|<span data-ttu-id="61d22-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61d22-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61d22-123">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="61d22-123">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="61d22-124">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="61d22-124">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="61d22-125">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="61d22-125">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="61d22-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="61d22-126">Parent Elements</span></span>  
  
|<span data-ttu-id="61d22-127">Element</span><span class="sxs-lookup"><span data-stu-id="61d22-127">Element</span></span>|<span data-ttu-id="61d22-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61d22-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61d22-129">\<binding></span><span class="sxs-lookup"><span data-stu-id="61d22-129">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="61d22-130">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="61d22-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="61d22-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61d22-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>  
 [<span data-ttu-id="61d22-132">Nachrichtencodierung</span><span class="sxs-lookup"><span data-stu-id="61d22-132">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="61d22-133">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="61d22-133">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="61d22-134">Bindungen</span><span class="sxs-lookup"><span data-stu-id="61d22-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="61d22-135">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="61d22-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="61d22-136">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="61d22-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="61d22-137">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="61d22-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
