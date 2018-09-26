---
title: '&lt;System.Diagnostics&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 35fe167beb53c27aa511e08507415a26b1749ca2
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47156977"
---
# <a name="ltsystemdiagnosticsgt-element"></a><span data-ttu-id="4d484-102">&lt;System.Diagnostics&gt; Element</span><span class="sxs-lookup"><span data-stu-id="4d484-102">&lt;system.diagnostics&gt; Element</span></span>
<span data-ttu-id="4d484-103">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4d484-103">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="4d484-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4d484-104">\<configuration></span></span>  
<span data-ttu-id="4d484-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="4d484-105">\<system.diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d484-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="4d484-106">Syntax</span></span>  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d484-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4d484-107">Attributes and Elements</span></span>  
 <span data-ttu-id="4d484-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4d484-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d484-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="4d484-109">Attributes</span></span>  
 <span data-ttu-id="4d484-110">Keine</span><span class="sxs-lookup"><span data-stu-id="4d484-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4d484-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4d484-111">Child Elements</span></span>  
  
|<span data-ttu-id="4d484-112">Element</span><span class="sxs-lookup"><span data-stu-id="4d484-112">Element</span></span>|<span data-ttu-id="4d484-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4d484-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d484-114">\<assert></span><span class="sxs-lookup"><span data-stu-id="4d484-114">\<assert></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|<span data-ttu-id="4d484-115">Gibt an, ob ein Meldungsfeld angezeigt wird, wenn Sie die <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>-Methode aufrufen. Außerdem wird der Name der Datei angegeben, in die die Meldung geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="4d484-115">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[<span data-ttu-id="4d484-116">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="4d484-116">\<performanceCounters></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|<span data-ttu-id="4d484-117">Gibt die Größe des globalen Speichers an, der von den Leistungsindikatoren freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4d484-117">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[<span data-ttu-id="4d484-118">\<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="4d484-118">\<sharedListeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|<span data-ttu-id="4d484-119">Enthält Listener, auf die jedes Quell- oder Ablaufverfolgungselement verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="4d484-119">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="4d484-120">Listener, die als freigegebene Listener können anhand des Namens mit Quellen oder ablaufverfolgungen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="4d484-120">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[<span data-ttu-id="4d484-121">\<sources></span><span class="sxs-lookup"><span data-stu-id="4d484-121">\<sources></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|<span data-ttu-id="4d484-122">Gibt die Ablaufverfolgungsquellen, die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="4d484-122">Specifies trace sources that initiate tracing messages.</span></span>|  
|[<span data-ttu-id="4d484-123">\<switches></span><span class="sxs-lookup"><span data-stu-id="4d484-123">\<switches></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|<span data-ttu-id="4d484-124">Enthält Ablaufverfolgungsschalter und die Ebenen, wo die Ablaufverfolgungsschalter festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4d484-124">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[<span data-ttu-id="4d484-125">\<trace></span><span class="sxs-lookup"><span data-stu-id="4d484-125">\<trace></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|<span data-ttu-id="4d484-126">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="4d484-126">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4d484-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4d484-127">Parent Elements</span></span>  
  
|<span data-ttu-id="4d484-128">Element</span><span class="sxs-lookup"><span data-stu-id="4d484-128">Element</span></span>|<span data-ttu-id="4d484-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4d484-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4d484-130">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="4d484-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4d484-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4d484-131">Example</span></span>  
 <span data-ttu-id="4d484-132">Das folgende Beispiel zeigt, wie Sie einen Ablaufverfolgungsschalter sowie eines Ablaufverfolgungslisteners in Einbetten der  **\<system.diagnostics >** Element.</span><span class="sxs-lookup"><span data-stu-id="4d484-132">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="4d484-133">Die `General` Ablaufverfolgungsschalter festgelegt ist, um die <xref:System.Diagnostics.TraceLevel> Ebene.</span><span class="sxs-lookup"><span data-stu-id="4d484-133">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="4d484-134">Der Ablaufverfolgungslistener `myListener` erstellt eine Datei namens `MyListener.log` und schreibt die Ausgabe in der Datei.</span><span class="sxs-lookup"><span data-stu-id="4d484-134">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d484-135">In .NET Framework 2.0 können Sie Text verwenden, um den Wert eines Schalters anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4d484-135">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="4d484-136">Sie können z. B. angeben `true` für eine <xref:System.Diagnostics.BooleanSwitch> oder verwenden Sie den Text, der einem Enumerationswert entspricht z. B. `Error` für eine <xref:System.Diagnostics.TraceSwitch>.</span><span class="sxs-lookup"><span data-stu-id="4d484-136">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="4d484-137">Die Zeile `<add name="myTraceSwitch" value="Error" />` ist gleichbedeutend mit `<add name="myTraceSwitch" value="1" />`.</span><span class="sxs-lookup"><span data-stu-id="4d484-137">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4d484-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d484-138">See Also</span></span>  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 [<span data-ttu-id="4d484-139">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="4d484-139">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
