---
title: '&lt;callbackDebug&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0bb730a00358f771408ff0431ff2ab77623354a4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltcallbackdebuggt"></a><span data-ttu-id="17b77-102">&lt;callbackDebug&gt;</span><span class="sxs-lookup"><span data-stu-id="17b77-102">&lt;callbackDebug&gt;</span></span>
<span data-ttu-id="17b77-103">Legt Dienstdebugging für ein [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Rückrufobjekt fest.</span><span class="sxs-lookup"><span data-stu-id="17b77-103">Specifies service debugging for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] callback object.</span></span>  
  
 <span data-ttu-id="17b77-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="17b77-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="17b77-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="17b77-105">\<behaviors></span></span>  
<span data-ttu-id="17b77-106">\<EndpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="17b77-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="17b77-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="17b77-107">\<behavior></span></span>  
<span data-ttu-id="17b77-108">\<CallbackDebug ></span><span class="sxs-lookup"><span data-stu-id="17b77-108">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17b77-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="17b77-109">Syntax</span></span>  
  
```xml  
<callbackDebug  includeExceptionDetailInFaults="Boolean" />  
```  
  
## <a name="type"></a><span data-ttu-id="17b77-110">Typ</span><span class="sxs-lookup"><span data-stu-id="17b77-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17b77-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="17b77-111">Attributes and Elements</span></span>  
 <span data-ttu-id="17b77-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="17b77-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17b77-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="17b77-113">Attributes</span></span>  
  
|<span data-ttu-id="17b77-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="17b77-114">Attribute</span></span>|<span data-ttu-id="17b77-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="17b77-115">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="17b77-116">Ein Wert, der angibt, ob Clientcallback-Objekte verwaltete Ausnahmeinformationen in SOAP-Fehlern zurück an den Dienst geben.</span><span class="sxs-lookup"><span data-stu-id="17b77-116">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="17b77-117">Wenn Sie dieses Attribut programmgesteuert auf `true` festlegen, können Sie die Übergabe von verwalteten Ausnahmeinformationen eines Clientcallback-Objekts zurück an den Dienst zu Debuggingzwecken aktivieren.</span><span class="sxs-lookup"><span data-stu-id="17b77-117">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="17b77-118">**Vorsicht:** zurückgeben, verwaltete Ausnahmeinformationen an Clients kann ein Sicherheitsrisiko sein.</span><span class="sxs-lookup"><span data-stu-id="17b77-118">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="17b77-119">Das liegt darin begründet, dass Ausnahmedetails Informationen zur internen Dienstimplementierung offen legen, die von nicht autorisierten Clients verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="17b77-119">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="17b77-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="17b77-120">Child Elements</span></span>  
 <span data-ttu-id="17b77-121">Keine</span><span class="sxs-lookup"><span data-stu-id="17b77-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="17b77-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="17b77-122">Parent Elements</span></span>  
  
|<span data-ttu-id="17b77-123">Element</span><span class="sxs-lookup"><span data-stu-id="17b77-123">Element</span></span>|<span data-ttu-id="17b77-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="17b77-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="17b77-125">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="17b77-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="17b77-126">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="17b77-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="17b77-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17b77-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackDebugElement>  
 <xref:System.ServiceModel.Description.CallbackDebugBehavior>
