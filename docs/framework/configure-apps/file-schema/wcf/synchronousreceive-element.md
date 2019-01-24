---
title: '&lt;synchronousReceive&gt;-Element'
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: dedbe156dea79c78f05acdb3a044c9080665675a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54598894"
---
# <a name="ltsynchronousreceivegt-element"></a><span data-ttu-id="f9a04-102">&lt;synchronousReceive&gt;-Element</span><span class="sxs-lookup"><span data-stu-id="f9a04-102">&lt;synchronousReceive&gt; element</span></span>
<span data-ttu-id="f9a04-103">Dieses Konfigurationselement wird zum Angeben des Laufzeitverhaltens für das Empfangen von Nachrichten in einem Dienst oder einer Clientanwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="f9a04-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="f9a04-104">Es enthält keine Attribute oder untergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="f9a04-104">It does not have any attributes or child elements.</span></span>  
  
 <span data-ttu-id="f9a04-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f9a04-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="f9a04-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="f9a04-106">\<behaviors></span></span>  
<span data-ttu-id="f9a04-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="f9a04-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="f9a04-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f9a04-108">\<behavior></span></span>  
<span data-ttu-id="f9a04-109">\<synchronousReceive></span><span class="sxs-lookup"><span data-stu-id="f9a04-109">\<synchronousReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9a04-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9a04-110">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9a04-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f9a04-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f9a04-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f9a04-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9a04-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="f9a04-113">Attributes</span></span>  
 <span data-ttu-id="f9a04-114">Keine</span><span class="sxs-lookup"><span data-stu-id="f9a04-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f9a04-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f9a04-115">Child Elements</span></span>  
 <span data-ttu-id="f9a04-116">Keine</span><span class="sxs-lookup"><span data-stu-id="f9a04-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f9a04-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f9a04-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f9a04-118">Element</span><span class="sxs-lookup"><span data-stu-id="f9a04-118">Element</span></span>|<span data-ttu-id="f9a04-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9a04-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9a04-120">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f9a04-120">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="f9a04-121">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="f9a04-121">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9a04-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f9a04-122">Remarks</span></span>  
 <span data-ttu-id="f9a04-123">Hiermit weisen Sie den Kanallistener an, anstatt der Standardeinstellung (asynchroner Empfang) einen synchronen Empfang zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f9a04-123">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="f9a04-124">Windows Communication Foundation (WCF) gibt einen neuen Thread zur Weiterleitung für jeden akzeptierten Kanal.</span><span class="sxs-lookup"><span data-stu-id="f9a04-124">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="f9a04-125">Bei einer großen Anzahl von Kanälen besteht die Gefahr, dass nicht genügend Threads verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f9a04-125">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9a04-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9a04-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
