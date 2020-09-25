---
title: <System. Diagnostics>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: aff324ac9952c95c78d7ca15572651dba23b79b7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195167"
---
# <a name="systemdiagnostics-element"></a><span data-ttu-id="7c96c-102">\<system.diagnostics>-Element</span><span class="sxs-lookup"><span data-stu-id="7c96c-102">\<system.diagnostics> Element</span></span>

<span data-ttu-id="7c96c-103">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7c96c-103">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.diagnostics>**  
  
## <a name="syntax"></a><span data-ttu-id="7c96c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c96c-104">Syntax</span></span>  
  
```xml  
<system.diagnostics>
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c96c-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7c96c-105">Attributes and Elements</span></span>  

 <span data-ttu-id="7c96c-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7c96c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c96c-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="7c96c-107">Attributes</span></span>  

 <span data-ttu-id="7c96c-108">Keine</span><span class="sxs-lookup"><span data-stu-id="7c96c-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7c96c-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7c96c-109">Child Elements</span></span>  
  
|<span data-ttu-id="7c96c-110">Element</span><span class="sxs-lookup"><span data-stu-id="7c96c-110">Element</span></span>|<span data-ttu-id="7c96c-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c96c-111">Description</span></span>|  
|-------------|-----------------|  
|[\<assert>](assert-element.md)|<span data-ttu-id="7c96c-112">Gibt an, ob ein Meldungsfeld angezeigt wird, wenn Sie die <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>-Methode aufrufen. Außerdem wird der Name der Datei angegeben, in die die Meldung geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="7c96c-112">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[\<performanceCounters>](performancecounters-element.md)|<span data-ttu-id="7c96c-113">Gibt die Größe des globalen Speichers an, der von den Leistungsindikatoren freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7c96c-113">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[\<sharedListeners>](sharedlisteners-element.md)|<span data-ttu-id="7c96c-114">Enthält Listener, auf die jedes Quell- oder Ablaufverfolgungselement verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="7c96c-114">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="7c96c-115">Listener, die als freigegebene Listener identifiziert werden, können Quellen oder Ablauf Verfolgungen anhand des Namens hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7c96c-115">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[\<sources>](sources-element.md)|<span data-ttu-id="7c96c-116">Gibt Ablauf Verfolgungs Quellen an, die Ablauf Verfolgungs Meldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="7c96c-116">Specifies trace sources that initiate tracing messages.</span></span>|  
|[\<switches>](switches-element.md)|<span data-ttu-id="7c96c-117">Enthält Ablauf Verfolgungs Schalter und die Ebenen, auf denen die Ablauf Verfolgungs Schalter festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="7c96c-117">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[\<trace>](trace-element.md)|<span data-ttu-id="7c96c-118">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="7c96c-118">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7c96c-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7c96c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="7c96c-120">Element</span><span class="sxs-lookup"><span data-stu-id="7c96c-120">Element</span></span>|<span data-ttu-id="7c96c-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c96c-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7c96c-122">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="7c96c-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7c96c-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7c96c-123">Example</span></span>  

 <span data-ttu-id="7c96c-124">Im folgenden Beispiel wird gezeigt, wie ein Ablauf Verfolgungs Schalter und ein Ablaufverfolgungslistener in das- **\<system.diagnostics>** Element eingebettet</span><span class="sxs-lookup"><span data-stu-id="7c96c-124">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="7c96c-125">Der Ablauf `General` Verfolgungs Schalter ist auf die-Ebene festgelegt <xref:System.Diagnostics.TraceLevel> .</span><span class="sxs-lookup"><span data-stu-id="7c96c-125">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="7c96c-126">Der Ablaufverfolgungslistener `myListener` erstellt eine Datei namens `MyListener.log` und schreibt die Ausgabe in die Datei.</span><span class="sxs-lookup"><span data-stu-id="7c96c-126">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7c96c-127">In .NET Framework 2.0 können Sie Text verwenden, um den Wert eines Schalters anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7c96c-127">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="7c96c-128">Beispielsweise können Sie `true` für einen angeben <xref:System.Diagnostics.BooleanSwitch> oder den Text verwenden, der einen Enumerationswert wie z `Error` . b. für einen darstellt <xref:System.Diagnostics.TraceSwitch> .</span><span class="sxs-lookup"><span data-stu-id="7c96c-128">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="7c96c-129">Die Zeile `<add name="myTraceSwitch" value="Error" />` ist gleichbedeutend mit `<add name="myTraceSwitch" value="1" />`.</span><span class="sxs-lookup"><span data-stu-id="7c96c-129">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7c96c-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7c96c-130">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="7c96c-131">Schema für Ablaufverfolgungs- und Debugeinstellungen</span><span class="sxs-lookup"><span data-stu-id="7c96c-131">Trace and Debug Settings Schema</span></span>](index.md)
