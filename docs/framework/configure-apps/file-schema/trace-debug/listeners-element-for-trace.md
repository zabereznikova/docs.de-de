---
title: <listeners>-Element für <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: 10530cfadf2e182f912c699e50294af4b57f47b5
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088864"
---
# <a name="listeners-element-for-trace"></a><span data-ttu-id="dc5c2-102">\<Listener > Element für \<Trace ></span><span class="sxs-lookup"><span data-stu-id="dc5c2-102">\<listeners> Element for \<trace></span></span>
<span data-ttu-id="dc5c2-103">Gibt einen Listener an, der Nachrichten sammelt, speichert und weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="dc5c2-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="dc5c2-104">Listener leiten die Ablauf Verfolgungs Ausgabe an ein entsprechendes Ziel weiter.</span><span class="sxs-lookup"><span data-stu-id="dc5c2-104">Listeners direct the tracing output to an appropriate target.</span></span>  

<span data-ttu-id="dc5c2-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dc5c2-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dc5c2-106">&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="dc5c2-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="dc5c2-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Ablauf Verfolgungs**](trace-element.md) ></span><span class="sxs-lookup"><span data-stu-id="dc5c2-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="dc5c2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<Listener **>**</span><span class="sxs-lookup"><span data-stu-id="dc5c2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>

## <a name="syntax"></a><span data-ttu-id="dc5c2-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc5c2-109">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc5c2-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dc5c2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="dc5c2-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dc5c2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc5c2-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="dc5c2-112">Attributes</span></span>  
 <span data-ttu-id="dc5c2-113">Keine</span><span class="sxs-lookup"><span data-stu-id="dc5c2-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dc5c2-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dc5c2-114">Child Elements</span></span>  
  
|<span data-ttu-id="dc5c2-115">Element</span><span class="sxs-lookup"><span data-stu-id="dc5c2-115">Element</span></span>|<span data-ttu-id="dc5c2-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc5c2-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc5c2-117">\<add></span><span class="sxs-lookup"><span data-stu-id="dc5c2-117">\<add></span></span>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="dc5c2-118">Fügt einen Listener zu der `Listeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc5c2-118">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="dc5c2-119">\<clear></span><span class="sxs-lookup"><span data-stu-id="dc5c2-119">\<clear></span></span>](clear-element-for-listeners-for-trace.md)|<span data-ttu-id="dc5c2-120">Löscht die `Listeners`-Sammlung für die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="dc5c2-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="dc5c2-121">\<remove></span><span class="sxs-lookup"><span data-stu-id="dc5c2-121">\<remove></span></span>](remove-element-for-listeners-for-trace.md)|<span data-ttu-id="dc5c2-122">Entfernt einen Listener aus der `Listeners` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="dc5c2-122">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dc5c2-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dc5c2-123">Parent Elements</span></span>  
  
|<span data-ttu-id="dc5c2-124">Element</span><span class="sxs-lookup"><span data-stu-id="dc5c2-124">Element</span></span>|<span data-ttu-id="dc5c2-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc5c2-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="dc5c2-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="dc5c2-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="dc5c2-127">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="dc5c2-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="dc5c2-128">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="dc5c2-128">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc5c2-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dc5c2-129">Remarks</span></span>  
 <span data-ttu-id="dc5c2-130">Die Klassen <xref:System.Diagnostics.Debug> und <xref:System.Diagnostics.Trace> **verwenden dieselbe Listener** -Auflistung.</span><span class="sxs-lookup"><span data-stu-id="dc5c2-130">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="dc5c2-131">Wenn Sie der Auflistung in einer dieser Klassen ein Listenerobjekt hinzufügen, verwendet die andere Klasse denselben Listener.</span><span class="sxs-lookup"><span data-stu-id="dc5c2-131">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="dc5c2-132">Die Listenerklassen, die mit dem .NET Framework ausgeliefert werden, werden von der <xref:System.Diagnostics.TraceListener> Klasse abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="dc5c2-132">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="dc5c2-133">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="dc5c2-133">Configuration File</span></span>  
 <span data-ttu-id="dc5c2-134">Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dc5c2-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc5c2-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dc5c2-135">Example</span></span>  
 <span data-ttu-id="dc5c2-136">Im folgenden Beispiel wird gezeigt, wie das **\<Listener >** -Element verwendet wird, um die Listener `MyListener` und **`MyEventListener` der Listener** -Auflistung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="dc5c2-136">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="dc5c2-137">`MyListener` erstellt eine Datei mit dem Namen `MyListener.log` und schreibt die Ausgabe in die Datei.</span><span class="sxs-lookup"><span data-stu-id="dc5c2-137">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="dc5c2-138">`MyEventListener` erstellt einen Eintrag im Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="dc5c2-138">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dc5c2-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc5c2-139">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="dc5c2-140">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="dc5c2-140">Trace and Debug Settings Schema</span></span>](index.md)
