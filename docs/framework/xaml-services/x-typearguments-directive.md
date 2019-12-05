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
ms.openlocfilehash: 2e64c716ee85934bf02c016ee408b8e5f612a819
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837193"
---
# <a name="xtypearguments-directive"></a><span data-ttu-id="b74e2-102">x:TypeArguments-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b74e2-102">x:TypeArguments Directive</span></span>
<span data-ttu-id="b74e2-103">Übergibt einschränkende Typargumente eines generischen an den Konstruktor des generischen Typs.</span><span class="sxs-lookup"><span data-stu-id="b74e2-103">Passes constraining type arguments of a generic to the constructor of the generic type.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="b74e2-104">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="b74e2-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:TypeArguments="typeString" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="b74e2-105">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="b74e2-105">XAML Values</span></span>  
  
|||  
|-|-|  
|`object`|<span data-ttu-id="b74e2-106">Eine Objekt Element Deklaration eines XAML-Typs, der durch einen generischen CLR-Typ unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="b74e2-106">An object element declaration of a XAML type, which is backed by a CLR generic type.</span></span> <span data-ttu-id="b74e2-107">Wenn `object` auf einen XAML-Typ verweist, der nicht aus dem XAML-Standard Namespace besteht, erfordert `object` ein Präfix, um den XAML-Namespace anzugeben, in dem `object` vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b74e2-107">If `object` refers to a XAML type that is not from the default XAML namespace, `object` requires a prefix to indicate the XAML namespace where `object` exists.</span></span>|  
|`typeString`|<span data-ttu-id="b74e2-108">Eine Zeichenfolge, die einen oder mehrere XAML-Typnamen als Zeichen folgen deklariert, die die Typargumente für den generischen CLR-Typ bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b74e2-108">A string that declares one or more XAML type names as strings, which supplies the type arguments for the CLR generic type.</span></span> <span data-ttu-id="b74e2-109">Weitere Informationen zur Syntax finden Sie in den hinweisen.</span><span class="sxs-lookup"><span data-stu-id="b74e2-109">See Remarks for additional syntax notes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b74e2-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b74e2-110">Remarks</span></span>  
 <span data-ttu-id="b74e2-111">In den meisten Fällen werden die XAML-Typen, die in einer `typeString` Zeichenfolge als Informationselement verwendet werden, als Präfix vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="b74e2-111">In most cases, the XAML types that are used as an information item in a `typeString` string are prefixed.</span></span> <span data-ttu-id="b74e2-112">Typische Typen von generischen CLR-Einschränkungen (z. b. <xref:System.Int32> und <xref:System.String>) stammen aus CLR-Basisklassen Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="b74e2-112">Typical types of CLR generic constraints (for example, <xref:System.Int32> and <xref:System.String>) come from CLR base class libraries.</span></span> <span data-ttu-id="b74e2-113">Diese Bibliotheken sind nicht typischen Framework-spezifischen XAML-Standard Namespaces zugeordnet und erfordern daher eine Präfix Zuordnung für die XAML-Verwendung.</span><span class="sxs-lookup"><span data-stu-id="b74e2-113">Those libraries are not mapped to typical framework-specific default XAML namespaces, and therefore, require a prefix mapping for XAML usage.</span></span>  
  
 <span data-ttu-id="b74e2-114">Sie können mehr als einen XAML-Typnamen angeben, indem Sie ein Komma Trennzeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b74e2-114">You can specify more than one XAML type name by using a comma delimiter.</span></span>  
  
 <span data-ttu-id="b74e2-115">Wenn die generischen Einschränkungen selbst generische Typen verwenden, können die Argumente der geschachtelten Einschränkungs Typen in Klammern () enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="b74e2-115">If the generic constraints themselves use generic types, the nested constraint type arguments can be contained by parentheses ().</span></span>  
  
 <span data-ttu-id="b74e2-116">Beachten Sie, dass diese Definition von `x:TypeArguments` für .NET Framework XAML-Dienste und die Verwendung von CLR-Unterstützung spezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="b74e2-116">Note that this definition of `x:TypeArguments` is specific to .NET Framework XAML Services and using CLR backing.</span></span> <span data-ttu-id="b74e2-117">Eine Definition auf Sprachebene finden Sie in [\[MS-XAML\] Abschnitt 5.3.11](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="b74e2-117">A language-level definition can be found in [\[MS-XAML\] Section 5.3.11](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>  
  
## <a name="usage-examples"></a><span data-ttu-id="b74e2-118">Anwendungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="b74e2-118">Usage Examples</span></span>  
 <span data-ttu-id="b74e2-119">Nehmen Sie für diese Beispiele an, dass die folgenden XAML-Namespace Definitionen deklariert sind:</span><span class="sxs-lookup"><span data-stu-id="b74e2-119">For these examples, assume that the following XAML namespace definitions are declared:</span></span>  
  
```xaml  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a><span data-ttu-id="b74e2-120">Liste\<Zeichenfolge ></span><span class="sxs-lookup"><span data-stu-id="b74e2-120">List\<String></span></span>  
 <span data-ttu-id="b74e2-121">`<scg:List x:TypeArguments="sys:String" ...>` instanziiert eine neue <xref:System.Collections.Generic.List%601> mit einem <xref:System.String> Typargument.</span><span class="sxs-lookup"><span data-stu-id="b74e2-121">`<scg:List x:TypeArguments="sys:String" ...>` instantiates a new <xref:System.Collections.Generic.List%601> with a <xref:System.String> type argument.</span></span>  
  
### <a name="dictionarystringstring"></a><span data-ttu-id="b74e2-122">Wörterbuch\<Zeichenfolge, Zeichenfolge ></span><span class="sxs-lookup"><span data-stu-id="b74e2-122">Dictionary\<String,String></span></span>  
 <span data-ttu-id="b74e2-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instanziiert eine neue <xref:System.Collections.Generic.Dictionary%602> mit zwei <xref:System.String> Typargumenten.</span><span class="sxs-lookup"><span data-stu-id="b74e2-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instantiates a new <xref:System.Collections.Generic.Dictionary%602> with two <xref:System.String> type arguments.</span></span>  
  
### <a name="queuekeyvaluepairstringstring"></a><span data-ttu-id="b74e2-124">Queue<KeyValuePair\<String,String>></span><span class="sxs-lookup"><span data-stu-id="b74e2-124">Queue<KeyValuePair\<String,String>></span></span>  
 <span data-ttu-id="b74e2-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instanziiert ein neues <xref:System.Collections.Generic.Queue%601>, das über eine Einschränkung von <xref:System.Collections.Generic.KeyValuePair%602> mit den inneren Einschränkungs Typargumenten <xref:System.String> und <xref:System.String>verfügt.</span><span class="sxs-lookup"><span data-stu-id="b74e2-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instantiates a new <xref:System.Collections.Generic.Queue%601> that has a constraint of <xref:System.Collections.Generic.KeyValuePair%602> with the inner constraint type arguments <xref:System.String> and <xref:System.String>.</span></span>  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a><span data-ttu-id="b74e2-126">XAML 2006 und allgemeine WPF-XAML-Verwendungen</span><span class="sxs-lookup"><span data-stu-id="b74e2-126">XAML 2006 and WPF Generic XAML Usages</span></span>  
 <span data-ttu-id="b74e2-127">Bei der Verwendung von XAML 2006 und XAML, die für WPF-Anwendungen verwendet werden, gibt es die folgenden Einschränkungen für `x:TypeArguments` und generische typverwendungen von XAML im allgemeinen:</span><span class="sxs-lookup"><span data-stu-id="b74e2-127">For XAML 2006 usage, and XAML that is used for WPF applications, the following restrictions exist for `x:TypeArguments` and generic type usages from XAML in general:</span></span>  
  
- <span data-ttu-id="b74e2-128">Nur das Stamm Element einer XAML-Datei kann eine generische XAML-Verwendung unterstützen, die auf einen generischen Typ verweist.</span><span class="sxs-lookup"><span data-stu-id="b74e2-128">Only the root element of a XAML file can support a generic XAML usage that references a generic type.</span></span>  
  
- <span data-ttu-id="b74e2-129">Das root-Element muss einem generischen Typ mit mindestens einem Typargument zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="b74e2-129">The root element must map to a generic type with at least one type argument.</span></span> <span data-ttu-id="b74e2-130">z. B. <xref:System.Windows.Navigation.PageFunction%601>.</span><span class="sxs-lookup"><span data-stu-id="b74e2-130">An example is <xref:System.Windows.Navigation.PageFunction%601>.</span></span> <span data-ttu-id="b74e2-131">Die Seitenfunktionen sind das primäre Szenario für die generische Verwendung von XAML in WPF.</span><span class="sxs-lookup"><span data-stu-id="b74e2-131">The page functions are the primary scenario for XAML generic usage support in WPF.</span></span>  
  
- <span data-ttu-id="b74e2-132">Das Stamm Element-XAML-Objekt Element für das generische muss auch eine partielle Klasse mit `x:Class`deklarieren.</span><span class="sxs-lookup"><span data-stu-id="b74e2-132">The root element XAML object element for the generic must also declare a partial class using `x:Class`.</span></span> <span data-ttu-id="b74e2-133">Dies gilt auch, wenn Sie eine WPF-Buildaktion definieren.</span><span class="sxs-lookup"><span data-stu-id="b74e2-133">This is true even if defining a WPF build action.</span></span>  
  
- <span data-ttu-id="b74e2-134">`x:TypeArguments` kann nicht auf die generischen generischen Einschränkungen verweisen.</span><span class="sxs-lookup"><span data-stu-id="b74e2-134">`x:TypeArguments` cannot reference nested generic constraints.</span></span>  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a><span data-ttu-id="b74e2-135">XAML 2009 oder XAML 2006 ohne WPF 3,0 oder WPF 3,5-Abhängigkeit</span><span class="sxs-lookup"><span data-stu-id="b74e2-135">XAML 2009 or XAML 2006 with No WPF 3.0 or WPF 3.5 Dependency</span></span>  
 <span data-ttu-id="b74e2-136">In .NET Framework XAML-Dienste für XAML 2006 oder XAML 2009 werden die WPF-bezogenen Einschränkungen bei der generischen XAML-Verwendung gelockert.</span><span class="sxs-lookup"><span data-stu-id="b74e2-136">In .NET Framework XAML Services for either XAML 2006 or XAML 2009, the WPF-related restrictions on generic XAML usage are relaxed.</span></span> <span data-ttu-id="b74e2-137">Sie können ein generisches Objekt Element an einer beliebigen Position in XAML-Markup instanziieren, die das Unterstützungs-Typsystem und das Objektmodell unterstützen können.</span><span class="sxs-lookup"><span data-stu-id="b74e2-137">You can instantiate a generic object element at any position in XAML markup that the backing type system and object model can support.</span></span>  
  
 <span data-ttu-id="b74e2-138">Wenn Sie XAML 2009 anstelle der Zuordnung der CLR-Basis Typen zum Abrufen von XAML-Typen für allgemeine sprach primitive verwenden, können Sie [integrierte Typen für allgemeine XAML-sprach primitive](built-in-types-for-common-xaml-language-primitives.md) als Informationselemente in einem `typeString`verwenden.</span><span class="sxs-lookup"><span data-stu-id="b74e2-138">If you use XAML 2009 instead of mapping the CLR base types to obtain XAML types for common language primitives, you can use [Built-in Types for Common XAML Language Primitives](built-in-types-for-common-xaml-language-primitives.md) as information items in a `typeString`.</span></span> <span data-ttu-id="b74e2-139">Sie könnten z. b. Folgendes deklarieren (Präfix Zuordnungen werden nicht angezeigt, aber x ist der XAML-sprach Namespace XAML-Namespace für XAML 2009):</span><span class="sxs-lookup"><span data-stu-id="b74e2-139">For example, you could declare the following (prefix mappings not shown, but x is the XAML language XAML namespace for XAML 2009):</span></span>  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 <span data-ttu-id="b74e2-140">In WPF und beim Ziel .NET Framework 4 können Sie XAML 2009-Funktionen zusammen mit `x:TypeArguments` verwenden, jedoch nur für Loose XAML (XAML, das nicht Markup kompiliert ist).</span><span class="sxs-lookup"><span data-stu-id="b74e2-140">In WPF and when targeting .NET Framework 4, you can use XAML 2009 features together with `x:TypeArguments` but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="b74e2-141">Markupkompilierte XAML für WPF und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht.</span><span class="sxs-lookup"><span data-stu-id="b74e2-141">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span> <span data-ttu-id="b74e2-142">Wenn Sie das XAML-Markup kompilieren müssen, müssen Sie unter den im Abschnitt "generische XAML-Verwendungen von XAML 2006 und WPF" notierten Einschränkungen arbeiten.</span><span class="sxs-lookup"><span data-stu-id="b74e2-142">If you need to markup compile the XAML, you must operate under the restrictions noted in the "XAML 2006 and WPF Generic XAML Usages" section.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b74e2-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b74e2-143">See also</span></span>

- [<span data-ttu-id="b74e2-144">x:Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b74e2-144">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="b74e2-145">x:Type-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="b74e2-145">x:Type Markup Extension</span></span>](x-type-markup-extension.md)
- [<span data-ttu-id="b74e2-146">Integrierte Typen für häufige XAML-Sprachprimitive</span><span class="sxs-lookup"><span data-stu-id="b74e2-146">Built-in Types for Common XAML Language Primitives</span></span>](built-in-types-for-common-xaml-language-primitives.md)
- [<span data-ttu-id="b74e2-147">Generics in XAML</span><span class="sxs-lookup"><span data-stu-id="b74e2-147">Generics in XAML</span></span>](generics-in-xaml.md)
