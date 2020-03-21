---
title: <add>Element <listeners> für für<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: 883eef32172c5a7f900197995b4c57c3d5a84e19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153684"
---
# <a name="add-element-for-listeners-for-source"></a><span data-ttu-id="43aa5-102">\<Hinzufügen> \<Elements für \<Listener> für></span><span class="sxs-lookup"><span data-stu-id="43aa5-102">\<add> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="43aa5-103">Fügt einen Listener zu der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="43aa5-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="43aa5-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="43aa5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="43aa5-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="43aa5-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="43aa5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<Quellen>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="43aa5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="43aa5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Quelle>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="43aa5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="43aa5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Hörer>**](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="43aa5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="43aa5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<hinzufügen>**</span><span class="sxs-lookup"><span data-stu-id="43aa5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="43aa5-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="43aa5-110">Syntax</span></span>  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43aa5-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="43aa5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="43aa5-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="43aa5-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43aa5-113">Attributes</span><span class="sxs-lookup"><span data-stu-id="43aa5-113">Attributes</span></span>  
  
|<span data-ttu-id="43aa5-114">attribute</span><span class="sxs-lookup"><span data-stu-id="43aa5-114">Attribute</span></span>|<span data-ttu-id="43aa5-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="43aa5-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="43aa5-116">Erforderliches Attribut, es sei denn, Sie `sharedListeners` verweisen auf einen Listener in der Auflistung, in diesem Fall müssen Sie nur mit dem Namen darauf verweisen (siehe [Beispiel](#example)).</span><span class="sxs-lookup"><span data-stu-id="43aa5-116">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="43aa5-117">Gibt den Typ des Listeners an.</span><span class="sxs-lookup"><span data-stu-id="43aa5-117">Specifies the type of the listener.</span></span> <span data-ttu-id="43aa5-118">Sie müssen eine Zeichenfolge verwenden, die die unter [Angeben von vollqualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)angegebenen Anforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="43aa5-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="43aa5-119">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="43aa5-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="43aa5-120">Die Zeichenfolge, die an den Konstruktor für die angegebene Klasse übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="43aa5-120">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="43aa5-121">A <xref:System.Configuration.ConfigurationException> wird ausgelöst, wenn die Klasse keinen Konstruktor hat, der eine Zeichenfolge annimmt.</span><span class="sxs-lookup"><span data-stu-id="43aa5-121">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="43aa5-122">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="43aa5-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="43aa5-123">Gibt den Namen des Listeners an.</span><span class="sxs-lookup"><span data-stu-id="43aa5-123">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="43aa5-124">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="43aa5-124">Optional attribute.</span></span><br /><br /> <span data-ttu-id="43aa5-125">Gibt den <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> Eigenschaftswert für den Ablaufverfolgungslistener an.</span><span class="sxs-lookup"><span data-stu-id="43aa5-125">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="43aa5-126">[benutzerdefinierte Attribute]</span><span class="sxs-lookup"><span data-stu-id="43aa5-126">[custom attributes]</span></span>|<span data-ttu-id="43aa5-127">Optionale Attribute.</span><span class="sxs-lookup"><span data-stu-id="43aa5-127">Optional attributes.</span></span><br /><br /> <span data-ttu-id="43aa5-128">Gibt den Wert für Listener-spezifische Attribute <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> an, die von der Methode für diesen Listener identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="43aa5-128">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="43aa5-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>ist ein Beispiel für ein <xref:System.Diagnostics.DelimitedListTraceListener> zusätzliches Attribut, das für die Klasse eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="43aa5-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="43aa5-130">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="43aa5-130">Child Elements</span></span>  
  
|<span data-ttu-id="43aa5-131">Element</span><span class="sxs-lookup"><span data-stu-id="43aa5-131">Element</span></span>|<span data-ttu-id="43aa5-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="43aa5-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43aa5-133">\<Filter></span><span class="sxs-lookup"><span data-stu-id="43aa5-133">\<filter></span></span>](filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="43aa5-134">Fügt einen Filter zu einem Listener in der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="43aa5-134">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="43aa5-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="43aa5-135">Parent Elements</span></span>  
  
|<span data-ttu-id="43aa5-136">Element</span><span class="sxs-lookup"><span data-stu-id="43aa5-136">Element</span></span>|<span data-ttu-id="43aa5-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="43aa5-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="43aa5-138">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="43aa5-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="43aa5-139">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="43aa5-139">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="43aa5-140">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="43aa5-140">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="43aa5-141">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="43aa5-141">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="43aa5-142">Gibt Listener an, die Nachrichten sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="43aa5-142">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43aa5-143">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="43aa5-143">Remarks</span></span>  
 <span data-ttu-id="43aa5-144">Die Listenerklassen, die mit .NET Framework <xref:System.Diagnostics.TraceListener> ausgeliefert wurden, leiten sich von der Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="43aa5-144">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="43aa5-145">Wenn Sie das `name` Attribut des Ablaufverfolgungslisteners nicht angeben, wird die <xref:System.Diagnostics.TraceListener.Name%2A> Eigenschaft des Ablaufverfolgungslisteners standardmäßig auf eine leere Zeichenfolge ("") festgelegt.</span><span class="sxs-lookup"><span data-stu-id="43aa5-145">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="43aa5-146">Wenn Ihre Anwendung nur über einen Listener verfügt, können Sie sie hinzufügen, ohne einen Namen anzugeben, und Sie können ihn entfernen, indem Sie eine leere Zeichenfolge für den Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="43aa5-146">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="43aa5-147">Wenn Ihre Anwendung jedoch über mehr als einen Listener verfügt, sollten Sie für jeden Ablaufverfolgungslistener <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> einen eindeutigen Namen angeben, mit dem Sie einzelne Ablaufverfolgungslistener in der Auflistung identifizieren und verwalten können.</span><span class="sxs-lookup"><span data-stu-id="43aa5-147">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="43aa5-148">Das Hinzufügen von mehr als einem Ablaufverfolgungslistener desselben Typs und mit demselben Namen führt `Listeners` dazu, dass der Auflistung nur ein Ablaufverfolgungslistener dieses Typs und namens hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="43aa5-148">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="43aa5-149">Sie können der `Listeners` Auflistung jedoch programmgesteuert mehrere identische Listener hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="43aa5-149">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="43aa5-150">Der Wert `initializeData` für das Attribut hängt vom Typ des Listeners ab, den Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="43aa5-150">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="43aa5-151">Nicht alle Ablaufverfolgungslistener erfordern, dass Sie angeben. `initializeData`</span><span class="sxs-lookup"><span data-stu-id="43aa5-151">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="43aa5-152">Wenn Sie `initializeData` das Attribut verwenden, erhalten Sie möglicherweise die Compilerwarnung "Das Attribut 'initializeData' ist nicht deklariert."</span><span class="sxs-lookup"><span data-stu-id="43aa5-152">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="43aa5-153">Diese Warnung wird angezeigt, weil die Konfigurationseinstellungen anhand der abstrakten Basisklasse <xref:System.Diagnostics.TraceListener>überprüft werden, die das `initializeData` Attribut nicht erkennt.</span><span class="sxs-lookup"><span data-stu-id="43aa5-153">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="43aa5-154">In der Regel können Sie diese Warnung für Ablaufverfolgungslistenerimplementierungen ignorieren, die über einen Konstruktor verfügen, der einen Parameter annimmt.</span><span class="sxs-lookup"><span data-stu-id="43aa5-154">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="43aa5-155">Die folgende Tabelle zeigt die Ablaufverfolgungslistener, die in `initializeData` .NET Framework enthalten sind, und beschreibt den Wert ihrer Attribute.</span><span class="sxs-lookup"><span data-stu-id="43aa5-155">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="43aa5-156">Ablaufverfolgungs-Listenerklasse</span><span class="sxs-lookup"><span data-stu-id="43aa5-156">Trace listener class</span></span>|<span data-ttu-id="43aa5-157">initializeData-Attributwert</span><span class="sxs-lookup"><span data-stu-id="43aa5-157">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="43aa5-158">Der `useErrorStream` Wert <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> für den Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="43aa5-158">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="43aa5-159">Legen `initializeData` Sie das`true`Attribut auf " fest, um die Ablaufverfolgung sende- und Debugausgabe in den Standardfehlerstream zu schreiben. setzen Sie`false`es auf " , um in den Standardausgabestream zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="43aa5-159">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="43aa5-160">Der Name der Datei, in die der <xref:System.Diagnostics.DelimitedListTraceListener> schreibt.</span><span class="sxs-lookup"><span data-stu-id="43aa5-160">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="43aa5-161">Der Name einer vorhandenen Ereignisprotokollquelle.</span><span class="sxs-lookup"><span data-stu-id="43aa5-161">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="43aa5-162">Der Name der Datei, in die die <xref:System.Diagnostics.EventSchemaTraceListener> Datei schreibt.</span><span class="sxs-lookup"><span data-stu-id="43aa5-162">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="43aa5-163">Der Name der Datei, in die die <xref:System.Diagnostics.TextWriterTraceListener> Datei schreibt.</span><span class="sxs-lookup"><span data-stu-id="43aa5-163">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="43aa5-164">Der Name der Datei, in die die <xref:System.Diagnostics.XmlWriterTraceListener> Datei schreibt.</span><span class="sxs-lookup"><span data-stu-id="43aa5-164">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="43aa5-165">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="43aa5-165">Configuration File</span></span>  
 <span data-ttu-id="43aa5-166">Dieses Element kann in der Maschinenkonfigurationsdatei (Machine.config) und in der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="43aa5-166">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43aa5-167">Beispiel</span><span class="sxs-lookup"><span data-stu-id="43aa5-167">Example</span></span>  
 <span data-ttu-id="43aa5-168">Das folgende Beispiel zeigt, wie Elemente `console` `textListener` zum Hinzufügen der Listener und zur `Listeners` Auflistung für die Ablaufverfolgungsquelle `TraceSourceApp`verwendet `<add>` werden.</span><span class="sxs-lookup"><span data-stu-id="43aa5-168">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="43aa5-169">Der `textListener` Listener schreibt die Ablaufverfolgungsausgabe in die Datei myListener.log.</span><span class="sxs-lookup"><span data-stu-id="43aa5-169">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="43aa5-170">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="43aa5-170">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="43aa5-171">Ablaufverfolgungs- und Debugeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="43aa5-171">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="43aa5-172">Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="43aa5-172">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
