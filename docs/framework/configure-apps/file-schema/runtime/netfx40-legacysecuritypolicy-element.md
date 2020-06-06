---
title: <NetFx40_LegacySecurityPolicy>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
ms.openlocfilehash: d5192eb56bb8b640544bdc52a0bb9d8a5277efef
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73116254"
---
# <a name="netfx40_legacysecuritypolicy-element"></a><span data-ttu-id="4e9a2-102">\<NetFx40_LegacySecurityPolicy>-Element</span><span class="sxs-lookup"><span data-stu-id="4e9a2-102">\<NetFx40_LegacySecurityPolicy> Element</span></span>

<span data-ttu-id="4e9a2-103">Gibt an, ob die Runtime die Legacyrichtlinie für Code Access Security (CAS) verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e9a2-103">Specifies whether the runtime uses legacy code access security (CAS) policy.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_LegacySecurityPolicy>**  

## <a name="syntax"></a><span data-ttu-id="4e9a2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e9a2-104">Syntax</span></span>

```xml
<NetFx40_LegacySecurityPolicy
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4e9a2-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4e9a2-105">Attributes and Elements</span></span>

<span data-ttu-id="4e9a2-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4e9a2-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="4e9a2-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="4e9a2-107">Attributes</span></span>

|<span data-ttu-id="4e9a2-108">attribute</span><span class="sxs-lookup"><span data-stu-id="4e9a2-108">Attribute</span></span>|<span data-ttu-id="4e9a2-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4e9a2-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="4e9a2-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="4e9a2-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="4e9a2-111">Gibt an, ob die Runtime die Legacy-CAS-Richtlinie verwendet</span><span class="sxs-lookup"><span data-stu-id="4e9a2-111">Specifies whether the runtime uses legacy CAS policy.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="4e9a2-112">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="4e9a2-112">enabled Attribute</span></span>

|<span data-ttu-id="4e9a2-113">Wert</span><span class="sxs-lookup"><span data-stu-id="4e9a2-113">Value</span></span>|<span data-ttu-id="4e9a2-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4e9a2-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="4e9a2-115">Die Common-CAS-Richtlinie wird von der Laufzeit nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e9a2-115">The runtime does not use legacy CAS policy.</span></span> <span data-ttu-id="4e9a2-116">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="4e9a2-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="4e9a2-117">Die Laufzeit verwendet die Legacy-CAS-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="4e9a2-117">The runtime uses legacy CAS policy.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="4e9a2-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4e9a2-118">Child Elements</span></span>

<span data-ttu-id="4e9a2-119">Keine</span><span class="sxs-lookup"><span data-stu-id="4e9a2-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4e9a2-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4e9a2-120">Parent Elements</span></span>

|<span data-ttu-id="4e9a2-121">Element</span><span class="sxs-lookup"><span data-stu-id="4e9a2-121">Element</span></span>|<span data-ttu-id="4e9a2-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4e9a2-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="4e9a2-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="4e9a2-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="4e9a2-124">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="4e9a2-124">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4e9a2-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4e9a2-125">Remarks</span></span>

<span data-ttu-id="4e9a2-126">In den .NET Framework Version 3,5 und früheren Versionen ist die CAS-Richtlinie immer wirksam.</span><span class="sxs-lookup"><span data-stu-id="4e9a2-126">In the .NET Framework version 3.5 and earlier versions, CAS policy is always in effect.</span></span> <span data-ttu-id="4e9a2-127">In der .NET Framework 4 muss die CAS-Richtlinie aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="4e9a2-127">In the .NET Framework 4, CAS policy must be enabled.</span></span>

<span data-ttu-id="4e9a2-128">Die CAS-Richtlinie ist Versions spezifisch.</span><span class="sxs-lookup"><span data-stu-id="4e9a2-128">CAS policy is version-specific.</span></span> <span data-ttu-id="4e9a2-129">Benutzerdefinierte CAS-Richtlinien, die in früheren Versionen der .NET Framework vorhanden sind, müssen in der .NET Framework 4 neu angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4e9a2-129">Custom CAS policies that exist in earlier versions of the .NET Framework must be respecified in the .NET Framework 4.</span></span>

<span data-ttu-id="4e9a2-130">Das Anwenden des- `<NetFx40_LegacySecurityPolicy>` Elements auf eine .NET Framework 4-Assembly wirkt sich nicht auf [Sicherheits transparenten Code](../../../misc/security-transparent-code.md)aus; die Transparenzregeln gelten weiterhin.</span><span class="sxs-lookup"><span data-stu-id="4e9a2-130">Applying the `<NetFx40_LegacySecurityPolicy>` element to a .NET Framework 4 assembly does not affect [security-transparent code](../../../misc/security-transparent-code.md); the transparency rules still apply.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e9a2-131">Das Anwenden des- `<NetFx40_LegacySecurityPolicy>` Elements kann zu erheblichen Leistungseinbußen für Native Image-Assemblys führen, die vom [Native Image Generator (Ngen. exe)](../../../tools/ngen-exe-native-image-generator.md) erstellt werden, die nicht im globalen Assemblycache installiert sind. [global assembly cache](../../../app-domains/gac.md)</span><span class="sxs-lookup"><span data-stu-id="4e9a2-131">Applying the `<NetFx40_LegacySecurityPolicy>` element can result in significant performance penalties for native image assemblies created by the [Native Image Generator (Ngen.exe)](../../../tools/ngen-exe-native-image-generator.md) that are not installed in the [global assembly cache](../../../app-domains/gac.md).</span></span> <span data-ttu-id="4e9a2-132">Die Leistungsminderung wird dadurch verursacht, dass die Common Language Runtime die Assemblys nicht als systemeigene Images lädt, wenn das Attribut angewendet wird, was dazu führt, dass Sie als Just-in-Time-Assemblys geladen werden.</span><span class="sxs-lookup"><span data-stu-id="4e9a2-132">The performance degradation is caused by the inability of the runtime to load the assemblies as native images when the attribute is applied, resulting in their being loaded as just-in-time assemblies.</span></span>

> [!NOTE]
> <span data-ttu-id="4e9a2-133">Wenn Sie in den Projekteinstellungen für das Visual Studio-Projekt eine Ziel .NET Framework Version angeben, die älter als die .NET Framework 4 ist, wird die CAS-Richtlinie aktiviert, einschließlich aller benutzerdefinierten CAS-Richtlinien, die Sie für diese Version angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="4e9a2-133">If you specify a target .NET Framework version that is earlier than the .NET Framework 4 in the project settings for your Visual Studio project, CAS policy will be enabled, including any custom CAS policies you specified for that version.</span></span> <span data-ttu-id="4e9a2-134">Sie können jedoch keine neuen .NET Framework 4-Typen und-Member verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e9a2-134">However, you will not be able to use new .NET Framework 4 types and members.</span></span> <span data-ttu-id="4e9a2-135">Sie können auch eine frühere Version der .NET Framework angeben, indem Sie das- [ \<supportedRuntime> Element](../startup/supportedruntime-element.md) im Schema der Start Einstellungen in der [Anwendungs Konfigurationsdatei](../../index.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e9a2-135">You can also specify an earlier version of the .NET Framework by using the [\<supportedRuntime> element](../startup/supportedruntime-element.md) in the startup settings schema in your [application configuration file](../../index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4e9a2-136">Bei der Syntax der Konfigurationsdatei wird die groß-/klein</span><span class="sxs-lookup"><span data-stu-id="4e9a2-136">Configuration file syntax is case-sensitive.</span></span> <span data-ttu-id="4e9a2-137">Sie sollten die Syntax verwenden, wie in den Abschnitten Syntax und example bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="4e9a2-137">You should use the syntax as provided in the Syntax and Example sections.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="4e9a2-138">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="4e9a2-138">Configuration File</span></span>

<span data-ttu-id="4e9a2-139">Dieses Element kann nur in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4e9a2-139">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="4e9a2-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4e9a2-140">Example</span></span>

<span data-ttu-id="4e9a2-141">Im folgenden Beispiel wird gezeigt, wie die Legacy-CAS-Richtlinie für eine Anwendung aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="4e9a2-141">The following example shows how to enable legacy CAS policy for an application.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="4e9a2-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4e9a2-142">See also</span></span>

- [<span data-ttu-id="4e9a2-143">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="4e9a2-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4e9a2-144">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="4e9a2-144">Configuration File Schema</span></span>](../index.md)
