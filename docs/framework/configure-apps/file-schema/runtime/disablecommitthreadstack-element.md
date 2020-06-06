---
title: <disableCommitThreadStack>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCommitThreadStack
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCommitThreadStack
helpviewer_keywords:
- <disableCommitThreadStack> element
- disableCommitThreadStack element
ms.assetid: 3559d46a-7640-4c72-9a11-7e980768929e
ms.openlocfilehash: 8aefb8a20d6a95c5b8062d0c03dcb28a3557ca3d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117473"
---
# <a name="disablecommitthreadstack-element"></a><span data-ttu-id="c646a-102">\<disableCommitThreadStack>-Element</span><span class="sxs-lookup"><span data-stu-id="c646a-102">\<disableCommitThreadStack> Element</span></span>
<span data-ttu-id="c646a-103">Gibt an, ob beim Starten eines Threads für den vollständigen Threadstapel ein Commit ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="c646a-103">Specifies whether the full thread stack is committed when a thread is started.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<disableCommitThreadStack>**  
  
## <a name="syntax"></a><span data-ttu-id="c646a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c646a-104">Syntax</span></span>  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c646a-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c646a-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c646a-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c646a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c646a-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="c646a-107">Attributes</span></span>  
  
|<span data-ttu-id="c646a-108">attribute</span><span class="sxs-lookup"><span data-stu-id="c646a-108">Attribute</span></span>|<span data-ttu-id="c646a-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c646a-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c646a-110">enabled</span><span class="sxs-lookup"><span data-stu-id="c646a-110">enabled</span></span>|<span data-ttu-id="c646a-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="c646a-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="c646a-112">Gibt an, ob das Standardverhalten, beim Starten des Threads den gesamten Threadstapel zu commiten, deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="c646a-112">Specifies whether committing the full thread stack on thread startup (the default behavior) is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c646a-113">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="c646a-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="c646a-114">Wert</span><span class="sxs-lookup"><span data-stu-id="c646a-114">Value</span></span>|<span data-ttu-id="c646a-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c646a-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c646a-116">0</span><span class="sxs-lookup"><span data-stu-id="c646a-116">0</span></span>|<span data-ttu-id="c646a-117">Das Standardverhalten der Common Language Runtime, beim Starten eines Threads einen Commit für den vollständigen Threadstapel auszuführen, ist nicht deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c646a-117">Do not disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
|<span data-ttu-id="c646a-118">1</span><span class="sxs-lookup"><span data-stu-id="c646a-118">1</span></span>|<span data-ttu-id="c646a-119">Das Standardverhalten der Common Language Runtime, beim Starten eines Threads einen Commit für den vollständigen Threadstapel auszuführen, ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c646a-119">Disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c646a-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c646a-120">Child Elements</span></span>  
 <span data-ttu-id="c646a-121">Keine</span><span class="sxs-lookup"><span data-stu-id="c646a-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c646a-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c646a-122">Parent Elements</span></span>  
  
|<span data-ttu-id="c646a-123">Element</span><span class="sxs-lookup"><span data-stu-id="c646a-123">Element</span></span>|<span data-ttu-id="c646a-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c646a-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c646a-125">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="c646a-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c646a-126">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c646a-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c646a-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c646a-127">Remarks</span></span>  
 <span data-ttu-id="c646a-128">Das Standardverhalten der Common Language Runtime ist, beim Starten eines Threads einen Commit für den vollständigen Threadstapel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c646a-128">The default behavior of the common language runtime is to commit the full thread stack when a thread is started.</span></span> <span data-ttu-id="c646a-129">Wenn eine große Anzahl von Threads auf einem Server erstellt werden muss, der nur über begrenzten Arbeitsspeicher verfügt, und der Großteil dieser Threads nur sehr wenig Stapelspeicher verwenden wird, ist die Leistung des Servers möglicherweise besser, wenn die Common Language Runtime nicht sofort einen Commit für den vollständigen Threadstapel ausführt, wenn ein Thread gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="c646a-129">If a large number of threads must be created on a server that has limited memory, and most of those threads will use very little stack space, the server might perform better if the common language runtime does not commit the full thread stack immediately when a thread is started.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c646a-130">Nicht verwaltete Hosts können das `STARTUP_DISABLE_COMMITTHREADSTACK` -Startflag in der [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) -Enumeration verwenden, um das gleiche Ergebnis zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="c646a-130">Unmanaged hosts can use the `STARTUP_DISABLE_COMMITTHREADSTACK` startup flag in the [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) enumeration to accomplish the same result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c646a-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c646a-131">Example</span></span>  
 <span data-ttu-id="c646a-132">Das folgende Beispiel zeigt, wie Sie das Standardverhalten der Common Language Runtime deaktivieren, die während des Threadstarts einen Commit für den vollständigen Threadstapel ausführen soll.</span><span class="sxs-lookup"><span data-stu-id="c646a-132">The following example shows how to disable the default behavior of the common language runtime, which is to commit the full thread stack on thread startup.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c646a-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c646a-133">See also</span></span>

- [<span data-ttu-id="c646a-134">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="c646a-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c646a-135">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="c646a-135">Configuration File Schema</span></span>](../index.md)
