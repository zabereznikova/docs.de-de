---
title: <filter>-Element <add> für für für <listeners><trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: d856fc742bc2dca51095ce0866dcbfdaadadf64d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176109"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="3a862-102">\<filter>-Element \<add> für für für \<listeners>\<trace></span><span class="sxs-lookup"><span data-stu-id="3a862-102">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>

<span data-ttu-id="3a862-103">Fügt einen Filter zu einem Listener in der-Auflistung `Listeners` für eine Ablauf Verfolgung hinzu.</span><span class="sxs-lookup"><span data-stu-id="3a862-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**

## <a name="syntax"></a><span data-ttu-id="3a862-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a862-104">Syntax</span></span>  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a862-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3a862-105">Attributes and Elements</span></span>  

 <span data-ttu-id="3a862-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3a862-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a862-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="3a862-107">Attributes</span></span>  
  
|<span data-ttu-id="3a862-108">attribute</span><span class="sxs-lookup"><span data-stu-id="3a862-108">Attribute</span></span>|<span data-ttu-id="3a862-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a862-109">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="3a862-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="3a862-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="3a862-111">Gibt den Typ des Filters an, der von der-Klasse erben soll <xref:System.Diagnostics.TraceFilter> .</span><span class="sxs-lookup"><span data-stu-id="3a862-111">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="3a862-112">Sie können den mit dem Namespace qualifizierten Namen des Typs verwenden, der der-Eigenschaft des Typs entspricht <xref:System.Type.FullName%2A> , oder Sie können den voll qualifizierten Typnamen einschließlich der Assemblyinformationen verwenden, die der- <xref:System.Type.AssemblyQualifiedName%2A> Eigenschaft entsprechen.</span><span class="sxs-lookup"><span data-stu-id="3a862-112">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="3a862-113">Informationen zu voll qualifizierten Typnamen finden Sie unter [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="3a862-113">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="3a862-114">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="3a862-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="3a862-115">Die Zeichenfolge, die an den Konstruktor für die angegebene Filterklasse übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="3a862-115">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a862-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3a862-116">Child Elements</span></span>  

 <span data-ttu-id="3a862-117">Keine</span><span class="sxs-lookup"><span data-stu-id="3a862-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a862-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3a862-118">Parent Elements</span></span>  
  
|<span data-ttu-id="3a862-119">Element</span><span class="sxs-lookup"><span data-stu-id="3a862-119">Element</span></span>|<span data-ttu-id="3a862-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a862-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3a862-121">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="3a862-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="3a862-122">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="3a862-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="3a862-123">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="3a862-123">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="3a862-124">Enthält Listener, die Nachrichten erfassen, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="3a862-124">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="3a862-125">Listener leiten die Ablauf Verfolgungs Ausgabe an ein entsprechendes Ziel weiter.</span><span class="sxs-lookup"><span data-stu-id="3a862-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="3a862-126">Fügt einen Listener zu der `Listeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="3a862-126">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a862-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3a862-127">Remarks</span></span>  

 <span data-ttu-id="3a862-128">Das-Element muss in einem-Element für einen Ablaufverfolgungslistener `<filter>` enthalten sein `<add>` , der den Typ des Listener angibt, nicht nur den Namen eines Listener, der in definiert ist [\<sharedListeners>](sharedlisteners-element.md) .</span><span class="sxs-lookup"><span data-stu-id="3a862-128">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="3a862-129">Wenn der Listener in einem definiert ist [\<sharedListeners>](sharedlisteners-element.md) , muss der Filter für diesen Listener in diesem Element definiert werden.</span><span class="sxs-lookup"><span data-stu-id="3a862-129">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="3a862-130">Dieses Element kann in der Computer Konfigurationsdatei (Machine.config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3a862-130">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a862-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3a862-131">Example</span></span>  

 <span data-ttu-id="3a862-132">Im folgenden Beispiel wird gezeigt, wie das- `<filter>` Element verwendet wird, um dem Listener in der-Auflistung für die Ablauf Verfolgung einen Filter hinzuzufügen `console` `Listeners` , wobei die Filter Ereignis Ebene als angegeben wird `Error` .</span><span class="sxs-lookup"><span data-stu-id="3a862-132">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3a862-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3a862-133">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="3a862-134">Schema für Ablaufverfolgungs- und Debugeinstellungen</span><span class="sxs-lookup"><span data-stu-id="3a862-134">Trace and Debug Settings Schema</span></span>](index.md)
