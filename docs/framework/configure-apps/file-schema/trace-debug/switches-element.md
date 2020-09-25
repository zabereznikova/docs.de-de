---
title: <switches>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches
- http://schemas.microsoft.com/.NetConfiguration/v2.0#switches
helpviewer_keywords:
- <switches> element
- switches element
- trace switches, <switches> element
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
ms.openlocfilehash: bdd6efdec1e118075495002509c7367c1162baba
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176096"
---
# <a name="switches-element"></a><span data-ttu-id="f051f-102">\<switches>-Element</span><span class="sxs-lookup"><span data-stu-id="f051f-102">\<switches> Element</span></span>

<span data-ttu-id="f051f-103">Enthält Ablaufverfolgungsschalter und die Ebene, für die diese festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="f051f-103">Contains trace switches and the level where the trace switches are set.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<switches>**

## <a name="syntax"></a><span data-ttu-id="f051f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f051f-104">Syntax</span></span>  
  
```xml  
      <switches>
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f051f-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f051f-105">Attributes and Elements</span></span>  

 <span data-ttu-id="f051f-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f051f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f051f-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="f051f-107">Attributes</span></span>  

 <span data-ttu-id="f051f-108">Keine</span><span class="sxs-lookup"><span data-stu-id="f051f-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f051f-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f051f-109">Child Elements</span></span>  
  
|<span data-ttu-id="f051f-110">Element</span><span class="sxs-lookup"><span data-stu-id="f051f-110">Element</span></span>|<span data-ttu-id="f051f-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f051f-111">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-switches.md)|<span data-ttu-id="f051f-112">Gibt die Ebene an, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f051f-112">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f051f-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f051f-113">Parent Elements</span></span>  
  
|<span data-ttu-id="f051f-114">Element</span><span class="sxs-lookup"><span data-stu-id="f051f-114">Element</span></span>|<span data-ttu-id="f051f-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f051f-115">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f051f-116">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f051f-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="f051f-117">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f051f-117">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f051f-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f051f-118">Remarks</span></span>  

 <span data-ttu-id="f051f-119">Sie können die Ebene eines Ablauf Verfolgungs Schalters ändern, indem Sie ihn in eine Konfigurationsdatei einfügen.</span><span class="sxs-lookup"><span data-stu-id="f051f-119">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="f051f-120">Wenn der Schalter ein ist <xref:System.Diagnostics.BooleanSwitch> , können Sie ihn aktivieren und deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f051f-120">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="f051f-121">Wenn der Schalter ein ist <xref:System.Diagnostics.TraceSwitch> , können Sie ihm verschiedene Ebenen zuweisen, um die Typen der Ablauf Verfolgungs-oder Debugmeldungen anzugeben, die die Anwendung ausgibt.</span><span class="sxs-lookup"><span data-stu-id="f051f-121">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f051f-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f051f-122">Example</span></span>  

 <span data-ttu-id="f051f-123">Im folgenden Beispiel wird gezeigt, wie das **\<switch>** -Element verwendet wird, um den Ablauf `General` Verfolgungs Schalter auf die Ebene festzulegen <xref:System.Diagnostics.TraceLevel> und den `Data` booleschen Ablauf Verfolgungs Schalter zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f051f-123">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f051f-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f051f-124">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="f051f-125">Schema für Ablaufverfolgungs- und Debugeinstellungen</span><span class="sxs-lookup"><span data-stu-id="f051f-125">Trace and Debug Settings Schema</span></span>](index.md)
