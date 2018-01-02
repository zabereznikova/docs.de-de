---
title: '&lt;synchronousReceive&gt;-Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 63923121ae96b85bd192899a8d8ad285a3ad5b2d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltsynchronousreceivegt-element"></a><span data-ttu-id="76846-102">&lt;synchronousReceive&gt;-Element</span><span class="sxs-lookup"><span data-stu-id="76846-102">&lt;synchronousReceive&gt; element</span></span>
<span data-ttu-id="76846-103">Dieses Konfigurationselement wird zum Angeben des Laufzeitverhaltens für das Empfangen von Nachrichten in einem Dienst oder einer Clientanwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="76846-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="76846-104">Es enthält keine Attribute oder untergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="76846-104">It does not have any attributes or child elements.</span></span>  
  
 <span data-ttu-id="76846-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="76846-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="76846-106">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="76846-106">\<behaviors></span></span>  
<span data-ttu-id="76846-107">\<EndpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="76846-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="76846-108">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="76846-108">\<behavior></span></span>  
<span data-ttu-id="76846-109">\<SynchronousReceive ></span><span class="sxs-lookup"><span data-stu-id="76846-109">\<synchronousReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76846-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="76846-110">Syntax</span></span>  
  
```xml  
<synchronousReceive />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76846-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="76846-111">Attributes and Elements</span></span>  
 <span data-ttu-id="76846-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="76846-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76846-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="76846-113">Attributes</span></span>  
 <span data-ttu-id="76846-114">Keine</span><span class="sxs-lookup"><span data-stu-id="76846-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="76846-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="76846-115">Child Elements</span></span>  
 <span data-ttu-id="76846-116">Keine</span><span class="sxs-lookup"><span data-stu-id="76846-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="76846-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="76846-117">Parent Elements</span></span>  
  
|<span data-ttu-id="76846-118">Element</span><span class="sxs-lookup"><span data-stu-id="76846-118">Element</span></span>|<span data-ttu-id="76846-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="76846-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="76846-120">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="76846-120">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="76846-121">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="76846-121">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76846-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="76846-122">Remarks</span></span>  
 <span data-ttu-id="76846-123">Hiermit weisen Sie den Kanallistener an, anstatt der Standardeinstellung (asynchroner Empfang) einen synchronen Empfang zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="76846-123">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="76846-124"> gibt einen neuen Thread zur Weiterleitung für jeden akzeptierten Kanal aus.</span><span class="sxs-lookup"><span data-stu-id="76846-124"> issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="76846-125">Bei einer großen Anzahl von Kanälen besteht die Gefahr, dass nicht genügend Threads verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="76846-125">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76846-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="76846-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>  
 <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
