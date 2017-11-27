---
title: '&lt;ShadowCopyVerifyByTimestamp&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 261962819e9b2b37682a13bffb53d2912a660566
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltshadowcopyverifybytimestampgt-element"></a><span data-ttu-id="e437d-102">&lt;ShadowCopyVerifyByTimestamp&gt; Element</span><span class="sxs-lookup"><span data-stu-id="e437d-102">&lt;shadowCopyVerifyByTimestamp&gt; Element</span></span>
<span data-ttu-id="e437d-103">Gibt an, ob die Schattenkopiefunktion das in [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] eingeführte Standardstartverhalten verwendet oder auf das Startverhalten früherer Versionen von .NET Framework zurückgreift.</span><span class="sxs-lookup"><span data-stu-id="e437d-103">Specifies whether shadow copying uses the default startup behavior introduced in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], or reverts to the startup behavior of earlier versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="e437d-104">\<Konfiguration >-Element</span><span class="sxs-lookup"><span data-stu-id="e437d-104">\<configuration> Element</span></span>  
<span data-ttu-id="e437d-105">\<Common Language Runtime >-Element</span><span class="sxs-lookup"><span data-stu-id="e437d-105">\<runtime> Element</span></span>  
<span data-ttu-id="e437d-106">\<ShadowCopyVerifyByTimestamp >-Element</span><span class="sxs-lookup"><span data-stu-id="e437d-106">\<shadowCopyVerifyByTimestamp> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e437d-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="e437d-107">Syntax</span></span>  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e437d-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e437d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e437d-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e437d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e437d-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="e437d-110">Attributes</span></span>  
  
|<span data-ttu-id="e437d-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="e437d-111">Attribute</span></span>|<span data-ttu-id="e437d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e437d-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e437d-113">enabled</span><span class="sxs-lookup"><span data-stu-id="e437d-113">enabled</span></span>|<span data-ttu-id="e437d-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="e437d-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="e437d-115">Gibt an, ob Anwendungsdomänen, die Schattenkopiefunktion verwenden Assembly Zeitstempel, beim Starten vergleichen zu bestimmen, ob eine Assembly aktualisiert wurde, bevor Sie die Assembly für die Schattenkopiefunktion.</span><span class="sxs-lookup"><span data-stu-id="e437d-115">Specifies whether application domains that use shadow copying compare assembly time stamps when starting up, to determine whether an assembly has been updated before shadow copying the assembly.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="e437d-116">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="e437d-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="e437d-117">Wert</span><span class="sxs-lookup"><span data-stu-id="e437d-117">Value</span></span>|<span data-ttu-id="e437d-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e437d-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e437d-119">true</span><span class="sxs-lookup"><span data-stu-id="e437d-119">true</span></span>|<span data-ttu-id="e437d-120">Beim Start kopiert wird nur für Assemblys, die aktualisiert wurden, seit sie zuletzt in das Schattenkopieverzeichnis kopiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e437d-120">At startup, copies only assemblies that have been updated since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="e437d-121">Dies ist die Standardeinstellung für die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e437d-121">This is the default for the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span>|  
|<span data-ttu-id="e437d-122">false</span><span class="sxs-lookup"><span data-stu-id="e437d-122">false</span></span>|<span data-ttu-id="e437d-123">Wird auf das Startverhalten vorheriger Versionen von .NET Framework, dem wurde so kopieren Sie alle Dateien beim Start.</span><span class="sxs-lookup"><span data-stu-id="e437d-123">Reverts to the startup behavior of previous versions of the .NET Framework, which was to copy all files at startup.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e437d-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e437d-124">Child Elements</span></span>  
 <span data-ttu-id="e437d-125">Keine</span><span class="sxs-lookup"><span data-stu-id="e437d-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e437d-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e437d-126">Parent Elements</span></span>  
  
|<span data-ttu-id="e437d-127">Element</span><span class="sxs-lookup"><span data-stu-id="e437d-127">Element</span></span>|<span data-ttu-id="e437d-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e437d-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e437d-129">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e437d-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e437d-130">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="e437d-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e437d-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e437d-131">Remarks</span></span>  
 <span data-ttu-id="e437d-132">Beginnend mit der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], Assemblys sind Schattenkopien nur, wenn ihre Zeitstempel angeben, dass sie geändert wurden, seit sie zuletzt in das Schattenkopieverzeichnis kopiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e437d-132">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], assemblies are shadow copied only if their time stamps indicate that they have changed since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="e437d-133">Dies verbessert die Startzeiten für viele Anwendungen, die von Schattenkopien zu verwenden, wie in beschrieben [von Schattenkopien von Assemblys](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="e437d-133">This improves startup times for many applications that use shadow copying, as described in [Shadow Copying Assemblies](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md).</span></span> <span data-ttu-id="e437d-134">Anwendungen, die einen hohen Prozentsatz und die Häufigkeit der Assemblyaktualisierungen verfügen möglicherweise nicht von dieser Änderung im Verhalten profitieren.</span><span class="sxs-lookup"><span data-stu-id="e437d-134">Applications that have a high percentage and frequency of assembly updates might not benefit from this change in behavior.</span></span> <span data-ttu-id="e437d-135">In diesem Fall können Sie dieses Element verwenden, um das Verhalten von früheren Versionen von .NET Framework wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="e437d-135">In that case, you can use this element to restore the behavior of previous versions of the .NET Framework.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e437d-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e437d-136">Example</span></span>  
 <span data-ttu-id="e437d-137">Im folgende Beispiel wird gezeigt, wie das standardmäßige Startverhalten der Schattenkopiefunktion Deaktivieren der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], und kehren Sie zu das Startverhalten vorheriger Versionen von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e437d-137">The following example shows how to disable the default startup behavior of shadow copying in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], and revert to the startup behavior of previous versions of the .NET Framework.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e437d-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e437d-138">See Also</span></span>  
 [<span data-ttu-id="e437d-139">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="e437d-139">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="e437d-140">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="e437d-140">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="e437d-141">Erstellen von Schattenkopien von Assemblys</span><span class="sxs-lookup"><span data-stu-id="e437d-141">Shadow Copying Assemblies</span></span>](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)
