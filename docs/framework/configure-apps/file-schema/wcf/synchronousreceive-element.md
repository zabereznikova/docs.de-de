---
title: <synchronousReceive>-Element
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: 20390f747c8beaccba1cfea7a9ea0ed366037ecb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757923"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="c3ffd-102">\<SynchronousReceive >-Element</span><span class="sxs-lookup"><span data-stu-id="c3ffd-102">\<synchronousReceive> element</span></span>
<span data-ttu-id="c3ffd-103">Dieses Konfigurationselement wird zum Angeben des Laufzeitverhaltens für das Empfangen von Nachrichten in einem Dienst oder einer Clientanwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="c3ffd-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="c3ffd-104">Es enthält keine Attribute oder untergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="c3ffd-104">It does not have any attributes or child elements.</span></span>  
  
 <span data-ttu-id="c3ffd-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c3ffd-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="c3ffd-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="c3ffd-106">\<behaviors></span></span>  
<span data-ttu-id="c3ffd-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="c3ffd-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="c3ffd-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c3ffd-108">\<behavior></span></span>  
<span data-ttu-id="c3ffd-109">\<synchronousReceive></span><span class="sxs-lookup"><span data-stu-id="c3ffd-109">\<synchronousReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3ffd-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="c3ffd-110">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3ffd-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c3ffd-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c3ffd-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c3ffd-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3ffd-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="c3ffd-113">Attributes</span></span>  
 <span data-ttu-id="c3ffd-114">Keine</span><span class="sxs-lookup"><span data-stu-id="c3ffd-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c3ffd-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c3ffd-115">Child Elements</span></span>  
 <span data-ttu-id="c3ffd-116">Keine</span><span class="sxs-lookup"><span data-stu-id="c3ffd-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c3ffd-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c3ffd-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c3ffd-118">Element</span><span class="sxs-lookup"><span data-stu-id="c3ffd-118">Element</span></span>|<span data-ttu-id="c3ffd-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3ffd-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c3ffd-120">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c3ffd-120">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="c3ffd-121">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="c3ffd-121">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3ffd-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c3ffd-122">Remarks</span></span>  
 <span data-ttu-id="c3ffd-123">Hiermit weisen Sie den Kanallistener an, anstatt der Standardeinstellung (asynchroner Empfang) einen synchronen Empfang zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c3ffd-123">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="c3ffd-124">Windows Communication Foundation (WCF) gibt einen neuen Thread zur Weiterleitung für jeden akzeptierten Kanal.</span><span class="sxs-lookup"><span data-stu-id="c3ffd-124">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="c3ffd-125">Bei einer großen Anzahl von Kanälen besteht die Gefahr, dass nicht genügend Threads verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c3ffd-125">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3ffd-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3ffd-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
