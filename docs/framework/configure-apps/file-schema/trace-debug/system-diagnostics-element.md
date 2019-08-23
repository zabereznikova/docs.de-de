---
title: < System. Diagnostics >-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: f3b4238a8d7028d47122a420526b38ee4f327332
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926944"
---
# <a name="systemdiagnostics-element"></a><span data-ttu-id="1e4a0-102">\<System. Diagnostics >-Element</span><span class="sxs-lookup"><span data-stu-id="1e4a0-102">\<system.diagnostics> Element</span></span>
<span data-ttu-id="1e4a0-103">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="1e4a0-103">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="1e4a0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1e4a0-104">\<configuration></span></span>  
<span data-ttu-id="1e4a0-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="1e4a0-105">\<system.diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e4a0-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e4a0-106">Syntax</span></span>  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e4a0-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1e4a0-107">Attributes and Elements</span></span>  
 <span data-ttu-id="1e4a0-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1e4a0-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e4a0-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="1e4a0-109">Attributes</span></span>  
 <span data-ttu-id="1e4a0-110">Keine</span><span class="sxs-lookup"><span data-stu-id="1e4a0-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1e4a0-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1e4a0-111">Child Elements</span></span>  
  
|<span data-ttu-id="1e4a0-112">Element</span><span class="sxs-lookup"><span data-stu-id="1e4a0-112">Element</span></span>|<span data-ttu-id="1e4a0-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e4a0-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e4a0-114">\<assert></span><span class="sxs-lookup"><span data-stu-id="1e4a0-114">\<assert></span></span>](assert-element.md)|<span data-ttu-id="1e4a0-115">Gibt an, ob ein Meldungsfeld angezeigt wird, wenn Sie die <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>-Methode aufrufen. Außerdem wird der Name der Datei angegeben, in die die Meldung geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="1e4a0-115">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[<span data-ttu-id="1e4a0-116">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="1e4a0-116">\<performanceCounters></span></span>](performancecounters-element.md)|<span data-ttu-id="1e4a0-117">Gibt die Größe des globalen Speichers an, der von den Leistungsindikatoren freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1e4a0-117">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[<span data-ttu-id="1e4a0-118">\<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="1e4a0-118">\<sharedListeners></span></span>](sharedlisteners-element.md)|<span data-ttu-id="1e4a0-119">Enthält Listener, auf die jedes Quell- oder Ablaufverfolgungselement verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="1e4a0-119">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="1e4a0-120">Listener, die als freigegebene Listener identifiziert werden, können Quellen oder Ablauf Verfolgungen anhand des Namens hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="1e4a0-120">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[<span data-ttu-id="1e4a0-121">\<sources></span><span class="sxs-lookup"><span data-stu-id="1e4a0-121">\<sources></span></span>](sources-element.md)|<span data-ttu-id="1e4a0-122">Gibt Ablauf Verfolgungs Quellen an, die Ablauf Verfolgungs Meldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="1e4a0-122">Specifies trace sources that initiate tracing messages.</span></span>|  
|[<span data-ttu-id="1e4a0-123">\<switches></span><span class="sxs-lookup"><span data-stu-id="1e4a0-123">\<switches></span></span>](switches-element.md)|<span data-ttu-id="1e4a0-124">Enthält Ablauf Verfolgungs Schalter und die Ebenen, auf denen die Ablauf Verfolgungs Schalter festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="1e4a0-124">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[<span data-ttu-id="1e4a0-125">\<trace></span><span class="sxs-lookup"><span data-stu-id="1e4a0-125">\<trace></span></span>](trace-element.md)|<span data-ttu-id="1e4a0-126">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="1e4a0-126">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1e4a0-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1e4a0-127">Parent Elements</span></span>  
  
|<span data-ttu-id="1e4a0-128">Element</span><span class="sxs-lookup"><span data-stu-id="1e4a0-128">Element</span></span>|<span data-ttu-id="1e4a0-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e4a0-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1e4a0-130">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="1e4a0-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1e4a0-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1e4a0-131">Example</span></span>  
 <span data-ttu-id="1e4a0-132">Das folgende Beispiel zeigt, wie Sie einen Ablauf Verfolgungs Schalter und einen Ablaufverfolgungslistener in das  **\<System. Diagnostics->** Element einbetten</span><span class="sxs-lookup"><span data-stu-id="1e4a0-132">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="1e4a0-133">Der `General` Ablauf Verfolgungs Schalter ist auf die <xref:System.Diagnostics.TraceLevel> -Ebene festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1e4a0-133">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="1e4a0-134">Der Ablaufverfolgungslistener erstellt eine Datei namens `MyListener.log` und schreibt die Ausgabe in die Datei. `myListener`</span><span class="sxs-lookup"><span data-stu-id="1e4a0-134">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1e4a0-135">In .NET Framework 2.0 können Sie Text verwenden, um den Wert eines Schalters anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1e4a0-135">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="1e4a0-136">Beispielsweise können Sie für einen `true` <xref:System.Diagnostics.BooleanSwitch> angeben oder den Text verwenden, der einen `Error` Enumerationswert wie z. <xref:System.Diagnostics.TraceSwitch>b. für einen darstellt.</span><span class="sxs-lookup"><span data-stu-id="1e4a0-136">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="1e4a0-137">Die Zeile `<add name="myTraceSwitch" value="Error" />` ist gleichbedeutend mit `<add name="myTraceSwitch" value="1" />`.</span><span class="sxs-lookup"><span data-stu-id="1e4a0-137">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1e4a0-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e4a0-138">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="1e4a0-139">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="1e4a0-139">Trace and Debug Settings Schema</span></span>](index.md)
