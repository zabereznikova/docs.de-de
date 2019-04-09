---
title: <add> Element für <sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
ms.openlocfilehash: e7934ed5e71005cfd28271298ff6ce1eb8829a0d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59095632"
---
# <a name="add-element-for-sharedlisteners"></a><span data-ttu-id="fc671-102">\<Hinzufügen >-Element für \<SharedListeners ></span><span class="sxs-lookup"><span data-stu-id="fc671-102">\<add> Element for \<sharedListeners></span></span>
<span data-ttu-id="fc671-103">Fügt einen Listener zu der `sharedListeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="fc671-103">Adds a listener to the `sharedListeners` collection.</span></span> `sharedListeners` <span data-ttu-id="fc671-104">eine Sammlung von Listenern, die von jedem ist [ \<Quelle >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) oder [ \<Ablaufverfolgung >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md) verweisen können.</span><span class="sxs-lookup"><span data-stu-id="fc671-104">is a collection of listeners that any [\<source>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) or [\<trace>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md) can reference.</span></span>  <span data-ttu-id="fc671-105">Standardmäßig werden von Listenern in der `sharedListeners` Auflistung befinden sich keine `Listeners` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="fc671-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="fc671-106">Sie müssen hinzugefügt werden, anhand des Namens der [ \<Quelle >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) oder [ \<Ablaufverfolgung >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md).</span><span class="sxs-lookup"><span data-stu-id="fc671-106">They must be added by name to the [\<source>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) or [\<trace>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md).</span></span> <span data-ttu-id="fc671-107">Es ist nicht möglich, um die Listener in der `sharedListeners` Auflistung im Code zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="fc671-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  
  
 <span data-ttu-id="fc671-108">\<configuration></span><span class="sxs-lookup"><span data-stu-id="fc671-108">\<configuration></span></span>  
<span data-ttu-id="fc671-109">&nbsp;&nbsp;\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="fc671-109">&nbsp;&nbsp;\<system.diagnostics></span></span>  
<span data-ttu-id="fc671-110">&nbsp;&nbsp;&nbsp;&nbsp;\<SharedListeners >-Element</span><span class="sxs-lookup"><span data-stu-id="fc671-110">&nbsp;&nbsp;&nbsp;&nbsp;\<sharedListeners> Element</span></span>  
<span data-ttu-id="fc671-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<add></span><span class="sxs-lookup"><span data-stu-id="fc671-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc671-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc671-112">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc671-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fc671-113">Attributes and Elements</span></span>  
 <span data-ttu-id="fc671-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fc671-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc671-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="fc671-115">Attributes</span></span>  
  
|<span data-ttu-id="fc671-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="fc671-116">Attribute</span></span>|<span data-ttu-id="fc671-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc671-117">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="fc671-118">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="fc671-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="fc671-119">Gibt den Namen des Listeners, mit dem den freigegebenen Listener zum Hinzufügen, einer `Listeners` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="fc671-119">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="fc671-120">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="fc671-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="fc671-121">Gibt den Typ des Listeners.</span><span class="sxs-lookup"><span data-stu-id="fc671-121">Specifies the type of the listener.</span></span> <span data-ttu-id="fc671-122">Sie müssen eine Zeichenfolge, die die in angegebenen Anforderungen erfüllt verwenden [angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="fc671-122">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="fc671-123">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="fc671-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="fc671-124">Die Zeichenfolge, die für die angegebene Klasse an den Konstruktor übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="fc671-124">The string passed to the constructor for the specified class.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="fc671-125">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="fc671-125">Optional attribute.</span></span><br/><br/><span data-ttu-id="fc671-126">Die Zeichenfolgendarstellung von einem oder mehreren <xref:System.Diagnostics.TraceOptions> Enumerationsmember, der die Daten in die Ablaufverfolgungsausgabe geschrieben werden angibt.</span><span class="sxs-lookup"><span data-stu-id="fc671-126">The string representation of one or more <xref:System.Diagnostics.TraceOptions> enumeration members that indicates the data to be written to the trace output.</span></span> <span data-ttu-id="fc671-127">Mehrere Elemente werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="fc671-127">Multiple items are separated by commas.</span></span> <span data-ttu-id="fc671-128">Der Standardwert ist "None".</span><span class="sxs-lookup"><span data-stu-id="fc671-128">The default value is "None".</span></span>|

### <a name="child-elements"></a><span data-ttu-id="fc671-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fc671-129">Child Elements</span></span>  
  
|<span data-ttu-id="fc671-130">Element</span><span class="sxs-lookup"><span data-stu-id="fc671-130">Element</span></span>|<span data-ttu-id="fc671-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc671-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc671-132">\<filter></span><span class="sxs-lookup"><span data-stu-id="fc671-132">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="fc671-133">Fügt einen Filter zu einem Listener in der `sharedListeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="fc671-133">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fc671-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fc671-134">Parent Elements</span></span>  
  
|<span data-ttu-id="fc671-135">Element</span><span class="sxs-lookup"><span data-stu-id="fc671-135">Element</span></span>|<span data-ttu-id="fc671-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc671-136">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fc671-137">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="fc671-137">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="fc671-138">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="fc671-138">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="fc671-139">Eine Auflistung der Listener, die jedes Quell- oder Ablaufverfolgungselement verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="fc671-139">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc671-140">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fc671-140">Remarks</span></span>  
 <span data-ttu-id="fc671-141">Die Listenerklassen, die im Lieferumfang von .NET Framework leiten sich von der <xref:System.Diagnostics.TraceListener> Klasse.</span><span class="sxs-lookup"><span data-stu-id="fc671-141">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="fc671-142">Der Wert für die `name` Attribut wird verwendet, um den freigegebenen Listener zum Hinzufügen einer `Listeners` Sammlung für eine Ablaufverfolgung oder eine Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="fc671-142">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="fc671-143">Der Wert für die `initializeData` -Attributs hängt der Typ des Listeners, die Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="fc671-143">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="fc671-144">Nicht alle Ablaufverfolgungslistener erfordern die Angabe `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="fc671-144">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc671-145">Bei Verwendung der `initializeData` -Attribut, erhalten Sie möglicherweise die compilerwarnung "das Attribut"InitializeData"ist nicht deklariert."</span><span class="sxs-lookup"><span data-stu-id="fc671-145">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="fc671-146">Diese Warnung tritt auf, da die Konfigurationseinstellungen für die abstrakte Basisklasse überprüft werden <xref:System.Diagnostics.TraceListener>, die nicht erkennt die `initializeData` Attribut.</span><span class="sxs-lookup"><span data-stu-id="fc671-146">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="fc671-147">In der Regel können Sie Ablaufverfolgungs-Listener-Implementierungen diese Warnung ignorieren, die über einen Konstruktor verfügen, der einen Parameter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="fc671-147">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="fc671-148">In der folgende Tabelle werden die Ablaufverfolgungslistener, die mit .NET Framework enthalten sind, und beschreibt den Wert der ihre `initializeData` Attribute.</span><span class="sxs-lookup"><span data-stu-id="fc671-148">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="fc671-149">Trace Listenerklasse</span><span class="sxs-lookup"><span data-stu-id="fc671-149">Trace listener class</span></span>|<span data-ttu-id="fc671-150">InitializeData-Attributwert</span><span class="sxs-lookup"><span data-stu-id="fc671-150">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="fc671-151">Die `useErrorStream` Wert für die <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="fc671-151">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="fc671-152">Legen Sie die `initializeData` -Attribut auf "`true`"Schreiben Ausgabe von Ablaufverfolgungs- und Debugeinstellungen in den Standardfehlerstream; so eingestellt, es"`false`" zum Schreiben in den Standardausgabestream.</span><span class="sxs-lookup"><span data-stu-id="fc671-152">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="fc671-153">Der Name der Datei die <xref:System.Diagnostics.DelimitedListTraceListener> schreibt in.</span><span class="sxs-lookup"><span data-stu-id="fc671-153">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="fc671-154">Der Name einer vorhandenen Ereignisprotokollquelle.</span><span class="sxs-lookup"><span data-stu-id="fc671-154">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="fc671-155">Der Name der Datei, die die <xref:System.Diagnostics.EventSchemaTraceListener> schreibt in.</span><span class="sxs-lookup"><span data-stu-id="fc671-155">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="fc671-156">Der Name der Datei, die die <xref:System.Diagnostics.TextWriterTraceListener> schreibt in.</span><span class="sxs-lookup"><span data-stu-id="fc671-156">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="fc671-157">Der Name der Datei, die die <xref:System.Diagnostics.XmlWriterTraceListener> schreibt in.</span><span class="sxs-lookup"><span data-stu-id="fc671-157">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="fc671-158">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="fc671-158">Configuration File</span></span>  
 <span data-ttu-id="fc671-159">Dieses Element kann in der Computerkonfigurationsdatei (Machine.config) und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fc671-159">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc671-160">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc671-160">Example</span></span>  
 <span data-ttu-id="fc671-161">Das folgende Beispiel zeigt, wie Sie mit `<add>` hinzuzufügenden Elemente der <xref:System.Diagnostics.TextWriterTraceListener>`textListener` auf die `sharedListeners` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="fc671-161">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   `textListener` <span data-ttu-id="fc671-162">wurde anhand des Namens der `Listeners` Auflistung für die Ablaufverfolgungsquelle `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="fc671-162">is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="fc671-163">Die `textListener` -Listener schreibt die Ausgabe der Ablaufverfolgung in die Datei myListener.log.</span><span class="sxs-lookup"><span data-stu-id="fc671-163">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fc671-164">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc671-164">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="fc671-165">Schema für Ablaufverfolgungs- und Debugeinstellungen</span><span class="sxs-lookup"><span data-stu-id="fc671-165">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="fc671-166">Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="fc671-166">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
