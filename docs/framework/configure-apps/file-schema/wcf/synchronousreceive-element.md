---
title: '&lt;synchronousReceive&gt;-Element'
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: af1ca2ee1fe3c03c33f05e0c30c7b843b3720a36
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753260"
---
# <a name="ltsynchronousreceivegt-element"></a><span data-ttu-id="62000-102">&lt;synchronousReceive&gt;-Element</span><span class="sxs-lookup"><span data-stu-id="62000-102">&lt;synchronousReceive&gt; element</span></span>
<span data-ttu-id="62000-103">Dieses Konfigurationselement wird zum Angeben des Laufzeitverhaltens für das Empfangen von Nachrichten in einem Dienst oder einer Clientanwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="62000-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="62000-104">Es enthält keine Attribute oder untergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="62000-104">It does not have any attributes or child elements.</span></span>  
  
 <span data-ttu-id="62000-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="62000-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="62000-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="62000-106">\<behaviors></span></span>  
<span data-ttu-id="62000-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="62000-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="62000-108">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="62000-108">\<behavior></span></span>  
<span data-ttu-id="62000-109">\<SynchronousReceive ></span><span class="sxs-lookup"><span data-stu-id="62000-109">\<synchronousReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62000-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="62000-110">Syntax</span></span>  
  
```xml  
<synchronousReceive />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62000-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="62000-111">Attributes and Elements</span></span>  
 <span data-ttu-id="62000-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="62000-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62000-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="62000-113">Attributes</span></span>  
 <span data-ttu-id="62000-114">Keine</span><span class="sxs-lookup"><span data-stu-id="62000-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="62000-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="62000-115">Child Elements</span></span>  
 <span data-ttu-id="62000-116">Keine</span><span class="sxs-lookup"><span data-stu-id="62000-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="62000-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="62000-117">Parent Elements</span></span>  
  
|<span data-ttu-id="62000-118">Element</span><span class="sxs-lookup"><span data-stu-id="62000-118">Element</span></span>|<span data-ttu-id="62000-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62000-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62000-120">\<behavior></span><span class="sxs-lookup"><span data-stu-id="62000-120">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="62000-121">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="62000-121">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62000-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="62000-122">Remarks</span></span>  
 <span data-ttu-id="62000-123">Hiermit weisen Sie den Kanallistener an, anstatt der Standardeinstellung (asynchroner Empfang) einen synchronen Empfang zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="62000-123">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="62000-124">Windows Communication Foundation (WCF) gibt einen neuen Thread zur Weiterleitung für jeden akzeptierten Kanal.</span><span class="sxs-lookup"><span data-stu-id="62000-124">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="62000-125">Bei einer großen Anzahl von Kanälen besteht die Gefahr, dass nicht genügend Threads verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="62000-125">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62000-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62000-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>  
 <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
