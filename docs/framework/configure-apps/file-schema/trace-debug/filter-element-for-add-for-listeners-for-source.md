---
title: "&lt;Filter&gt; -Element für &lt;hinzufügen&gt; für &lt;Listener&gt; für &lt;Quelle&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: ff5acf8edcda68979c04f5e62237464ee6f040a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="8feb1-102">&lt;Filter&gt; -Element für &lt;hinzufügen&gt; für &lt;Listener&gt; für &lt;Quelle&gt;</span><span class="sxs-lookup"><span data-stu-id="8feb1-102">&lt;filter&gt; Element for &lt;add&gt; for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="8feb1-103">Fügt einen Filter zu einem Listener in der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="8feb1-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="8feb1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8feb1-104">\<configuration></span></span>  
<span data-ttu-id="8feb1-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="8feb1-105">\<system.diagnostics></span></span>  
<span data-ttu-id="8feb1-106">\<Quellen ></span><span class="sxs-lookup"><span data-stu-id="8feb1-106">\<sources></span></span>  
<span data-ttu-id="8feb1-107">\<Quelle ></span><span class="sxs-lookup"><span data-stu-id="8feb1-107">\<source></span></span>  
<span data-ttu-id="8feb1-108">\<Listener ></span><span class="sxs-lookup"><span data-stu-id="8feb1-108">\<listeners></span></span>  
<span data-ttu-id="8feb1-109">\<add></span><span class="sxs-lookup"><span data-stu-id="8feb1-109">\<add></span></span>  
<span data-ttu-id="8feb1-110">\<Filter ></span><span class="sxs-lookup"><span data-stu-id="8feb1-110">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8feb1-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="8feb1-111">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8feb1-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8feb1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8feb1-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8feb1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8feb1-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="8feb1-114">Attributes</span></span>  
  
|<span data-ttu-id="8feb1-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="8feb1-115">Attribute</span></span>|<span data-ttu-id="8feb1-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8feb1-116">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="8feb1-117">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="8feb1-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="8feb1-118">Gibt den Typ des Filters, die von erben soll die <xref:System.Diagnostics.TraceFilter> Klasse.</span><span class="sxs-lookup"><span data-stu-id="8feb1-118">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="8feb1-119">Können Sie die Namespace-qualifizierten Namen des Typs ab, der dem Typ entspricht <xref:System.Type.FullName%2A> -Eigenschaft, oder Sie können den vollqualifizierten Typnamen einschließlich der Assemblyinformationen, entspricht die <xref:System.Type.AssemblyQualifiedName%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8feb1-119">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="8feb1-120">Weitere Informationen zu den vollqualifizierten Typnamen, finden Sie unter [angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="8feb1-120">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="8feb1-121">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="8feb1-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="8feb1-122">Die Zeichenfolge, die für die angegebenen Filter-Klasse an den Konstruktor übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="8feb1-122">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8feb1-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8feb1-123">Child Elements</span></span>  
 <span data-ttu-id="8feb1-124">Keine</span><span class="sxs-lookup"><span data-stu-id="8feb1-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8feb1-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8feb1-125">Parent Elements</span></span>  
  
|<span data-ttu-id="8feb1-126">Element</span><span class="sxs-lookup"><span data-stu-id="8feb1-126">Element</span></span>|<span data-ttu-id="8feb1-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8feb1-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8feb1-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="8feb1-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="8feb1-129">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="8feb1-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="8feb1-130">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="8feb1-130">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="8feb1-131">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="8feb1-131">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="8feb1-132">Enthält die Listener, mit die sammeln, speichern und Weiterleiten von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="8feb1-132">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="8feb1-133">Listener leiten die Ablaufverfolgungsausgabe an ein geeignetes Ziel an.</span><span class="sxs-lookup"><span data-stu-id="8feb1-133">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="8feb1-134">Fügt einen Listener zu der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="8feb1-134">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8feb1-135">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8feb1-135">Remarks</span></span>  
 <span data-ttu-id="8feb1-136">Die `<filter>` Element muss enthalten sein, einer `<add>` -Element für einen Ablaufverfolgungslistener für die Quelle, die den Typ des Listeners angibt, nicht nur der Namen eines Listeners definiert, einem [ \<SharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span><span class="sxs-lookup"><span data-stu-id="8feb1-136">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span></span> <span data-ttu-id="8feb1-137">Wenn der Listener in definiert ist ein [ \<SharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), muss der Filter für diesen Listener in diesem Element definiert werden.</span><span class="sxs-lookup"><span data-stu-id="8feb1-137">If the listener is defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="8feb1-138">Dieses Element kann in der Computerkonfigurationsdatei ("Machine.config") und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8feb1-138">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8feb1-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8feb1-139">Example</span></span>  
 <span data-ttu-id="8feb1-140">Das folgende Beispiel zeigt, wie Sie die `<filter>` Element zum Hinzufügen eines Filters mit dem Listener `console` in der `Listeners` Auflistung für die Ablaufverfolgungsquelle `myTraceSource`, Angeben der Ereignisebene Filter als `Error`.</span><span class="sxs-lookup"><span data-stu-id="8feb1-140">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" switchName="SourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="SourceSwitch" value="Warning" />  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8feb1-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8feb1-141">See Also</span></span>  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>  
 <xref:System.Diagnostics.TraceFilter>  
 [<span data-ttu-id="8feb1-142">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="8feb1-142">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
