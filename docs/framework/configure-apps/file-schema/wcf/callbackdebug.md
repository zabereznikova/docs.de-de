---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 02632cc3f668bb9e4cc6f8c9726d7bcb3cab2c5d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183818"
---
# \<callbackDebug>

<span data-ttu-id="8e79a-101">Gibt das Dienst Debuggen für ein Windows Communication Foundation (WCF)-Rückruf Objekt an.</span><span class="sxs-lookup"><span data-stu-id="8e79a-101">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackDebug>**  
  
## <a name="syntax"></a><span data-ttu-id="8e79a-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e79a-102">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="8e79a-103">Typ</span><span class="sxs-lookup"><span data-stu-id="8e79a-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e79a-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8e79a-104">Attributes and Elements</span></span>  

 <span data-ttu-id="8e79a-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8e79a-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e79a-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="8e79a-106">Attributes</span></span>  
  
|<span data-ttu-id="8e79a-107">attribute</span><span class="sxs-lookup"><span data-stu-id="8e79a-107">Attribute</span></span>|<span data-ttu-id="8e79a-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8e79a-108">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="8e79a-109">Ein Wert, der angibt, ob Clientcallback-Objekte verwaltete Ausnahmeinformationen in SOAP-Fehlern zurück an den Dienst geben.</span><span class="sxs-lookup"><span data-stu-id="8e79a-109">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="8e79a-110">Wenn Sie dieses Attribut programmgesteuert auf `true` festlegen, können Sie die Übergabe von verwalteten Ausnahmeinformationen eines Clientcallback-Objekts zurück an den Dienst zu Debuggingzwecken aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8e79a-110">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="8e79a-111">**Vorsicht:**  Das Zurückgeben von Informationen zu verwalteten Ausnahmen an Clients kann ein Sicherheitsrisiko darstellen.</span><span class="sxs-lookup"><span data-stu-id="8e79a-111">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="8e79a-112">Das liegt darin begründet, dass Ausnahmedetails Informationen zur internen Dienstimplementierung offen legen, die von nicht autorisierten Clients verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="8e79a-112">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e79a-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8e79a-113">Child Elements</span></span>  

 <span data-ttu-id="8e79a-114">Keine</span><span class="sxs-lookup"><span data-stu-id="8e79a-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e79a-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8e79a-115">Parent Elements</span></span>  
  
|<span data-ttu-id="8e79a-116">Element</span><span class="sxs-lookup"><span data-stu-id="8e79a-116">Element</span></span>|<span data-ttu-id="8e79a-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8e79a-117">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="8e79a-118">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="8e79a-118">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8e79a-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8e79a-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
