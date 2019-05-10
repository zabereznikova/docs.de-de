---
title: <legacyCorruptedStateExceptionsPolicy>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 78b670d8b23b5ecf274432d3758d07dae34dcfcf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64607175"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a><span data-ttu-id="8b06e-102">\<legacyCorruptedStateExceptionsPolicy> Element</span><span class="sxs-lookup"><span data-stu-id="8b06e-102">\<legacyCorruptedStateExceptionsPolicy> Element</span></span>
<span data-ttu-id="8b06e-103">Gibt an, ob die common Language Runtime verwalteten Code zum Abfangen von zugriffsverletzungen und anderen Beschädigungen hervorgerufenen Ausnahmen zulässt.</span><span class="sxs-lookup"><span data-stu-id="8b06e-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
 <span data-ttu-id="8b06e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8b06e-104">\<configuration></span></span>  
<span data-ttu-id="8b06e-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="8b06e-105">\<runtime></span></span>  
<span data-ttu-id="8b06e-106">\<legacyCorruptedStateExceptionsPolicy></span><span class="sxs-lookup"><span data-stu-id="8b06e-106">\<legacyCorruptedStateExceptionsPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b06e-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b06e-107">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8b06e-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8b06e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8b06e-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8b06e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8b06e-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="8b06e-110">Attributes</span></span>  
  
|<span data-ttu-id="8b06e-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="8b06e-111">Attribute</span></span>|<span data-ttu-id="8b06e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8b06e-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="8b06e-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="8b06e-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="8b06e-114">Gibt an, dass die Anwendung abgefangen werden Fehler wie z. B. zugriffsverletzungen beschädigen.</span><span class="sxs-lookup"><span data-stu-id="8b06e-114">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="8b06e-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="8b06e-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="8b06e-116">Wert</span><span class="sxs-lookup"><span data-stu-id="8b06e-116">Value</span></span>|<span data-ttu-id="8b06e-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8b06e-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="8b06e-118">Die Anwendung fängt keine Fehler z.B. zugriffsverletzungen beschädigen.</span><span class="sxs-lookup"><span data-stu-id="8b06e-118">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="8b06e-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="8b06e-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="8b06e-120">Die Anwendung fängt Fehler z.B. zugriffsverletzungen beschädigen.</span><span class="sxs-lookup"><span data-stu-id="8b06e-120">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8b06e-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8b06e-121">Child Elements</span></span>  
 <span data-ttu-id="8b06e-122">Keine</span><span class="sxs-lookup"><span data-stu-id="8b06e-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8b06e-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8b06e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8b06e-124">Element</span><span class="sxs-lookup"><span data-stu-id="8b06e-124">Element</span></span>|<span data-ttu-id="8b06e-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8b06e-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8b06e-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="8b06e-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="8b06e-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="8b06e-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b06e-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8b06e-128">Remarks</span></span>  
 <span data-ttu-id="8b06e-129">In .NET Framework, Version 3.5 und früher darf die common Language Runtime verwalteten Code zum Abfangen von Ausnahmen, die vom Status der beschädigten Prozess ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="8b06e-129">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="8b06e-130">Eine zugriffsverletzung ist ein Beispiel für diese Art von Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="8b06e-130">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="8b06e-131">Beginnend mit der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], verwalteten Code nicht mehr fängt diese Arten von Ausnahmen in `catch` Blöcke.</span><span class="sxs-lookup"><span data-stu-id="8b06e-131">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="8b06e-132">Allerdings können außer Kraft setzen diese Änderung und verwaltet die Behandlung von Beschädigungen hervorgerufenen Ausnahmen gibt es zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="8b06e-132">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
- <span data-ttu-id="8b06e-133">Legen Sie die `<legacyCorruptedStateExceptionsPolicy>` des Elements `enabled` Attribut `true`.</span><span class="sxs-lookup"><span data-stu-id="8b06e-133">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="8b06e-134">Diese Konfigurationseinstellung wird angewendeten Processwide und wirkt sich auf alle Methoden.</span><span class="sxs-lookup"><span data-stu-id="8b06e-134">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="8b06e-135">- oder - </span><span class="sxs-lookup"><span data-stu-id="8b06e-135">-or-</span></span>  
  
- <span data-ttu-id="8b06e-136">Anwenden der <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> -Attribut auf die Methode, die die Ausnahmen enthält `catch` Block.</span><span class="sxs-lookup"><span data-stu-id="8b06e-136">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="8b06e-137">Dieses Konfigurationselement steht nur in der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] und höher.</span><span class="sxs-lookup"><span data-stu-id="8b06e-137">This configuration element is available only in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b06e-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8b06e-138">Example</span></span>  
 <span data-ttu-id="8b06e-139">Das folgende Beispiel zeigt, wie angegeben, dass die Anwendung das Verhalten vor zurückkehren soll die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], und alle Beschädigung Fehler abgefangen.</span><span class="sxs-lookup"><span data-stu-id="8b06e-139">The following example shows how to specify that the application should revert to the behavior before the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8b06e-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b06e-140">See also</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [<span data-ttu-id="8b06e-141">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="8b06e-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="8b06e-142">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="8b06e-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
