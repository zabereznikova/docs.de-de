---
title: <UseSmallInternalThreadStacks>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74678089bb1b19295983064eb7ad54fbf0a1e361
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663388"
---
# <a name="usesmallinternalthreadstacks-element"></a><span data-ttu-id="24679-102">\<Das Element "" ist > Element "" von "".</span><span class="sxs-lookup"><span data-stu-id="24679-102">\<UseSmallInternalThreadStacks> Element</span></span>
<span data-ttu-id="24679-103">Fordert an, dass die Common Language Runtime (CLR) die Speicherauslastung reduziert, indem explizite Stapel Größen angegeben werden, wenn bestimmte, intern verwendete Threads erstellt werden, anstatt die Standard Stapelgröße für diese Threads zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="24679-103">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
 <span data-ttu-id="24679-104">\<Configuration >-Element</span><span class="sxs-lookup"><span data-stu-id="24679-104">\<configuration> Element</span></span>  
<span data-ttu-id="24679-105">\<Runtime-> Element</span><span class="sxs-lookup"><span data-stu-id="24679-105">\<runtime> Element</span></span>  
<span data-ttu-id="24679-106">\<Das Element "" ist > Element "" von "".</span><span class="sxs-lookup"><span data-stu-id="24679-106">\<UseSmallInternalThreadStacks> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24679-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="24679-107">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24679-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="24679-108">Attributes and Elements</span></span>  
 <span data-ttu-id="24679-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="24679-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24679-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="24679-110">Attributes</span></span>  
  
|<span data-ttu-id="24679-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="24679-111">Attribute</span></span>|<span data-ttu-id="24679-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24679-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="24679-113">enabled</span><span class="sxs-lookup"><span data-stu-id="24679-113">enabled</span></span>|<span data-ttu-id="24679-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="24679-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="24679-115">Gibt an, ob die CLR explizite Stapel Größen anstelle der Standard Stapelgröße verwenden soll, wenn bestimmte, intern verwendete Threads erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="24679-115">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="24679-116">Die expliziten Stapel Größen sind kleiner als die Standard Stapelgröße von 1 MB.</span><span class="sxs-lookup"><span data-stu-id="24679-116">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="24679-117">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="24679-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="24679-118">Wert</span><span class="sxs-lookup"><span data-stu-id="24679-118">Value</span></span>|<span data-ttu-id="24679-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24679-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="24679-120">true</span><span class="sxs-lookup"><span data-stu-id="24679-120">true</span></span>|<span data-ttu-id="24679-121">Anfordern von expliziten Stapel Größen.</span><span class="sxs-lookup"><span data-stu-id="24679-121">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="24679-122">false</span><span class="sxs-lookup"><span data-stu-id="24679-122">false</span></span>|<span data-ttu-id="24679-123">Verwenden Sie die Standard Stapelgröße.</span><span class="sxs-lookup"><span data-stu-id="24679-123">Use the default stack size.</span></span> <span data-ttu-id="24679-124">Dies ist die Standardeinstellung für die .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="24679-124">This is the default for the .NET Framework 4.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="24679-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="24679-125">Child Elements</span></span>  
 <span data-ttu-id="24679-126">Keine</span><span class="sxs-lookup"><span data-stu-id="24679-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="24679-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="24679-127">Parent Elements</span></span>  
  
|<span data-ttu-id="24679-128">Element</span><span class="sxs-lookup"><span data-stu-id="24679-128">Element</span></span>|<span data-ttu-id="24679-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24679-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="24679-130">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="24679-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="24679-131">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="24679-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24679-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="24679-132">Remarks</span></span>  
 <span data-ttu-id="24679-133">Dieses Konfigurationselement wird verwendet, um eine reduzierte Verwendung des virtuellen Speichers in einem Prozess anzufordern, da die von der CLR für die internen Threads verwendeten expliziten Thread Größen, wenn die Anforderung berücksichtigt wird, kleiner als die Standardgröße sind.</span><span class="sxs-lookup"><span data-stu-id="24679-133">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="24679-134">Bei diesem Konfigurationselement handelt es sich um eine Anforderung an die CLR und nicht um eine absolute Anforderung.</span><span class="sxs-lookup"><span data-stu-id="24679-134">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="24679-135">In der .NET Framework 4 wird die Anforderung nur für die x86-Architektur berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="24679-135">In the .NET Framework 4, the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="24679-136">Dieses Element kann in zukünftigen Versionen der CLR vollständig ignoriert oder durch explizite Stapel Größen ersetzt werden, die immer für ausgewählte interne Threads verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="24679-136">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="24679-137">Wenn Sie dieses Konfigurationselement angeben, wird die Zuverlässigkeit für den geringeren virtuellen Speicher verwendet, wenn die CLR die Anforderung erfüllt, da kleinere Stapel Größen potenziell zu einem Stapelüberlauf führen könnten.</span><span class="sxs-lookup"><span data-stu-id="24679-137">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24679-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="24679-138">Example</span></span>  
 <span data-ttu-id="24679-139">Im folgenden Beispiel wird gezeigt, wie angefordert wird, dass die CLR explizite Stapel Größen für bestimmte Threads verwendet, die intern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="24679-139">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="24679-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24679-140">See also</span></span>

- [<span data-ttu-id="24679-141">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="24679-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="24679-142">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="24679-142">Configuration File Schema</span></span>](../index.md)
