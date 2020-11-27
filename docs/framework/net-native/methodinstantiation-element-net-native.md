---
title: <MethodInstantiation> -Element (.net Native)
ms.date: 03/30/2017
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
ms.openlocfilehash: e247db05f8442d4fcfddbf03b5eb8955b8ff425a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250956"
---
# <a name="methodinstantiation-element-net-native"></a><span data-ttu-id="94d61-102">\<MethodInstantiation> -Element (.net Native)</span><span class="sxs-lookup"><span data-stu-id="94d61-102">\<MethodInstantiation> Element (.NET Native)</span></span>

<span data-ttu-id="94d61-103">Wendet eine Laufzeitreflektionsrichtlinie auf eine konstruierte generische Methode an.</span><span class="sxs-lookup"><span data-stu-id="94d61-103">Applies runtime reflection policy to a constructed generic method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94d61-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="94d61-104">Syntax</span></span>  
  
```xml  
<MethodInstantiation Name="method_name"  
                     Signature="method_signature"  
                     Arguments="method_arguments"  
                     Browse="policy_type"  
                     Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="94d61-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="94d61-105">Attributes and Elements</span></span>  

 <span data-ttu-id="94d61-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="94d61-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="94d61-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="94d61-107">Attributes</span></span>  
  
|<span data-ttu-id="94d61-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="94d61-108">Attribute</span></span>|<span data-ttu-id="94d61-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="94d61-109">Attribute type</span></span>|<span data-ttu-id="94d61-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="94d61-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="94d61-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="94d61-111">General</span></span>|<span data-ttu-id="94d61-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="94d61-112">Required attribute.</span></span> <span data-ttu-id="94d61-113">Gibt den Namen der Methode an.</span><span class="sxs-lookup"><span data-stu-id="94d61-113">Specifies the method name.</span></span>|  
|`Signature`|<span data-ttu-id="94d61-114">Allgemein</span><span class="sxs-lookup"><span data-stu-id="94d61-114">General</span></span>|<span data-ttu-id="94d61-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="94d61-115">Optional attribute.</span></span> <span data-ttu-id="94d61-116">Gibt benannte Parameter der Methode an.</span><span class="sxs-lookup"><span data-stu-id="94d61-116">Specifies named parameters of the method.</span></span> <span data-ttu-id="94d61-117">Mehrere benannte Parameter werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="94d61-117">Multiple named parameters are separated by commas.</span></span> <span data-ttu-id="94d61-118">Das `Signature`-Attribut wird dazu verwendet, überladene Methoden zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="94d61-118">The `Signature` attribute is used to differentiate overloaded methods.</span></span>|  
|`Arguments`|<span data-ttu-id="94d61-119">Allgemein</span><span class="sxs-lookup"><span data-stu-id="94d61-119">General</span></span>|<span data-ttu-id="94d61-120">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="94d61-120">Required attribute.</span></span> <span data-ttu-id="94d61-121">Gibt die generischen Typargumente an.</span><span class="sxs-lookup"><span data-stu-id="94d61-121">Specifies the generic type arguments.</span></span> <span data-ttu-id="94d61-122">Wenn mehrere Argumente vorhanden sind, werden sie durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="94d61-122">If multiple arguments are present, they are separated by commas.</span></span>|  
|`Browse`|<span data-ttu-id="94d61-123">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="94d61-123">Reflection</span></span>|<span data-ttu-id="94d61-124">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="94d61-124">Optional attribute.</span></span> <span data-ttu-id="94d61-125">Steuert das Abfragen nach Informationen über eine Methode oder das Auflisten einer Methode, ermöglicht jedoch keinen dynamischen Aufruf zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="94d61-125">Controls querying for information about or enumerating a method but does not enable any dynamic invocation at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="94d61-126">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="94d61-126">Reflection</span></span>|<span data-ttu-id="94d61-127">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="94d61-127">Optional attribute.</span></span> <span data-ttu-id="94d61-128">Steuert den Laufzeitzugriff auf einen Konstruktor oder eine Methode, um die dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="94d61-128">Controls runtime access to a constructor or method to enable dynamic programming.</span></span> <span data-ttu-id="94d61-129">Diese Richtlinie stellt sicher, dass ein Member dynamisch zur Laufzeit aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="94d61-129">This policy ensures that a member can be invoked dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="94d61-130">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="94d61-130">Name attribute</span></span>  
  
|<span data-ttu-id="94d61-131">Wert</span><span class="sxs-lookup"><span data-stu-id="94d61-131">Value</span></span>|<span data-ttu-id="94d61-132">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="94d61-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="94d61-133">*method_name*</span><span class="sxs-lookup"><span data-stu-id="94d61-133">*method_name*</span></span>|<span data-ttu-id="94d61-134">Der Methodenname.</span><span class="sxs-lookup"><span data-stu-id="94d61-134">The method name.</span></span> <span data-ttu-id="94d61-135">Der Typ der Methode wird durch das übergeordnete- [\<Type>](type-element-net-native.md) oder- [\<TypeInstantiation>](typeinstantiation-element-net-native.md) Element definiert.</span><span class="sxs-lookup"><span data-stu-id="94d61-135">The type of the method is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="signature-attribute"></a><span data-ttu-id="94d61-136">Signature-Attribut</span><span class="sxs-lookup"><span data-stu-id="94d61-136">Signature attribute</span></span>  
  
|<span data-ttu-id="94d61-137">Wert</span><span class="sxs-lookup"><span data-stu-id="94d61-137">Value</span></span>|<span data-ttu-id="94d61-138">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="94d61-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="94d61-139">*method_signature*</span><span class="sxs-lookup"><span data-stu-id="94d61-139">*method_signature*</span></span>|<span data-ttu-id="94d61-140">Gibt die benannten Parameter der Methode an.</span><span class="sxs-lookup"><span data-stu-id="94d61-140">Specifies the named parameters of the method.</span></span> <span data-ttu-id="94d61-141">Wenn mehrere Parameter vorhanden sind, werden sie durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="94d61-141">If multiple parameters are present, they are separated by commas.</span></span>|  
  
## <a name="arguments-attribute"></a><span data-ttu-id="94d61-142">Arguments-Attribut</span><span class="sxs-lookup"><span data-stu-id="94d61-142">Arguments attribute</span></span>  
  
|<span data-ttu-id="94d61-143">Wert</span><span class="sxs-lookup"><span data-stu-id="94d61-143">Value</span></span>|<span data-ttu-id="94d61-144">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="94d61-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="94d61-145">*method_arguments*</span><span class="sxs-lookup"><span data-stu-id="94d61-145">*method_arguments*</span></span>|<span data-ttu-id="94d61-146">Gibt die generischen Typargumente an.</span><span class="sxs-lookup"><span data-stu-id="94d61-146">Specifies the generic type arguments.</span></span> <span data-ttu-id="94d61-147">Wenn mehrere Argumente vorhanden sind, werden sie durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="94d61-147">If multiple arguments are present, they are separated by commas.</span></span> <span data-ttu-id="94d61-148">Jedes Argument muss aus dem vollqualifizierten Typnamen bestehen.</span><span class="sxs-lookup"><span data-stu-id="94d61-148">Each argument must consist of the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="94d61-149">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="94d61-149">All other attributes</span></span>  
  
|<span data-ttu-id="94d61-150">Wert</span><span class="sxs-lookup"><span data-stu-id="94d61-150">Value</span></span>|<span data-ttu-id="94d61-151">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="94d61-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="94d61-152">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="94d61-152">*policy_setting*</span></span>|<span data-ttu-id="94d61-153">Die Einstellung, die auf diesen Richtlinientyp für die Methode angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="94d61-153">The setting to apply to this policy type for the method.</span></span> <span data-ttu-id="94d61-154">Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`.</span><span class="sxs-lookup"><span data-stu-id="94d61-154">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="94d61-155">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="94d61-155">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="94d61-156">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="94d61-156">Child Elements</span></span>  

 <span data-ttu-id="94d61-157">Keine</span><span class="sxs-lookup"><span data-stu-id="94d61-157">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="94d61-158">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="94d61-158">Parent Elements</span></span>  
  
|<span data-ttu-id="94d61-159">Element</span><span class="sxs-lookup"><span data-stu-id="94d61-159">Element</span></span>|<span data-ttu-id="94d61-160">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="94d61-160">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="94d61-161">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="94d61-161">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="94d61-162">Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="94d61-162">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94d61-163">Hinweise</span><span class="sxs-lookup"><span data-stu-id="94d61-163">Remarks</span></span>  

 <span data-ttu-id="94d61-164">Das `<MethodInstantiation>`-Element überschreibt die Laufzeitreflektionsrichtlinie der entsprechenden offenen generischen Methode.</span><span class="sxs-lookup"><span data-stu-id="94d61-164">The `<MethodInstantiation>` element overrides the runtime reflection policy of its corresponding open generic method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94d61-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="94d61-165">See also</span></span>

- [<span data-ttu-id="94d61-166">Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz</span><span class="sxs-lookup"><span data-stu-id="94d61-166">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="94d61-167">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="94d61-167">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="94d61-168">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="94d61-168">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="94d61-169">\<Method>-Element</span><span class="sxs-lookup"><span data-stu-id="94d61-169">\<Method> Element</span></span>](method-element-net-native.md)
