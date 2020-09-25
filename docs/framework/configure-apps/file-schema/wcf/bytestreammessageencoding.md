---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: ceb40558cd979a54f72c2e9aa88f3af47bee9b68
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183896"
---
# \<byteStreamMessageEncoding>

<span data-ttu-id="b85f1-101">Gibt die Nachrichtencodierung als Datenstrom von Bytes an, mit der Option zur Angabe der Zeichencodierung.</span><span class="sxs-lookup"><span data-stu-id="b85f1-101">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<byteStreamMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="b85f1-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="b85f1-102">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b85f1-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b85f1-103">Attributes and Elements</span></span>  

 <span data-ttu-id="b85f1-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b85f1-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b85f1-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="b85f1-105">Attributes</span></span>  
  
|<span data-ttu-id="b85f1-106">attribute</span><span class="sxs-lookup"><span data-stu-id="b85f1-106">Attribute</span></span>|<span data-ttu-id="b85f1-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b85f1-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b85f1-108">messageVersion</span><span class="sxs-lookup"><span data-stu-id="b85f1-108">messageVersion</span></span>|<span data-ttu-id="b85f1-109">Gibt die SOAP-Version der Nachrichten an, die mithilfe der Bindung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="b85f1-109">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="b85f1-110">Diese Eigenschaft kann nur auf den Nachrichtenversionswert von <xref:System.ServiceModel.Channels.MessageVersion.None%2A> festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b85f1-110">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="b85f1-111">Der Bytedatenstromnachrichtenencoder unterstützt keine anderen Nachrichtenversionen.</span><span class="sxs-lookup"><span data-stu-id="b85f1-111">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="b85f1-112">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="b85f1-112">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b85f1-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b85f1-113">Child Elements</span></span>  
  
|<span data-ttu-id="b85f1-114">Element</span><span class="sxs-lookup"><span data-stu-id="b85f1-114">Element</span></span>|<span data-ttu-id="b85f1-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b85f1-115">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="b85f1-116">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="b85f1-116">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="b85f1-117">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="b85f1-117">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b85f1-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b85f1-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b85f1-119">Element</span><span class="sxs-lookup"><span data-stu-id="b85f1-119">Element</span></span>|<span data-ttu-id="b85f1-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b85f1-120">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="b85f1-121">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="b85f1-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b85f1-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b85f1-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="b85f1-123">Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="b85f1-123">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="b85f1-124">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="b85f1-124">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="b85f1-125">Bindungen</span><span class="sxs-lookup"><span data-stu-id="b85f1-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b85f1-126">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="b85f1-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b85f1-127">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="b85f1-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
