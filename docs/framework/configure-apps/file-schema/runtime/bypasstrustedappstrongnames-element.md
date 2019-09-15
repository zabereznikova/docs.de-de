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
ms.openlocfilehash: 35b4c6201b5181b8d7241906f60a731e4175d523
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991235"
---
# <a name="bypasstrustedappstrongnames-element"></a><span data-ttu-id="a3fff-102">\<bypassTrustedAppStrongNames>-Element</span><span class="sxs-lookup"><span data-stu-id="a3fff-102">\<bypassTrustedAppStrongNames> Element</span></span>

<span data-ttu-id="a3fff-103">Gibt an, ob die Überprüfung von starken Namen für vollständig vertrauenswürdige Assemblys umgangen werden soll, <xref:System.AppDomain>die in eine vollständige Vertrauenswürdigkeit geladen werden.</span><span class="sxs-lookup"><span data-stu-id="a3fff-103">Specifies whether to bypass the validation of strong names on full-trust assemblies that are loaded into a full-trust <xref:System.AppDomain>.</span></span>

<span data-ttu-id="a3fff-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a3fff-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a3fff-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="a3fff-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="a3fff-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<bypassTrustedAppStrongNames>**</span><span class="sxs-lookup"><span data-stu-id="a3fff-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<bypassTrustedAppStrongNames>**</span></span>

## <a name="syntax"></a><span data-ttu-id="a3fff-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3fff-107">Syntax</span></span>

```xml
<bypassTrustedAppStrongNames
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a3fff-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a3fff-108">Attributes and Elements</span></span>

<span data-ttu-id="a3fff-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a3fff-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a3fff-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="a3fff-110">Attributes</span></span>

|<span data-ttu-id="a3fff-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="a3fff-111">Attribute</span></span>|<span data-ttu-id="a3fff-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3fff-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="a3fff-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="a3fff-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="a3fff-114">Gibt an, ob das Umgehungs Feature aktiviert ist, das das Validieren starker Namen für vollständig vertrauenswürdige Assemblys vermeidet.</span><span class="sxs-lookup"><span data-stu-id="a3fff-114">Specifies whether the bypass feature that avoids validating strong names for full-trust assemblies is enabled.</span></span> <span data-ttu-id="a3fff-115">Wenn diese Funktion aktiviert ist, werden starke Namen nicht auf Richtigkeit überprüft, wenn die Assembly geladen wird.</span><span class="sxs-lookup"><span data-stu-id="a3fff-115">When this feature is enabled, strong names are not validated for correctness when the assembly is loaded.</span></span> <span data-ttu-id="a3fff-116">Die Standardeinstellung ist `true`.</span><span class="sxs-lookup"><span data-stu-id="a3fff-116">The default is `true`.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="a3fff-117">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="a3fff-117">enabled Attribute</span></span>

|<span data-ttu-id="a3fff-118">Wert</span><span class="sxs-lookup"><span data-stu-id="a3fff-118">Value</span></span>|<span data-ttu-id="a3fff-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3fff-119">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="a3fff-120">Signaturen mit starkem Namen für vollständig vertrauenswürdige Assemblys werden nicht überprüft, wenn die Assemblys in <xref:System.AppDomain>eine voll vertrauenswürdige Assembly geladen werden.</span><span class="sxs-lookup"><span data-stu-id="a3fff-120">Strong-name signatures on full-trust assemblies are not validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="a3fff-121">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="a3fff-121">This is the default.</span></span>|
|`false`|<span data-ttu-id="a3fff-122">Signaturen mit starkem Namen für vollständig vertrauenswürdige Assemblys werden überprüft, wenn die Assemblys in <xref:System.AppDomain>eine voll vertrauenswürdige Assembly geladen werden.</span><span class="sxs-lookup"><span data-stu-id="a3fff-122">Strong-name signatures on full-trust assemblies are validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="a3fff-123">Die Signatur des starken Namens wird nur zur Richtigkeit der Signatur geprüft. Er wird nicht mit einem anderen starken Namen für eine Entsprechung verglichen.</span><span class="sxs-lookup"><span data-stu-id="a3fff-123">The strong-name signature is checked only for signature correctness; it is not compared to another strong name for a match.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="a3fff-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a3fff-124">Child Elements</span></span>

<span data-ttu-id="a3fff-125">Keine</span><span class="sxs-lookup"><span data-stu-id="a3fff-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a3fff-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a3fff-126">Parent Elements</span></span>

|<span data-ttu-id="a3fff-127">Element</span><span class="sxs-lookup"><span data-stu-id="a3fff-127">Element</span></span>|<span data-ttu-id="a3fff-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3fff-128">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="a3fff-129">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="a3fff-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="a3fff-130">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a3fff-130">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a3fff-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a3fff-131">Remarks</span></span>

<span data-ttu-id="a3fff-132">Die Strong-Name-Bypass-Funktion vermeidet den Aufwand der Signatur Überprüfung mit starkem Namen für vollständig vertrauenswürdige Assemblys.</span><span class="sxs-lookup"><span data-stu-id="a3fff-132">The strong-name bypass feature avoids the overhead of strong-name signature verification of full-trust assemblies.</span></span>

<span data-ttu-id="a3fff-133">Das Bypass-Feature gilt für jede Assembly, die mit einem starken Namen signiert ist und die folgenden Eigenschaften aufweist:</span><span class="sxs-lookup"><span data-stu-id="a3fff-133">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>

- <span data-ttu-id="a3fff-134">Voll vertrauenswürdig ohne <xref:System.Security.Policy.StrongName> den Beweis (z. b `MyComputer` . hat einen Zonen Nachweis).</span><span class="sxs-lookup"><span data-stu-id="a3fff-134">Fully trusted without the <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>

- <span data-ttu-id="a3fff-135">Geladen in eine voll vertrauenswürdige <xref:System.AppDomain></span><span class="sxs-lookup"><span data-stu-id="a3fff-135">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>

- <span data-ttu-id="a3fff-136">Geladen von einem Speicherort unter der <xref:System.AppDomainSetup.ApplicationBase%2A>-Eigenschaft von dieser <xref:System.AppDomain></span><span class="sxs-lookup"><span data-stu-id="a3fff-136">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>

- <span data-ttu-id="a3fff-137">Nicht verzögert signiert</span><span class="sxs-lookup"><span data-stu-id="a3fff-137">Not delay-signed.</span></span>

> [!NOTE]
> <span data-ttu-id="a3fff-138">Wenn das Umgehungs Feature für alle Anwendungen auf dem Computer mithilfe eines Registrierungsschlüssels ausgeschaltet wurde, hat diese Einstellung keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="a3fff-138">If the bypass feature has been turned off for all applications on the computer by using a registry key, this configuration file setting has no effect.</span></span> <span data-ttu-id="a3fff-139">Weitere Informationen finden Sie unter [Vorgehensweise: Deaktivieren der Strong-Name-Bypass-Funktion](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span><span class="sxs-lookup"><span data-stu-id="a3fff-139">For more information, see [How to: Disable the Strong-Name Bypass Feature](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span></span>

## <a name="example"></a><span data-ttu-id="a3fff-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a3fff-140">Example</span></span>

<span data-ttu-id="a3fff-141">Im folgenden Beispiel wird gezeigt, wie das Verhalten angegeben wird, mit dem die Signatur mit starkem Namen für vollständig vertrauenswürdige Assemblys überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="a3fff-141">The following example shows how to specify the behavior that validates the strong-name signature on full-trust assemblies.</span></span>

```xml
<configuration>
   <runtime>
      <bypassTrustedAppStrongNames enabled="false"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="a3fff-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3fff-142">See also</span></span>

- [<span data-ttu-id="a3fff-143">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="a3fff-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a3fff-144">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="a3fff-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a3fff-145">Vorgehensweise: Deaktivieren des Strong-Name-Bypass-Features</span><span class="sxs-lookup"><span data-stu-id="a3fff-145">How to: Disable the strong-name bypass feature</span></span>](../../../../standard/assembly/disable-strong-name-bypass-feature.md)
