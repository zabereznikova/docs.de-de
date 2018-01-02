---
title: "&lt;Hinzufügen&gt; -Element für &lt;SharedListeners&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 490e58d4514667c5ec781dd76644012b0c97509d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-element-for-ltsharedlistenersgt"></a><span data-ttu-id="632a4-102">&lt;Hinzufügen&gt; -Element für &lt;SharedListeners&gt;</span><span class="sxs-lookup"><span data-stu-id="632a4-102">&lt;add&gt; Element for &lt;sharedListeners&gt;</span></span>
<span data-ttu-id="632a4-103">Fügt einen Listener zu der `sharedListeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="632a4-103">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="632a4-104">`sharedListeners`eine Auflistung von Listenern, die von jedem ist [ \<Quelle >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) oder [ \<Trace >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md) verweisen können.</span><span class="sxs-lookup"><span data-stu-id="632a4-104">`sharedListeners` is a collection of listeners that any [\<source>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) or [\<trace>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md) can reference.</span></span>  <span data-ttu-id="632a4-105">Standardmäßig Listener in der `sharedListeners` Auflistung befinden sich keinem `Listeners` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="632a4-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="632a4-106">Sie müssen hinzugefügt werden, anhand des Namens der [ \<Quelle >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) oder [ \<Trace >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md).</span><span class="sxs-lookup"><span data-stu-id="632a4-106">They must be added by name to the [\<source>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) or [\<trace>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md).</span></span> <span data-ttu-id="632a4-107">Es ist nicht möglich, den Listener zu erhalten, in der `sharedListeners` Auflistung im Code zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="632a4-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  
  
 <span data-ttu-id="632a4-108">\<configuration></span><span class="sxs-lookup"><span data-stu-id="632a4-108">\<configuration></span></span>  
<span data-ttu-id="632a4-109">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="632a4-109">\<system.diagnostics></span></span>  
<span data-ttu-id="632a4-110">\<SharedListeners >-Element</span><span class="sxs-lookup"><span data-stu-id="632a4-110">\<sharedListeners> Element</span></span>  
<span data-ttu-id="632a4-111">\<add></span><span class="sxs-lookup"><span data-stu-id="632a4-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="632a4-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="632a4-112">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="632a4-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="632a4-113">Attributes and Elements</span></span>  
 <span data-ttu-id="632a4-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="632a4-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="632a4-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="632a4-115">Attributes</span></span>  
  
|<span data-ttu-id="632a4-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="632a4-116">Attribute</span></span>|<span data-ttu-id="632a4-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="632a4-117">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="632a4-118">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="632a4-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="632a4-119">Gibt den Namen des Listeners, den verwendet wird, um die freigegebene Listener zum Hinzufügen einer `Listeners` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="632a4-119">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="632a4-120">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="632a4-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="632a4-121">Gibt den Typ des Listeners.</span><span class="sxs-lookup"><span data-stu-id="632a4-121">Specifies the type of the listener.</span></span> <span data-ttu-id="632a4-122">Müssen Sie eine Zeichenfolge, die im angegebenen Anforderungen erfüllt verwenden [angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="632a4-122">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="632a4-123">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="632a4-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="632a4-124">Die Zeichenfolge, die für die angegebene Klasse an den Konstruktor übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="632a4-124">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="632a4-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="632a4-125">Child Elements</span></span>  
  
|<span data-ttu-id="632a4-126">Element</span><span class="sxs-lookup"><span data-stu-id="632a4-126">Element</span></span>|<span data-ttu-id="632a4-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="632a4-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="632a4-128">\<filter></span><span class="sxs-lookup"><span data-stu-id="632a4-128">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="632a4-129">Fügt einen Filter zu einem Listener in der `sharedListeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="632a4-129">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="632a4-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="632a4-130">Parent Elements</span></span>  
  
|<span data-ttu-id="632a4-131">Element</span><span class="sxs-lookup"><span data-stu-id="632a4-131">Element</span></span>|<span data-ttu-id="632a4-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="632a4-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="632a4-133">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="632a4-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="632a4-134">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="632a4-134">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="632a4-135">Eine Auflistung von Listenern, die jeder Quelle oder das Trace-Element verweisen können.</span><span class="sxs-lookup"><span data-stu-id="632a4-135">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="632a4-136">Hinweise</span><span class="sxs-lookup"><span data-stu-id="632a4-136">Remarks</span></span>  
 <span data-ttu-id="632a4-137">Die Listenerklassen, die im Lieferumfang von .NET Framework abgeleitet werden, aus der <xref:System.Diagnostics.TraceListener> Klasse.</span><span class="sxs-lookup"><span data-stu-id="632a4-137">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="632a4-138">Der Wert für die `name` Attribut wird verwendet, um die freigegebene Listener zum Hinzufügen einer `Listeners` -Auflistung für eine Ablaufverfolgung oder eine Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="632a4-138">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="632a4-139">Der Wert für die `initializeData` Attribut hängt vom Typ des Listeners, die Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="632a4-139">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="632a4-140">Nicht alle Ablaufverfolgungslistener erfordern die Angabe `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="632a4-140">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="632a4-141">Bei Verwendung der `initializeData` -Attribut, erhalten Sie möglicherweise die compilerwarnung "das Attribut"InitializeData"ist nicht deklariert."</span><span class="sxs-lookup"><span data-stu-id="632a4-141">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="632a4-142">Diese Warnung tritt auf, da die Konfigurationseinstellungen für die abstrakte Basisklasse überprüft werden <xref:System.Diagnostics.TraceListener>, die nicht erkennt die `initializeData` Attribut.</span><span class="sxs-lookup"><span data-stu-id="632a4-142">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="632a4-143">In der Regel können Sie diese Warnung für Trace-Listener-Implementierungen ignorieren, die über einen Konstruktor verfügen, der einen Parameter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="632a4-143">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="632a4-144">In der folgenden Tabelle werden die Ablaufverfolgungslistener, die mit .NET Framework enthalten sind, und beschreibt den Wert der ihre `initializeData` Attribute.</span><span class="sxs-lookup"><span data-stu-id="632a4-144">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="632a4-145">Trace Listenerklasse</span><span class="sxs-lookup"><span data-stu-id="632a4-145">Trace listener class</span></span>|<span data-ttu-id="632a4-146">InitializeData-Attribut-Wert</span><span class="sxs-lookup"><span data-stu-id="632a4-146">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="632a4-147">Die `useErrorStream` Wert für die <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="632a4-147">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="632a4-148">Legen Sie die `initializeData` -Attribut auf "`true`"zum Schreiben von Ablaufverfolgung und Debuggen die Ausgabe des Standardfehlerstreams; legen Sie sie auf"`false`" zum Schreiben in den Standardausgabestream.</span><span class="sxs-lookup"><span data-stu-id="632a4-148">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="632a4-149">Der Name der Datei die <xref:System.Diagnostics.DelimitedListTraceListener> schreibt in.</span><span class="sxs-lookup"><span data-stu-id="632a4-149">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="632a4-150">Der Name einer vorhandenen Ereignisprotokoll-Quelle.</span><span class="sxs-lookup"><span data-stu-id="632a4-150">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="632a4-151">Der Name der Datei, die die <xref:System.Diagnostics.EventSchemaTraceListener> schreibt in.</span><span class="sxs-lookup"><span data-stu-id="632a4-151">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="632a4-152">Der Name der Datei, die die <xref:System.Diagnostics.TextWriterTraceListener> schreibt in.</span><span class="sxs-lookup"><span data-stu-id="632a4-152">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="632a4-153">Der Name der Datei, die die <xref:System.Diagnostics.XmlWriterTraceListener> schreibt in.</span><span class="sxs-lookup"><span data-stu-id="632a4-153">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="632a4-154">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="632a4-154">Configuration File</span></span>  
 <span data-ttu-id="632a4-155">Dieses Element kann in der Computerkonfigurationsdatei ("Machine.config") und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="632a4-155">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="632a4-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="632a4-156">Example</span></span>  
 <span data-ttu-id="632a4-157">Das folgende Beispiel zeigt, wie Sie `<add>` hinzuzufügenden Elemente der <xref:System.Diagnostics.TextWriterTraceListener> `textListener` auf die `sharedListeners` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="632a4-157">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="632a4-158">`textListener`anhand des Namens hinzugefügt wird die `Listeners` Auflistung für die Ablaufverfolgungsquelle `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="632a4-158">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="632a4-159">Die `textListener` Listener schreibt die Ablaufverfolgungsausgabe in die Datei myListener.log.</span><span class="sxs-lookup"><span data-stu-id="632a4-159">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"   
        type="System.Diagnostics.TextWriterTraceListener"   
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="632a4-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="632a4-160">See Also</span></span>  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="632a4-161">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="632a4-161">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="632a4-162">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="632a4-162">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
