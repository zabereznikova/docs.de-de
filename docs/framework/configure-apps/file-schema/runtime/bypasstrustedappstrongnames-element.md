---
title: <bypassTrustedAppStrongNames>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3fb198d6a19e25df4c86186d35aab3330c53121c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252768"
---
# <a name="bypasstrustedappstrongnames-element"></a><span data-ttu-id="0edea-102">\<bypassTrustedAppStrongNames>-Element</span><span class="sxs-lookup"><span data-stu-id="0edea-102">\<bypassTrustedAppStrongNames> Element</span></span>
<span data-ttu-id="0edea-103">Gibt an, ob die Überprüfung von starken Namen für vollständig vertrauenswürdige Assemblys umgangen werden soll, <xref:System.AppDomain>die in eine vollständige Vertrauenswürdigkeit geladen werden.</span><span class="sxs-lookup"><span data-stu-id="0edea-103">Specifies whether to bypass the validation of strong names on full-trust assemblies that are loaded into a full-trust <xref:System.AppDomain>.</span></span>  
  
<span data-ttu-id="0edea-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0edea-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0edea-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="0edea-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="0edea-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<bypassTrustedAppStrongNames>**</span><span class="sxs-lookup"><span data-stu-id="0edea-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<bypassTrustedAppStrongNames>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0edea-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="0edea-107">Syntax</span></span>  
  
```xml  
<bypassTrustedAppStrongNames    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0edea-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0edea-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0edea-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0edea-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0edea-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="0edea-110">Attributes</span></span>  
  
|<span data-ttu-id="0edea-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="0edea-111">Attribute</span></span>|<span data-ttu-id="0edea-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0edea-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="0edea-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="0edea-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="0edea-114">Gibt an, ob das Umgehungs Feature aktiviert ist, das das Validieren starker Namen für vollständig vertrauenswürdige Assemblys vermeidet.</span><span class="sxs-lookup"><span data-stu-id="0edea-114">Specifies whether the bypass feature that avoids validating strong names for full-trust assemblies is enabled.</span></span> <span data-ttu-id="0edea-115">Wenn diese Funktion aktiviert ist, werden starke Namen nicht auf Richtigkeit überprüft, wenn die Assembly geladen wird.</span><span class="sxs-lookup"><span data-stu-id="0edea-115">When this feature is enabled, strong names are not validated for correctness when the assembly is loaded.</span></span> <span data-ttu-id="0edea-116">Die Standardeinstellung ist `true`.</span><span class="sxs-lookup"><span data-stu-id="0edea-116">The default is `true`.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="0edea-117">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="0edea-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="0edea-118">Wert</span><span class="sxs-lookup"><span data-stu-id="0edea-118">Value</span></span>|<span data-ttu-id="0edea-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0edea-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="0edea-120">Signaturen mit starkem Namen für vollständig vertrauenswürdige Assemblys werden nicht überprüft, wenn die Assemblys in <xref:System.AppDomain>eine voll vertrauenswürdige Assembly geladen werden.</span><span class="sxs-lookup"><span data-stu-id="0edea-120">Strong-name signatures on full-trust assemblies are not validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="0edea-121">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="0edea-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="0edea-122">Signaturen mit starkem Namen für vollständig vertrauenswürdige Assemblys werden überprüft, wenn die Assemblys in <xref:System.AppDomain>eine voll vertrauenswürdige Assembly geladen werden.</span><span class="sxs-lookup"><span data-stu-id="0edea-122">Strong-name signatures on full-trust assemblies are validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="0edea-123">Die Signatur des starken Namens wird nur zur Richtigkeit der Signatur geprüft. Er wird nicht mit einem anderen starken Namen für eine Entsprechung verglichen.</span><span class="sxs-lookup"><span data-stu-id="0edea-123">The strong-name signature is checked only for signature correctness; it is not compared to another strong name for a match.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0edea-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0edea-124">Child Elements</span></span>  
 <span data-ttu-id="0edea-125">Keine</span><span class="sxs-lookup"><span data-stu-id="0edea-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0edea-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0edea-126">Parent Elements</span></span>  
  
|<span data-ttu-id="0edea-127">Element</span><span class="sxs-lookup"><span data-stu-id="0edea-127">Element</span></span>|<span data-ttu-id="0edea-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0edea-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0edea-129">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="0edea-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="0edea-130">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="0edea-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0edea-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0edea-131">Remarks</span></span>  
 <span data-ttu-id="0edea-132">Die Strong-Name-Bypass-Funktion vermeidet den Aufwand der Signatur Überprüfung mit starkem Namen für vollständig vertrauenswürdige Assemblys.</span><span class="sxs-lookup"><span data-stu-id="0edea-132">The strong-name bypass feature avoids the overhead of strong-name signature verification of full-trust assemblies.</span></span>  
  
 <span data-ttu-id="0edea-133">Das Bypass-Feature gilt für jede Assembly, die mit einem starken Namen signiert ist und die folgenden Eigenschaften aufweist:</span><span class="sxs-lookup"><span data-stu-id="0edea-133">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>  
  
- <span data-ttu-id="0edea-134">Voll vertrauenswürdig ohne <xref:System.Security.Policy.StrongName> den Beweis (z. b `MyComputer` . hat einen Zonen Nachweis).</span><span class="sxs-lookup"><span data-stu-id="0edea-134">Fully trusted without the <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>  
  
- <span data-ttu-id="0edea-135">Geladen in eine voll vertrauenswürdige <xref:System.AppDomain></span><span class="sxs-lookup"><span data-stu-id="0edea-135">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>  
  
- <span data-ttu-id="0edea-136">Geladen von einem Speicherort unter der <xref:System.AppDomainSetup.ApplicationBase%2A>-Eigenschaft von dieser <xref:System.AppDomain></span><span class="sxs-lookup"><span data-stu-id="0edea-136">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>  
  
- <span data-ttu-id="0edea-137">Nicht verzögert signiert</span><span class="sxs-lookup"><span data-stu-id="0edea-137">Not delay-signed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0edea-138">Wenn das Umgehungs Feature für alle Anwendungen auf dem Computer mithilfe eines Registrierungsschlüssels ausgeschaltet wurde, hat diese Einstellung keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="0edea-138">If the bypass feature has been turned off for all applications on the computer by using a registry key, this configuration file setting has no effect.</span></span> <span data-ttu-id="0edea-139">Weitere Informationen finden Sie unter [Vorgehensweise: Deaktivieren der Strong-Name-Bypass-Funktion](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span><span class="sxs-lookup"><span data-stu-id="0edea-139">For more information, see [How to: Disable the Strong-Name Bypass Feature](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0edea-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0edea-140">Example</span></span>  
 <span data-ttu-id="0edea-141">Im folgenden Beispiel wird gezeigt, wie das Verhalten angegeben wird, mit dem die Signatur mit starkem Namen für vollständig vertrauenswürdige Assemblys überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="0edea-141">The following example shows how to specify the behavior that validates the strong-name signature on full-trust assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0edea-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0edea-142">See also</span></span>

- [<span data-ttu-id="0edea-143">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="0edea-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0edea-144">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="0edea-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="0edea-145">Vorgehensweise: Deaktivieren der Strong-Name-Bypass-Funktion</span><span class="sxs-lookup"><span data-stu-id="0edea-145">How to: Disable the Strong-Name Bypass Feature</span></span>](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md)
