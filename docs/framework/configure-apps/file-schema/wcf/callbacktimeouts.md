---
title: '&lt;callbackTimeouts&gt;'
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: 48da0351d162a2143a26cc5b9eaa05b731358639
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749565"
---
# <a name="ltcallbacktimeoutsgt"></a><span data-ttu-id="62385-102">&lt;callbackTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="62385-102">&lt;callbackTimeouts&gt;</span></span>
<span data-ttu-id="62385-103">Gibt den Timeoutwert bei der Weitergabe von Transaktionen vom Server zum Client in einem Duplexrückrufvertragsszenario an.</span><span class="sxs-lookup"><span data-stu-id="62385-103">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="62385-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="62385-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="62385-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="62385-105">\<behaviors></span></span>  
<span data-ttu-id="62385-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="62385-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="62385-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="62385-107">\<behavior></span></span>  
<span data-ttu-id="62385-108">\<CallbackTimeOuts ></span><span class="sxs-lookup"><span data-stu-id="62385-108">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62385-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="62385-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />  
```  
  
## <a name="type"></a><span data-ttu-id="62385-110">Typ</span><span class="sxs-lookup"><span data-stu-id="62385-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62385-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="62385-111">Attributes and Elements</span></span>  
 <span data-ttu-id="62385-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="62385-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62385-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="62385-113">Attributes</span></span>  
  
|<span data-ttu-id="62385-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="62385-114">Attribute</span></span>|<span data-ttu-id="62385-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62385-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="62385-116">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall angibt, in dem Transaktionen abgeschlossen oder automatisch beendet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="62385-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="62385-117">Die Standardeinstellung ist "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="62385-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62385-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="62385-118">Child Elements</span></span>  
 <span data-ttu-id="62385-119">Keine</span><span class="sxs-lookup"><span data-stu-id="62385-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="62385-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="62385-120">Parent Elements</span></span>  
  
|<span data-ttu-id="62385-121">Element</span><span class="sxs-lookup"><span data-stu-id="62385-121">Element</span></span>|<span data-ttu-id="62385-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62385-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62385-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="62385-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="62385-124">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="62385-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62385-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62385-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
