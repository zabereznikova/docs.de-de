---
title: <legacyCorruptedStateExceptionsPolicy>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
ms.openlocfilehash: d1d29a37999a01f3e370897a1052f4f94435a218
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116460"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a><span data-ttu-id="5c67a-102">\<legacybeschädigte tedstateexceptionspolicy > Element</span><span class="sxs-lookup"><span data-stu-id="5c67a-102">\<legacyCorruptedStateExceptionsPolicy> Element</span></span>
<span data-ttu-id="5c67a-103">Gibt an, ob durch den Common Language Runtime verwalteter Code Zugriffs Verletzungen und andere beschädigte Zustands Ausnahmen abfangen kann.</span><span class="sxs-lookup"><span data-stu-id="5c67a-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
<span data-ttu-id="5c67a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5c67a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5c67a-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="5c67a-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="5c67a-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<legacybeschädigte tedstateexceptionspolicy >**</span><span class="sxs-lookup"><span data-stu-id="5c67a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyCorruptedStateExceptionsPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c67a-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c67a-107">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c67a-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5c67a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5c67a-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5c67a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c67a-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="5c67a-110">Attributes</span></span>  
  
|<span data-ttu-id="5c67a-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="5c67a-111">Attribute</span></span>|<span data-ttu-id="5c67a-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5c67a-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="5c67a-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="5c67a-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="5c67a-114">Gibt an, dass die Anwendung beschädigte Zustands Ausnahme Fehler abfängt, wie z. b. Zugriffs Verletzungen.</span><span class="sxs-lookup"><span data-stu-id="5c67a-114">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="5c67a-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="5c67a-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="5c67a-116">Wert</span><span class="sxs-lookup"><span data-stu-id="5c67a-116">Value</span></span>|<span data-ttu-id="5c67a-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5c67a-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="5c67a-118">Die Anwendung fängt keine Beschädigung von Zustands Ausnahme Fehlern, z. b. Zugriffs Verletzungen, ab.</span><span class="sxs-lookup"><span data-stu-id="5c67a-118">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="5c67a-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="5c67a-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="5c67a-120">Die Anwendung fängt beschädigte Zustands Ausnahme Fehler wie z. b. Zugriffs Verletzungen auf.</span><span class="sxs-lookup"><span data-stu-id="5c67a-120">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5c67a-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5c67a-121">Child Elements</span></span>  
 <span data-ttu-id="5c67a-122">Keine</span><span class="sxs-lookup"><span data-stu-id="5c67a-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5c67a-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5c67a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5c67a-124">Element</span><span class="sxs-lookup"><span data-stu-id="5c67a-124">Element</span></span>|<span data-ttu-id="5c67a-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5c67a-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5c67a-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="5c67a-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="5c67a-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="5c67a-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c67a-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5c67a-128">Remarks</span></span>  
 <span data-ttu-id="5c67a-129">In der .NET Framework Version 3,5 und früher ermöglichte der Common Language Runtime verwalteten Code das Abfangen von Ausnahmen, die von beschädigten Prozesszuständen ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="5c67a-129">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="5c67a-130">Eine Zugriffsverletzung ist ein Beispiel für diese Art von Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="5c67a-130">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="5c67a-131">Ab .NET Framework 4 fängt der verwaltete Code diese Typen von Ausnahmen nicht mehr in `catch` Blöcken ab.</span><span class="sxs-lookup"><span data-stu-id="5c67a-131">Starting with the .NET Framework 4, managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="5c67a-132">Sie können diese Änderung jedoch außer Kraft setzen und die Behandlung von beschädigten Zustands Ausnahmen auf zwei Arten beibehalten:</span><span class="sxs-lookup"><span data-stu-id="5c67a-132">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
- <span data-ttu-id="5c67a-133">Legen Sie das `enabled`-Attribut des `<legacyCorruptedStateExceptionsPolicy>` Elements auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="5c67a-133">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="5c67a-134">Diese Konfigurationseinstellung wird Processwide angewendet und wirkt sich auf alle Methoden aus.</span><span class="sxs-lookup"><span data-stu-id="5c67a-134">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="5c67a-135">- oder -</span><span class="sxs-lookup"><span data-stu-id="5c67a-135">-or-</span></span>  
  
- <span data-ttu-id="5c67a-136">Wenden Sie das <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType>-Attribut auf die Methode an, die die Ausnahmen `catch` Block enthält.</span><span class="sxs-lookup"><span data-stu-id="5c67a-136">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="5c67a-137">Dieses Konfigurationselement ist nur in den .NET Framework 4 und höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5c67a-137">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c67a-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c67a-138">Example</span></span>  
 <span data-ttu-id="5c67a-139">Im folgenden Beispiel wird gezeigt, wie angegeben wird, dass die Anwendung auf das Verhalten vor dem .NET Framework 4 zurückgesetzt werden soll, und alle Fehler bei der Beschädigung von Zustands Fehlern abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="5c67a-139">The following example shows how to specify that the application should revert to the behavior before the .NET Framework 4, and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5c67a-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c67a-140">See also</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [<span data-ttu-id="5c67a-141">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="5c67a-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5c67a-142">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="5c67a-142">Configuration File Schema</span></span>](../index.md)
