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
ms.openlocfilehash: 94f09bdd3b6ee0b180e30bab0993f0b4e41730ac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="xtypearguments-directive"></a><span data-ttu-id="0db12-102">x:TypeArguments-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0db12-102">x:TypeArguments Directive</span></span>
<span data-ttu-id="0db12-103">Einschränken übergibt die Typargumente einer generischen an den Konstruktor des generischen Typs.</span><span class="sxs-lookup"><span data-stu-id="0db12-103">Passes constraining type arguments of a generic to the constructor of the generic type.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="0db12-104">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="0db12-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:TypeArguments="typeString" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="0db12-105">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="0db12-105">XAML Values</span></span>  
  
|||  
|-|-|  
|`object`|<span data-ttu-id="0db12-106">Ein Objektelementdeklaration eines XAML-Typs, der durch einen generischen CLR-Typ unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="0db12-106">An object element declaration of a XAML type, which is backed by a CLR generic type.</span></span> <span data-ttu-id="0db12-107">Wenn `object` bezieht sich auf einen XAML-Typ, der nicht aus dem XAML-Standardnamespace ist `object` erfordert ein Präfix an, dass die Verwendung von XAML-Namespace, in dem `object` vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="0db12-107">If `object` refers to a XAML type that is not from the default XAML namespace, `object` requires a prefix to indicate the XAML namespace where `object` exists.</span></span>|  
|`typeString`|<span data-ttu-id="0db12-108">Eine Zeichenfolge, die eine oder mehrere XAML deklariert-Typnamen Zeichenfolgen, die die Typargumente für den generischen CLR-Typ.</span><span class="sxs-lookup"><span data-stu-id="0db12-108">A string that declares one or more XAML type names as strings, which supplies the type arguments for the CLR generic type.</span></span> <span data-ttu-id="0db12-109">Zusätzliche Syntaxhinweise finden Sie unter "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="0db12-109">See Remarks for additional syntax notes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0db12-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0db12-110">Remarks</span></span>  
 <span data-ttu-id="0db12-111">In den meisten Fällen, die XAML-Typen, die verwendet werden, als ein Informationselement in einem `typeString` Zeichenfolge vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0db12-111">In most cases, the XAML types that are used as an information item in a `typeString` string are prefixed.</span></span> <span data-ttu-id="0db12-112">Typische generische Einschränkungen CLR-Typen (z. B. <xref:System.Int32> und <xref:System.String>) aus CLR-Basisklassenbibliotheken stammen.</span><span class="sxs-lookup"><span data-stu-id="0db12-112">Typical types of CLR generic constraints (for example, <xref:System.Int32> and <xref:System.String>) come from CLR base class libraries.</span></span> <span data-ttu-id="0db12-113">Diese Bibliotheken sind nicht zugeordnete typischen Framework-spezifischen XAML-Standardnamespaces und erfordert daher eine/Präfix-Zuordnung für die Verwendung von XAML-Verwendung.</span><span class="sxs-lookup"><span data-stu-id="0db12-113">Those libraries are not mapped to typical framework-specific default XAML namespaces, and therefore, require a prefix mapping for XAML usage.</span></span>  
  
 <span data-ttu-id="0db12-114">Sie können mehr als eine XAML-Typnamen angeben, durch ein Komma als Trennzeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="0db12-114">You can specify more than one XAML type name by using a comma delimiter.</span></span>  
  
 <span data-ttu-id="0db12-115">Wenn der generischen Einschränkungen selbst generische Typen zu verwenden, können die geschachtelten Einschränkung Typargumente durch Klammern () enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="0db12-115">If the generic constraints themselves use generic types, the nested constraint type arguments can be contained by parentheses ().</span></span>  
  
 <span data-ttu-id="0db12-116">Beachten Sie, dass diese Definition von `x:TypeArguments` bezieht sich auf .NET Framework-XAML-Dienste, und Verwenden von CLR-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="0db12-116">Note that this definition of `x:TypeArguments` is specific to .NET Framework XAML Services and using CLR backing.</span></span> <span data-ttu-id="0db12-117">Eine Definition auf Sprachebene finden Sie im [ \[MS-XAML-\] Abschnitt 5.3.11](http://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="0db12-117">A language-level definition can be found in [\[MS-XAML\] Section 5.3.11](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="usage-examples"></a><span data-ttu-id="0db12-118">Anwendungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="0db12-118">Usage Examples</span></span>  
 <span data-ttu-id="0db12-119">Für diesen Beispielen wird davon ausgegangen Sie, dass die folgenden XAML-Namespacedefinitionen deklariert werden:</span><span class="sxs-lookup"><span data-stu-id="0db12-119">For these examples, assume that the following XAML namespace definitions are declared:</span></span>  
  
```  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a><span data-ttu-id="0db12-120">Liste\<Zeichenfolge ></span><span class="sxs-lookup"><span data-stu-id="0db12-120">List\<String></span></span>  
 <span data-ttu-id="0db12-121">`<scg:List x:TypeArguments="sys:String" ...>` instanziiert eine neue <xref:System.Collections.Generic.List%601> mit einem <xref:System.String> Typargument.</span><span class="sxs-lookup"><span data-stu-id="0db12-121">`<scg:List x:TypeArguments="sys:String" ...>` instantiates a new <xref:System.Collections.Generic.List%601> with a <xref:System.String> type argument.</span></span>  
  
### <a name="dictionarystringstring"></a><span data-ttu-id="0db12-122">Wörterbuch\<Zeichenfolge, Zeichenfolge ></span><span class="sxs-lookup"><span data-stu-id="0db12-122">Dictionary\<String,String></span></span>  
 <span data-ttu-id="0db12-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instanziiert eine neue <xref:System.Collections.Generic.Dictionary%602> mit zwei <xref:System.String> Typargumente.</span><span class="sxs-lookup"><span data-stu-id="0db12-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instantiates a new <xref:System.Collections.Generic.Dictionary%602> with two <xref:System.String> type arguments.</span></span>  
  
### <a name="queuekeyvaluepairstringstring"></a><span data-ttu-id="0db12-124">Warteschlange < KeyValuePair\<Zeichenfolge "," String ">></span><span class="sxs-lookup"><span data-stu-id="0db12-124">Queue<KeyValuePair\<String,String>></span></span>  
 <span data-ttu-id="0db12-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instanziiert eine neue <xref:System.Collections.Generic.Queue%601> enthält, die die Einschränkung der <xref:System.Collections.Generic.KeyValuePair%602> mit die Typargumente für die interne Einschränkung <xref:System.String> und <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="0db12-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instantiates a new <xref:System.Collections.Generic.Queue%601> that has a constraint of <xref:System.Collections.Generic.KeyValuePair%602> with the inner constraint type arguments <xref:System.String> and <xref:System.String>.</span></span>  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a><span data-ttu-id="0db12-126">XAML 2006 und WPF generische XAML-Verwendungen</span><span class="sxs-lookup"><span data-stu-id="0db12-126">XAML 2006 and WPF Generic XAML Usages</span></span>  
 <span data-ttu-id="0db12-127">Für die Verwendung von XAML 2006 und XAML, das für die WPF-Anwendungen verwendet wird, der die folgenden Einschränkungen gelten für `x:TypeArguments` und generischen Typs Verwendungen von XAML im Allgemeinen:</span><span class="sxs-lookup"><span data-stu-id="0db12-127">For XAML 2006 usage, and XAML that is used for WPF applications, the following restrictions exist for `x:TypeArguments` and generic type usages from XAML in general:</span></span>  
  
-   <span data-ttu-id="0db12-128">Nur das Stammelement einer XAML-Datei kann es sich um eine allgemeine XAML-Verwendung unterstützen, die einen generischen Typ verweist.</span><span class="sxs-lookup"><span data-stu-id="0db12-128">Only the root element of a XAML file can support a generic XAML usage that references a generic type.</span></span>  
  
-   <span data-ttu-id="0db12-129">Das Stammelement muss ein generischer Typ mit mindestens einem Typargument zuordnen.</span><span class="sxs-lookup"><span data-stu-id="0db12-129">The root element must map to a generic type with at least one type argument.</span></span> <span data-ttu-id="0db12-130">Ein Beispiel ist <xref:System.Windows.Navigation.PageFunction%601>.</span><span class="sxs-lookup"><span data-stu-id="0db12-130">An example is <xref:System.Windows.Navigation.PageFunction%601>.</span></span> <span data-ttu-id="0db12-131">Die Seitenfunktionen sind das Hauptszenario für die Verwendung von XAML-generischen Verwendung-Unterstützung in WPF.</span><span class="sxs-lookup"><span data-stu-id="0db12-131">The page functions are the primary scenario for XAML generic usage support in WPF.</span></span>  
  
-   <span data-ttu-id="0db12-132">Außerdem muss der Stamm-XAML-Objektelement für den generischen deklariert eine partielle Klasse mit `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="0db12-132">The root element XAML object element for the generic must also declare a partial class using `x:Class`.</span></span> <span data-ttu-id="0db12-133">Dies gilt auch, wenn Definieren eines WPF-Buildvorgang.</span><span class="sxs-lookup"><span data-stu-id="0db12-133">This is true even if defining a WPF build action.</span></span>  
  
-   <span data-ttu-id="0db12-134">`x:TypeArguments` Geschachtelte generische Einschränkungen kann nicht verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="0db12-134">`x:TypeArguments` cannot reference nested generic constraints.</span></span>  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a><span data-ttu-id="0db12-135">XAML 2009 oder XAML 2006 ohne WPF 3.0 oder WPF 3.5 Abhängigkeit</span><span class="sxs-lookup"><span data-stu-id="0db12-135">XAML 2009 or XAML 2006 with No WPF 3.0 or WPF 3.5 Dependency</span></span>  
 <span data-ttu-id="0db12-136">In .NET Framework-XAML-Dienste für XAML 2006 oder XAML 2009 werden die WPF-bezogene Einschränkungen für generische XAML-Verwendung gelockert.</span><span class="sxs-lookup"><span data-stu-id="0db12-136">In .NET Framework XAML Services for either XAML 2006 or XAML 2009, the WPF-related restrictions on generic XAML usage are relaxed.</span></span> <span data-ttu-id="0db12-137">Sie können ein generisches Objektelement an einer beliebigen Position im XAML-Markup instanziieren, die die dahinter liegende Typ und dem Objektmodell unterstützen kann.</span><span class="sxs-lookup"><span data-stu-id="0db12-137">You can instantiate a generic object element at any position in XAML markup that the backing type system and object model can support.</span></span>  
  
 <span data-ttu-id="0db12-138">Bei Verwendung von XAML 2009 anstelle von mapping des CLR-Basistypen um XAML-Typen für häufige Sprachprimitive zu erhalten, können Sie [integrierte Typen für häufige XAML-Sprachprimitive](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) als Informationselementen in einem `typeString`.</span><span class="sxs-lookup"><span data-stu-id="0db12-138">If you use XAML 2009 instead of mapping the CLR base types to obtain XAML types for common language primitives, you can use [Built-in Types for Common XAML Language Primitives](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) as information items in a `typeString`.</span></span> <span data-ttu-id="0db12-139">Beispielsweise konnten Sie die folgenden deklarieren (/ Präfix-Zuordnungen, die nicht angezeigt, aber x ist die Verwendung von XAML-Verwendung von XAML-Sprachnamespace für XAML 2009):</span><span class="sxs-lookup"><span data-stu-id="0db12-139">For example, you could declare the following (prefix mappings not shown, but x is the XAML language XAML namespace for XAML 2009):</span></span>  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 <span data-ttu-id="0db12-140">In WPF und beim Abzielen auf [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], können Sie XAML 2009-Funktionen zusammen mit `x:TypeArguments` jedoch nur für loose XAML (, das nicht markupkompiliert ist).</span><span class="sxs-lookup"><span data-stu-id="0db12-140">In WPF and when targeting [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use XAML 2009 features together with `x:TypeArguments` but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="0db12-141">Markupkompilierte XAML für WPF und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht.</span><span class="sxs-lookup"><span data-stu-id="0db12-141">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span> <span data-ttu-id="0db12-142">Wenn Sie Markup den XAML-Code kompilieren müssen, müssen Sie unter den Einschränkungen dar, die im Abschnitt "XAML 2006 und WPF generische XAML-Verwendungen" ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0db12-142">If you need to markup compile the XAML, you must operate under the restrictions noted in the "XAML 2006 and WPF Generic XAML Usages" section.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0db12-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0db12-143">See Also</span></span>  
 [<span data-ttu-id="0db12-144">x:Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0db12-144">x:Class Directive</span></span>](../../../docs/framework/xaml-services/x-class-directive.md)  
 [<span data-ttu-id="0db12-145">x:Type-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="0db12-145">x:Type Markup Extension</span></span>](../../../docs/framework/xaml-services/x-type-markup-extension.md)  
 [<span data-ttu-id="0db12-146">Integrierte Typen für häufige XAML-Sprachprimitive</span><span class="sxs-lookup"><span data-stu-id="0db12-146">Built-in Types for Common XAML Language Primitives</span></span>](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)  
 [<span data-ttu-id="0db12-147">Generika in XAML</span><span class="sxs-lookup"><span data-stu-id="0db12-147">Generics in XAML</span></span>](../../../docs/framework/xaml-services/generics-in-xaml.md)
