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
ms.workload: dotnet
ms.openlocfilehash: 71fc89a4b9735c13429b31d8cd7c5995f641afa8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltcallbacktimeoutsgt"></a><span data-ttu-id="0072a-102">&lt;callbackTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="0072a-102">&lt;callbackTimeouts&gt;</span></span>
<span data-ttu-id="0072a-103">Gibt den Timeoutwert bei der Weitergabe von Transaktionen vom Server zum Client in einem Duplexrückrufvertragsszenario an.</span><span class="sxs-lookup"><span data-stu-id="0072a-103">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="0072a-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0072a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0072a-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="0072a-105">\<behaviors></span></span>  
<span data-ttu-id="0072a-106">\<EndpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="0072a-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="0072a-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="0072a-107">\<behavior></span></span>  
<span data-ttu-id="0072a-108">\<CallbackTimeOuts ></span><span class="sxs-lookup"><span data-stu-id="0072a-108">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0072a-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="0072a-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />  
```  
  
## <a name="type"></a><span data-ttu-id="0072a-110">Typ</span><span class="sxs-lookup"><span data-stu-id="0072a-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0072a-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0072a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0072a-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0072a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0072a-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="0072a-113">Attributes</span></span>  
  
|<span data-ttu-id="0072a-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="0072a-114">Attribute</span></span>|<span data-ttu-id="0072a-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0072a-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="0072a-116">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall angibt, in dem Transaktionen abgeschlossen oder automatisch beendet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="0072a-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="0072a-117">Die Standardeinstellung ist "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="0072a-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0072a-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0072a-118">Child Elements</span></span>  
 <span data-ttu-id="0072a-119">Keine</span><span class="sxs-lookup"><span data-stu-id="0072a-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0072a-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0072a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="0072a-121">Element</span><span class="sxs-lookup"><span data-stu-id="0072a-121">Element</span></span>|<span data-ttu-id="0072a-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0072a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0072a-123">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="0072a-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="0072a-124">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="0072a-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0072a-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0072a-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
