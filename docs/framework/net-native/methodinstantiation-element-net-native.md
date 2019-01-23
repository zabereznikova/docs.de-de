---
title: '&lt;MethodInstantiation&gt; Element (.NET Native)'
ms.date: 03/30/2017
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2d05f9c727672c4f249e388a32b1101aaafd2f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54538259"
---
# <a name="ltmethodinstantiationgt-element-net-native"></a><span data-ttu-id="b0a35-102">&lt;MethodInstantiation&gt; Element (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="b0a35-102">&lt;MethodInstantiation&gt; Element (.NET Native)</span></span>
<span data-ttu-id="b0a35-103">Wendet eine Laufzeitreflektionsrichtlinie auf eine konstruierte generische Methode an.</span><span class="sxs-lookup"><span data-stu-id="b0a35-103">Applies runtime reflection policy to a constructed generic method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0a35-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b0a35-104">Syntax</span></span>  
  
```xml  
<MethodInstantiation Name="method_name"  
                     Signature="method_signature"  
                     Arguments="method_arguments"  
                     Browse="policy_type"  
                     Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0a35-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b0a35-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b0a35-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b0a35-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0a35-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="b0a35-107">Attributes</span></span>  
  
|<span data-ttu-id="b0a35-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="b0a35-108">Attribute</span></span>|<span data-ttu-id="b0a35-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="b0a35-109">Attribute type</span></span>|<span data-ttu-id="b0a35-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0a35-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="b0a35-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="b0a35-111">General</span></span>|<span data-ttu-id="b0a35-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="b0a35-112">Required attribute.</span></span> <span data-ttu-id="b0a35-113">Gibt den Namen der Methode an.</span><span class="sxs-lookup"><span data-stu-id="b0a35-113">Specifies the method name.</span></span>|  
|`Signature`|<span data-ttu-id="b0a35-114">Allgemein</span><span class="sxs-lookup"><span data-stu-id="b0a35-114">General</span></span>|<span data-ttu-id="b0a35-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b0a35-115">Optional attribute.</span></span> <span data-ttu-id="b0a35-116">Gibt benannte Parameter der Methode an.</span><span class="sxs-lookup"><span data-stu-id="b0a35-116">Specifies named parameters of the method.</span></span> <span data-ttu-id="b0a35-117">Mehrere benannte Parameter werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="b0a35-117">Multiple named parameters are separated by commas.</span></span> <span data-ttu-id="b0a35-118">Das `Signature`-Attribut wird dazu verwendet, überladene Methoden zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="b0a35-118">The `Signature` attribute is used to differentiate overloaded methods.</span></span>|  
|`Arguments`|<span data-ttu-id="b0a35-119">Allgemein</span><span class="sxs-lookup"><span data-stu-id="b0a35-119">General</span></span>|<span data-ttu-id="b0a35-120">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="b0a35-120">Required attribute.</span></span> <span data-ttu-id="b0a35-121">Gibt die generischen Typargumente an.</span><span class="sxs-lookup"><span data-stu-id="b0a35-121">Specifies the generic type arguments.</span></span> <span data-ttu-id="b0a35-122">Wenn mehrere Argumente vorhanden sind, werden sie durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="b0a35-122">If multiple arguments are present, they are separated by commas.</span></span>|  
|`Browse`|<span data-ttu-id="b0a35-123">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="b0a35-123">Reflection</span></span>|<span data-ttu-id="b0a35-124">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b0a35-124">Optional attribute.</span></span> <span data-ttu-id="b0a35-125">Steuert das Abfragen nach Informationen über eine Methode oder das Auflisten einer Methode, ermöglicht jedoch keinen dynamischen Aufruf zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="b0a35-125">Controls querying for information about or enumerating a method but does not enable any dynamic invocation at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="b0a35-126">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="b0a35-126">Reflection</span></span>|<span data-ttu-id="b0a35-127">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b0a35-127">Optional attribute.</span></span> <span data-ttu-id="b0a35-128">Steuert den Laufzeitzugriff auf einen Konstruktor oder eine Methode, um die dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b0a35-128">Controls runtime access to a constructor or method to enable dynamic programming.</span></span> <span data-ttu-id="b0a35-129">Diese Richtlinie stellt sicher, dass ein Member dynamisch zur Laufzeit aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="b0a35-129">This policy ensures that a member can be invoked dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="b0a35-130">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="b0a35-130">Name attribute</span></span>  
  
|<span data-ttu-id="b0a35-131">Wert</span><span class="sxs-lookup"><span data-stu-id="b0a35-131">Value</span></span>|<span data-ttu-id="b0a35-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0a35-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b0a35-133">*method_name*</span><span class="sxs-lookup"><span data-stu-id="b0a35-133">*method_name*</span></span>|<span data-ttu-id="b0a35-134">Der Methodenname.</span><span class="sxs-lookup"><span data-stu-id="b0a35-134">The method name.</span></span> <span data-ttu-id="b0a35-135">Der Typ der Methode wird durch das übergeordnete Element [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) oder [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) definiert.</span><span class="sxs-lookup"><span data-stu-id="b0a35-135">The type of the method is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="signature-attribute"></a><span data-ttu-id="b0a35-136">Signature-Attribut</span><span class="sxs-lookup"><span data-stu-id="b0a35-136">Signature attribute</span></span>  
  
|<span data-ttu-id="b0a35-137">Wert</span><span class="sxs-lookup"><span data-stu-id="b0a35-137">Value</span></span>|<span data-ttu-id="b0a35-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0a35-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b0a35-139">*method_signature*</span><span class="sxs-lookup"><span data-stu-id="b0a35-139">*method_signature*</span></span>|<span data-ttu-id="b0a35-140">Gibt die benannten Parameter der Methode an.</span><span class="sxs-lookup"><span data-stu-id="b0a35-140">Specifies the named parameters of the method.</span></span> <span data-ttu-id="b0a35-141">Wenn mehrere Parameter vorhanden sind, werden sie durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="b0a35-141">If multiple parameters are present, they are separated by commas.</span></span>|  
  
## <a name="arguments-attribute"></a><span data-ttu-id="b0a35-142">Arguments-Attribut</span><span class="sxs-lookup"><span data-stu-id="b0a35-142">Arguments attribute</span></span>  
  
|<span data-ttu-id="b0a35-143">Wert</span><span class="sxs-lookup"><span data-stu-id="b0a35-143">Value</span></span>|<span data-ttu-id="b0a35-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0a35-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b0a35-145">*method_arguments*</span><span class="sxs-lookup"><span data-stu-id="b0a35-145">*method_arguments*</span></span>|<span data-ttu-id="b0a35-146">Gibt die generischen Typargumente an.</span><span class="sxs-lookup"><span data-stu-id="b0a35-146">Specifies the generic type arguments.</span></span> <span data-ttu-id="b0a35-147">Wenn mehrere Argumente vorhanden sind, werden sie durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="b0a35-147">If multiple arguments are present, they are separated by commas.</span></span> <span data-ttu-id="b0a35-148">Jedes Argument muss aus dem vollqualifizierten Typnamen bestehen.</span><span class="sxs-lookup"><span data-stu-id="b0a35-148">Each argument must consist of the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="b0a35-149">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="b0a35-149">All other attributes</span></span>  
  
|<span data-ttu-id="b0a35-150">Wert</span><span class="sxs-lookup"><span data-stu-id="b0a35-150">Value</span></span>|<span data-ttu-id="b0a35-151">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0a35-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b0a35-152">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="b0a35-152">*policy_setting*</span></span>|<span data-ttu-id="b0a35-153">Die Einstellung, die auf diesen Richtlinientyp für die Methode angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b0a35-153">The setting to apply to this policy type for the method.</span></span> <span data-ttu-id="b0a35-154">Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`.</span><span class="sxs-lookup"><span data-stu-id="b0a35-154">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="b0a35-155">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="b0a35-155">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0a35-156">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b0a35-156">Child Elements</span></span>  
 <span data-ttu-id="b0a35-157">Keine</span><span class="sxs-lookup"><span data-stu-id="b0a35-157">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0a35-158">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b0a35-158">Parent Elements</span></span>  
  
|<span data-ttu-id="b0a35-159">Element</span><span class="sxs-lookup"><span data-stu-id="b0a35-159">Element</span></span>|<span data-ttu-id="b0a35-160">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0a35-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0a35-161">\<Type></span><span class="sxs-lookup"><span data-stu-id="b0a35-161">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="b0a35-162">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="b0a35-162">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="b0a35-163">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="b0a35-163">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="b0a35-164">Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="b0a35-164">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0a35-165">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b0a35-165">Remarks</span></span>  
 <span data-ttu-id="b0a35-166">Das `<MethodInstantiation>`-Element überschreibt die Laufzeitreflektionsrichtlinie der entsprechenden offenen generischen Methode.</span><span class="sxs-lookup"><span data-stu-id="b0a35-166">The `<MethodInstantiation>` element overrides the runtime reflection policy of its corresponding open generic method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0a35-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0a35-167">See also</span></span>
- [<span data-ttu-id="b0a35-168">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="b0a35-168">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="b0a35-169">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="b0a35-169">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
- [<span data-ttu-id="b0a35-170">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="b0a35-170">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
- [<span data-ttu-id="b0a35-171">\<Method> Element (Element <Method>)</span><span class="sxs-lookup"><span data-stu-id="b0a35-171">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)
