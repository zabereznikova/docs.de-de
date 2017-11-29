---
title: '&lt;UseSmallInternalThreadStacks&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2558423b412333a4d6ac9f650ad8ff3dab449d74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltusesmallinternalthreadstacksgt-element"></a><span data-ttu-id="ea353-102">&lt;UseSmallInternalThreadStacks&gt; Element</span><span class="sxs-lookup"><span data-stu-id="ea353-102">&lt;UseSmallInternalThreadStacks&gt; Element</span></span>
<span data-ttu-id="ea353-103">Fordert an, dass die common Language Runtime (CLR) Speicher reduzieren verwenden, indem Sie explizite Stack-Größe angeben, wenn es bestimmte Threads, die sie intern verwendet erstellt, anstatt die Standardgröße des Stapel für diese Threads.</span><span class="sxs-lookup"><span data-stu-id="ea353-103">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
 <span data-ttu-id="ea353-104">\<Konfiguration >-Element</span><span class="sxs-lookup"><span data-stu-id="ea353-104">\<configuration> Element</span></span>  
<span data-ttu-id="ea353-105">\<Common Language Runtime >-Element</span><span class="sxs-lookup"><span data-stu-id="ea353-105">\<runtime> Element</span></span>  
<span data-ttu-id="ea353-106">\<UseSmallInternalThreadStacks >-Element</span><span class="sxs-lookup"><span data-stu-id="ea353-106">\<UseSmallInternalThreadStacks> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea353-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea353-107">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea353-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ea353-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ea353-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ea353-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea353-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="ea353-110">Attributes</span></span>  
  
|<span data-ttu-id="ea353-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="ea353-111">Attribute</span></span>|<span data-ttu-id="ea353-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea353-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ea353-113">enabled</span><span class="sxs-lookup"><span data-stu-id="ea353-113">enabled</span></span>|<span data-ttu-id="ea353-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="ea353-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="ea353-115">Gibt an, ob anfordern, die die CLR verwenden expliziter Stapelgrößen statt die standardmäßige Stapelgröße, wenn sie bestimmte Threads erstellt, die intern verwendet.</span><span class="sxs-lookup"><span data-stu-id="ea353-115">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="ea353-116">Die explizite Stapelgrößen sind kleiner als die Standardstapelgröße 1 MB.</span><span class="sxs-lookup"><span data-stu-id="ea353-116">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="ea353-117">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="ea353-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="ea353-118">Wert</span><span class="sxs-lookup"><span data-stu-id="ea353-118">Value</span></span>|<span data-ttu-id="ea353-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea353-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ea353-120">true</span><span class="sxs-lookup"><span data-stu-id="ea353-120">true</span></span>|<span data-ttu-id="ea353-121">Anforderungsgrößen Sie explizite Stapel.</span><span class="sxs-lookup"><span data-stu-id="ea353-121">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="ea353-122">false</span><span class="sxs-lookup"><span data-stu-id="ea353-122">false</span></span>|<span data-ttu-id="ea353-123">Verwenden Sie die Standardgröße des Stapel an.</span><span class="sxs-lookup"><span data-stu-id="ea353-123">Use the default stack size.</span></span> <span data-ttu-id="ea353-124">Dies ist die Standardeinstellung für die [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea353-124">This is the default for the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea353-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ea353-125">Child Elements</span></span>  
 <span data-ttu-id="ea353-126">Keine</span><span class="sxs-lookup"><span data-stu-id="ea353-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ea353-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ea353-127">Parent Elements</span></span>  
  
|<span data-ttu-id="ea353-128">Element</span><span class="sxs-lookup"><span data-stu-id="ea353-128">Element</span></span>|<span data-ttu-id="ea353-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea353-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ea353-130">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ea353-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ea353-131">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="ea353-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea353-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ea353-132">Remarks</span></span>  
 <span data-ttu-id="ea353-133">Dieses Konfigurationselements wird verwendet, um reduzierte virtueller Arbeitsspeicher-Verwendung in einem Prozess anzufordern, da die expliziten Threadgrößen, die die CLR für die internen Threads verwendet werden, wenn die Anforderung berücksichtigt wird, kleiner als die Standardgröße sind.</span><span class="sxs-lookup"><span data-stu-id="ea353-133">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ea353-134">Dieses Element ist eine Anforderung an die CLR anstatt eine zwingende Voraussetzung nicht erfüllt.</span><span class="sxs-lookup"><span data-stu-id="ea353-134">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="ea353-135">In der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], die Anforderung wird nur für die X86 berücksichtigt Architektur.</span><span class="sxs-lookup"><span data-stu-id="ea353-135">In the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="ea353-136">Dieses Element möglicherweise in künftigen Versionen der CLR vollständig ignoriert, oder durch explizite Stack-Größe, die immer für ausgewählte interne Threads verwendet werden ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="ea353-136">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="ea353-137">Angeben, dass dieses Konfigurationselements Geschäftsbeziehungen Zuverlässigkeit kleiner virtueller Arbeitsspeicher verwendet, wenn die CLR die Anforderung berücksichtigt da kleinere Stapel potenziell Stapel vornehmen können führt zu einem Überlauf wahrscheinlicher ist.</span><span class="sxs-lookup"><span data-stu-id="ea353-137">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea353-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ea353-138">Example</span></span>  
 <span data-ttu-id="ea353-139">Im folgende Beispiel wird gezeigt, wie um anzufordern, dass die CLR verwenden explizite Stapel für bestimmte Threads Größen, die intern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ea353-139">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ea353-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea353-140">See Also</span></span>  
 [<span data-ttu-id="ea353-141">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="ea353-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="ea353-142">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="ea353-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
