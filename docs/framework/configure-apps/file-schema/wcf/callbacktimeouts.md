---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: d57a888a19e684ac13632c1ab2476e304667c3e3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919667"
---
# <a name="callbacktimeouts"></a><span data-ttu-id="8ea6f-101">\<callbackTimeouts></span><span class="sxs-lookup"><span data-stu-id="8ea6f-101">\<callbackTimeouts></span></span>
<span data-ttu-id="8ea6f-102">Gibt den Timeoutwert bei der Weitergabe von Transaktionen vom Server zum Client in einem Duplexrückrufvertragsszenario an.</span><span class="sxs-lookup"><span data-stu-id="8ea6f-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="8ea6f-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8ea6f-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="8ea6f-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="8ea6f-104">\<behaviors></span></span>  
<span data-ttu-id="8ea6f-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="8ea6f-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="8ea6f-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8ea6f-106">\<behavior></span></span>  
<span data-ttu-id="8ea6f-107">\<callbackTimeOuts></span><span class="sxs-lookup"><span data-stu-id="8ea6f-107">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ea6f-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ea6f-108">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="8ea6f-109">Typ</span><span class="sxs-lookup"><span data-stu-id="8ea6f-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ea6f-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8ea6f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8ea6f-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8ea6f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ea6f-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="8ea6f-112">Attributes</span></span>  
  
|<span data-ttu-id="8ea6f-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="8ea6f-113">Attribute</span></span>|<span data-ttu-id="8ea6f-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8ea6f-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="8ea6f-115">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall angibt, in dem Transaktionen abgeschlossen oder automatisch beendet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="8ea6f-115">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="8ea6f-116">Der Standardwert ist "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="8ea6f-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ea6f-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8ea6f-117">Child Elements</span></span>  
 <span data-ttu-id="8ea6f-118">Keine</span><span class="sxs-lookup"><span data-stu-id="8ea6f-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8ea6f-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8ea6f-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8ea6f-120">Element</span><span class="sxs-lookup"><span data-stu-id="8ea6f-120">Element</span></span>|<span data-ttu-id="8ea6f-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8ea6f-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ea6f-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8ea6f-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="8ea6f-123">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="8ea6f-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8ea6f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ea6f-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
