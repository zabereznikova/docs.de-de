---
title: <Method> -Element (.net Native)
ms.date: 03/30/2017
ms.assetid: 348b49e5-589d-4eb2-a597-d6ff60ab52d1
ms.openlocfilehash: 1d57457c90e44c70caa301eccc02c5831d283cea
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287903"
---
# <a name="method-element-net-native"></a><span data-ttu-id="40313-102">\<Method> -Element (.net Native)</span><span class="sxs-lookup"><span data-stu-id="40313-102">\<Method> Element (.NET Native)</span></span>

<span data-ttu-id="40313-103">Wendet die Laufzeitreflektionsrichtlinie auf einen Konstruktor oder eine Methode an.</span><span class="sxs-lookup"><span data-stu-id="40313-103">Applies runtime reflection policy to a constructor or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40313-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="40313-104">Syntax</span></span>  
  
```xml  
<Method Name="method_name"  
        Signature="method_signature"  
        Browse="policy_type"  
        Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40313-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="40313-105">Attributes and Elements</span></span>  

 <span data-ttu-id="40313-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="40313-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40313-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="40313-107">Attributes</span></span>  
  
|<span data-ttu-id="40313-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="40313-108">Attribute</span></span>|<span data-ttu-id="40313-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="40313-109">Attribute type</span></span>|<span data-ttu-id="40313-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="40313-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="40313-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="40313-111">General</span></span>|<span data-ttu-id="40313-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="40313-112">Required attribute.</span></span> <span data-ttu-id="40313-113">Gibt den Namen der Methode an.</span><span class="sxs-lookup"><span data-stu-id="40313-113">Specifies the method name.</span></span>|  
|`Signature`|<span data-ttu-id="40313-114">Allgemein</span><span class="sxs-lookup"><span data-stu-id="40313-114">General</span></span>|<span data-ttu-id="40313-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="40313-115">Optional attribute.</span></span> <span data-ttu-id="40313-116">Gibt die Methodensignatur an.</span><span class="sxs-lookup"><span data-stu-id="40313-116">Specifies the method signature.</span></span> <span data-ttu-id="40313-117">Wenn mehrere Parameter vorhanden sind, werden sie durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="40313-117">If multiple parameters are present, they are separated by commas.</span></span> <span data-ttu-id="40313-118">Das folgende `<Method>`-Element definiert beispielsweise die Richtlinie für die <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29>-Methode.</span><span class="sxs-lookup"><span data-stu-id="40313-118">For example, the following `<Method>` element defines policy for the <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29> method.</span></span><br /><br /> `<Type Name="System.DateTime">    <Method Name="ToString" Signature="System.String,System.IFormatProvider"            Dynamic="Required" /> </Type>`<br /><br /> <span data-ttu-id="40313-119">Wenn das Attribut nicht vorhanden ist, gilt die Laufzeitrichtlinie für alle Überladungen der Methode.</span><span class="sxs-lookup"><span data-stu-id="40313-119">If the attribute is absent, the runtime directive applies to all overloads of the method.</span></span>|  
|`Browse`|<span data-ttu-id="40313-120">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="40313-120">Reflection</span></span>|<span data-ttu-id="40313-121">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="40313-121">Optional attribute.</span></span> <span data-ttu-id="40313-122">Steuert das Abfragen nach Informationen über eine Methode oder das Auflisten einer Methode, ermöglicht jedoch keinen dynamischen Aufruf zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="40313-122">Controls querying for information about or enumerating a method but does not enable any dynamic invocation at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="40313-123">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="40313-123">Reflection</span></span>|<span data-ttu-id="40313-124">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="40313-124">Optional attribute.</span></span> <span data-ttu-id="40313-125">Steuert den Laufzeitzugriff auf einen Konstruktor oder eine Methode, um die dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="40313-125">Controls runtime access to a constructor or method to enable dynamic programming.</span></span> <span data-ttu-id="40313-126">Diese Richtlinie stellt sicher, dass ein Member dynamisch zur Laufzeit aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="40313-126">This policy ensures that a member can be invoked dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="40313-127">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="40313-127">Name attribute</span></span>  
  
|<span data-ttu-id="40313-128">Wert</span><span class="sxs-lookup"><span data-stu-id="40313-128">Value</span></span>|<span data-ttu-id="40313-129">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="40313-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="40313-130">*method_name*</span><span class="sxs-lookup"><span data-stu-id="40313-130">*method_name*</span></span>|<span data-ttu-id="40313-131">Der Methodenname.</span><span class="sxs-lookup"><span data-stu-id="40313-131">The method name.</span></span> <span data-ttu-id="40313-132">Der Typ der Methode wird durch das übergeordnete- [\<Type>](type-element-net-native.md) oder- [\<TypeInstantiation>](typeinstantiation-element-net-native.md) Element definiert.</span><span class="sxs-lookup"><span data-stu-id="40313-132">The type of the method is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="signature-attribute"></a><span data-ttu-id="40313-133">Signature-Attribut</span><span class="sxs-lookup"><span data-stu-id="40313-133">Signature attribute</span></span>  
  
|<span data-ttu-id="40313-134">Wert</span><span class="sxs-lookup"><span data-stu-id="40313-134">Value</span></span>|<span data-ttu-id="40313-135">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="40313-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="40313-136">*method_signature*</span><span class="sxs-lookup"><span data-stu-id="40313-136">*method_signature*</span></span>|<span data-ttu-id="40313-137">Die Parametertypen, die die Signatur der Methode bilden.</span><span class="sxs-lookup"><span data-stu-id="40313-137">The parameter types that form the method signature.</span></span> <span data-ttu-id="40313-138">Mehrere Parameter werden durch Kommas getrennt, z. B. `"System.String,System.Int32,System.Int32)"`.</span><span class="sxs-lookup"><span data-stu-id="40313-138">Multiple parameters are separated by commas, for example, `"System.String,System.Int32,System.Int32)"`.</span></span> <span data-ttu-id="40313-139">Parametertypnamen müssen vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="40313-139">Parameter type names should be fully qualified.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="40313-140">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="40313-140">All other attributes</span></span>  
  
|<span data-ttu-id="40313-141">Wert</span><span class="sxs-lookup"><span data-stu-id="40313-141">Value</span></span>|<span data-ttu-id="40313-142">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="40313-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="40313-143">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="40313-143">*policy_setting*</span></span>|<span data-ttu-id="40313-144">Die Einstellung, die auf diesen Richtlinientyp angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="40313-144">The setting to apply to this policy type.</span></span> <span data-ttu-id="40313-145">Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`.</span><span class="sxs-lookup"><span data-stu-id="40313-145">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="40313-146">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="40313-146">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40313-147">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="40313-147">Child Elements</span></span>  
  
|<span data-ttu-id="40313-148">Element</span><span class="sxs-lookup"><span data-stu-id="40313-148">Element</span></span>|<span data-ttu-id="40313-149">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="40313-149">Description</span></span>|  
|-------------|-----------------|  
|[\<Parameter>](parameter-element-net-native.md)|<span data-ttu-id="40313-150">Wendet die Richtlinie auf den Typ des Arguments an, das an eine Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="40313-150">Applies policy to the type of the argument passed to a method.</span></span>|  
|[\<GenericParameter>](genericparameter-element-net-native.md)|<span data-ttu-id="40313-151">Wendet die Richtlinie auf den Parametertyp eines generischen Typs oder einer generischen Methode an.</span><span class="sxs-lookup"><span data-stu-id="40313-151">Applies policy to the parameter type of a generic type or method.</span></span>|  
|[\<ImpliesType>](impliestype-element-net-native.md)|<span data-ttu-id="40313-152">Wendet die Richtlinie auf einen Typ an, wenn diese Richtlinie auf die Methode angewendet wurde, die vom enthaltenden `<Method>`-Element dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="40313-152">Applies policy to a type, if that policy has been applied to the method represented by the containing `<Method>` element.</span></span>|  
|[\<TypeParameter>](typeparameter-element-net-native.md)|<span data-ttu-id="40313-153">Wendet die Richtlinie auf den Typ an, der von einem <xref:System.Type>-Argument dargestellt wird, dass an eine Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="40313-153">Applies policy to the type represented by a <xref:System.Type> argument passed to a method.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="40313-154">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="40313-154">Parent Elements</span></span>  
  
|<span data-ttu-id="40313-155">Element</span><span class="sxs-lookup"><span data-stu-id="40313-155">Element</span></span>|<span data-ttu-id="40313-156">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="40313-156">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="40313-157">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="40313-157">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="40313-158">Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="40313-158">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40313-159">Hinweise</span><span class="sxs-lookup"><span data-stu-id="40313-159">Remarks</span></span>  

 <span data-ttu-id="40313-160">Ein `<Method>`-Element einer generischen Methode wendet seine Richtlinie für alle Instanziierungen an, die keine eigene Richtlinie haben.</span><span class="sxs-lookup"><span data-stu-id="40313-160">A `<Method>` element of a generic method applies its policy to all instantiations that do not have their own policy.</span></span>  
  
 <span data-ttu-id="40313-161">Sie können das `Signature`-Attribut zum Angeben einer Richtlinie für eine bestimmte Methodenüberladung verwenden.</span><span class="sxs-lookup"><span data-stu-id="40313-161">You can use the `Signature` attribute to specify policy for a particular method overload.</span></span> <span data-ttu-id="40313-162">Wenn das `Signature`-Attribut aber nicht vorhanden ist, gilt die Laufzeitrichtlinie für alle Überladungen der Methode.</span><span class="sxs-lookup"><span data-stu-id="40313-162">Otherwise, if the `Signature` attribute is absent, the runtime directive applies to all overloads of the method.</span></span>  
  
 <span data-ttu-id="40313-163">Sie können die Laufzeitreflektionsrichtlinie für einen Konstruktor nicht mit dem `<Method>`-Element definieren.</span><span class="sxs-lookup"><span data-stu-id="40313-163">You cannot define the runtime reflection policy for a constructor by using the `<Method>` element.</span></span> <span data-ttu-id="40313-164">Verwenden Sie stattdessen das-Attribut des-,-,- `Activate`  [\<Assembly>](assembly-element-net-native.md) oder- [\<Namespace>](namespace-element-net-native.md) [\<Type>](type-element-net-native.md) [\<TypeInstantiation>](typeinstantiation-element-net-native.md) Elements.</span><span class="sxs-lookup"><span data-stu-id="40313-164">Instead, use the `Activate` attribute of the  [\<Assembly>](assembly-element-net-native.md), [\<Namespace>](namespace-element-net-native.md), [\<Type>](type-element-net-native.md), or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40313-165">Beispiel</span><span class="sxs-lookup"><span data-stu-id="40313-165">Example</span></span>  

 <span data-ttu-id="40313-166">Die `Stringify`-Methode im folgenden Beispiel ist eine allgemeine Formatierungsmethode, die Reflektion verwendet, um ein Objekt in seine Zeichenfolgendarstellung zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="40313-166">The `Stringify` method in the following example is a general-purpose formatting method that uses reflection to convert an object to its string representation.</span></span> <span data-ttu-id="40313-167">Zusätzlich zum Aufrufen der Standard-`ToString`-Methode des Objekts kann die Methode eine formatierte Ergebniszeichenfolge durch Übergeben der `ToString`-Methode eines Objekts an eine Formatzeichenfolge, eine <xref:System.IFormatProvider>-Implementierung oder beides erzeugen.</span><span class="sxs-lookup"><span data-stu-id="40313-167">In addition to calling the object's default `ToString` method, the method can produce a formatted result string by passing an object's `ToString` method a format string, an <xref:System.IFormatProvider> implementation, or both.</span></span> <span data-ttu-id="40313-168">Sie kann auch eine der <xref:System.Convert.ToString%2A?displayProperty=nameWithType>-Überladungen aufrufen, die eine Zahl in die binäre, oktale oder hexadezimale Zeichenfolgendarstellung konvertiert.</span><span class="sxs-lookup"><span data-stu-id="40313-168">It can also call one of the <xref:System.Convert.ToString%2A?displayProperty=nameWithType> overloads that converts a number to its binary, hexadecimal, or octal representation.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/method1.cs#7)]  
  
 <span data-ttu-id="40313-169">Die `Stringify`-Methode kann durch Code wie dem folgenden aufgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="40313-169">The `Stringify` method can be called by code like the following:</span></span>  
  
 [!code-csharp[ProjectN_Reflection#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/method1.cs#7)]  
  
 <span data-ttu-id="40313-170">Bei der Kompilierung mit .NET Native kann das Beispiel allerdings zur Laufzeit einige Ausnahmen auslösen, einschließlich der <xref:System.NullReferenceException>- und [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md)-Ausnahmen. Dies geschieht, da die `Stringify`-Methode in erster Linie die dynamische Formatierung der primitiven Typen in der Klassenbibliothek von .NET Framework unterstützen soll.</span><span class="sxs-lookup"><span data-stu-id="40313-170">However, when compiled with .NET Native, the example can throw an number of exceptions at runtime, including <xref:System.NullReferenceException> and [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) exceptions, This occurs because the `Stringify` method is intended primarily to support dynamically formatting the primitive types in the .NET Framework Class Library.</span></span> <span data-ttu-id="40313-171">Allerdings werden die Metadaten nicht durch die Standardanweisungsdatei zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="40313-171">However, their metadata is not made available by the default directives file.</span></span> <span data-ttu-id="40313-172">Auch wenn die Metadaten verfügbar gemacht werden, löst das Beispiel [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md)-Ausnahmen aus, da die entsprechenden `ToString`-Implementierungen nicht im nativen Code eingeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="40313-172">Even when their metadata is made available, however, the example throws [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) exceptions because the appropriate `ToString` implementations have not been include in the native code.</span></span>  
  
 <span data-ttu-id="40313-173">Diese Ausnahmen können entfernt werden, indem das- [\<Type>](type-element-net-native.md) Element verwendet wird, um die Typen zu definieren, deren Metadaten vorhanden sein müssen, und durch Hinzufügen von `<Method>` Elementen, um sicherzustellen, dass die Implementierung von Methoden Überladungen, die dynamisch aufgerufen werden können, ebenfalls vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="40313-173">These exceptions can all be eliminated by using the [\<Type>](type-element-net-native.md) element to define the types whose metadata must be present, and by adding `<Method>` elements to ensure that the implementation of method overloads that can be called dynamically is also present.</span></span> <span data-ttu-id="40313-174">So sieht die Datei "default.rd.xml" aus, die diese Ausnahmen eliminiert und die Ausführung des Beispiels ohne Fehler ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="40313-174">The following is the default.rd.xml file that eliminates these exceptions and allows the example to execute without error.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
     <Assembly Name="*Application*" Dynamic="Required All" />  
  
     <Type Name = "System.Convert" Browse="Required Public" Dynamic="Required Public" >  
        <Method Name="ToString"    Dynamic ="Required" />  
     </Type>  
     <Type Name="System.Double" Browse="Required Public">  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Type Name ="System.Int32" Browse="Required Public" >  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Type Name ="System.Int64" Browse="Required Public" >  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Namespace Name="System" >  
        <Type Name="Byte" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="DateTime" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Decimal" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Guid" Browse ="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Int16" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="SByte" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Single" Browse="Required Public" >  
          <Method Name="ToString" Dynamic="Required" />
        </Type>  
        <Type Name="TimeSpan" Browse="Required Public" >  
          <Method Name="ToString" Dynamic="Required" />
        </Type>  
        <Type Name="UInt16" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="UInt32" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="UInt64" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
     </Namespace>  
  </Application>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="40313-175">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="40313-175">See also</span></span>

- [<span data-ttu-id="40313-176">Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz</span><span class="sxs-lookup"><span data-stu-id="40313-176">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="40313-177">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="40313-177">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="40313-178">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="40313-178">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="40313-179">\<MethodInstantiation>-Element</span><span class="sxs-lookup"><span data-stu-id="40313-179">\<MethodInstantiation> Element</span></span>](methodinstantiation-element-net-native.md)
