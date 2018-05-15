---
title: '&lt;Hinzufügen&gt; -Element für &lt;Switches&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e0dc425327f6577606e1205a23fdaffcc39f6e01
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-element-for-ltswitchesgt"></a><span data-ttu-id="42940-102">&lt;Hinzufügen&gt; -Element für &lt;Switches&gt;</span><span class="sxs-lookup"><span data-stu-id="42940-102">&lt;add&gt; Element for &lt;switches&gt;</span></span>
<span data-ttu-id="42940-103">Gibt die Ebene an, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="42940-103">Specifies the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="42940-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="42940-104">\<configuration></span></span>  
<span data-ttu-id="42940-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="42940-105">\<system.diagnostics></span></span>  
<span data-ttu-id="42940-106">\<Switches ></span><span class="sxs-lookup"><span data-stu-id="42940-106">\<switches></span></span>  
<span data-ttu-id="42940-107">\<add></span><span class="sxs-lookup"><span data-stu-id="42940-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42940-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="42940-108">Syntax</span></span>  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42940-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="42940-109">Attributes and Elements</span></span>  
 <span data-ttu-id="42940-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="42940-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42940-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="42940-111">Attributes</span></span>  
  
|<span data-ttu-id="42940-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="42940-112">Attribute</span></span>|<span data-ttu-id="42940-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42940-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42940-114">**name**</span><span class="sxs-lookup"><span data-stu-id="42940-114">**name**</span></span>|<span data-ttu-id="42940-115">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="42940-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="42940-116">Gibt den Namen des Schalters.</span><span class="sxs-lookup"><span data-stu-id="42940-116">Specifies the name of the switch.</span></span> <span data-ttu-id="42940-117">Der Wert dieses Attributs entspricht dem *DisplayName* Parameter, der übergeben wird, um den Konstruktor zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="42940-117">The value of this attribute corresponds to the *displayName* parameter that is passed to switch constructor.</span></span>|  
|<span data-ttu-id="42940-118">**value**</span><span class="sxs-lookup"><span data-stu-id="42940-118">**value**</span></span>|<span data-ttu-id="42940-119">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="42940-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="42940-120">Gibt die Ebene des Schalters.</span><span class="sxs-lookup"><span data-stu-id="42940-120">Specifies the level of the switch.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42940-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="42940-121">Child Elements</span></span>  
 <span data-ttu-id="42940-122">Keine</span><span class="sxs-lookup"><span data-stu-id="42940-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="42940-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="42940-123">Parent Elements</span></span>  
  
|<span data-ttu-id="42940-124">Element</span><span class="sxs-lookup"><span data-stu-id="42940-124">Element</span></span>|<span data-ttu-id="42940-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42940-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="42940-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="42940-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`switches`|<span data-ttu-id="42940-127">Enthält Ablaufverfolgungsschalter und die Ebene, für die diese festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="42940-127">Contains trace switches and the level where the trace switches are set.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="42940-128">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="42940-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42940-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="42940-129">Remarks</span></span>  
 <span data-ttu-id="42940-130">Sie können das Maß an einen Ablaufverfolgungsschalter ändern, indem Sie diese in einer Konfigurationsdatei zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="42940-130">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="42940-131">Wenn der Schalter ist eine <xref:System.Diagnostics.BooleanSwitch>, Sie können Sie aktivieren und deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="42940-131">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="42940-132">Wenn der Schalter ist eine <xref:System.Diagnostics.TraceSwitch>, können Sie verschiedene Ebenen hinzu, um die Typen von Ablaufverfolgung angeben zuweisen oder Debug Nachrichten, die Ausgaben der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="42940-132">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42940-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="42940-133">Example</span></span>  
 <span data-ttu-id="42940-134">Das folgende Beispiel zeigt, wie Sie die  **\<hinzufügen >** festzulegenden Elements der `General` Trace-Schalter, um die <xref:System.Diagnostics.TraceLevel> Ebene, und aktivieren Sie die `Data` booleschen Ablaufverfolgungsschalter.</span><span class="sxs-lookup"><span data-stu-id="42940-134">The following example shows how to use the **\<add>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="42940-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42940-135">See Also</span></span>  
 <xref:System.Diagnostics.Switch>  
 <xref:System.Diagnostics.TraceSwitch>  
 <xref:System.Diagnostics.BooleanSwitch>  
 [<span data-ttu-id="42940-136">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="42940-136">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
