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
ms.openlocfilehash: 5588892ec75a791eda1eb043936c0af95e79354e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153606"
---
# <a name="add-element-for-sharedlisteners"></a><span data-ttu-id="8900d-102">\<Hinzufügen> \<Elements für sharedListeners></span><span class="sxs-lookup"><span data-stu-id="8900d-102">\<add> Element for \<sharedListeners></span></span>
<span data-ttu-id="8900d-103">Fügt einen Listener zu der `sharedListeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="8900d-103">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="8900d-104">`sharedListeners`ist eine Sammlung von [ \<](source-element.md) Listenern, auf die jede Quelle>oder [ \<Ablaufverfolgungs>](trace-element.md) verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="8900d-104">`sharedListeners` is a collection of listeners that any [\<source>](source-element.md) or [\<trace>](trace-element.md) can reference.</span></span>  <span data-ttu-id="8900d-105">Standardmäßig werden Listener `sharedListeners` in der Auflistung `Listeners` nicht in einer Auflistung platziert.</span><span class="sxs-lookup"><span data-stu-id="8900d-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="8900d-106">Sie müssen dem [ \<Quell>](source-element.md) oder [ \<Ablaufverfolgungs->](trace-element.md)mit Namen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="8900d-106">They must be added by name to the [\<source>](source-element.md) or [\<trace>](trace-element.md).</span></span> <span data-ttu-id="8900d-107">Es ist nicht möglich, die `sharedListeners` Listener in der Auflistung zur Laufzeit im Code abrufe.</span><span class="sxs-lookup"><span data-stu-id="8900d-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  

<span data-ttu-id="8900d-108">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8900d-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8900d-109">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="8900d-109">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="8900d-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)</span><span class="sxs-lookup"><span data-stu-id="8900d-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)</span></span>\
<span data-ttu-id="8900d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<hinzufügen>**</span><span class="sxs-lookup"><span data-stu-id="8900d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="8900d-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="8900d-112">Syntax</span></span>  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8900d-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8900d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="8900d-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8900d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8900d-115">Attributes</span><span class="sxs-lookup"><span data-stu-id="8900d-115">Attributes</span></span>  
  
|<span data-ttu-id="8900d-116">attribute</span><span class="sxs-lookup"><span data-stu-id="8900d-116">Attribute</span></span>|<span data-ttu-id="8900d-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8900d-117">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="8900d-118">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="8900d-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="8900d-119">Gibt den Namen des Listeners an, der zum Hinzufügen `Listeners` des freigegebenen Listeners zu einer Auflistung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8900d-119">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="8900d-120">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="8900d-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="8900d-121">Gibt den Typ des Listeners an.</span><span class="sxs-lookup"><span data-stu-id="8900d-121">Specifies the type of the listener.</span></span> <span data-ttu-id="8900d-122">Sie müssen eine Zeichenfolge verwenden, die die unter [Angeben von vollqualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)angegebenen Anforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="8900d-122">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="8900d-123">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="8900d-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="8900d-124">Die Zeichenfolge, die an den Konstruktor für die angegebene Klasse übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="8900d-124">The string passed to the constructor for the specified class.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="8900d-125">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="8900d-125">Optional attribute.</span></span><br/><br/><span data-ttu-id="8900d-126">Die Zeichenfolgendarstellung eines <xref:System.Diagnostics.TraceOptions> oder mehrerer Enumerationsmember, die die Daten angibt, die in die Ablaufverfolgungsausgabe geschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8900d-126">The string representation of one or more <xref:System.Diagnostics.TraceOptions> enumeration members that indicates the data to be written to the trace output.</span></span> <span data-ttu-id="8900d-127">Mehrere Elemente werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="8900d-127">Multiple items are separated by commas.</span></span> <span data-ttu-id="8900d-128">Der Standardwert ist "Keine".</span><span class="sxs-lookup"><span data-stu-id="8900d-128">The default value is "None".</span></span>|

### <a name="child-elements"></a><span data-ttu-id="8900d-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8900d-129">Child Elements</span></span>  
  
|<span data-ttu-id="8900d-130">Element</span><span class="sxs-lookup"><span data-stu-id="8900d-130">Element</span></span>|<span data-ttu-id="8900d-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8900d-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8900d-132">\<Filter></span><span class="sxs-lookup"><span data-stu-id="8900d-132">\<filter></span></span>](filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="8900d-133">Fügt einen Filter zu einem Listener in der `sharedListeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="8900d-133">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8900d-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8900d-134">Parent Elements</span></span>  
  
|<span data-ttu-id="8900d-135">Element</span><span class="sxs-lookup"><span data-stu-id="8900d-135">Element</span></span>|<span data-ttu-id="8900d-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8900d-136">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8900d-137">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="8900d-137">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="8900d-138">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="8900d-138">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="8900d-139">Eine Auflistung von Listenern, auf die jedes Quell- oder Ablaufverfolgungselement verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="8900d-139">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8900d-140">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8900d-140">Remarks</span></span>  
 <span data-ttu-id="8900d-141">Die Listenerklassen, die mit .NET Framework <xref:System.Diagnostics.TraceListener> ausgeliefert wurden, leiten sich von der Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="8900d-141">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="8900d-142">Der Wert `name` für das Attribut wird verwendet, `Listeners` um den freigegebenen Listener zu einer Auflistung für eine Ablaufverfolgung oder eine Ablaufverfolgungsquelle hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="8900d-142">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="8900d-143">Der Wert `initializeData` für das Attribut hängt vom Typ des Listeners ab, den Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="8900d-143">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="8900d-144">Nicht alle Ablaufverfolgungslistener erfordern, dass Sie angeben. `initializeData`</span><span class="sxs-lookup"><span data-stu-id="8900d-144">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8900d-145">Wenn Sie `initializeData` das Attribut verwenden, erhalten Sie möglicherweise die Compilerwarnung "Das Attribut 'initializeData' ist nicht deklariert."</span><span class="sxs-lookup"><span data-stu-id="8900d-145">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="8900d-146">Diese Warnung wird angezeigt, weil die Konfigurationseinstellungen anhand der abstrakten Basisklasse <xref:System.Diagnostics.TraceListener>überprüft werden, die das `initializeData` Attribut nicht erkennt.</span><span class="sxs-lookup"><span data-stu-id="8900d-146">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="8900d-147">In der Regel können Sie diese Warnung für Ablaufverfolgungslistenerimplementierungen ignorieren, die über einen Konstruktor verfügen, der einen Parameter annimmt.</span><span class="sxs-lookup"><span data-stu-id="8900d-147">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="8900d-148">Die folgende Tabelle zeigt die Ablaufverfolgungslistener, die in `initializeData` .NET Framework enthalten sind, und beschreibt den Wert ihrer Attribute.</span><span class="sxs-lookup"><span data-stu-id="8900d-148">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="8900d-149">Ablaufverfolgungs-Listenerklasse</span><span class="sxs-lookup"><span data-stu-id="8900d-149">Trace listener class</span></span>|<span data-ttu-id="8900d-150">initializeData-Attributwert</span><span class="sxs-lookup"><span data-stu-id="8900d-150">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="8900d-151">Der `useErrorStream` Wert <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> für den Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="8900d-151">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="8900d-152">Legen `initializeData` Sie das`true`Attribut auf " fest, um die Ablaufverfolgung sende- und Debugausgabe in den Standardfehlerstream zu schreiben. setzen Sie`false`es auf " , um in den Standardausgabestream zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="8900d-152">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="8900d-153">Der Name der Datei, in die der <xref:System.Diagnostics.DelimitedListTraceListener> schreibt.</span><span class="sxs-lookup"><span data-stu-id="8900d-153">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="8900d-154">Der Name einer vorhandenen Ereignisprotokollquelle.</span><span class="sxs-lookup"><span data-stu-id="8900d-154">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="8900d-155">Der Name der Datei, in die die <xref:System.Diagnostics.EventSchemaTraceListener> Datei schreibt.</span><span class="sxs-lookup"><span data-stu-id="8900d-155">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="8900d-156">Der Name der Datei, in die die <xref:System.Diagnostics.TextWriterTraceListener> Datei schreibt.</span><span class="sxs-lookup"><span data-stu-id="8900d-156">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="8900d-157">Der Name der Datei, in die die <xref:System.Diagnostics.XmlWriterTraceListener> Datei schreibt.</span><span class="sxs-lookup"><span data-stu-id="8900d-157">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="8900d-158">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="8900d-158">Configuration File</span></span>  
 <span data-ttu-id="8900d-159">Dieses Element kann in der Maschinenkonfigurationsdatei (Machine.config) und in der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8900d-159">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8900d-160">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8900d-160">Example</span></span>  
 <span data-ttu-id="8900d-161">Das folgende Beispiel zeigt, wie <xref:System.Diagnostics.TextWriterTraceListener> `textListener` Elemente `sharedListeners` zum Hinzufügen der Elemente zur Auflistung verwendet `<add>` werden.</span><span class="sxs-lookup"><span data-stu-id="8900d-161">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="8900d-162">`textListener`wird der `Listeners` Auflistung für die Ablaufverfolgungsquelle `TraceSourceApp`nach Namen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8900d-162">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="8900d-163">Der `textListener` Listener schreibt die Ablaufverfolgungsausgabe in die Datei myListener.log.</span><span class="sxs-lookup"><span data-stu-id="8900d-163">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8900d-164">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8900d-164">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="8900d-165">Ablaufverfolgungs- und Debugeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="8900d-165">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8900d-166">Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="8900d-166">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
