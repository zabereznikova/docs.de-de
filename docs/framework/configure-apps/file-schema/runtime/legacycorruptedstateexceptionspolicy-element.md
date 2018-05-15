---
title: '&lt;LegacyCorruptedStateExceptionsPolicy&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6228aaf4c7da70337d9d1a99adcb78f71a0039b2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltlegacycorruptedstateexceptionspolicygt-element"></a><span data-ttu-id="72ecc-102">&lt;LegacyCorruptedStateExceptionsPolicy&gt; Element</span><span class="sxs-lookup"><span data-stu-id="72ecc-102">&lt;legacyCorruptedStateExceptionsPolicy&gt; Element</span></span>
<span data-ttu-id="72ecc-103">Gibt an, ob die common Language Runtime verwalteten Codes zugriffsverletzungen und Beschädigung Ausnahmen abfangen kann.</span><span class="sxs-lookup"><span data-stu-id="72ecc-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
 <span data-ttu-id="72ecc-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="72ecc-104">\<configuration></span></span>  
<span data-ttu-id="72ecc-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="72ecc-105">\<runtime></span></span>  
<span data-ttu-id="72ecc-106">\<LegacyCorruptedStateExceptionsPolicy ></span><span class="sxs-lookup"><span data-stu-id="72ecc-106">\<legacyCorruptedStateExceptionsPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72ecc-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="72ecc-107">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72ecc-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="72ecc-108">Attributes and Elements</span></span>  
 <span data-ttu-id="72ecc-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="72ecc-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72ecc-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="72ecc-110">Attributes</span></span>  
  
|<span data-ttu-id="72ecc-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="72ecc-111">Attribute</span></span>|<span data-ttu-id="72ecc-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72ecc-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="72ecc-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="72ecc-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="72ecc-114">Gibt an, dass die Anwendung abgefangen werden Fehler wie z. B. zugriffsverletzungen beschädigen.</span><span class="sxs-lookup"><span data-stu-id="72ecc-114">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="72ecc-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="72ecc-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="72ecc-116">Wert</span><span class="sxs-lookup"><span data-stu-id="72ecc-116">Value</span></span>|<span data-ttu-id="72ecc-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72ecc-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="72ecc-118">Die Anwendung wird nicht abfangen Fehler wie z. B. zugriffsverletzungen beschädigen.</span><span class="sxs-lookup"><span data-stu-id="72ecc-118">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="72ecc-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="72ecc-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="72ecc-120">Die Anwendung fängt Fehler wie z. B. zugriffsverletzungen beschädigen.</span><span class="sxs-lookup"><span data-stu-id="72ecc-120">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="72ecc-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="72ecc-121">Child Elements</span></span>  
 <span data-ttu-id="72ecc-122">Keine</span><span class="sxs-lookup"><span data-stu-id="72ecc-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="72ecc-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="72ecc-123">Parent Elements</span></span>  
  
|<span data-ttu-id="72ecc-124">Element</span><span class="sxs-lookup"><span data-stu-id="72ecc-124">Element</span></span>|<span data-ttu-id="72ecc-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72ecc-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="72ecc-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="72ecc-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="72ecc-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="72ecc-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72ecc-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="72ecc-128">Remarks</span></span>  
 <span data-ttu-id="72ecc-129">In .NET Framework, Version 3.5 und früher zulässig die common Language Runtime verwalteten Code zum Abfangen von Ausnahmen, die nach beschädigten Prozess Status ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="72ecc-129">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="72ecc-130">Eine zugriffsverletzung ist ein Beispiel für diese Art von Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="72ecc-130">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="72ecc-131">Beginnend mit der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], verwalteten Code nicht mehr fängt diese Arten von Ausnahmen in `catch` blockiert.</span><span class="sxs-lookup"><span data-stu-id="72ecc-131">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="72ecc-132">Allerdings können außer Kraft setzen diese Änderung und die Handhabung von beschädigten Zustandsausnahmen auf zwei Arten verwalten:</span><span class="sxs-lookup"><span data-stu-id="72ecc-132">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
-   <span data-ttu-id="72ecc-133">Legen Sie die `<legacyCorruptedStateExceptionsPolicy>` des Elements `enabled` -Attribut `true`.</span><span class="sxs-lookup"><span data-stu-id="72ecc-133">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="72ecc-134">Diese Konfigurationseinstellung wird Processwide angewendet und wirkt sich auf alle Methoden.</span><span class="sxs-lookup"><span data-stu-id="72ecc-134">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="72ecc-135">- oder - </span><span class="sxs-lookup"><span data-stu-id="72ecc-135">-or-</span></span>  
  
-   <span data-ttu-id="72ecc-136">Anwenden der <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> -Attribut auf die Methode, die Ausnahmen enthält `catch` Block.</span><span class="sxs-lookup"><span data-stu-id="72ecc-136">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="72ecc-137">Dieses Konfigurationselement steht nur in der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] und höher.</span><span class="sxs-lookup"><span data-stu-id="72ecc-137">This configuration element is available only in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72ecc-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="72ecc-138">Example</span></span>  
 <span data-ttu-id="72ecc-139">Das folgende Beispiel zeigt, wie angegeben, dass die Anwendung zurückgesetzt werden soll, um das Verhalten vor dem [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], und alle fehlt Fehler abgefangen.</span><span class="sxs-lookup"><span data-stu-id="72ecc-139">The following example shows how to specify that the application should revert to the behavior before the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="72ecc-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72ecc-140">See Also</span></span>  
 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>  
 [<span data-ttu-id="72ecc-141">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="72ecc-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="72ecc-142">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="72ecc-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
