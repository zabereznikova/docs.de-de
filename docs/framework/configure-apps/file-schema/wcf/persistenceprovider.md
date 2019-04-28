---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: dc8dea0ddd1ea074c08952e3e2ebfef2d12f7183
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783291"
---
# <a name="persistenceprovider"></a><span data-ttu-id="4d7a9-101">\<persistenceProvider></span><span class="sxs-lookup"><span data-stu-id="4d7a9-101">\<persistenceProvider></span></span>
<span data-ttu-id="4d7a9-102">Gibt den Typ der zu verwendenden Persistenzanbieterimplementierung sowie das Timeout für Persistenzvorgänge an.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-102">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
 <span data-ttu-id="4d7a9-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4d7a9-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="4d7a9-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="4d7a9-104">\<behaviors></span></span>  
<span data-ttu-id="4d7a9-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="4d7a9-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="4d7a9-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4d7a9-106">\<behavior></span></span>  
<span data-ttu-id="4d7a9-107">\<persistenceProvider></span><span class="sxs-lookup"><span data-stu-id="4d7a9-107">\<persistenceProvider></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d7a9-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="4d7a9-108">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d7a9-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4d7a9-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4d7a9-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d7a9-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="4d7a9-111">Attributes</span></span>  
  
|<span data-ttu-id="4d7a9-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="4d7a9-112">Attribute</span></span>|<span data-ttu-id="4d7a9-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4d7a9-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4d7a9-114">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="4d7a9-114">persistenceOperationTimeout</span></span>|<span data-ttu-id="4d7a9-115">Ein <xref:System.TimeSpan>-Wert, der das Timeout angibt, das für Persistenzvorgänge verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-115">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="4d7a9-116">Der Standardwert ist "00: 00:30".</span><span class="sxs-lookup"><span data-stu-id="4d7a9-116">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="4d7a9-117">Typ</span><span class="sxs-lookup"><span data-stu-id="4d7a9-117">type</span></span>|<span data-ttu-id="4d7a9-118">Eine Zeichenfolge, die den Typ der zu verwendenden Persistenz-Providerfactory angibt.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-118">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d7a9-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4d7a9-119">Child Elements</span></span>  
 <span data-ttu-id="4d7a9-120">Keine</span><span class="sxs-lookup"><span data-stu-id="4d7a9-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4d7a9-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4d7a9-121">Parent Elements</span></span>  
  
|<span data-ttu-id="4d7a9-122">Element</span><span class="sxs-lookup"><span data-stu-id="4d7a9-122">Element</span></span>|<span data-ttu-id="4d7a9-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4d7a9-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d7a9-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4d7a9-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="4d7a9-125">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-125">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d7a9-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4d7a9-126">Remarks</span></span>  
 <span data-ttu-id="4d7a9-127">Dieses Element gibt den Persistenz-Provider an, der verwendet werden soll, um den Zustand eines WCF-Dienstes zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-127">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="4d7a9-128">Es sollte zusammen mit der `wsHttpContextBinding` verwendet werden, die Zustandsinformationen in HTTP-Headern übergibt.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-128">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d7a9-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d7a9-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
