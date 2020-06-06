---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 92a8fa83b5cf5f429278ac8edc8439b627839aad
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400572"
---
# \<callbackDebug>
<span data-ttu-id="423e0-101">Gibt das Dienst Debuggen für ein Windows Communication Foundation (WCF)-Rückruf Objekt an.</span><span class="sxs-lookup"><span data-stu-id="423e0-101">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackDebug>**  
  
## <a name="syntax"></a><span data-ttu-id="423e0-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="423e0-102">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="423e0-103">type</span><span class="sxs-lookup"><span data-stu-id="423e0-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="423e0-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="423e0-104">Attributes and Elements</span></span>  
 <span data-ttu-id="423e0-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="423e0-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="423e0-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="423e0-106">Attributes</span></span>  
  
|<span data-ttu-id="423e0-107">attribute</span><span class="sxs-lookup"><span data-stu-id="423e0-107">Attribute</span></span>|<span data-ttu-id="423e0-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="423e0-108">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="423e0-109">Ein Wert, der angibt, ob Clientcallback-Objekte verwaltete Ausnahmeinformationen in SOAP-Fehlern zurück an den Dienst geben.</span><span class="sxs-lookup"><span data-stu-id="423e0-109">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="423e0-110">Wenn Sie dieses Attribut programmgesteuert auf `true` festlegen, können Sie die Übergabe von verwalteten Ausnahmeinformationen eines Clientcallback-Objekts zurück an den Dienst zu Debuggingzwecken aktivieren.</span><span class="sxs-lookup"><span data-stu-id="423e0-110">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="423e0-111">**Vorsicht:**  Das Zurückgeben von Informationen zu verwalteten Ausnahmen an Clients kann ein Sicherheitsrisiko darstellen.</span><span class="sxs-lookup"><span data-stu-id="423e0-111">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="423e0-112">Das liegt darin begründet, dass Ausnahmedetails Informationen zur internen Dienstimplementierung offen legen, die von nicht autorisierten Clients verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="423e0-112">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="423e0-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="423e0-113">Child Elements</span></span>  
 <span data-ttu-id="423e0-114">Keine</span><span class="sxs-lookup"><span data-stu-id="423e0-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="423e0-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="423e0-115">Parent Elements</span></span>  
  
|<span data-ttu-id="423e0-116">Element</span><span class="sxs-lookup"><span data-stu-id="423e0-116">Element</span></span>|<span data-ttu-id="423e0-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="423e0-117">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="423e0-118">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="423e0-118">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="423e0-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="423e0-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
