---
title: <shadowCopyVerifyByTimestamp>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1815da141beb3dd1022fe1a74f872aa70b4ded43
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456346"
---
# <a name="shadowcopyverifybytimestamp-element"></a><span data-ttu-id="02521-102">\<shadowCopyVerifyByTimestamp>-Element</span><span class="sxs-lookup"><span data-stu-id="02521-102">\<shadowCopyVerifyByTimestamp> Element</span></span>
<span data-ttu-id="02521-103">Gibt an, ob die Schattenkopiefunktion das in [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] eingeführte Standardstartverhalten verwendet oder auf das Startverhalten früherer Versionen von .NET Framework zurückgreift.</span><span class="sxs-lookup"><span data-stu-id="02521-103">Specifies whether shadow copying uses the default startup behavior introduced in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], or reverts to the startup behavior of earlier versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="02521-104">\<Configuration >-Element</span><span class="sxs-lookup"><span data-stu-id="02521-104">\<configuration> Element</span></span>  
<span data-ttu-id="02521-105">\<Common Language Runtime >-Element</span><span class="sxs-lookup"><span data-stu-id="02521-105">\<runtime> Element</span></span>  
<span data-ttu-id="02521-106">\<shadowCopyVerifyByTimestamp>-Element</span><span class="sxs-lookup"><span data-stu-id="02521-106">\<shadowCopyVerifyByTimestamp> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02521-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="02521-107">Syntax</span></span>  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02521-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="02521-108">Attributes and Elements</span></span>  
 <span data-ttu-id="02521-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="02521-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02521-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="02521-110">Attributes</span></span>  
  
|<span data-ttu-id="02521-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="02521-111">Attribute</span></span>|<span data-ttu-id="02521-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02521-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="02521-113">enabled</span><span class="sxs-lookup"><span data-stu-id="02521-113">enabled</span></span>|<span data-ttu-id="02521-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="02521-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="02521-115">Gibt an, ob die Anwendungsdomänen, die verwenden der Schattenkopiefunktion Assembly-Zeitstempel vergleichen, beim Starten zu bestimmen, ob eine Assembly aktualisiert wurde, bevor Sie die Assembly für die Schattenkopiefunktion.</span><span class="sxs-lookup"><span data-stu-id="02521-115">Specifies whether application domains that use shadow copying compare assembly time stamps when starting up, to determine whether an assembly has been updated before shadow copying the assembly.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="02521-116">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="02521-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="02521-117">Wert</span><span class="sxs-lookup"><span data-stu-id="02521-117">Value</span></span>|<span data-ttu-id="02521-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02521-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="02521-119">true</span><span class="sxs-lookup"><span data-stu-id="02521-119">true</span></span>|<span data-ttu-id="02521-120">Beim Start kopiert wird nur Assemblys, die aktualisiert wurden, seit sie zuletzt in das Schattenkopieverzeichnis kopiert wurden.</span><span class="sxs-lookup"><span data-stu-id="02521-120">At startup, copies only assemblies that have been updated since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="02521-121">Dies ist die Standardeinstellung für .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="02521-121">This is the default for the .NET Framework 4.</span></span>|  
|<span data-ttu-id="02521-122">False</span><span class="sxs-lookup"><span data-stu-id="02521-122">false</span></span>|<span data-ttu-id="02521-123">Wird auf das Startverhalten früherer Versionen von .NET Framework, dem bestand darin, alle Dateien beim Start zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="02521-123">Reverts to the startup behavior of previous versions of the .NET Framework, which was to copy all files at startup.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02521-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="02521-124">Child Elements</span></span>  
 <span data-ttu-id="02521-125">Keine</span><span class="sxs-lookup"><span data-stu-id="02521-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02521-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="02521-126">Parent Elements</span></span>  
  
|<span data-ttu-id="02521-127">Element</span><span class="sxs-lookup"><span data-stu-id="02521-127">Element</span></span>|<span data-ttu-id="02521-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02521-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="02521-129">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="02521-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="02521-130">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="02521-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02521-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="02521-131">Remarks</span></span>  
 <span data-ttu-id="02521-132">Ab .NET Framework 4 sind Assemblys Schattenkopien nur, wenn ihre Zeitstempel angeben, dass sie geändert wurden, seit sie zuletzt in das Schattenkopieverzeichnis kopiert wurden.</span><span class="sxs-lookup"><span data-stu-id="02521-132">Starting with the .NET Framework 4, assemblies are shadow copied only if their time stamps indicate that they have changed since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="02521-133">Dies verbessert die Startzeiten für viele Anwendungen, die Schattenkopiefunktion, verwenden Sie, wie in beschrieben [Schattenkopien von Assemblys](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="02521-133">This improves startup times for many applications that use shadow copying, as described in [Shadow Copying Assemblies](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md).</span></span> <span data-ttu-id="02521-134">Anwendungen, die einen hohen Prozentsatz und Häufigkeit von Assembly-Updates verfügen möglicherweise nicht aufgrund der Änderung im Verhalten profitieren.</span><span class="sxs-lookup"><span data-stu-id="02521-134">Applications that have a high percentage and frequency of assembly updates might not benefit from this change in behavior.</span></span> <span data-ttu-id="02521-135">In diesem Fall können Sie dieses Element, um das Verhalten früherer Versionen von .NET Framework wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="02521-135">In that case, you can use this element to restore the behavior of previous versions of the .NET Framework.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02521-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="02521-136">Example</span></span>  
 <span data-ttu-id="02521-137">Das folgende Beispiel zeigt, wie Sie das standardmäßige Startverhalten der Schattenkopiefunktion in .NET Framework 4 zu deaktivieren, und machen Sie auf das Startverhalten vorheriger Versionen von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="02521-137">The following example shows how to disable the default startup behavior of shadow copying in the .NET Framework 4, and revert to the startup behavior of previous versions of the .NET Framework.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="02521-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02521-138">See also</span></span>

- [<span data-ttu-id="02521-139">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="02521-139">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="02521-140">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="02521-140">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="02521-141">Erstellen von Schattenkopien von Assemblys</span><span class="sxs-lookup"><span data-stu-id="02521-141">Shadow Copying Assemblies</span></span>](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)
