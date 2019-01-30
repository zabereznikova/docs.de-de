---
title: <listeners>-Element für <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: cc6ba06127703fbda5d9edf8211b4b206127cbda
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271672"
---
# <a name="listeners-element-for-trace"></a><span data-ttu-id="58f64-102">\<Listener >-Element für \<Ablaufverfolgung ></span><span class="sxs-lookup"><span data-stu-id="58f64-102">\<listeners> Element for \<trace></span></span>
<span data-ttu-id="58f64-103">Gibt an, einen Listener, der sammelt, speichert, und leitet Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="58f64-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="58f64-104">Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel.</span><span class="sxs-lookup"><span data-stu-id="58f64-104">Listeners direct the tracing output to an appropriate target.</span></span>  
  
 <span data-ttu-id="58f64-105">\<Configuration >-Element</span><span class="sxs-lookup"><span data-stu-id="58f64-105">\<configuration> Element</span></span>  
<span data-ttu-id="58f64-106">\<System.Diagnostics >-Element</span><span class="sxs-lookup"><span data-stu-id="58f64-106">\<system.diagnostics> Element</span></span>  
<span data-ttu-id="58f64-107">\<Ablaufverfolgung >-Element</span><span class="sxs-lookup"><span data-stu-id="58f64-107">\<trace> Element</span></span>  
<span data-ttu-id="58f64-108">\<Listener >-Element für \<Ablaufverfolgung ></span><span class="sxs-lookup"><span data-stu-id="58f64-108">\<listeners> Element for \<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58f64-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="58f64-109">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58f64-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="58f64-110">Attributes and Elements</span></span>  
 <span data-ttu-id="58f64-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="58f64-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58f64-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="58f64-112">Attributes</span></span>  
 <span data-ttu-id="58f64-113">Keine</span><span class="sxs-lookup"><span data-stu-id="58f64-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="58f64-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="58f64-114">Child Elements</span></span>  
  
|<span data-ttu-id="58f64-115">Element</span><span class="sxs-lookup"><span data-stu-id="58f64-115">Element</span></span>|<span data-ttu-id="58f64-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58f64-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58f64-117">\<add></span><span class="sxs-lookup"><span data-stu-id="58f64-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|<span data-ttu-id="58f64-118">Fügt einen Listener zu der `Listeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="58f64-118">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="58f64-119">\<clear></span><span class="sxs-lookup"><span data-stu-id="58f64-119">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-trace.md)|<span data-ttu-id="58f64-120">Löscht die `Listeners`-Sammlung für die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="58f64-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="58f64-121">\<remove></span><span class="sxs-lookup"><span data-stu-id="58f64-121">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)|<span data-ttu-id="58f64-122">Entfernt einen Listener aus der `Listeners` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="58f64-122">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="58f64-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="58f64-123">Parent Elements</span></span>  
  
|<span data-ttu-id="58f64-124">Element</span><span class="sxs-lookup"><span data-stu-id="58f64-124">Element</span></span>|<span data-ttu-id="58f64-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58f64-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="58f64-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="58f64-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="58f64-127">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="58f64-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="58f64-128">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="58f64-128">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58f64-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="58f64-129">Remarks</span></span>  
 <span data-ttu-id="58f64-130">Die <xref:System.Diagnostics.Debug> und <xref:System.Diagnostics.Trace> Klassen verwenden dieselbe **Listener** Auflistung.</span><span class="sxs-lookup"><span data-stu-id="58f64-130">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="58f64-131">Wenn Sie einen Listener-Objekt der Auflistung in einer dieser Klassen hinzufügen, wird die andere Klasse den gleichen Listener verwendet.</span><span class="sxs-lookup"><span data-stu-id="58f64-131">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="58f64-132">Die Listenerklassen, die im Lieferumfang von .NET Framework leiten sich von der <xref:System.Diagnostics.TraceListener> Klasse.</span><span class="sxs-lookup"><span data-stu-id="58f64-132">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="58f64-133">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="58f64-133">Configuration File</span></span>  
 <span data-ttu-id="58f64-134">Dieses Element kann in der Computerkonfigurationsdatei (Machine.config) und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="58f64-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58f64-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="58f64-135">Example</span></span>  
 <span data-ttu-id="58f64-136">Das folgende Beispiel zeigt, wie Sie mit der  **\<Listener >** Element, um die Listener hinzuzufügen `MyListener` und `MyEventListener` auf die **Listener** Auflistung.</span><span class="sxs-lookup"><span data-stu-id="58f64-136">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="58f64-137">`MyListener` erstellt eine Datei namens `MyListener.log` und schreibt die Ausgabe in der Datei.</span><span class="sxs-lookup"><span data-stu-id="58f64-137">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="58f64-138">`MyEventListener` erstellt einen Eintrag im Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="58f64-138">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="58f64-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58f64-139">See also</span></span>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="58f64-140">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="58f64-140">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
