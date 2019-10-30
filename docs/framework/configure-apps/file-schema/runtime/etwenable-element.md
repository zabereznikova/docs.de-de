---
title: <etwEnable>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
ms.openlocfilehash: 14cea171a4a25e148ea32f75a8ef09b83a4ec8ad
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73117395"
---
# <a name="etwenable-element"></a><span data-ttu-id="cfb49-102">\<EtwEnable-> Element</span><span class="sxs-lookup"><span data-stu-id="cfb49-102">\<etwEnable> Element</span></span>
<span data-ttu-id="cfb49-103">Gibt an, ob die Ereignisablaufverfolgung für Windows (ETW) für Common Language Runtime-Ereignisse aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="cfb49-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
<span data-ttu-id="cfb49-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cfb49-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cfb49-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="cfb49-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="cfb49-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<etwenabled >**</span><span class="sxs-lookup"><span data-stu-id="cfb49-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<etwEnabled>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfb49-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="cfb49-107">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cfb49-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cfb49-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cfb49-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cfb49-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cfb49-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="cfb49-110">Attributes</span></span>  
  
|<span data-ttu-id="cfb49-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="cfb49-111">Attribute</span></span>|<span data-ttu-id="cfb49-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cfb49-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cfb49-113">enabled</span><span class="sxs-lookup"><span data-stu-id="cfb49-113">enabled</span></span>|<span data-ttu-id="cfb49-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="cfb49-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="cfb49-115">Gibt an, ob etw aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="cfb49-115">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="cfb49-116">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="cfb49-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="cfb49-117">Wert</span><span class="sxs-lookup"><span data-stu-id="cfb49-117">Value</span></span>|<span data-ttu-id="cfb49-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cfb49-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cfb49-119">true</span><span class="sxs-lookup"><span data-stu-id="cfb49-119">true</span></span>|<span data-ttu-id="cfb49-120">Etw aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cfb49-120">Enable ETW.</span></span> <span data-ttu-id="cfb49-121">Dies ist die Standardeinstellung für Windows-Versionen, die mit den Betriebssystemen Windows Vista und Windows Server 2008 beginnen.</span><span class="sxs-lookup"><span data-stu-id="cfb49-121">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="cfb49-122">False</span><span class="sxs-lookup"><span data-stu-id="cfb49-122">false</span></span>|<span data-ttu-id="cfb49-123">Deaktivieren Sie etw.</span><span class="sxs-lookup"><span data-stu-id="cfb49-123">Disable ETW.</span></span> <span data-ttu-id="cfb49-124">Dies ist die Standardeinstellung für frühere Versionen von Windows.</span><span class="sxs-lookup"><span data-stu-id="cfb49-124">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cfb49-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cfb49-125">Child Elements</span></span>  
 <span data-ttu-id="cfb49-126">Keine</span><span class="sxs-lookup"><span data-stu-id="cfb49-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cfb49-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cfb49-127">Parent Elements</span></span>  
  
|<span data-ttu-id="cfb49-128">Element</span><span class="sxs-lookup"><span data-stu-id="cfb49-128">Element</span></span>|<span data-ttu-id="cfb49-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cfb49-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="cfb49-130">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="cfb49-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="cfb49-131">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="cfb49-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfb49-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cfb49-132">Remarks</span></span>  
 <span data-ttu-id="cfb49-133">Ab Windows Vista ist etw standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="cfb49-133">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="cfb49-134">Verwenden Sie dieses Element, um etw für eine Anwendung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="cfb49-134">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="cfb49-135">In früheren Versionen von Windows verwenden Sie dieses Element, um etw für eine Anwendung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cfb49-135">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cfb49-136">Etw kann mithilfe einer Registrierungs Einstellung Global auf einem Server aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="cfb49-136">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="cfb49-137">Siehe [Steuern der .NET Framework Protokollierung](../../../performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="cfb49-137">See [Controlling .NET Framework Logging](../../../performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfb49-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cfb49-138">Example</span></span>  
 <span data-ttu-id="cfb49-139">Im folgenden Beispiel wird gezeigt, wie die ETW-Ablauf Verfolgung für eine Anwendung aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="cfb49-139">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cfb49-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cfb49-140">See also</span></span>

- [<span data-ttu-id="cfb49-141">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="cfb49-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="cfb49-142">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="cfb49-142">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="cfb49-143">Controlling .NET Framework Logging (Steuern der Protokollierung in .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="cfb49-143">Controlling .NET Framework Logging</span></span>](../../../performance/controlling-logging.md)
