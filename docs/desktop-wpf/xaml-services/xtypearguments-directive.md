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
ms.openlocfilehash: 69da9329f140121b66c71d4cf2e99e9d14a1b207
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432629"
---
# <a name="xtypearguments-directive"></a><span data-ttu-id="ed174-102">x:TypeArguments-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ed174-102">x:TypeArguments Directive</span></span>

<span data-ttu-id="ed174-103">Übergibt einschränkende Typargumente eines generischen Typs an den Konstruktor des generischen Typs.</span><span class="sxs-lookup"><span data-stu-id="ed174-103">Passes constraining type arguments of a generic to the constructor of the generic type.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="ed174-104">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="ed174-104">XAML Attribute Usage</span></span>

```xaml
<object x:TypeArguments="typeString" .../>
```

## <a name="xaml-values"></a><span data-ttu-id="ed174-105">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="ed174-105">XAML Values</span></span>

|||
|-|-|
|`object`|<span data-ttu-id="ed174-106">Eine Objektelementdeklaration eines XAML-Typs, die von einem generischen CLR-Typ unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="ed174-106">An object element declaration of a XAML type, which is backed by a CLR generic type.</span></span> <span data-ttu-id="ed174-107">Wenn `object` auf einen XAML-Typ verweist, der nicht aus `object` dem Standardmäßigen XAML-Namespace `object` stammt, ist ein Präfix erforderlich, um den XAML-Namespace anzugeben, wo vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ed174-107">If `object` refers to a XAML type that is not from the default XAML namespace, `object` requires a prefix to indicate the XAML namespace where `object` exists.</span></span>|
|`typeString`|<span data-ttu-id="ed174-108">Eine Zeichenfolge, die einen oder mehrere XAML-Typnamen als Zeichenfolgen deklariert, die die Typargumente für den generischen CLR-Typ bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ed174-108">A string that declares one or more XAML type names as strings, which supplies the type arguments for the CLR generic type.</span></span> <span data-ttu-id="ed174-109">Weitere Syntaxhinweise finden Sie unter Anmerkungen.</span><span class="sxs-lookup"><span data-stu-id="ed174-109">See Remarks for additional syntax notes.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ed174-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ed174-110">Remarks</span></span>

<span data-ttu-id="ed174-111">In den meisten Fällen werden den XAML-Typen, `typeString` die als Informationselement in einer Zeichenfolge verwendet werden, vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="ed174-111">In most cases, the XAML types that are used as an information item in a `typeString` string are prefixed.</span></span> <span data-ttu-id="ed174-112">Typische Typen generischer CLR-Einschränkungen <xref:System.Int32> (z. B. und <xref:System.String>) stammen aus CLR-Basisklassenbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="ed174-112">Typical types of CLR generic constraints (for example, <xref:System.Int32> and <xref:System.String>) come from CLR base class libraries.</span></span> <span data-ttu-id="ed174-113">Diese Bibliotheken sind nicht typischen frameworkspezifischen XAML-Standard-XAML-Namespaces zugeordnet und erfordern daher eine Präfixzuordnung für die XAML-Verwendung.</span><span class="sxs-lookup"><span data-stu-id="ed174-113">Those libraries are not mapped to typical framework-specific default XAML namespaces, and therefore, require a prefix mapping for XAML usage.</span></span>

<span data-ttu-id="ed174-114">Sie können mehr als einen XAML-Typnamen angeben, indem Sie ein Kommatrennzeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="ed174-114">You can specify more than one XAML type name by using a comma delimiter.</span></span>

<span data-ttu-id="ed174-115">Wenn die generischen Einschränkungen selbst generische Typen verwenden, können die geschachtelten Einschränkungstypargumente in Klammern () enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="ed174-115">If the generic constraints themselves use generic types, the nested constraint type arguments can be contained by parentheses ().</span></span>

<span data-ttu-id="ed174-116">Beachten Sie, `x:TypeArguments` dass diese Definition für .NET XAML-Dienste und die Verwendung von CLR-Unterstützung spezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="ed174-116">Note that this definition of `x:TypeArguments` is specific to .NET XAML Services and using CLR backing.</span></span> <span data-ttu-id="ed174-117">Eine Definition auf Sprachebene finden Sie in [ \[MS-XAML\] Abschnitt 5.3.11](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="ed174-117">A language-level definition can be found in [\[MS-XAML\] Section 5.3.11](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

## <a name="usage-examples"></a><span data-ttu-id="ed174-118">Anwendungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="ed174-118">Usage Examples</span></span>

<span data-ttu-id="ed174-119">In diesen Beispielen wird davon ausgegangen, dass die folgenden XAML-Namespacedefinitionen deklariert werden:</span><span class="sxs-lookup"><span data-stu-id="ed174-119">For these examples, assume that the following XAML namespace definitions are declared:</span></span>

```xaml
xmlns:sys="clr-namespace:System;assembly=mscorlib"
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"
```

### <a name="liststring"></a><span data-ttu-id="ed174-120">Listenzeichenfolge\<></span><span class="sxs-lookup"><span data-stu-id="ed174-120">List\<String></span></span>

<span data-ttu-id="ed174-121">`<scg:List x:TypeArguments="sys:String" ...>`instanziiert ein <xref:System.Collections.Generic.List%601> neues <xref:System.String> mit einem Typargument.</span><span class="sxs-lookup"><span data-stu-id="ed174-121">`<scg:List x:TypeArguments="sys:String" ...>` instantiates a new <xref:System.Collections.Generic.List%601> with a <xref:System.String> type argument.</span></span>

### <a name="dictionarystringstring"></a><span data-ttu-id="ed174-122">Wörterbuch-String,\<String-></span><span class="sxs-lookup"><span data-stu-id="ed174-122">Dictionary\<String,String></span></span>

<span data-ttu-id="ed174-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>`instanziiert ein <xref:System.Collections.Generic.Dictionary%602> neues <xref:System.String> mit zwei Typargumenten.</span><span class="sxs-lookup"><span data-stu-id="ed174-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instantiates a new <xref:System.Collections.Generic.Dictionary%602> with two <xref:System.String> type arguments.</span></span>

### <a name="queuekeyvaluepairstringstring"></a><span data-ttu-id="ed174-124">Warteschlange<KeyValuePair\<String, String>></span><span class="sxs-lookup"><span data-stu-id="ed174-124">Queue<KeyValuePair\<String,String>></span></span>

<span data-ttu-id="ed174-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>`instanziiert eine <xref:System.Collections.Generic.Queue%601> neue, die <xref:System.Collections.Generic.KeyValuePair%602> eine Einschränkung von <xref:System.String> mit <xref:System.String>den inneren Einschränkungstypargumenten und hat.</span><span class="sxs-lookup"><span data-stu-id="ed174-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instantiates a new <xref:System.Collections.Generic.Queue%601> that has a constraint of <xref:System.Collections.Generic.KeyValuePair%602> with the inner constraint type arguments <xref:System.String> and <xref:System.String>.</span></span>

## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a><span data-ttu-id="ed174-126">XAML 2006 und WPF Generische XAML-Verwendungen</span><span class="sxs-lookup"><span data-stu-id="ed174-126">XAML 2006 and WPF Generic XAML Usages</span></span>

<span data-ttu-id="ed174-127">Für die XAML 2006-Verwendung und XAML, die für WPF-Anwendungen verwendet wird, gelten die folgenden Einschränkungen für `x:TypeArguments` und generische Typverwendungen aus XAML im Allgemeinen:</span><span class="sxs-lookup"><span data-stu-id="ed174-127">For XAML 2006 usage, and XAML that is used for WPF applications, the following restrictions exist for `x:TypeArguments` and generic type usages from XAML in general:</span></span>

- <span data-ttu-id="ed174-128">Nur das Stammelement einer XAML-Datei kann eine generische XAML-Verwendung unterstützen, die auf einen generischen Typ verweist.</span><span class="sxs-lookup"><span data-stu-id="ed174-128">Only the root element of a XAML file can support a generic XAML usage that references a generic type.</span></span>

- <span data-ttu-id="ed174-129">Das Root-Element muss einem generischen Typ mit mindestens einem Typargument zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="ed174-129">The root element must map to a generic type with at least one type argument.</span></span> <span data-ttu-id="ed174-130">z. B. <xref:System.Windows.Navigation.PageFunction%601>.</span><span class="sxs-lookup"><span data-stu-id="ed174-130">An example is <xref:System.Windows.Navigation.PageFunction%601>.</span></span> <span data-ttu-id="ed174-131">Die Seitenfunktionen sind das primäre Szenario für die allgemeine XAML-Nutzungsunterstützung in WPF.</span><span class="sxs-lookup"><span data-stu-id="ed174-131">The page functions are the primary scenario for XAML generic usage support in WPF.</span></span>

- <span data-ttu-id="ed174-132">Das Stammelement XAML-Objektelement für das generische `x:Class`Element muss auch eine partielle Klasse mit deklarieren.</span><span class="sxs-lookup"><span data-stu-id="ed174-132">The root element XAML object element for the generic must also declare a partial class using `x:Class`.</span></span> <span data-ttu-id="ed174-133">Dies gilt auch dann, wenn Sie eine WPF-Buildaktion definieren.</span><span class="sxs-lookup"><span data-stu-id="ed174-133">This is true even if defining a WPF build action.</span></span>

- <span data-ttu-id="ed174-134">`x:TypeArguments`nicht auf geschachtelte generische Einschränkungen verweisen.</span><span class="sxs-lookup"><span data-stu-id="ed174-134">`x:TypeArguments` cannot reference nested generic constraints.</span></span>

## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a><span data-ttu-id="ed174-135">XAML 2009 oder XAML 2006 ohne WPF 3.0 oder WPF 3.5 Abhängigkeit</span><span class="sxs-lookup"><span data-stu-id="ed174-135">XAML 2009 or XAML 2006 with No WPF 3.0 or WPF 3.5 Dependency</span></span>

<span data-ttu-id="ed174-136">In .NET XAML-Diensten für XAML 2006 oder XAML 2009 werden die WPF-bezogenen Einschränkungen für die generische XAML-Nutzung gelockert.</span><span class="sxs-lookup"><span data-stu-id="ed174-136">In .NET XAML Services for either XAML 2006 or XAML 2009, the WPF-related restrictions on generic XAML usage are relaxed.</span></span> <span data-ttu-id="ed174-137">Sie können ein generisches Objektelement an jeder beliebigen Position im XAML-Markup instanziieren, das das Sicherungstypsystem und das Objektmodell unterstützen können.</span><span class="sxs-lookup"><span data-stu-id="ed174-137">You can instantiate a generic object element at any position in XAML markup that the backing type system and object model can support.</span></span>

<span data-ttu-id="ed174-138">Wenn Sie XAML 2009 verwenden, anstatt die CLR-Basistypen zuzuordnen, um XAML-Typen für primitive Benutzerfürsprachen zu erhalten, `typeString`können Sie integrierte Typen für allgemeine [XAML-Sprachprimitive](types-for-primitives.md) als Informationselemente in einem verwenden.</span><span class="sxs-lookup"><span data-stu-id="ed174-138">If you use XAML 2009 instead of mapping the CLR base types to obtain XAML types for common language primitives, you can use [Built-in Types for Common XAML Language Primitives](types-for-primitives.md) as information items in a `typeString`.</span></span> <span data-ttu-id="ed174-139">Sie können z. B. Folgendes deklarieren (Präfixzuordnungen werden nicht angezeigt, aber x ist der XAML-XAML-Namespace für XAML 2009):</span><span class="sxs-lookup"><span data-stu-id="ed174-139">For example, you could declare the following (prefix mappings not shown, but x is the XAML language XAML namespace for XAML 2009):</span></span>

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

<span data-ttu-id="ed174-140">In WPF und beim Targeting von .NET Framework 4 oder .NET Core 3.0 (oder `x:TypeArguments` höher) können Sie XAML 2009-Features zusammen mit, aber nur für loses XAML (XAML, das nicht markupkompiliert ist) verwenden.</span><span class="sxs-lookup"><span data-stu-id="ed174-140">In WPF and when targeting .NET Framework 4 or .NET Core 3.0 (or later), you can use XAML 2009 features together with `x:TypeArguments` but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="ed174-141">Markupkompilierte XAML für WPF und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht.</span><span class="sxs-lookup"><span data-stu-id="ed174-141">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span> <span data-ttu-id="ed174-142">Wenn Sie die XAML-Kompilierung markieren müssen, müssen Sie unter den Einschränkungen arbeiten, die im Abschnitt [XAML 2006 und WPF Generic XAML Usages](#xaml-2006-and-wpf-generic-xaml-usages) angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="ed174-142">If you need to markup compile the XAML, you must operate under the restrictions noted in the [XAML 2006 and WPF Generic XAML Usages](#xaml-2006-and-wpf-generic-xaml-usages) section.</span></span> <span data-ttu-id="ed174-143">BAML wird nur in .NET Framework unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ed174-143">BAML is only supported in .NET Framework.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed174-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ed174-144">See also</span></span>

- [<span data-ttu-id="ed174-145">x:Class-Direktive</span><span class="sxs-lookup"><span data-stu-id="ed174-145">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="ed174-146">x:Type-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="ed174-146">x:Type Markup Extension</span></span>](xtype-markup-extension.md)
- [<span data-ttu-id="ed174-147">Integrierte Typen für häufige XAML-Sprachprimitive</span><span class="sxs-lookup"><span data-stu-id="ed174-147">Built-in Types for Common XAML Language Primitives</span></span>](types-for-primitives.md)
- [<span data-ttu-id="ed174-148">Generics in XAML</span><span class="sxs-lookup"><span data-stu-id="ed174-148">Generics in XAML</span></span>](generics.md)
