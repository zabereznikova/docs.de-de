---
title: '&lt;callbackTimeouts&gt;'
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: 85e7b1f0d009e27cbacd9f69b381e4f05984bf56
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149110"
---
# <a name="ltcallbacktimeoutsgt"></a><span data-ttu-id="56738-102">&lt;callbackTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="56738-102">&lt;callbackTimeouts&gt;</span></span>
<span data-ttu-id="56738-103">Gibt den Timeoutwert bei der Weitergabe von Transaktionen vom Server zum Client in einem Duplexrückrufvertragsszenario an.</span><span class="sxs-lookup"><span data-stu-id="56738-103">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="56738-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="56738-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="56738-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="56738-105">\<behaviors></span></span>  
<span data-ttu-id="56738-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="56738-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="56738-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="56738-107">\<behavior></span></span>  
<span data-ttu-id="56738-108">\<CallbackTimeOuts ></span><span class="sxs-lookup"><span data-stu-id="56738-108">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56738-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="56738-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="56738-110">Typ</span><span class="sxs-lookup"><span data-stu-id="56738-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56738-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="56738-111">Attributes and Elements</span></span>  
 <span data-ttu-id="56738-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="56738-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56738-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="56738-113">Attributes</span></span>  
  
|<span data-ttu-id="56738-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="56738-114">Attribute</span></span>|<span data-ttu-id="56738-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56738-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="56738-116">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall angibt, in dem Transaktionen abgeschlossen oder automatisch beendet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="56738-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="56738-117">Der Standardwert ist "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="56738-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56738-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="56738-118">Child Elements</span></span>  
 <span data-ttu-id="56738-119">Keine</span><span class="sxs-lookup"><span data-stu-id="56738-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56738-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="56738-120">Parent Elements</span></span>  
  
|<span data-ttu-id="56738-121">Element</span><span class="sxs-lookup"><span data-stu-id="56738-121">Element</span></span>|<span data-ttu-id="56738-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56738-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56738-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="56738-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="56738-124">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="56738-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="56738-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56738-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
