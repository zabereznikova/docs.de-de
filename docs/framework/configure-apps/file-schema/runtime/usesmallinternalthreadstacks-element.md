---
title: <UseSmallInternalThreadStacks>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 70113d98c5a4ab41700f6c9842dba89e2b49c297
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489328"
---
# <a name="usesmallinternalthreadstacks-element"></a><span data-ttu-id="42fba-102">\<UseSmallInternalThreadStacks >-Element</span><span class="sxs-lookup"><span data-stu-id="42fba-102">\<UseSmallInternalThreadStacks> Element</span></span>
<span data-ttu-id="42fba-103">Fordert an, dass die common Language Runtime (CLR) Speicher reduzieren verwenden, indem Sie explizite Stapelgrößen angeben, wenn es sich um bestimmte Threads, die sie intern verwendet erstellt, statt die standardmäßige Stapelgröße für diese Threads.</span><span class="sxs-lookup"><span data-stu-id="42fba-103">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
 <span data-ttu-id="42fba-104">\<Configuration >-Element</span><span class="sxs-lookup"><span data-stu-id="42fba-104">\<configuration> Element</span></span>  
<span data-ttu-id="42fba-105">\<Common Language Runtime >-Element</span><span class="sxs-lookup"><span data-stu-id="42fba-105">\<runtime> Element</span></span>  
<span data-ttu-id="42fba-106">\<UseSmallInternalThreadStacks >-Element</span><span class="sxs-lookup"><span data-stu-id="42fba-106">\<UseSmallInternalThreadStacks> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42fba-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="42fba-107">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42fba-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="42fba-108">Attributes and Elements</span></span>  
 <span data-ttu-id="42fba-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="42fba-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42fba-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="42fba-110">Attributes</span></span>  
  
|<span data-ttu-id="42fba-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="42fba-111">Attribute</span></span>|<span data-ttu-id="42fba-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42fba-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42fba-113">enabled</span><span class="sxs-lookup"><span data-stu-id="42fba-113">enabled</span></span>|<span data-ttu-id="42fba-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="42fba-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="42fba-115">Gibt an, ob anfordern, die die CLR explizite Stapelgrößen anstelle der Standardstapelgröße Wenn es sich um bestimmte Threads erstellt, die intern verwendet.</span><span class="sxs-lookup"><span data-stu-id="42fba-115">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="42fba-116">Die explizite Stapelgrößen sind kleiner als die Standardstapelgröße 1 MB.</span><span class="sxs-lookup"><span data-stu-id="42fba-116">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="42fba-117">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="42fba-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="42fba-118">Wert</span><span class="sxs-lookup"><span data-stu-id="42fba-118">Value</span></span>|<span data-ttu-id="42fba-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42fba-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="42fba-120">true</span><span class="sxs-lookup"><span data-stu-id="42fba-120">true</span></span>|<span data-ttu-id="42fba-121">Fordern Sie explizite Stapelgrößen an.</span><span class="sxs-lookup"><span data-stu-id="42fba-121">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="42fba-122">False</span><span class="sxs-lookup"><span data-stu-id="42fba-122">false</span></span>|<span data-ttu-id="42fba-123">Verwenden Sie die standardmäßige Stapelgröße.</span><span class="sxs-lookup"><span data-stu-id="42fba-123">Use the default stack size.</span></span> <span data-ttu-id="42fba-124">Dies ist die Standardeinstellung für .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="42fba-124">This is the default for the .NET Framework 4.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42fba-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="42fba-125">Child Elements</span></span>  
 <span data-ttu-id="42fba-126">Keine</span><span class="sxs-lookup"><span data-stu-id="42fba-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="42fba-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="42fba-127">Parent Elements</span></span>  
  
|<span data-ttu-id="42fba-128">Element</span><span class="sxs-lookup"><span data-stu-id="42fba-128">Element</span></span>|<span data-ttu-id="42fba-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42fba-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="42fba-130">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="42fba-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="42fba-131">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="42fba-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42fba-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="42fba-132">Remarks</span></span>  
 <span data-ttu-id="42fba-133">Dieses Konfigurationselement wird verwendet, weniger virtuelle Arbeitsspeicher verwenden, in einem Prozess, anfordern, da die Größe der expliziten Threads, die die CLR für die internen Threads verwendet werden, wenn die Anforderung berücksichtigt wird, kleiner als die Standardgröße ist.</span><span class="sxs-lookup"><span data-stu-id="42fba-133">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="42fba-134">Dieses Element ist eine Anforderung an die CLR, anstatt eine zwingende Voraussetzung nicht erfüllt.</span><span class="sxs-lookup"><span data-stu-id="42fba-134">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="42fba-135">In .NET Framework 4, wird die Anforderung nur für die X86 berücksichtigt Architektur.</span><span class="sxs-lookup"><span data-stu-id="42fba-135">In the .NET Framework 4, the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="42fba-136">Dieses Element möglicherweise vollständig in zukünftigen Versionen der CLR ignoriert, oder durch explizite Stapelgrößen, die immer für den ausgewählten internen Threads verwendet werden ersetzt.</span><span class="sxs-lookup"><span data-stu-id="42fba-136">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="42fba-137">Angeben, dass dieses Konfigurationselement Klassen Zuverlässigkeit für kleinere virtueller Arbeitsspeicher verwenden, wenn die CLR die Anforderung berücksichtigt, da kleinere Stapel möglicherweise Stack vornehmen könnten eher überläuft.</span><span class="sxs-lookup"><span data-stu-id="42fba-137">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42fba-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="42fba-138">Example</span></span>  
 <span data-ttu-id="42fba-139">Das folgende Beispiel zeigt, wie Sie anfordern, dass die CLR mit explizite Stapel für bestimmte Threads Größen, die intern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="42fba-139">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="42fba-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42fba-140">See also</span></span>

- [<span data-ttu-id="42fba-141">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="42fba-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="42fba-142">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="42fba-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
