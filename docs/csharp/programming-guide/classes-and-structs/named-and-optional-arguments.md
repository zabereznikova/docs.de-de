---
title: Benannte und optionale Argumente (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- namedParameter_CSharpKeyword
- cs_namedParameter
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], named
- named arguments [C#]
- arguments [C#], named
- optional arguments [C#]
- arguments [C#], optional
- parameters [C#], optional
- named and optional arguments [C#]
ms.assetid: 839c960c-c2dc-4d05-af4d-ca5428e54008
caps.latest.revision: 43
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 0dc2fcee3903b80816c98bab47e2b9a2e5ef78b0
ms.openlocfilehash: a7f05e3e0b19bf6457989f8db2b46741cf6b28c1
ms.contentlocale: de-de
ms.lasthandoff: 08/28/2017

---
# <a name="named-and-optional-arguments-c-programming-guide"></a><span data-ttu-id="df140-102">Benannte und optionale Argumente (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="df140-102">Named and Optional Arguments (C# Programming Guide)</span></span>
[!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)]<span data-ttu-id="df140-103"> führt benannte und optionale Argumente ein.</span><span class="sxs-lookup"><span data-stu-id="df140-103"> introduces named and optional arguments.</span></span> <span data-ttu-id="df140-104">*Benannte Argumente* ermöglichen es Ihnen, ein Argument für einen bestimmten Parameter anzugeben, indem Sie das Argument dem Parameternamen anstatt der Position des Parameters in der Parameterliste zuordnen.</span><span class="sxs-lookup"><span data-stu-id="df140-104">*Named arguments* enable you to specify an argument for a particular parameter by associating the argument with the parameter's name rather than with the parameter's position in the parameter list.</span></span> <span data-ttu-id="df140-105">*Optionale Argumente* ermöglichen es Ihnen, Argumente für einige Parameter auszulassen.</span><span class="sxs-lookup"><span data-stu-id="df140-105">*Optional arguments* enable you to omit arguments for some parameters.</span></span> <span data-ttu-id="df140-106">Beide Techniken können mit Methoden, Indexern, Konstruktoren und Delegaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="df140-106">Both techniques can be used with methods, indexers, constructors, and delegates.</span></span>  
  
 <span data-ttu-id="df140-107">Wenn Sie benannte und optionale Argumente verwenden, werden die Argumente in der Reihenfolge ausgewertet, in der sie in der Argumentliste, nicht in der Parameterliste, erscheinen.</span><span class="sxs-lookup"><span data-stu-id="df140-107">When you use named and optional arguments, the arguments are evaluated in the order in which they appear in the argument list, not the parameter list.</span></span>  
  
 <span data-ttu-id="df140-108">Wenn Sie benannte und optionale Parameter zusammen verwenden, können Sie Argumente für nur ein paar Parameter aus einer Liste von optionalen Parametern bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="df140-108">Named and optional parameters, when used together, enable you to supply arguments for only a few parameters from a list of optional parameters.</span></span> <span data-ttu-id="df140-109">Diese Funktion erleichtert den Zugriff auf COM-Schnittstellen wie etwa die Automatisierungs-APIs in Microsoft Office erheblich.</span><span class="sxs-lookup"><span data-stu-id="df140-109">This capability greatly facilitates calls to COM interfaces such as the Microsoft Office Automation APIs.</span></span>  
  
## <a name="named-arguments"></a><span data-ttu-id="df140-110">Benannte Argumente</span><span class="sxs-lookup"><span data-stu-id="df140-110">Named Arguments</span></span>  
 <span data-ttu-id="df140-111">Bei Verwendung benannter Argumente bleibt es Ihnen erspart, sich an die Reihenfolge von Parametern in den Parameterlisten von aufgerufenen Methoden zu erinnern oder sie nachzuschauen.</span><span class="sxs-lookup"><span data-stu-id="df140-111">Named arguments free you from the need to remember or to look up the order of parameters in the parameter lists of called methods.</span></span> <span data-ttu-id="df140-112">Der Parameter für jedes Argument kann vom Parameternamen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="df140-112">The parameter for each argument can be specified by parameter name.</span></span> <span data-ttu-id="df140-113">Eine Funktion, die den Body-Mass-Index (BMI) berechnet, kann beispielsweise auf normale Weise aufgerufen werden, indem anhand der Position Argumente für Gewicht und Höhe in der Reihenfolge gesendet werden, die von der Funktion definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="df140-113">For example, a function that calculates body mass index (BMI) can be called in the standard way by sending arguments for weight and height by position, in the order defined by the function.</span></span>  
  
 `CalculateBMI(123, 64);`  
  
 <span data-ttu-id="df140-114">Wenn Sie sich nicht an die Reihenfolge der Parameter erinnern, aber ihre Namen wissen, können Sie die Argumente in beliebiger Reihenfolge – zuerst das Gewicht oder die Höhe – senden.</span><span class="sxs-lookup"><span data-stu-id="df140-114">If you do not remember the order of the parameters but you do know their names, you can send the arguments in either order, weight first or height first.</span></span>  
  
 `CalculateBMI(weight: 123, height: 64);`  
  
 `CalculateBMI(height: 64, weight: 123);`  
  
 <span data-ttu-id="df140-115">Benannte Argumente verbessern auch die Lesbarkeit des Codes, indem sie identifizieren, was jedes Argument darstellt.</span><span class="sxs-lookup"><span data-stu-id="df140-115">Named arguments also improve the readability of your code by identifying what each argument represents.</span></span>  
  
 <span data-ttu-id="df140-116">Ein benanntes Argument kann Positionsargumenten folgen, wie hier gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="df140-116">A named argument can follow positional arguments, as shown here.</span></span>  
  
 `CalculateBMI(123, height: 64);`  
  
 <span data-ttu-id="df140-117">Auf ein benanntes Argument kann jedoch kein Positionsargument folgen.</span><span class="sxs-lookup"><span data-stu-id="df140-117">However, a positional argument cannot follow a named argument.</span></span> <span data-ttu-id="df140-118">Compilerfehler werden durch folgende Anweisung verursacht.</span><span class="sxs-lookup"><span data-stu-id="df140-118">The following statement causes a compiler error.</span></span>  
  
 `//CalculateBMI(weight: 123, 64);`  
  
## <a name="example"></a><span data-ttu-id="df140-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="df140-119">Example</span></span>  
 <span data-ttu-id="df140-120">Der folgende Code implementiert die Beispiele in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="df140-120">The following code implements the examples from this section.</span></span>  
  
 <span data-ttu-id="df140-121">[!code-cs[csProgGuideNamedAndOptional#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="df140-121">[!code-cs[csProgGuideNamedAndOptional#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_1.cs)]</span></span>  
  
## <a name="optional-arguments"></a><span data-ttu-id="df140-122">Optionale Argumente</span><span class="sxs-lookup"><span data-stu-id="df140-122">Optional Arguments</span></span>  
 <span data-ttu-id="df140-123">Die Definition einer Methode, eines Konstruktors, eines Indexers oder Delegaten kann angeben, dass deren Parameter benötigt werden oder optional sind.</span><span class="sxs-lookup"><span data-stu-id="df140-123">The definition of a method, constructor, indexer, or delegate can specify that its parameters are required or that they are optional.</span></span> <span data-ttu-id="df140-124">Jeder Aufruf muss Argumente für alle benötigten Parameter bereitstellen, kann aber Argumente für optionale Parameter auslassen.</span><span class="sxs-lookup"><span data-stu-id="df140-124">Any call must provide arguments for all required parameters, but can omit arguments for optional parameters.</span></span>  
  
 <span data-ttu-id="df140-125">Jeder optionale Parameter hat einen Standardwert als Teil seiner Definition.</span><span class="sxs-lookup"><span data-stu-id="df140-125">Each optional parameter has a default value as part of its definition.</span></span> <span data-ttu-id="df140-126">Wenn für diesen Parameter kein Argument gesendet wird, wird der Standardwert verwendet.</span><span class="sxs-lookup"><span data-stu-id="df140-126">If no argument is sent for that parameter, the default value is used.</span></span> <span data-ttu-id="df140-127">Ein Standardwert muss einer der folgenden Typen von Ausdrücken sein:</span><span class="sxs-lookup"><span data-stu-id="df140-127">A default value must be one of the following types of expressions:</span></span>  
  
-   <span data-ttu-id="df140-128">Ein konstanter Ausdruck</span><span class="sxs-lookup"><span data-stu-id="df140-128">a constant expression;</span></span>  
  
-   <span data-ttu-id="df140-129">Ein Ausdruck der Form `new ValType()`, wobei `ValType` ein Werttyp wie [enum](../../../csharp/language-reference/keywords/enum.md) oder [struct](../../../csharp/programming-guide/classes-and-structs/structs.md) ist</span><span class="sxs-lookup"><span data-stu-id="df140-129">an expression of the form `new ValType()`, where `ValType` is a value type, such as an [enum](../../../csharp/language-reference/keywords/enum.md) or a [struct](../../../csharp/programming-guide/classes-and-structs/structs.md);</span></span>  
  
-   <span data-ttu-id="df140-130">Ein Ausdruck in Form von [default(ValType)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md), wobei `ValType` ein Werttyp ist</span><span class="sxs-lookup"><span data-stu-id="df140-130">an expression of the form [default(ValType)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md),  where `ValType` is a value type.</span></span>  
  
 <span data-ttu-id="df140-131">Optionale Parameter werden am Ende der Parameterliste nach den erforderlichen Parametern definiert.</span><span class="sxs-lookup"><span data-stu-id="df140-131">Optional parameters are defined at the end of the parameter list, after any required parameters.</span></span> <span data-ttu-id="df140-132">Wenn der Aufrufer ein Argument für einen beliebigen Parameter aus einer Folge von optionalen Parametern bereitstellt, muss er Argumente für alle vorherigen optionalen Parameter bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="df140-132">If the caller provides an argument for any one of a succession of optional parameters, it must provide arguments for all preceding optional parameters.</span></span> <span data-ttu-id="df140-133">Durch Trennzeichen getrennte Lücken in der Argumentliste werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="df140-133">Comma-separated gaps in the argument list are not supported.</span></span> <span data-ttu-id="df140-134">Im folgenden Code wird z.B. die Instanzmethode `ExampleMethod` mit einem erforderlichen und zwei optionalen Parametern definiert.</span><span class="sxs-lookup"><span data-stu-id="df140-134">For example, in the following code, instance method `ExampleMethod` is defined with one required and two optional parameters.</span></span>  
  
 <span data-ttu-id="df140-135">[!code-cs[csProgGuideNamedAndOptional#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="df140-135">[!code-cs[csProgGuideNamedAndOptional#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_2.cs)]</span></span>  
  
 <span data-ttu-id="df140-136">Der folgende Aufruf von `ExampleMethod` verursacht einen Compilerfehler, da ein Argument für den dritten Parameter, aber nicht für den zweiten, bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="df140-136">The following call to `ExampleMethod` causes a compiler error, because an argument is provided for the third parameter but not for the second.</span></span>  
  
 `//anExample.ExampleMethod(3, ,4);`  
  
 <span data-ttu-id="df140-137">Wenn Sie den Namen des dritten Parameters kennen, können Sie ein benanntes Argument zum Ausführen der Aufgabe verwenden.</span><span class="sxs-lookup"><span data-stu-id="df140-137">However, if you know the name of the third parameter, you can use a named argument to accomplish the task.</span></span>  
  
 `anExample.ExampleMethod(3, optionalint: 4);`  
  
 <span data-ttu-id="df140-138">IntelliSense verwendet zum Anzeigen von optionalen Parametern Klammern, wie in folgender Abbildung veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="df140-138">IntelliSense uses brackets to indicate optional parameters, as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="df140-139">![IntelliSense-QuickInfo für die Methode „ExampleMethod.“](../../../csharp/programming-guide/classes-and-structs/media/optional_parameters.png "Optional_Parameters")</span><span class="sxs-lookup"><span data-stu-id="df140-139">![IntelliSense Quick Info for method ExampleMethod.](../../../csharp/programming-guide/classes-and-structs/media/optional_parameters.png "Optional_Parameters")</span></span>  
<span data-ttu-id="df140-140">Optionale Parameter in ExampleMethod</span><span class="sxs-lookup"><span data-stu-id="df140-140">Optional parameters in ExampleMethod</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df140-141">Sie können auch optionale Parameter mit der .NET-Klasse <xref:System.Runtime.InteropServices.OptionalAttribute> deklarieren.</span><span class="sxs-lookup"><span data-stu-id="df140-141">You can also declare optional parameters by using the .NET <xref:System.Runtime.InteropServices.OptionalAttribute> class.</span></span> <span data-ttu-id="df140-142">`OptionalAttribute`-Parameter erfordern keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="df140-142">`OptionalAttribute` parameters do not require a default value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df140-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="df140-143">Example</span></span>  
 <span data-ttu-id="df140-144">Im folgenden Beispiel hat der Konstruktor für `ExampleClass` einen Parameter, der optional ist.</span><span class="sxs-lookup"><span data-stu-id="df140-144">In the following example, the constructor for `ExampleClass` has one parameter, which is optional.</span></span> <span data-ttu-id="df140-145">Instanzmethode `ExampleMethod` hat einen erforderlichen Parameter (`required`) und zwei optionale Parameter (`optionalstr` und `optionalint`).</span><span class="sxs-lookup"><span data-stu-id="df140-145">Instance method `ExampleMethod` has one required parameter, `required`, and two optional parameters, `optionalstr` and `optionalint`.</span></span> <span data-ttu-id="df140-146">Der Code in `Main` veranschaulicht die unterschiedlichen Methoden, in denen der Konstruktor und die Methode aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="df140-146">The code in `Main` shows the different ways in which the constructor and method can be invoked.</span></span>  
  
 <span data-ttu-id="df140-147">[!code-cs[csProgGuideNamedAndOptional#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="df140-147">[!code-cs[csProgGuideNamedAndOptional#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_3.cs)]</span></span>  
  
## <a name="com-interfaces"></a><span data-ttu-id="df140-148">COM-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="df140-148">COM Interfaces</span></span>  
 <span data-ttu-id="df140-149">Benannte und optionale Argumente verbessern zusammen mit der Unterstützung von dynamischen Objekten und anderen Verbesserungen deutlich die Interoperabilität mit COM-APIs wie Office-Automatisierungs-APIs.</span><span class="sxs-lookup"><span data-stu-id="df140-149">Named and optional arguments, along with support for dynamic objects and other enhancements, greatly improve interoperability with COM APIs, such as Office Automation APIs.</span></span>  
  
 <span data-ttu-id="df140-150">Die Methode [AutoFormat](http://go.microsoft.com/fwlink/?LinkId=148201) hat z.B. in der Schnittstelle [Bereich](http://go.microsoft.com/fwlink/?LinkId=148196) von Microsoft Office Excel sieben Parameter, von denen alle optional sind.</span><span class="sxs-lookup"><span data-stu-id="df140-150">For example, the [AutoFormat](http://go.microsoft.com/fwlink/?LinkId=148201) method in the Microsoft Office Excel [Range](http://go.microsoft.com/fwlink/?LinkId=148196) interface has seven parameters, all of which are optional.</span></span> <span data-ttu-id="df140-151">Diese Parameter sind in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="df140-151">These parameters are shown in the following illustration.</span></span>  
  
 <span data-ttu-id="df140-152">![IntelliSense-QuickInfo für die AutoFormat-Methode.](../../../csharp/programming-guide/classes-and-structs/media/autoformat_parameters.png "AutoFormat_Parameters")</span><span class="sxs-lookup"><span data-stu-id="df140-152">![IntelliSense Quick Info for the AutoFormat method.](../../../csharp/programming-guide/classes-and-structs/media/autoformat_parameters.png "AutoFormat_Parameters")</span></span>  
<span data-ttu-id="df140-153">AutoFormat-Parameter</span><span class="sxs-lookup"><span data-stu-id="df140-153">AutoFormat parameters</span></span>  
  
 <span data-ttu-id="df140-154">In C# 3.0 und früheren Versionen wird ein Argument für jeden Parameter benötigt, wie im folgenden Beispiel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="df140-154">In C# 3.0 and earlier versions, an argument is required for each parameter, as shown in the following example.</span></span>  
  
 <span data-ttu-id="df140-155">[!code-cs[csProgGuideNamedAndOptional#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="df140-155">[!code-cs[csProgGuideNamedAndOptional#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_4.cs)]</span></span>  
  
 <span data-ttu-id="df140-156">Sie können jedoch den Aufruf an `AutoFormat` erheblich vereinfachen, indem Sie benannte und optionale Argumente verwenden, die in C# 4.0 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="df140-156">However, you can greatly simplify the call to `AutoFormat` by using named and optional arguments, introduced in C# 4.0.</span></span> <span data-ttu-id="df140-157">Benannte und optionale Parameter helfen Ihnen dabei, das Argument für einen optionalen Parameter auszulassen, wenn Sie den Standardwert des Parameters nicht ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="df140-157">Named and optional arguments enable you to omit the argument for an optional parameter if you do not want to change the parameter's default value.</span></span> <span data-ttu-id="df140-158">Im folgenden Aufruf wird ein Wert für nur einen der sieben Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="df140-158">In the following call, a value is specified for only one of the seven parameters.</span></span>  
  
 <span data-ttu-id="df140-159">[!code-cs[csProgGuideNamedAndOptional#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="df140-159">[!code-cs[csProgGuideNamedAndOptional#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_5.cs)]</span></span>  
  
 <span data-ttu-id="df140-160">Weitere Informationen und Beispiele finden Sie unter [Vorgehensweise: Verwenden von benannten und optionalen Argumenten in der Office-Programmierung](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) und [Vorgehensweise: Zugreifen auf Office Interop-Objekte mithilfe von Visual C#-Funktionen](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span><span class="sxs-lookup"><span data-stu-id="df140-160">For more information and examples, see [How to: Use Named and Optional Arguments in Office Programming](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) and [How to: Access Office Interop Objects by Using Visual C# Features](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span></span>  
  
## <a name="overload-resolution"></a><span data-ttu-id="df140-161">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="df140-161">Overload Resolution</span></span>  
 <span data-ttu-id="df140-162">Das Verwenden von benannten und optionalen Argumenten wirkt sich auf die Überladungsauflösung folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="df140-162">Use of named and optional arguments affects overload resolution in the following ways:</span></span>  
  
-   <span data-ttu-id="df140-163">Eine Methode, ein Indexer oder ein Konstruktor ist ein Kandidat für die Ausführung, wenn jeder der Parameter entweder optional ist oder über Namen oder Position auf ein einzelnes Argument in der aufrufenden Anweisung reagiert. Dieses Argument kann in dem Typ des Parameters konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="df140-163">A method, indexer, or constructor is a candidate for execution if each of its parameters either is optional or corresponds, by name or by position, to a single argument in the calling statement, and that argument can be converted to the type of the parameter.</span></span>  
  
-   <span data-ttu-id="df140-164">Wenn mehr als ein Kandidat gefunden wird, werden die Regeln der Überladungsauflösung als bevorzugte Konvertierungen auf die Argumente angewandt, die ausdrücklich angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="df140-164">If more than one candidate is found, overload resolution rules for preferred conversions are applied to the arguments that are explicitly specified.</span></span> <span data-ttu-id="df140-165">Ausgelassene Argumente für optionale Parameter werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="df140-165">Omitted arguments for optional parameters are ignored.</span></span>  
  
-   <span data-ttu-id="df140-166">Wenn zwei Kandidaten gleich gut geeignet sind, wird ein Kandidat bevorzugt, der keine optionalen Parameter besitzt, für die Argumente im Aufruf ausgelassen wurden.</span><span class="sxs-lookup"><span data-stu-id="df140-166">If two candidates are judged to be equally good, preference goes to a candidate that does not have optional parameters for which arguments were omitted in the call.</span></span> <span data-ttu-id="df140-167">Dies ist die Folge einer allgemeinen Präferenz bei der Überladungsauflösung für Kandidaten, die weniger Parameter besitzen.</span><span class="sxs-lookup"><span data-stu-id="df140-167">This is a consequence of a general preference in overload resolution for candidates that have fewer parameters.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="df140-168">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="df140-168">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="df140-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df140-169">See Also</span></span>  
 <span data-ttu-id="df140-170">[Vorgehensweise: Verwenden von benannten und optionalen Argumenten in der Office-Programmierung](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) </span><span class="sxs-lookup"><span data-stu-id="df140-170">[How to: Use Named and Optional Arguments in Office Programming](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) </span></span>  
 <span data-ttu-id="df140-171">[Verwenden von dynamischen Typen](../../../csharp/programming-guide/types/using-type-dynamic.md) </span><span class="sxs-lookup"><span data-stu-id="df140-171">[Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md) </span></span>  
 <span data-ttu-id="df140-172">[Verwenden von Konstruktoren](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) </span><span class="sxs-lookup"><span data-stu-id="df140-172">[Using Constructors](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) </span></span>  
 [<span data-ttu-id="df140-173">Verwenden von Indexern</span><span class="sxs-lookup"><span data-stu-id="df140-173">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)

