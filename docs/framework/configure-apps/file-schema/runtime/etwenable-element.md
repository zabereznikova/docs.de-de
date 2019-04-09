---
title: <etwEnable> Element
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ba411114bfb853e06c83adb42713d43f1452d9c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135069"
---
# <a name="etwenable-element"></a><span data-ttu-id="c6a9c-102">\<EtwEnable >-Element</span><span class="sxs-lookup"><span data-stu-id="c6a9c-102">\<etwEnable> Element</span></span>
<span data-ttu-id="c6a9c-103">Gibt an, ob die Ereignisablaufverfolgung für Windows (ETW) für Common Language Runtime-Ereignisse aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="c6a9c-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
 <span data-ttu-id="c6a9c-104">\<Configuration >-Element</span><span class="sxs-lookup"><span data-stu-id="c6a9c-104">\<configuration> Element</span></span>  
<span data-ttu-id="c6a9c-105">\<Common Language Runtime >-Element</span><span class="sxs-lookup"><span data-stu-id="c6a9c-105">\<runtime> Element</span></span>  
<span data-ttu-id="c6a9c-106">\<etwEnabled></span><span class="sxs-lookup"><span data-stu-id="c6a9c-106">\<etwEnabled></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6a9c-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6a9c-107">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6a9c-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c6a9c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c6a9c-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c6a9c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6a9c-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="c6a9c-110">Attributes</span></span>  
  
|<span data-ttu-id="c6a9c-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="c6a9c-111">Attribute</span></span>|<span data-ttu-id="c6a9c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c6a9c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c6a9c-113">enabled</span><span class="sxs-lookup"><span data-stu-id="c6a9c-113">enabled</span></span>|<span data-ttu-id="c6a9c-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="c6a9c-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="c6a9c-115">Gibt an, ob es sich bei ETW aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c6a9c-115">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c6a9c-116">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="c6a9c-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="c6a9c-117">Wert</span><span class="sxs-lookup"><span data-stu-id="c6a9c-117">Value</span></span>|<span data-ttu-id="c6a9c-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c6a9c-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c6a9c-119">true</span><span class="sxs-lookup"><span data-stu-id="c6a9c-119">true</span></span>|<span data-ttu-id="c6a9c-120">Aktivieren Sie ETW.</span><span class="sxs-lookup"><span data-stu-id="c6a9c-120">Enable ETW.</span></span> <span data-ttu-id="c6a9c-121">Dies ist die Standardeinstellung für Versionen von Windows ab Windows Vista und Windows Server 2008-Betriebssysteme.</span><span class="sxs-lookup"><span data-stu-id="c6a9c-121">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="c6a9c-122">False</span><span class="sxs-lookup"><span data-stu-id="c6a9c-122">false</span></span>|<span data-ttu-id="c6a9c-123">Deaktivieren Sie ETW.</span><span class="sxs-lookup"><span data-stu-id="c6a9c-123">Disable ETW.</span></span> <span data-ttu-id="c6a9c-124">Dies ist die Standardeinstellung für frühere Versionen von Windows.</span><span class="sxs-lookup"><span data-stu-id="c6a9c-124">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c6a9c-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c6a9c-125">Child Elements</span></span>  
 <span data-ttu-id="c6a9c-126">Keine</span><span class="sxs-lookup"><span data-stu-id="c6a9c-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c6a9c-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c6a9c-127">Parent Elements</span></span>  
  
|<span data-ttu-id="c6a9c-128">Element</span><span class="sxs-lookup"><span data-stu-id="c6a9c-128">Element</span></span>|<span data-ttu-id="c6a9c-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c6a9c-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c6a9c-130">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="c6a9c-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c6a9c-131">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c6a9c-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6a9c-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c6a9c-132">Remarks</span></span>  
 <span data-ttu-id="c6a9c-133">Ab Windows Vista ist ETW standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c6a9c-133">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="c6a9c-134">Verwenden Sie dieses Element, um ETW für eine Anwendung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c6a9c-134">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="c6a9c-135">Verwenden Sie dieses Element in früheren Versionen von Windows ETW für eine Anwendung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c6a9c-135">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6a9c-136">ETW kann aktiviert oder deaktiviert global auf einem Server mit einer registrierungseinstellung.</span><span class="sxs-lookup"><span data-stu-id="c6a9c-136">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="c6a9c-137">Finden Sie unter [Steuern der Protokollierung in .NET Framework](../../../../../docs/framework/performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="c6a9c-137">See [Controlling .NET Framework Logging](../../../../../docs/framework/performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6a9c-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c6a9c-138">Example</span></span>  
 <span data-ttu-id="c6a9c-139">Das folgende Beispiel zeigt, wie die ETW-Ablaufverfolgung für eine Anwendung aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="c6a9c-139">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6a9c-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6a9c-140">See also</span></span>

- [<span data-ttu-id="c6a9c-141">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="c6a9c-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="c6a9c-142">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="c6a9c-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="c6a9c-143">Steuern der Protokollierung in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c6a9c-143">Controlling .NET Framework Logging</span></span>](../../../../../docs/framework/performance/controlling-logging.md)
