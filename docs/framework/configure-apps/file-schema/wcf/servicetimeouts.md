---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 92d3de42daf6f7baf288e3e74242381a60e76618
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153598"
---
# \<serviceTimeouts>

<span data-ttu-id="db03d-101">Gibt den Timeout für einen Dienst an.</span><span class="sxs-lookup"><span data-stu-id="db03d-101">Specifies the timeout for a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTimeouts>**  
  
## <a name="syntax"></a><span data-ttu-id="db03d-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="db03d-102">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="db03d-103">Typ</span><span class="sxs-lookup"><span data-stu-id="db03d-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db03d-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="db03d-104">Attributes and Elements</span></span>  

 <span data-ttu-id="db03d-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="db03d-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db03d-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="db03d-106">Attributes</span></span>  
  
|<span data-ttu-id="db03d-107">attribute</span><span class="sxs-lookup"><span data-stu-id="db03d-107">Attribute</span></span>|<span data-ttu-id="db03d-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="db03d-108">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="db03d-109">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall angibt, in dem eine Transaktion vom Client an den Server weitergegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="db03d-109">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="db03d-110">Der Standardwert ist "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="db03d-110">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="db03d-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="db03d-111">Child Elements</span></span>  

 <span data-ttu-id="db03d-112">Keine</span><span class="sxs-lookup"><span data-stu-id="db03d-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="db03d-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="db03d-113">Parent Elements</span></span>  
  
|<span data-ttu-id="db03d-114">Element</span><span class="sxs-lookup"><span data-stu-id="db03d-114">Element</span></span>|<span data-ttu-id="db03d-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="db03d-115">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="db03d-116">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="db03d-116">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="db03d-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="db03d-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
