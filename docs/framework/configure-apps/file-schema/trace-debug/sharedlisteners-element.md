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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153320"
---
# <a name="sharedlisteners-element"></a><span data-ttu-id="fe0a9-102">\<sharedListeners>-Element</span><span class="sxs-lookup"><span data-stu-id="fe0a9-102">\<sharedListeners> Element</span></span>
<span data-ttu-id="fe0a9-103">Enthält Listener, auf die jedes Quell- oder Ablaufverfolgungselement verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-103">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="fe0a9-104">Diese Listener empfangen standardmäßig keine Ablauf Verfolgungen, und es ist nicht möglich, diese Listener zur Laufzeit abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-104">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="fe0a9-105">Listener, die als freigegebene Listener identifiziert werden, können Quellen oder Ablauf Verfolgungen anhand des Namens hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-105">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<sharedListeners>**  
  
## <a name="syntax"></a><span data-ttu-id="fe0a9-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe0a9-106">Syntax</span></span>  
  
```xml  
<sharedListeners>
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe0a9-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fe0a9-107">Attributes and Elements</span></span>  
 <span data-ttu-id="fe0a9-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe0a9-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="fe0a9-109">Attributes</span></span>  
 <span data-ttu-id="fe0a9-110">Keine</span><span class="sxs-lookup"><span data-stu-id="fe0a9-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fe0a9-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fe0a9-111">Child Elements</span></span>  
  
|<span data-ttu-id="fe0a9-112">Element</span><span class="sxs-lookup"><span data-stu-id="fe0a9-112">Element</span></span>|<span data-ttu-id="fe0a9-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fe0a9-113">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="fe0a9-114">Fügt einen Listener zu der `sharedListeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-114">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fe0a9-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fe0a9-115">Parent Elements</span></span>  
  
|<span data-ttu-id="fe0a9-116">Element</span><span class="sxs-lookup"><span data-stu-id="fe0a9-116">Element</span></span>|<span data-ttu-id="fe0a9-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fe0a9-117">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="fe0a9-118">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="fe0a9-119">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-119">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe0a9-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fe0a9-120">Remarks</span></span>  
 <span data-ttu-id="fe0a9-121">Durch das Hinzufügen eines Listener zur Auflistung der freigegebenen Listener wird er nicht zu einem aktiven Listener.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-121">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="fe0a9-122">Es muss dennoch einer Ablauf Verfolgungs Quelle oder einer Ablauf Verfolgung hinzugefügt werden, indem es der-Auflistung `Listeners` für dieses Trace-Element hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-122">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="fe0a9-123">Die Listenerklassen in der .NET Framework von der- <xref:System.Diagnostics.TraceListener> Klasse abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-123">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="fe0a9-124">Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe0a9-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fe0a9-125">Example</span></span>  
 <span data-ttu-id="fe0a9-126">Im folgenden Beispiel wird gezeigt, wie das `<sharedListeners>` -Element verwendet wird, um den Listener der `console` `Listeners` -Auflistung für die <xref:System.Diagnostics.TraceSource> -Klasse und die- <xref:System.Diagnostics.Trace> Klasse hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-126">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="fe0a9-127">Der Ablaufverfolgungslistener der Konsole schreibt Ablauf Verfolgungs Informationen über Aufrufe von oder in die Konsole <xref:System.Diagnostics.TraceSource> <xref:System.Diagnostics.Trace> .</span><span class="sxs-lookup"><span data-stu-id="fe0a9-127">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fe0a9-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fe0a9-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="fe0a9-129">Schema für Ablaufverfolgungs- und Debugeinstellungen</span><span class="sxs-lookup"><span data-stu-id="fe0a9-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="fe0a9-130">Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="fe0a9-130">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
