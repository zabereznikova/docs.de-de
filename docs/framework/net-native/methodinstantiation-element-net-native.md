---
title: <MethodInstantiation>-Element (.net Native)
ms.date: 03/30/2017
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
ms.openlocfilehash: f19bd3c20088431bcbbafac298398b82a664bee9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128324"
---
# <a name="methodinstantiation-element-net-native"></a><span data-ttu-id="4a95a-102">\<MethodInstantiation>-Element (.net Native)</span><span class="sxs-lookup"><span data-stu-id="4a95a-102">\<MethodInstantiation> Element (.NET Native)</span></span>
<span data-ttu-id="4a95a-103">Wendet eine Laufzeitreflektionsrichtlinie auf eine konstruierte generische Methode an.</span><span class="sxs-lookup"><span data-stu-id="4a95a-103">Applies runtime reflection policy to a constructed generic method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a95a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4a95a-104">Syntax</span></span>  
  
```xml  
<MethodInstantiation Name="method_name"  
                     Signature="method_signature"  
                     Arguments="method_arguments"  
                     Browse="policy_type"  
                     Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4a95a-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4a95a-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4a95a-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4a95a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a95a-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="4a95a-107">Attributes</span></span>  
  
|<span data-ttu-id="4a95a-108">attribute</span><span class="sxs-lookup"><span data-stu-id="4a95a-108">Attribute</span></span>|<span data-ttu-id="4a95a-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="4a95a-109">Attribute type</span></span>|<span data-ttu-id="4a95a-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4a95a-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="4a95a-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="4a95a-111">General</span></span>|<span data-ttu-id="4a95a-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="4a95a-112">Required attribute.</span></span> <span data-ttu-id="4a95a-113">Gibt den Namen der Methode an.</span><span class="sxs-lookup"><span data-stu-id="4a95a-113">Specifies the method name.</span></span>|  
|`Signature`|<span data-ttu-id="4a95a-114">Allgemein</span><span class="sxs-lookup"><span data-stu-id="4a95a-114">General</span></span>|<span data-ttu-id="4a95a-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="4a95a-115">Optional attribute.</span></span> <span data-ttu-id="4a95a-116">Gibt benannte Parameter der Methode an.</span><span class="sxs-lookup"><span data-stu-id="4a95a-116">Specifies named parameters of the method.</span></span> <span data-ttu-id="4a95a-117">Mehrere benannte Parameter werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="4a95a-117">Multiple named parameters are separated by commas.</span></span> <span data-ttu-id="4a95a-118">Das `Signature`-Attribut wird dazu verwendet, überladene Methoden zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="4a95a-118">The `Signature` attribute is used to differentiate overloaded methods.</span></span>|  
|`Arguments`|<span data-ttu-id="4a95a-119">Allgemein</span><span class="sxs-lookup"><span data-stu-id="4a95a-119">General</span></span>|<span data-ttu-id="4a95a-120">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="4a95a-120">Required attribute.</span></span> <span data-ttu-id="4a95a-121">Gibt die generischen Typargumente an.</span><span class="sxs-lookup"><span data-stu-id="4a95a-121">Specifies the generic type arguments.</span></span> <span data-ttu-id="4a95a-122">Wenn mehrere Argumente vorhanden sind, werden sie durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="4a95a-122">If multiple arguments are present, they are separated by commas.</span></span>|  
|`Browse`|<span data-ttu-id="4a95a-123">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="4a95a-123">Reflection</span></span>|<span data-ttu-id="4a95a-124">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="4a95a-124">Optional attribute.</span></span> <span data-ttu-id="4a95a-125">Steuert das Abfragen nach Informationen über eine Methode oder das Auflisten einer Methode, ermöglicht jedoch keinen dynamischen Aufruf zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="4a95a-125">Controls querying for information about or enumerating a method but does not enable any dynamic invocation at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="4a95a-126">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="4a95a-126">Reflection</span></span>|<span data-ttu-id="4a95a-127">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="4a95a-127">Optional attribute.</span></span> <span data-ttu-id="4a95a-128">Steuert den Laufzeitzugriff auf einen Konstruktor oder eine Methode, um die dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="4a95a-128">Controls runtime access to a constructor or method to enable dynamic programming.</span></span> <span data-ttu-id="4a95a-129">Diese Richtlinie stellt sicher, dass ein Member dynamisch zur Laufzeit aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="4a95a-129">This policy ensures that a member can be invoked dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="4a95a-130">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="4a95a-130">Name attribute</span></span>  
  
|<span data-ttu-id="4a95a-131">Wert</span><span class="sxs-lookup"><span data-stu-id="4a95a-131">Value</span></span>|<span data-ttu-id="4a95a-132">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4a95a-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4a95a-133">*method_name*</span><span class="sxs-lookup"><span data-stu-id="4a95a-133">*method_name*</span></span>|<span data-ttu-id="4a95a-134">Der Methodenname.</span><span class="sxs-lookup"><span data-stu-id="4a95a-134">The method name.</span></span> <span data-ttu-id="4a95a-135">Der Typ der Methode wird durch das übergeordnete- [\<Type>](type-element-net-native.md) oder- [\<TypeInstantiation>](typeinstantiation-element-net-native.md) Element definiert.</span><span class="sxs-lookup"><span data-stu-id="4a95a-135">The type of the method is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="signature-attribute"></a><span data-ttu-id="4a95a-136">Signature-Attribut</span><span class="sxs-lookup"><span data-stu-id="4a95a-136">Signature attribute</span></span>  
  
|<span data-ttu-id="4a95a-137">Wert</span><span class="sxs-lookup"><span data-stu-id="4a95a-137">Value</span></span>|<span data-ttu-id="4a95a-138">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4a95a-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4a95a-139">*method_signature*</span><span class="sxs-lookup"><span data-stu-id="4a95a-139">*method_signature*</span></span>|<span data-ttu-id="4a95a-140">Gibt die benannten Parameter der Methode an.</span><span class="sxs-lookup"><span data-stu-id="4a95a-140">Specifies the named parameters of the method.</span></span> <span data-ttu-id="4a95a-141">Wenn mehrere Parameter vorhanden sind, werden sie durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="4a95a-141">If multiple parameters are present, they are separated by commas.</span></span>|  
  
## <a name="arguments-attribute"></a><span data-ttu-id="4a95a-142">Arguments-Attribut</span><span class="sxs-lookup"><span data-stu-id="4a95a-142">Arguments attribute</span></span>  
  
|<span data-ttu-id="4a95a-143">Wert</span><span class="sxs-lookup"><span data-stu-id="4a95a-143">Value</span></span>|<span data-ttu-id="4a95a-144">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4a95a-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4a95a-145">*method_arguments*</span><span class="sxs-lookup"><span data-stu-id="4a95a-145">*method_arguments*</span></span>|<span data-ttu-id="4a95a-146">Gibt die generischen Typargumente an.</span><span class="sxs-lookup"><span data-stu-id="4a95a-146">Specifies the generic type arguments.</span></span> <span data-ttu-id="4a95a-147">Wenn mehrere Argumente vorhanden sind, werden sie durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="4a95a-147">If multiple arguments are present, they are separated by commas.</span></span> <span data-ttu-id="4a95a-148">Jedes Argument muss aus dem vollqualifizierten Typnamen bestehen.</span><span class="sxs-lookup"><span data-stu-id="4a95a-148">Each argument must consist of the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="4a95a-149">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="4a95a-149">All other attributes</span></span>  
  
|<span data-ttu-id="4a95a-150">Wert</span><span class="sxs-lookup"><span data-stu-id="4a95a-150">Value</span></span>|<span data-ttu-id="4a95a-151">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4a95a-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4a95a-152">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="4a95a-152">*policy_setting*</span></span>|<span data-ttu-id="4a95a-153">Die Einstellung, die auf diesen Richtlinientyp für die Methode angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4a95a-153">The setting to apply to this policy type for the method.</span></span> <span data-ttu-id="4a95a-154">Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`.</span><span class="sxs-lookup"><span data-stu-id="4a95a-154">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="4a95a-155">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="4a95a-155">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4a95a-156">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4a95a-156">Child Elements</span></span>  
 <span data-ttu-id="4a95a-157">Keine</span><span class="sxs-lookup"><span data-stu-id="4a95a-157">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4a95a-158">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4a95a-158">Parent Elements</span></span>  
  
|<span data-ttu-id="4a95a-159">Element</span><span class="sxs-lookup"><span data-stu-id="4a95a-159">Element</span></span>|<span data-ttu-id="4a95a-160">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4a95a-160">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="4a95a-161">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="4a95a-161">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="4a95a-162">Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="4a95a-162">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a95a-163">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4a95a-163">Remarks</span></span>  
 <span data-ttu-id="4a95a-164">Das `<MethodInstantiation>`-Element überschreibt die Laufzeitreflektionsrichtlinie der entsprechenden offenen generischen Methode.</span><span class="sxs-lookup"><span data-stu-id="4a95a-164">The `<MethodInstantiation>` element overrides the runtime reflection policy of its corresponding open generic method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a95a-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4a95a-165">See also</span></span>

- [<span data-ttu-id="4a95a-166">Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz</span><span class="sxs-lookup"><span data-stu-id="4a95a-166">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="4a95a-167">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="4a95a-167">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="4a95a-168">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="4a95a-168">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="4a95a-169">\<Method>Gewisses</span><span class="sxs-lookup"><span data-stu-id="4a95a-169">\<Method> Element</span></span>](method-element-net-native.md)
