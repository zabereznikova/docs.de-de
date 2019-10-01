---
title: <listeners>-Element für <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: 84b67532825372e7f69d86e1ef6060f4263587eb
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699351"
---
# <a name="listeners-element-for-trace"></a><span data-ttu-id="f0a1b-102">\<listener > Element für \<trace ></span><span class="sxs-lookup"><span data-stu-id="f0a1b-102">\<listeners> Element for \<trace></span></span>
<span data-ttu-id="f0a1b-103">Gibt einen Listener an, der Nachrichten sammelt, speichert und weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="f0a1b-104">Listener leiten die Ablauf Verfolgungs Ausgabe an ein entsprechendes Ziel weiter.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-104">Listeners direct the tracing output to an appropriate target.</span></span>  
  
[<span data-ttu-id="f0a1b-105"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="f0a1b-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="f0a1b-106">&nbsp; @ no__t-1[ **\<system. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="f0a1b-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="f0a1b-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<trace >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="f0a1b-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>  
<span data-ttu-id="f0a1b-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<listener >**</span><span class="sxs-lookup"><span data-stu-id="f0a1b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0a1b-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0a1b-109">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0a1b-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f0a1b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f0a1b-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0a1b-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="f0a1b-112">Attributes</span></span>  
 <span data-ttu-id="f0a1b-113">Keine</span><span class="sxs-lookup"><span data-stu-id="f0a1b-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f0a1b-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f0a1b-114">Child Elements</span></span>  
  
|<span data-ttu-id="f0a1b-115">Element</span><span class="sxs-lookup"><span data-stu-id="f0a1b-115">Element</span></span>|<span data-ttu-id="f0a1b-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0a1b-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0a1b-117">\<add></span><span class="sxs-lookup"><span data-stu-id="f0a1b-117">\<add></span></span>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="f0a1b-118">Fügt einen Listener zu der `Listeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-118">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="f0a1b-119">\<clear></span><span class="sxs-lookup"><span data-stu-id="f0a1b-119">\<clear></span></span>](clear-element-for-listeners-for-trace.md)|<span data-ttu-id="f0a1b-120">Löscht die `Listeners`-Sammlung für die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="f0a1b-121">\<remove></span><span class="sxs-lookup"><span data-stu-id="f0a1b-121">\<remove></span></span>](remove-element-for-listeners-for-trace.md)|<span data-ttu-id="f0a1b-122">Entfernt einen Listener aus der `Listeners`-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-122">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f0a1b-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f0a1b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f0a1b-124">Element</span><span class="sxs-lookup"><span data-stu-id="f0a1b-124">Element</span></span>|<span data-ttu-id="f0a1b-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0a1b-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f0a1b-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="f0a1b-127">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="f0a1b-128">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-128">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0a1b-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0a1b-129">Remarks</span></span>  
 <span data-ttu-id="f0a1b-130">Die Klassen <xref:System.Diagnostics.Debug> und <xref:System.Diagnostics.Trace> **verwenden dieselbe Listener** -Auflistung.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-130">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="f0a1b-131">Wenn Sie der Auflistung in einer dieser Klassen ein Listenerobjekt hinzufügen, verwendet die andere Klasse denselben Listener.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-131">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="f0a1b-132">Die Listenerklassen, die mit dem .NET Framework ausgeliefert werden, werden von der <xref:System.Diagnostics.TraceListener>-Klasse abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-132">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="f0a1b-133">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="f0a1b-133">Configuration File</span></span>  
 <span data-ttu-id="f0a1b-134">Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0a1b-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f0a1b-135">Example</span></span>  
 <span data-ttu-id="f0a1b-136">Im folgenden Beispiel wird gezeigt, wie das **\<listener->** -Element verwendet wird, **um die Listener** `MyListener` und `MyEventListener` der Listener-Auflistung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-136">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="f0a1b-137">`MyListener` erstellt eine Datei mit dem Namen `MyListener.log` und schreibt die Ausgabe in die Datei.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-137">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="f0a1b-138">`MyEventListener` erstellt einen Eintrag im Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-138">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="true" indentsize="0">  
      <listeners>  
        <add name="myListener"   
          type="System.Diagnostics.TextWriterTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"   
          initializeData="c:\myListener.log" />  
        <add name="MyEventListener"  
          type="System.Diagnostics.EventLogTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"  
          initializeData="MyConfigEventLog"/>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0a1b-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0a1b-139">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="f0a1b-140">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="f0a1b-140">Trace and Debug Settings Schema</span></span>](index.md)
