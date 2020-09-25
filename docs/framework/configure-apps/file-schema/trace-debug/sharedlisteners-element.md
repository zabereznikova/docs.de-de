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
ms.openlocfilehash: 7e249e59423740b36e42f59fae8854412d01a0cc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173847"
---
# <a name="sharedlisteners-element"></a><span data-ttu-id="900bc-102">\<sharedListeners>-Element</span><span class="sxs-lookup"><span data-stu-id="900bc-102">\<sharedListeners> Element</span></span>

<span data-ttu-id="900bc-103">Enthält Listener, auf die jedes Quell- oder Ablaufverfolgungselement verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="900bc-103">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="900bc-104">Diese Listener empfangen standardmäßig keine Ablauf Verfolgungen, und es ist nicht möglich, diese Listener zur Laufzeit abzurufen.</span><span class="sxs-lookup"><span data-stu-id="900bc-104">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="900bc-105">Listener, die als freigegebene Listener identifiziert werden, können Quellen oder Ablauf Verfolgungen anhand des Namens hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="900bc-105">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<sharedListeners>**  
  
## <a name="syntax"></a><span data-ttu-id="900bc-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="900bc-106">Syntax</span></span>  
  
```xml  
<sharedListeners>
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="900bc-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="900bc-107">Attributes and Elements</span></span>  

 <span data-ttu-id="900bc-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="900bc-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="900bc-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="900bc-109">Attributes</span></span>  

 <span data-ttu-id="900bc-110">Keine</span><span class="sxs-lookup"><span data-stu-id="900bc-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="900bc-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="900bc-111">Child Elements</span></span>  
  
|<span data-ttu-id="900bc-112">Element</span><span class="sxs-lookup"><span data-stu-id="900bc-112">Element</span></span>|<span data-ttu-id="900bc-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="900bc-113">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="900bc-114">Fügt einen Listener zu der `sharedListeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="900bc-114">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="900bc-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="900bc-115">Parent Elements</span></span>  
  
|<span data-ttu-id="900bc-116">Element</span><span class="sxs-lookup"><span data-stu-id="900bc-116">Element</span></span>|<span data-ttu-id="900bc-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="900bc-117">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="900bc-118">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="900bc-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="900bc-119">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="900bc-119">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="900bc-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="900bc-120">Remarks</span></span>  

 <span data-ttu-id="900bc-121">Durch das Hinzufügen eines Listener zur Auflistung der freigegebenen Listener wird er nicht zu einem aktiven Listener.</span><span class="sxs-lookup"><span data-stu-id="900bc-121">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="900bc-122">Es muss dennoch einer Ablauf Verfolgungs Quelle oder einer Ablauf Verfolgung hinzugefügt werden, indem es der-Auflistung `Listeners` für dieses Trace-Element hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="900bc-122">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="900bc-123">Die Listenerklassen in der .NET Framework von der- <xref:System.Diagnostics.TraceListener> Klasse abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="900bc-123">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="900bc-124">Dieses Element kann in der Computer Konfigurationsdatei (Machine.config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="900bc-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="900bc-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="900bc-125">Example</span></span>  

 <span data-ttu-id="900bc-126">Im folgenden Beispiel wird gezeigt, wie das `<sharedListeners>` -Element verwendet wird, um den Listener der `console` `Listeners` -Auflistung für die <xref:System.Diagnostics.TraceSource> -Klasse und die- <xref:System.Diagnostics.Trace> Klasse hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="900bc-126">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="900bc-127">Der Ablaufverfolgungslistener der Konsole schreibt Ablauf Verfolgungs Informationen über Aufrufe von oder in die Konsole <xref:System.Diagnostics.TraceSource> <xref:System.Diagnostics.Trace> .</span><span class="sxs-lookup"><span data-stu-id="900bc-127">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="900bc-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="900bc-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="900bc-129">Schema für Ablaufverfolgungs- und Debugeinstellungen</span><span class="sxs-lookup"><span data-stu-id="900bc-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="900bc-130">Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="900bc-130">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
