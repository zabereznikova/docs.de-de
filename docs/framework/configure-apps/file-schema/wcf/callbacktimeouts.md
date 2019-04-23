---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: e666bac0be772e417f140e1482649f82ea70e2f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173640"
---
# <a name="callbacktimeouts"></a><span data-ttu-id="a20d1-101">\<callbackTimeouts></span><span class="sxs-lookup"><span data-stu-id="a20d1-101">\<callbackTimeouts></span></span>
<span data-ttu-id="a20d1-102">Gibt den Timeoutwert bei der Weitergabe von Transaktionen vom Server zum Client in einem Duplexrückrufvertragsszenario an.</span><span class="sxs-lookup"><span data-stu-id="a20d1-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="a20d1-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a20d1-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="a20d1-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="a20d1-104">\<behaviors></span></span>  
<span data-ttu-id="a20d1-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="a20d1-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="a20d1-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a20d1-106">\<behavior></span></span>  
<span data-ttu-id="a20d1-107">\<callbackTimeOuts></span><span class="sxs-lookup"><span data-stu-id="a20d1-107">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a20d1-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="a20d1-108">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="a20d1-109">Typ</span><span class="sxs-lookup"><span data-stu-id="a20d1-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a20d1-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a20d1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a20d1-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a20d1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a20d1-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="a20d1-112">Attributes</span></span>  
  
|<span data-ttu-id="a20d1-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="a20d1-113">Attribute</span></span>|<span data-ttu-id="a20d1-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a20d1-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="a20d1-115">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall angibt, in dem Transaktionen abgeschlossen oder automatisch beendet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="a20d1-115">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="a20d1-116">Der Standardwert ist "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="a20d1-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a20d1-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a20d1-117">Child Elements</span></span>  
 <span data-ttu-id="a20d1-118">Keine</span><span class="sxs-lookup"><span data-stu-id="a20d1-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a20d1-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a20d1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a20d1-120">Element</span><span class="sxs-lookup"><span data-stu-id="a20d1-120">Element</span></span>|<span data-ttu-id="a20d1-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a20d1-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a20d1-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a20d1-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="a20d1-123">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="a20d1-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a20d1-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a20d1-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
