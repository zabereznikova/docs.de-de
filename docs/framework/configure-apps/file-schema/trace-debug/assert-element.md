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
ms.openlocfilehash: 5ba781598542d271f41476b1a1e9d61faeb6ff74
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927188"
---
# <a name="assert-element"></a><span data-ttu-id="91bdf-102">\<Assert >-Element</span><span class="sxs-lookup"><span data-stu-id="91bdf-102">\<assert> Element</span></span>
<span data-ttu-id="91bdf-103">Gibt an, ob ein Meldungsfeld angezeigt wird, wenn Sie die <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>-Methode aufrufen. Außerdem wird der Name der Datei angegeben, in die die Meldung geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="91bdf-103">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>  
  
 <span data-ttu-id="91bdf-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="91bdf-104">\<configuration></span></span>  
<span data-ttu-id="91bdf-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="91bdf-105">\<system.diagnostics></span></span>  
<span data-ttu-id="91bdf-106">\<assert></span><span class="sxs-lookup"><span data-stu-id="91bdf-106">\<assert></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91bdf-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="91bdf-107">Syntax</span></span>  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91bdf-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="91bdf-108">Attributes and Elements</span></span>  
 <span data-ttu-id="91bdf-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="91bdf-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91bdf-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="91bdf-110">Attributes</span></span>  
  
|<span data-ttu-id="91bdf-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="91bdf-111">Attribute</span></span>|<span data-ttu-id="91bdf-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="91bdf-112">Description</span></span>|  
|---------------|-----------------|  
|`assertuienabled`|<span data-ttu-id="91bdf-113">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="91bdf-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="91bdf-114">Gibt an, ob ein Meldungs Feld angezeigt werden soll, wenn die **Debug. Assert** -Methode als **false**ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="91bdf-114">Specifies whether to display a message box when the **Debug.Assert** method evaluates to **false**.</span></span>|  
|`logfilename`|<span data-ttu-id="91bdf-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="91bdf-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="91bdf-116">Gibt den Namen der Datei an, in die die Nachricht geschrieben werden soll, wenn **Debug. Assert** als **false**ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="91bdf-116">Specifies the name of the file to write the message to if **Debug.Assert** evaluates to **false**.</span></span>|  
  
## <a name="assertuienabled-attribute"></a><span data-ttu-id="91bdf-117">assertuiaktiviertes Attribut</span><span class="sxs-lookup"><span data-stu-id="91bdf-117">assertuienabled Attribute</span></span>  
  
|<span data-ttu-id="91bdf-118">Wert</span><span class="sxs-lookup"><span data-stu-id="91bdf-118">Value</span></span>|<span data-ttu-id="91bdf-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="91bdf-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="91bdf-120">Zeigt das Meldungs Feld an.</span><span class="sxs-lookup"><span data-stu-id="91bdf-120">Displays the message box.</span></span> <span data-ttu-id="91bdf-121">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="91bdf-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="91bdf-122">Das Meldungs Feld wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="91bdf-122">Does not display the message box.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91bdf-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="91bdf-123">Child Elements</span></span>  
 <span data-ttu-id="91bdf-124">Keine</span><span class="sxs-lookup"><span data-stu-id="91bdf-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91bdf-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="91bdf-125">Parent Elements</span></span>  
  
|<span data-ttu-id="91bdf-126">Element</span><span class="sxs-lookup"><span data-stu-id="91bdf-126">Element</span></span>|<span data-ttu-id="91bdf-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="91bdf-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="91bdf-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="91bdf-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="91bdf-129">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="91bdf-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91bdf-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="91bdf-130">Remarks</span></span>  
 <span data-ttu-id="91bdf-131">Beide Attribute im  **\<Assert->** Element sind optional.</span><span class="sxs-lookup"><span data-stu-id="91bdf-131">Both attributes in the **\<assert>** element are optional.</span></span> <span data-ttu-id="91bdf-132">Sie können Meldungs Felder deaktivieren, ohne eine Datei anzugeben, in die die Nachrichten geschrieben werden sollen, oder Sie können eine Datei angeben, in die Nachrichten geschrieben werden, während die Nachrichten Felder aktiviert werden</span><span class="sxs-lookup"><span data-stu-id="91bdf-132">You can disable message boxes without specifying a file to write the messages to, or you can specify a file to write messages to while leaving message boxes enabled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91bdf-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91bdf-133">Example</span></span>  
 <span data-ttu-id="91bdf-134">Im folgenden Beispiel wird gezeigt, wie Sie das Anzeigen von Meldungs Feldern deaktivieren, wenn Sie **Debug. Assert** aufzurufen und die Nachrichten in `c:\log.txt`schreiben.</span><span class="sxs-lookup"><span data-stu-id="91bdf-134">The following example shows how to disable displaying message boxes when you call **Debug.Assert** and write the messages to `c:\log.txt`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="91bdf-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91bdf-135">See also</span></span>

- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="91bdf-136">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="91bdf-136">Trace and Debug Settings Schema</span></span>](index.md)
