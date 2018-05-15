---
title: '&lt;Listener&gt; -Element für &lt;Trace&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 2f0d795d6a8789772ff3fd46648fbc0d683c66e5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltlistenersgt-element-for-lttracegt"></a><span data-ttu-id="d38ce-102">&lt;Listener&gt; -Element für &lt;Trace&gt;</span><span class="sxs-lookup"><span data-stu-id="d38ce-102">&lt;listeners&gt; Element for &lt;trace&gt;</span></span>
<span data-ttu-id="d38ce-103">Gibt an, einen Listener, der erfasst hat, speichert, und leitet Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="d38ce-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="d38ce-104">Listener leiten die Ablaufverfolgungsausgabe an ein geeignetes Ziel an.</span><span class="sxs-lookup"><span data-stu-id="d38ce-104">Listeners direct the tracing output to an appropriate target.</span></span>  
  
 <span data-ttu-id="d38ce-105">\<Konfiguration >-Element</span><span class="sxs-lookup"><span data-stu-id="d38ce-105">\<configuration> Element</span></span>  
<span data-ttu-id="d38ce-106">\<System.Diagnostics > Element</span><span class="sxs-lookup"><span data-stu-id="d38ce-106">\<system.diagnostics> Element</span></span>  
<span data-ttu-id="d38ce-107">\<Trace >-Element</span><span class="sxs-lookup"><span data-stu-id="d38ce-107">\<trace> Element</span></span>  
<span data-ttu-id="d38ce-108">\<Listener >-Element für \<Trace ></span><span class="sxs-lookup"><span data-stu-id="d38ce-108">\<listeners> Element for \<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d38ce-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="d38ce-109">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d38ce-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d38ce-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d38ce-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d38ce-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d38ce-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="d38ce-112">Attributes</span></span>  
 <span data-ttu-id="d38ce-113">Keine</span><span class="sxs-lookup"><span data-stu-id="d38ce-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d38ce-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d38ce-114">Child Elements</span></span>  
  
|<span data-ttu-id="d38ce-115">Element</span><span class="sxs-lookup"><span data-stu-id="d38ce-115">Element</span></span>|<span data-ttu-id="d38ce-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d38ce-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d38ce-117">\<add></span><span class="sxs-lookup"><span data-stu-id="d38ce-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|<span data-ttu-id="d38ce-118">Fügt einen Listener zu der `Listeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="d38ce-118">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="d38ce-119">\<clear></span><span class="sxs-lookup"><span data-stu-id="d38ce-119">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-trace.md)|<span data-ttu-id="d38ce-120">Löscht die `Listeners`-Sammlung für die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="d38ce-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="d38ce-121">\<remove></span><span class="sxs-lookup"><span data-stu-id="d38ce-121">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)|<span data-ttu-id="d38ce-122">Entfernt einen Listener aus der `Listeners` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="d38ce-122">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d38ce-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d38ce-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d38ce-124">Element</span><span class="sxs-lookup"><span data-stu-id="d38ce-124">Element</span></span>|<span data-ttu-id="d38ce-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d38ce-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d38ce-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="d38ce-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="d38ce-127">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="d38ce-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="d38ce-128">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="d38ce-128">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d38ce-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d38ce-129">Remarks</span></span>  
 <span data-ttu-id="d38ce-130">Die <xref:System.Diagnostics.Debug> und <xref:System.Diagnostics.Trace> Klassen verwenden dieselbe **Listener** Auflistung.</span><span class="sxs-lookup"><span data-stu-id="d38ce-130">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="d38ce-131">Wenn Sie der Auflistung in einer dieser Klassen ein Listener-Objekt hinzugefügt haben, verwendet die andere Klasse denselben Listener.</span><span class="sxs-lookup"><span data-stu-id="d38ce-131">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="d38ce-132">Die Listenerklassen, die im Lieferumfang von .NET Framework abgeleitet werden, aus der <xref:System.Diagnostics.TraceListener> Klasse.</span><span class="sxs-lookup"><span data-stu-id="d38ce-132">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="d38ce-133">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="d38ce-133">Configuration File</span></span>  
 <span data-ttu-id="d38ce-134">Dieses Element kann in der Computerkonfigurationsdatei ("Machine.config") und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d38ce-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d38ce-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d38ce-135">Example</span></span>  
 <span data-ttu-id="d38ce-136">Das folgende Beispiel zeigt, wie Sie die  **\<Listener >** Listener hinzuzufügenden Elements `MyListener` und `MyEventListener` auf die **Listener** Auflistung.</span><span class="sxs-lookup"><span data-stu-id="d38ce-136">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="d38ce-137">`MyListener` erstellt eine Datei namens `MyListener.log` und schreibt die Ausgabe in die Datei.</span><span class="sxs-lookup"><span data-stu-id="d38ce-137">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="d38ce-138">`MyEventListener` erstellt einen Eintrag im Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="d38ce-138">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="true" indentsize="0">  
      <listeners>  
        <add name="myListener"   
          type="System.Diagnostics.TextWriterTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"   
          initializeData="c:\myListener.log" />  
        <add name="MyEventListener"  
          type="System.Diagnostics.EventLogTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"  
          initializeData="MyConfigEventLog"/>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d38ce-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d38ce-139">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="d38ce-140">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="d38ce-140">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
