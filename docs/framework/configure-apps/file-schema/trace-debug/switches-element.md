---
title: '&lt;Switches&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches
- http://schemas.microsoft.com/.NetConfiguration/v2.0#switches
helpviewer_keywords:
- <switches> element
- switches element
- trace switches, <switches> element
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 7ca375935c1dfcdb406257ece1a9dfd18851dddf
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47113883"
---
# <a name="ltswitchesgt-element"></a><span data-ttu-id="9db44-102">&lt;Switches&gt; Element</span><span class="sxs-lookup"><span data-stu-id="9db44-102">&lt;switches&gt; Element</span></span>
<span data-ttu-id="9db44-103">Enthält Ablaufverfolgungsschalter und die Ebene, für die diese festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="9db44-103">Contains trace switches and the level where the trace switches are set.</span></span>  
  
 <span data-ttu-id="9db44-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9db44-104">\<configuration></span></span>  
<span data-ttu-id="9db44-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="9db44-105">\<system.diagnostics></span></span>  
<span data-ttu-id="9db44-106">\<Switches ></span><span class="sxs-lookup"><span data-stu-id="9db44-106">\<switches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9db44-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="9db44-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9db44-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9db44-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9db44-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9db44-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9db44-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="9db44-110">Attributes</span></span>  
 <span data-ttu-id="9db44-111">Keine</span><span class="sxs-lookup"><span data-stu-id="9db44-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9db44-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9db44-112">Child Elements</span></span>  
  
|<span data-ttu-id="9db44-113">Element</span><span class="sxs-lookup"><span data-stu-id="9db44-113">Element</span></span>|<span data-ttu-id="9db44-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9db44-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9db44-115">\<add></span><span class="sxs-lookup"><span data-stu-id="9db44-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|<span data-ttu-id="9db44-116">Gibt die Ebene an, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9db44-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9db44-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9db44-117">Parent Elements</span></span>  
  
|<span data-ttu-id="9db44-118">Element</span><span class="sxs-lookup"><span data-stu-id="9db44-118">Element</span></span>|<span data-ttu-id="9db44-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9db44-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9db44-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="9db44-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="9db44-121">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9db44-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9db44-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9db44-122">Remarks</span></span>  
 <span data-ttu-id="9db44-123">Sie können die Ebene der einen Ablaufverfolgungsschalter ändern, indem Sie es in einer Konfigurationsdatei platzieren.</span><span class="sxs-lookup"><span data-stu-id="9db44-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="9db44-124">Wenn der Schalter ist eine <xref:System.Diagnostics.BooleanSwitch>, Sie können Sie aktivieren und deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9db44-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="9db44-125">Wenn der Schalter ist eine <xref:System.Diagnostics.TraceSwitch>, können Sie verschiedene Ebenen, um die Typen der Ablaufverfolgung angeben zuweisen oder Debug Nachrichten, die Ausgaben der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9db44-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9db44-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9db44-126">Example</span></span>  
 <span data-ttu-id="9db44-127">Das folgende Beispiel zeigt, wie Sie mit der  **\<wechseln >** festzulegende Element der `General` Trace-Schalter, um die <xref:System.Diagnostics.TraceLevel> Ebene, und aktivieren Sie die `Data` booleschen Ablaufverfolgungsschalter.</span><span class="sxs-lookup"><span data-stu-id="9db44-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9db44-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9db44-128">See Also</span></span>  
 <xref:System.Diagnostics.Switch>  
 <xref:System.Diagnostics.TraceSwitch>  
 <xref:System.Diagnostics.BooleanSwitch>  
 [<span data-ttu-id="9db44-129">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="9db44-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
