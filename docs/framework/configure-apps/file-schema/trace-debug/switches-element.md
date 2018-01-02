---
title: '&lt;Switches&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches
- http://schemas.microsoft.com/.NetConfiguration/v2.0#switches
helpviewer_keywords:
- <switches> element
- switches element
- trace switches, <switches> element
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 64cf3ba9e5529c4a46b2d5365931a47ad2ab211a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltswitchesgt-element"></a><span data-ttu-id="27c42-102">&lt;Switches&gt; Element</span><span class="sxs-lookup"><span data-stu-id="27c42-102">&lt;switches&gt; Element</span></span>
<span data-ttu-id="27c42-103">Enthält Ablaufverfolgungsschalter und die Ebene, für die diese festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="27c42-103">Contains trace switches and the level where the trace switches are set.</span></span>  
  
 <span data-ttu-id="27c42-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="27c42-104">\<configuration></span></span>  
<span data-ttu-id="27c42-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="27c42-105">\<system.diagnostics></span></span>  
<span data-ttu-id="27c42-106">\<Switches ></span><span class="sxs-lookup"><span data-stu-id="27c42-106">\<switches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27c42-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="27c42-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27c42-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="27c42-108">Attributes and Elements</span></span>  
 <span data-ttu-id="27c42-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="27c42-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27c42-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="27c42-110">Attributes</span></span>  
 <span data-ttu-id="27c42-111">Keine</span><span class="sxs-lookup"><span data-stu-id="27c42-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="27c42-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="27c42-112">Child Elements</span></span>  
  
|<span data-ttu-id="27c42-113">Element</span><span class="sxs-lookup"><span data-stu-id="27c42-113">Element</span></span>|<span data-ttu-id="27c42-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="27c42-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27c42-115">\<add></span><span class="sxs-lookup"><span data-stu-id="27c42-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|<span data-ttu-id="27c42-116">Gibt die Ebene an, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="27c42-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="27c42-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="27c42-117">Parent Elements</span></span>  
  
|<span data-ttu-id="27c42-118">Element</span><span class="sxs-lookup"><span data-stu-id="27c42-118">Element</span></span>|<span data-ttu-id="27c42-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="27c42-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="27c42-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="27c42-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="27c42-121">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="27c42-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27c42-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="27c42-122">Remarks</span></span>  
 <span data-ttu-id="27c42-123">Sie können das Maß an einen Ablaufverfolgungsschalter ändern, indem Sie diese in einer Konfigurationsdatei zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="27c42-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="27c42-124">Wenn der Schalter ist eine <xref:System.Diagnostics.BooleanSwitch>, Sie können Sie aktivieren und deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="27c42-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="27c42-125">Wenn der Schalter ist eine <xref:System.Diagnostics.TraceSwitch>, können Sie verschiedene Ebenen hinzu, um die Typen von Ablaufverfolgung angeben zuweisen oder Debug Nachrichten, die Ausgaben der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="27c42-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27c42-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="27c42-126">Example</span></span>  
 <span data-ttu-id="27c42-127">Das folgende Beispiel zeigt, wie Sie die  **\<wechseln >** festzulegenden Elements der `General` Trace-Schalter, um die <xref:System.Diagnostics.TraceLevel> Ebene, und aktivieren Sie die `Data` booleschen Ablaufverfolgungsschalter.</span><span class="sxs-lookup"><span data-stu-id="27c42-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="27c42-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27c42-128">See Also</span></span>  
 <xref:System.Diagnostics.Switch>  
 <xref:System.Diagnostics.TraceSwitch>  
 <xref:System.Diagnostics.BooleanSwitch>  
 [<span data-ttu-id="27c42-129">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="27c42-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
