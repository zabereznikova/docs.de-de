---
title: '&lt;byteStreamMessageEncoding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1996a33666ac6b92f1b7bca8c2e2e0ef51456dea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltbytestreammessageencodinggt"></a><span data-ttu-id="d22c5-102">&lt;byteStreamMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="d22c5-102">&lt;byteStreamMessageEncoding&gt;</span></span>
<span data-ttu-id="d22c5-103">Gibt die Nachrichtencodierung als Datenstrom von Bytes an, mit der Option zur Angabe der Zeichencodierung.</span><span class="sxs-lookup"><span data-stu-id="d22c5-103">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="d22c5-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="d22c5-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d22c5-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="d22c5-105">\<bindings></span></span>  
<span data-ttu-id="d22c5-106">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="d22c5-106">\<customBinding></span></span>  
<span data-ttu-id="d22c5-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="d22c5-107">\<binding></span></span>  
<span data-ttu-id="d22c5-108">\<BinaryMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="d22c5-108">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d22c5-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="d22c5-109">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d22c5-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d22c5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d22c5-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d22c5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d22c5-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="d22c5-112">Attributes</span></span>  
  
|<span data-ttu-id="d22c5-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="d22c5-113">Attribute</span></span>|<span data-ttu-id="d22c5-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d22c5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d22c5-115">messageVersion</span><span class="sxs-lookup"><span data-stu-id="d22c5-115">messageVersion</span></span>|<span data-ttu-id="d22c5-116">Gibt die SOAP-Version der Nachrichten an, die mithilfe der Bindung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="d22c5-116">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="d22c5-117">Diese Eigenschaft kann nur auf den Nachrichtenversionswert von <xref:System.ServiceModel.Channels.MessageVersion.None%2A> festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="d22c5-117">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="d22c5-118">Der Bytedatenstromnachrichtenencoder unterstützt keine anderen Nachrichtenversionen.</span><span class="sxs-lookup"><span data-stu-id="d22c5-118">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="d22c5-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="d22c5-119">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d22c5-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d22c5-120">Child Elements</span></span>  
  
|<span data-ttu-id="d22c5-121">Element</span><span class="sxs-lookup"><span data-stu-id="d22c5-121">Element</span></span>|<span data-ttu-id="d22c5-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d22c5-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d22c5-123">\<ReaderQuotas ></span><span class="sxs-lookup"><span data-stu-id="d22c5-123">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="d22c5-124">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="d22c5-124">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="d22c5-125">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="d22c5-125">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d22c5-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d22c5-126">Parent Elements</span></span>  
  
|<span data-ttu-id="d22c5-127">Element</span><span class="sxs-lookup"><span data-stu-id="d22c5-127">Element</span></span>|<span data-ttu-id="d22c5-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d22c5-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d22c5-129">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="d22c5-129">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="d22c5-130">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="d22c5-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d22c5-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d22c5-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>  
 [<span data-ttu-id="d22c5-132">Nachrichtencodierung</span><span class="sxs-lookup"><span data-stu-id="d22c5-132">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="d22c5-133">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="d22c5-133">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="d22c5-134">Bindungen</span><span class="sxs-lookup"><span data-stu-id="d22c5-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="d22c5-135">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="d22c5-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="d22c5-136">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="d22c5-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="d22c5-137">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="d22c5-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
