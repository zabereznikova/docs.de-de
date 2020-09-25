---
title: <add> -Element für <listeners> für <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: a5abaffbad986785b8879297883da9614f0a8103
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201693"
---
# <a name="add-element-for-listeners-for-source"></a><span data-ttu-id="6a2f6-102">\<add> -Element für \<listeners> für \<source></span><span class="sxs-lookup"><span data-stu-id="6a2f6-102">\<add> Element for \<listeners> for \<source></span></span>

<span data-ttu-id="6a2f6-103">Fügt einen Listener zu der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="6a2f6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a2f6-104">Syntax</span></span>  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a2f6-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6a2f6-105">Attributes and Elements</span></span>  

 <span data-ttu-id="6a2f6-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a2f6-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="6a2f6-107">Attributes</span></span>  
  
|<span data-ttu-id="6a2f6-108">attribute</span><span class="sxs-lookup"><span data-stu-id="6a2f6-108">Attribute</span></span>|<span data-ttu-id="6a2f6-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a2f6-109">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="6a2f6-110">Erforderliches Attribut, es sei denn, Sie verweisen in der Auflistung auf einen Listener `sharedListeners` . in diesem Fall müssen Sie nur anhand des Namens darauf verweisen (siehe [Beispiel](#example)).</span><span class="sxs-lookup"><span data-stu-id="6a2f6-110">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="6a2f6-111">Gibt den Typ des Listener an.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-111">Specifies the type of the listener.</span></span> <span data-ttu-id="6a2f6-112">Sie müssen eine Zeichenfolge verwenden, die den unter [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)angegebenen Anforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-112">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="6a2f6-113">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="6a2f6-114">Die Zeichenfolge, die an den Konstruktor für die angegebene Klasse übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-114">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="6a2f6-115">Eine <xref:System.Configuration.ConfigurationException> wird ausgelöst, wenn die Klasse über keinen Konstruktor verfügt, der eine Zeichenfolge annimmt.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-115">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="6a2f6-116">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="6a2f6-117">Gibt den Namen des Listener an.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-117">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="6a2f6-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="6a2f6-119">Gibt den <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> Eigenschafts Wert für den Ablaufverfolgungslistener an.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-119">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="6a2f6-120">[benutzerdefinierte Attribute]</span><span class="sxs-lookup"><span data-stu-id="6a2f6-120">[custom attributes]</span></span>|<span data-ttu-id="6a2f6-121">Optionale Attribute.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-121">Optional attributes.</span></span><br /><br /> <span data-ttu-id="6a2f6-122">Gibt den Wert für listenerspezifische Attribute an, die von der- <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> Methode für diesen Listener identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-122">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="6a2f6-123"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> ist ein Beispiel für ein zusätzliches Attribut, das für die-Klasse eindeutig ist <xref:System.Diagnostics.DelimitedListTraceListener> .</span><span class="sxs-lookup"><span data-stu-id="6a2f6-123"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6a2f6-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6a2f6-124">Child Elements</span></span>  
  
|<span data-ttu-id="6a2f6-125">Element</span><span class="sxs-lookup"><span data-stu-id="6a2f6-125">Element</span></span>|<span data-ttu-id="6a2f6-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a2f6-126">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="6a2f6-127">Fügt einen Filter zu einem Listener in der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-127">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6a2f6-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6a2f6-128">Parent Elements</span></span>  
  
|<span data-ttu-id="6a2f6-129">Element</span><span class="sxs-lookup"><span data-stu-id="6a2f6-129">Element</span></span>|<span data-ttu-id="6a2f6-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a2f6-130">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6a2f6-131">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-131">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="6a2f6-132">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-132">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="6a2f6-133">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-133">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="6a2f6-134">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-134">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="6a2f6-135">Gibt Listener an, die Nachrichten erfassen, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-135">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a2f6-136">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6a2f6-136">Remarks</span></span>  

 <span data-ttu-id="6a2f6-137">Die Listenerklassen, die mit dem .NET Framework ausgeliefert werden, werden von der- <xref:System.Diagnostics.TraceListener> Klasse abgeleitet</span><span class="sxs-lookup"><span data-stu-id="6a2f6-137">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="6a2f6-138">Wenn Sie das-Attribut des Ablaufverfolgungslistener nicht angeben `name` , wird <xref:System.Diagnostics.TraceListener.Name%2A> standardmäßig eine leere Zeichenfolge ("") für die-Eigenschaft des Ablaufverfolgungslistener verwendet</span><span class="sxs-lookup"><span data-stu-id="6a2f6-138">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="6a2f6-139">Wenn die Anwendung nur über einen Listener verfügt, können Sie Sie hinzufügen, ohne einen Namen anzugeben, und Sie können Sie entfernen, indem Sie eine leere Zeichenfolge für den Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-139">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="6a2f6-140">Wenn Ihre Anwendung jedoch über mehr als einen Listener verfügt, sollten Sie einen eindeutigen Namen für jeden Ablaufverfolgungslistener angeben, mit dem Sie einzelne Ablaufverfolgungslistener in der Sammlung identifizieren und verwalten können <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="6a2f6-140">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6a2f6-141">Das Hinzufügen von mehr als einem Ablaufverfolgungslistener desselben Typs und desselben Namens führt dazu, dass nur ein Ablaufverfolgungslistener dieses Typs und namens zur Auflistung hinzugefügt wird `Listeners` .</span><span class="sxs-lookup"><span data-stu-id="6a2f6-141">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="6a2f6-142">Allerdings können Sie der Auflistung Programm gesteuert mehrere identische Listener hinzufügen `Listeners` .</span><span class="sxs-lookup"><span data-stu-id="6a2f6-142">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="6a2f6-143">Der Wert für das-Attribut ist abhängig vom `initializeData` Typ des von Ihnen erstellten Listener.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-143">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="6a2f6-144">Nicht alle Ablaufverfolgungslistener erfordern, dass `initializeData` Sie angeben</span><span class="sxs-lookup"><span data-stu-id="6a2f6-144">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6a2f6-145">Wenn Sie das- `initializeData` Attribut verwenden, erhalten Sie möglicherweise die Compilerwarnung, dass das initializeData-Attribut nicht deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-145">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="6a2f6-146">Diese Warnung tritt auf, weil die Konfigurationseinstellungen anhand der abstrakten Basisklasse überprüft werden <xref:System.Diagnostics.TraceListener> , die das- `initializeData` Attribut nicht erkennt.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-146">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="6a2f6-147">Normalerweise können Sie diese Warnung für Ablaufverfolgungslistener-Implementierungen ignorieren, die über einen Konstruktor verfügen, der einen Parameter annimmt</span><span class="sxs-lookup"><span data-stu-id="6a2f6-147">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="6a2f6-148">In der folgenden Tabelle werden die Ablaufverfolgungslistener angezeigt, die im .NET Framework enthalten sind, und der Wert ihrer Attribute wird beschrieben `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="6a2f6-148">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="6a2f6-149">Trace-Listenerklasse</span><span class="sxs-lookup"><span data-stu-id="6a2f6-149">Trace listener class</span></span>|<span data-ttu-id="6a2f6-150">initializeData-Attribut Wert</span><span class="sxs-lookup"><span data-stu-id="6a2f6-150">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="6a2f6-151">Der `useErrorStream` Wert für den <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-151">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="6a2f6-152">Legen `initializeData` Sie das-Attribut auf "" fest, um die Ablauf `true` Verfolgung und Debugausgabe in den Standardfehlerstream zu schreiben. Legen Sie Sie auf " `false` " fest</span><span class="sxs-lookup"><span data-stu-id="6a2f6-152">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="6a2f6-153">Der Name der Datei, in die der <xref:System.Diagnostics.DelimitedListTraceListener> schreibt.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-153">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="6a2f6-154">Der Name einer vorhandenen Ereignisprotokollquelle.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-154">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="6a2f6-155">Der Name der Datei, in die <xref:System.Diagnostics.EventSchemaTraceListener> geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-155">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="6a2f6-156">Der Name der Datei, in die <xref:System.Diagnostics.TextWriterTraceListener> geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-156">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="6a2f6-157">Der Name der Datei, in die <xref:System.Diagnostics.XmlWriterTraceListener> geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-157">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="6a2f6-158">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="6a2f6-158">Configuration File</span></span>  

 <span data-ttu-id="6a2f6-159">Dieses Element kann in der Computer Konfigurationsdatei (Machine.config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6a2f6-159">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a2f6-160">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6a2f6-160">Example</span></span>  

 <span data-ttu-id="6a2f6-161">Im folgenden Beispiel wird gezeigt, wie Elemente verwendet werden, `<add>` um die Listener `console` und der-Auflistung `textListener` `Listeners` für die Ablauf Verfolgungs Quelle hinzuzufügen `TraceSourceApp` .</span><span class="sxs-lookup"><span data-stu-id="6a2f6-161">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="6a2f6-162">Der `textListener` Listener schreibt die Ablauf Verfolgungs Ausgabe in die Datei "MyListener. log".</span><span class="sxs-lookup"><span data-stu-id="6a2f6-162">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6a2f6-163">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6a2f6-163">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="6a2f6-164">Schema für Ablaufverfolgungs- und Debugeinstellungen</span><span class="sxs-lookup"><span data-stu-id="6a2f6-164">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6a2f6-165">Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="6a2f6-165">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
