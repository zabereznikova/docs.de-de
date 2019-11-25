---
title: <filter> Element für <add> für <listeners> für <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: 766088b8a26ce3218031df74b193658ba8024280
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088906"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a><span data-ttu-id="fe485-102">\<> Element filtern, \<um > für \<Listener > \<Quelle hinzuzufügen ></span><span class="sxs-lookup"><span data-stu-id="fe485-102">\<filter> Element for \<add> for \<listeners> for \<source></span></span>
<span data-ttu-id="fe485-103">Fügt einen Filter zu einem Listener in der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="fe485-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="fe485-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fe485-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fe485-105">&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="fe485-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="fe485-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Quellen**](sources-element.md) ></span><span class="sxs-lookup"><span data-stu-id="fe485-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="fe485-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**Quelle**](source-element.md) ></span><span class="sxs-lookup"><span data-stu-id="fe485-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="fe485-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](listeners-element-for-source.md) Listener ></span><span class="sxs-lookup"><span data-stu-id="fe485-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="fe485-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> hinzufügen**](add-element-for-listeners-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="fe485-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-source.md)</span></span>\
<span data-ttu-id="fe485-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Filter >**</span><span class="sxs-lookup"><span data-stu-id="fe485-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>

## <a name="syntax"></a><span data-ttu-id="fe485-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe485-111">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe485-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fe485-112">Attributes and Elements</span></span>  
 <span data-ttu-id="fe485-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fe485-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe485-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="fe485-114">Attributes</span></span>  
  
|<span data-ttu-id="fe485-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="fe485-115">Attribute</span></span>|<span data-ttu-id="fe485-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe485-116">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="fe485-117">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="fe485-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="fe485-118">Gibt den Typ des Filters an, der von der <xref:System.Diagnostics.TraceFilter> Klasse erben soll.</span><span class="sxs-lookup"><span data-stu-id="fe485-118">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="fe485-119">Sie können den mit dem Namespace qualifizierten Namen des Typs verwenden, der der <xref:System.Type.FullName%2A>-Eigenschaft des Typs entspricht, oder Sie können den voll qualifizierten Typnamen einschließlich der Assemblyinformationen verwenden, die der <xref:System.Type.AssemblyQualifiedName%2A>-Eigenschaft entsprechen.</span><span class="sxs-lookup"><span data-stu-id="fe485-119">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="fe485-120">Informationen zu voll qualifizierten Typnamen finden Sie unter [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="fe485-120">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="fe485-121">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="fe485-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="fe485-122">Die Zeichenfolge, die an den Konstruktor für die angegebene Filterklasse übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="fe485-122">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fe485-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fe485-123">Child Elements</span></span>  
 <span data-ttu-id="fe485-124">Keine</span><span class="sxs-lookup"><span data-stu-id="fe485-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fe485-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fe485-125">Parent Elements</span></span>  
  
|<span data-ttu-id="fe485-126">Element</span><span class="sxs-lookup"><span data-stu-id="fe485-126">Element</span></span>|<span data-ttu-id="fe485-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe485-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fe485-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="fe485-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="fe485-129">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="fe485-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="fe485-130">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="fe485-130">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="fe485-131">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="fe485-131">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="fe485-132">Enthält Listener, die Nachrichten erfassen, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="fe485-132">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="fe485-133">Listener leiten die Ablauf Verfolgungs Ausgabe an ein entsprechendes Ziel weiter.</span><span class="sxs-lookup"><span data-stu-id="fe485-133">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="fe485-134">Fügt einen Listener zu der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="fe485-134">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe485-135">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fe485-135">Remarks</span></span>  
 <span data-ttu-id="fe485-136">Das `<filter>`-Element muss in einem `<add>`-Element für einen Ablaufverfolgungs-quelllistener enthalten sein, der den Typ des Listener angibt, nicht nur den Namen eines Listener, der in einem [\<sharedlistener->](sharedlisteners-element.md)definiert ist.</span><span class="sxs-lookup"><span data-stu-id="fe485-136">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="fe485-137">Wenn der Listener in einem [\<sharedlistener->](sharedlisteners-element.md)definiert ist, muss der Filter für diesen Listener in diesem Element definiert werden.</span><span class="sxs-lookup"><span data-stu-id="fe485-137">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="fe485-138">Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fe485-138">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe485-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fe485-139">Example</span></span>  
 <span data-ttu-id="fe485-140">Im folgenden Beispiel wird gezeigt, wie das `<filter>`-Element verwendet wird, um dem Listener `console` in der `Listeners`-Auflistung für die `myTraceSource`der Ablauf Verfolgungs Quelle einen Filter hinzuzufügen, wobei die Filter Ereignis Ebene als `Error`angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fe485-140">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fe485-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe485-141">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="fe485-142">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="fe485-142">Trace and Debug Settings Schema</span></span>](index.md)
