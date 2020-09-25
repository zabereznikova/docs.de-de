---
title: <filter>-Element <add> für für für <listeners><source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: 2b83fd10da506202427aaeee454411822ff1ae5b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201680"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a><span data-ttu-id="b4d06-102">\<filter>-Element \<add> für für für \<listeners>\<source></span><span class="sxs-lookup"><span data-stu-id="b4d06-102">\<filter> Element for \<add> for \<listeners> for \<source></span></span>

<span data-ttu-id="b4d06-103">Fügt einen Filter zu einem Listener in der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="b4d06-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**

## <a name="syntax"></a><span data-ttu-id="b4d06-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4d06-104">Syntax</span></span>  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4d06-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b4d06-105">Attributes and Elements</span></span>  

 <span data-ttu-id="b4d06-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b4d06-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4d06-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="b4d06-107">Attributes</span></span>  
  
|<span data-ttu-id="b4d06-108">attribute</span><span class="sxs-lookup"><span data-stu-id="b4d06-108">Attribute</span></span>|<span data-ttu-id="b4d06-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4d06-109">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="b4d06-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="b4d06-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="b4d06-111">Gibt den Typ des Filters an, der von der-Klasse erben soll <xref:System.Diagnostics.TraceFilter> .</span><span class="sxs-lookup"><span data-stu-id="b4d06-111">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="b4d06-112">Sie können den mit dem Namespace qualifizierten Namen des Typs verwenden, der der-Eigenschaft des Typs entspricht <xref:System.Type.FullName%2A> , oder Sie können den voll qualifizierten Typnamen einschließlich der Assemblyinformationen verwenden, die der- <xref:System.Type.AssemblyQualifiedName%2A> Eigenschaft entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b4d06-112">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="b4d06-113">Informationen zu voll qualifizierten Typnamen finden Sie unter [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="b4d06-113">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="b4d06-114">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b4d06-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b4d06-115">Die Zeichenfolge, die an den Konstruktor für die angegebene Filterklasse übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="b4d06-115">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b4d06-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b4d06-116">Child Elements</span></span>  

 <span data-ttu-id="b4d06-117">Keine</span><span class="sxs-lookup"><span data-stu-id="b4d06-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b4d06-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b4d06-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b4d06-119">Element</span><span class="sxs-lookup"><span data-stu-id="b4d06-119">Element</span></span>|<span data-ttu-id="b4d06-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4d06-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b4d06-121">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b4d06-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b4d06-122">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b4d06-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="b4d06-123">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="b4d06-123">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="b4d06-124">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="b4d06-124">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="b4d06-125">Enthält Listener, die Nachrichten erfassen, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="b4d06-125">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="b4d06-126">Listener leiten die Ablauf Verfolgungs Ausgabe an ein entsprechendes Ziel weiter.</span><span class="sxs-lookup"><span data-stu-id="b4d06-126">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="b4d06-127">Fügt einen Listener zu der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="b4d06-127">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4d06-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b4d06-128">Remarks</span></span>  

 <span data-ttu-id="b4d06-129">Das- `<filter>` Element muss in einem- `<add>` Element für einen Ablaufverfolgungs-quelllistener enthalten sein, der den Typ des Listener angibt, nicht nur den Namen eines Listener, der in definiert ist [\<sharedListeners>](sharedlisteners-element.md) .</span><span class="sxs-lookup"><span data-stu-id="b4d06-129">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="b4d06-130">Wenn der Listener in einem definiert ist [\<sharedListeners>](sharedlisteners-element.md) , muss der Filter für diesen Listener in diesem Element definiert werden.</span><span class="sxs-lookup"><span data-stu-id="b4d06-130">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="b4d06-131">Dieses Element kann in der Computer Konfigurationsdatei (Machine.config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b4d06-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4d06-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4d06-132">Example</span></span>  

 <span data-ttu-id="b4d06-133">Im folgenden Beispiel wird gezeigt, wie das- `<filter>` Element verwendet wird, um dem Listener `console` in der-Auflistung für die Ablauf Verfolgungs Quelle einen Filter hinzuzufügen `Listeners` `myTraceSource` , wobei die Filter Ereignis Ebene als angegeben wird `Error` .</span><span class="sxs-lookup"><span data-stu-id="b4d06-133">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b4d06-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b4d06-134">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="b4d06-135">Schema für Ablaufverfolgungs- und Debugeinstellungen</span><span class="sxs-lookup"><span data-stu-id="b4d06-135">Trace and Debug Settings Schema</span></span>](index.md)
