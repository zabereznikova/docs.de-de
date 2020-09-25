---
title: <UseSmallInternalThreadStacks>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
ms.openlocfilehash: 4917b47e9e8196eabe691f74531d12308ef80311
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91174081"
---
# <a name="usesmallinternalthreadstacks-element"></a><span data-ttu-id="da69f-102">\<UseSmallInternalThreadStacks>-Element</span><span class="sxs-lookup"><span data-stu-id="da69f-102">\<UseSmallInternalThreadStacks> Element</span></span>

<span data-ttu-id="da69f-103">Fordert an, dass die Common Language Runtime (CLR) die Speicherauslastung reduziert, indem explizite Stapel Größen angegeben werden, wenn bestimmte, intern verwendete Threads erstellt werden, anstatt die Standard Stapelgröße für diese Threads zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="da69f-103">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<UseSmallInternalThreadStacks>**  
  
## <a name="syntax"></a><span data-ttu-id="da69f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="da69f-104">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da69f-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="da69f-105">Attributes and Elements</span></span>  

 <span data-ttu-id="da69f-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="da69f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da69f-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="da69f-107">Attributes</span></span>  
  
|<span data-ttu-id="da69f-108">attribute</span><span class="sxs-lookup"><span data-stu-id="da69f-108">Attribute</span></span>|<span data-ttu-id="da69f-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="da69f-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="da69f-110">enabled</span><span class="sxs-lookup"><span data-stu-id="da69f-110">enabled</span></span>|<span data-ttu-id="da69f-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="da69f-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="da69f-112">Gibt an, ob die CLR explizite Stapel Größen anstelle der Standard Stapelgröße verwenden soll, wenn bestimmte, intern verwendete Threads erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="da69f-112">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="da69f-113">Die expliziten Stapel Größen sind kleiner als die Standard Stapelgröße von 1 MB.</span><span class="sxs-lookup"><span data-stu-id="da69f-113">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="da69f-114">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="da69f-114">enabled Attribute</span></span>  
  
|<span data-ttu-id="da69f-115">Wert</span><span class="sxs-lookup"><span data-stu-id="da69f-115">Value</span></span>|<span data-ttu-id="da69f-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="da69f-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="da69f-117">true</span><span class="sxs-lookup"><span data-stu-id="da69f-117">true</span></span>|<span data-ttu-id="da69f-118">Anfordern von expliziten Stapel Größen.</span><span class="sxs-lookup"><span data-stu-id="da69f-118">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="da69f-119">false</span><span class="sxs-lookup"><span data-stu-id="da69f-119">false</span></span>|<span data-ttu-id="da69f-120">Verwenden Sie die Standard Stapelgröße.</span><span class="sxs-lookup"><span data-stu-id="da69f-120">Use the default stack size.</span></span> <span data-ttu-id="da69f-121">Dies ist die Standardeinstellung für die .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="da69f-121">This is the default for the .NET Framework 4.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da69f-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="da69f-122">Child Elements</span></span>  

 <span data-ttu-id="da69f-123">Keine</span><span class="sxs-lookup"><span data-stu-id="da69f-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="da69f-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="da69f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="da69f-125">Element</span><span class="sxs-lookup"><span data-stu-id="da69f-125">Element</span></span>|<span data-ttu-id="da69f-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="da69f-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="da69f-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="da69f-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="da69f-128">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="da69f-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da69f-129">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="da69f-129">Remarks</span></span>  

 <span data-ttu-id="da69f-130">Dieses Konfigurationselement wird verwendet, um eine reduzierte Verwendung des virtuellen Speichers in einem Prozess anzufordern, da die von der CLR für die internen Threads verwendeten expliziten Thread Größen, wenn die Anforderung berücksichtigt wird, kleiner als die Standardgröße sind.</span><span class="sxs-lookup"><span data-stu-id="da69f-130">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="da69f-131">Bei diesem Konfigurationselement handelt es sich um eine Anforderung an die CLR und nicht um eine absolute Anforderung.</span><span class="sxs-lookup"><span data-stu-id="da69f-131">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="da69f-132">In der .NET Framework 4 wird die Anforderung nur für die x86-Architektur berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="da69f-132">In the .NET Framework 4, the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="da69f-133">Dieses Element kann in zukünftigen Versionen der CLR vollständig ignoriert oder durch explizite Stapel Größen ersetzt werden, die immer für ausgewählte interne Threads verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="da69f-133">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="da69f-134">Wenn Sie dieses Konfigurationselement angeben, wird die Zuverlässigkeit für den geringeren virtuellen Speicher verwendet, wenn die CLR die Anforderung erfüllt, da kleinere Stapel Größen potenziell zu einem Stapelüberlauf führen könnten.</span><span class="sxs-lookup"><span data-stu-id="da69f-134">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da69f-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="da69f-135">Example</span></span>  

 <span data-ttu-id="da69f-136">Im folgenden Beispiel wird gezeigt, wie angefordert wird, dass die CLR explizite Stapel Größen für bestimmte Threads verwendet, die intern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="da69f-136">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="da69f-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="da69f-137">See also</span></span>

- [<span data-ttu-id="da69f-138">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="da69f-138">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="da69f-139">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="da69f-139">Configuration File Schema</span></span>](../index.md)
