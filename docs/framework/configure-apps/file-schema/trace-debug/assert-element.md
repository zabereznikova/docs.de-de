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
ms.openlocfilehash: 30ec24aefcf8c4d1e110238a2c60a958eded5545
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699386"
---
# <a name="assert-element"></a><span data-ttu-id="43067-102">\<assert >-Element</span><span class="sxs-lookup"><span data-stu-id="43067-102">\<assert> Element</span></span>
<span data-ttu-id="43067-103">Gibt an, ob ein Meldungsfeld angezeigt wird, wenn Sie die <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>-Methode aufrufen. Außerdem wird der Name der Datei angegeben, in die die Meldung geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="43067-103">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>  
  
[<span data-ttu-id="43067-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="43067-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="43067-105">&nbsp; @ no__t-1[ **\<system. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="43067-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="43067-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<assert >**</span><span class="sxs-lookup"><span data-stu-id="43067-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<assert>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43067-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="43067-107">Syntax</span></span>  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43067-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="43067-108">Attributes and Elements</span></span>  
 <span data-ttu-id="43067-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="43067-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43067-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="43067-110">Attributes</span></span>  
  
|<span data-ttu-id="43067-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="43067-111">Attribute</span></span>|<span data-ttu-id="43067-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="43067-112">Description</span></span>|  
|---------------|-----------------|  
|`assertuienabled`|<span data-ttu-id="43067-113">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="43067-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="43067-114">Gibt an, ob ein Meldungs Feld angezeigt werden soll, wenn die **Debug. Assert** -Methode als **false**ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="43067-114">Specifies whether to display a message box when the **Debug.Assert** method evaluates to **false**.</span></span>|  
|`logfilename`|<span data-ttu-id="43067-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="43067-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="43067-116">Gibt den Namen der Datei an, in die die Nachricht geschrieben werden soll, wenn **Debug. Assert** als **false**ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="43067-116">Specifies the name of the file to write the message to if **Debug.Assert** evaluates to **false**.</span></span>|  
  
## <a name="assertuienabled-attribute"></a><span data-ttu-id="43067-117">assertuiaktiviertes Attribut</span><span class="sxs-lookup"><span data-stu-id="43067-117">assertuienabled Attribute</span></span>  
  
|<span data-ttu-id="43067-118">Wert</span><span class="sxs-lookup"><span data-stu-id="43067-118">Value</span></span>|<span data-ttu-id="43067-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="43067-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="43067-120">Zeigt das Meldungs Feld an.</span><span class="sxs-lookup"><span data-stu-id="43067-120">Displays the message box.</span></span> <span data-ttu-id="43067-121">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="43067-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="43067-122">Das Meldungs Feld wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="43067-122">Does not display the message box.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="43067-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="43067-123">Child Elements</span></span>  
 <span data-ttu-id="43067-124">Keine</span><span class="sxs-lookup"><span data-stu-id="43067-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="43067-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="43067-125">Parent Elements</span></span>  
  
|<span data-ttu-id="43067-126">Element</span><span class="sxs-lookup"><span data-stu-id="43067-126">Element</span></span>|<span data-ttu-id="43067-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="43067-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="43067-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="43067-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="43067-129">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="43067-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43067-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="43067-130">Remarks</span></span>  
 <span data-ttu-id="43067-131">Beide Attribute im **\<assert->** Element sind optional.</span><span class="sxs-lookup"><span data-stu-id="43067-131">Both attributes in the **\<assert>** element are optional.</span></span> <span data-ttu-id="43067-132">Sie können Meldungs Felder deaktivieren, ohne eine Datei anzugeben, in die die Nachrichten geschrieben werden sollen, oder Sie können eine Datei angeben, in die Nachrichten geschrieben werden, während die Nachrichten Felder aktiviert werden</span><span class="sxs-lookup"><span data-stu-id="43067-132">You can disable message boxes without specifying a file to write the messages to, or you can specify a file to write messages to while leaving message boxes enabled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43067-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="43067-133">Example</span></span>  
 <span data-ttu-id="43067-134">Im folgenden Beispiel wird gezeigt, wie die Anzeige von Meldungs Feldern beim Abrufen von **Debug. Assert** deaktiviert und die Nachrichten in `c:\log.txt` geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="43067-134">The following example shows how to disable displaying message boxes when you call **Debug.Assert** and write the messages to `c:\log.txt`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="43067-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43067-135">See also</span></span>

- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="43067-136">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="43067-136">Trace and Debug Settings Schema</span></span>](index.md)
