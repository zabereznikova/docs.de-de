---
title: <gcServer>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
ms.openlocfilehash: 98ecc7069df20a92492e9a6276a0d88331ccc0bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116669"
---
# <a name="gcserver-element"></a><span data-ttu-id="fca6b-102">\<gcserver >-Element</span><span class="sxs-lookup"><span data-stu-id="fca6b-102">\<gcServer> Element</span></span>
<span data-ttu-id="fca6b-103">Gibt an, ob die Common Language Runtime die Garbage Collection auf dem Server ausführt.</span><span class="sxs-lookup"><span data-stu-id="fca6b-103">Specifies whether the common language runtime runs server garbage collection.</span></span>  
  
<span data-ttu-id="fca6b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fca6b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fca6b-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="fca6b-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="fca6b-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<gcserver >**</span><span class="sxs-lookup"><span data-stu-id="fca6b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<gcServer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fca6b-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="fca6b-107">Syntax</span></span>  
  
```xml  
<gcServer    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fca6b-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fca6b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fca6b-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fca6b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fca6b-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="fca6b-110">Attributes</span></span>  
  
|<span data-ttu-id="fca6b-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="fca6b-111">Attribute</span></span>|<span data-ttu-id="fca6b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fca6b-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="fca6b-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="fca6b-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="fca6b-114">Gibt an, ob die Runtime die Garbage Collection auf dem Server ausführt.</span><span class="sxs-lookup"><span data-stu-id="fca6b-114">Specifies whether the runtime runs server garbage collection.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="fca6b-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="fca6b-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="fca6b-116">Wert</span><span class="sxs-lookup"><span data-stu-id="fca6b-116">Value</span></span>|<span data-ttu-id="fca6b-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fca6b-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="fca6b-118">Die Garbage Collection wird nicht auf dem Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fca6b-118">Does not run server garbage collection.</span></span> <span data-ttu-id="fca6b-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="fca6b-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="fca6b-120">Die Garbage Collection wird auf dem Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fca6b-120">Runs server garbage collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fca6b-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fca6b-121">Child Elements</span></span>  
 <span data-ttu-id="fca6b-122">Keine</span><span class="sxs-lookup"><span data-stu-id="fca6b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fca6b-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fca6b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="fca6b-124">Element</span><span class="sxs-lookup"><span data-stu-id="fca6b-124">Element</span></span>|<span data-ttu-id="fca6b-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fca6b-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fca6b-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="fca6b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="fca6b-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="fca6b-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fca6b-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fca6b-128">Remarks</span></span>  
 <span data-ttu-id="fca6b-129">Die Common Language Runtime (CLR) unterstützt zwei Arten der Garbage Collection: die Garbage Collection auf der Arbeitsstation, die auf allen Systemen verfügbar ist, und die Garbage Collection auf dem Server, die auf Systemen mit mehreren Prozessoren verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="fca6b-129">The common language runtime (CLR) supports two types of garbage collection: workstation garbage collection, which is available on all systems, and server garbage collection, which is available on multiprocessor systems.</span></span> <span data-ttu-id="fca6b-130">Mit dem `<gcServer>`-Element steuern Sie die Art der von der CLR ausgeführten Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="fca6b-130">You use the `<gcServer>` element to control the type of garbage collection the CLR performs.</span></span> <span data-ttu-id="fca6b-131">Mithilfe der <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>-Eigenschaft können Sie bestimmen, ob die Garbage Collection auf dem Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="fca6b-131">Use the <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> property to determine if server garbage collection is enabled.</span></span>  
  
 <span data-ttu-id="fca6b-132">Für Computer mit einem Prozessor stellt die Garbage Collection auf der Arbeitsstation (Standardeinstellung) in der Regel die schnellste Lösung dar.</span><span class="sxs-lookup"><span data-stu-id="fca6b-132">For single-processor computers, the default workstation garbage collection should be the fastest option.</span></span> <span data-ttu-id="fca6b-133">Auf Computern mit zwei Prozessoren kann die Arbeitsstation- oder die Serveroption verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fca6b-133">Either workstation or server can be used for two-processor computers.</span></span> <span data-ttu-id="fca6b-134">Sind mehr als zwei Prozessoren vorhanden, stellt die Garbage Collection auf dem Server in der Regel die schnellste Lösung dar.</span><span class="sxs-lookup"><span data-stu-id="fca6b-134">Server garbage collection should be the fastest option for more than two processors.</span></span>  
  
 <span data-ttu-id="fca6b-135">Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden. Wenn es in der Computerkonfigurationsdatei enthalten ist, wird es ignoriert.</span><span class="sxs-lookup"><span data-stu-id="fca6b-135">This element can be used only in the application configuration file; it is ignored if it is in the machine configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fca6b-136">In .NET Framework 4 und früheren Versionen ist die gleichzeitige Garbage Collection nicht verfügbar, wenn die Garbage Collection auf dem Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="fca6b-136">In the .NET Framework 4 and earlier versions, concurrent garbage collection is not available when server garbage collection is enabled.</span></span> <span data-ttu-id="fca6b-137">Beginnend mit dem .NET Framework 4,5 ist der Server Garbage Collection gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="fca6b-137">Starting with the .NET Framework 4.5, server garbage collection is concurrent.</span></span> <span data-ttu-id="fca6b-138">Um nicht gleichzeitige Server Garbage Collection zu verwenden, legen Sie das `<gcServer>`-Element auf `true` und das [\<gcConcurrent-> Element](gcconcurrent-element.md) auf `false`fest.</span><span class="sxs-lookup"><span data-stu-id="fca6b-138">To use non-concurrent server garbage collection, set the `<gcServer>` element to `true` and the [\<gcConcurrent> element](gcconcurrent-element.md) to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fca6b-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fca6b-139">Example</span></span>  
 <span data-ttu-id="fca6b-140">Im folgenden Beispiel wird die Garbage Collection auf dem Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="fca6b-140">The following example enables server garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fca6b-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fca6b-141">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="fca6b-142">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="fca6b-142">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="fca6b-143">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="fca6b-143">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="fca6b-144">So deaktivieren Sie die parallele Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="fca6b-144">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
