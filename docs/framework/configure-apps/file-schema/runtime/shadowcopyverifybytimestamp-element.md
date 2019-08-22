---
title: <shadowCopyVerifyByTimestamp>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f3ea57364832553d16c7e34fc887b1c9f821602
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663451"
---
# <a name="shadowcopyverifybytimestamp-element"></a><span data-ttu-id="073ad-102">\<shadowCopyVerifyByTimestamp>-Element</span><span class="sxs-lookup"><span data-stu-id="073ad-102">\<shadowCopyVerifyByTimestamp> Element</span></span>
<span data-ttu-id="073ad-103">Gibt an, ob beim Schatten kopieren das standardmäßige Startverhalten verwendet wird, das in der .NET Framework 4 eingeführt wurde, oder ob das Startverhalten früherer Versionen der .NET Framework wieder hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="073ad-103">Specifies whether shadow copying uses the default startup behavior introduced in the .NET Framework 4, or reverts to the startup behavior of earlier versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="073ad-104">\<Configuration >-Element</span><span class="sxs-lookup"><span data-stu-id="073ad-104">\<configuration> Element</span></span>  
<span data-ttu-id="073ad-105">\<Runtime-> Element</span><span class="sxs-lookup"><span data-stu-id="073ad-105">\<runtime> Element</span></span>  
<span data-ttu-id="073ad-106">\<shadowCopyVerifyByTimestamp>-Element</span><span class="sxs-lookup"><span data-stu-id="073ad-106">\<shadowCopyVerifyByTimestamp> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="073ad-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="073ad-107">Syntax</span></span>  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="073ad-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="073ad-108">Attributes and Elements</span></span>  
 <span data-ttu-id="073ad-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="073ad-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="073ad-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="073ad-110">Attributes</span></span>  
  
|<span data-ttu-id="073ad-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="073ad-111">Attribute</span></span>|<span data-ttu-id="073ad-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="073ad-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="073ad-113">enabled</span><span class="sxs-lookup"><span data-stu-id="073ad-113">enabled</span></span>|<span data-ttu-id="073ad-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="073ad-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="073ad-115">Gibt an, ob Anwendungs Domänen, die die Schatten Kopien verwenden, beim Start assemblyzeit Stempel vergleichen, um zu bestimmen, ob eine Assembly vor dem Kopieren der Assembly aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="073ad-115">Specifies whether application domains that use shadow copying compare assembly time stamps when starting up, to determine whether an assembly has been updated before shadow copying the assembly.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="073ad-116">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="073ad-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="073ad-117">Wert</span><span class="sxs-lookup"><span data-stu-id="073ad-117">Value</span></span>|<span data-ttu-id="073ad-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="073ad-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="073ad-119">true</span><span class="sxs-lookup"><span data-stu-id="073ad-119">true</span></span>|<span data-ttu-id="073ad-120">Beim Start von werden nur Assemblys kopiert, die aktualisiert wurden, seit Sie zuletzt in das schattenkopiesverzeichnis kopiert wurden.</span><span class="sxs-lookup"><span data-stu-id="073ad-120">At startup, copies only assemblies that have been updated since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="073ad-121">Dies ist die Standardeinstellung für die .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="073ad-121">This is the default for the .NET Framework 4.</span></span>|  
|<span data-ttu-id="073ad-122">false</span><span class="sxs-lookup"><span data-stu-id="073ad-122">false</span></span>|<span data-ttu-id="073ad-123">Setzt auf das Startverhalten vorheriger Versionen der .NET Framework zurück, bei der alle Dateien beim Start kopiert wurden.</span><span class="sxs-lookup"><span data-stu-id="073ad-123">Reverts to the startup behavior of previous versions of the .NET Framework, which was to copy all files at startup.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="073ad-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="073ad-124">Child Elements</span></span>  
 <span data-ttu-id="073ad-125">Keine</span><span class="sxs-lookup"><span data-stu-id="073ad-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="073ad-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="073ad-126">Parent Elements</span></span>  
  
|<span data-ttu-id="073ad-127">Element</span><span class="sxs-lookup"><span data-stu-id="073ad-127">Element</span></span>|<span data-ttu-id="073ad-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="073ad-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="073ad-129">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="073ad-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="073ad-130">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="073ad-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="073ad-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="073ad-131">Remarks</span></span>  
 <span data-ttu-id="073ad-132">Beginnend mit dem .NET Framework 4 werden Assemblys nur dann als Schatten kopiert, wenn Ihre Zeitstempel darauf hindeuten, dass Sie geändert wurden, seit Sie zuletzt in das schattenkopieverzeichnis kopiert wurden.</span><span class="sxs-lookup"><span data-stu-id="073ad-132">Starting with the .NET Framework 4, assemblies are shadow copied only if their time stamps indicate that they have changed since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="073ad-133">Dies verbessert die Startzeiten für viele Anwendungen, die Schatten Kopien verwenden, wie in [Schatten Kopien](../../../app-domains/shadow-copy-assemblies.md)von Assemblys beschrieben.</span><span class="sxs-lookup"><span data-stu-id="073ad-133">This improves startup times for many applications that use shadow copying, as described in [Shadow Copying Assemblies](../../../app-domains/shadow-copy-assemblies.md).</span></span> <span data-ttu-id="073ad-134">Anwendungen, die einen hohen Prozentsatz und eine Häufigkeit von Assemblyaktualisierungen aufweisen, profitieren möglicherweise nicht von dieser Änderung des Verhaltens.</span><span class="sxs-lookup"><span data-stu-id="073ad-134">Applications that have a high percentage and frequency of assembly updates might not benefit from this change in behavior.</span></span> <span data-ttu-id="073ad-135">In diesem Fall können Sie dieses Element verwenden, um das Verhalten vorheriger Versionen des .NET Framework wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="073ad-135">In that case, you can use this element to restore the behavior of previous versions of the .NET Framework.</span></span>  
  
## <a name="example"></a><span data-ttu-id="073ad-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="073ad-136">Example</span></span>  
 <span data-ttu-id="073ad-137">Im folgenden Beispiel wird gezeigt, wie Sie das Standard Startverhalten des schattenkopierens in .NET Framework 4 deaktivieren und das Startverhalten vorheriger Versionen der .NET Framework wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="073ad-137">The following example shows how to disable the default startup behavior of shadow copying in the .NET Framework 4, and revert to the startup behavior of previous versions of the .NET Framework.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="073ad-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="073ad-138">See also</span></span>

- [<span data-ttu-id="073ad-139">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="073ad-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="073ad-140">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="073ad-140">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="073ad-141">Erstellen von Schattenkopien von Assemblys</span><span class="sxs-lookup"><span data-stu-id="073ad-141">Shadow Copying Assemblies</span></span>](../../../app-domains/shadow-copy-assemblies.md)
