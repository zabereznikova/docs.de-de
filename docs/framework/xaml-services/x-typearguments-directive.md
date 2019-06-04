---
title: x:TypeArguments-Anweisung
ms.date: 03/30/2017
f1_keywords:
- x:TypeArguments
- xTypeArguments
- TypeArguments
helpviewer_keywords:
- x:TypeArguments attribute [XAML Services]
- TypeArguments attribute in XAML [XAML Services]
- XAML [XAML Services], x:TypeArguments attribute
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
ms.openlocfilehash: 41f29673622fa7918238dd014b97ee3cf0766257
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486204"
---
# <a name="xtypearguments-directive"></a><span data-ttu-id="fcf6e-102">x:TypeArguments-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fcf6e-102">x:TypeArguments Directive</span></span>
<span data-ttu-id="fcf6e-103">Einschränken von übergibt Typargumente eines generischen an den Konstruktor des generischen Typs.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-103">Passes constraining type arguments of a generic to the constructor of the generic type.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="fcf6e-104">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="fcf6e-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:TypeArguments="typeString" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="fcf6e-105">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="fcf6e-105">XAML Values</span></span>  
  
|||  
|-|-|  
|`object`|<span data-ttu-id="fcf6e-106">Ein Object-Element-Deklaration eines XAML-Typs, der von einem generischen CLR-Typ unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-106">An object element declaration of a XAML type, which is backed by a CLR generic type.</span></span> <span data-ttu-id="fcf6e-107">Wenn `object` verweist auf einen XAML-Typ, der nicht aus dem XAML-Standardnamespace ist `object` erfordert ein Präfix an, dass der XAML-Namespace, in denen `object` vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-107">If `object` refers to a XAML type that is not from the default XAML namespace, `object` requires a prefix to indicate the XAML namespace where `object` exists.</span></span>|  
|`typeString`|<span data-ttu-id="fcf6e-108">Eine Zeichenfolge, die eine oder mehrere XAML deklariert Typnamen als Zeichenfolgen, die die Typargumente für den generischen CLR-Typ.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-108">A string that declares one or more XAML type names as strings, which supplies the type arguments for the CLR generic type.</span></span> <span data-ttu-id="fcf6e-109">Anmerkungen zu dieser Version zusätzliche Syntax finden Sie unter "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="fcf6e-109">See Remarks for additional syntax notes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fcf6e-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fcf6e-110">Remarks</span></span>  
 <span data-ttu-id="fcf6e-111">In den meisten Fällen, die XAML-Typen, die verwendet werden, als ein Informationselement in einem `typeString` Zeichenfolge vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-111">In most cases, the XAML types that are used as an information item in a `typeString` string are prefixed.</span></span> <span data-ttu-id="fcf6e-112">Typische Typen von CLR generische Einschränkungen (z. B. <xref:System.Int32> und <xref:System.String>) stammen aus CLR-Basisklassenbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-112">Typical types of CLR generic constraints (for example, <xref:System.Int32> and <xref:System.String>) come from CLR base class libraries.</span></span> <span data-ttu-id="fcf6e-113">Diese Bibliotheken sind nicht zugeordneten typischen frameworkspezifische-standardmäßigen XAML-Namespaces und erfordert daher eine Präfix-Zuordnung für die Verwendung von XAML.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-113">Those libraries are not mapped to typical framework-specific default XAML namespaces, and therefore, require a prefix mapping for XAML usage.</span></span>  
  
 <span data-ttu-id="fcf6e-114">Sie können mehr als eine XAML-Typnamen angeben, durch ein Komma als Trennzeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-114">You can specify more than one XAML type name by using a comma delimiter.</span></span>  
  
 <span data-ttu-id="fcf6e-115">Wenn der generischen Einschränkungen selbst generische Typen verwenden, können die geschachtelte Einschränkung Typargumente durch Klammern () enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-115">If the generic constraints themselves use generic types, the nested constraint type arguments can be contained by parentheses ().</span></span>  
  
 <span data-ttu-id="fcf6e-116">Beachten Sie, dass diese Definition von `x:TypeArguments` bezieht sich auf .NET Framework-XAML-Dienste, und Verwenden von CLR-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-116">Note that this definition of `x:TypeArguments` is specific to .NET Framework XAML Services and using CLR backing.</span></span> <span data-ttu-id="fcf6e-117">Eine Definition auf Sprachebene finden Sie im [ \[MS-XAML-\] Abschnitt 5.3.11](https://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="fcf6e-117">A language-level definition can be found in [\[MS-XAML\] Section 5.3.11](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="usage-examples"></a><span data-ttu-id="fcf6e-118">Beispiele zur Verwendung</span><span class="sxs-lookup"><span data-stu-id="fcf6e-118">Usage Examples</span></span>  
 <span data-ttu-id="fcf6e-119">Diesen Beispielen wird davon ausgegangen Sie, dass die folgenden XAML-Namespacedefinitionen deklariert werden:</span><span class="sxs-lookup"><span data-stu-id="fcf6e-119">For these examples, assume that the following XAML namespace definitions are declared:</span></span>  
  
```  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a><span data-ttu-id="fcf6e-120">List\<String></span><span class="sxs-lookup"><span data-stu-id="fcf6e-120">List\<String></span></span>  
 <span data-ttu-id="fcf6e-121">`<scg:List x:TypeArguments="sys:String" ...>` instanziiert ein neues <xref:System.Collections.Generic.List%601> mit einem <xref:System.String> Typargument.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-121">`<scg:List x:TypeArguments="sys:String" ...>` instantiates a new <xref:System.Collections.Generic.List%601> with a <xref:System.String> type argument.</span></span>  
  
### <a name="dictionarystringstring"></a><span data-ttu-id="fcf6e-122">Dictionary\<String,String></span><span class="sxs-lookup"><span data-stu-id="fcf6e-122">Dictionary\<String,String></span></span>  
 <span data-ttu-id="fcf6e-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instanziiert ein neues <xref:System.Collections.Generic.Dictionary%602> mit zwei <xref:System.String> Typargumente.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instantiates a new <xref:System.Collections.Generic.Dictionary%602> with two <xref:System.String> type arguments.</span></span>  
  
### <a name="queuekeyvaluepairstringstring"></a><span data-ttu-id="fcf6e-124">Queue<KeyValuePair\<String,String>></span><span class="sxs-lookup"><span data-stu-id="fcf6e-124">Queue<KeyValuePair\<String,String>></span></span>  
 <span data-ttu-id="fcf6e-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instanziiert ein neues <xref:System.Collections.Generic.Queue%601> enthält, die die Einschränkung der <xref:System.Collections.Generic.KeyValuePair%602> mit die Typargumente für die interne Einschränkung <xref:System.String> und <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instantiates a new <xref:System.Collections.Generic.Queue%601> that has a constraint of <xref:System.Collections.Generic.KeyValuePair%602> with the inner constraint type arguments <xref:System.String> and <xref:System.String>.</span></span>  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a><span data-ttu-id="fcf6e-126">Generische XAML-Verwendungen von XAML 2006 und WPF</span><span class="sxs-lookup"><span data-stu-id="fcf6e-126">XAML 2006 and WPF Generic XAML Usages</span></span>  
 <span data-ttu-id="fcf6e-127">Für die Verwendung von XAML 2006 und XAML, das für WPF-Anwendungen verwendet wird, der die folgenden Einschränkungen gelten für `x:TypeArguments` und generische Typverwendungen aus XAML im Allgemeinen:</span><span class="sxs-lookup"><span data-stu-id="fcf6e-127">For XAML 2006 usage, and XAML that is used for WPF applications, the following restrictions exist for `x:TypeArguments` and generic type usages from XAML in general:</span></span>  
  
- <span data-ttu-id="fcf6e-128">Nur das Stammelement einer XAML-Datei kann es sich um einen generischen XAML-Verwendung unterstützen, die einen generischen Typ verweist.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-128">Only the root element of a XAML file can support a generic XAML usage that references a generic type.</span></span>  
  
- <span data-ttu-id="fcf6e-129">Das Stammelement muss auf einen generischen Typ mit mindestens einem Typargument zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-129">The root element must map to a generic type with at least one type argument.</span></span> <span data-ttu-id="fcf6e-130">Ein Beispiel hierfür ist <xref:System.Windows.Navigation.PageFunction%601>.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-130">An example is <xref:System.Windows.Navigation.PageFunction%601>.</span></span> <span data-ttu-id="fcf6e-131">Die Seitenfunktionen sind das primäre Szenario für die generischen Verwendung-Unterstützung in WPF-XAML.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-131">The page functions are the primary scenario for XAML generic usage support in WPF.</span></span>  
  
- <span data-ttu-id="fcf6e-132">Außerdem muss das Stammelement Element XAML-Objektelement für das generische deklariert eine partielle Klasse mit `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-132">The root element XAML object element for the generic must also declare a partial class using `x:Class`.</span></span> <span data-ttu-id="fcf6e-133">Dies gilt auch, wenn Definieren eines WPF-Buildvorgang.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-133">This is true even if defining a WPF build action.</span></span>  
  
- <span data-ttu-id="fcf6e-134">`x:TypeArguments` Geschachtelte generische Einschränkungen kann nicht verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-134">`x:TypeArguments` cannot reference nested generic constraints.</span></span>  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a><span data-ttu-id="fcf6e-135">XAML 2009 oder XAML 2006 ohne WPF 3.0 oder WPF 3.5 Abhängigkeit</span><span class="sxs-lookup"><span data-stu-id="fcf6e-135">XAML 2009 or XAML 2006 with No WPF 3.0 or WPF 3.5 Dependency</span></span>  
 <span data-ttu-id="fcf6e-136">In .NET Framework-XAML-Dienste für XAML 2006 oder XAML 2009 sind die WPF-bezogene Einschränkungen für generische XAML-Verwendung gelockert.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-136">In .NET Framework XAML Services for either XAML 2006 or XAML 2009, the WPF-related restrictions on generic XAML usage are relaxed.</span></span> <span data-ttu-id="fcf6e-137">Sie können ein generisches Objektelement an einer beliebigen Position im XAML-Markup instanziieren, die das dahinter liegende Typ und dem Objektmodell unterstützen kann.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-137">You can instantiate a generic object element at any position in XAML markup that the backing type system and object model can support.</span></span>  
  
 <span data-ttu-id="fcf6e-138">Wenn Sie XAML 2009 verwenden anstelle von mapping des CLR-Basistypen zum Abrufen von XAML-Typen für häufige Sprachprimitive, können Sie [integrierte Typen für häufige XAML-Sprachprimitive](built-in-types-for-common-xaml-language-primitives.md) als Informationselemente in eine `typeString`.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-138">If you use XAML 2009 instead of mapping the CLR base types to obtain XAML types for common language primitives, you can use [Built-in Types for Common XAML Language Primitives](built-in-types-for-common-xaml-language-primitives.md) as information items in a `typeString`.</span></span> <span data-ttu-id="fcf6e-139">Sie können z. B. die folgenden deklarieren (Präfix-Zuordnungen, die nicht angezeigt, aber x ist der XAML-Sprachnamespace XAML für XAML 2009):</span><span class="sxs-lookup"><span data-stu-id="fcf6e-139">For example, you could declare the following (prefix mappings not shown, but x is the XAML language XAML namespace for XAML 2009):</span></span>  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 <span data-ttu-id="fcf6e-140">In WPF und .NET Framework 4 abzielen, können Sie XAML 2009-Funktionen zusammen mit `x:TypeArguments` jedoch nur für loose XAML (XAML, das nicht markupkompiliert ist).</span><span class="sxs-lookup"><span data-stu-id="fcf6e-140">In WPF and when targeting .NET Framework 4, you can use XAML 2009 features together with `x:TypeArguments` but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="fcf6e-141">Markupkompilierte XAML für WPF und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-141">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span> <span data-ttu-id="fcf6e-142">Wenn Sie in Markup der XAML kompilieren müssen, müssen Sie unter den Einschränkungen, die im Abschnitt "XAML 2006 und WPF-generische XAML-Verwendungen" erwähnt ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fcf6e-142">If you need to markup compile the XAML, you must operate under the restrictions noted in the "XAML 2006 and WPF Generic XAML Usages" section.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcf6e-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fcf6e-143">See also</span></span>

- [<span data-ttu-id="fcf6e-144">x:Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fcf6e-144">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="fcf6e-145">x:Type-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="fcf6e-145">x:Type Markup Extension</span></span>](x-type-markup-extension.md)
- [<span data-ttu-id="fcf6e-146">Integrierte Typen für häufige XAML-Sprachprimitive</span><span class="sxs-lookup"><span data-stu-id="fcf6e-146">Built-in Types for Common XAML Language Primitives</span></span>](built-in-types-for-common-xaml-language-primitives.md)
- [<span data-ttu-id="fcf6e-147">Generics in XAML</span><span class="sxs-lookup"><span data-stu-id="fcf6e-147">Generics in XAML</span></span>](generics-in-xaml.md)
