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
ms.openlocfilehash: 430ab65af52282ccb1d429cd2523efe213f13609
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543550"
---
# <a name="xtypearguments-directive"></a><span data-ttu-id="f2d5e-102">x:TypeArguments-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f2d5e-102">x:TypeArguments Directive</span></span>

<span data-ttu-id="f2d5e-103">Übergibt einschränkende Typargumente eines generischen an den Konstruktor des generischen Typs.</span><span class="sxs-lookup"><span data-stu-id="f2d5e-103">Passes constraining type arguments of a generic to the constructor of the generic type.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="f2d5e-104">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="f2d5e-104">XAML Attribute Usage</span></span>

```xaml
<object x:TypeArguments="typeString" .../>
```

## <a name="xaml-values"></a><span data-ttu-id="f2d5e-105">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="f2d5e-105">XAML Values</span></span>

|||
|-|-|
|`object`|<span data-ttu-id="f2d5e-106">Eine Objekt Element Deklaration eines XAML-Typs, der durch einen generischen CLR-Typ unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="f2d5e-106">An object element declaration of a XAML type, which is backed by a CLR generic type.</span></span> <span data-ttu-id="f2d5e-107">Wenn `object` auf einen XAML-Typ verweist, der nicht aus dem XAML-Standard Namespace gehört, `object` erfordert ein Präfix, um den XAML-Namespace anzugeben, in dem `object` vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f2d5e-107">If `object` refers to a XAML type that is not from the default XAML namespace, `object` requires a prefix to indicate the XAML namespace where `object` exists.</span></span>|
|`typeString`|<span data-ttu-id="f2d5e-108">Eine Zeichenfolge, die einen oder mehrere XAML-Typnamen als Zeichen folgen deklariert, die die Typargumente für den generischen CLR-Typ bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f2d5e-108">A string that declares one or more XAML type names as strings, which supplies the type arguments for the CLR generic type.</span></span> <span data-ttu-id="f2d5e-109">Weitere Informationen zur Syntax finden Sie in den hinweisen.</span><span class="sxs-lookup"><span data-stu-id="f2d5e-109">See Remarks for additional syntax notes.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f2d5e-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f2d5e-110">Remarks</span></span>

<span data-ttu-id="f2d5e-111">In den meisten Fällen werden die XAML-Typen, die als Informationselement in einer Zeichenfolge verwendet werden, als `typeString` Präfix vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="f2d5e-111">In most cases, the XAML types that are used as an information item in a `typeString` string are prefixed.</span></span> <span data-ttu-id="f2d5e-112">Typische Typen von generischen CLR-Einschränkungen (z. b. <xref:System.Int32> und <xref:System.String> ) stammen aus CLR-Basisklassen Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="f2d5e-112">Typical types of CLR generic constraints (for example, <xref:System.Int32> and <xref:System.String>) come from CLR base class libraries.</span></span> <span data-ttu-id="f2d5e-113">Diese Bibliotheken sind nicht typischen Framework-spezifischen XAML-Standard Namespaces zugeordnet und erfordern daher eine Präfix Zuordnung für die XAML-Verwendung.</span><span class="sxs-lookup"><span data-stu-id="f2d5e-113">Those libraries are not mapped to typical framework-specific default XAML namespaces, and therefore, require a prefix mapping for XAML usage.</span></span>

<span data-ttu-id="f2d5e-114">Sie können mehr als einen XAML-Typnamen angeben, indem Sie ein Komma Trennzeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="f2d5e-114">You can specify more than one XAML type name by using a comma delimiter.</span></span>

<span data-ttu-id="f2d5e-115">Wenn die generischen Einschränkungen selbst generische Typen verwenden, können die Argumente der geschachtelten Einschränkungs Typen in Klammern () enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="f2d5e-115">If the generic constraints themselves use generic types, the nested constraint type arguments can be contained by parentheses ().</span></span>

<span data-ttu-id="f2d5e-116">Beachten Sie, dass diese Definition von `x:TypeArguments` speziell für .net XAML-Dienste und die Verwendung von CLR-Unterstützung gilt.</span><span class="sxs-lookup"><span data-stu-id="f2d5e-116">Note that this definition of `x:TypeArguments` is specific to .NET XAML Services and using CLR backing.</span></span> <span data-ttu-id="f2d5e-117">Eine Definition auf Sprachebene finden Sie im [ \[ \] Abschnitt 5.3.11 des MS-XAML-Abschnitts](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="f2d5e-117">A language-level definition can be found in [\[MS-XAML\] Section 5.3.11](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

## <a name="usage-examples"></a><span data-ttu-id="f2d5e-118">Anwendungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="f2d5e-118">Usage Examples</span></span>

<span data-ttu-id="f2d5e-119">Nehmen Sie für diese Beispiele an, dass die folgenden XAML-Namespace Definitionen deklariert sind:</span><span class="sxs-lookup"><span data-stu-id="f2d5e-119">For these examples, assume that the following XAML namespace definitions are declared:</span></span>

```xaml
xmlns:sys="clr-namespace:System;assembly=mscorlib"
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"
```

### <a name="liststring"></a><span data-ttu-id="f2d5e-120">List\<String></span><span class="sxs-lookup"><span data-stu-id="f2d5e-120">List\<String></span></span>

<span data-ttu-id="f2d5e-121">`<scg:List x:TypeArguments="sys:String" ...>` instanziiert ein neues- <xref:System.Collections.Generic.List%601> Argument mit einem <xref:System.String> Typargument.</span><span class="sxs-lookup"><span data-stu-id="f2d5e-121">`<scg:List x:TypeArguments="sys:String" ...>` instantiates a new <xref:System.Collections.Generic.List%601> with a <xref:System.String> type argument.</span></span>

### <a name="dictionarystringstring"></a><span data-ttu-id="f2d5e-122">Wörterbuch\<String,String></span><span class="sxs-lookup"><span data-stu-id="f2d5e-122">Dictionary\<String,String></span></span>

<span data-ttu-id="f2d5e-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instanziiert eine neue <xref:System.Collections.Generic.Dictionary%602> mit zwei <xref:System.String> Typargumenten.</span><span class="sxs-lookup"><span data-stu-id="f2d5e-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instantiates a new <xref:System.Collections.Generic.Dictionary%602> with two <xref:System.String> type arguments.</span></span>

### <a name="queuekeyvaluepairstringstring"></a><span data-ttu-id="f2d5e-124">Queue<KeyValuePair\<String,String>></span><span class="sxs-lookup"><span data-stu-id="f2d5e-124">Queue<KeyValuePair\<String,String>></span></span>

<span data-ttu-id="f2d5e-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instanziiert einen neuen <xref:System.Collections.Generic.Queue%601> , der über eine Einschränkung von <xref:System.Collections.Generic.KeyValuePair%602> mit den inneren Einschränkungs Typargumenten <xref:System.String> und verfügt <xref:System.String> .</span><span class="sxs-lookup"><span data-stu-id="f2d5e-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instantiates a new <xref:System.Collections.Generic.Queue%601> that has a constraint of <xref:System.Collections.Generic.KeyValuePair%602> with the inner constraint type arguments <xref:System.String> and <xref:System.String>.</span></span>

## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a><span data-ttu-id="f2d5e-126">XAML 2006 und allgemeine WPF-XAML-Verwendungen</span><span class="sxs-lookup"><span data-stu-id="f2d5e-126">XAML 2006 and WPF Generic XAML Usages</span></span>

<span data-ttu-id="f2d5e-127">Bei der Verwendung von XAML 2006 und XAML, die für WPF-Anwendungen verwendet werden, gibt es die folgenden Einschränkungen für `x:TypeArguments` und generische typverwendungen von XAML im allgemeinen:</span><span class="sxs-lookup"><span data-stu-id="f2d5e-127">For XAML 2006 usage, and XAML that is used for WPF applications, the following restrictions exist for `x:TypeArguments` and generic type usages from XAML in general:</span></span>

- <span data-ttu-id="f2d5e-128">Nur das Stamm Element einer XAML-Datei kann eine generische XAML-Verwendung unterstützen, die auf einen generischen Typ verweist.</span><span class="sxs-lookup"><span data-stu-id="f2d5e-128">Only the root element of a XAML file can support a generic XAML usage that references a generic type.</span></span>

- <span data-ttu-id="f2d5e-129">Das root-Element muss einem generischen Typ mit mindestens einem Typargument zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="f2d5e-129">The root element must map to a generic type with at least one type argument.</span></span> <span data-ttu-id="f2d5e-130">z. B. <xref:System.Windows.Navigation.PageFunction%601>.</span><span class="sxs-lookup"><span data-stu-id="f2d5e-130">An example is <xref:System.Windows.Navigation.PageFunction%601>.</span></span> <span data-ttu-id="f2d5e-131">Die Seitenfunktionen sind das primäre Szenario für die generische Verwendung von XAML in WPF.</span><span class="sxs-lookup"><span data-stu-id="f2d5e-131">The page functions are the primary scenario for XAML generic usage support in WPF.</span></span>

- <span data-ttu-id="f2d5e-132">Das Stamm Element-XAML-Objekt Element für den generischen muss ebenfalls mithilfe von eine partielle Klasse deklarieren `x:Class` .</span><span class="sxs-lookup"><span data-stu-id="f2d5e-132">The root element XAML object element for the generic must also declare a partial class using `x:Class`.</span></span> <span data-ttu-id="f2d5e-133">Dies gilt auch, wenn Sie eine WPF-Buildaktion definieren.</span><span class="sxs-lookup"><span data-stu-id="f2d5e-133">This is true even if defining a WPF build action.</span></span>

- <span data-ttu-id="f2d5e-134">`x:TypeArguments` auf die generischen generischen Einschränkungen kann nicht verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="f2d5e-134">`x:TypeArguments` cannot reference nested generic constraints.</span></span>

## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a><span data-ttu-id="f2d5e-135">XAML 2009 oder XAML 2006 ohne WPF 3,0 oder WPF 3,5-Abhängigkeit</span><span class="sxs-lookup"><span data-stu-id="f2d5e-135">XAML 2009 or XAML 2006 with No WPF 3.0 or WPF 3.5 Dependency</span></span>

<span data-ttu-id="f2d5e-136">In .net XAML-Diensten für XAML 2006 oder XAML 2009 werden die WPF-bezogenen Einschränkungen bei der generischen XAML-Verwendung gelockert.</span><span class="sxs-lookup"><span data-stu-id="f2d5e-136">In .NET XAML Services for either XAML 2006 or XAML 2009, the WPF-related restrictions on generic XAML usage are relaxed.</span></span> <span data-ttu-id="f2d5e-137">Sie können ein generisches Objekt Element an einer beliebigen Position in XAML-Markup instanziieren, die das Unterstützungs-Typsystem und das Objektmodell unterstützen können.</span><span class="sxs-lookup"><span data-stu-id="f2d5e-137">You can instantiate a generic object element at any position in XAML markup that the backing type system and object model can support.</span></span>

<span data-ttu-id="f2d5e-138">Wenn Sie XAML 2009 anstelle der Zuordnung der CLR-Basis Typen zum Abrufen von XAML-Typen für allgemeine sprach primitive verwenden, können Sie [integrierte Typen für allgemeine XAML-sprach primitive](types-for-primitives.md) als Informationselemente in einem verwenden `typeString` .</span><span class="sxs-lookup"><span data-stu-id="f2d5e-138">If you use XAML 2009 instead of mapping the CLR base types to obtain XAML types for common language primitives, you can use [Built-in Types for Common XAML Language Primitives](types-for-primitives.md) as information items in a `typeString`.</span></span> <span data-ttu-id="f2d5e-139">Sie könnten z. b. Folgendes deklarieren (Präfix Zuordnungen werden nicht angezeigt, aber x ist der XAML-sprach Namespace XAML-Namespace für XAML 2009):</span><span class="sxs-lookup"><span data-stu-id="f2d5e-139">For example, you could declare the following (prefix mappings not shown, but x is the XAML language XAML namespace for XAML 2009):</span></span>

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

<span data-ttu-id="f2d5e-140">In WPF und beim Ziel .NET Framework 4 oder .net Core 3,0 (oder höher) können Sie XAML 2009-Funktionen zusammen mit verwenden, `x:TypeArguments` aber nur für Loose XAML (XAML, das nicht Markup kompiliert ist).</span><span class="sxs-lookup"><span data-stu-id="f2d5e-140">In WPF and when targeting .NET Framework 4 or .NET Core 3.0 (or later), you can use XAML 2009 features together with `x:TypeArguments` but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="f2d5e-141">Markupkompilierte XAML für WPF und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht.</span><span class="sxs-lookup"><span data-stu-id="f2d5e-141">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span> <span data-ttu-id="f2d5e-142">Wenn Sie das XAML-Markup kompilieren müssen, müssen Sie unter den im Abschnitt [generische XAML-Verwendungen von XAML 2006 und WPF](#xaml-2006-and-wpf-generic-xaml-usages) notierten Einschränkungen arbeiten.</span><span class="sxs-lookup"><span data-stu-id="f2d5e-142">If you need to markup compile the XAML, you must operate under the restrictions noted in the [XAML 2006 and WPF Generic XAML Usages](#xaml-2006-and-wpf-generic-xaml-usages) section.</span></span> <span data-ttu-id="f2d5e-143">BAML wird nur in .NET Framework unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f2d5e-143">BAML is only supported in .NET Framework.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2d5e-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2d5e-144">See also</span></span>

- [<span data-ttu-id="f2d5e-145">x:Class-Direktive</span><span class="sxs-lookup"><span data-stu-id="f2d5e-145">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="f2d5e-146">x:Type-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="f2d5e-146">x:Type Markup Extension</span></span>](xtype-markup-extension.md)
- [<span data-ttu-id="f2d5e-147">Integrierte Typen für häufige XAML-Sprachprimitive</span><span class="sxs-lookup"><span data-stu-id="f2d5e-147">Built-in Types for Common XAML Language Primitives</span></span>](types-for-primitives.md)
- [<span data-ttu-id="f2d5e-148">Generics in XAML</span><span class="sxs-lookup"><span data-stu-id="f2d5e-148">Generics in XAML</span></span>](generics.md)
