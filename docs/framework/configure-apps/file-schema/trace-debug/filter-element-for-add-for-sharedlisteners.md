---
title: <filter>-Element <add> für für<sharedListeners>
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
ms.openlocfilehash: 571a3add232f3e4f9747040dc104b85e8cc3085e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920512"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a><span data-ttu-id="5616f-102">\<Filter > Element für \<Add > for \<sharedlistener ></span><span class="sxs-lookup"><span data-stu-id="5616f-102">\<filter> Element for \<add> for \<sharedListeners></span></span>
<span data-ttu-id="5616f-103">Fügt einen Filter zu einem Listener in der `sharedListeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="5616f-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  
  
 <span data-ttu-id="5616f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5616f-104">\<configuration></span></span>  
<span data-ttu-id="5616f-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="5616f-105">\<system.diagnostics></span></span>  
<span data-ttu-id="5616f-106">\<sharedlistener-> Element</span><span class="sxs-lookup"><span data-stu-id="5616f-106">\<sharedListeners> Element</span></span>  
<span data-ttu-id="5616f-107">\<add></span><span class="sxs-lookup"><span data-stu-id="5616f-107">\<add></span></span>  
<span data-ttu-id="5616f-108">\<Filter ></span><span class="sxs-lookup"><span data-stu-id="5616f-108">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5616f-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="5616f-109">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5616f-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5616f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5616f-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5616f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5616f-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="5616f-112">Attributes</span></span>  
  
|<span data-ttu-id="5616f-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="5616f-113">Attribute</span></span>|<span data-ttu-id="5616f-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5616f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5616f-115">**Typ**</span><span class="sxs-lookup"><span data-stu-id="5616f-115">**type**</span></span>|<span data-ttu-id="5616f-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="5616f-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="5616f-117">Gibt den Filtertyp an.</span><span class="sxs-lookup"><span data-stu-id="5616f-117">Specifies the type of the filter.</span></span> <span data-ttu-id="5616f-118">Sie können nur den vollständigen Namen des Typs (im Format <xref:System.Type.FullName%2A?displayProperty=nameWithType> der-Eigenschaft) verwenden, oder Sie können den voll qualifizierten Typnamen verwenden, einschließlich der Assemblyinformationen (im Format <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> der-Eigenschaft).</span><span class="sxs-lookup"><span data-stu-id="5616f-118">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="5616f-119">Weitere Informationen zum Erstellen eines voll qualifizierten Typnamens finden Sie unter [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="5616f-119">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="5616f-120">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="5616f-120">**initializeData**</span></span>|<span data-ttu-id="5616f-121">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="5616f-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="5616f-122">Die Zeichenfolge, die an den Konstruktor für die angegebene Klasse übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="5616f-122">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5616f-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5616f-123">Child Elements</span></span>  
 <span data-ttu-id="5616f-124">Keine</span><span class="sxs-lookup"><span data-stu-id="5616f-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5616f-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5616f-125">Parent Elements</span></span>  
  
|<span data-ttu-id="5616f-126">Element</span><span class="sxs-lookup"><span data-stu-id="5616f-126">Element</span></span>|<span data-ttu-id="5616f-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5616f-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5616f-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="5616f-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="5616f-129">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="5616f-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="5616f-130">Eine Auflistung von Listenern, auf die beliebige Quell-oder Ablauf Verfolgungs Elemente verweisen können.</span><span class="sxs-lookup"><span data-stu-id="5616f-130">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="5616f-131">Fügt der **sharedlistener** -Auflistung einen Listener hinzu.</span><span class="sxs-lookup"><span data-stu-id="5616f-131">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5616f-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5616f-132">Remarks</span></span>  
 <span data-ttu-id="5616f-133">Wenn ein Listener in `<add>` einem Element `<sharedListeners>` des-Elements definiert ist, sollte der Filter für diesen Listener in einem `<filter>` -Element definiert werden, das ein untergeordnetes `<add>` Element des-Elements ist.</span><span class="sxs-lookup"><span data-stu-id="5616f-133">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="5616f-134">Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5616f-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5616f-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5616f-135">Example</span></span>  
 <span data-ttu-id="5616f-136">Das folgende Beispiel zeigt, wie das `<filter>` -Element verwendet wird, um dem `console` Ablaufverfolgungslistener in der `sharedListeners` -Auflistung einen Filter hinzuzufügen</span><span class="sxs-lookup"><span data-stu-id="5616f-136">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5616f-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5616f-137">See also</span></span>

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="5616f-138">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="5616f-138">Trace and Debug Settings Schema</span></span>](index.md)
