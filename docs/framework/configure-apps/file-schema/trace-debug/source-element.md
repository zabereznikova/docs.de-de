---
title: <source>-Element
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: 417722ce2f3865350158413307495e3ab435d386
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153294"
---
# <a name="source-element"></a><span data-ttu-id="7dcea-102">\<source>-Element</span><span class="sxs-lookup"><span data-stu-id="7dcea-102">\<source> Element</span></span>
<span data-ttu-id="7dcea-103">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="7dcea-103">Specifies a trace source that initiates tracing messages.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<source>**

## <a name="syntax"></a><span data-ttu-id="7dcea-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7dcea-104">Syntax</span></span>  
  
```xml  
<source>
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7dcea-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7dcea-105">Attributes and Elements</span></span>  
 <span data-ttu-id="7dcea-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7dcea-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7dcea-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="7dcea-107">Attributes</span></span>  
  
|<span data-ttu-id="7dcea-108">attribute</span><span class="sxs-lookup"><span data-stu-id="7dcea-108">Attribute</span></span>|<span data-ttu-id="7dcea-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7dcea-109">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="7dcea-110">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="7dcea-110">Optional attribute.</span></span><br /><br /> <span data-ttu-id="7dcea-111">Gibt den Namen der Ablauf Verfolgungs Quelle an.</span><span class="sxs-lookup"><span data-stu-id="7dcea-111">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="7dcea-112">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="7dcea-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="7dcea-113">Gibt den Namen einer Instanz eines Ablauf Verfolgungs Switchs in der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="7dcea-113">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="7dcea-114">Wenn der Schalter nicht in einem-Element identifiziert wird `<switches>` , gibt der Wert die Ebene für den Schalter an.</span><span class="sxs-lookup"><span data-stu-id="7dcea-114">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="7dcea-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="7dcea-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="7dcea-116">Gibt den Typ des Ablauf Verfolgungs Schalters an.</span><span class="sxs-lookup"><span data-stu-id="7dcea-116">Specifies the type of the trace switch.</span></span> <span data-ttu-id="7dcea-117">Wenn der Typ vorhanden ist, muss er ein gültiger Klassenname sein und darf keine leere Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="7dcea-117">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="7dcea-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="7dcea-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="7dcea-119">Gibt den Wert für ein Attribut für eine Ablauf Verfolgungs Quelle an, das durch die- <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> Methode für diese Ablauf Verfolgungs Quelle identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="7dcea-119">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7dcea-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7dcea-120">Child Elements</span></span>  
  
|<span data-ttu-id="7dcea-121">Element</span><span class="sxs-lookup"><span data-stu-id="7dcea-121">Element</span></span>|<span data-ttu-id="7dcea-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7dcea-122">Description</span></span>|  
|-------------|-----------------|  
|[\<listeners>](listeners-element-for-source.md)|<span data-ttu-id="7dcea-123">Enthält Listener, die Nachrichten erfassen, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="7dcea-123">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7dcea-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7dcea-124">Parent Elements</span></span>  
  
|<span data-ttu-id="7dcea-125">Element</span><span class="sxs-lookup"><span data-stu-id="7dcea-125">Element</span></span>|<span data-ttu-id="7dcea-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7dcea-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7dcea-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="7dcea-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="7dcea-128">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7dcea-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="7dcea-129">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="7dcea-129">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7dcea-130">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7dcea-130">Remarks</span></span>  
 <span data-ttu-id="7dcea-131">Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7dcea-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dcea-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7dcea-132">Example</span></span>  
 <span data-ttu-id="7dcea-133">Im folgenden Beispiel wird gezeigt, wie das `<source>` -Element verwendet wird, um die Ablauf Verfolgungs Quelle hinzuzufügen `mySource` und die Ebene für den Quell Switch mit dem Namen festzulegen `sourceSwitch` .</span><span class="sxs-lookup"><span data-stu-id="7dcea-133">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="7dcea-134">Ein Konsolen Ablaufverfolgungslistener wird hinzugefügt, der Ablauf Verfolgungs Informationen in die Konsole</span><span class="sxs-lookup"><span data-stu-id="7dcea-134">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
        <switches>  
           <add name="sourceSwitch" value="Warning" />  
        </switches>
  </system.diagnostics>
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7dcea-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7dcea-135">See also</span></span>

- [<span data-ttu-id="7dcea-136">Schema für Ablaufverfolgungs- und Debugeinstellungen</span><span class="sxs-lookup"><span data-stu-id="7dcea-136">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7dcea-137">Ablaufverfolgungsschalter</span><span class="sxs-lookup"><span data-stu-id="7dcea-137">Trace Switches</span></span>](../../../debug-trace-profile/trace-switches.md)
