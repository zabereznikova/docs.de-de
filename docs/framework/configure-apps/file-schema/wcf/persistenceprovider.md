---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: 7c4d9ae29ca1e543217d444e05a661b48e2cbb62
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400076"
---
# <a name="persistenceprovider"></a><span data-ttu-id="99a89-101">\<persistenceProvider></span><span class="sxs-lookup"><span data-stu-id="99a89-101">\<persistenceProvider></span></span>
<span data-ttu-id="99a89-102">Gibt den Typ der zu verwendenden Persistenzanbieterimplementierung sowie das Timeout für Persistenzvorgänge an.</span><span class="sxs-lookup"><span data-stu-id="99a89-102">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
<span data-ttu-id="99a89-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="99a89-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="99a89-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="99a89-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="99a89-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="99a89-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="99a89-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceverhaltens>** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="99a89-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="99a89-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="99a89-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="99a89-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<PersistenceProvider->**</span><span class="sxs-lookup"><span data-stu-id="99a89-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistenceProvider>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99a89-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="99a89-109">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99a89-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="99a89-110">Attributes and Elements</span></span>  
 <span data-ttu-id="99a89-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="99a89-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99a89-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="99a89-112">Attributes</span></span>  
  
|<span data-ttu-id="99a89-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="99a89-113">Attribute</span></span>|<span data-ttu-id="99a89-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99a89-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99a89-115">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="99a89-115">persistenceOperationTimeout</span></span>|<span data-ttu-id="99a89-116">Ein <xref:System.TimeSpan>-Wert, der das Timeout angibt, das für Persistenzvorgänge verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="99a89-116">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="99a89-117">Der Standardwert ist "00:00:30".</span><span class="sxs-lookup"><span data-stu-id="99a89-117">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="99a89-118">Typ</span><span class="sxs-lookup"><span data-stu-id="99a89-118">type</span></span>|<span data-ttu-id="99a89-119">Eine Zeichenfolge, die den Typ der zu verwendenden Persistenz-Providerfactory angibt.</span><span class="sxs-lookup"><span data-stu-id="99a89-119">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99a89-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="99a89-120">Child Elements</span></span>  
 <span data-ttu-id="99a89-121">Keine</span><span class="sxs-lookup"><span data-stu-id="99a89-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99a89-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="99a89-122">Parent Elements</span></span>  
  
|<span data-ttu-id="99a89-123">Element</span><span class="sxs-lookup"><span data-stu-id="99a89-123">Element</span></span>|<span data-ttu-id="99a89-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99a89-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99a89-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="99a89-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="99a89-126">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="99a89-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99a89-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="99a89-127">Remarks</span></span>  
 <span data-ttu-id="99a89-128">Dieses Element gibt den Persistenz-Provider an, der verwendet werden soll, um den Zustand eines WCF-Dienstes zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="99a89-128">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="99a89-129">Es sollte zusammen mit der `wsHttpContextBinding` verwendet werden, die Zustandsinformationen in HTTP-Headern übergibt.</span><span class="sxs-lookup"><span data-stu-id="99a89-129">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99a89-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99a89-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
