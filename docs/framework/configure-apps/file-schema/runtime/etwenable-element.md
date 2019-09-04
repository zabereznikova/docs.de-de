---
title: <etwEnable>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb4d0ed5b33170c40aacb32bebbf1b59ca659be4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252618"
---
# <a name="etwenable-element"></a><span data-ttu-id="4c3d9-102">\<EtwEnable-> Element</span><span class="sxs-lookup"><span data-stu-id="4c3d9-102">\<etwEnable> Element</span></span>
<span data-ttu-id="4c3d9-103">Gibt an, ob die Ereignisablaufverfolgung für Windows (ETW) für Common Language Runtime-Ereignisse aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="4c3d9-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
<span data-ttu-id="4c3d9-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4c3d9-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4c3d9-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="4c3d9-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="4c3d9-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<etwenabled->**</span><span class="sxs-lookup"><span data-stu-id="4c3d9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<etwEnabled>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c3d9-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c3d9-107">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c3d9-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4c3d9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4c3d9-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4c3d9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c3d9-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="4c3d9-110">Attributes</span></span>  
  
|<span data-ttu-id="4c3d9-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="4c3d9-111">Attribute</span></span>|<span data-ttu-id="4c3d9-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c3d9-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4c3d9-113">enabled</span><span class="sxs-lookup"><span data-stu-id="4c3d9-113">enabled</span></span>|<span data-ttu-id="4c3d9-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="4c3d9-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="4c3d9-115">Gibt an, ob etw aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4c3d9-115">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4c3d9-116">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="4c3d9-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="4c3d9-117">Wert</span><span class="sxs-lookup"><span data-stu-id="4c3d9-117">Value</span></span>|<span data-ttu-id="4c3d9-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c3d9-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4c3d9-119">true</span><span class="sxs-lookup"><span data-stu-id="4c3d9-119">true</span></span>|<span data-ttu-id="4c3d9-120">Etw aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4c3d9-120">Enable ETW.</span></span> <span data-ttu-id="4c3d9-121">Dies ist die Standardeinstellung für Windows-Versionen, die mit den Betriebssystemen Windows Vista und Windows Server 2008 beginnen.</span><span class="sxs-lookup"><span data-stu-id="4c3d9-121">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="4c3d9-122">false</span><span class="sxs-lookup"><span data-stu-id="4c3d9-122">false</span></span>|<span data-ttu-id="4c3d9-123">Deaktivieren Sie etw.</span><span class="sxs-lookup"><span data-stu-id="4c3d9-123">Disable ETW.</span></span> <span data-ttu-id="4c3d9-124">Dies ist die Standardeinstellung für frühere Versionen von Windows.</span><span class="sxs-lookup"><span data-stu-id="4c3d9-124">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c3d9-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4c3d9-125">Child Elements</span></span>  
 <span data-ttu-id="4c3d9-126">Keine</span><span class="sxs-lookup"><span data-stu-id="4c3d9-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4c3d9-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4c3d9-127">Parent Elements</span></span>  
  
|<span data-ttu-id="4c3d9-128">Element</span><span class="sxs-lookup"><span data-stu-id="4c3d9-128">Element</span></span>|<span data-ttu-id="4c3d9-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c3d9-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4c3d9-130">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="4c3d9-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4c3d9-131">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4c3d9-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c3d9-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4c3d9-132">Remarks</span></span>  
 <span data-ttu-id="4c3d9-133">Ab Windows Vista ist etw standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4c3d9-133">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="4c3d9-134">Verwenden Sie dieses Element, um etw für eine Anwendung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4c3d9-134">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="4c3d9-135">In früheren Versionen von Windows verwenden Sie dieses Element, um etw für eine Anwendung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4c3d9-135">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4c3d9-136">Etw kann mithilfe einer Registrierungs Einstellung Global auf einem Server aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="4c3d9-136">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="4c3d9-137">Siehe [Steuern der .NET Framework Protokollierung](../../../performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="4c3d9-137">See [Controlling .NET Framework Logging](../../../performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c3d9-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4c3d9-138">Example</span></span>  
 <span data-ttu-id="4c3d9-139">Im folgenden Beispiel wird gezeigt, wie die ETW-Ablauf Verfolgung für eine Anwendung aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="4c3d9-139">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4c3d9-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c3d9-140">See also</span></span>

- [<span data-ttu-id="4c3d9-141">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="4c3d9-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4c3d9-142">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="4c3d9-142">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="4c3d9-143">Controlling .NET Framework Logging (Steuern der Protokollierung in .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="4c3d9-143">Controlling .NET Framework Logging</span></span>](../../../performance/controlling-logging.md)
