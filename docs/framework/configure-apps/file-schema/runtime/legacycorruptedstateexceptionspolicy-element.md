---
title: <legacyCorruptedStateExceptionsPolicy>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
ms.openlocfilehash: f36e27a1b85cff2ba8c7e838bace37890a5aa760
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151206"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a><span data-ttu-id="90dcb-102">\<legacyCorruptedStateExceptionsPolicy>-Element</span><span class="sxs-lookup"><span data-stu-id="90dcb-102">\<legacyCorruptedStateExceptionsPolicy> Element</span></span>

<span data-ttu-id="90dcb-103">Gibt an, ob durch den Common Language Runtime verwalteter Code Zugriffs Verletzungen und andere beschädigte Zustands Ausnahmen abfangen kann.</span><span class="sxs-lookup"><span data-stu-id="90dcb-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyCorruptedStateExceptionsPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="90dcb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="90dcb-104">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90dcb-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="90dcb-105">Attributes and Elements</span></span>  

 <span data-ttu-id="90dcb-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="90dcb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90dcb-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="90dcb-107">Attributes</span></span>  
  
|<span data-ttu-id="90dcb-108">attribute</span><span class="sxs-lookup"><span data-stu-id="90dcb-108">Attribute</span></span>|<span data-ttu-id="90dcb-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90dcb-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="90dcb-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="90dcb-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="90dcb-111">Gibt an, dass die Anwendung beschädigte Zustands Ausnahme Fehler abfängt, wie z. b. Zugriffs Verletzungen.</span><span class="sxs-lookup"><span data-stu-id="90dcb-111">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="90dcb-112">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="90dcb-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="90dcb-113">Wert</span><span class="sxs-lookup"><span data-stu-id="90dcb-113">Value</span></span>|<span data-ttu-id="90dcb-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90dcb-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="90dcb-115">Die Anwendung fängt keine Beschädigung von Zustands Ausnahme Fehlern, z. b. Zugriffs Verletzungen, ab.</span><span class="sxs-lookup"><span data-stu-id="90dcb-115">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="90dcb-116">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="90dcb-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="90dcb-117">Die Anwendung fängt beschädigte Zustands Ausnahme Fehler wie z. b. Zugriffs Verletzungen auf.</span><span class="sxs-lookup"><span data-stu-id="90dcb-117">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="90dcb-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="90dcb-118">Child Elements</span></span>  

 <span data-ttu-id="90dcb-119">Keine</span><span class="sxs-lookup"><span data-stu-id="90dcb-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="90dcb-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="90dcb-120">Parent Elements</span></span>  
  
|<span data-ttu-id="90dcb-121">Element</span><span class="sxs-lookup"><span data-stu-id="90dcb-121">Element</span></span>|<span data-ttu-id="90dcb-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90dcb-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="90dcb-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="90dcb-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="90dcb-124">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="90dcb-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90dcb-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="90dcb-125">Remarks</span></span>  

 <span data-ttu-id="90dcb-126">In der .NET Framework Version 3,5 und früher ermöglichte der Common Language Runtime verwalteten Code das Abfangen von Ausnahmen, die von beschädigten Prozesszuständen ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="90dcb-126">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="90dcb-127">Eine Zugriffsverletzung ist ein Beispiel für diese Art von Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="90dcb-127">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="90dcb-128">Ab .NET Framework 4 fängt der verwaltete Code diese Typen von Ausnahmen in-Blöcken nicht mehr ab `catch` .</span><span class="sxs-lookup"><span data-stu-id="90dcb-128">Starting with the .NET Framework 4, managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="90dcb-129">Sie können diese Änderung jedoch außer Kraft setzen und die Behandlung von beschädigten Zustands Ausnahmen auf zwei Arten beibehalten:</span><span class="sxs-lookup"><span data-stu-id="90dcb-129">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
- <span data-ttu-id="90dcb-130">Legen `<legacyCorruptedStateExceptionsPolicy>` Sie das-Attribut des-Elements `enabled` auf fest `true` .</span><span class="sxs-lookup"><span data-stu-id="90dcb-130">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="90dcb-131">Diese Konfigurationseinstellung wird Processwide angewendet und wirkt sich auf alle Methoden aus.</span><span class="sxs-lookup"><span data-stu-id="90dcb-131">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="90dcb-132">- oder -</span><span class="sxs-lookup"><span data-stu-id="90dcb-132">-or-</span></span>  
  
- <span data-ttu-id="90dcb-133">Wenden Sie das- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> Attribut auf die Methode an, die den Ausnahmen `catch` Block enthält.</span><span class="sxs-lookup"><span data-stu-id="90dcb-133">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="90dcb-134">Dieses Konfigurationselement ist nur in den .NET Framework 4 und höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="90dcb-134">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90dcb-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90dcb-135">Example</span></span>  

 <span data-ttu-id="90dcb-136">Im folgenden Beispiel wird gezeigt, wie angegeben wird, dass die Anwendung auf das Verhalten vor dem .NET Framework 4 zurückgesetzt werden soll, und alle Fehler bei der Beschädigung von Zustands Fehlern abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="90dcb-136">The following example shows how to specify that the application should revert to the behavior before the .NET Framework 4, and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="90dcb-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90dcb-137">See also</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [<span data-ttu-id="90dcb-138">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="90dcb-138">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="90dcb-139">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="90dcb-139">Configuration File Schema</span></span>](../index.md)
