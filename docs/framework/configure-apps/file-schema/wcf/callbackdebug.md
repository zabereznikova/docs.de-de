---
title: '&lt;callbackDebug&gt;'
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 2103c32112b6c5554d7b510f486d4cbb1349f35d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747948"
---
# <a name="ltcallbackdebuggt"></a><span data-ttu-id="0bdc6-102">&lt;callbackDebug&gt;</span><span class="sxs-lookup"><span data-stu-id="0bdc6-102">&lt;callbackDebug&gt;</span></span>
<span data-ttu-id="0bdc6-103">Gibt das dienstdebugging für ein Rückrufobjekt für Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="0bdc6-103">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
 <span data-ttu-id="0bdc6-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0bdc6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0bdc6-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="0bdc6-105">\<behaviors></span></span>  
<span data-ttu-id="0bdc6-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="0bdc6-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="0bdc6-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="0bdc6-107">\<behavior></span></span>  
<span data-ttu-id="0bdc6-108">\<CallbackDebug ></span><span class="sxs-lookup"><span data-stu-id="0bdc6-108">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bdc6-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="0bdc6-109">Syntax</span></span>  
  
```xml  
<callbackDebug  includeExceptionDetailInFaults="Boolean" />  
```  
  
## <a name="type"></a><span data-ttu-id="0bdc6-110">Typ</span><span class="sxs-lookup"><span data-stu-id="0bdc6-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0bdc6-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0bdc6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0bdc6-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0bdc6-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="0bdc6-113">Attributes</span></span>  
  
|<span data-ttu-id="0bdc6-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="0bdc6-114">Attribute</span></span>|<span data-ttu-id="0bdc6-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0bdc6-115">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="0bdc6-116">Ein Wert, der angibt, ob Clientcallback-Objekte verwaltete Ausnahmeinformationen in SOAP-Fehlern zurück an den Dienst geben.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-116">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="0bdc6-117">Wenn Sie dieses Attribut programmgesteuert auf `true` festlegen, können Sie die Übergabe von verwalteten Ausnahmeinformationen eines Clientcallback-Objekts zurück an den Dienst zu Debuggingzwecken aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-117">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="0bdc6-118">**Vorsicht:** zurückgeben, verwaltete Ausnahmeinformationen an Clients kann ein Sicherheitsrisiko sein.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-118">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="0bdc6-119">Das liegt darin begründet, dass Ausnahmedetails Informationen zur internen Dienstimplementierung offen legen, die von nicht autorisierten Clients verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-119">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0bdc6-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0bdc6-120">Child Elements</span></span>  
 <span data-ttu-id="0bdc6-121">Keine</span><span class="sxs-lookup"><span data-stu-id="0bdc6-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0bdc6-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0bdc6-122">Parent Elements</span></span>  
  
|<span data-ttu-id="0bdc6-123">Element</span><span class="sxs-lookup"><span data-stu-id="0bdc6-123">Element</span></span>|<span data-ttu-id="0bdc6-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0bdc6-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0bdc6-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="0bdc6-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="0bdc6-126">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="0bdc6-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0bdc6-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0bdc6-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackDebugElement>  
 <xref:System.ServiceModel.Description.CallbackDebugBehavior>
