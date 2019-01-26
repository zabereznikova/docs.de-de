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
ms.openlocfilehash: ed5d30408b2c0f45f3bef091f4828bd812a63a7a
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083352"
---
# <a name="ltswitchesgt-element"></a><span data-ttu-id="ddb5a-102">&lt;Switches&gt; Element</span><span class="sxs-lookup"><span data-stu-id="ddb5a-102">&lt;switches&gt; Element</span></span>
<span data-ttu-id="ddb5a-103">Enthält Ablaufverfolgungsschalter und die Ebene, für die diese festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="ddb5a-103">Contains trace switches and the level where the trace switches are set.</span></span>  
  
 <span data-ttu-id="ddb5a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ddb5a-104">\<configuration></span></span>  
<span data-ttu-id="ddb5a-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="ddb5a-105">\<system.diagnostics></span></span>  
<span data-ttu-id="ddb5a-106">\<switches></span><span class="sxs-lookup"><span data-stu-id="ddb5a-106">\<switches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddb5a-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ddb5a-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ddb5a-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ddb5a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ddb5a-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ddb5a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ddb5a-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="ddb5a-110">Attributes</span></span>  
 <span data-ttu-id="ddb5a-111">Keine</span><span class="sxs-lookup"><span data-stu-id="ddb5a-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ddb5a-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ddb5a-112">Child Elements</span></span>  
  
|<span data-ttu-id="ddb5a-113">Element</span><span class="sxs-lookup"><span data-stu-id="ddb5a-113">Element</span></span>|<span data-ttu-id="ddb5a-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ddb5a-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ddb5a-115">\<add></span><span class="sxs-lookup"><span data-stu-id="ddb5a-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|<span data-ttu-id="ddb5a-116">Gibt die Ebene an, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ddb5a-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ddb5a-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ddb5a-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ddb5a-118">Element</span><span class="sxs-lookup"><span data-stu-id="ddb5a-118">Element</span></span>|<span data-ttu-id="ddb5a-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ddb5a-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ddb5a-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ddb5a-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="ddb5a-121">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ddb5a-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ddb5a-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ddb5a-122">Remarks</span></span>  
 <span data-ttu-id="ddb5a-123">Sie können die Ebene der einen Ablaufverfolgungsschalter ändern, indem Sie es in einer Konfigurationsdatei platzieren.</span><span class="sxs-lookup"><span data-stu-id="ddb5a-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="ddb5a-124">Wenn der Schalter ist eine <xref:System.Diagnostics.BooleanSwitch>, Sie können Sie aktivieren und deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ddb5a-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="ddb5a-125">Wenn der Schalter ist eine <xref:System.Diagnostics.TraceSwitch>, können Sie verschiedene Ebenen, um die Typen der Ablaufverfolgung angeben zuweisen oder Debug Nachrichten, die Ausgaben der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ddb5a-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddb5a-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ddb5a-126">Example</span></span>  
 <span data-ttu-id="ddb5a-127">Das folgende Beispiel zeigt, wie Sie mit der  **\<wechseln >** festzulegende Element der `General` Trace-Schalter, um die <xref:System.Diagnostics.TraceLevel> Ebene, und aktivieren Sie die `Data` booleschen Ablaufverfolgungsschalter.</span><span class="sxs-lookup"><span data-stu-id="ddb5a-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ddb5a-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ddb5a-128">See also</span></span>
- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="ddb5a-129">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ddb5a-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
