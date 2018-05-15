---
title: '&lt;NetFx40_LegacySecurityPolicy&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d9312d25842ccfcdf84e678d34b9bfde3fe7dd0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltnetfx40legacysecuritypolicygt-element"></a><span data-ttu-id="201f3-102">&lt;NetFx40_LegacySecurityPolicy&gt; Element</span><span class="sxs-lookup"><span data-stu-id="201f3-102">&lt;NetFx40_LegacySecurityPolicy&gt; Element</span></span>
<span data-ttu-id="201f3-103">Gibt an, ob die Runtime die Legacyrichtlinie für Code Access Security (CAS) verwendet.</span><span class="sxs-lookup"><span data-stu-id="201f3-103">Specifies whether the runtime uses legacy code access security (CAS) policy.</span></span>  
  
 <span data-ttu-id="201f3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="201f3-104">\<configuration></span></span>  
<span data-ttu-id="201f3-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="201f3-105">\<runtime></span></span>  
<span data-ttu-id="201f3-106">< NetFx40_LegacySecurityPolicy ></span><span class="sxs-lookup"><span data-stu-id="201f3-106"><NetFx40_LegacySecurityPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="201f3-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="201f3-107">Syntax</span></span>  
  
```xml  
<NetFx40_LegacySecurityPolicy  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="201f3-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="201f3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="201f3-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="201f3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="201f3-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="201f3-110">Attributes</span></span>  
  
|<span data-ttu-id="201f3-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="201f3-111">Attribute</span></span>|<span data-ttu-id="201f3-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="201f3-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="201f3-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="201f3-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="201f3-114">Gibt an, ob die Common Language Runtime CAS-legacyrichtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="201f3-114">Specifies whether the runtime uses legacy CAS policy.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="201f3-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="201f3-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="201f3-116">Wert</span><span class="sxs-lookup"><span data-stu-id="201f3-116">Value</span></span>|<span data-ttu-id="201f3-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="201f3-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="201f3-118">Legacy-CAS-Richtlinie wird von die Laufzeit nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="201f3-118">The runtime does not use legacy CAS policy.</span></span> <span data-ttu-id="201f3-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="201f3-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="201f3-120">Die Laufzeit verwendet die legacy-CAS-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="201f3-120">The runtime uses legacy CAS policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="201f3-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="201f3-121">Child Elements</span></span>  
 <span data-ttu-id="201f3-122">Keine</span><span class="sxs-lookup"><span data-stu-id="201f3-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="201f3-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="201f3-123">Parent Elements</span></span>  
  
|<span data-ttu-id="201f3-124">Element</span><span class="sxs-lookup"><span data-stu-id="201f3-124">Element</span></span>|<span data-ttu-id="201f3-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="201f3-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="201f3-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="201f3-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="201f3-127">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="201f3-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="201f3-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="201f3-128">Remarks</span></span>  
 <span data-ttu-id="201f3-129">Die CAS-Richtlinie ist in .NET Framework, Version 3.5 und frühere Versionen müssen immer wirksam.</span><span class="sxs-lookup"><span data-stu-id="201f3-129">In the .NET Framework version 3.5 and earlier versions, CAS policy is always in effect.</span></span> <span data-ttu-id="201f3-130">In der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], CAS-Richtlinie muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="201f3-130">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], CAS policy must be enabled.</span></span>  
  
 <span data-ttu-id="201f3-131">Die CAS-Richtlinie ist versionsspezifisch.</span><span class="sxs-lookup"><span data-stu-id="201f3-131">CAS policy is version-specific.</span></span> <span data-ttu-id="201f3-132">Benutzerdefinierte CAS-Richtlinien, die in früheren Versionen von .NET Framework vorhanden sein müssen erneut angegeben werden, der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="201f3-132">Custom CAS policies that exist in earlier versions of the .NET Framework must be respecified in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span>  
  
 <span data-ttu-id="201f3-133">Anwenden der `<NetFx40_LegacySecurityPolicy>` Element um eine [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] Assembly hat keinen Einfluss auf [Sicherheitstransparenter Code](../../../../../docs/framework/misc/security-transparent-code.md); die Transparenzregeln gelten weiterhin.</span><span class="sxs-lookup"><span data-stu-id="201f3-133">Applying the `<NetFx40_LegacySecurityPolicy>` element to a [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] assembly does not affect [security-transparent code](../../../../../docs/framework/misc/security-transparent-code.md); the transparency rules still apply.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="201f3-134">Anwenden der `<NetFx40_LegacySecurityPolicy>` Element kann bedeutenden Leistungseinbußen führen, für die Assemblys von systemeigenen Images erstellt, indem die [Native Image Generator (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) , die nicht installiert sind die [globaler Assemblycache ](../../../../../docs/framework/app-domains/gac.md).</span><span class="sxs-lookup"><span data-stu-id="201f3-134">Applying the `<NetFx40_LegacySecurityPolicy>` element can result in significant performance penalties for native image assemblies created by the [Native Image Generator (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) that are not installed in the [global assembly cache](../../../../../docs/framework/app-domains/gac.md).</span></span> <span data-ttu-id="201f3-135">Leistungsabfälle wird verursacht, wenn die Unfähigkeit der Laufzeit, Assemblys als systemeigene Images zu laden, wenn das Attribut angewendet wird, wodurch ihre wird als just-in-Time-Assemblys geladen.</span><span class="sxs-lookup"><span data-stu-id="201f3-135">The performance degradation is caused by the inability of the runtime to load the assemblies as native images when the attribute is applied, resulting in their being loaded as just-in-time assemblies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="201f3-136">Wenn Sie eine .NET Framework-Zielversion angeben, die älter ist als die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] in den projekteinstellungen für Visual Studio-Projekts, die CAS-Richtlinie aktiviert, einschließlich alle benutzerdefinierten CAS-Richtlinien, die Sie für die jeweilige Version angegeben.</span><span class="sxs-lookup"><span data-stu-id="201f3-136">If you specify a target .NET Framework version that is earlier than the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] in the project settings for your Visual Studio project, CAS policy will be enabled, including any custom CAS policies you specified for that version.</span></span> <span data-ttu-id="201f3-137">Sie werden jedoch neue verwenden [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] Typen und Member.</span><span class="sxs-lookup"><span data-stu-id="201f3-137">However, you will not be able to use new [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] types and members.</span></span> <span data-ttu-id="201f3-138">Sie können auch eine frühere Version von .NET Framework angeben, mit der [ \<SupportedRuntime >-Element](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) in das Schema für starteinstellungen in Ihre [Anwendungskonfigurationsdatei](../../../../../docs/framework/configure-apps/index.md).</span><span class="sxs-lookup"><span data-stu-id="201f3-138">You can also specify an earlier version of the .NET Framework by using the [\<supportedRuntime> element](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) in the startup settings schema in your [application configuration file](../../../../../docs/framework/configure-apps/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="201f3-139">Syntax von Konfigurationsdateien wird Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="201f3-139">Configuration file syntax is case-sensitive.</span></span> <span data-ttu-id="201f3-140">Sie sollten die Syntax verwenden, wie in den Abschnitten Syntax und ein Beispiel bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="201f3-140">You should use the syntax as provided in the Syntax and Example sections.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="201f3-141">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="201f3-141">Configuration File</span></span>  
 <span data-ttu-id="201f3-142">Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="201f3-142">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="201f3-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="201f3-143">Example</span></span>  
 <span data-ttu-id="201f3-144">Das folgende Beispiel veranschaulicht die legacy-CAS-Richtlinie für eine Anwendung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="201f3-144">The following example shows how to enable legacy CAS policy for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="201f3-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="201f3-145">See Also</span></span>  
 [<span data-ttu-id="201f3-146">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="201f3-146">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="201f3-147">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="201f3-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
