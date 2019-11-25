---
title: <filter> Element für <add> für <sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter
helpviewer_keywords:
- filter element for <add> for <sharedListeners>
- initializeData attribute
- <filter> element for <add> for <sharedListeners>
- filters, trace listeners
- trace listeners, filters
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
ms.openlocfilehash: e04ecd773bd6aa7791858711edbd72128dc391ea
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088883"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a><span data-ttu-id="87467-102">\<> Element filtern, \<um > für \<sharedlistener hinzuzufügen ></span><span class="sxs-lookup"><span data-stu-id="87467-102">\<filter> Element for \<add> for \<sharedListeners></span></span>
<span data-ttu-id="87467-103">Fügt einen Filter zu einem Listener in der `sharedListeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="87467-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  

<span data-ttu-id="87467-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="87467-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="87467-105">&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="87467-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="87467-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sharedlistener >** ](sharedlisteners-element.md)</span><span class="sxs-lookup"><span data-stu-id="87467-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)</span></span>\
<span data-ttu-id="87467-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> hinzufügen**](add-element-for-sharedlisteners.md)</span><span class="sxs-lookup"><span data-stu-id="87467-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-sharedlisteners.md)</span></span>\
<span data-ttu-id="87467-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Filter >**</span><span class="sxs-lookup"><span data-stu-id="87467-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>

## <a name="syntax"></a><span data-ttu-id="87467-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="87467-109">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87467-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="87467-110">Attributes and Elements</span></span>  
 <span data-ttu-id="87467-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="87467-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87467-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="87467-112">Attributes</span></span>  
  
|<span data-ttu-id="87467-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="87467-113">Attribute</span></span>|<span data-ttu-id="87467-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87467-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="87467-115">**Typ**</span><span class="sxs-lookup"><span data-stu-id="87467-115">**type**</span></span>|<span data-ttu-id="87467-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="87467-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="87467-117">Gibt den Filtertyp an.</span><span class="sxs-lookup"><span data-stu-id="87467-117">Specifies the type of the filter.</span></span> <span data-ttu-id="87467-118">Sie können nur den vollständigen Namen des Typs (im Format der <xref:System.Type.FullName%2A?displayProperty=nameWithType>-Eigenschaft) verwenden, oder Sie können den voll qualifizierten Typnamen einschließlich der Assemblyinformationen verwenden (im Format der <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType>-Eigenschaft).</span><span class="sxs-lookup"><span data-stu-id="87467-118">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="87467-119">Weitere Informationen zum Erstellen eines voll qualifizierten Typnamens finden Sie unter [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="87467-119">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="87467-120">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="87467-120">**initializeData**</span></span>|<span data-ttu-id="87467-121">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="87467-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="87467-122">Die Zeichenfolge, die an den Konstruktor für die angegebene Klasse übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="87467-122">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87467-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="87467-123">Child Elements</span></span>  
 <span data-ttu-id="87467-124">Keine</span><span class="sxs-lookup"><span data-stu-id="87467-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="87467-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="87467-125">Parent Elements</span></span>  
  
|<span data-ttu-id="87467-126">Element</span><span class="sxs-lookup"><span data-stu-id="87467-126">Element</span></span>|<span data-ttu-id="87467-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87467-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="87467-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="87467-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="87467-129">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="87467-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="87467-130">Eine Auflistung von Listenern, auf die beliebige Quell-oder Ablauf Verfolgungs Elemente verweisen können.</span><span class="sxs-lookup"><span data-stu-id="87467-130">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="87467-131">Fügt der **sharedlistener** -Auflistung einen Listener hinzu.</span><span class="sxs-lookup"><span data-stu-id="87467-131">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87467-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="87467-132">Remarks</span></span>  
 <span data-ttu-id="87467-133">Wenn ein Listener in einem `<add>`-Element des `<sharedListeners>`-Elements definiert ist, sollte der Filter für diesen Listener in einem `<filter>`-Element definiert werden, das ein untergeordnetes Element des `<add>`-Elements ist.</span><span class="sxs-lookup"><span data-stu-id="87467-133">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="87467-134">Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="87467-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87467-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="87467-135">Example</span></span>  
 <span data-ttu-id="87467-136">Im folgenden Beispiel wird gezeigt, wie Sie mit dem `<filter>`-Element dem Ablaufverfolgungslistener `console` in der `sharedListeners`-Auflistung einen Filter hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="87467-136">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"   
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"   
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="87467-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87467-137">See also</span></span>

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="87467-138">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="87467-138">Trace and Debug Settings Schema</span></span>](index.md)
