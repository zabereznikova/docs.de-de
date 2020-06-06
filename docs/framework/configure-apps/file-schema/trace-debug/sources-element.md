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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153268"
---
# <a name="sources-element"></a><span data-ttu-id="0fc2f-102">\<sources>-Element</span><span class="sxs-lookup"><span data-stu-id="0fc2f-102">\<sources> Element</span></span>
<span data-ttu-id="0fc2f-103">Gibt Ablauf Verfolgungs Quellen an, die Ablauf Verfolgungs Meldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="0fc2f-103">Specifies trace sources that initiate tracing messages.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<sources>**

## <a name="syntax"></a><span data-ttu-id="0fc2f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0fc2f-104">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0fc2f-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0fc2f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0fc2f-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0fc2f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0fc2f-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="0fc2f-107">Attributes</span></span>  
 <span data-ttu-id="0fc2f-108">Keine</span><span class="sxs-lookup"><span data-stu-id="0fc2f-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0fc2f-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0fc2f-109">Child Elements</span></span>  
  
|<span data-ttu-id="0fc2f-110">Element</span><span class="sxs-lookup"><span data-stu-id="0fc2f-110">Element</span></span>|<span data-ttu-id="0fc2f-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0fc2f-111">Description</span></span>|  
|-------------|-----------------|  
|[\<source>](source-element.md)|<span data-ttu-id="0fc2f-112">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="0fc2f-112">Required element.</span></span><br /><br /> <span data-ttu-id="0fc2f-113">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="0fc2f-113">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0fc2f-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0fc2f-114">Parent Elements</span></span>  
  
|<span data-ttu-id="0fc2f-115">Element</span><span class="sxs-lookup"><span data-stu-id="0fc2f-115">Element</span></span>|<span data-ttu-id="0fc2f-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0fc2f-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0fc2f-117">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="0fc2f-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="0fc2f-118">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="0fc2f-118">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0fc2f-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0fc2f-119">Remarks</span></span>  
 <span data-ttu-id="0fc2f-120">Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0fc2f-120">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fc2f-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0fc2f-121">Example</span></span>  
 <span data-ttu-id="0fc2f-122">Im folgenden Beispiel wird gezeigt, wie das `<sources>` -Element verwendet wird, um die Ablauf Verfolgungs Quelle hinzuzufügen `mySource` und die Ebene für den Quell Switch mit dem Namen festzulegen `sourceSwitch` .</span><span class="sxs-lookup"><span data-stu-id="0fc2f-122">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="0fc2f-123">Ein Konsolen Ablaufverfolgungslistener wird hinzugefügt, der Ablauf Verfolgungs Informationen in die Konsole</span><span class="sxs-lookup"><span data-stu-id="0fc2f-123">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0fc2f-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0fc2f-124">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- [<span data-ttu-id="0fc2f-125">Schema für Ablaufverfolgungs- und Debugeinstellungen</span><span class="sxs-lookup"><span data-stu-id="0fc2f-125">Trace and Debug Settings Schema</span></span>](index.md)
- [\<source>](source-element.md)
