---
title: '&lt;callbackDebug&gt;'
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 5bd2356c3bb798e948341cb3c4ba504ac886ed44
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145080"
---
# <a name="ltcallbackdebuggt"></a><span data-ttu-id="cb48d-102">&lt;callbackDebug&gt;</span><span class="sxs-lookup"><span data-stu-id="cb48d-102">&lt;callbackDebug&gt;</span></span>
<span data-ttu-id="cb48d-103">Gibt an, das dienstdebugging für ein Windows Communication Foundation (WCF)-Rückrufobjekt.</span><span class="sxs-lookup"><span data-stu-id="cb48d-103">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
 <span data-ttu-id="cb48d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cb48d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cb48d-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="cb48d-105">\<behaviors></span></span>  
<span data-ttu-id="cb48d-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="cb48d-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="cb48d-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="cb48d-107">\<behavior></span></span>  
<span data-ttu-id="cb48d-108">\<CallbackDebug ></span><span class="sxs-lookup"><span data-stu-id="cb48d-108">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb48d-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="cb48d-109">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="cb48d-110">Typ</span><span class="sxs-lookup"><span data-stu-id="cb48d-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb48d-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cb48d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="cb48d-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cb48d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb48d-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="cb48d-113">Attributes</span></span>  
  
|<span data-ttu-id="cb48d-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="cb48d-114">Attribute</span></span>|<span data-ttu-id="cb48d-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cb48d-115">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="cb48d-116">Ein Wert, der angibt, ob Clientcallback-Objekte verwaltete Ausnahmeinformationen in SOAP-Fehlern zurück an den Dienst geben.</span><span class="sxs-lookup"><span data-stu-id="cb48d-116">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="cb48d-117">Wenn Sie dieses Attribut programmgesteuert auf `true` festlegen, können Sie die Übergabe von verwalteten Ausnahmeinformationen eines Clientcallback-Objekts zurück an den Dienst zu Debuggingzwecken aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cb48d-117">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="cb48d-118">**Vorsicht**:  Verwaltete Ausnahmeinformationen an Clients zurückzugeben, kann ein Sicherheitsrisiko darstellen.</span><span class="sxs-lookup"><span data-stu-id="cb48d-118">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="cb48d-119">Das liegt darin begründet, dass Ausnahmedetails Informationen zur internen Dienstimplementierung offen legen, die von nicht autorisierten Clients verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="cb48d-119">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cb48d-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cb48d-120">Child Elements</span></span>  
 <span data-ttu-id="cb48d-121">Keine</span><span class="sxs-lookup"><span data-stu-id="cb48d-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cb48d-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cb48d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="cb48d-123">Element</span><span class="sxs-lookup"><span data-stu-id="cb48d-123">Element</span></span>|<span data-ttu-id="cb48d-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cb48d-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb48d-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="cb48d-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="cb48d-126">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="cb48d-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cb48d-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb48d-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackDebugElement>  
 <xref:System.ServiceModel.Description.CallbackDebugBehavior>
