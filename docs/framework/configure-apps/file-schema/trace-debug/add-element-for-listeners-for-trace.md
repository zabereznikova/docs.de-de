---
title: <add>-Element für <listeners> für<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: c64673908dc9afe67d97c08f93e5b9d9533bd34d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153671"
---
# <a name="add-element-for-listeners-for-trace"></a><span data-ttu-id="da10f-102">\<add>-Element für \<listeners> für\<trace></span><span class="sxs-lookup"><span data-stu-id="da10f-102">\<add> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="da10f-103">Fügt der **listenerauflistung** einen Listener hinzu.</span><span class="sxs-lookup"><span data-stu-id="da10f-103">Adds a listener to the **Listeners** collection.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="da10f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="da10f-104">Syntax</span></span>  
  
```xml  
<add name="name"
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da10f-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="da10f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="da10f-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="da10f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da10f-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="da10f-107">Attributes</span></span>  
  
|<span data-ttu-id="da10f-108">attribute</span><span class="sxs-lookup"><span data-stu-id="da10f-108">Attribute</span></span>|<span data-ttu-id="da10f-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="da10f-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="da10f-110">**type**</span><span class="sxs-lookup"><span data-stu-id="da10f-110">**type**</span></span>|<span data-ttu-id="da10f-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="da10f-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="da10f-112">Gibt den Typ des Listener an.</span><span class="sxs-lookup"><span data-stu-id="da10f-112">Specifies the type of the listener.</span></span> <span data-ttu-id="da10f-113">Sie müssen eine Zeichenfolge verwenden, die den unter [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)angegebenen Anforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="da10f-113">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="da10f-114">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="da10f-114">**initializeData**</span></span>|<span data-ttu-id="da10f-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="da10f-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="da10f-116">Die Zeichenfolge, die an den Konstruktor für die angegebene Klasse übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="da10f-116">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="da10f-117">**name**</span><span class="sxs-lookup"><span data-stu-id="da10f-117">**name**</span></span>|<span data-ttu-id="da10f-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="da10f-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="da10f-119">Gibt den Namen des Listener an.</span><span class="sxs-lookup"><span data-stu-id="da10f-119">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da10f-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="da10f-120">Child Elements</span></span>  
  
|<span data-ttu-id="da10f-121">Element</span><span class="sxs-lookup"><span data-stu-id="da10f-121">Element</span></span>|<span data-ttu-id="da10f-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="da10f-122">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="da10f-123">Fügt einen Filter zu einem Listener in der-Auflistung `Listeners` für eine Ablauf Verfolgung hinzu.</span><span class="sxs-lookup"><span data-stu-id="da10f-123">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="da10f-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="da10f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="da10f-125">Element</span><span class="sxs-lookup"><span data-stu-id="da10f-125">Element</span></span>|<span data-ttu-id="da10f-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="da10f-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="da10f-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="da10f-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="da10f-128">Gibt einen Listener an, der Nachrichten sammelt, speichert und weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="da10f-128">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="da10f-129">Listener leiten die Ablauf Verfolgungs Ausgabe an ein entsprechendes Ziel weiter.</span><span class="sxs-lookup"><span data-stu-id="da10f-129">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="da10f-130">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="da10f-130">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="da10f-131">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="da10f-131">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da10f-132">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="da10f-132">Remarks</span></span>  
 <span data-ttu-id="da10f-133">Die <xref:System.Diagnostics.Debug> - <xref:System.Diagnostics.Trace> Klasse und die- **Listeners** Klasse verwenden dieselbe Listener-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="da10f-133">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="da10f-134">Wenn Sie der Auflistung in einer dieser Klassen ein Listenerobjekt hinzufügen, verwendet die andere Klasse denselben Listener.</span><span class="sxs-lookup"><span data-stu-id="da10f-134">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="da10f-135">Die Listenerklassen werden von abgeleitet <xref:System.Diagnostics.TraceListener> .</span><span class="sxs-lookup"><span data-stu-id="da10f-135">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="da10f-136">Wenn Sie das-Attribut des Ablaufverfolgungslistener nicht angeben, wird für den Ablaufverfolgungslistener `name` <xref:System.Diagnostics.TraceListener.Name%2A> standardmäßig eine leere Zeichenfolge ("")</span><span class="sxs-lookup"><span data-stu-id="da10f-136">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="da10f-137">Wenn die Anwendung nur über einen Listener verfügt, können Sie Sie ohne Angabe eines Namens hinzufügen und entfernen, indem Sie eine leere Zeichenfolge für den Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="da10f-137">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="da10f-138">Wenn Ihre Anwendung jedoch über mehr als einen Listener verfügt, sollten Sie eindeutige Namen für jeden Ablaufverfolgungslistener angeben, sodass Sie einzelne Ablaufverfolgungslistener innerhalb der-und-Auflistung identifizieren und verwalten können <xref:System.Diagnostics.Debug.Listeners%2A> <xref:System.Diagnostics.Trace.Listeners%2A> .</span><span class="sxs-lookup"><span data-stu-id="da10f-138">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da10f-139">Das Hinzufügen von mehr als einem Ablaufverfolgungslistener desselben Typs und desselben Namens führt dazu, dass nur ein Ablaufverfolgungslistener dieses Typs und namens zur Auflistung hinzugefügt wird `Listeners` .</span><span class="sxs-lookup"><span data-stu-id="da10f-139">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="da10f-140">Allerdings können Sie der Auflistung Programm gesteuert mehrere identische Listener hinzufügen `Listeners` .</span><span class="sxs-lookup"><span data-stu-id="da10f-140">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="da10f-141">Der Wert für das **initializeData** -Attribut hängt vom Typ des von Ihnen erstellten Listener ab.</span><span class="sxs-lookup"><span data-stu-id="da10f-141">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="da10f-142">Nicht alle Ablaufverfolgungslistener erfordern, dass Sie **initializeData**angeben.</span><span class="sxs-lookup"><span data-stu-id="da10f-142">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da10f-143">Wenn Sie das- `initializeData` Attribut verwenden, erhalten Sie möglicherweise die Compilerwarnung, dass das initializeData-Attribut nicht deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="da10f-143">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="da10f-144">Diese Warnung tritt auf, weil die Konfigurationseinstellungen anhand der abstrakten Basisklasse überprüft werden <xref:System.Diagnostics.TraceListener> , die das- `initializeData` Attribut nicht erkennt.</span><span class="sxs-lookup"><span data-stu-id="da10f-144">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="da10f-145">Normalerweise können Sie diese Warnung für Ablaufverfolgungslistener-Implementierungen ignorieren, die über einen Konstruktor verfügen, der einen Parameter annimmt</span><span class="sxs-lookup"><span data-stu-id="da10f-145">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="da10f-146">In der folgenden Tabelle werden die Ablaufverfolgungslistener angezeigt, die im .NET Framework enthalten sind, und der Wert Ihrer **initializeData** -Attribute wird beschrieben.</span><span class="sxs-lookup"><span data-stu-id="da10f-146">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="da10f-147">Trace-Listenerklasse</span><span class="sxs-lookup"><span data-stu-id="da10f-147">Trace listener class</span></span>|<span data-ttu-id="da10f-148">initializeData-Attribut Wert</span><span class="sxs-lookup"><span data-stu-id="da10f-148">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="da10f-149">Der `useErrorStream` Wert für den <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="da10f-149">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="da10f-150">Legen Sie das `initializeData` -Attribut auf "" fest, um die Ablauf `true` Verfolgung und Debugausgabe in <xref:System.Console.Error%2A?displayProperty=nameWithType> " `false` ", in die geschrieben werden soll <xref:System.Console.Out%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="da10f-150">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="da10f-151">Der Name der Datei, in die der <xref:System.Diagnostics.DelimitedListTraceListener> schreibt.</span><span class="sxs-lookup"><span data-stu-id="da10f-151">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="da10f-152">Der Name des Namens einer vorhandenen Ereignisprotokoll Quelle.</span><span class="sxs-lookup"><span data-stu-id="da10f-152">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="da10f-153">Der Name der Datei, in die <xref:System.Diagnostics.EventSchemaTraceListener> geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="da10f-153">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="da10f-154">Der Name der Datei, in die <xref:System.Diagnostics.TextWriterTraceListener> geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="da10f-154">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="da10f-155">Der Name der Datei, in die <xref:System.Diagnostics.XmlWriterTraceListener> geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="da10f-155">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="da10f-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="da10f-156">Example</span></span>  
 <span data-ttu-id="da10f-157">Im folgenden Beispiel wird gezeigt, wie Elemente verwendet werden, **\<add>** um die Listener und der Listener-Auflistung hinzuzufügen `MyListener` `MyEventListener` . **Listeners**</span><span class="sxs-lookup"><span data-stu-id="da10f-157">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="da10f-158">`MyListener`erstellt eine Datei `MyListener.log` mit dem Namen und schreibt die Ausgabe in die Datei.</span><span class="sxs-lookup"><span data-stu-id="da10f-158">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="da10f-159">`MyEventListener`erstellt einen Eintrag im Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="da10f-159">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="da10f-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="da10f-160">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [<span data-ttu-id="da10f-161">Schema für Ablaufverfolgungs- und Debugeinstellungen</span><span class="sxs-lookup"><span data-stu-id="da10f-161">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="da10f-162">Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="da10f-162">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
