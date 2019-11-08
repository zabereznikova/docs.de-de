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
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739087"
---
# <a name="bypasstrustedappstrongnames-element"></a><span data-ttu-id="434e2-102">\<bypassTrustedAppStrongNames>-Element</span><span class="sxs-lookup"><span data-stu-id="434e2-102">\<bypassTrustedAppStrongNames> Element</span></span>

<span data-ttu-id="434e2-103">Gibt an, ob die Überprüfung von starken Namen für vollständig vertrauenswürdige Assemblys umgangen werden soll, die in eine voll vertrauenswürdige <xref:System.AppDomain>geladen werden.</span><span class="sxs-lookup"><span data-stu-id="434e2-103">Specifies whether to bypass the validation of strong names on full-trust assemblies that are loaded into a full-trust <xref:System.AppDomain>.</span></span>

<span data-ttu-id="434e2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="434e2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="434e2-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="434e2-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="434e2-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<bypasstrustedappstrongnames >**</span><span class="sxs-lookup"><span data-stu-id="434e2-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<bypassTrustedAppStrongNames>**</span></span>

## <a name="syntax"></a><span data-ttu-id="434e2-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="434e2-107">Syntax</span></span>

```xml
<bypassTrustedAppStrongNames
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="434e2-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="434e2-108">Attributes and Elements</span></span>

<span data-ttu-id="434e2-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="434e2-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="434e2-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="434e2-110">Attributes</span></span>

|<span data-ttu-id="434e2-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="434e2-111">Attribute</span></span>|<span data-ttu-id="434e2-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="434e2-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="434e2-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="434e2-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="434e2-114">Gibt an, ob das Umgehungs Feature aktiviert ist, das das Validieren starker Namen für vollständig vertrauenswürdige Assemblys vermeidet.</span><span class="sxs-lookup"><span data-stu-id="434e2-114">Specifies whether the bypass feature that avoids validating strong names for full-trust assemblies is enabled.</span></span> <span data-ttu-id="434e2-115">Wenn diese Funktion aktiviert ist, werden starke Namen nicht auf Richtigkeit überprüft, wenn die Assembly geladen wird.</span><span class="sxs-lookup"><span data-stu-id="434e2-115">When this feature is enabled, strong names are not validated for correctness when the assembly is loaded.</span></span> <span data-ttu-id="434e2-116">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="434e2-116">The default is `true`.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="434e2-117">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="434e2-117">enabled Attribute</span></span>

|<span data-ttu-id="434e2-118">Wert</span><span class="sxs-lookup"><span data-stu-id="434e2-118">Value</span></span>|<span data-ttu-id="434e2-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="434e2-119">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="434e2-120">Signaturen mit starkem Namen für vollständig vertrauenswürdige Assemblys werden nicht überprüft, wenn die Assemblys in eine voll vertrauenswürdige <xref:System.AppDomain>geladen werden.</span><span class="sxs-lookup"><span data-stu-id="434e2-120">Strong-name signatures on full-trust assemblies are not validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="434e2-121">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="434e2-121">This is the default.</span></span>|
|`false`|<span data-ttu-id="434e2-122">Signaturen mit starkem Namen für vollständig vertrauenswürdige Assemblys werden überprüft, wenn die Assemblys in eine voll vertrauenswürdige <xref:System.AppDomain>geladen werden.</span><span class="sxs-lookup"><span data-stu-id="434e2-122">Strong-name signatures on full-trust assemblies are validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="434e2-123">Die Signatur des starken Namens wird nur zur Richtigkeit der Signatur geprüft. Er wird nicht mit einem anderen starken Namen für eine Entsprechung verglichen.</span><span class="sxs-lookup"><span data-stu-id="434e2-123">The strong-name signature is checked only for signature correctness; it is not compared to another strong name for a match.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="434e2-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="434e2-124">Child Elements</span></span>

<span data-ttu-id="434e2-125">Keine</span><span class="sxs-lookup"><span data-stu-id="434e2-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="434e2-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="434e2-126">Parent Elements</span></span>

|<span data-ttu-id="434e2-127">Element</span><span class="sxs-lookup"><span data-stu-id="434e2-127">Element</span></span>|<span data-ttu-id="434e2-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="434e2-128">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="434e2-129">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="434e2-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="434e2-130">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="434e2-130">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="434e2-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="434e2-131">Remarks</span></span>

<span data-ttu-id="434e2-132">Die Strong-Name-Bypass-Funktion vermeidet den Aufwand der Signatur Überprüfung mit starkem Namen für vollständig vertrauenswürdige Assemblys.</span><span class="sxs-lookup"><span data-stu-id="434e2-132">The strong-name bypass feature avoids the overhead of strong-name signature verification of full-trust assemblies.</span></span>

<span data-ttu-id="434e2-133">Das Bypass-Feature gilt für jede Assembly, die mit einem starken Namen signiert ist und die folgenden Eigenschaften aufweist:</span><span class="sxs-lookup"><span data-stu-id="434e2-133">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>

- <span data-ttu-id="434e2-134">Voll vertrauenswürdig ohne den <xref:System.Security.Policy.StrongName> Beweis (z. b. hat `MyComputer` Zonenbeweis).</span><span class="sxs-lookup"><span data-stu-id="434e2-134">Fully trusted without the <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>

- <span data-ttu-id="434e2-135">Geladen in eine voll vertrauenswürdige <xref:System.AppDomain></span><span class="sxs-lookup"><span data-stu-id="434e2-135">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>

- <span data-ttu-id="434e2-136">Geladen von einem Speicherort unter der <xref:System.AppDomainSetup.ApplicationBase%2A>-Eigenschaft von dieser <xref:System.AppDomain></span><span class="sxs-lookup"><span data-stu-id="434e2-136">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>

- <span data-ttu-id="434e2-137">Nicht verzögert signiert</span><span class="sxs-lookup"><span data-stu-id="434e2-137">Not delay-signed.</span></span>

> [!NOTE]
> <span data-ttu-id="434e2-138">Wenn das Umgehungs Feature für alle Anwendungen auf dem Computer mithilfe eines Registrierungsschlüssels ausgeschaltet wurde, hat diese Einstellung keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="434e2-138">If the bypass feature has been turned off for all applications on the computer by using a registry key, this configuration file setting has no effect.</span></span> <span data-ttu-id="434e2-139">Weitere Informationen finden Sie unter Gewusst [wie: Deaktivieren des Strong-Name-Bypass-Features](../../../../standard/assembly/disable-strong-name-bypass-feature.md).</span><span class="sxs-lookup"><span data-stu-id="434e2-139">For more information, see [How to: Disable the Strong-Name Bypass Feature](../../../../standard/assembly/disable-strong-name-bypass-feature.md).</span></span>

## <a name="example"></a><span data-ttu-id="434e2-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="434e2-140">Example</span></span>

<span data-ttu-id="434e2-141">Im folgenden Beispiel wird gezeigt, wie das Verhalten angegeben wird, mit dem die Signatur mit starkem Namen für vollständig vertrauenswürdige Assemblys überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="434e2-141">The following example shows how to specify the behavior that validates the strong-name signature on full-trust assemblies.</span></span>

```xml
<configuration>
   <runtime>
      <bypassTrustedAppStrongNames enabled="false"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="434e2-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="434e2-142">See also</span></span>

- [<span data-ttu-id="434e2-143">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="434e2-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="434e2-144">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="434e2-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="434e2-145">Gewusst wie: Deaktivieren des Strong-Name-Bypass-Features</span><span class="sxs-lookup"><span data-stu-id="434e2-145">How to: Disable the strong-name bypass feature</span></span>](../../../../standard/assembly/disable-strong-name-bypass-feature.md)
