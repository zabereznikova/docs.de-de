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
ms.openlocfilehash: 2f3823265e358976f970cdfa36772d2251894280
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701358"
---
# <a name="assert-element"></a><span data-ttu-id="61968-102">\<Assert->-Element</span><span class="sxs-lookup"><span data-stu-id="61968-102">\<assert> Element</span></span>
<span data-ttu-id="61968-103">Gibt an, ob ein Meldungsfeld angezeigt wird, wenn Sie die <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>-Methode aufrufen. Außerdem wird der Name der Datei angegeben, in die die Meldung geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="61968-103">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>  
  
 <span data-ttu-id="61968-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="61968-104">\<configuration></span></span>  
<span data-ttu-id="61968-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="61968-105">\<system.diagnostics></span></span>  
<span data-ttu-id="61968-106">\<assert></span><span class="sxs-lookup"><span data-stu-id="61968-106">\<assert></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61968-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="61968-107">Syntax</span></span>  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61968-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="61968-108">Attributes and Elements</span></span>  
 <span data-ttu-id="61968-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="61968-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61968-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="61968-110">Attributes</span></span>  
  
|<span data-ttu-id="61968-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="61968-111">Attribute</span></span>|<span data-ttu-id="61968-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61968-112">Description</span></span>|  
|---------------|-----------------|  
|`assertuienabled`|<span data-ttu-id="61968-113">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="61968-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="61968-114">Gibt an, ob die anzuzeigende ein Meldungsfeld, wenn die **Debug.Assert** Methode ergibt **"false"**.</span><span class="sxs-lookup"><span data-stu-id="61968-114">Specifies whether to display a message box when the **Debug.Assert** method evaluates to **false**.</span></span>|  
|`logfilename`|<span data-ttu-id="61968-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="61968-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="61968-116">Gibt den Namen der Datei zum Schreiben der Nachricht auf, wenn **Debug.Assert** ergibt **"false"**.</span><span class="sxs-lookup"><span data-stu-id="61968-116">Specifies the name of the file to write the message to if **Debug.Assert** evaluates to **false**.</span></span>|  
  
## <a name="assertuienabled-attribute"></a><span data-ttu-id="61968-117">assertuienabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="61968-117">assertuienabled Attribute</span></span>  
  
|<span data-ttu-id="61968-118">Wert</span><span class="sxs-lookup"><span data-stu-id="61968-118">Value</span></span>|<span data-ttu-id="61968-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61968-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="61968-120">Zeigt das Meldungsfeld an.</span><span class="sxs-lookup"><span data-stu-id="61968-120">Displays the message box.</span></span> <span data-ttu-id="61968-121">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="61968-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="61968-122">Das Meldungsfeld wird nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="61968-122">Does not display the message box.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="61968-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="61968-123">Child Elements</span></span>  
 <span data-ttu-id="61968-124">Keine</span><span class="sxs-lookup"><span data-stu-id="61968-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="61968-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="61968-125">Parent Elements</span></span>  
  
|<span data-ttu-id="61968-126">Element</span><span class="sxs-lookup"><span data-stu-id="61968-126">Element</span></span>|<span data-ttu-id="61968-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61968-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="61968-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="61968-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="61968-129">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="61968-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61968-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="61968-130">Remarks</span></span>  
 <span data-ttu-id="61968-131">Beide Attribute in der  **\<assert >** -Element sind optional.</span><span class="sxs-lookup"><span data-stu-id="61968-131">Both attributes in the **\<assert>** element are optional.</span></span> <span data-ttu-id="61968-132">Können Sie Meldungsfelder deaktivieren, ohne dass eine Datei zum Schreiben der Nachrichten an, oder Sie können eine Datei zum Schreiben, dass Nachrichten bei verlassen Felder aktiviert Nachricht angeben.</span><span class="sxs-lookup"><span data-stu-id="61968-132">You can disable message boxes without specifying a file to write the messages to, or you can specify a file to write messages to while leaving message boxes enabled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61968-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="61968-133">Example</span></span>  
 <span data-ttu-id="61968-134">Das folgende Beispiel zeigt die zum Anzeigen von Meldungsfeldern zu deaktivieren, beim Aufrufen **Debug.Assert** und schreiben die Nachrichten an `c:\log.txt`.</span><span class="sxs-lookup"><span data-stu-id="61968-134">The following example shows how to disable displaying message boxes when you call **Debug.Assert** and write the messages to `c:\log.txt`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="61968-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61968-135">See also</span></span>

- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="61968-136">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="61968-136">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
