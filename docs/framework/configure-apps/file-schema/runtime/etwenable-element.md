---
title: <etwEnable>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ba411114bfb853e06c83adb42713d43f1452d9c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704803"
---
# <a name="etwenable-element"></a><span data-ttu-id="dabaa-102">\<EtwEnable >-Element</span><span class="sxs-lookup"><span data-stu-id="dabaa-102">\<etwEnable> Element</span></span>
<span data-ttu-id="dabaa-103">Gibt an, ob die Ereignisablaufverfolgung für Windows (ETW) für Common Language Runtime-Ereignisse aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="dabaa-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
 <span data-ttu-id="dabaa-104">\<Configuration >-Element</span><span class="sxs-lookup"><span data-stu-id="dabaa-104">\<configuration> Element</span></span>  
<span data-ttu-id="dabaa-105">\<Common Language Runtime >-Element</span><span class="sxs-lookup"><span data-stu-id="dabaa-105">\<runtime> Element</span></span>  
<span data-ttu-id="dabaa-106">\<etwEnabled></span><span class="sxs-lookup"><span data-stu-id="dabaa-106">\<etwEnabled></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dabaa-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="dabaa-107">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dabaa-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dabaa-108">Attributes and Elements</span></span>  
 <span data-ttu-id="dabaa-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dabaa-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dabaa-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="dabaa-110">Attributes</span></span>  
  
|<span data-ttu-id="dabaa-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="dabaa-111">Attribute</span></span>|<span data-ttu-id="dabaa-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dabaa-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dabaa-113">enabled</span><span class="sxs-lookup"><span data-stu-id="dabaa-113">enabled</span></span>|<span data-ttu-id="dabaa-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="dabaa-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="dabaa-115">Gibt an, ob es sich bei ETW aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="dabaa-115">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="dabaa-116">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="dabaa-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="dabaa-117">Wert</span><span class="sxs-lookup"><span data-stu-id="dabaa-117">Value</span></span>|<span data-ttu-id="dabaa-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dabaa-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dabaa-119">true</span><span class="sxs-lookup"><span data-stu-id="dabaa-119">true</span></span>|<span data-ttu-id="dabaa-120">Aktivieren Sie ETW.</span><span class="sxs-lookup"><span data-stu-id="dabaa-120">Enable ETW.</span></span> <span data-ttu-id="dabaa-121">Dies ist die Standardeinstellung für Versionen von Windows ab Windows Vista und Windows Server 2008-Betriebssysteme.</span><span class="sxs-lookup"><span data-stu-id="dabaa-121">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="dabaa-122">False</span><span class="sxs-lookup"><span data-stu-id="dabaa-122">false</span></span>|<span data-ttu-id="dabaa-123">Deaktivieren Sie ETW.</span><span class="sxs-lookup"><span data-stu-id="dabaa-123">Disable ETW.</span></span> <span data-ttu-id="dabaa-124">Dies ist die Standardeinstellung für frühere Versionen von Windows.</span><span class="sxs-lookup"><span data-stu-id="dabaa-124">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dabaa-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dabaa-125">Child Elements</span></span>  
 <span data-ttu-id="dabaa-126">Keine</span><span class="sxs-lookup"><span data-stu-id="dabaa-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dabaa-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dabaa-127">Parent Elements</span></span>  
  
|<span data-ttu-id="dabaa-128">Element</span><span class="sxs-lookup"><span data-stu-id="dabaa-128">Element</span></span>|<span data-ttu-id="dabaa-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dabaa-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="dabaa-130">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="dabaa-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="dabaa-131">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="dabaa-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dabaa-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dabaa-132">Remarks</span></span>  
 <span data-ttu-id="dabaa-133">Ab Windows Vista ist ETW standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="dabaa-133">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="dabaa-134">Verwenden Sie dieses Element, um ETW für eine Anwendung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="dabaa-134">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="dabaa-135">Verwenden Sie dieses Element in früheren Versionen von Windows ETW für eine Anwendung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="dabaa-135">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dabaa-136">ETW kann aktiviert oder deaktiviert global auf einem Server mit einer registrierungseinstellung.</span><span class="sxs-lookup"><span data-stu-id="dabaa-136">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="dabaa-137">Finden Sie unter [Steuern der Protokollierung in .NET Framework](../../../../../docs/framework/performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="dabaa-137">See [Controlling .NET Framework Logging](../../../../../docs/framework/performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dabaa-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dabaa-138">Example</span></span>  
 <span data-ttu-id="dabaa-139">Das folgende Beispiel zeigt, wie die ETW-Ablaufverfolgung für eine Anwendung aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="dabaa-139">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dabaa-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dabaa-140">See also</span></span>

- [<span data-ttu-id="dabaa-141">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="dabaa-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="dabaa-142">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="dabaa-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="dabaa-143">Controlling .NET Framework Logging (Steuern der Protokollierung in .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="dabaa-143">Controlling .NET Framework Logging</span></span>](../../../../../docs/framework/performance/controlling-logging.md)
