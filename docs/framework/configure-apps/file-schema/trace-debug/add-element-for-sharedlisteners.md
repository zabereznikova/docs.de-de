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
ms.openlocfilehash: f0ede5f9dc19e9589afc888e7fcd01785bc1840c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91174029"
---
# <a name="add-element-for-sharedlisteners"></a><span data-ttu-id="baf4e-102">\<add>-Element für \<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="baf4e-102">\<add> Element for \<sharedListeners></span></span>

<span data-ttu-id="baf4e-103">Fügt einen Listener zu der `sharedListeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="baf4e-103">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="baf4e-104">`sharedListeners` eine Auflistung von Listenern, auf die Any [\<source>](source-element.md) oder [\<trace>](trace-element.md) verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="baf4e-104">`sharedListeners` is a collection of listeners that any [\<source>](source-element.md) or [\<trace>](trace-element.md) can reference.</span></span>  <span data-ttu-id="baf4e-105">Standardmäßig werden Listener in der Auflistung `sharedListeners` nicht in eine Auflistung eingefügt `Listeners` .</span><span class="sxs-lookup"><span data-stu-id="baf4e-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="baf4e-106">Sie müssen mit dem Namen zu oder hinzugefügt werden [\<source>](source-element.md) [\<trace>](trace-element.md) .</span><span class="sxs-lookup"><span data-stu-id="baf4e-106">They must be added by name to the [\<source>](source-element.md) or [\<trace>](trace-element.md).</span></span> <span data-ttu-id="baf4e-107">Es ist nicht möglich, die Listener in der Auflistung `sharedListeners` zur Laufzeit im Code zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="baf4e-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="baf4e-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="baf4e-108">Syntax</span></span>  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="baf4e-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="baf4e-109">Attributes and Elements</span></span>  

 <span data-ttu-id="baf4e-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="baf4e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="baf4e-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="baf4e-111">Attributes</span></span>  
  
|<span data-ttu-id="baf4e-112">attribute</span><span class="sxs-lookup"><span data-stu-id="baf4e-112">Attribute</span></span>|<span data-ttu-id="baf4e-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="baf4e-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="baf4e-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="baf4e-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="baf4e-115">Gibt den Namen des Listener an, der verwendet wird, um den freigegebenen Listener einer Auflistung hinzuzufügen `Listeners` .</span><span class="sxs-lookup"><span data-stu-id="baf4e-115">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="baf4e-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="baf4e-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="baf4e-117">Gibt den Typ des Listener an.</span><span class="sxs-lookup"><span data-stu-id="baf4e-117">Specifies the type of the listener.</span></span> <span data-ttu-id="baf4e-118">Sie müssen eine Zeichenfolge verwenden, die den unter [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)angegebenen Anforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="baf4e-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="baf4e-119">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="baf4e-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="baf4e-120">Die Zeichenfolge, die an den Konstruktor für die angegebene Klasse übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="baf4e-120">The string passed to the constructor for the specified class.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="baf4e-121">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="baf4e-121">Optional attribute.</span></span><br/><br/><span data-ttu-id="baf4e-122">Die Zeichen folgen Darstellung eines oder mehrerer <xref:System.Diagnostics.TraceOptions> Enumerationsmember, die die Daten angibt, die in die Ablauf Verfolgungs Ausgabe geschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="baf4e-122">The string representation of one or more <xref:System.Diagnostics.TraceOptions> enumeration members that indicates the data to be written to the trace output.</span></span> <span data-ttu-id="baf4e-123">Mehrere Elemente werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="baf4e-123">Multiple items are separated by commas.</span></span> <span data-ttu-id="baf4e-124">Der Standardwert ist "None".</span><span class="sxs-lookup"><span data-stu-id="baf4e-124">The default value is "None".</span></span>|

### <a name="child-elements"></a><span data-ttu-id="baf4e-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="baf4e-125">Child Elements</span></span>  
  
|<span data-ttu-id="baf4e-126">Element</span><span class="sxs-lookup"><span data-stu-id="baf4e-126">Element</span></span>|<span data-ttu-id="baf4e-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="baf4e-127">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="baf4e-128">Fügt einen Filter zu einem Listener in der `sharedListeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="baf4e-128">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="baf4e-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="baf4e-129">Parent Elements</span></span>  
  
|<span data-ttu-id="baf4e-130">Element</span><span class="sxs-lookup"><span data-stu-id="baf4e-130">Element</span></span>|<span data-ttu-id="baf4e-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="baf4e-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="baf4e-132">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="baf4e-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="baf4e-133">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="baf4e-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="baf4e-134">Eine Auflistung von Listenern, auf die beliebige Quell-oder Ablauf Verfolgungs Elemente verweisen können.</span><span class="sxs-lookup"><span data-stu-id="baf4e-134">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="baf4e-135">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="baf4e-135">Remarks</span></span>  

 <span data-ttu-id="baf4e-136">Die Listenerklassen, die mit dem .NET Framework ausgeliefert werden, werden von der- <xref:System.Diagnostics.TraceListener> Klasse abgeleitet</span><span class="sxs-lookup"><span data-stu-id="baf4e-136">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="baf4e-137">Der Wert für das- `name` Attribut wird verwendet, um den freigegebenen Listener einer Auflistung `Listeners` entweder für eine Ablauf Verfolgung oder eine Ablauf Verfolgungs Quelle hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="baf4e-137">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="baf4e-138">Der Wert für das-Attribut ist abhängig vom `initializeData` Typ des von Ihnen erstellten Listener.</span><span class="sxs-lookup"><span data-stu-id="baf4e-138">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="baf4e-139">Nicht alle Ablaufverfolgungslistener erfordern, dass `initializeData` Sie angeben</span><span class="sxs-lookup"><span data-stu-id="baf4e-139">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="baf4e-140">Wenn Sie das- `initializeData` Attribut verwenden, erhalten Sie möglicherweise die Compilerwarnung, dass das initializeData-Attribut nicht deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="baf4e-140">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="baf4e-141">Diese Warnung tritt auf, weil die Konfigurationseinstellungen anhand der abstrakten Basisklasse überprüft werden <xref:System.Diagnostics.TraceListener> , die das- `initializeData` Attribut nicht erkennt.</span><span class="sxs-lookup"><span data-stu-id="baf4e-141">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="baf4e-142">Normalerweise können Sie diese Warnung für Ablaufverfolgungslistener-Implementierungen ignorieren, die über einen Konstruktor verfügen, der einen Parameter annimmt</span><span class="sxs-lookup"><span data-stu-id="baf4e-142">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="baf4e-143">In der folgenden Tabelle werden die Ablaufverfolgungslistener angezeigt, die im .NET Framework enthalten sind, und der Wert ihrer Attribute wird beschrieben `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="baf4e-143">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="baf4e-144">Trace-Listenerklasse</span><span class="sxs-lookup"><span data-stu-id="baf4e-144">Trace listener class</span></span>|<span data-ttu-id="baf4e-145">initializeData-Attribut Wert</span><span class="sxs-lookup"><span data-stu-id="baf4e-145">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="baf4e-146">Der `useErrorStream` Wert für den <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="baf4e-146">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="baf4e-147">Legen `initializeData` Sie das-Attribut auf "" fest, um die Ablauf `true` Verfolgung und Debugausgabe in den Standardfehlerstream zu schreiben. Legen Sie Sie auf " `false` " fest</span><span class="sxs-lookup"><span data-stu-id="baf4e-147">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="baf4e-148">Der Name der Datei, in die der <xref:System.Diagnostics.DelimitedListTraceListener> schreibt.</span><span class="sxs-lookup"><span data-stu-id="baf4e-148">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="baf4e-149">Der Name einer vorhandenen Ereignisprotokollquelle.</span><span class="sxs-lookup"><span data-stu-id="baf4e-149">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="baf4e-150">Der Name der Datei, in die <xref:System.Diagnostics.EventSchemaTraceListener> geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="baf4e-150">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="baf4e-151">Der Name der Datei, in die <xref:System.Diagnostics.TextWriterTraceListener> geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="baf4e-151">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="baf4e-152">Der Name der Datei, in die <xref:System.Diagnostics.XmlWriterTraceListener> geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="baf4e-152">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="baf4e-153">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="baf4e-153">Configuration File</span></span>  

 <span data-ttu-id="baf4e-154">Dieses Element kann in der Computer Konfigurationsdatei (Machine.config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="baf4e-154">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="baf4e-155">Beispiel</span><span class="sxs-lookup"><span data-stu-id="baf4e-155">Example</span></span>  

 <span data-ttu-id="baf4e-156">Im folgenden Beispiel wird gezeigt, wie-Elemente verwendet werden, `<add>` um der-Auflistung hinzuzufügen <xref:System.Diagnostics.TextWriterTraceListener> `textListener` `sharedListeners` .</span><span class="sxs-lookup"><span data-stu-id="baf4e-156">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="baf4e-157">`textListener` wird der-Auflistung `Listeners` für die Ablauf Verfolgungs Quelle nach Name hinzugefügt `TraceSourceApp` .</span><span class="sxs-lookup"><span data-stu-id="baf4e-157">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="baf4e-158">Der `textListener` Listener schreibt die Ablauf Verfolgungs Ausgabe in die Datei "MyListener. log".</span><span class="sxs-lookup"><span data-stu-id="baf4e-158">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="baf4e-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="baf4e-159">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="baf4e-160">Schema für Ablaufverfolgungs- und Debugeinstellungen</span><span class="sxs-lookup"><span data-stu-id="baf4e-160">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="baf4e-161">Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="baf4e-161">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
