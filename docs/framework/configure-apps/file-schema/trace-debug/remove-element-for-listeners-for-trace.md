---
title: <remove> -Element für <listeners> für <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: 01b797e1fb62d32e9f0d44c54b803dd969615361
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173834"
---
# <a name="remove-element-for-listeners-for-trace"></a><span data-ttu-id="7f988-102">\<remove> -Element für \<listeners> für \<trace></span><span class="sxs-lookup"><span data-stu-id="7f988-102">\<remove> Element for \<listeners> for \<trace></span></span>

<span data-ttu-id="7f988-103">Entfernt einen Listener aus der **listenerauflistung** .</span><span class="sxs-lookup"><span data-stu-id="7f988-103">Removes a listener from the **Listeners** collection.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="7f988-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7f988-104">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f988-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7f988-105">Attributes and Elements</span></span>  

 <span data-ttu-id="7f988-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7f988-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f988-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="7f988-107">Attributes</span></span>  
  
|<span data-ttu-id="7f988-108">attribute</span><span class="sxs-lookup"><span data-stu-id="7f988-108">Attribute</span></span>|<span data-ttu-id="7f988-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7f988-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7f988-110">**name**</span><span class="sxs-lookup"><span data-stu-id="7f988-110">**name**</span></span>|<span data-ttu-id="7f988-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="7f988-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="7f988-112">Der Name des Listener, der aus der **listenerauflistung** entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7f988-112">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f988-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7f988-113">Child Elements</span></span>  

 <span data-ttu-id="7f988-114">Keine</span><span class="sxs-lookup"><span data-stu-id="7f988-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7f988-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7f988-115">Parent Elements</span></span>  
  
|<span data-ttu-id="7f988-116">Element</span><span class="sxs-lookup"><span data-stu-id="7f988-116">Element</span></span>|<span data-ttu-id="7f988-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7f988-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7f988-118">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="7f988-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="7f988-119">Gibt einen Listener an, der Nachrichten sammelt, speichert und weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="7f988-119">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="7f988-120">Listener leiten die Ablauf Verfolgungs Ausgabe an ein entsprechendes Ziel weiter.</span><span class="sxs-lookup"><span data-stu-id="7f988-120">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="7f988-121">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7f988-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="7f988-122">Konfiguriert den ASP.NET-Ablaufverfolgungsdienst.</span><span class="sxs-lookup"><span data-stu-id="7f988-122">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f988-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7f988-123">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7f988-124">Wenn Sie <xref:System.Diagnostics.DefaultTraceListener> aus der Auflistung entfernen `Listeners` , ändert sich das Verhalten der <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> Methoden,, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> und <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="7f988-124">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="7f988-125">Wenn Sie eine- `Assert` oder- `Fail` Methode aufrufen, wird normalerweise die Anzeige eines Meldungs Felds angezeigt, das Meldungs Feld wird jedoch nicht angezeigt, wenn <xref:System.Diagnostics.DefaultTraceListener> sich nicht in der Auflistung befindet `Listeners` .</span><span class="sxs-lookup"><span data-stu-id="7f988-125">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f988-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7f988-126">Example</span></span>  

 <span data-ttu-id="7f988-127">Im folgenden Beispiel wird gezeigt, wie der Standardablaufverfolgungslistener aus der Auflistung der ablaufverfol **Listeners**</span><span class="sxs-lookup"><span data-stu-id="7f988-127">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f988-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7f988-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="7f988-129">Schema für Ablaufverfolgungs- und Debugeinstellungen</span><span class="sxs-lookup"><span data-stu-id="7f988-129">Trace and Debug Settings Schema</span></span>](index.md)
