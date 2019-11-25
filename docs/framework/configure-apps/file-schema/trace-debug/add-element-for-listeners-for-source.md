---
title: <add> Element für <listeners> für <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: c32205310f9fc451a5a55a943f925ee52f65c8a8
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088999"
---
# <a name="add-element-for-listeners-for-source"></a><span data-ttu-id="5cb59-102">\<> Element für \<Listener > für \<Quelle hinzufügen ></span><span class="sxs-lookup"><span data-stu-id="5cb59-102">\<add> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="5cb59-103">Fügt einen Listener zu der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="5cb59-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="5cb59-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5cb59-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5cb59-105">&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="5cb59-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="5cb59-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Quellen**](sources-element.md) ></span><span class="sxs-lookup"><span data-stu-id="5cb59-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="5cb59-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**Quelle**](source-element.md) ></span><span class="sxs-lookup"><span data-stu-id="5cb59-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="5cb59-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](listeners-element-for-source.md) Listener ></span><span class="sxs-lookup"><span data-stu-id="5cb59-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="5cb59-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<hinzufügen >**</span><span class="sxs-lookup"><span data-stu-id="5cb59-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="5cb59-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="5cb59-110">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5cb59-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5cb59-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5cb59-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5cb59-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5cb59-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="5cb59-113">Attributes</span></span>  
  
|<span data-ttu-id="5cb59-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="5cb59-114">Attribute</span></span>|<span data-ttu-id="5cb59-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5cb59-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="5cb59-116">Erforderliches Attribut, es sei denn, Sie verweisen in der `sharedListeners` Auflistung auf einen Listener. in diesem Fall müssen Sie nur anhand des Namens darauf verweisen (siehe [Beispiel](#example)).</span><span class="sxs-lookup"><span data-stu-id="5cb59-116">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="5cb59-117">Gibt den Typ des Listener an.</span><span class="sxs-lookup"><span data-stu-id="5cb59-117">Specifies the type of the listener.</span></span> <span data-ttu-id="5cb59-118">Sie müssen eine Zeichenfolge verwenden, die den unter [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)angegebenen Anforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="5cb59-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="5cb59-119">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="5cb59-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="5cb59-120">Die Zeichenfolge, die an den Konstruktor für die angegebene Klasse übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="5cb59-120">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="5cb59-121">Eine <xref:System.Configuration.ConfigurationException> wird ausgelöst, wenn die Klasse über keinen Konstruktor verfügt, der eine Zeichenfolge annimmt.</span><span class="sxs-lookup"><span data-stu-id="5cb59-121">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="5cb59-122">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="5cb59-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="5cb59-123">Gibt den Namen des Listener an.</span><span class="sxs-lookup"><span data-stu-id="5cb59-123">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="5cb59-124">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="5cb59-124">Optional attribute.</span></span><br /><br /> <span data-ttu-id="5cb59-125">Gibt den <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A>-Eigenschafts Wert für den Ablaufverfolgungslistener an</span><span class="sxs-lookup"><span data-stu-id="5cb59-125">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="5cb59-126">[benutzerdefinierte Attribute]</span><span class="sxs-lookup"><span data-stu-id="5cb59-126">[custom attributes]</span></span>|<span data-ttu-id="5cb59-127">Optionale Attribute.</span><span class="sxs-lookup"><span data-stu-id="5cb59-127">Optional attributes.</span></span><br /><br /> <span data-ttu-id="5cb59-128">Gibt den Wert für listenerspezifische Attribute an, die durch die <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A>-Methode für diesen Listener identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="5cb59-128">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="5cb59-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> ist ein Beispiel für ein zusätzliches Attribut, das für die Klasse <xref:System.Diagnostics.DelimitedListTraceListener> eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="5cb59-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5cb59-130">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5cb59-130">Child Elements</span></span>  
  
|<span data-ttu-id="5cb59-131">Element</span><span class="sxs-lookup"><span data-stu-id="5cb59-131">Element</span></span>|<span data-ttu-id="5cb59-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5cb59-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5cb59-133">\<filter></span><span class="sxs-lookup"><span data-stu-id="5cb59-133">\<filter></span></span>](filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="5cb59-134">Fügt einen Filter zu einem Listener in der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="5cb59-134">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5cb59-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5cb59-135">Parent Elements</span></span>  
  
|<span data-ttu-id="5cb59-136">Element</span><span class="sxs-lookup"><span data-stu-id="5cb59-136">Element</span></span>|<span data-ttu-id="5cb59-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5cb59-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5cb59-138">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="5cb59-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="5cb59-139">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="5cb59-139">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="5cb59-140">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="5cb59-140">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="5cb59-141">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="5cb59-141">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="5cb59-142">Gibt Listener an, die Nachrichten erfassen, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="5cb59-142">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5cb59-143">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5cb59-143">Remarks</span></span>  
 <span data-ttu-id="5cb59-144">Die Listenerklassen, die mit dem .NET Framework ausgeliefert werden, werden von der <xref:System.Diagnostics.TraceListener> Klasse abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="5cb59-144">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="5cb59-145">Wenn Sie das `name`-Attribut des Ablaufverfolgungslistener nicht angeben, wird für die <xref:System.Diagnostics.TraceListener.Name%2A>-Eigenschaft des Ablaufverfolgungslistener standardmäßig eine leere Zeichenfolge ("") verwendet</span><span class="sxs-lookup"><span data-stu-id="5cb59-145">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="5cb59-146">Wenn die Anwendung nur über einen Listener verfügt, können Sie Sie hinzufügen, ohne einen Namen anzugeben, und Sie können Sie entfernen, indem Sie eine leere Zeichenfolge für den Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="5cb59-146">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="5cb59-147">Wenn Ihre Anwendung jedoch über mehr als einen Listener verfügt, sollten Sie einen eindeutigen Namen für jeden Ablaufverfolgungslistener angeben, mit dem Sie einzelne Ablaufverfolgungslistener in der <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> Sammlung identifizieren und verwalten können.</span><span class="sxs-lookup"><span data-stu-id="5cb59-147">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5cb59-148">Das Hinzufügen von mehr als einem Ablaufverfolgungslistener desselben Typs und desselben Namens führt dazu, dass nur ein Ablaufverfolgungslistener dieses Typs und namens zur `Listeners` Auflistung hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="5cb59-148">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="5cb59-149">Allerdings können Sie der `Listeners` Auflistung Programm gesteuert mehrere identische Listener hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5cb59-149">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="5cb59-150">Der Wert für das `initializeData`-Attribut ist abhängig vom Typ des von Ihnen erstellten Listener.</span><span class="sxs-lookup"><span data-stu-id="5cb59-150">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="5cb59-151">Nicht alle Ablaufverfolgungslistener erfordern, dass Sie `initializeData`angeben</span><span class="sxs-lookup"><span data-stu-id="5cb59-151">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5cb59-152">Wenn Sie das `initializeData`-Attribut verwenden, erhalten Sie möglicherweise die Compilerwarnung, dass das initializeData-Attribut nicht deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="5cb59-152">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="5cb59-153">Diese Warnung tritt auf, weil die Konfigurationseinstellungen anhand der abstrakten Basisklasse <xref:System.Diagnostics.TraceListener>überprüft werden, die das `initializeData`-Attribut nicht erkennt.</span><span class="sxs-lookup"><span data-stu-id="5cb59-153">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="5cb59-154">Normalerweise können Sie diese Warnung für Ablaufverfolgungslistener-Implementierungen ignorieren, die über einen Konstruktor verfügen, der einen Parameter annimmt</span><span class="sxs-lookup"><span data-stu-id="5cb59-154">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="5cb59-155">Die folgende Tabelle zeigt die Ablaufverfolgungslistener, die im .NET Framework enthalten sind, und beschreibt den Wert ihrer `initializeData` Attribute.</span><span class="sxs-lookup"><span data-stu-id="5cb59-155">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="5cb59-156">Trace-Listenerklasse</span><span class="sxs-lookup"><span data-stu-id="5cb59-156">Trace listener class</span></span>|<span data-ttu-id="5cb59-157">initializeData-Attribut Wert</span><span class="sxs-lookup"><span data-stu-id="5cb59-157">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="5cb59-158">Der `useErrorStream` Wert für den <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>-Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="5cb59-158">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="5cb59-159">Legen Sie das `initializeData`-Attribut auf "`true`" fest, um die Ablauf Verfolgung und Debugausgabe in den Standardfehlerstream zu schreiben Legen Sie Sie auf "`false`" fest, um in den Standardausgabestream zu schreiben</span><span class="sxs-lookup"><span data-stu-id="5cb59-159">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="5cb59-160">Der Name der Datei, in die der <xref:System.Diagnostics.DelimitedListTraceListener> schreibt.</span><span class="sxs-lookup"><span data-stu-id="5cb59-160">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="5cb59-161">Der Name einer vorhandenen Ereignisprotokoll Quelle.</span><span class="sxs-lookup"><span data-stu-id="5cb59-161">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="5cb59-162">Der Name der Datei, in die der <xref:System.Diagnostics.EventSchemaTraceListener> schreibt.</span><span class="sxs-lookup"><span data-stu-id="5cb59-162">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="5cb59-163">Der Name der Datei, in die der <xref:System.Diagnostics.TextWriterTraceListener> schreibt.</span><span class="sxs-lookup"><span data-stu-id="5cb59-163">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="5cb59-164">Der Name der Datei, in die der <xref:System.Diagnostics.XmlWriterTraceListener> schreibt.</span><span class="sxs-lookup"><span data-stu-id="5cb59-164">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="5cb59-165">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="5cb59-165">Configuration File</span></span>  
 <span data-ttu-id="5cb59-166">Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5cb59-166">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5cb59-167">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5cb59-167">Example</span></span>  
 <span data-ttu-id="5cb59-168">Im folgenden Beispiel wird gezeigt, wie `<add>`-Elemente verwendet werden, um die Listener `console` und `textListener` der `Listeners` Auflistung für die Ablauf Verfolgungs Quelle `TraceSourceApp`hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="5cb59-168">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="5cb59-169">Der `textListener` Listener schreibt die Ablauf Verfolgungs Ausgabe in die Datei "MyListener. log".</span><span class="sxs-lookup"><span data-stu-id="5cb59-169">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5cb59-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5cb59-170">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="5cb59-171">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="5cb59-171">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5cb59-172">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="5cb59-172">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
