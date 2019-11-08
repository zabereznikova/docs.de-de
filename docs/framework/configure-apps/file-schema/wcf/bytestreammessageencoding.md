---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: 1d4109bde9c1668bc0832689b05e5d1dc3b198e9
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739064"
---
# <a name="bytestreammessageencoding"></a><span data-ttu-id="2ef0f-101">\<bytestreammessageencoding ></span><span class="sxs-lookup"><span data-stu-id="2ef0f-101">\<byteStreamMessageEncoding></span></span>
<span data-ttu-id="2ef0f-102">Gibt die Nachrichtencodierung als Datenstrom von Bytes an, mit der Option zur Angabe der Zeichencodierung.</span><span class="sxs-lookup"><span data-stu-id="2ef0f-102">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
<span data-ttu-id="2ef0f-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2ef0f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2ef0f-104">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="2ef0f-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2ef0f-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="2ef0f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="2ef0f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="2ef0f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="2ef0f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="2ef0f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="2ef0f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<bytestreammessageencoding >**</span><span class="sxs-lookup"><span data-stu-id="2ef0f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<byteStreamMessageEncoding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ef0f-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ef0f-109">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ef0f-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2ef0f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2ef0f-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2ef0f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ef0f-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="2ef0f-112">Attributes</span></span>  
  
|<span data-ttu-id="2ef0f-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="2ef0f-113">Attribute</span></span>|<span data-ttu-id="2ef0f-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ef0f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ef0f-115">messageVersion</span><span class="sxs-lookup"><span data-stu-id="2ef0f-115">messageVersion</span></span>|<span data-ttu-id="2ef0f-116">Gibt die SOAP-Version der Nachrichten an, die mithilfe der Bindung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="2ef0f-116">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="2ef0f-117">Diese Eigenschaft kann nur auf den Nachrichtenversionswert von <xref:System.ServiceModel.Channels.MessageVersion.None%2A> festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2ef0f-117">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="2ef0f-118">Der Bytedatenstromnachrichtenencoder unterstützt keine anderen Nachrichtenversionen.</span><span class="sxs-lookup"><span data-stu-id="2ef0f-118">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="2ef0f-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="2ef0f-119">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ef0f-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2ef0f-120">Child Elements</span></span>  
  
|<span data-ttu-id="2ef0f-121">Element</span><span class="sxs-lookup"><span data-stu-id="2ef0f-121">Element</span></span>|<span data-ttu-id="2ef0f-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ef0f-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2ef0f-123">[\<von Readerkontingenten >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2ef0f-123">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="2ef0f-124">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="2ef0f-124">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="2ef0f-125">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="2ef0f-125">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2ef0f-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2ef0f-126">Parent Elements</span></span>  
  
|<span data-ttu-id="2ef0f-127">Element</span><span class="sxs-lookup"><span data-stu-id="2ef0f-127">Element</span></span>|<span data-ttu-id="2ef0f-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ef0f-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ef0f-129">\<binding ></span><span class="sxs-lookup"><span data-stu-id="2ef0f-129">\<binding></span></span>](bindings.md)|<span data-ttu-id="2ef0f-130">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="2ef0f-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2ef0f-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ef0f-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="2ef0f-132">Nachrichtencodierung</span><span class="sxs-lookup"><span data-stu-id="2ef0f-132">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="2ef0f-133">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="2ef0f-133">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="2ef0f-134">Bindungen</span><span class="sxs-lookup"><span data-stu-id="2ef0f-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2ef0f-135">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="2ef0f-135">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="2ef0f-136">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="2ef0f-136">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="2ef0f-137">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="2ef0f-137">\<customBinding></span></span>](custombinding.md)
