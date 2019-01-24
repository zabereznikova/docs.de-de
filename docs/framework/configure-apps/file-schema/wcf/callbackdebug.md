---
title: '&lt;callbackDebug&gt;'
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 1aa292a3fe06af9cf1dbc53ebf5bbdf9841be8d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687374"
---
# <a name="ltcallbackdebuggt"></a><span data-ttu-id="f3c10-102">&lt;callbackDebug&gt;</span><span class="sxs-lookup"><span data-stu-id="f3c10-102">&lt;callbackDebug&gt;</span></span>
<span data-ttu-id="f3c10-103">Gibt an, das dienstdebugging für ein Windows Communication Foundation (WCF)-Rückrufobjekt.</span><span class="sxs-lookup"><span data-stu-id="f3c10-103">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
 <span data-ttu-id="f3c10-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f3c10-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f3c10-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="f3c10-105">\<behaviors></span></span>  
<span data-ttu-id="f3c10-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="f3c10-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="f3c10-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f3c10-107">\<behavior></span></span>  
<span data-ttu-id="f3c10-108">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="f3c10-108">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3c10-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="f3c10-109">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="f3c10-110">Typ</span><span class="sxs-lookup"><span data-stu-id="f3c10-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3c10-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f3c10-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f3c10-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f3c10-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3c10-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="f3c10-113">Attributes</span></span>  
  
|<span data-ttu-id="f3c10-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="f3c10-114">Attribute</span></span>|<span data-ttu-id="f3c10-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f3c10-115">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="f3c10-116">Ein Wert, der angibt, ob Clientcallback-Objekte verwaltete Ausnahmeinformationen in SOAP-Fehlern zurück an den Dienst geben.</span><span class="sxs-lookup"><span data-stu-id="f3c10-116">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="f3c10-117">Wenn Sie dieses Attribut programmgesteuert auf `true` festlegen, können Sie die Übergabe von verwalteten Ausnahmeinformationen eines Clientcallback-Objekts zurück an den Dienst zu Debuggingzwecken aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f3c10-117">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="f3c10-118">**Vorsicht**:  Verwaltete Ausnahmeinformationen an Clients zurückzugeben, kann ein Sicherheitsrisiko darstellen.</span><span class="sxs-lookup"><span data-stu-id="f3c10-118">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="f3c10-119">Das liegt darin begründet, dass Ausnahmedetails Informationen zur internen Dienstimplementierung offen legen, die von nicht autorisierten Clients verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="f3c10-119">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f3c10-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f3c10-120">Child Elements</span></span>  
 <span data-ttu-id="f3c10-121">Keine</span><span class="sxs-lookup"><span data-stu-id="f3c10-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f3c10-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f3c10-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f3c10-123">Element</span><span class="sxs-lookup"><span data-stu-id="f3c10-123">Element</span></span>|<span data-ttu-id="f3c10-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f3c10-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3c10-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f3c10-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="f3c10-126">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="f3c10-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f3c10-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3c10-127">See also</span></span>
- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
