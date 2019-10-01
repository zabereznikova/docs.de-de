---
title: <filter>-Element für <add> für <listeners> für <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: f6b1ec99c5aab8e85df7f1920aca32f49a5be066
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699363"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="425d8-102">\<filter > Element für \<ADD > für \<listener > für \<trace ></span><span class="sxs-lookup"><span data-stu-id="425d8-102">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>
<span data-ttu-id="425d8-103">Fügt einen Filter zu einem Listener in der `Listeners`-Auflistung für eine Ablauf Verfolgung hinzu.</span><span class="sxs-lookup"><span data-stu-id="425d8-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  
  
[<span data-ttu-id="425d8-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="425d8-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="425d8-105">&nbsp; @ no__t-1[ **\<system. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="425d8-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="425d8-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<trace >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="425d8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>  
<span data-ttu-id="425d8-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<listener >** ](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="425d8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>  
<span data-ttu-id="425d8-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0add >** ](add-element-for-listeners-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="425d8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-trace.md)</span></span>  
<span data-ttu-id="425d8-109">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 @ no__t-8 @ no__t-9 **&nbsp;1filter >**</span><span class="sxs-lookup"><span data-stu-id="425d8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="425d8-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="425d8-110">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="425d8-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="425d8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="425d8-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="425d8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="425d8-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="425d8-113">Attributes</span></span>  
  
|<span data-ttu-id="425d8-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="425d8-114">Attribute</span></span>|<span data-ttu-id="425d8-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="425d8-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="425d8-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="425d8-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="425d8-117">Gibt den Typ des Filters an, der von der <xref:System.Diagnostics.TraceFilter>-Klasse erben soll.</span><span class="sxs-lookup"><span data-stu-id="425d8-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="425d8-118">Sie können den mit dem Namespace qualifizierten Namen des Typs verwenden, der der <xref:System.Type.FullName%2A>-Eigenschaft des Typs entspricht, oder Sie können den voll qualifizierten Typnamen einschließlich der Assemblyinformationen verwenden, die der Eigenschaft <xref:System.Type.AssemblyQualifiedName%2A> entsprechen.</span><span class="sxs-lookup"><span data-stu-id="425d8-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="425d8-119">Informationen zu voll qualifizierten Typnamen finden Sie unter [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="425d8-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="425d8-120">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="425d8-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="425d8-121">Die Zeichenfolge, die an den Konstruktor für die angegebene Filterklasse übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="425d8-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="425d8-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="425d8-122">Child Elements</span></span>  
 <span data-ttu-id="425d8-123">Keine</span><span class="sxs-lookup"><span data-stu-id="425d8-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="425d8-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="425d8-124">Parent Elements</span></span>  
  
|<span data-ttu-id="425d8-125">Element</span><span class="sxs-lookup"><span data-stu-id="425d8-125">Element</span></span>|<span data-ttu-id="425d8-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="425d8-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="425d8-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="425d8-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="425d8-128">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="425d8-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="425d8-129">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="425d8-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="425d8-130">Enthält Listener, die Nachrichten erfassen, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="425d8-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="425d8-131">Listener leiten die Ablauf Verfolgungs Ausgabe an ein entsprechendes Ziel weiter.</span><span class="sxs-lookup"><span data-stu-id="425d8-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="425d8-132">Fügt einen Listener zu der `Listeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="425d8-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="425d8-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="425d8-133">Remarks</span></span>  
 <span data-ttu-id="425d8-134">Das `<filter>`-Element muss in einem `<add>`-Element für einen Ablaufverfolgungslistener enthalten sein, der den Typ des Listener angibt, nicht nur den Namen eines Listener, der in einem [\<sharedlistener->](sharedlisteners-element.md)definiert ist.</span><span class="sxs-lookup"><span data-stu-id="425d8-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="425d8-135">Wenn der Listener in einem [\<sharedlistener->](sharedlisteners-element.md)definiert ist, muss der Filter für diesen Listener in diesem Element definiert werden.</span><span class="sxs-lookup"><span data-stu-id="425d8-135">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="425d8-136">Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="425d8-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="425d8-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="425d8-137">Example</span></span>  
 <span data-ttu-id="425d8-138">Im folgenden Beispiel wird gezeigt, wie das `<filter>`-Element verwendet wird, um dem Listener `console` in der `Listeners`-Auflistung für die Ablauf Verfolgung einen Filter hinzuzufügen, wobei die Filter Ereignis Ebene als `Error` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="425d8-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="425d8-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="425d8-139">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="425d8-140">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="425d8-140">Trace and Debug Settings Schema</span></span>](index.md)
