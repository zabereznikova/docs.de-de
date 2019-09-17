---
title: <NetFx40_LegacySecurityPolicy>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2cd6f937811ae503dd4de7ff989510c4eb8b8933
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252444"
---
# <a name="netfx40_legacysecuritypolicy-element"></a><span data-ttu-id="aab6c-102">\<NetFx40_LegacySecurityPolicy >-Element</span><span class="sxs-lookup"><span data-stu-id="aab6c-102">\<NetFx40_LegacySecurityPolicy> Element</span></span>

<span data-ttu-id="aab6c-103">Gibt an, ob die Runtime die Legacyrichtlinie für Code Access Security (CAS) verwendet.</span><span class="sxs-lookup"><span data-stu-id="aab6c-103">Specifies whether the runtime uses legacy code access security (CAS) policy.</span></span>

<span data-ttu-id="aab6c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="aab6c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="aab6c-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="aab6c-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="aab6c-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<NetFx40_LegacySecurityPolicy >**</span><span class="sxs-lookup"><span data-stu-id="aab6c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_LegacySecurityPolicy>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="aab6c-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="aab6c-107">Syntax</span></span>

```xml
<NetFx40_LegacySecurityPolicy
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="aab6c-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="aab6c-108">Attributes and Elements</span></span>

<span data-ttu-id="aab6c-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="aab6c-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="aab6c-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="aab6c-110">Attributes</span></span>

|<span data-ttu-id="aab6c-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="aab6c-111">Attribute</span></span>|<span data-ttu-id="aab6c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aab6c-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="aab6c-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="aab6c-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="aab6c-114">Gibt an, ob die Runtime die Legacy-CAS-Richtlinie verwendet</span><span class="sxs-lookup"><span data-stu-id="aab6c-114">Specifies whether the runtime uses legacy CAS policy.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="aab6c-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="aab6c-115">enabled Attribute</span></span>

|<span data-ttu-id="aab6c-116">Wert</span><span class="sxs-lookup"><span data-stu-id="aab6c-116">Value</span></span>|<span data-ttu-id="aab6c-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aab6c-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="aab6c-118">Die Common-CAS-Richtlinie wird von der Laufzeit nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="aab6c-118">The runtime does not use legacy CAS policy.</span></span> <span data-ttu-id="aab6c-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="aab6c-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="aab6c-120">Die Laufzeit verwendet die Legacy-CAS-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="aab6c-120">The runtime uses legacy CAS policy.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="aab6c-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aab6c-121">Child Elements</span></span>

<span data-ttu-id="aab6c-122">Keine</span><span class="sxs-lookup"><span data-stu-id="aab6c-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="aab6c-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aab6c-123">Parent Elements</span></span>

|<span data-ttu-id="aab6c-124">Element</span><span class="sxs-lookup"><span data-stu-id="aab6c-124">Element</span></span>|<span data-ttu-id="aab6c-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aab6c-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="aab6c-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="aab6c-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="aab6c-127">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="aab6c-127">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="aab6c-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aab6c-128">Remarks</span></span>

<span data-ttu-id="aab6c-129">In den .NET Framework Version 3,5 und früheren Versionen ist die CAS-Richtlinie immer wirksam.</span><span class="sxs-lookup"><span data-stu-id="aab6c-129">In the .NET Framework version 3.5 and earlier versions, CAS policy is always in effect.</span></span> <span data-ttu-id="aab6c-130">In der .NET Framework 4 muss die CAS-Richtlinie aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="aab6c-130">In the .NET Framework 4, CAS policy must be enabled.</span></span>

<span data-ttu-id="aab6c-131">Die CAS-Richtlinie ist Versions spezifisch.</span><span class="sxs-lookup"><span data-stu-id="aab6c-131">CAS policy is version-specific.</span></span> <span data-ttu-id="aab6c-132">Benutzerdefinierte CAS-Richtlinien, die in früheren Versionen der .NET Framework vorhanden sind, müssen in der .NET Framework 4 neu angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="aab6c-132">Custom CAS policies that exist in earlier versions of the .NET Framework must be respecified in the .NET Framework 4.</span></span>

<span data-ttu-id="aab6c-133">Das Anwenden `<NetFx40_LegacySecurityPolicy>` des-Elements auf eine .NET Framework 4-Assembly wirkt sich nicht auf [Sicherheits transparenten Code](../../../misc/security-transparent-code.md)aus; die Transparenzregeln gelten weiterhin.</span><span class="sxs-lookup"><span data-stu-id="aab6c-133">Applying the `<NetFx40_LegacySecurityPolicy>` element to a .NET Framework 4 assembly does not affect [security-transparent code](../../../misc/security-transparent-code.md); the transparency rules still apply.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aab6c-134">Das Anwenden des `<NetFx40_LegacySecurityPolicy>`-Elements kann zu erheblichen Leistungseinbußen für native Imageassemblys führen, die vom [Native Image Generator (Ngen.exe)](../../../tools/ngen-exe-native-image-generator.md) erstellt wurden und nicht im globalen [Assemblycache](../../../app-domains/gac.md) installiert sind.</span><span class="sxs-lookup"><span data-stu-id="aab6c-134">Applying the `<NetFx40_LegacySecurityPolicy>` element can result in significant performance penalties for native image assemblies created by the [Native Image Generator (Ngen.exe)](../../../tools/ngen-exe-native-image-generator.md) that are not installed in the [global assembly cache](../../../app-domains/gac.md).</span></span> <span data-ttu-id="aab6c-135">Die Leistungsminderung wird dadurch verursacht, dass die Common Language Runtime die Assemblys nicht als systemeigene Images lädt, wenn das Attribut angewendet wird, was dazu führt, dass Sie als Just-in-Time-Assemblys geladen werden.</span><span class="sxs-lookup"><span data-stu-id="aab6c-135">The performance degradation is caused by the inability of the runtime to load the assemblies as native images when the attribute is applied, resulting in their being loaded as just-in-time assemblies.</span></span>

> [!NOTE]
> <span data-ttu-id="aab6c-136">Wenn Sie in den Projekteinstellungen für das Visual Studio-Projekt eine Ziel .NET Framework Version angeben, die älter als die .NET Framework 4 ist, wird die CAS-Richtlinie aktiviert, einschließlich aller benutzerdefinierten CAS-Richtlinien, die Sie für diese Version angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="aab6c-136">If you specify a target .NET Framework version that is earlier than the .NET Framework 4 in the project settings for your Visual Studio project, CAS policy will be enabled, including any custom CAS policies you specified for that version.</span></span> <span data-ttu-id="aab6c-137">Sie können jedoch keine neuen .NET Framework 4-Typen und-Member verwenden.</span><span class="sxs-lookup"><span data-stu-id="aab6c-137">However, you will not be able to use new .NET Framework 4 types and members.</span></span> <span data-ttu-id="aab6c-138">Sie können auch eine frühere Version der .NET Framework angeben, indem Sie das [ \<supportedRuntime-> Element](../startup/supportedruntime-element.md) im Schema der Start Einstellungen in der [Anwendungs Konfigurationsdatei](../../index.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="aab6c-138">You can also specify an earlier version of the .NET Framework by using the [\<supportedRuntime> element](../startup/supportedruntime-element.md) in the startup settings schema in your [application configuration file](../../index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="aab6c-139">Bei der Syntax der Konfigurationsdatei wird die groß-/klein</span><span class="sxs-lookup"><span data-stu-id="aab6c-139">Configuration file syntax is case-sensitive.</span></span> <span data-ttu-id="aab6c-140">Sie sollten die Syntax verwenden, wie in den Abschnitten Syntax und example bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="aab6c-140">You should use the syntax as provided in the Syntax and Example sections.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="aab6c-141">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="aab6c-141">Configuration File</span></span>

<span data-ttu-id="aab6c-142">Dieses Element kann nur in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aab6c-142">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="aab6c-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aab6c-143">Example</span></span>

<span data-ttu-id="aab6c-144">Im folgenden Beispiel wird gezeigt, wie die Legacy-CAS-Richtlinie für eine Anwendung aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="aab6c-144">The following example shows how to enable legacy CAS policy for an application.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="aab6c-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aab6c-145">See also</span></span>

- [<span data-ttu-id="aab6c-146">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="aab6c-146">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="aab6c-147">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="aab6c-147">Configuration File Schema</span></span>](../index.md)
