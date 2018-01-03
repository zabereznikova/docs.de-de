---
title: '&lt;MethodInstantiation&gt; Element (.NET Native)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c888bf806744c5c62d130ec00b89838c52f67d0a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltmethodinstantiationgt-element-net-native"></a><span data-ttu-id="7b061-102">&lt;MethodInstantiation&gt; Element (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="7b061-102">&lt;MethodInstantiation&gt; Element (.NET Native)</span></span>
<span data-ttu-id="7b061-103">Wendet eine Laufzeitreflektionsrichtlinie auf eine konstruierte generische Methode an.</span><span class="sxs-lookup"><span data-stu-id="7b061-103">Applies runtime reflection policy to a constructed generic method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b061-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b061-104">Syntax</span></span>  
  
```xml  
<MethodInstantiation Name="method_name"  
                     Signature="method_signature"  
                     Arguments="method_arguments"  
                     Browse="policy_type"  
                     Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b061-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7b061-105">Attributes and Elements</span></span>  
 <span data-ttu-id="7b061-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7b061-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b061-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="7b061-107">Attributes</span></span>  
  
|<span data-ttu-id="7b061-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="7b061-108">Attribute</span></span>|<span data-ttu-id="7b061-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="7b061-109">Attribute type</span></span>|<span data-ttu-id="7b061-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b061-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="7b061-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="7b061-111">General</span></span>|<span data-ttu-id="7b061-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="7b061-112">Required attribute.</span></span> <span data-ttu-id="7b061-113">Gibt den Namen der Methode an.</span><span class="sxs-lookup"><span data-stu-id="7b061-113">Specifies the method name.</span></span>|  
|`Signature`|<span data-ttu-id="7b061-114">Allgemein</span><span class="sxs-lookup"><span data-stu-id="7b061-114">General</span></span>|<span data-ttu-id="7b061-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="7b061-115">Optional attribute.</span></span> <span data-ttu-id="7b061-116">Gibt benannte Parameter der Methode an.</span><span class="sxs-lookup"><span data-stu-id="7b061-116">Specifies named parameters of the method.</span></span> <span data-ttu-id="7b061-117">Mehrere benannte Parameter werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="7b061-117">Multiple named parameters are separated by commas.</span></span> <span data-ttu-id="7b061-118">Das `Signature`-Attribut wird dazu verwendet, überladene Methoden zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="7b061-118">The `Signature` attribute is used to differentiate overloaded methods.</span></span>|  
|`Arguments`|<span data-ttu-id="7b061-119">Allgemein</span><span class="sxs-lookup"><span data-stu-id="7b061-119">General</span></span>|<span data-ttu-id="7b061-120">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="7b061-120">Required attribute.</span></span> <span data-ttu-id="7b061-121">Gibt die generischen Typargumente an.</span><span class="sxs-lookup"><span data-stu-id="7b061-121">Specifies the generic type arguments.</span></span> <span data-ttu-id="7b061-122">Wenn mehrere Argumente vorhanden sind, werden sie durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="7b061-122">If multiple arguments are present, they are separated by commas.</span></span>|  
|`Browse`|<span data-ttu-id="7b061-123">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="7b061-123">Reflection</span></span>|<span data-ttu-id="7b061-124">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="7b061-124">Optional attribute.</span></span> <span data-ttu-id="7b061-125">Steuert das Abfragen nach Informationen über eine Methode oder das Auflisten einer Methode, ermöglicht jedoch keinen dynamischen Aufruf zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="7b061-125">Controls querying for information about or enumerating a method but does not enable any dynamic invocation at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="7b061-126">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="7b061-126">Reflection</span></span>|<span data-ttu-id="7b061-127">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="7b061-127">Optional attribute.</span></span> <span data-ttu-id="7b061-128">Steuert den Laufzeitzugriff auf einen Konstruktor oder eine Methode, um die dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="7b061-128">Controls runtime access to a constructor or method to enable dynamic programming.</span></span> <span data-ttu-id="7b061-129">Diese Richtlinie stellt sicher, dass ein Member dynamisch zur Laufzeit aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="7b061-129">This policy ensures that a member can be invoked dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="7b061-130">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="7b061-130">Name attribute</span></span>  
  
|<span data-ttu-id="7b061-131">Wert</span><span class="sxs-lookup"><span data-stu-id="7b061-131">Value</span></span>|<span data-ttu-id="7b061-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b061-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7b061-133">*method_name*</span><span class="sxs-lookup"><span data-stu-id="7b061-133">*method_name*</span></span>|<span data-ttu-id="7b061-134">Der Methodenname.</span><span class="sxs-lookup"><span data-stu-id="7b061-134">The method name.</span></span> <span data-ttu-id="7b061-135">Der Typ der Methode wird durch das übergeordnete Element [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) oder [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) definiert.</span><span class="sxs-lookup"><span data-stu-id="7b061-135">The type of the method is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="signature-attribute"></a><span data-ttu-id="7b061-136">Signature-Attribut</span><span class="sxs-lookup"><span data-stu-id="7b061-136">Signature attribute</span></span>  
  
|<span data-ttu-id="7b061-137">Wert</span><span class="sxs-lookup"><span data-stu-id="7b061-137">Value</span></span>|<span data-ttu-id="7b061-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b061-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7b061-139">*method_signature*</span><span class="sxs-lookup"><span data-stu-id="7b061-139">*method_signature*</span></span>|<span data-ttu-id="7b061-140">Gibt die benannten Parameter der Methode an.</span><span class="sxs-lookup"><span data-stu-id="7b061-140">Specifies the named parameters of the method.</span></span> <span data-ttu-id="7b061-141">Wenn mehrere Parameter vorhanden sind, werden sie durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="7b061-141">If multiple parameters are present, they are separated by commas.</span></span>|  
  
## <a name="arguments-attribute"></a><span data-ttu-id="7b061-142">Arguments-Attribut</span><span class="sxs-lookup"><span data-stu-id="7b061-142">Arguments attribute</span></span>  
  
|<span data-ttu-id="7b061-143">Wert</span><span class="sxs-lookup"><span data-stu-id="7b061-143">Value</span></span>|<span data-ttu-id="7b061-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b061-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7b061-145">*method_arguments*</span><span class="sxs-lookup"><span data-stu-id="7b061-145">*method_arguments*</span></span>|<span data-ttu-id="7b061-146">Gibt die generischen Typargumente an.</span><span class="sxs-lookup"><span data-stu-id="7b061-146">Specifies the generic type arguments.</span></span> <span data-ttu-id="7b061-147">Wenn mehrere Argumente vorhanden sind, werden sie durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="7b061-147">If multiple arguments are present, they are separated by commas.</span></span> <span data-ttu-id="7b061-148">Jedes Argument muss aus dem vollqualifizierten Typnamen bestehen.</span><span class="sxs-lookup"><span data-stu-id="7b061-148">Each argument must consist of the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="7b061-149">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="7b061-149">All other attributes</span></span>  
  
|<span data-ttu-id="7b061-150">Wert</span><span class="sxs-lookup"><span data-stu-id="7b061-150">Value</span></span>|<span data-ttu-id="7b061-151">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b061-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7b061-152">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="7b061-152">*policy_setting*</span></span>|<span data-ttu-id="7b061-153">Die Einstellung, die auf diesen Richtlinientyp für die Methode angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7b061-153">The setting to apply to this policy type for the method.</span></span> <span data-ttu-id="7b061-154">Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`.</span><span class="sxs-lookup"><span data-stu-id="7b061-154">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="7b061-155">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="7b061-155">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7b061-156">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7b061-156">Child Elements</span></span>  
 <span data-ttu-id="7b061-157">Keine</span><span class="sxs-lookup"><span data-stu-id="7b061-157">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7b061-158">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7b061-158">Parent Elements</span></span>  
  
|<span data-ttu-id="7b061-159">Element</span><span class="sxs-lookup"><span data-stu-id="7b061-159">Element</span></span>|<span data-ttu-id="7b061-160">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b061-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7b061-161">\<Type></span><span class="sxs-lookup"><span data-stu-id="7b061-161">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="7b061-162">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="7b061-162">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="7b061-163">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="7b061-163">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="7b061-164">Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="7b061-164">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b061-165">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7b061-165">Remarks</span></span>  
 <span data-ttu-id="7b061-166">Das `<MethodInstantiation>`-Element überschreibt die Laufzeitreflektionsrichtlinie der entsprechenden offenen generischen Methode.</span><span class="sxs-lookup"><span data-stu-id="7b061-166">The `<MethodInstantiation>` element overrides the runtime reflection policy of its corresponding open generic method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b061-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b061-167">See Also</span></span>  
 [<span data-ttu-id="7b061-168">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="7b061-168">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="7b061-169">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="7b061-169">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="7b061-170">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="7b061-170">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)  
 [<span data-ttu-id="7b061-171">\<Method> Element (Element <Method>)</span><span class="sxs-lookup"><span data-stu-id="7b061-171">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)
