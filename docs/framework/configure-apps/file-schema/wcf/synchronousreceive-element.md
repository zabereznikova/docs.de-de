---
title: <synchronousReceive>-Element
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: b3f4860be6b7edac776a1c30611271b2eb36968e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399495"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="3cf17-102">\<synchronousreceive-> Element</span><span class="sxs-lookup"><span data-stu-id="3cf17-102">\<synchronousReceive> element</span></span>
<span data-ttu-id="3cf17-103">Dieses Konfigurationselement wird zum Angeben des Laufzeitverhaltens für das Empfangen von Nachrichten in einem Dienst oder einer Clientanwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="3cf17-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="3cf17-104">Es enthält keine Attribute oder untergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="3cf17-104">It does not have any attributes or child elements.</span></span>  
  
<span data-ttu-id="3cf17-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3cf17-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3cf17-106">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3cf17-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3cf17-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3cf17-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="3cf17-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3cf17-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="3cf17-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3cf17-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="3cf17-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<synchronousreceive->**</span><span class="sxs-lookup"><span data-stu-id="3cf17-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<synchronousReceive>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cf17-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="3cf17-111">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cf17-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3cf17-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3cf17-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3cf17-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cf17-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="3cf17-114">Attributes</span></span>  
 <span data-ttu-id="3cf17-115">Keine</span><span class="sxs-lookup"><span data-stu-id="3cf17-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3cf17-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3cf17-116">Child Elements</span></span>  
 <span data-ttu-id="3cf17-117">Keine</span><span class="sxs-lookup"><span data-stu-id="3cf17-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3cf17-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3cf17-118">Parent Elements</span></span>  
  
|<span data-ttu-id="3cf17-119">Element</span><span class="sxs-lookup"><span data-stu-id="3cf17-119">Element</span></span>|<span data-ttu-id="3cf17-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3cf17-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3cf17-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="3cf17-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="3cf17-122">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="3cf17-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cf17-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3cf17-123">Remarks</span></span>  
 <span data-ttu-id="3cf17-124">Hiermit weisen Sie den Kanallistener an, anstatt der Standardeinstellung (asynchroner Empfang) einen synchronen Empfang zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3cf17-124">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="3cf17-125">Windows Communication Foundation (WCF) gibt für jeden akzeptierten Kanal einen neuen Thread für die Verschiebung aus.</span><span class="sxs-lookup"><span data-stu-id="3cf17-125">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="3cf17-126">Bei einer großen Anzahl von Kanälen besteht die Gefahr, dass nicht genügend Threads verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3cf17-126">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cf17-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3cf17-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
