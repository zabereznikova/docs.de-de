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
ms.openlocfilehash: c161f842192396101dcc6850f3b3da328958eac3
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697085"
---
# <a name="switches-element"></a><span data-ttu-id="9e225-102">\<switches > Element</span><span class="sxs-lookup"><span data-stu-id="9e225-102">\<switches> Element</span></span>
<span data-ttu-id="9e225-103">Enthält Ablaufverfolgungsschalter und die Ebene, für die diese festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="9e225-103">Contains trace switches and the level where the trace switches are set.</span></span>  
  
[<span data-ttu-id="9e225-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="9e225-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="9e225-105">&nbsp; @ no__t-1[ **\<system. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="9e225-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="9e225-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<switches >**</span><span class="sxs-lookup"><span data-stu-id="9e225-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<switches>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e225-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="9e225-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e225-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9e225-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9e225-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9e225-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e225-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="9e225-110">Attributes</span></span>  
 <span data-ttu-id="9e225-111">Keine</span><span class="sxs-lookup"><span data-stu-id="9e225-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9e225-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9e225-112">Child Elements</span></span>  
  
|<span data-ttu-id="9e225-113">Element</span><span class="sxs-lookup"><span data-stu-id="9e225-113">Element</span></span>|<span data-ttu-id="9e225-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e225-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e225-115">\<add></span><span class="sxs-lookup"><span data-stu-id="9e225-115">\<add></span></span>](add-element-for-switches.md)|<span data-ttu-id="9e225-116">Gibt die Ebene an, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9e225-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9e225-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9e225-117">Parent Elements</span></span>  
  
|<span data-ttu-id="9e225-118">Element</span><span class="sxs-lookup"><span data-stu-id="9e225-118">Element</span></span>|<span data-ttu-id="9e225-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e225-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9e225-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="9e225-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="9e225-121">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9e225-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e225-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9e225-122">Remarks</span></span>  
 <span data-ttu-id="9e225-123">Sie können die Ebene eines Ablauf Verfolgungs Schalters ändern, indem Sie ihn in eine Konfigurationsdatei einfügen.</span><span class="sxs-lookup"><span data-stu-id="9e225-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="9e225-124">Wenn der Schalter ein <xref:System.Diagnostics.BooleanSwitch> ist, können Sie ihn aktivieren und deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9e225-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="9e225-125">Wenn der Schalter ein <xref:System.Diagnostics.TraceSwitch> ist, können Sie ihm verschiedene Ebenen zuweisen, um die Typen der Ablauf Verfolgungs-oder Debugmeldungen anzugeben, die die Anwendung ausgibt.</span><span class="sxs-lookup"><span data-stu-id="9e225-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e225-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9e225-126">Example</span></span>  
 <span data-ttu-id="9e225-127">Im folgenden Beispiel wird gezeigt, wie Sie das **\<switch >-** Element verwenden, um den `General`-Ablauf Verfolgungs Schalter auf die <xref:System.Diagnostics.TraceLevel>-Ebene festzulegen und den `Data` booleschen Ablauf Verfolgungs Schalter zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9e225-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9e225-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e225-128">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="9e225-129">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="9e225-129">Trace and Debug Settings Schema</span></span>](index.md)
 