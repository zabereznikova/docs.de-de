---
title: <bypassTrustedAppStrongNames>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
ms.openlocfilehash: 96361a6742d1d2f76cb237344189d3277d7c8069
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73739087"
---
# <a name="bypasstrustedappstrongnames-element"></a><span data-ttu-id="085b7-102">\<bypassTrustedAppStrongNames>-Element</span><span class="sxs-lookup"><span data-stu-id="085b7-102">\<bypassTrustedAppStrongNames> Element</span></span>

<span data-ttu-id="085b7-103">Gibt an, ob die Überprüfung von starken Namen für vollständig vertrauenswürdige Assemblys umgangen werden soll, die in eine vollständige Vertrauenswürdigkeit geladen werden <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="085b7-103">Specifies whether to bypass the validation of strong names on full-trust assemblies that are loaded into a full-trust <xref:System.AppDomain>.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<bypassTrustedAppStrongNames>**

## <a name="syntax"></a><span data-ttu-id="085b7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="085b7-104">Syntax</span></span>

```xml
<bypassTrustedAppStrongNames
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="085b7-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="085b7-105">Attributes and Elements</span></span>

<span data-ttu-id="085b7-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="085b7-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="085b7-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="085b7-107">Attributes</span></span>

|<span data-ttu-id="085b7-108">attribute</span><span class="sxs-lookup"><span data-stu-id="085b7-108">Attribute</span></span>|<span data-ttu-id="085b7-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="085b7-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="085b7-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="085b7-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="085b7-111">Gibt an, ob das Umgehungs Feature aktiviert ist, das das Validieren starker Namen für vollständig vertrauenswürdige Assemblys vermeidet.</span><span class="sxs-lookup"><span data-stu-id="085b7-111">Specifies whether the bypass feature that avoids validating strong names for full-trust assemblies is enabled.</span></span> <span data-ttu-id="085b7-112">Wenn diese Funktion aktiviert ist, werden starke Namen nicht auf Richtigkeit überprüft, wenn die Assembly geladen wird.</span><span class="sxs-lookup"><span data-stu-id="085b7-112">When this feature is enabled, strong names are not validated for correctness when the assembly is loaded.</span></span> <span data-ttu-id="085b7-113">Der Standardwert lautet `true`.</span><span class="sxs-lookup"><span data-stu-id="085b7-113">The default is `true`.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="085b7-114">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="085b7-114">enabled Attribute</span></span>

|<span data-ttu-id="085b7-115">Wert</span><span class="sxs-lookup"><span data-stu-id="085b7-115">Value</span></span>|<span data-ttu-id="085b7-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="085b7-116">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="085b7-117">Signaturen mit starkem Namen für vollständig vertrauenswürdige Assemblys werden nicht überprüft, wenn die Assemblys in eine voll vertrauenswürdige Assembly geladen werden <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="085b7-117">Strong-name signatures on full-trust assemblies are not validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="085b7-118">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="085b7-118">This is the default.</span></span>|
|`false`|<span data-ttu-id="085b7-119">Signaturen mit starkem Namen für vollständig vertrauenswürdige Assemblys werden überprüft, wenn die Assemblys in eine voll vertrauenswürdige Assembly geladen werden <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="085b7-119">Strong-name signatures on full-trust assemblies are validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="085b7-120">Die Signatur des starken Namens wird nur zur Richtigkeit der Signatur geprüft. Er wird nicht mit einem anderen starken Namen für eine Entsprechung verglichen.</span><span class="sxs-lookup"><span data-stu-id="085b7-120">The strong-name signature is checked only for signature correctness; it is not compared to another strong name for a match.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="085b7-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="085b7-121">Child Elements</span></span>

<span data-ttu-id="085b7-122">Keine</span><span class="sxs-lookup"><span data-stu-id="085b7-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="085b7-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="085b7-123">Parent Elements</span></span>

|<span data-ttu-id="085b7-124">Element</span><span class="sxs-lookup"><span data-stu-id="085b7-124">Element</span></span>|<span data-ttu-id="085b7-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="085b7-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="085b7-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="085b7-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="085b7-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="085b7-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="085b7-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="085b7-128">Remarks</span></span>

<span data-ttu-id="085b7-129">Die Strong-Name-Bypass-Funktion vermeidet den Aufwand der Signatur Überprüfung mit starkem Namen für vollständig vertrauenswürdige Assemblys.</span><span class="sxs-lookup"><span data-stu-id="085b7-129">The strong-name bypass feature avoids the overhead of strong-name signature verification of full-trust assemblies.</span></span>

<span data-ttu-id="085b7-130">Das Bypass-Feature gilt für jede Assembly, die mit einem starken Namen signiert ist und die folgenden Eigenschaften aufweist:</span><span class="sxs-lookup"><span data-stu-id="085b7-130">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>

- <span data-ttu-id="085b7-131">Voll vertrauenswürdig ohne den <xref:System.Security.Policy.StrongName> Beweis (z. b `MyComputer` . hat einen Zonen Nachweis).</span><span class="sxs-lookup"><span data-stu-id="085b7-131">Fully trusted without the <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>

- <span data-ttu-id="085b7-132">Geladen in eine voll vertrauenswürdige <xref:System.AppDomain></span><span class="sxs-lookup"><span data-stu-id="085b7-132">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>

- <span data-ttu-id="085b7-133">Geladen von einem Speicherort unter der <xref:System.AppDomainSetup.ApplicationBase%2A>-Eigenschaft von dieser <xref:System.AppDomain></span><span class="sxs-lookup"><span data-stu-id="085b7-133">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>

- <span data-ttu-id="085b7-134">Nicht verzögert signiert</span><span class="sxs-lookup"><span data-stu-id="085b7-134">Not delay-signed.</span></span>

> [!NOTE]
> <span data-ttu-id="085b7-135">Wenn das Umgehungs Feature für alle Anwendungen auf dem Computer mithilfe eines Registrierungsschlüssels ausgeschaltet wurde, hat diese Einstellung keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="085b7-135">If the bypass feature has been turned off for all applications on the computer by using a registry key, this configuration file setting has no effect.</span></span> <span data-ttu-id="085b7-136">Weitere Informationen finden Sie unter Gewusst [wie: Deaktivieren des Strong-Name-Bypass-Features](../../../../standard/assembly/disable-strong-name-bypass-feature.md).</span><span class="sxs-lookup"><span data-stu-id="085b7-136">For more information, see [How to: Disable the Strong-Name Bypass Feature](../../../../standard/assembly/disable-strong-name-bypass-feature.md).</span></span>

## <a name="example"></a><span data-ttu-id="085b7-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="085b7-137">Example</span></span>

<span data-ttu-id="085b7-138">Im folgenden Beispiel wird gezeigt, wie das Verhalten angegeben wird, mit dem die Signatur mit starkem Namen für vollständig vertrauenswürdige Assemblys überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="085b7-138">The following example shows how to specify the behavior that validates the strong-name signature on full-trust assemblies.</span></span>

```xml
<configuration>
   <runtime>
      <bypassTrustedAppStrongNames enabled="false"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="085b7-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="085b7-139">See also</span></span>

- [<span data-ttu-id="085b7-140">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="085b7-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="085b7-141">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="085b7-141">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="085b7-142">How to: Deaktivieren des Features zur Umgehung von starken Namen</span><span class="sxs-lookup"><span data-stu-id="085b7-142">How to: Disable the strong-name bypass feature</span></span>](../../../../standard/assembly/disable-strong-name-bypass-feature.md)
