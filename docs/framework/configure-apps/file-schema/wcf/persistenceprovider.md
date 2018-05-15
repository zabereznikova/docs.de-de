---
title: '&lt;persistenceProvider&gt;'
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: 3c7fd74a84184ddbf8cc8db90141174ed84e5774
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltpersistenceprovidergt"></a><span data-ttu-id="b7d63-102">&lt;persistenceProvider&gt;</span><span class="sxs-lookup"><span data-stu-id="b7d63-102">&lt;persistenceProvider&gt;</span></span>
<span data-ttu-id="b7d63-103">Gibt den Typ der zu verwendenden Persistenzanbieterimplementierung sowie das Timeout für Persistenzvorgänge an.</span><span class="sxs-lookup"><span data-stu-id="b7d63-103">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
 <span data-ttu-id="b7d63-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b7d63-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b7d63-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="b7d63-105">\<behaviors></span></span>  
<span data-ttu-id="b7d63-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="b7d63-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="b7d63-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="b7d63-107">\<behavior></span></span>  
<span data-ttu-id="b7d63-108">\<PersistenceProvider ></span><span class="sxs-lookup"><span data-stu-id="b7d63-108">\<persistenceProvider></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7d63-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7d63-109">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"  
   type="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7d63-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b7d63-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b7d63-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b7d63-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7d63-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="b7d63-112">Attributes</span></span>  
  
|<span data-ttu-id="b7d63-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="b7d63-113">Attribute</span></span>|<span data-ttu-id="b7d63-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b7d63-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b7d63-115">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="b7d63-115">persistenceOperationTimeout</span></span>|<span data-ttu-id="b7d63-116">Ein <xref:System.TimeSpan>-Wert, der das Timeout angibt, das für Persistenzvorgänge verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b7d63-116">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="b7d63-117">Die Standardeinstellung ist "00: 00:30".</span><span class="sxs-lookup"><span data-stu-id="b7d63-117">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="b7d63-118">Typ</span><span class="sxs-lookup"><span data-stu-id="b7d63-118">type</span></span>|<span data-ttu-id="b7d63-119">Eine Zeichenfolge, die den Typ der zu verwendenden Persistenz-Providerfactory angibt.</span><span class="sxs-lookup"><span data-stu-id="b7d63-119">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7d63-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b7d63-120">Child Elements</span></span>  
 <span data-ttu-id="b7d63-121">Keine</span><span class="sxs-lookup"><span data-stu-id="b7d63-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b7d63-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b7d63-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b7d63-123">Element</span><span class="sxs-lookup"><span data-stu-id="b7d63-123">Element</span></span>|<span data-ttu-id="b7d63-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b7d63-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b7d63-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="b7d63-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="b7d63-126">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="b7d63-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7d63-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b7d63-127">Remarks</span></span>  
 <span data-ttu-id="b7d63-128">Dieses Element gibt den Persistenz-Provider an, der verwendet werden soll, um den Zustand eines WCF-Dienstes zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="b7d63-128">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="b7d63-129">Es sollte zusammen mit der `wsHttpContextBinding` verwendet werden, die Zustandsinformationen in HTTP-Headern übergibt.</span><span class="sxs-lookup"><span data-stu-id="b7d63-129">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7d63-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7d63-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PersistenceProviderElement>  
 <xref:System.ServiceModel.Persistence.PersistenceProvider>
