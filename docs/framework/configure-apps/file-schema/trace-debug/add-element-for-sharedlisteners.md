---
title: <add>-Element für <sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
ms.openlocfilehash: c4b83834fb7aaf64a696b85bd2c8da47cfba2397
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927209"
---
# <a name="add-element-for-sharedlisteners"></a><span data-ttu-id="27cdb-102">\<Fügen Sie >- \<Element für sharedlistener hinzu ></span><span class="sxs-lookup"><span data-stu-id="27cdb-102">\<add> Element for \<sharedListeners></span></span>
<span data-ttu-id="27cdb-103">Fügt einen Listener zu der `sharedListeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="27cdb-103">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="27cdb-104">`sharedListeners`eine Auflistung von Listenern, auf die beliebige [ \<Quell >](source-element.md) oder [ \<Ablauf Verfolgungs >](trace-element.md) verweisen können.</span><span class="sxs-lookup"><span data-stu-id="27cdb-104">`sharedListeners` is a collection of listeners that any [\<source>](source-element.md) or [\<trace>](trace-element.md) can reference.</span></span>  <span data-ttu-id="27cdb-105">Standardmäßig werden Listener in der `sharedListeners` Auflistung nicht in eine `Listeners` Auflistung eingefügt.</span><span class="sxs-lookup"><span data-stu-id="27cdb-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="27cdb-106">Sie müssen dem [ \<Quell->](source-element.md) oder [ \<Ablauf Verfolgungs >](trace-element.md)nach Name hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="27cdb-106">They must be added by name to the [\<source>](source-element.md) or [\<trace>](trace-element.md).</span></span> <span data-ttu-id="27cdb-107">Es ist nicht möglich, die Listener in der `sharedListeners` Auflistung zur Laufzeit im Code zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="27cdb-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  
  
 <span data-ttu-id="27cdb-108">\<configuration></span><span class="sxs-lookup"><span data-stu-id="27cdb-108">\<configuration></span></span>  
<span data-ttu-id="27cdb-109">&nbsp;&nbsp;\<System. Diagnostics-></span><span class="sxs-lookup"><span data-stu-id="27cdb-109">&nbsp;&nbsp;\<system.diagnostics></span></span>  
<span data-ttu-id="27cdb-110">&nbsp;&nbsp;&nbsp;&nbsp;\<sharedlistener-> Element</span><span class="sxs-lookup"><span data-stu-id="27cdb-110">&nbsp;&nbsp;&nbsp;&nbsp;\<sharedListeners> Element</span></span>  
<span data-ttu-id="27cdb-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<add></span><span class="sxs-lookup"><span data-stu-id="27cdb-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27cdb-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="27cdb-112">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27cdb-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="27cdb-113">Attributes and Elements</span></span>  
 <span data-ttu-id="27cdb-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="27cdb-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27cdb-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="27cdb-115">Attributes</span></span>  
  
|<span data-ttu-id="27cdb-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="27cdb-116">Attribute</span></span>|<span data-ttu-id="27cdb-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="27cdb-117">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="27cdb-118">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="27cdb-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="27cdb-119">Gibt den Namen des Listener an, der verwendet wird, um den freigegebenen Listener `Listeners` einer Auflistung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="27cdb-119">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="27cdb-120">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="27cdb-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="27cdb-121">Gibt den Typ des Listener an.</span><span class="sxs-lookup"><span data-stu-id="27cdb-121">Specifies the type of the listener.</span></span> <span data-ttu-id="27cdb-122">Sie müssen eine Zeichenfolge verwenden, die den unter [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)angegebenen Anforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="27cdb-122">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="27cdb-123">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="27cdb-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="27cdb-124">Die Zeichenfolge, die an den Konstruktor für die angegebene Klasse übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="27cdb-124">The string passed to the constructor for the specified class.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="27cdb-125">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="27cdb-125">Optional attribute.</span></span><br/><br/><span data-ttu-id="27cdb-126">Die Zeichen folgen Darstellung eines oder mehrerer <xref:System.Diagnostics.TraceOptions> Enumerationsmember, die die Daten angibt, die in die Ablauf Verfolgungs Ausgabe geschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="27cdb-126">The string representation of one or more <xref:System.Diagnostics.TraceOptions> enumeration members that indicates the data to be written to the trace output.</span></span> <span data-ttu-id="27cdb-127">Mehrere Elemente werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="27cdb-127">Multiple items are separated by commas.</span></span> <span data-ttu-id="27cdb-128">Der Standardwert ist "None".</span><span class="sxs-lookup"><span data-stu-id="27cdb-128">The default value is "None".</span></span>|

### <a name="child-elements"></a><span data-ttu-id="27cdb-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="27cdb-129">Child Elements</span></span>  
  
|<span data-ttu-id="27cdb-130">Element</span><span class="sxs-lookup"><span data-stu-id="27cdb-130">Element</span></span>|<span data-ttu-id="27cdb-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="27cdb-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27cdb-132">\<filter></span><span class="sxs-lookup"><span data-stu-id="27cdb-132">\<filter></span></span>](filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="27cdb-133">Fügt einen Filter zu einem Listener in der `sharedListeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="27cdb-133">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="27cdb-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="27cdb-134">Parent Elements</span></span>  
  
|<span data-ttu-id="27cdb-135">Element</span><span class="sxs-lookup"><span data-stu-id="27cdb-135">Element</span></span>|<span data-ttu-id="27cdb-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="27cdb-136">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="27cdb-137">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="27cdb-137">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="27cdb-138">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="27cdb-138">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="27cdb-139">Eine Auflistung von Listenern, auf die beliebige Quell-oder Ablauf Verfolgungs Elemente verweisen können.</span><span class="sxs-lookup"><span data-stu-id="27cdb-139">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27cdb-140">Hinweise</span><span class="sxs-lookup"><span data-stu-id="27cdb-140">Remarks</span></span>  
 <span data-ttu-id="27cdb-141">Die Listenerklassen, die mit dem .NET Framework ausgeliefert <xref:System.Diagnostics.TraceListener> werden, werden von der-Klasse abgeleitet</span><span class="sxs-lookup"><span data-stu-id="27cdb-141">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="27cdb-142">Der Wert für das `name` -Attribut wird verwendet, um den freigegebenen Listener `Listeners` einer Auflistung entweder für eine Ablauf Verfolgung oder eine Ablauf Verfolgungs Quelle hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="27cdb-142">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="27cdb-143">Der Wert für das `initializeData` -Attribut ist abhängig vom Typ des von Ihnen erstellten Listener.</span><span class="sxs-lookup"><span data-stu-id="27cdb-143">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="27cdb-144">Nicht alle Ablaufverfolgungslistener erfordern, dass Sie angeben `initializeData`</span><span class="sxs-lookup"><span data-stu-id="27cdb-144">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="27cdb-145">Wenn Sie das `initializeData` -Attribut verwenden, erhalten Sie möglicherweise die Compilerwarnung, dass das initializeData-Attribut nicht deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="27cdb-145">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="27cdb-146">Diese Warnung tritt auf, weil die Konfigurationseinstellungen anhand der abstrakten Basisklasse <xref:System.Diagnostics.TraceListener>überprüft werden, die das `initializeData` -Attribut nicht erkennt.</span><span class="sxs-lookup"><span data-stu-id="27cdb-146">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="27cdb-147">Normalerweise können Sie diese Warnung für Ablaufverfolgungslistener-Implementierungen ignorieren, die über einen Konstruktor verfügen, der einen Parameter annimmt</span><span class="sxs-lookup"><span data-stu-id="27cdb-147">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="27cdb-148">In der folgenden Tabelle werden die Ablaufverfolgungslistener angezeigt, die im .NET Framework enthalten `initializeData` sind, und der Wert ihrer Attribute wird beschrieben.</span><span class="sxs-lookup"><span data-stu-id="27cdb-148">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="27cdb-149">Trace-Listenerklasse</span><span class="sxs-lookup"><span data-stu-id="27cdb-149">Trace listener class</span></span>|<span data-ttu-id="27cdb-150">initializeData-Attribut Wert</span><span class="sxs-lookup"><span data-stu-id="27cdb-150">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="27cdb-151">Der `useErrorStream` Wert für den <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="27cdb-151">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="27cdb-152">Legen Sie `initializeData` das-Attribut`true`auf "" fest, um die Ablauf Verfolgung und Debugausgabe in den Standardfehlerstream zu schreiben. Legen Sie Sie auf "`false`" fest</span><span class="sxs-lookup"><span data-stu-id="27cdb-152">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="27cdb-153">Der Name der Datei, in <xref:System.Diagnostics.DelimitedListTraceListener> die geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="27cdb-153">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="27cdb-154">Der Name einer vorhandenen Ereignisprotokoll Quelle.</span><span class="sxs-lookup"><span data-stu-id="27cdb-154">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="27cdb-155">Der Name der Datei, in die <xref:System.Diagnostics.EventSchemaTraceListener> geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="27cdb-155">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="27cdb-156">Der Name der Datei, in die <xref:System.Diagnostics.TextWriterTraceListener> geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="27cdb-156">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="27cdb-157">Der Name der Datei, in die <xref:System.Diagnostics.XmlWriterTraceListener> geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="27cdb-157">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="27cdb-158">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="27cdb-158">Configuration File</span></span>  
 <span data-ttu-id="27cdb-159">Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="27cdb-159">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27cdb-160">Beispiel</span><span class="sxs-lookup"><span data-stu-id="27cdb-160">Example</span></span>  
 <span data-ttu-id="27cdb-161">Im folgenden Beispiel wird gezeigt, wie `<add>` -Elemente verwendet werden <xref:System.Diagnostics.TextWriterTraceListener> , um `sharedListeners` der `textListener` -Auflistung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="27cdb-161">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="27cdb-162">`textListener`wird der `Listeners` -Auflistung für die Ablauf Verfolgungs Quelle `TraceSourceApp`nach Name hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="27cdb-162">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="27cdb-163">Der `textListener` Listener schreibt die Ablauf Verfolgungs Ausgabe in die Datei "MyListener. log".</span><span class="sxs-lookup"><span data-stu-id="27cdb-163">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="27cdb-164">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27cdb-164">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="27cdb-165">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="27cdb-165">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="27cdb-166">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="27cdb-166">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
