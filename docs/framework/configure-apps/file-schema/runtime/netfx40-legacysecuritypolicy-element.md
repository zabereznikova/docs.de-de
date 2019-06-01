---
title: <NetFx40_LegacySecurityPolicy>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 848c56773c0ff2986f0bec3e82a08a3d0dd35434
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456472"
---
# <a name="netfx40legacysecuritypolicy-element"></a><span data-ttu-id="ebc66-102">\<NetFx40_LegacySecurityPolicy >-Element</span><span class="sxs-lookup"><span data-stu-id="ebc66-102">\<NetFx40_LegacySecurityPolicy> Element</span></span>
<span data-ttu-id="ebc66-103">Gibt an, ob die Runtime die Legacyrichtlinie für Code Access Security (CAS) verwendet.</span><span class="sxs-lookup"><span data-stu-id="ebc66-103">Specifies whether the runtime uses legacy code access security (CAS) policy.</span></span>  
  
 <span data-ttu-id="ebc66-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ebc66-104">\<configuration></span></span>  
<span data-ttu-id="ebc66-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="ebc66-105">\<runtime></span></span>  
<span data-ttu-id="ebc66-106"><NetFx40_LegacySecurityPolicy></span><span class="sxs-lookup"><span data-stu-id="ebc66-106"><NetFx40_LegacySecurityPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebc66-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ebc66-107">Syntax</span></span>  
  
```xml  
<NetFx40_LegacySecurityPolicy  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ebc66-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ebc66-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ebc66-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ebc66-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ebc66-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="ebc66-110">Attributes</span></span>  
  
|<span data-ttu-id="ebc66-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="ebc66-111">Attribute</span></span>|<span data-ttu-id="ebc66-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ebc66-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="ebc66-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="ebc66-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="ebc66-114">Gibt an, ob die Runtime die CAS-legacyrichtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="ebc66-114">Specifies whether the runtime uses legacy CAS policy.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="ebc66-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="ebc66-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="ebc66-116">Wert</span><span class="sxs-lookup"><span data-stu-id="ebc66-116">Value</span></span>|<span data-ttu-id="ebc66-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ebc66-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="ebc66-118">Die Runtime verwendet nicht CAS-legacyrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="ebc66-118">The runtime does not use legacy CAS policy.</span></span> <span data-ttu-id="ebc66-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="ebc66-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="ebc66-120">Die Runtime verwendet die legacy-CAS-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="ebc66-120">The runtime uses legacy CAS policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ebc66-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ebc66-121">Child Elements</span></span>  
 <span data-ttu-id="ebc66-122">Keine</span><span class="sxs-lookup"><span data-stu-id="ebc66-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ebc66-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ebc66-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ebc66-124">Element</span><span class="sxs-lookup"><span data-stu-id="ebc66-124">Element</span></span>|<span data-ttu-id="ebc66-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ebc66-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ebc66-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ebc66-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ebc66-127">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="ebc66-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ebc66-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ebc66-128">Remarks</span></span>  
 <span data-ttu-id="ebc66-129">CAS-Richtlinie ist in der .NET Framework, Version 3.5 und früheren Versionen immer wirksam.</span><span class="sxs-lookup"><span data-stu-id="ebc66-129">In the .NET Framework version 3.5 and earlier versions, CAS policy is always in effect.</span></span> <span data-ttu-id="ebc66-130">In der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], CAS-Richtlinie muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="ebc66-130">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], CAS policy must be enabled.</span></span>  
  
 <span data-ttu-id="ebc66-131">CAS-Richtlinie ist versionsspezifisch.</span><span class="sxs-lookup"><span data-stu-id="ebc66-131">CAS policy is version-specific.</span></span> <span data-ttu-id="ebc66-132">Benutzerdefinierte CAS-Richtlinien, die in früheren Versionen von .NET Framework vorhanden sind, müssen in .NET Framework 4 erneut angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ebc66-132">Custom CAS policies that exist in earlier versions of the .NET Framework must be respecified in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="ebc66-133">Anwenden der `<NetFx40_LegacySecurityPolicy>` Element eine [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] Assembly hat keine Auswirkungen auf [Sicherheitstransparenter Code](../../../../../docs/framework/misc/security-transparent-code.md); die Transparenzregeln gelten weiterhin.</span><span class="sxs-lookup"><span data-stu-id="ebc66-133">Applying the `<NetFx40_LegacySecurityPolicy>` element to a [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] assembly does not affect [security-transparent code](../../../../../docs/framework/misc/security-transparent-code.md); the transparency rules still apply.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ebc66-134">Anwenden der `<NetFx40_LegacySecurityPolicy>` Elements kann dazu führen, Leistungseinbußen für Assemblys systemeigener Abbilder, die erstellt werden, indem der [Native Image Generator (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) nicht im installierten der [globalen Assemblycache ](../../../../../docs/framework/app-domains/gac.md).</span><span class="sxs-lookup"><span data-stu-id="ebc66-134">Applying the `<NetFx40_LegacySecurityPolicy>` element can result in significant performance penalties for native image assemblies created by the [Native Image Generator (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) that are not installed in the [global assembly cache](../../../../../docs/framework/app-domains/gac.md).</span></span> <span data-ttu-id="ebc66-135">Die Leistungsminderung wird verursacht, wenn die Unmöglichkeit der Runtime, die die Assemblys als native Bilder geladen werden, wenn das Attribut angewendet wird, und ihre wird als just-in-Time-Assemblys geladen.</span><span class="sxs-lookup"><span data-stu-id="ebc66-135">The performance degradation is caused by the inability of the runtime to load the assemblies as native images when the attribute is applied, resulting in their being loaded as just-in-time assemblies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ebc66-136">Wenn Sie eine .NET Framework-Zielversion, die älter als .NET Framework 4 in den projekteinstellungen für Visual Studio-Projekt ist angeben, wird die CAS-Richtlinie aktiviert werden, einschließlich benutzerdefinierten CAS-Richtlinien, die Sie für diese Version angegeben.</span><span class="sxs-lookup"><span data-stu-id="ebc66-136">If you specify a target .NET Framework version that is earlier than the .NET Framework 4 in the project settings for your Visual Studio project, CAS policy will be enabled, including any custom CAS policies you specified for that version.</span></span> <span data-ttu-id="ebc66-137">Allerdings werden Sie nicht neue .NET Framework 4-Typen und Member verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ebc66-137">However, you will not be able to use new .NET Framework 4 types and members.</span></span> <span data-ttu-id="ebc66-138">Sie können auch eine frühere Version von .NET Framework angeben, indem die [ \<SupportedRuntime >-Element](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) in das Schema für starteinstellungen in Ihrer [Konfigurationsdatei der Anwendung](../../../../../docs/framework/configure-apps/index.md).</span><span class="sxs-lookup"><span data-stu-id="ebc66-138">You can also specify an earlier version of the .NET Framework by using the [\<supportedRuntime> element](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) in the startup settings schema in your [application configuration file](../../../../../docs/framework/configure-apps/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ebc66-139">Syntax von Konfigurationsdateien wird Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="ebc66-139">Configuration file syntax is case-sensitive.</span></span> <span data-ttu-id="ebc66-140">Sie sollten die Syntax verwenden, wie in den Abschnitten zu Syntax und Beispiel bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ebc66-140">You should use the syntax as provided in the Syntax and Example sections.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="ebc66-141">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="ebc66-141">Configuration File</span></span>  
 <span data-ttu-id="ebc66-142">Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ebc66-142">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebc66-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ebc66-143">Example</span></span>  
 <span data-ttu-id="ebc66-144">Das folgende Beispiel zeigt, wie Sie die legacy-CAS-Richtlinie für eine Anwendung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ebc66-144">The following example shows how to enable legacy CAS policy for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ebc66-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebc66-145">See also</span></span>

- [<span data-ttu-id="ebc66-146">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="ebc66-146">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="ebc66-147">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="ebc66-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
