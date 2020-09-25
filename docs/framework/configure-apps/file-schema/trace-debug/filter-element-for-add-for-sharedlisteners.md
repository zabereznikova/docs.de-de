---
title: <filter> -Element für <add> für <sharedListeners>
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
ms.openlocfilehash: e140148a342e31d6ade7def8849d8a7738301704
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173925"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a><span data-ttu-id="eb675-102">\<filter> -Element für \<add> für \<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="eb675-102">\<filter> Element for \<add> for \<sharedListeners></span></span>

<span data-ttu-id="eb675-103">Fügt einen Filter zu einem Listener in der `sharedListeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="eb675-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-sharedlisteners.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**

## <a name="syntax"></a><span data-ttu-id="eb675-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb675-104">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb675-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="eb675-105">Attributes and Elements</span></span>  

 <span data-ttu-id="eb675-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eb675-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb675-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="eb675-107">Attributes</span></span>  
  
|<span data-ttu-id="eb675-108">attribute</span><span class="sxs-lookup"><span data-stu-id="eb675-108">Attribute</span></span>|<span data-ttu-id="eb675-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="eb675-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eb675-110">**type**</span><span class="sxs-lookup"><span data-stu-id="eb675-110">**type**</span></span>|<span data-ttu-id="eb675-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="eb675-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="eb675-112">Gibt den Filtertyp an.</span><span class="sxs-lookup"><span data-stu-id="eb675-112">Specifies the type of the filter.</span></span> <span data-ttu-id="eb675-113">Sie können nur den vollständigen Namen des Typs (im Format der- <xref:System.Type.FullName%2A?displayProperty=nameWithType> Eigenschaft) verwenden, oder Sie können den voll qualifizierten Typnamen verwenden, einschließlich der Assemblyinformationen (im Format der- <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> Eigenschaft).</span><span class="sxs-lookup"><span data-stu-id="eb675-113">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="eb675-114">Weitere Informationen zum Erstellen eines voll qualifizierten Typnamens finden Sie unter [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="eb675-114">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="eb675-115">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="eb675-115">**initializeData**</span></span>|<span data-ttu-id="eb675-116">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="eb675-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="eb675-117">Die Zeichenfolge, die an den Konstruktor für die angegebene Klasse übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="eb675-117">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb675-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eb675-118">Child Elements</span></span>  

 <span data-ttu-id="eb675-119">Keine</span><span class="sxs-lookup"><span data-stu-id="eb675-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb675-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eb675-120">Parent Elements</span></span>  
  
|<span data-ttu-id="eb675-121">Element</span><span class="sxs-lookup"><span data-stu-id="eb675-121">Element</span></span>|<span data-ttu-id="eb675-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb675-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="eb675-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="eb675-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="eb675-124">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="eb675-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="eb675-125">Eine Auflistung von Listenern, auf die beliebige Quell-oder Ablauf Verfolgungs Elemente verweisen können.</span><span class="sxs-lookup"><span data-stu-id="eb675-125">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="eb675-126">Fügt der **sharedlistener** -Auflistung einen Listener hinzu.</span><span class="sxs-lookup"><span data-stu-id="eb675-126">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb675-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="eb675-127">Remarks</span></span>  

 <span data-ttu-id="eb675-128">Wenn ein Listener in einem `<add>` Element des-Elements definiert ist `<sharedListeners>` , sollte der Filter für diesen Listener in einem-Element definiert werden `<filter>` , das ein untergeordnetes Element des- `<add>` Elements ist.</span><span class="sxs-lookup"><span data-stu-id="eb675-128">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="eb675-129">Dieses Element kann in der Computer Konfigurationsdatei (Machine.config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eb675-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb675-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eb675-130">Example</span></span>  

 <span data-ttu-id="eb675-131">Das folgende Beispiel zeigt, wie das-Element verwendet wird, um dem Ablaufverfolgungslistener `<filter>` in der-Auflistung einen Filter hinzuzufügen `console` `sharedListeners`</span><span class="sxs-lookup"><span data-stu-id="eb675-131">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eb675-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb675-132">See also</span></span>

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="eb675-133">Schema für Ablaufverfolgungs- und Debugeinstellungen</span><span class="sxs-lookup"><span data-stu-id="eb675-133">Trace and Debug Settings Schema</span></span>](index.md)
