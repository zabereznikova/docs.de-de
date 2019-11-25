---
title: <assert>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assert
helpviewer_keywords:
- <assert> element
- assert element
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
ms.openlocfilehash: f3c1a1670139a8262dea449bfff99c7c1c19f088
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088950"
---
# <a name="assert-element"></a><span data-ttu-id="2e33b-102">\<Assert >-Element</span><span class="sxs-lookup"><span data-stu-id="2e33b-102">\<assert> Element</span></span>
<span data-ttu-id="2e33b-103">Gibt an, ob ein Meldungsfeld angezeigt wird, wenn Sie die <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>-Methode aufrufen. Außerdem wird der Name der Datei angegeben, in die die Meldung geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="2e33b-103">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>  

<span data-ttu-id="2e33b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2e33b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2e33b-105">&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="2e33b-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="2e33b-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Assert->**</span><span class="sxs-lookup"><span data-stu-id="2e33b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<assert>**</span></span>

## <a name="syntax"></a><span data-ttu-id="2e33b-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e33b-107">Syntax</span></span>  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e33b-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2e33b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2e33b-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2e33b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e33b-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="2e33b-110">Attributes</span></span>  
  
|<span data-ttu-id="2e33b-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="2e33b-111">Attribute</span></span>|<span data-ttu-id="2e33b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e33b-112">Description</span></span>|  
|---------------|-----------------|  
|`assertuienabled`|<span data-ttu-id="2e33b-113">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="2e33b-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2e33b-114">Gibt an, ob ein Meldungs Feld angezeigt werden soll, wenn die **Debug. Assert** -Methode als **false**ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="2e33b-114">Specifies whether to display a message box when the **Debug.Assert** method evaluates to **false**.</span></span>|  
|`logfilename`|<span data-ttu-id="2e33b-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="2e33b-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2e33b-116">Gibt den Namen der Datei an, in die die Nachricht geschrieben werden soll, wenn **Debug. Assert** als **false**ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="2e33b-116">Specifies the name of the file to write the message to if **Debug.Assert** evaluates to **false**.</span></span>|  
  
## <a name="assertuienabled-attribute"></a><span data-ttu-id="2e33b-117">assertuiaktiviertes Attribut</span><span class="sxs-lookup"><span data-stu-id="2e33b-117">assertuienabled Attribute</span></span>  
  
|<span data-ttu-id="2e33b-118">Wert</span><span class="sxs-lookup"><span data-stu-id="2e33b-118">Value</span></span>|<span data-ttu-id="2e33b-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e33b-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="2e33b-120">Zeigt das Meldungs Feld an.</span><span class="sxs-lookup"><span data-stu-id="2e33b-120">Displays the message box.</span></span> <span data-ttu-id="2e33b-121">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="2e33b-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="2e33b-122">Das Meldungs Feld wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2e33b-122">Does not display the message box.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2e33b-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2e33b-123">Child Elements</span></span>  
 <span data-ttu-id="2e33b-124">Keine</span><span class="sxs-lookup"><span data-stu-id="2e33b-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2e33b-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2e33b-125">Parent Elements</span></span>  
  
|<span data-ttu-id="2e33b-126">Element</span><span class="sxs-lookup"><span data-stu-id="2e33b-126">Element</span></span>|<span data-ttu-id="2e33b-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e33b-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2e33b-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="2e33b-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="2e33b-129">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2e33b-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e33b-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2e33b-130">Remarks</span></span>  
 <span data-ttu-id="2e33b-131">Beide Attribute im **\<Assert->** Element sind optional.</span><span class="sxs-lookup"><span data-stu-id="2e33b-131">Both attributes in the **\<assert>** element are optional.</span></span> <span data-ttu-id="2e33b-132">Sie können Meldungs Felder deaktivieren, ohne eine Datei anzugeben, in die die Nachrichten geschrieben werden sollen, oder Sie können eine Datei angeben, in die Nachrichten geschrieben werden, während die Nachrichten Felder aktiviert werden</span><span class="sxs-lookup"><span data-stu-id="2e33b-132">You can disable message boxes without specifying a file to write the messages to, or you can specify a file to write messages to while leaving message boxes enabled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e33b-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2e33b-133">Example</span></span>  
 <span data-ttu-id="2e33b-134">Das folgende Beispiel zeigt, wie Sie das Anzeigen von Meldungs Feldern deaktivieren, wenn Sie **Debug. Assert** aufzurufen und die Nachrichten in `c:\log.txt`schreiben.</span><span class="sxs-lookup"><span data-stu-id="2e33b-134">The following example shows how to disable displaying message boxes when you call **Debug.Assert** and write the messages to `c:\log.txt`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e33b-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e33b-135">See also</span></span>

- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="2e33b-136">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="2e33b-136">Trace and Debug Settings Schema</span></span>](index.md)
