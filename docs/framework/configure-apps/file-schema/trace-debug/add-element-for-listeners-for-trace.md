---
title: <add> Element für <listeners> für <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: eb3e9cf4a6d138998cfde865cda8ed4146be26d0
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088983"
---
# <a name="add-element-for-listeners-for-trace"></a><span data-ttu-id="c5f20-102">\<> Element für \<Listener > für \<Ablauf Verfolgung hinzufügen ></span><span class="sxs-lookup"><span data-stu-id="c5f20-102">\<add> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="c5f20-103">Fügt der **listenerauflistung** einen Listener hinzu.</span><span class="sxs-lookup"><span data-stu-id="c5f20-103">Adds a listener to the **Listeners** collection.</span></span>  

<span data-ttu-id="c5f20-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c5f20-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c5f20-105">&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="c5f20-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="c5f20-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Ablauf Verfolgungs**](trace-element.md) ></span><span class="sxs-lookup"><span data-stu-id="c5f20-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="c5f20-107">&nbsp;&nbsp;&nbsp;&nbsp;[ \**&nbsp;&nbsp;\<Listener >\** ](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="c5f20-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\</span></span>
<span data-ttu-id="c5f20-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<hinzufügen >**</span><span class="sxs-lookup"><span data-stu-id="c5f20-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c5f20-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="c5f20-109">Syntax</span></span>  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c5f20-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c5f20-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c5f20-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c5f20-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c5f20-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="c5f20-112">Attributes</span></span>  
  
|<span data-ttu-id="c5f20-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="c5f20-113">Attribute</span></span>|<span data-ttu-id="c5f20-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c5f20-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c5f20-115">**Typ**</span><span class="sxs-lookup"><span data-stu-id="c5f20-115">**type**</span></span>|<span data-ttu-id="c5f20-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="c5f20-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="c5f20-117">Gibt den Typ des Listener an.</span><span class="sxs-lookup"><span data-stu-id="c5f20-117">Specifies the type of the listener.</span></span> <span data-ttu-id="c5f20-118">Sie müssen eine Zeichenfolge verwenden, die den unter [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)angegebenen Anforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="c5f20-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="c5f20-119">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="c5f20-119">**initializeData**</span></span>|<span data-ttu-id="c5f20-120">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="c5f20-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="c5f20-121">Die Zeichenfolge, die an den Konstruktor für die angegebene Klasse übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="c5f20-121">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="c5f20-122">**name**</span><span class="sxs-lookup"><span data-stu-id="c5f20-122">**name**</span></span>|<span data-ttu-id="c5f20-123">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="c5f20-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="c5f20-124">Gibt den Namen des Listener an.</span><span class="sxs-lookup"><span data-stu-id="c5f20-124">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c5f20-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c5f20-125">Child Elements</span></span>  
  
|<span data-ttu-id="c5f20-126">Element</span><span class="sxs-lookup"><span data-stu-id="c5f20-126">Element</span></span>|<span data-ttu-id="c5f20-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c5f20-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c5f20-128">\<filter></span><span class="sxs-lookup"><span data-stu-id="c5f20-128">\<filter></span></span>](filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="c5f20-129">Fügt einen Filter zu einem Listener in der `Listeners`-Auflistung für eine Ablauf Verfolgung hinzu.</span><span class="sxs-lookup"><span data-stu-id="c5f20-129">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c5f20-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c5f20-130">Parent Elements</span></span>  
  
|<span data-ttu-id="c5f20-131">Element</span><span class="sxs-lookup"><span data-stu-id="c5f20-131">Element</span></span>|<span data-ttu-id="c5f20-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c5f20-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c5f20-133">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="c5f20-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="c5f20-134">Gibt einen Listener an, der Nachrichten sammelt, speichert und weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="c5f20-134">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="c5f20-135">Listener leiten die Ablauf Verfolgungs Ausgabe an ein entsprechendes Ziel weiter.</span><span class="sxs-lookup"><span data-stu-id="c5f20-135">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="c5f20-136">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="c5f20-136">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="c5f20-137">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="c5f20-137">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5f20-138">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c5f20-138">Remarks</span></span>  
 <span data-ttu-id="c5f20-139">Die Klassen <xref:System.Diagnostics.Debug> und <xref:System.Diagnostics.Trace> **verwenden dieselbe Listener** -Auflistung.</span><span class="sxs-lookup"><span data-stu-id="c5f20-139">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="c5f20-140">Wenn Sie der Auflistung in einer dieser Klassen ein Listenerobjekt hinzufügen, verwendet die andere Klasse denselben Listener.</span><span class="sxs-lookup"><span data-stu-id="c5f20-140">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="c5f20-141">Die Listenerklassen werden vom <xref:System.Diagnostics.TraceListener>abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="c5f20-141">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="c5f20-142">Wenn Sie das `name`-Attribut des Ablaufverfolgungslistener nicht angeben, wird der <xref:System.Diagnostics.TraceListener.Name%2A> des Ablaufverfolgungslistener standardmäßig auf eine leere Zeichenfolge ("")</span><span class="sxs-lookup"><span data-stu-id="c5f20-142">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="c5f20-143">Wenn die Anwendung nur über einen Listener verfügt, können Sie Sie ohne Angabe eines Namens hinzufügen und entfernen, indem Sie eine leere Zeichenfolge für den Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="c5f20-143">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="c5f20-144">Wenn Ihre Anwendung jedoch über mehr als einen Listener verfügt, sollten Sie eindeutige Namen für jeden Ablaufverfolgungslistener angeben, sodass Sie einzelne Ablaufverfolgungslistener in den <xref:System.Diagnostics.Debug.Listeners%2A>-und <xref:System.Diagnostics.Trace.Listeners%2A> Sammlungen identifizieren und verwalten können.</span><span class="sxs-lookup"><span data-stu-id="c5f20-144">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c5f20-145">Das Hinzufügen von mehr als einem Ablaufverfolgungslistener desselben Typs und desselben Namens führt dazu, dass nur ein Ablaufverfolgungslistener dieses Typs und namens zur `Listeners` Auflistung hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="c5f20-145">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="c5f20-146">Allerdings können Sie der `Listeners` Auflistung Programm gesteuert mehrere identische Listener hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c5f20-146">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="c5f20-147">Der Wert für das **initializeData** -Attribut hängt vom Typ des von Ihnen erstellten Listener ab.</span><span class="sxs-lookup"><span data-stu-id="c5f20-147">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="c5f20-148">Nicht alle Ablaufverfolgungslistener erfordern, dass Sie **initializeData**angeben.</span><span class="sxs-lookup"><span data-stu-id="c5f20-148">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c5f20-149">Wenn Sie das `initializeData`-Attribut verwenden, erhalten Sie möglicherweise die Compilerwarnung, dass das initializeData-Attribut nicht deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="c5f20-149">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="c5f20-150">Diese Warnung tritt auf, weil die Konfigurationseinstellungen anhand der abstrakten Basisklasse <xref:System.Diagnostics.TraceListener>überprüft werden, die das `initializeData`-Attribut nicht erkennt.</span><span class="sxs-lookup"><span data-stu-id="c5f20-150">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="c5f20-151">Normalerweise können Sie diese Warnung für Ablaufverfolgungslistener-Implementierungen ignorieren, die über einen Konstruktor verfügen, der einen Parameter annimmt</span><span class="sxs-lookup"><span data-stu-id="c5f20-151">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="c5f20-152">In der folgenden Tabelle werden die Ablaufverfolgungslistener angezeigt, die im .NET Framework enthalten sind, und der Wert Ihrer **initializeData** -Attribute wird beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c5f20-152">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="c5f20-153">Trace-Listenerklasse</span><span class="sxs-lookup"><span data-stu-id="c5f20-153">Trace listener class</span></span>|<span data-ttu-id="c5f20-154">initializeData-Attribut Wert</span><span class="sxs-lookup"><span data-stu-id="c5f20-154">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="c5f20-155">Der `useErrorStream` Wert für den <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>-Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="c5f20-155">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="c5f20-156">Legen Sie das `initializeData`-Attribut auf "`true`" fest, um die Ablaufverfolgungs-und Debugausgabe in <xref:System.Console.Error%2A?displayProperty=nameWithType>zu schreiben; "`false`", um in <xref:System.Console.Out%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="c5f20-156">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="c5f20-157">Der Name der Datei, in die der <xref:System.Diagnostics.DelimitedListTraceListener> schreibt.</span><span class="sxs-lookup"><span data-stu-id="c5f20-157">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="c5f20-158">Der Name des Namens einer vorhandenen Ereignisprotokoll Quelle.</span><span class="sxs-lookup"><span data-stu-id="c5f20-158">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="c5f20-159">Der Name der Datei, in die der <xref:System.Diagnostics.EventSchemaTraceListener> schreibt.</span><span class="sxs-lookup"><span data-stu-id="c5f20-159">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="c5f20-160">Der Name der Datei, in die der <xref:System.Diagnostics.TextWriterTraceListener> schreibt.</span><span class="sxs-lookup"><span data-stu-id="c5f20-160">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="c5f20-161">Der Name der Datei, in die der <xref:System.Diagnostics.XmlWriterTraceListener> schreibt.</span><span class="sxs-lookup"><span data-stu-id="c5f20-161">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c5f20-162">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c5f20-162">Example</span></span>  
 <span data-ttu-id="c5f20-163">Im folgenden Beispiel wird gezeigt, wie **\<Hinzufügen von >** Elementen zum hinzu **fügen der Listener** `MyListener` und `MyEventListener` zur Listener-Auflistung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c5f20-163">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="c5f20-164">`MyListener` erstellt eine Datei mit dem Namen `MyListener.log` und schreibt die Ausgabe in die Datei.</span><span class="sxs-lookup"><span data-stu-id="c5f20-164">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="c5f20-165">`MyEventListener` erstellt einen Eintrag im Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="c5f20-165">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c5f20-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5f20-166">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [<span data-ttu-id="c5f20-167">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c5f20-167">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c5f20-168">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="c5f20-168">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
