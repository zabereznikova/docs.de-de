---
title: <synchronousReceive>-Element
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: 20390f747c8beaccba1cfea7a9ea0ed366037ecb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166542"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="39716-102">\<SynchronousReceive >-Element</span><span class="sxs-lookup"><span data-stu-id="39716-102">\<synchronousReceive> element</span></span>
<span data-ttu-id="39716-103">Dieses Konfigurationselement wird zum Angeben des Laufzeitverhaltens für das Empfangen von Nachrichten in einem Dienst oder einer Clientanwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="39716-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="39716-104">Es enthält keine Attribute oder untergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="39716-104">It does not have any attributes or child elements.</span></span>  
  
 <span data-ttu-id="39716-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="39716-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="39716-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="39716-106">\<behaviors></span></span>  
<span data-ttu-id="39716-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="39716-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="39716-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="39716-108">\<behavior></span></span>  
<span data-ttu-id="39716-109">\<synchronousReceive></span><span class="sxs-lookup"><span data-stu-id="39716-109">\<synchronousReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39716-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="39716-110">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39716-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="39716-111">Attributes and Elements</span></span>  
 <span data-ttu-id="39716-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="39716-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39716-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="39716-113">Attributes</span></span>  
 <span data-ttu-id="39716-114">Keine</span><span class="sxs-lookup"><span data-stu-id="39716-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="39716-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="39716-115">Child Elements</span></span>  
 <span data-ttu-id="39716-116">Keine</span><span class="sxs-lookup"><span data-stu-id="39716-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="39716-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="39716-117">Parent Elements</span></span>  
  
|<span data-ttu-id="39716-118">Element</span><span class="sxs-lookup"><span data-stu-id="39716-118">Element</span></span>|<span data-ttu-id="39716-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39716-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39716-120">\<behavior></span><span class="sxs-lookup"><span data-stu-id="39716-120">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="39716-121">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="39716-121">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39716-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="39716-122">Remarks</span></span>  
 <span data-ttu-id="39716-123">Hiermit weisen Sie den Kanallistener an, anstatt der Standardeinstellung (asynchroner Empfang) einen synchronen Empfang zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="39716-123">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="39716-124">Windows Communication Foundation (WCF) gibt einen neuen Thread zur Weiterleitung für jeden akzeptierten Kanal.</span><span class="sxs-lookup"><span data-stu-id="39716-124">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="39716-125">Bei einer großen Anzahl von Kanälen besteht die Gefahr, dass nicht genügend Threads verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="39716-125">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39716-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39716-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
