---
title: <add> -Element für <listeners> für <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: ba0ffc4f95b9af7fcd319068501ce0bb9714c2ad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089575"
---
# <a name="add-element-for-listeners-for-trace"></a><span data-ttu-id="fcc76-102">\<Hinzufügen >-Element für \<Listener > für \<Ablaufverfolgung ></span><span class="sxs-lookup"><span data-stu-id="fcc76-102">\<add> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="fcc76-103">Fügt einen Listener, damit die **Listener** Auflistung.</span><span class="sxs-lookup"><span data-stu-id="fcc76-103">Adds a listener to the **Listeners** collection.</span></span>  
  
 <span data-ttu-id="fcc76-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="fcc76-104">\<configuration></span></span>  
<span data-ttu-id="fcc76-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="fcc76-105">\<system.diagnostics></span></span>  
<span data-ttu-id="fcc76-106">\<trace></span><span class="sxs-lookup"><span data-stu-id="fcc76-106">\<trace></span></span>  
<span data-ttu-id="fcc76-107">\<listeners></span><span class="sxs-lookup"><span data-stu-id="fcc76-107">\<listeners></span></span>  
<span data-ttu-id="fcc76-108">\<add></span><span class="sxs-lookup"><span data-stu-id="fcc76-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcc76-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="fcc76-109">Syntax</span></span>  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fcc76-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fcc76-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fcc76-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fcc76-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fcc76-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="fcc76-112">Attributes</span></span>  
  
|<span data-ttu-id="fcc76-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="fcc76-113">Attribute</span></span>|<span data-ttu-id="fcc76-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fcc76-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fcc76-115">**Typ**</span><span class="sxs-lookup"><span data-stu-id="fcc76-115">**type**</span></span>|<span data-ttu-id="fcc76-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="fcc76-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="fcc76-117">Gibt den Typ des Listeners.</span><span class="sxs-lookup"><span data-stu-id="fcc76-117">Specifies the type of the listener.</span></span> <span data-ttu-id="fcc76-118">Sie müssen eine Zeichenfolge, die die in angegebenen Anforderungen erfüllt verwenden [angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="fcc76-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="fcc76-119">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="fcc76-119">**initializeData**</span></span>|<span data-ttu-id="fcc76-120">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="fcc76-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="fcc76-121">Die Zeichenfolge, die für die angegebene Klasse an den Konstruktor übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="fcc76-121">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="fcc76-122">**name**</span><span class="sxs-lookup"><span data-stu-id="fcc76-122">**name**</span></span>|<span data-ttu-id="fcc76-123">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="fcc76-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="fcc76-124">Gibt den Namen des Listeners.</span><span class="sxs-lookup"><span data-stu-id="fcc76-124">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fcc76-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fcc76-125">Child Elements</span></span>  
  
|<span data-ttu-id="fcc76-126">Element</span><span class="sxs-lookup"><span data-stu-id="fcc76-126">Element</span></span>|<span data-ttu-id="fcc76-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fcc76-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fcc76-128">\<filter></span><span class="sxs-lookup"><span data-stu-id="fcc76-128">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="fcc76-129">Fügt einen Filter zu einem Listener in der `Listeners` Sammlung für eine Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="fcc76-129">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fcc76-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fcc76-130">Parent Elements</span></span>  
  
|<span data-ttu-id="fcc76-131">Element</span><span class="sxs-lookup"><span data-stu-id="fcc76-131">Element</span></span>|<span data-ttu-id="fcc76-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fcc76-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fcc76-133">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="fcc76-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="fcc76-134">Gibt an, einen Listener, der sammelt, speichert, und leitet Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="fcc76-134">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="fcc76-135">Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel.</span><span class="sxs-lookup"><span data-stu-id="fcc76-135">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="fcc76-136">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="fcc76-136">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="fcc76-137">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="fcc76-137">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fcc76-138">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fcc76-138">Remarks</span></span>  
 <span data-ttu-id="fcc76-139">Die <xref:System.Diagnostics.Debug> und <xref:System.Diagnostics.Trace> Klassen verwenden dieselbe **Listener** Auflistung.</span><span class="sxs-lookup"><span data-stu-id="fcc76-139">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="fcc76-140">Wenn Sie einen Listener-Objekt der Auflistung in einer dieser Klassen hinzufügen, wird die andere Klasse den gleichen Listener verwendet.</span><span class="sxs-lookup"><span data-stu-id="fcc76-140">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="fcc76-141">Die Listenerklassen leiten sich von der <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="fcc76-141">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="fcc76-142">Wenn Sie keinen angeben der `name` Attribut des Ablaufverfolgungslisteners, der <xref:System.Diagnostics.TraceListener.Name%2A> die Trace-Listener-Standardwerte in eine leere Zeichenfolge ("").</span><span class="sxs-lookup"><span data-stu-id="fcc76-142">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="fcc76-143">Wenn Ihre Anwendung nur einen Listener verfügt, können Sie ohne Angabe eines Namens hinzufügen und entfernen sie, indem Sie eine leere Zeichenfolge für den Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="fcc76-143">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="fcc76-144">Wenn Ihre Anwendung mehr als einen Listener verfügt, Sie jedoch sollte angeben eindeutige Namen für jeden Ablaufverfolgungslistener, wodurch Sie zum Erkennen und Verwalten von einzelnen Ablaufverfolgungslistener in der <xref:System.Diagnostics.Debug.Listeners%2A> und <xref:System.Diagnostics.Trace.Listeners%2A> Sammlungen.</span><span class="sxs-lookup"><span data-stu-id="fcc76-144">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fcc76-145">Hinzufügen von mehr als eine Ablaufverfolgungs-Listener des gleichen Typs und mit dem gleichen nennen Sie dieses Typs führt nur eine Ablaufverfolgungs-Listener und hinzugefügte der `Listeners` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="fcc76-145">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="fcc76-146">Allerdings können Sie programmgesteuert mehrere identische Listener hinzufügen der `Listeners` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="fcc76-146">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="fcc76-147">Der Wert für die **InitializeData** -Attributs hängt der Typ des Listeners, die Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="fcc76-147">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="fcc76-148">Nicht alle Ablaufverfolgungslistener erfordern die Angabe **InitializeData**.</span><span class="sxs-lookup"><span data-stu-id="fcc76-148">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fcc76-149">Bei Verwendung der `initializeData` -Attribut, erhalten Sie möglicherweise die compilerwarnung "das Attribut"InitializeData"ist nicht deklariert."</span><span class="sxs-lookup"><span data-stu-id="fcc76-149">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="fcc76-150">Diese Warnung tritt auf, da die Konfigurationseinstellungen für die abstrakte Basisklasse überprüft werden <xref:System.Diagnostics.TraceListener>, die nicht erkennt die `initializeData` Attribut.</span><span class="sxs-lookup"><span data-stu-id="fcc76-150">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="fcc76-151">In der Regel können Sie Ablaufverfolgungs-Listener-Implementierungen diese Warnung ignorieren, die über einen Konstruktor verfügen, der einen Parameter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="fcc76-151">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="fcc76-152">In der folgende Tabelle werden die Ablaufverfolgungslistener, die mit .NET Framework enthalten sind, und beschreibt den Wert der ihre **InitializeData** Attribute.</span><span class="sxs-lookup"><span data-stu-id="fcc76-152">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="fcc76-153">Trace Listenerklasse</span><span class="sxs-lookup"><span data-stu-id="fcc76-153">Trace listener class</span></span>|<span data-ttu-id="fcc76-154">InitializeData-Attributwert</span><span class="sxs-lookup"><span data-stu-id="fcc76-154">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="fcc76-155">Die `useErrorStream` Wert für die <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="fcc76-155">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="fcc76-156">Legen Sie die `initializeData` -Attribut auf "`true`" Ablaufverfolgungs- und Debugeinstellungen schreiben die Ausgabe <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" zum Schreiben in <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fcc76-156">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="fcc76-157">Der Name der Datei die <xref:System.Diagnostics.DelimitedListTraceListener> schreibt in.</span><span class="sxs-lookup"><span data-stu-id="fcc76-157">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="fcc76-158">Der Name des Namens einer vorhandenen Ereignisprotokollquelle.</span><span class="sxs-lookup"><span data-stu-id="fcc76-158">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="fcc76-159">Der Name der Datei, die die <xref:System.Diagnostics.EventSchemaTraceListener> schreibt in.</span><span class="sxs-lookup"><span data-stu-id="fcc76-159">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="fcc76-160">Der Name der Datei, die die <xref:System.Diagnostics.TextWriterTraceListener> schreibt in.</span><span class="sxs-lookup"><span data-stu-id="fcc76-160">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="fcc76-161">Der Name der Datei, die die <xref:System.Diagnostics.XmlWriterTraceListener> schreibt in.</span><span class="sxs-lookup"><span data-stu-id="fcc76-161">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fcc76-162">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fcc76-162">Example</span></span>  
 <span data-ttu-id="fcc76-163">Das folgende Beispiel zeigt, wie Sie mit  **\<hinzufügen >** Elemente, die Listener hinzugefügt `MyListener` und `MyEventListener` auf die **Listener** Auflistung.</span><span class="sxs-lookup"><span data-stu-id="fcc76-163">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="fcc76-164">`MyListener` erstellt eine Datei namens `MyListener.log` und schreibt die Ausgabe in der Datei.</span><span class="sxs-lookup"><span data-stu-id="fcc76-164">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="fcc76-165">`MyEventListener` erstellt einen Eintrag im Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="fcc76-165">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
            <add name="MyEventListener"  
                 type="System.Diagnostics.EventLogTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"                 initializeData="MyConfigEventLog"/>  
            <add name="configConsoleListener"  
                 type="System.Diagnostics.ConsoleTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fcc76-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fcc76-166">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [<span data-ttu-id="fcc76-167">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="fcc76-167">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="fcc76-168">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="fcc76-168">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
