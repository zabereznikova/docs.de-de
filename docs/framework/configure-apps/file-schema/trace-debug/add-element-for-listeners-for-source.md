---
title: <add>-Element für <listeners> für <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: ae5231f43e7c157b5250376f7ab97deccea595e5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277120"
---
# <a name="add-element-for-listeners-for-source"></a><span data-ttu-id="dee79-102">\<Hinzufügen >-Element für \<Listener > für \<Quelle ></span><span class="sxs-lookup"><span data-stu-id="dee79-102">\<add> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="dee79-103">Fügt einen Listener zu der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="dee79-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="dee79-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="dee79-104">\<configuration></span></span>  
<span data-ttu-id="dee79-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="dee79-105">\<system.diagnostics></span></span>  
<span data-ttu-id="dee79-106">\<Quellen ></span><span class="sxs-lookup"><span data-stu-id="dee79-106">\<sources></span></span>  
<span data-ttu-id="dee79-107">\<Quelle ></span><span class="sxs-lookup"><span data-stu-id="dee79-107">\<source></span></span>  
<span data-ttu-id="dee79-108">\<listeners></span><span class="sxs-lookup"><span data-stu-id="dee79-108">\<listeners></span></span>  
<span data-ttu-id="dee79-109">\<add></span><span class="sxs-lookup"><span data-stu-id="dee79-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dee79-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="dee79-110">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dee79-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dee79-111">Attributes and Elements</span></span>  
 <span data-ttu-id="dee79-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dee79-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dee79-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="dee79-113">Attributes</span></span>  
  
|<span data-ttu-id="dee79-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="dee79-114">Attribute</span></span>|<span data-ttu-id="dee79-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dee79-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="dee79-116">Attribut erforderlich, es sei denn, Sie auf einen Listener im verweisen die `sharedListeners` Auflistung, in dem Fall müssen Sie mit Namen auf sie verweisen nur (finden Sie unter den [Beispiel](#example)).</span><span class="sxs-lookup"><span data-stu-id="dee79-116">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="dee79-117">Gibt den Typ des Listeners.</span><span class="sxs-lookup"><span data-stu-id="dee79-117">Specifies the type of the listener.</span></span> <span data-ttu-id="dee79-118">Sie müssen eine Zeichenfolge, die die in angegebenen Anforderungen erfüllt verwenden [angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="dee79-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="dee79-119">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="dee79-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="dee79-120">Die Zeichenfolge, die für die angegebene Klasse an den Konstruktor übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="dee79-120">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="dee79-121">Ein <xref:System.Configuration.ConfigurationException> wird ausgelöst, wenn die Klasse keinen Konstruktor verfügt, die eine Zeichenfolge annimmt.</span><span class="sxs-lookup"><span data-stu-id="dee79-121">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="dee79-122">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="dee79-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="dee79-123">Gibt den Namen des Listeners.</span><span class="sxs-lookup"><span data-stu-id="dee79-123">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="dee79-124">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="dee79-124">Optional attribute.</span></span><br /><br /> <span data-ttu-id="dee79-125">Gibt an, die <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> Eigenschaftswert für den Ablaufverfolgungslistener.</span><span class="sxs-lookup"><span data-stu-id="dee79-125">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="dee79-126">[benutzerdefinierte Attribute]</span><span class="sxs-lookup"><span data-stu-id="dee79-126">[custom attributes]</span></span>|<span data-ttu-id="dee79-127">Optionale Attribute.</span><span class="sxs-lookup"><span data-stu-id="dee79-127">Optional attributes.</span></span><br /><br /> <span data-ttu-id="dee79-128">Gibt den Wert für den Listener-spezifischen Attribute von der <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> Methode für diesen Listener.</span><span class="sxs-lookup"><span data-stu-id="dee79-128">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="dee79-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> ist ein Beispiel für ein zusätzliches Attribut nur für die <xref:System.Diagnostics.DelimitedListTraceListener> Klasse.</span><span class="sxs-lookup"><span data-stu-id="dee79-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dee79-130">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dee79-130">Child Elements</span></span>  
  
|<span data-ttu-id="dee79-131">Element</span><span class="sxs-lookup"><span data-stu-id="dee79-131">Element</span></span>|<span data-ttu-id="dee79-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dee79-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dee79-133">\<filter></span><span class="sxs-lookup"><span data-stu-id="dee79-133">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="dee79-134">Fügt einen Filter zu einem Listener in der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="dee79-134">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dee79-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dee79-135">Parent Elements</span></span>  
  
|<span data-ttu-id="dee79-136">Element</span><span class="sxs-lookup"><span data-stu-id="dee79-136">Element</span></span>|<span data-ttu-id="dee79-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dee79-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="dee79-138">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="dee79-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="dee79-139">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="dee79-139">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="dee79-140">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="dee79-140">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="dee79-141">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="dee79-141">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="dee79-142">Gibt die Listener, die sammeln, speichern und Weiterleiten von Nachrichten an.</span><span class="sxs-lookup"><span data-stu-id="dee79-142">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dee79-143">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dee79-143">Remarks</span></span>  
 <span data-ttu-id="dee79-144">Die Listenerklassen, die im Lieferumfang von .NET Framework leiten sich von der <xref:System.Diagnostics.TraceListener> Klasse.</span><span class="sxs-lookup"><span data-stu-id="dee79-144">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="dee79-145">Wenn Sie keinen angeben der `name` Attribut des Ablaufverfolgungslisteners, der <xref:System.Diagnostics.TraceListener.Name%2A> Eigenschaft des Ablaufverfolgungslisteners standardmäßig eine leere Zeichenfolge ("").</span><span class="sxs-lookup"><span data-stu-id="dee79-145">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="dee79-146">Wenn Ihre Anwendung nur einen Listener verfügt, können Sie ihn hinzufügen, ohne Angabe eines Namens, und können Sie ihn entfernen, indem Sie eine leere Zeichenfolge für den Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="dee79-146">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="dee79-147">Wenn Ihre Anwendung mehr als einen Listener verfügt, Sie jedoch sollte angeben einen eindeutigen Namen für jeden Ablaufverfolgungslistener, wodurch Sie zum Erkennen und Verwalten von einzelnen Ablaufverfolgungslistener in der <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="dee79-147">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dee79-148">Hinzufügen von mehr als eine Ablaufverfolgungs-Listener des gleichen Typs und mit dem gleichen nennen Sie dieses Typs führt nur eine Ablaufverfolgungs-Listener und hinzugefügte der `Listeners` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="dee79-148">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="dee79-149">Allerdings können Sie programmgesteuert mehrere identische Listener hinzufügen der `Listeners` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="dee79-149">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="dee79-150">Der Wert für die `initializeData` -Attributs hängt der Typ des Listeners, die Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="dee79-150">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="dee79-151">Nicht alle Ablaufverfolgungslistener erfordern die Angabe `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="dee79-151">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dee79-152">Bei Verwendung der `initializeData` -Attribut, erhalten Sie möglicherweise die compilerwarnung "das Attribut"InitializeData"ist nicht deklariert."</span><span class="sxs-lookup"><span data-stu-id="dee79-152">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="dee79-153">Diese Warnung tritt auf, da die Konfigurationseinstellungen für die abstrakte Basisklasse überprüft werden <xref:System.Diagnostics.TraceListener>, die nicht erkennt die `initializeData` Attribut.</span><span class="sxs-lookup"><span data-stu-id="dee79-153">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="dee79-154">In der Regel können Sie Ablaufverfolgungs-Listener-Implementierungen diese Warnung ignorieren, die über einen Konstruktor verfügen, der einen Parameter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="dee79-154">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="dee79-155">In der folgende Tabelle werden die Ablaufverfolgungslistener, die mit .NET Framework enthalten sind, und beschreibt den Wert der ihre `initializeData` Attribute.</span><span class="sxs-lookup"><span data-stu-id="dee79-155">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="dee79-156">Trace Listenerklasse</span><span class="sxs-lookup"><span data-stu-id="dee79-156">Trace listener class</span></span>|<span data-ttu-id="dee79-157">InitializeData-Attributwert</span><span class="sxs-lookup"><span data-stu-id="dee79-157">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="dee79-158">Die `useErrorStream` Wert für die <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="dee79-158">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="dee79-159">Legen Sie die `initializeData` -Attribut auf "`true`"Schreiben Ausgabe von Ablaufverfolgungs- und Debugeinstellungen in den Standardfehlerstream; so eingestellt, es"`false`" zum Schreiben in den Standardausgabestream.</span><span class="sxs-lookup"><span data-stu-id="dee79-159">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="dee79-160">Der Name der Datei die <xref:System.Diagnostics.DelimitedListTraceListener> schreibt in.</span><span class="sxs-lookup"><span data-stu-id="dee79-160">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="dee79-161">Der Name einer vorhandenen Ereignisprotokollquelle.</span><span class="sxs-lookup"><span data-stu-id="dee79-161">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="dee79-162">Der Name der Datei, die die <xref:System.Diagnostics.EventSchemaTraceListener> schreibt in.</span><span class="sxs-lookup"><span data-stu-id="dee79-162">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="dee79-163">Der Name der Datei, die die <xref:System.Diagnostics.TextWriterTraceListener> schreibt in.</span><span class="sxs-lookup"><span data-stu-id="dee79-163">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="dee79-164">Der Name der Datei, die die <xref:System.Diagnostics.XmlWriterTraceListener> schreibt in.</span><span class="sxs-lookup"><span data-stu-id="dee79-164">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="dee79-165">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="dee79-165">Configuration File</span></span>  
 <span data-ttu-id="dee79-166">Dieses Element kann in der Computerkonfigurationsdatei (Machine.config) und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dee79-166">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dee79-167">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dee79-167">Example</span></span>  
 <span data-ttu-id="dee79-168">Das folgende Beispiel zeigt, wie Sie mit `<add>` Elemente, die Listener hinzugefügt `console` und `textListener` auf die `Listeners` Auflistung für die Ablaufverfolgungsquelle `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="dee79-168">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="dee79-169">Die `textListener` -Listener schreibt die Ausgabe der Ablaufverfolgung in die Datei myListener.log.</span><span class="sxs-lookup"><span data-stu-id="dee79-169">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dee79-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dee79-170">See also</span></span>
- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="dee79-171">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="dee79-171">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="dee79-172">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="dee79-172">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
