---
title: '&lt;callbackTimeouts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5a030a615aae0159e1426bdf4c640ddfab7287dd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltcallbacktimeoutsgt"></a><span data-ttu-id="8b33d-102">&lt;callbackTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="8b33d-102">&lt;callbackTimeouts&gt;</span></span>
<span data-ttu-id="8b33d-103">Gibt den Timeoutwert bei der Weitergabe von Transaktionen vom Server zum Client in einem Duplexrückrufvertragsszenario an.</span><span class="sxs-lookup"><span data-stu-id="8b33d-103">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="8b33d-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8b33d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8b33d-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="8b33d-105">\<behaviors></span></span>  
<span data-ttu-id="8b33d-106">\<EndpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="8b33d-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="8b33d-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="8b33d-107">\<behavior></span></span>  
<span data-ttu-id="8b33d-108">\<CallbackTimeOuts ></span><span class="sxs-lookup"><span data-stu-id="8b33d-108">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b33d-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b33d-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />  
```  
  
## <a name="type"></a><span data-ttu-id="8b33d-110">Typ</span><span class="sxs-lookup"><span data-stu-id="8b33d-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8b33d-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8b33d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8b33d-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8b33d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8b33d-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="8b33d-113">Attributes</span></span>  
  
|<span data-ttu-id="8b33d-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="8b33d-114">Attribute</span></span>|<span data-ttu-id="8b33d-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8b33d-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="8b33d-116">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall angibt, in dem Transaktionen abgeschlossen oder automatisch beendet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="8b33d-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="8b33d-117">Die Standardeinstellung ist "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="8b33d-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8b33d-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8b33d-118">Child Elements</span></span>  
 <span data-ttu-id="8b33d-119">Keine</span><span class="sxs-lookup"><span data-stu-id="8b33d-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8b33d-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8b33d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8b33d-121">Element</span><span class="sxs-lookup"><span data-stu-id="8b33d-121">Element</span></span>|<span data-ttu-id="8b33d-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8b33d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b33d-123">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="8b33d-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="8b33d-124">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="8b33d-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8b33d-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b33d-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
