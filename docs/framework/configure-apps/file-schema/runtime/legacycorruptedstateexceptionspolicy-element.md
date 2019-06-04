---
title: <legacyCorruptedStateExceptionsPolicy>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6191ee2169a85725f0367763874e60c0ceb1d7a4
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489431"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a><span data-ttu-id="55a36-102">\<legacyCorruptedStateExceptionsPolicy> Element</span><span class="sxs-lookup"><span data-stu-id="55a36-102">\<legacyCorruptedStateExceptionsPolicy> Element</span></span>
<span data-ttu-id="55a36-103">Gibt an, ob die common Language Runtime verwalteten Code zum Abfangen von zugriffsverletzungen und anderen Beschädigungen hervorgerufenen Ausnahmen zulässt.</span><span class="sxs-lookup"><span data-stu-id="55a36-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
 <span data-ttu-id="55a36-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="55a36-104">\<configuration></span></span>  
<span data-ttu-id="55a36-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="55a36-105">\<runtime></span></span>  
<span data-ttu-id="55a36-106">\<legacyCorruptedStateExceptionsPolicy></span><span class="sxs-lookup"><span data-stu-id="55a36-106">\<legacyCorruptedStateExceptionsPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55a36-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="55a36-107">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55a36-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="55a36-108">Attributes and Elements</span></span>  
 <span data-ttu-id="55a36-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="55a36-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55a36-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="55a36-110">Attributes</span></span>  
  
|<span data-ttu-id="55a36-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="55a36-111">Attribute</span></span>|<span data-ttu-id="55a36-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55a36-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="55a36-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="55a36-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="55a36-114">Gibt an, dass die Anwendung abgefangen werden Fehler wie z. B. zugriffsverletzungen beschädigen.</span><span class="sxs-lookup"><span data-stu-id="55a36-114">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="55a36-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="55a36-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="55a36-116">Wert</span><span class="sxs-lookup"><span data-stu-id="55a36-116">Value</span></span>|<span data-ttu-id="55a36-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55a36-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="55a36-118">Die Anwendung fängt keine Fehler z.B. zugriffsverletzungen beschädigen.</span><span class="sxs-lookup"><span data-stu-id="55a36-118">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="55a36-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="55a36-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="55a36-120">Die Anwendung fängt Fehler z.B. zugriffsverletzungen beschädigen.</span><span class="sxs-lookup"><span data-stu-id="55a36-120">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="55a36-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="55a36-121">Child Elements</span></span>  
 <span data-ttu-id="55a36-122">Keine</span><span class="sxs-lookup"><span data-stu-id="55a36-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="55a36-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="55a36-123">Parent Elements</span></span>  
  
|<span data-ttu-id="55a36-124">Element</span><span class="sxs-lookup"><span data-stu-id="55a36-124">Element</span></span>|<span data-ttu-id="55a36-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55a36-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="55a36-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="55a36-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="55a36-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="55a36-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55a36-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="55a36-128">Remarks</span></span>  
 <span data-ttu-id="55a36-129">In .NET Framework, Version 3.5 und früher darf die common Language Runtime verwalteten Code zum Abfangen von Ausnahmen, die vom Status der beschädigten Prozess ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="55a36-129">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="55a36-130">Eine zugriffsverletzung ist ein Beispiel für diese Art von Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="55a36-130">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="55a36-131">Ab .NET Framework 4, fängt verwalteter Code nicht mehr diese Arten von Ausnahmen in `catch` Blöcke.</span><span class="sxs-lookup"><span data-stu-id="55a36-131">Starting with the .NET Framework 4, managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="55a36-132">Allerdings können außer Kraft setzen diese Änderung und verwaltet die Behandlung von Beschädigungen hervorgerufenen Ausnahmen gibt es zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="55a36-132">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
- <span data-ttu-id="55a36-133">Legen Sie die `<legacyCorruptedStateExceptionsPolicy>` des Elements `enabled` Attribut `true`.</span><span class="sxs-lookup"><span data-stu-id="55a36-133">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="55a36-134">Diese Konfigurationseinstellung wird angewendeten Processwide und wirkt sich auf alle Methoden.</span><span class="sxs-lookup"><span data-stu-id="55a36-134">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="55a36-135">- oder -</span><span class="sxs-lookup"><span data-stu-id="55a36-135">-or-</span></span>  
  
- <span data-ttu-id="55a36-136">Anwenden der <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> -Attribut auf die Methode, die die Ausnahmen enthält `catch` Block.</span><span class="sxs-lookup"><span data-stu-id="55a36-136">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="55a36-137">Dieses Element ist nur in .NET Framework 4 und höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="55a36-137">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55a36-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="55a36-138">Example</span></span>  
 <span data-ttu-id="55a36-139">Das folgende Beispiel zeigt, wie Sie angeben, dass die Anwendung sollte auf das Verhalten vor .NET Framework 4 zurückgesetzt und alle Beschädigung Fehler abgefangen wird.</span><span class="sxs-lookup"><span data-stu-id="55a36-139">The following example shows how to specify that the application should revert to the behavior before the .NET Framework 4, and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="55a36-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55a36-140">See also</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [<span data-ttu-id="55a36-141">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="55a36-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="55a36-142">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="55a36-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
