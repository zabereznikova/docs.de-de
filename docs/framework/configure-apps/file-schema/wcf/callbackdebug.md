---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 91e7bd63bf496f2c38776d88173ed2ac12a3b888
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926311"
---
# <a name="callbackdebug"></a><span data-ttu-id="cb3e9-101">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="cb3e9-101">\<callbackDebug></span></span>
<span data-ttu-id="cb3e9-102">Gibt das Dienst Debuggen für ein Windows Communication Foundation (WCF)-Rückruf Objekt an.</span><span class="sxs-lookup"><span data-stu-id="cb3e9-102">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
 <span data-ttu-id="cb3e9-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cb3e9-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="cb3e9-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="cb3e9-104">\<behaviors></span></span>  
<span data-ttu-id="cb3e9-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="cb3e9-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="cb3e9-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="cb3e9-106">\<behavior></span></span>  
<span data-ttu-id="cb3e9-107">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="cb3e9-107">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb3e9-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="cb3e9-108">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="cb3e9-109">Typ</span><span class="sxs-lookup"><span data-stu-id="cb3e9-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb3e9-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cb3e9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cb3e9-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cb3e9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb3e9-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="cb3e9-112">Attributes</span></span>  
  
|<span data-ttu-id="cb3e9-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="cb3e9-113">Attribute</span></span>|<span data-ttu-id="cb3e9-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cb3e9-114">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="cb3e9-115">Ein Wert, der angibt, ob Clientcallback-Objekte verwaltete Ausnahmeinformationen in SOAP-Fehlern zurück an den Dienst geben.</span><span class="sxs-lookup"><span data-stu-id="cb3e9-115">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="cb3e9-116">Wenn Sie dieses Attribut programmgesteuert auf `true` festlegen, können Sie die Übergabe von verwalteten Ausnahmeinformationen eines Clientcallback-Objekts zurück an den Dienst zu Debuggingzwecken aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cb3e9-116">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="cb3e9-117">**Vorsicht**:  Verwaltete Ausnahmeinformationen an Clients zurückzugeben, kann ein Sicherheitsrisiko darstellen.</span><span class="sxs-lookup"><span data-stu-id="cb3e9-117">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="cb3e9-118">Das liegt darin begründet, dass Ausnahmedetails Informationen zur internen Dienstimplementierung offen legen, die von nicht autorisierten Clients verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="cb3e9-118">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cb3e9-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cb3e9-119">Child Elements</span></span>  
 <span data-ttu-id="cb3e9-120">Keine</span><span class="sxs-lookup"><span data-stu-id="cb3e9-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cb3e9-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cb3e9-121">Parent Elements</span></span>  
  
|<span data-ttu-id="cb3e9-122">Element</span><span class="sxs-lookup"><span data-stu-id="cb3e9-122">Element</span></span>|<span data-ttu-id="cb3e9-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cb3e9-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb3e9-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="cb3e9-124">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="cb3e9-125">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="cb3e9-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cb3e9-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb3e9-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
