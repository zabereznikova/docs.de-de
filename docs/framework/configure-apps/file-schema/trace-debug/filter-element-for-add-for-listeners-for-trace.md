---
title: '&lt;Filter&gt; -Element für &lt;hinzufügen&gt; für &lt;Listener&gt; für &lt;Trace&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 095212f73adb906d9d80db747c331c436c1cf846
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="9379e-102">&lt;Filter&gt; -Element für &lt;hinzufügen&gt; für &lt;Listener&gt; für &lt;Trace&gt;</span><span class="sxs-lookup"><span data-stu-id="9379e-102">&lt;filter&gt; Element for &lt;add&gt; for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="9379e-103">Fügt einen Filter mit einem Listener in der `Listeners` Auflistung für eine Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="9379e-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  
  
 <span data-ttu-id="9379e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9379e-104">\<configuration></span></span>  
<span data-ttu-id="9379e-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="9379e-105">\<system.diagnostics></span></span>  
<span data-ttu-id="9379e-106">\<Trace ></span><span class="sxs-lookup"><span data-stu-id="9379e-106">\<trace></span></span>  
<span data-ttu-id="9379e-107">\<Listener ></span><span class="sxs-lookup"><span data-stu-id="9379e-107">\<listeners></span></span>  
<span data-ttu-id="9379e-108">\<add></span><span class="sxs-lookup"><span data-stu-id="9379e-108">\<add></span></span>  
<span data-ttu-id="9379e-109">\<Filter ></span><span class="sxs-lookup"><span data-stu-id="9379e-109">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9379e-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="9379e-110">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9379e-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9379e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9379e-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9379e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9379e-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="9379e-113">Attributes</span></span>  
  
|<span data-ttu-id="9379e-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="9379e-114">Attribute</span></span>|<span data-ttu-id="9379e-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9379e-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="9379e-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="9379e-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="9379e-117">Gibt den Typ des Filters, die von erben soll die <xref:System.Diagnostics.TraceFilter> Klasse.</span><span class="sxs-lookup"><span data-stu-id="9379e-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="9379e-118">Können Sie die Namespace-qualifizierten Namen des Typs ab, der dem Typ entspricht <xref:System.Type.FullName%2A> -Eigenschaft, oder Sie können den vollqualifizierten Typnamen einschließlich der Assemblyinformationen, entspricht die <xref:System.Type.AssemblyQualifiedName%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9379e-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="9379e-119">Weitere Informationen zu den vollqualifizierten Typnamen, finden Sie unter [angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="9379e-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="9379e-120">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="9379e-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="9379e-121">Die Zeichenfolge, die für die angegebenen Filter-Klasse an den Konstruktor übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="9379e-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9379e-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9379e-122">Child Elements</span></span>  
 <span data-ttu-id="9379e-123">Keine</span><span class="sxs-lookup"><span data-stu-id="9379e-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9379e-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9379e-124">Parent Elements</span></span>  
  
|<span data-ttu-id="9379e-125">Element</span><span class="sxs-lookup"><span data-stu-id="9379e-125">Element</span></span>|<span data-ttu-id="9379e-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9379e-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9379e-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="9379e-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="9379e-128">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9379e-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="9379e-129">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="9379e-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="9379e-130">Enthält die Listener, mit die sammeln, speichern und Weiterleiten von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="9379e-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="9379e-131">Listener leiten die Ablaufverfolgungsausgabe an ein geeignetes Ziel an.</span><span class="sxs-lookup"><span data-stu-id="9379e-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="9379e-132">Fügt einen Listener zu der `Listeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="9379e-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9379e-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9379e-133">Remarks</span></span>  
 <span data-ttu-id="9379e-134">Die `<filter>` Element muss enthalten sein, einer `<add>` -Element für einen Ablaufverfolgungslistener, der den Typ des Listeners angibt, nicht nur der Namen eines Listeners definiert, einem [ \<SharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span><span class="sxs-lookup"><span data-stu-id="9379e-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span></span> <span data-ttu-id="9379e-135">Wenn der Listener in definiert ist ein [ \<SharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), muss der Filter für diesen Listener in diesem Element definiert werden.</span><span class="sxs-lookup"><span data-stu-id="9379e-135">If the listener is defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="9379e-136">Dieses Element kann in der Computerkonfigurationsdatei ("Machine.config") und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9379e-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9379e-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9379e-137">Example</span></span>  
 <span data-ttu-id="9379e-138">Das folgende Beispiel zeigt, wie Sie die `<filter>` Element zum Hinzufügen eines Filters mit dem Listener `console` in der `Listeners` Auflistung für die Ablaufverfolgung, Angeben der Ereignisebene Filter als `Error`.</span><span class="sxs-lookup"><span data-stu-id="9379e-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
        <remove name="Default" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9379e-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9379e-139">See Also</span></span>  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>  
 <xref:System.Diagnostics.TraceFilter>  
 [<span data-ttu-id="9379e-140">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="9379e-140">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
