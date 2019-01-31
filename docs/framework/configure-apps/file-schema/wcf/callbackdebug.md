---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 62ce1bc179c7215d4988e4c6bda08025c3d3e5de
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286311"
---
# <a name="callbackdebug"></a><span data-ttu-id="06a2d-101">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="06a2d-101">\<callbackDebug></span></span>
<span data-ttu-id="06a2d-102">Gibt an, das dienstdebugging für ein Windows Communication Foundation (WCF)-Rückrufobjekt.</span><span class="sxs-lookup"><span data-stu-id="06a2d-102">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
 <span data-ttu-id="06a2d-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="06a2d-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="06a2d-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="06a2d-104">\<behaviors></span></span>  
<span data-ttu-id="06a2d-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="06a2d-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="06a2d-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="06a2d-106">\<behavior></span></span>  
<span data-ttu-id="06a2d-107">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="06a2d-107">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06a2d-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="06a2d-108">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="06a2d-109">Typ</span><span class="sxs-lookup"><span data-stu-id="06a2d-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06a2d-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="06a2d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="06a2d-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="06a2d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06a2d-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="06a2d-112">Attributes</span></span>  
  
|<span data-ttu-id="06a2d-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="06a2d-113">Attribute</span></span>|<span data-ttu-id="06a2d-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="06a2d-114">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="06a2d-115">Ein Wert, der angibt, ob Clientcallback-Objekte verwaltete Ausnahmeinformationen in SOAP-Fehlern zurück an den Dienst geben.</span><span class="sxs-lookup"><span data-stu-id="06a2d-115">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="06a2d-116">Wenn Sie dieses Attribut programmgesteuert auf `true` festlegen, können Sie die Übergabe von verwalteten Ausnahmeinformationen eines Clientcallback-Objekts zurück an den Dienst zu Debuggingzwecken aktivieren.</span><span class="sxs-lookup"><span data-stu-id="06a2d-116">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="06a2d-117">**Vorsicht**:  Verwaltete Ausnahmeinformationen an Clients zurückzugeben, kann ein Sicherheitsrisiko darstellen.</span><span class="sxs-lookup"><span data-stu-id="06a2d-117">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="06a2d-118">Das liegt darin begründet, dass Ausnahmedetails Informationen zur internen Dienstimplementierung offen legen, die von nicht autorisierten Clients verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="06a2d-118">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06a2d-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="06a2d-119">Child Elements</span></span>  
 <span data-ttu-id="06a2d-120">Keine</span><span class="sxs-lookup"><span data-stu-id="06a2d-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="06a2d-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="06a2d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="06a2d-122">Element</span><span class="sxs-lookup"><span data-stu-id="06a2d-122">Element</span></span>|<span data-ttu-id="06a2d-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="06a2d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06a2d-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="06a2d-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="06a2d-125">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="06a2d-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="06a2d-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06a2d-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
