---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 92a8fa83b5cf5f429278ac8edc8439b627839aad
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400572"
---
# <a name="callbackdebug"></a><span data-ttu-id="05852-101">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="05852-101">\<callbackDebug></span></span>
<span data-ttu-id="05852-102">Gibt das Dienst Debuggen für ein Windows Communication Foundation (WCF)-Rückruf Objekt an.</span><span class="sxs-lookup"><span data-stu-id="05852-102">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
<span data-ttu-id="05852-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="05852-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="05852-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="05852-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="05852-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="05852-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="05852-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="05852-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="05852-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="05852-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="05852-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<callbackdebug->**</span><span class="sxs-lookup"><span data-stu-id="05852-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackDebug>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05852-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="05852-109">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="05852-110">Typ</span><span class="sxs-lookup"><span data-stu-id="05852-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05852-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="05852-111">Attributes and Elements</span></span>  
 <span data-ttu-id="05852-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="05852-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05852-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="05852-113">Attributes</span></span>  
  
|<span data-ttu-id="05852-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="05852-114">Attribute</span></span>|<span data-ttu-id="05852-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05852-115">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="05852-116">Ein Wert, der angibt, ob Clientcallback-Objekte verwaltete Ausnahmeinformationen in SOAP-Fehlern zurück an den Dienst geben.</span><span class="sxs-lookup"><span data-stu-id="05852-116">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="05852-117">Wenn Sie dieses Attribut programmgesteuert auf `true` festlegen, können Sie die Übergabe von verwalteten Ausnahmeinformationen eines Clientcallback-Objekts zurück an den Dienst zu Debuggingzwecken aktivieren.</span><span class="sxs-lookup"><span data-stu-id="05852-117">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="05852-118">**Vorsicht**:  Verwaltete Ausnahmeinformationen an Clients zurückzugeben, kann ein Sicherheitsrisiko darstellen.</span><span class="sxs-lookup"><span data-stu-id="05852-118">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="05852-119">Das liegt darin begründet, dass Ausnahmedetails Informationen zur internen Dienstimplementierung offen legen, die von nicht autorisierten Clients verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="05852-119">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="05852-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="05852-120">Child Elements</span></span>  
 <span data-ttu-id="05852-121">Keine</span><span class="sxs-lookup"><span data-stu-id="05852-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="05852-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="05852-122">Parent Elements</span></span>  
  
|<span data-ttu-id="05852-123">Element</span><span class="sxs-lookup"><span data-stu-id="05852-123">Element</span></span>|<span data-ttu-id="05852-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05852-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05852-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="05852-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="05852-126">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="05852-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05852-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05852-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
