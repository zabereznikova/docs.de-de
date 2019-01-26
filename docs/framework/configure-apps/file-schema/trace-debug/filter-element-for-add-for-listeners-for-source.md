---
title: '&lt;Filter&gt; -Element für &lt;hinzufügen&gt; für &lt;Listener&gt; für &lt;Quelle&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: 76aecf0b97a1b203d790dc34d83bc01ea1de5236
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083287"
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="f9ef9-102">&lt;Filter&gt; -Element für &lt;hinzufügen&gt; für &lt;Listener&gt; für &lt;Quelle&gt;</span><span class="sxs-lookup"><span data-stu-id="f9ef9-102">&lt;filter&gt; Element for &lt;add&gt; for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="f9ef9-103">Fügt einen Filter zu einem Listener in der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="f9ef9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f9ef9-104">\<configuration></span></span>  
<span data-ttu-id="f9ef9-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="f9ef9-105">\<system.diagnostics></span></span>  
<span data-ttu-id="f9ef9-106">\<Quellen ></span><span class="sxs-lookup"><span data-stu-id="f9ef9-106">\<sources></span></span>  
<span data-ttu-id="f9ef9-107">\<Quelle ></span><span class="sxs-lookup"><span data-stu-id="f9ef9-107">\<source></span></span>  
<span data-ttu-id="f9ef9-108">\<listeners></span><span class="sxs-lookup"><span data-stu-id="f9ef9-108">\<listeners></span></span>  
<span data-ttu-id="f9ef9-109">\<add></span><span class="sxs-lookup"><span data-stu-id="f9ef9-109">\<add></span></span>  
<span data-ttu-id="f9ef9-110">\<filter></span><span class="sxs-lookup"><span data-stu-id="f9ef9-110">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9ef9-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9ef9-111">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9ef9-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f9ef9-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f9ef9-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9ef9-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="f9ef9-114">Attributes</span></span>  
  
|<span data-ttu-id="f9ef9-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="f9ef9-115">Attribute</span></span>|<span data-ttu-id="f9ef9-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9ef9-116">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="f9ef9-117">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="f9ef9-118">Gibt den Typ des Filters an, der von erben soll die <xref:System.Diagnostics.TraceFilter> Klasse.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-118">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="f9ef9-119">Sie können den Namespace-qualifizierten Namen des Typs, der des Typs entspricht <xref:System.Type.FullName%2A> -Eigenschaft, oder Sie können den vollqualifizierten Typnamen einschließlich der Assemblyinformationen, die entspricht der <xref:System.Type.AssemblyQualifiedName%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-119">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="f9ef9-120">Weitere Informationen zu vollqualifizierten Typnamen, finden Sie unter [angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="f9ef9-120">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="f9ef9-121">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f9ef9-122">Die Zeichenfolge, die für die angegebenen Filter-Klasse an den Konstruktor übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-122">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f9ef9-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f9ef9-123">Child Elements</span></span>  
 <span data-ttu-id="f9ef9-124">Keine</span><span class="sxs-lookup"><span data-stu-id="f9ef9-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f9ef9-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f9ef9-125">Parent Elements</span></span>  
  
|<span data-ttu-id="f9ef9-126">Element</span><span class="sxs-lookup"><span data-stu-id="f9ef9-126">Element</span></span>|<span data-ttu-id="f9ef9-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9ef9-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f9ef9-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="f9ef9-129">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="f9ef9-130">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-130">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="f9ef9-131">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-131">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="f9ef9-132">Enthält Listener, die sammeln, speichern und Weiterleiten von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-132">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="f9ef9-133">Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-133">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="f9ef9-134">Fügt einen Listener zu der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-134">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9ef9-135">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f9ef9-135">Remarks</span></span>  
 <span data-ttu-id="f9ef9-136">Die `<filter>` Element muss enthalten sein, eine `<add>` -Element für einen Ablaufverfolgungslistener für die Datenquelle, die den Typ des Listeners, der angibt, die nicht nur der Namen eines Listeners in definiert eine [ \<SharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span><span class="sxs-lookup"><span data-stu-id="f9ef9-136">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span></span> <span data-ttu-id="f9ef9-137">Wenn der Listener in definiert ist eine [ \<SharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), muss der Filter für diesen Listener in diesem Element definiert werden.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-137">If the listener is defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="f9ef9-138">Dieses Element kann in der Computerkonfigurationsdatei (Machine.config) und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-138">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9ef9-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f9ef9-139">Example</span></span>  
 <span data-ttu-id="f9ef9-140">Das folgende Beispiel zeigt, wie Sie mit der `<filter>` Element um einen Filter hinzuzufügen, mit dem Listener `console` in die `Listeners` Auflistung für die Ablaufverfolgungsquelle `myTraceSource`, Angeben der Ebene des Filter-Ereignis wie `Error`.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-140">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f9ef9-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9ef9-141">See also</span></span>
- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="f9ef9-142">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="f9ef9-142">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
