---
title: <sources>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sources
helpviewer_keywords:
- sources element
- trace sources
- <sources> element
ms.assetid: c727b2e2-423a-4463-a223-013f40ff16a3
ms.openlocfilehash: 2a76816ee73f516b3c7544877a77531acaa8e09c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153268"
---
# <a name="sources-element"></a><span data-ttu-id="b4d90-102">\<Quellen> Element</span><span class="sxs-lookup"><span data-stu-id="b4d90-102">\<sources> Element</span></span>
<span data-ttu-id="b4d90-103">Gibt Ablaufverfolgungsquellen an, die Ablaufverfolgungsnachrichten initiieren.</span><span class="sxs-lookup"><span data-stu-id="b4d90-103">Specifies trace sources that initiate tracing messages.</span></span>  

<span data-ttu-id="b4d90-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b4d90-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b4d90-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="b4d90-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="b4d90-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Quellen>**</span><span class="sxs-lookup"><span data-stu-id="b4d90-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sources>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b4d90-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4d90-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4d90-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b4d90-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b4d90-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b4d90-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4d90-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="b4d90-110">Attributes</span></span>  
 <span data-ttu-id="b4d90-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="b4d90-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b4d90-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b4d90-112">Child Elements</span></span>  
  
|<span data-ttu-id="b4d90-113">Element</span><span class="sxs-lookup"><span data-stu-id="b4d90-113">Element</span></span>|<span data-ttu-id="b4d90-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4d90-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4d90-115">\<Quelle></span><span class="sxs-lookup"><span data-stu-id="b4d90-115">\<source></span></span>](source-element.md)|<span data-ttu-id="b4d90-116">Erforderliches Element</span><span class="sxs-lookup"><span data-stu-id="b4d90-116">Required element.</span></span><br /><br /> <span data-ttu-id="b4d90-117">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="b4d90-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b4d90-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b4d90-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b4d90-119">Element</span><span class="sxs-lookup"><span data-stu-id="b4d90-119">Element</span></span>|<span data-ttu-id="b4d90-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4d90-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b4d90-121">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b4d90-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b4d90-122">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b4d90-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4d90-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b4d90-123">Remarks</span></span>  
 <span data-ttu-id="b4d90-124">Dieses Element kann in der Maschinenkonfigurationsdatei (Machine.config) und in der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b4d90-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4d90-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4d90-125">Example</span></span>  
 <span data-ttu-id="b4d90-126">Das folgende Beispiel zeigt, `<sources>` wie sie das `mySource` Element verwenden, um die `sourceSwitch`Ablaufverfolgungsquelle hinzuzufügen und die Ebene für den Quellschalter mit dem Namen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="b4d90-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="b4d90-127">Ein Konsolenablaufverfolgungslistener wird hinzugefügt, der Ablaufverfolgungsinformationen in die Konsole schreibt.</span><span class="sxs-lookup"><span data-stu-id="b4d90-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <sources>  
         <source name="mySource" switchName="sourceSwitch"
            switchType="System.Diagnostics.SourceSwitch"  >  
            <listeners>  
               <add name="console"
                  type="System.Diagnostics.ConsoleTraceListener" >  
                  <filter type="System.Diagnostics.EventTypeFilter"
                     initializeData="Error" />  
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
  
## <a name="see-also"></a><span data-ttu-id="b4d90-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b4d90-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- [<span data-ttu-id="b4d90-129">Ablaufverfolgungs- und Debugeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="b4d90-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b4d90-130">\<Quelle></span><span class="sxs-lookup"><span data-stu-id="b4d90-130">\<source></span></span>](source-element.md)
