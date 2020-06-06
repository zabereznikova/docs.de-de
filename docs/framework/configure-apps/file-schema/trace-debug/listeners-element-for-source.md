---
title: <listeners>-Element für <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: 0eee325e01b41a15a19e4f40f479596f9d70f73b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153411"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="e11f0-102">\<listeners>-Element für \<source></span><span class="sxs-lookup"><span data-stu-id="e11f0-102">\<listeners> Element for \<source></span></span>
<span data-ttu-id="e11f0-103">Fügt Listener in der-Auflistung für eine hinzu oder entfernt Sie <xref:System.Diagnostics.TraceSource.Listeners%2A> <xref:System.Diagnostics.TraceSource> .</span><span class="sxs-lookup"><span data-stu-id="e11f0-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="e11f0-104">Ein Listener leitet die Ablauf Verfolgungs Ausgabe an ein entsprechendes Ziel, z. b. ein Protokoll, ein Fenster oder eine Textdatei.</span><span class="sxs-lookup"><span data-stu-id="e11f0-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**  
  
## <a name="syntax"></a><span data-ttu-id="e11f0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e11f0-105">Syntax</span></span>  
  
```xml  
<listeners>
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e11f0-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e11f0-106">Attributes and Elements</span></span>  
 <span data-ttu-id="e11f0-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e11f0-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e11f0-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="e11f0-108">Attributes</span></span>  
 <span data-ttu-id="e11f0-109">Keine</span><span class="sxs-lookup"><span data-stu-id="e11f0-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e11f0-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e11f0-110">Child Elements</span></span>  
  
|<span data-ttu-id="e11f0-111">Element</span><span class="sxs-lookup"><span data-stu-id="e11f0-111">Element</span></span>|<span data-ttu-id="e11f0-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e11f0-112">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-source.md)|<span data-ttu-id="e11f0-113">Fügt einen Listener zu der `Listeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="e11f0-113">Adds a listener to the `Listeners` collection.</span></span>|  
|[\<remove>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="e11f0-114">Entfernt einen Listener aus der Auflistung `Listeners` .</span><span class="sxs-lookup"><span data-stu-id="e11f0-114">Removes a listener from the `Listeners` collection.</span></span>|  
|[\<clear>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="e11f0-115">Löscht die `Listeners`-Sammlung für eine Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="e11f0-115">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e11f0-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e11f0-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e11f0-117">Element</span><span class="sxs-lookup"><span data-stu-id="e11f0-117">Element</span></span>|<span data-ttu-id="e11f0-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e11f0-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e11f0-119">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e11f0-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="e11f0-120">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e11f0-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="e11f0-121">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="e11f0-121">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="e11f0-122">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="e11f0-122">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e11f0-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e11f0-123">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="e11f0-124">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="e11f0-124">Configuration File</span></span>  
 <span data-ttu-id="e11f0-125">Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e11f0-125">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e11f0-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e11f0-126">Example</span></span>  
 <span data-ttu-id="e11f0-127">Im folgenden Beispiel wird gezeigt, wie das-Element verwendet wird, um der Quelle einen Ablaufverfolgungslistener `<listeners>` für die `mySource` -Quelle hinzuzufügen und um den Standard</span><span class="sxs-lookup"><span data-stu-id="e11f0-127">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"
            type="System.Diagnostics.ConsoleTraceListener">  
            <filter type="System.Diagnostics.EventTypeFilter"
              initializeData="Error"/>  
          </add>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e11f0-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e11f0-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="e11f0-129">Schema für Ablaufverfolgungs- und Debugeinstellungen</span><span class="sxs-lookup"><span data-stu-id="e11f0-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e11f0-130">Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="e11f0-130">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
