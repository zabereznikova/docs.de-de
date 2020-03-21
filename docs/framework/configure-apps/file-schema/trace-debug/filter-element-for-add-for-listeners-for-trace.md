---
title: <filter>Element <add> für <listeners> für für<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: b6c2c2bf7fe953a75f9d8129039ef33b4d8a3f56
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153465"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="81e26-102">\<Filter> \<Element zum \<Hinzufügen \<von> für Listener> für Ablaufverfolgungs></span><span class="sxs-lookup"><span data-stu-id="81e26-102">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>
<span data-ttu-id="81e26-103">Fügt einem Listener in `Listeners` der Auflistung einen Filter für eine Ablaufverfolgung hinzu.</span><span class="sxs-lookup"><span data-stu-id="81e26-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  

<span data-ttu-id="81e26-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="81e26-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="81e26-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="81e26-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="81e26-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<Spur>**](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="81e26-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="81e26-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Hörer>**](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="81e26-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="81e26-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<hinzufügen>**](add-element-for-listeners-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="81e26-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-trace.md)</span></span>\
<span data-ttu-id="81e26-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<Filter>**</span><span class="sxs-lookup"><span data-stu-id="81e26-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>

## <a name="syntax"></a><span data-ttu-id="81e26-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="81e26-110">Syntax</span></span>  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81e26-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="81e26-111">Attributes and Elements</span></span>  
 <span data-ttu-id="81e26-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="81e26-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81e26-113">Attributes</span><span class="sxs-lookup"><span data-stu-id="81e26-113">Attributes</span></span>  
  
|<span data-ttu-id="81e26-114">attribute</span><span class="sxs-lookup"><span data-stu-id="81e26-114">Attribute</span></span>|<span data-ttu-id="81e26-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81e26-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="81e26-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="81e26-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="81e26-117">Gibt den Typ des Filters an, der <xref:System.Diagnostics.TraceFilter> von der Klasse erben soll.</span><span class="sxs-lookup"><span data-stu-id="81e26-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="81e26-118">Sie können den Namespace-qualifizierten Namen des Typs verwenden, <xref:System.Type.FullName%2A> der der Eigenschaft des Typs entspricht, oder Sie können <xref:System.Type.AssemblyQualifiedName%2A> den vollqualifizierten Typnamen einschließlich der Assemblyinformationen verwenden, der der Eigenschaft entspricht.</span><span class="sxs-lookup"><span data-stu-id="81e26-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="81e26-119">Informationen zu vollqualifizierten Typnamen finden Sie unter [Angeben von vollqualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="81e26-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="81e26-120">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="81e26-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="81e26-121">Die Zeichenfolge, die an den Konstruktor für die angegebene Filterklasse übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="81e26-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="81e26-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="81e26-122">Child Elements</span></span>  
 <span data-ttu-id="81e26-123">Keine.</span><span class="sxs-lookup"><span data-stu-id="81e26-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="81e26-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="81e26-124">Parent Elements</span></span>  
  
|<span data-ttu-id="81e26-125">Element</span><span class="sxs-lookup"><span data-stu-id="81e26-125">Element</span></span>|<span data-ttu-id="81e26-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81e26-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="81e26-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="81e26-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="81e26-128">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="81e26-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="81e26-129">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="81e26-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="81e26-130">Enthält Listener, die Nachrichten sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="81e26-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="81e26-131">Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel weiter.</span><span class="sxs-lookup"><span data-stu-id="81e26-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="81e26-132">Fügt einen Listener zu der `Listeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="81e26-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81e26-133">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="81e26-133">Remarks</span></span>  
 <span data-ttu-id="81e26-134">Das `<filter>` Element muss in `<add>` einem Element für einen Ablaufverfolgungslistener enthalten sein, der den Typ des Listeners angibt, nicht nur den Namen eines Listeners, der in einem [ \<freigegebenen Listeners>](sharedlisteners-element.md)definiert ist.</span><span class="sxs-lookup"><span data-stu-id="81e26-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="81e26-135">Wenn der Listener in einem [ \<freigegebenen Listeners>](sharedlisteners-element.md)definiert ist, muss der Filter für diesen Listener in diesem Element definiert werden.</span><span class="sxs-lookup"><span data-stu-id="81e26-135">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="81e26-136">Dieses Element kann in der Maschinenkonfigurationsdatei (Machine.config) und in der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="81e26-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81e26-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="81e26-137">Example</span></span>  
 <span data-ttu-id="81e26-138">Das folgende Beispiel zeigt, `<filter>` wie Sie das Element `console` verwenden, `Listeners` um dem Listener in der `Error`Auflistung für die Ablaufverfolgung einen Filter hinzuzufügen, und geben die Filterereignisebene als an.</span><span class="sxs-lookup"><span data-stu-id="81e26-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="81e26-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="81e26-139">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="81e26-140">Ablaufverfolgungs- und Debugeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="81e26-140">Trace and Debug Settings Schema</span></span>](index.md)
