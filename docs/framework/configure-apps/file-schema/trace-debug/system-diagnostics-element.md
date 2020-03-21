---
title: <system.diagnostics> Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: 4f831592d7d178276b1625e1ef7d8512085342af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153206"
---
# <a name="systemdiagnostics-element"></a><span data-ttu-id="e9b59-102">\<system.diagnostics> Element</span><span class="sxs-lookup"><span data-stu-id="e9b59-102">\<system.diagnostics> Element</span></span>
<span data-ttu-id="e9b59-103">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e9b59-103">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
[<span data-ttu-id="e9b59-104">**\<Konfiguration>**</span><span class="sxs-lookup"><span data-stu-id="e9b59-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="e9b59-105">&nbsp;&nbsp;**\<system.diagnostics>**</span><span class="sxs-lookup"><span data-stu-id="e9b59-105">&nbsp;&nbsp;**\<system.diagnostics>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9b59-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9b59-106">Syntax</span></span>  
  
```xml  
<system.diagnostics>
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9b59-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e9b59-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e9b59-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e9b59-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9b59-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="e9b59-109">Attributes</span></span>  
 <span data-ttu-id="e9b59-110">Keine.</span><span class="sxs-lookup"><span data-stu-id="e9b59-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e9b59-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e9b59-111">Child Elements</span></span>  
  
|<span data-ttu-id="e9b59-112">Element</span><span class="sxs-lookup"><span data-stu-id="e9b59-112">Element</span></span>|<span data-ttu-id="e9b59-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9b59-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9b59-114">\<>geltend machen</span><span class="sxs-lookup"><span data-stu-id="e9b59-114">\<assert></span></span>](assert-element.md)|<span data-ttu-id="e9b59-115">Gibt an, ob ein Meldungsfeld angezeigt wird, wenn Sie die <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>-Methode aufrufen. Außerdem wird der Name der Datei angegeben, in die die Meldung geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="e9b59-115">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[<span data-ttu-id="e9b59-116">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="e9b59-116">\<performanceCounters></span></span>](performancecounters-element.md)|<span data-ttu-id="e9b59-117">Gibt die Größe des globalen Speichers an, der von den Leistungsindikatoren freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e9b59-117">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[<span data-ttu-id="e9b59-118">\<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="e9b59-118">\<sharedListeners></span></span>](sharedlisteners-element.md)|<span data-ttu-id="e9b59-119">Enthält Listener, auf die jedes Quell- oder Ablaufverfolgungselement verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="e9b59-119">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="e9b59-120">Listener, die als freigegebene Listener identifiziert wurden, können Quellen oder Ablaufverfolgungen nach Namen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e9b59-120">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[<span data-ttu-id="e9b59-121">\<Quellen></span><span class="sxs-lookup"><span data-stu-id="e9b59-121">\<sources></span></span>](sources-element.md)|<span data-ttu-id="e9b59-122">Gibt Ablaufverfolgungsquellen an, die Ablaufverfolgungsnachrichten initiieren.</span><span class="sxs-lookup"><span data-stu-id="e9b59-122">Specifies trace sources that initiate tracing messages.</span></span>|  
|[<span data-ttu-id="e9b59-123">\<Switches></span><span class="sxs-lookup"><span data-stu-id="e9b59-123">\<switches></span></span>](switches-element.md)|<span data-ttu-id="e9b59-124">Enthält Ablaufverfolgungsschalter und die Ebenen, auf denen die Ablaufverfolgungsschalter festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="e9b59-124">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[<span data-ttu-id="e9b59-125">\<Spur></span><span class="sxs-lookup"><span data-stu-id="e9b59-125">\<trace></span></span>](trace-element.md)|<span data-ttu-id="e9b59-126">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="e9b59-126">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e9b59-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e9b59-127">Parent Elements</span></span>  
  
|<span data-ttu-id="e9b59-128">Element</span><span class="sxs-lookup"><span data-stu-id="e9b59-128">Element</span></span>|<span data-ttu-id="e9b59-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9b59-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e9b59-130">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e9b59-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e9b59-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e9b59-131">Example</span></span>  
 <span data-ttu-id="e9b59-132">Das folgende Beispiel zeigt, wie Sie einen Ablaufverfolgungsschalter und einen Ablaufverfolgungslistener in das \*\* \<system.diagnostics>-Element\*\* einbetten.</span><span class="sxs-lookup"><span data-stu-id="e9b59-132">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="e9b59-133">Der `General` Ablaufverfolgungsschalter <xref:System.Diagnostics.TraceLevel> wird auf die Ebene eingestellt.</span><span class="sxs-lookup"><span data-stu-id="e9b59-133">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="e9b59-134">Der Ablaufverfolgungslistener `myListener` `MyListener.log` erstellt eine Datei, die aufgerufen wird, und schreibt die Ausgabe in die Datei.</span><span class="sxs-lookup"><span data-stu-id="e9b59-134">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e9b59-135">In .NET Framework 2.0 können Sie Text verwenden, um den Wert eines Schalters anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e9b59-135">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="e9b59-136">Sie können z. `true` B. für eine <xref:System.Diagnostics.BooleanSwitch> angeben oder den Text `Error` verwenden, der einen Enumerationswert darstellt, z. B. für eine <xref:System.Diagnostics.TraceSwitch>.</span><span class="sxs-lookup"><span data-stu-id="e9b59-136">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="e9b59-137">Die Zeile `<add name="myTraceSwitch" value="Error" />` ist gleichbedeutend mit `<add name="myTraceSwitch" value="1" />`.</span><span class="sxs-lookup"><span data-stu-id="e9b59-137">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e9b59-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e9b59-138">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="e9b59-139">Ablaufverfolgungs- und Debugeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="e9b59-139">Trace and Debug Settings Schema</span></span>](index.md)
