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
ms.openlocfilehash: 79d78517b62e4476106ff1ed7978c770a17caf2a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltsynchronousreceivegt-element"></a><span data-ttu-id="07719-102">&lt;synchronousReceive&gt;-Element</span><span class="sxs-lookup"><span data-stu-id="07719-102">&lt;synchronousReceive&gt; element</span></span>
<span data-ttu-id="07719-103">Dieses Konfigurationselement wird zum Angeben des Laufzeitverhaltens für das Empfangen von Nachrichten in einem Dienst oder einer Clientanwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="07719-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="07719-104">Es enthält keine Attribute oder untergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="07719-104">It does not have any attributes or child elements.</span></span>  
  
 <span data-ttu-id="07719-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="07719-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="07719-106">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="07719-106">\<behaviors></span></span>  
<span data-ttu-id="07719-107">\<EndpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="07719-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="07719-108">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="07719-108">\<behavior></span></span>  
<span data-ttu-id="07719-109">\<SynchronousReceive ></span><span class="sxs-lookup"><span data-stu-id="07719-109">\<synchronousReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07719-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="07719-110">Syntax</span></span>  
  
```xml  
<synchronousReceive />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07719-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="07719-111">Attributes and Elements</span></span>  
 <span data-ttu-id="07719-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="07719-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07719-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="07719-113">Attributes</span></span>  
 <span data-ttu-id="07719-114">Keine.</span><span class="sxs-lookup"><span data-stu-id="07719-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="07719-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="07719-115">Child Elements</span></span>  
 <span data-ttu-id="07719-116">Keine</span><span class="sxs-lookup"><span data-stu-id="07719-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="07719-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="07719-117">Parent Elements</span></span>  
  
|<span data-ttu-id="07719-118">Element</span><span class="sxs-lookup"><span data-stu-id="07719-118">Element</span></span>|<span data-ttu-id="07719-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07719-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07719-120">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="07719-120">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="07719-121">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="07719-121">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07719-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="07719-122">Remarks</span></span>  
 <span data-ttu-id="07719-123">Hiermit weisen Sie den Kanallistener an, anstatt der Standardeinstellung (asynchroner Empfang) einen synchronen Empfang zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="07719-123">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="07719-124"> gibt einen neuen Thread zur Weiterleitung für jeden akzeptierten Kanal aus.</span><span class="sxs-lookup"><span data-stu-id="07719-124"> issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="07719-125">Bei einer großen Anzahl von Kanälen besteht die Gefahr, dass nicht genügend Threads verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="07719-125">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07719-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07719-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>  
 <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
