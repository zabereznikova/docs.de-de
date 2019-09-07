---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 801a7aaf1f0d0fa267fa8cca3d2e7fd02919c475
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399548"
---
# <a name="servicetimeouts"></a><span data-ttu-id="80513-101">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="80513-101">\<serviceTimeouts></span></span>
<span data-ttu-id="80513-102">Gibt den Timeout für einen Dienst an.</span><span class="sxs-lookup"><span data-stu-id="80513-102">Specifies the timeout for a service.</span></span>  
  
<span data-ttu-id="80513-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="80513-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="80513-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="80513-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="80513-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="80513-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="80513-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceverhaltens>** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="80513-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="80513-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="80513-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="80513-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<servicetimeouts >**</span><span class="sxs-lookup"><span data-stu-id="80513-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTimeouts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80513-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="80513-109">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="80513-110">Typ</span><span class="sxs-lookup"><span data-stu-id="80513-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80513-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="80513-111">Attributes and Elements</span></span>  
 <span data-ttu-id="80513-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="80513-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80513-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="80513-113">Attributes</span></span>  
  
|<span data-ttu-id="80513-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="80513-114">Attribute</span></span>|<span data-ttu-id="80513-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="80513-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="80513-116">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall angibt, in dem eine Transaktion vom Client an den Server weitergegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="80513-116">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="80513-117">Der Standardwert ist "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="80513-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="80513-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="80513-118">Child Elements</span></span>  
 <span data-ttu-id="80513-119">Keine</span><span class="sxs-lookup"><span data-stu-id="80513-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="80513-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="80513-120">Parent Elements</span></span>  
  
|<span data-ttu-id="80513-121">Element</span><span class="sxs-lookup"><span data-stu-id="80513-121">Element</span></span>|<span data-ttu-id="80513-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="80513-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80513-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="80513-123">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="80513-124">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="80513-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="80513-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80513-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
