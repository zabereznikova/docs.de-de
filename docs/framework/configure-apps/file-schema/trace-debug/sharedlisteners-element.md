---
title: <sharedListeners>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sharedListeners
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners
helpviewer_keywords:
- <sharedListeners> element
- listeners
- shared listeners
- trace listeners, <sharedListeners> element
- sharedListeners element
ms.assetid: de200534-19dd-4156-86cf-c50521802c4c
ms.openlocfilehash: 69f15cc9583b397017ac30a0c567914495867c18
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153320"
---
# <a name="sharedlisteners-element"></a><span data-ttu-id="05fd2-102">\<SharedListeners> Element</span><span class="sxs-lookup"><span data-stu-id="05fd2-102">\<sharedListeners> Element</span></span>
<span data-ttu-id="05fd2-103">Enthält Listener, auf die jedes Quell- oder Ablaufverfolgungselement verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="05fd2-103">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="05fd2-104">Diese Listener erhalten standardmäßig keine Ablaufverfolgungen, und es ist nicht möglich, diese Listener zur Laufzeit abzurufen.</span><span class="sxs-lookup"><span data-stu-id="05fd2-104">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="05fd2-105">Listener, die als freigegebene Listener identifiziert wurden, können Quellen oder Ablaufverfolgungen nach Namen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="05fd2-105">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
[<span data-ttu-id="05fd2-106">**\<Konfiguration>**</span><span class="sxs-lookup"><span data-stu-id="05fd2-106">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="05fd2-107">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="05fd2-107">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="05fd2-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<sharedListeners>**</span><span class="sxs-lookup"><span data-stu-id="05fd2-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<sharedListeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05fd2-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="05fd2-109">Syntax</span></span>  
  
```xml  
<sharedListeners>
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05fd2-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="05fd2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="05fd2-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="05fd2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05fd2-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="05fd2-112">Attributes</span></span>  
 <span data-ttu-id="05fd2-113">Keine.</span><span class="sxs-lookup"><span data-stu-id="05fd2-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="05fd2-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="05fd2-114">Child Elements</span></span>  
  
|<span data-ttu-id="05fd2-115">Element</span><span class="sxs-lookup"><span data-stu-id="05fd2-115">Element</span></span>|<span data-ttu-id="05fd2-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05fd2-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05fd2-117">\<hinzufügen></span><span class="sxs-lookup"><span data-stu-id="05fd2-117">\<add></span></span>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="05fd2-118">Fügt einen Listener zu der `sharedListeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="05fd2-118">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="05fd2-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="05fd2-119">Parent Elements</span></span>  
  
|<span data-ttu-id="05fd2-120">Element</span><span class="sxs-lookup"><span data-stu-id="05fd2-120">Element</span></span>|<span data-ttu-id="05fd2-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05fd2-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="05fd2-122">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="05fd2-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="05fd2-123">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="05fd2-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05fd2-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="05fd2-124">Remarks</span></span>  
 <span data-ttu-id="05fd2-125">Das Hinzufügen eines Listeners zur Sammlung "Freigegebene Listener" macht ihn nicht zu einem aktiven Listener.</span><span class="sxs-lookup"><span data-stu-id="05fd2-125">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="05fd2-126">Sie muss weiterhin einer Ablaufverfolgungsquelle oder einer `Listeners` Ablaufverfolgung hinzugefügt werden, indem sie der Auflistung für dieses Ablaufverfolgungselement hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="05fd2-126">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="05fd2-127">Die Listenerklassen in .NET Framework <xref:System.Diagnostics.TraceListener> leiten sich von der Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="05fd2-127">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="05fd2-128">Dieses Element kann in der Maschinenkonfigurationsdatei (Machine.config) und in der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="05fd2-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05fd2-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="05fd2-129">Example</span></span>  
 <span data-ttu-id="05fd2-130">Das folgende Beispiel zeigt, `<sharedListeners>` wie sie das `console` Element `Listeners` verwenden, <xref:System.Diagnostics.TraceSource> um <xref:System.Diagnostics.Trace> den Listener der Auflistung sowohl für die als auch für die Klassen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="05fd2-130">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="05fd2-131">Der Konsolenablaufverfolgungslistener schreibt Ablaufverfolgungsinformationen <xref:System.Diagnostics.TraceSource> <xref:System.Diagnostics.Trace>über Aufrufe von oder an an die Konsole.</span><span class="sxs-lookup"><span data-stu-id="05fd2-131">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sharedListeners>  
      <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"  
          initializeData="Warning" />  
      </add>  
    </sharedListeners>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"  >  
        <listeners>  
          <add name="console" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Verbose"/>  
    </switches>  
    <trace>  
      <listeners>  
        <add name="console" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="05fd2-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="05fd2-132">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="05fd2-133">Ablaufverfolgungs- und Debugeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="05fd2-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="05fd2-134">Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="05fd2-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
