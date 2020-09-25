---
title: <listeners>-Element für <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: 59d078f8dc573a1ce949d225f497dd4500fe808f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173860"
---
# <a name="listeners-element-for-trace"></a><span data-ttu-id="c2cae-102">\<listeners>-Element für \<trace></span><span class="sxs-lookup"><span data-stu-id="c2cae-102">\<listeners> Element for \<trace></span></span>

<span data-ttu-id="c2cae-103">Gibt einen Listener an, der Nachrichten sammelt, speichert und weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="c2cae-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="c2cae-104">Listener leiten die Ablauf Verfolgungs Ausgabe an ein entsprechendes Ziel weiter.</span><span class="sxs-lookup"><span data-stu-id="c2cae-104">Listeners direct the tracing output to an appropriate target.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**

## <a name="syntax"></a><span data-ttu-id="c2cae-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2cae-105">Syntax</span></span>  
  
```xml  
<listeners>
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2cae-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c2cae-106">Attributes and Elements</span></span>  

 <span data-ttu-id="c2cae-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c2cae-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2cae-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="c2cae-108">Attributes</span></span>  

 <span data-ttu-id="c2cae-109">Keine</span><span class="sxs-lookup"><span data-stu-id="c2cae-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c2cae-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c2cae-110">Child Elements</span></span>  
  
|<span data-ttu-id="c2cae-111">Element</span><span class="sxs-lookup"><span data-stu-id="c2cae-111">Element</span></span>|<span data-ttu-id="c2cae-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c2cae-112">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="c2cae-113">Fügt einen Listener zu der `Listeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="c2cae-113">Adds a listener to the `Listeners` collection.</span></span>|  
|[\<clear>](clear-element-for-listeners-for-trace.md)|<span data-ttu-id="c2cae-114">Löscht die `Listeners`-Sammlung für die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="c2cae-114">Clears the `Listeners` collection for trace.</span></span>|  
|[\<remove>](remove-element-for-listeners-for-trace.md)|<span data-ttu-id="c2cae-115">Entfernt einen Listener aus der Auflistung `Listeners` .</span><span class="sxs-lookup"><span data-stu-id="c2cae-115">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c2cae-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c2cae-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c2cae-117">Element</span><span class="sxs-lookup"><span data-stu-id="c2cae-117">Element</span></span>|<span data-ttu-id="c2cae-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c2cae-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c2cae-119">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="c2cae-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="c2cae-120">Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.</span><span class="sxs-lookup"><span data-stu-id="c2cae-120">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="c2cae-121">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="c2cae-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2cae-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c2cae-122">Remarks</span></span>  

 <span data-ttu-id="c2cae-123">Die <xref:System.Diagnostics.Debug> - <xref:System.Diagnostics.Trace> Klasse und die- **Listeners** Klasse verwenden dieselbe Listener-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="c2cae-123">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="c2cae-124">Wenn Sie der Auflistung in einer dieser Klassen ein Listenerobjekt hinzufügen, verwendet die andere Klasse denselben Listener.</span><span class="sxs-lookup"><span data-stu-id="c2cae-124">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="c2cae-125">Die Listenerklassen, die mit dem .NET Framework ausgeliefert werden, werden von der- <xref:System.Diagnostics.TraceListener> Klasse abgeleitet</span><span class="sxs-lookup"><span data-stu-id="c2cae-125">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="c2cae-126">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="c2cae-126">Configuration File</span></span>  

 <span data-ttu-id="c2cae-127">Dieses Element kann in der Computer Konfigurationsdatei (Machine.config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c2cae-127">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2cae-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c2cae-128">Example</span></span>  

 <span data-ttu-id="c2cae-129">Im folgenden Beispiel wird gezeigt, wie das **\<listeners>** -Element verwendet wird, um die Listener und der Listener-Auflistung hinzuzufügen `MyListener` `MyEventListener` . **Listeners**</span><span class="sxs-lookup"><span data-stu-id="c2cae-129">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="c2cae-130">`MyListener` erstellt eine Datei `MyListener.log` mit dem Namen und schreibt die Ausgabe in die Datei.</span><span class="sxs-lookup"><span data-stu-id="c2cae-130">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="c2cae-131">`MyEventListener` erstellt einen Eintrag im Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="c2cae-131">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c2cae-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c2cae-132">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="c2cae-133">Schema für Ablaufverfolgungs- und Debugeinstellungen</span><span class="sxs-lookup"><span data-stu-id="c2cae-133">Trace and Debug Settings Schema</span></span>](index.md)
