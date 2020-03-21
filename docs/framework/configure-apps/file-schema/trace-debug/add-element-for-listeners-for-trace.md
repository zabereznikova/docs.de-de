---
title: <add>Element <listeners> für für<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: c64673908dc9afe67d97c08f93e5b9d9533bd34d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153671"
---
# <a name="add-element-for-listeners-for-trace"></a><span data-ttu-id="384f4-102">\<Hinzufügen von \<> Element \<für Listener> für Ablaufverfolgungs-></span><span class="sxs-lookup"><span data-stu-id="384f4-102">\<add> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="384f4-103">Fügt der **Listeners-Auflistung** einen Listener hinzu.</span><span class="sxs-lookup"><span data-stu-id="384f4-103">Adds a listener to the **Listeners** collection.</span></span>  

<span data-ttu-id="384f4-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="384f4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="384f4-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="384f4-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="384f4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<Spur>**](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="384f4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="384f4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Hörer>**](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="384f4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="384f4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<hinzufügen>**</span><span class="sxs-lookup"><span data-stu-id="384f4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="384f4-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="384f4-109">Syntax</span></span>  
  
```xml  
<add name="name"
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="384f4-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="384f4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="384f4-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="384f4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="384f4-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="384f4-112">Attributes</span></span>  
  
|<span data-ttu-id="384f4-113">attribute</span><span class="sxs-lookup"><span data-stu-id="384f4-113">Attribute</span></span>|<span data-ttu-id="384f4-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="384f4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="384f4-115">**Typ**</span><span class="sxs-lookup"><span data-stu-id="384f4-115">**type**</span></span>|<span data-ttu-id="384f4-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="384f4-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="384f4-117">Gibt den Typ des Listeners an.</span><span class="sxs-lookup"><span data-stu-id="384f4-117">Specifies the type of the listener.</span></span> <span data-ttu-id="384f4-118">Sie müssen eine Zeichenfolge verwenden, die die unter [Angeben von vollqualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)angegebenen Anforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="384f4-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="384f4-119">**Initializedata**</span><span class="sxs-lookup"><span data-stu-id="384f4-119">**initializeData**</span></span>|<span data-ttu-id="384f4-120">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="384f4-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="384f4-121">Die Zeichenfolge, die an den Konstruktor für die angegebene Klasse übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="384f4-121">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="384f4-122">**Name**</span><span class="sxs-lookup"><span data-stu-id="384f4-122">**name**</span></span>|<span data-ttu-id="384f4-123">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="384f4-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="384f4-124">Gibt den Namen des Listeners an.</span><span class="sxs-lookup"><span data-stu-id="384f4-124">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="384f4-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="384f4-125">Child Elements</span></span>  
  
|<span data-ttu-id="384f4-126">Element</span><span class="sxs-lookup"><span data-stu-id="384f4-126">Element</span></span>|<span data-ttu-id="384f4-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="384f4-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="384f4-128">\<Filter></span><span class="sxs-lookup"><span data-stu-id="384f4-128">\<filter></span></span>](filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="384f4-129">Fügt einem Listener in `Listeners` der Auflistung einen Filter für eine Ablaufverfolgung hinzu.</span><span class="sxs-lookup"><span data-stu-id="384f4-129">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="384f4-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="384f4-130">Parent Elements</span></span>  
  
|<span data-ttu-id="384f4-131">Element</span><span class="sxs-lookup"><span data-stu-id="384f4-131">Element</span></span>|<span data-ttu-id="384f4-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="384f4-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="384f4-133">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="384f4-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="384f4-134">Gibt einen Listener an, der Nachrichten sammelt, speichert und leitet.</span><span class="sxs-lookup"><span data-stu-id="384f4-134">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="384f4-135">Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel weiter.</span><span class="sxs-lookup"><span data-stu-id="384f4-135">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="384f4-136">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="384f4-136">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="384f4-137">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="384f4-137">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="384f4-138">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="384f4-138">Remarks</span></span>  
 <span data-ttu-id="384f4-139">Die <xref:System.Diagnostics.Debug> <xref:System.Diagnostics.Trace> und die Klassen verwenden dieselbe **Listeners-Auflistung.**</span><span class="sxs-lookup"><span data-stu-id="384f4-139">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="384f4-140">Wenn Sie der Auflistung in einer dieser Klassen ein Listenerobjekt hinzufügen, verwendet die andere Klasse denselben Listener.</span><span class="sxs-lookup"><span data-stu-id="384f4-140">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="384f4-141">Die Listenerklassen leiten <xref:System.Diagnostics.TraceListener>sich von der ab.</span><span class="sxs-lookup"><span data-stu-id="384f4-141">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="384f4-142">Wenn Sie das `name` Attribut des Ablaufverfolgungslisteners nicht angeben, wird der <xref:System.Diagnostics.TraceListener.Name%2A> Ablaufverfolgungslistener standardmäßig auf eine leere Zeichenfolge ("") festgelegt.</span><span class="sxs-lookup"><span data-stu-id="384f4-142">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="384f4-143">Wenn Ihre Anwendung nur über einen Listener verfügt, können Sie sie hinzufügen, ohne einen Namen anzugeben, und sie entfernen, indem Sie eine leere Zeichenfolge für den Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="384f4-143">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="384f4-144">Wenn Ihre Anwendung jedoch über mehr als einen Listener verfügt, sollten Sie eindeutige Namen für jeden <xref:System.Diagnostics.Debug.Listeners%2A> Ablaufverfolgungslistener angeben, mit dem Sie einzelne Ablaufverfolgungslistener innerhalb der und <xref:System.Diagnostics.Trace.Listeners%2A> der Sammlungen identifizieren und verwalten können.</span><span class="sxs-lookup"><span data-stu-id="384f4-144">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="384f4-145">Das Hinzufügen von mehr als einem Ablaufverfolgungslistener desselben Typs und mit demselben Namen führt `Listeners` dazu, dass der Auflistung nur ein Ablaufverfolgungslistener dieses Typs und namens hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="384f4-145">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="384f4-146">Sie können der `Listeners` Auflistung jedoch programmgesteuert mehrere identische Listener hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="384f4-146">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="384f4-147">Der Wert für das **initializeData-Attribut** hängt vom Typ des Listeners ab, den Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="384f4-147">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="384f4-148">Nicht alle Ablaufverfolgungslistener erfordern, dass Sie **initializeData**angeben.</span><span class="sxs-lookup"><span data-stu-id="384f4-148">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="384f4-149">Wenn Sie `initializeData` das Attribut verwenden, erhalten Sie möglicherweise die Compilerwarnung "Das Attribut 'initializeData' ist nicht deklariert."</span><span class="sxs-lookup"><span data-stu-id="384f4-149">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="384f4-150">Diese Warnung wird angezeigt, weil die Konfigurationseinstellungen anhand der abstrakten Basisklasse <xref:System.Diagnostics.TraceListener>überprüft werden, die das `initializeData` Attribut nicht erkennt.</span><span class="sxs-lookup"><span data-stu-id="384f4-150">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="384f4-151">In der Regel können Sie diese Warnung für Ablaufverfolgungslistenerimplementierungen ignorieren, die über einen Konstruktor verfügen, der einen Parameter annimmt.</span><span class="sxs-lookup"><span data-stu-id="384f4-151">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="384f4-152">Die folgende Tabelle zeigt die Ablaufverfolgungslistener, die in .NET Framework enthalten sind, und beschreibt den Wert ihrer **initializeData-Attribute.**</span><span class="sxs-lookup"><span data-stu-id="384f4-152">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="384f4-153">Ablaufverfolgungs-Listenerklasse</span><span class="sxs-lookup"><span data-stu-id="384f4-153">Trace listener class</span></span>|<span data-ttu-id="384f4-154">initializeData-Attributwert</span><span class="sxs-lookup"><span data-stu-id="384f4-154">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="384f4-155">Der `useErrorStream` Wert <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> für den Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="384f4-155">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="384f4-156">Legen `initializeData` Sie das`true`Attribut auf " fest, um die Ablaufverfolgung zu schreiben und die Ausgabe auf zu <xref:System.Console.Error%2A?displayProperty=nameWithType>debuggen. "`false`", um <xref:System.Console.Out%2A?displayProperty=nameWithType>an zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="384f4-156">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="384f4-157">Der Name der Datei, in die der <xref:System.Diagnostics.DelimitedListTraceListener> schreibt.</span><span class="sxs-lookup"><span data-stu-id="384f4-157">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="384f4-158">Der Name des Namens einer vorhandenen Ereignisprotokollquelle.</span><span class="sxs-lookup"><span data-stu-id="384f4-158">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="384f4-159">Der Name der Datei, in die die <xref:System.Diagnostics.EventSchemaTraceListener> Datei schreibt.</span><span class="sxs-lookup"><span data-stu-id="384f4-159">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="384f4-160">Der Name der Datei, in die die <xref:System.Diagnostics.TextWriterTraceListener> Datei schreibt.</span><span class="sxs-lookup"><span data-stu-id="384f4-160">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="384f4-161">Der Name der Datei, in die die <xref:System.Diagnostics.XmlWriterTraceListener> Datei schreibt.</span><span class="sxs-lookup"><span data-stu-id="384f4-161">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="384f4-162">Beispiel</span><span class="sxs-lookup"><span data-stu-id="384f4-162">Example</span></span>  
 <span data-ttu-id="384f4-163">Das folgende Beispiel zeigt, wie \*\* \<Sie>\*\* `MyEventListener` Elemente zum Hinzufügen der Listener `MyListener` und zur **Listener-Auflistung** verwenden.</span><span class="sxs-lookup"><span data-stu-id="384f4-163">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="384f4-164">`MyListener`erstellt eine `MyListener.log` aufgerufene Datei und schreibt die Ausgabe in die Datei.</span><span class="sxs-lookup"><span data-stu-id="384f4-164">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="384f4-165">`MyEventListener`erstellt einen Eintrag im Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="384f4-165">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="384f4-166">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="384f4-166">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [<span data-ttu-id="384f4-167">Ablaufverfolgungs- und Debugeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="384f4-167">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="384f4-168">Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="384f4-168">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
