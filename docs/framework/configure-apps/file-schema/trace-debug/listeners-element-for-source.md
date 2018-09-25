---
title: '&lt;Listener&gt; -Element für &lt;Quelle&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 86b85779f4eff72e8ab910a5ccd32fd369270509
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47085663"
---
# <a name="ltlistenersgt-element-for-ltsourcegt"></a><span data-ttu-id="c2591-102">&lt;Listener&gt; -Element für &lt;Quelle&gt;</span><span class="sxs-lookup"><span data-stu-id="c2591-102">&lt;listeners&gt; Element for &lt;source&gt;</span></span>
<span data-ttu-id="c2591-103">Fügt Listener hinzu oder entfernt den <xref:System.Diagnostics.TraceSource.Listeners%2A> Sammlung für einen <xref:System.Diagnostics.TraceSource>.</span><span class="sxs-lookup"><span data-stu-id="c2591-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="c2591-104">Ein Listener leitet die Ablaufverfolgungsausgabe an ein entsprechendes Ziel, z. B. ein Protokoll, Fenster oder Text-Datei.</span><span class="sxs-lookup"><span data-stu-id="c2591-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
 <span data-ttu-id="c2591-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c2591-105">\<configuration></span></span>  
<span data-ttu-id="c2591-106">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="c2591-106">\<system.diagnostics></span></span>  
<span data-ttu-id="c2591-107">\<Quellen ></span><span class="sxs-lookup"><span data-stu-id="c2591-107">\<sources></span></span>  
<span data-ttu-id="c2591-108">\<Quelle ></span><span class="sxs-lookup"><span data-stu-id="c2591-108">\<source></span></span>  
<span data-ttu-id="c2591-109">\<Listener >-Element</span><span class="sxs-lookup"><span data-stu-id="c2591-109">\<listeners> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2591-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2591-110">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2591-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c2591-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c2591-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c2591-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2591-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="c2591-113">Attributes</span></span>  
 <span data-ttu-id="c2591-114">Keine</span><span class="sxs-lookup"><span data-stu-id="c2591-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c2591-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c2591-115">Child Elements</span></span>  
  
|<span data-ttu-id="c2591-116">Element</span><span class="sxs-lookup"><span data-stu-id="c2591-116">Element</span></span>|<span data-ttu-id="c2591-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c2591-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c2591-118">\<add></span><span class="sxs-lookup"><span data-stu-id="c2591-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-source.md)|<span data-ttu-id="c2591-119">Fügt einen Listener zu der `Listeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="c2591-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="c2591-120">\<remove></span><span class="sxs-lookup"><span data-stu-id="c2591-120">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-source.md)|<span data-ttu-id="c2591-121">Entfernt einen Listener aus der `Listeners` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="c2591-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="c2591-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="c2591-122">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)|<span data-ttu-id="c2591-123">Löscht die `Listeners`-Sammlung für eine Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="c2591-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c2591-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c2591-124">Parent Elements</span></span>  
  
|<span data-ttu-id="c2591-125">Element</span><span class="sxs-lookup"><span data-stu-id="c2591-125">Element</span></span>|<span data-ttu-id="c2591-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c2591-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c2591-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="c2591-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="c2591-128">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c2591-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="c2591-129">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="c2591-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="c2591-130">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="c2591-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2591-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c2591-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="c2591-132">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="c2591-132">Configuration File</span></span>  
 <span data-ttu-id="c2591-133">Dieses Element kann in der Computerkonfigurationsdatei (Machine.config) und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c2591-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2591-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c2591-134">Example</span></span>  
 <span data-ttu-id="c2591-135">Das folgende Beispiel zeigt, wie Sie mit der `<listeners>` Element, um einen Konsolen-Ablaufverfolgungslistener hinzugefügt werden die `mySource` Quelle und den standardmäßigen Ablaufverfolgungslistener zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="c2591-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener">  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error"/>  
          </add>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2591-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2591-136">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="c2591-137">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c2591-137">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="c2591-138">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="c2591-138">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
