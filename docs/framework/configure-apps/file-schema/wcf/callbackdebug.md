---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: a1190eb1c015ba07488ff5a5952f2f5f1b10974c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704517"
---
# <a name="callbackdebug"></a><span data-ttu-id="5630c-101">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="5630c-101">\<callbackDebug></span></span>
<span data-ttu-id="5630c-102">Gibt an, das dienstdebugging für ein Windows Communication Foundation (WCF)-Rückrufobjekt.</span><span class="sxs-lookup"><span data-stu-id="5630c-102">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
 <span data-ttu-id="5630c-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5630c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="5630c-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="5630c-104">\<behaviors></span></span>  
<span data-ttu-id="5630c-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="5630c-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="5630c-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5630c-106">\<behavior></span></span>  
<span data-ttu-id="5630c-107">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="5630c-107">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5630c-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="5630c-108">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="5630c-109">Typ</span><span class="sxs-lookup"><span data-stu-id="5630c-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5630c-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5630c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5630c-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5630c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5630c-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="5630c-112">Attributes</span></span>  
  
|<span data-ttu-id="5630c-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="5630c-113">Attribute</span></span>|<span data-ttu-id="5630c-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5630c-114">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="5630c-115">Ein Wert, der angibt, ob Clientcallback-Objekte verwaltete Ausnahmeinformationen in SOAP-Fehlern zurück an den Dienst geben.</span><span class="sxs-lookup"><span data-stu-id="5630c-115">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="5630c-116">Wenn Sie dieses Attribut programmgesteuert auf `true` festlegen, können Sie die Übergabe von verwalteten Ausnahmeinformationen eines Clientcallback-Objekts zurück an den Dienst zu Debuggingzwecken aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5630c-116">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="5630c-117">**Vorsicht**:  Verwaltete Ausnahmeinformationen an Clients zurückzugeben, kann ein Sicherheitsrisiko darstellen.</span><span class="sxs-lookup"><span data-stu-id="5630c-117">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="5630c-118">Das liegt darin begründet, dass Ausnahmedetails Informationen zur internen Dienstimplementierung offen legen, die von nicht autorisierten Clients verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="5630c-118">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5630c-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5630c-119">Child Elements</span></span>  
 <span data-ttu-id="5630c-120">Keine</span><span class="sxs-lookup"><span data-stu-id="5630c-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5630c-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5630c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5630c-122">Element</span><span class="sxs-lookup"><span data-stu-id="5630c-122">Element</span></span>|<span data-ttu-id="5630c-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5630c-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5630c-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5630c-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="5630c-125">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="5630c-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5630c-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5630c-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
