---
title: <etwEnable>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
ms.openlocfilehash: 14cea171a4a25e148ea32f75a8ef09b83a4ec8ad
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117395"
---
# <a name="etwenable-element"></a><span data-ttu-id="44122-102">\<etwEnable>-Element</span><span class="sxs-lookup"><span data-stu-id="44122-102">\<etwEnable> Element</span></span>
<span data-ttu-id="44122-103">Gibt an, ob die Ereignisablaufverfolgung für Windows (ETW) für Common Language Runtime-Ereignisse aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="44122-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<etwEnabled>**  
  
## <a name="syntax"></a><span data-ttu-id="44122-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="44122-104">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44122-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="44122-105">Attributes and Elements</span></span>  
 <span data-ttu-id="44122-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="44122-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44122-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="44122-107">Attributes</span></span>  
  
|<span data-ttu-id="44122-108">attribute</span><span class="sxs-lookup"><span data-stu-id="44122-108">Attribute</span></span>|<span data-ttu-id="44122-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="44122-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="44122-110">enabled</span><span class="sxs-lookup"><span data-stu-id="44122-110">enabled</span></span>|<span data-ttu-id="44122-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="44122-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="44122-112">Gibt an, ob etw aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="44122-112">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="44122-113">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="44122-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="44122-114">Wert</span><span class="sxs-lookup"><span data-stu-id="44122-114">Value</span></span>|<span data-ttu-id="44122-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="44122-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="44122-116">true</span><span class="sxs-lookup"><span data-stu-id="44122-116">true</span></span>|<span data-ttu-id="44122-117">Etw aktivieren.</span><span class="sxs-lookup"><span data-stu-id="44122-117">Enable ETW.</span></span> <span data-ttu-id="44122-118">Dies ist die Standardeinstellung für Windows-Versionen, die mit den Betriebssystemen Windows Vista und Windows Server 2008 beginnen.</span><span class="sxs-lookup"><span data-stu-id="44122-118">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="44122-119">false</span><span class="sxs-lookup"><span data-stu-id="44122-119">false</span></span>|<span data-ttu-id="44122-120">Deaktivieren Sie etw.</span><span class="sxs-lookup"><span data-stu-id="44122-120">Disable ETW.</span></span> <span data-ttu-id="44122-121">Dies ist die Standardeinstellung für frühere Versionen von Windows.</span><span class="sxs-lookup"><span data-stu-id="44122-121">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44122-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="44122-122">Child Elements</span></span>  
 <span data-ttu-id="44122-123">Keine</span><span class="sxs-lookup"><span data-stu-id="44122-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="44122-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="44122-124">Parent Elements</span></span>  
  
|<span data-ttu-id="44122-125">Element</span><span class="sxs-lookup"><span data-stu-id="44122-125">Element</span></span>|<span data-ttu-id="44122-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="44122-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="44122-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="44122-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="44122-128">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="44122-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44122-129">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="44122-129">Remarks</span></span>  
 <span data-ttu-id="44122-130">Ab Windows Vista ist etw standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="44122-130">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="44122-131">Verwenden Sie dieses Element, um etw für eine Anwendung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="44122-131">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="44122-132">In früheren Versionen von Windows verwenden Sie dieses Element, um etw für eine Anwendung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="44122-132">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="44122-133">Etw kann mithilfe einer Registrierungs Einstellung Global auf einem Server aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="44122-133">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="44122-134">Siehe [Steuern der .NET Framework Protokollierung](../../../performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="44122-134">See [Controlling .NET Framework Logging](../../../performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="44122-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="44122-135">Example</span></span>  
 <span data-ttu-id="44122-136">Im folgenden Beispiel wird gezeigt, wie die ETW-Ablauf Verfolgung für eine Anwendung aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="44122-136">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="44122-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="44122-137">See also</span></span>

- [<span data-ttu-id="44122-138">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="44122-138">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="44122-139">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="44122-139">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="44122-140">Steuern der Protokollierung in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="44122-140">Controlling .NET Framework Logging</span></span>](../../../performance/controlling-logging.md)
