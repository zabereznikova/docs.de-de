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
ms.openlocfilehash: dc05c46cb1ba74baceaaeadc2959a6889faf19c9
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699192"
---
# <a name="systemdiagnostics-element"></a><span data-ttu-id="ce4b1-102">\<System. Diagnostics >-Element</span><span class="sxs-lookup"><span data-stu-id="ce4b1-102">\<system.diagnostics> Element</span></span>
<span data-ttu-id="ce4b1-103">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ce4b1-103">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
[<span data-ttu-id="ce4b1-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="ce4b1-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="ce4b1-105">&nbsp;&nbsp; **\<System. Diagnostics >**</span><span class="sxs-lookup"><span data-stu-id="ce4b1-105">&nbsp;&nbsp;**\<system.diagnostics>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce4b1-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce4b1-106">Syntax</span></span>  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce4b1-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ce4b1-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ce4b1-108">In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ce4b1-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce4b1-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="ce4b1-109">Attributes</span></span>  
 <span data-ttu-id="ce4b1-110">None.</span><span class="sxs-lookup"><span data-stu-id="ce4b1-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ce4b1-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ce4b1-111">Child Elements</span></span>  
  
|<span data-ttu-id="ce4b1-112">Element</span><span class="sxs-lookup"><span data-stu-id="ce4b1-112">Element</span></span>|<span data-ttu-id="ce4b1-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce4b1-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce4b1-114">\<assert></span><span class="sxs-lookup"><span data-stu-id="ce4b1-114">\<assert></span></span>](assert-element.md)|<span data-ttu-id="ce4b1-115">Gibt an, ob ein Meldungsfeld angezeigt wird, wenn Sie die <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>-Methode aufrufen. Außerdem wird der Name der Datei angegeben, in die die Meldung geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="ce4b1-115">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[<span data-ttu-id="ce4b1-116">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="ce4b1-116">\<performanceCounters></span></span>](performancecounters-element.md)|<span data-ttu-id="ce4b1-117">Gibt die Größe des globalen Speichers an, der von den Leistungsindikatoren freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ce4b1-117">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[<span data-ttu-id="ce4b1-118">\<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="ce4b1-118">\<sharedListeners></span></span>](sharedlisteners-element.md)|<span data-ttu-id="ce4b1-119">Enthält Listener, auf die jedes Quell- oder Ablaufverfolgungselement verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="ce4b1-119">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="ce4b1-120">Listener, die als freigegebene Listener identifiziert werden, können Quellen oder Ablauf Verfolgungen anhand des Namens hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ce4b1-120">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[<span data-ttu-id="ce4b1-121">\<sources></span><span class="sxs-lookup"><span data-stu-id="ce4b1-121">\<sources></span></span>](sources-element.md)|<span data-ttu-id="ce4b1-122">Gibt Ablauf Verfolgungs Quellen an, die Ablauf Verfolgungs Meldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="ce4b1-122">Specifies trace sources that initiate tracing messages.</span></span>|  
|[<span data-ttu-id="ce4b1-123">\<switches></span><span class="sxs-lookup"><span data-stu-id="ce4b1-123">\<switches></span></span>](switches-element.md)|<span data-ttu-id="ce4b1-124">Enthält Ablauf Verfolgungs Schalter und die Ebenen, auf denen die Ablauf Verfolgungs Schalter festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="ce4b1-124">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[<span data-ttu-id="ce4b1-125">\<trace></span><span class="sxs-lookup"><span data-stu-id="ce4b1-125">\<trace></span></span>](trace-element.md)|<span data-ttu-id="ce4b1-126">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="ce4b1-126">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ce4b1-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ce4b1-127">Parent Elements</span></span>  
  
|<span data-ttu-id="ce4b1-128">Element</span><span class="sxs-lookup"><span data-stu-id="ce4b1-128">Element</span></span>|<span data-ttu-id="ce4b1-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce4b1-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ce4b1-130">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ce4b1-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ce4b1-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ce4b1-131">Example</span></span>  
 <span data-ttu-id="ce4b1-132">Im folgenden Beispiel wird gezeigt, wie ein Ablauf Verfolgungs Schalter und ein Ablaufverfolgungslistener in das **\<System. Diagnostics->** Element eingebettet werden.</span><span class="sxs-lookup"><span data-stu-id="ce4b1-132">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="ce4b1-133">Der Schalter für die `General` Ablauf Verfolgung ist auf <xref:System.Diagnostics.TraceLevel> Ebene festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ce4b1-133">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="ce4b1-134">Der Ablaufverfolgungslistener `myListener` erstellt eine Datei mit dem Namen `MyListener.log` und schreibt die Ausgabe in die Datei.</span><span class="sxs-lookup"><span data-stu-id="ce4b1-134">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ce4b1-135">In .NET Framework 2.0 können Sie Text verwenden, um den Wert eines Schalters anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ce4b1-135">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="ce4b1-136">Sie können z. b. `true` für eine <xref:System.Diagnostics.BooleanSwitch> angeben oder den Text verwenden, der einen Enumerationswert darstellt, z. b. `Error` für einen <xref:System.Diagnostics.TraceSwitch>.</span><span class="sxs-lookup"><span data-stu-id="ce4b1-136">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="ce4b1-137">Die Zeile `<add name="myTraceSwitch" value="Error" />` ist gleichbedeutend mit `<add name="myTraceSwitch" value="1" />`.</span><span class="sxs-lookup"><span data-stu-id="ce4b1-137">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ce4b1-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce4b1-138">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="ce4b1-139">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ce4b1-139">Trace and Debug Settings Schema</span></span>](index.md)
