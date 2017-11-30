---
title: Benannte und optionale Argumente (C#-Programmierhandbuch)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- namedParameter_CSharpKeyword
- cs_namedParameter
helpviewer_keywords:
- parameters [C#], named
- named arguments [C#]
- arguments [C#], named
- optional arguments [C#]
- arguments [C#], optional
- parameters [C#], optional
- named and optional arguments [C#]
ms.assetid: 839c960c-c2dc-4d05-af4d-ca5428e54008
caps.latest.revision: "43"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e6fceb569a79b5988171f06ae6c09d86b5fc667d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="named-and-optional-arguments-c-programming-guide"></a><span data-ttu-id="f8951-102">Benannte und optionale Argumente (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="f8951-102">Named and Optional Arguments (C# Programming Guide)</span></span>
[!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)]<span data-ttu-id="f8951-103"> führt benannte und optionale Argumente ein.</span><span class="sxs-lookup"><span data-stu-id="f8951-103"> introduces named and optional arguments.</span></span> <span data-ttu-id="f8951-104">*Benannte Argumente* ermöglichen es Ihnen, ein Argument für einen bestimmten Parameter anzugeben, indem Sie das Argument dem Parameternamen anstatt der Position des Parameters in der Parameterliste zuordnen.</span><span class="sxs-lookup"><span data-stu-id="f8951-104">*Named arguments* enable you to specify an argument for a particular parameter by associating the argument with the parameter's name rather than with the parameter's position in the parameter list.</span></span> <span data-ttu-id="f8951-105">*Optionale Argumente* ermöglichen es Ihnen, Argumente für einige Parameter auszulassen.</span><span class="sxs-lookup"><span data-stu-id="f8951-105">*Optional arguments* enable you to omit arguments for some parameters.</span></span> <span data-ttu-id="f8951-106">Beide Techniken können mit Methoden, Indexern, Konstruktoren und Delegaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f8951-106">Both techniques can be used with methods, indexers, constructors, and delegates.</span></span>  
  
 <span data-ttu-id="f8951-107">Wenn Sie benannte und optionale Argumente verwenden, werden die Argumente in der Reihenfolge ausgewertet, in der sie in der Argumentliste, nicht in der Parameterliste, erscheinen.</span><span class="sxs-lookup"><span data-stu-id="f8951-107">When you use named and optional arguments, the arguments are evaluated in the order in which they appear in the argument list, not the parameter list.</span></span>  
  
 <span data-ttu-id="f8951-108">Wenn Sie benannte und optionale Parameter zusammen verwenden, können Sie Argumente für nur ein paar Parameter aus einer Liste von optionalen Parametern bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f8951-108">Named and optional parameters, when used together, enable you to supply arguments for only a few parameters from a list of optional parameters.</span></span> <span data-ttu-id="f8951-109">Diese Funktion erleichtert den Zugriff auf COM-Schnittstellen wie etwa die Automatisierungs-APIs in Microsoft Office erheblich.</span><span class="sxs-lookup"><span data-stu-id="f8951-109">This capability greatly facilitates calls to COM interfaces such as the Microsoft Office Automation APIs.</span></span>  
  
## <a name="named-arguments"></a><span data-ttu-id="f8951-110">Benannte Argumente</span><span class="sxs-lookup"><span data-stu-id="f8951-110">Named Arguments</span></span>  
 <span data-ttu-id="f8951-111">Bei Verwendung benannter Argumente bleibt es Ihnen erspart, sich an die Reihenfolge von Parametern in den Parameterlisten von aufgerufenen Methoden zu erinnern oder sie nachzuschauen.</span><span class="sxs-lookup"><span data-stu-id="f8951-111">Named arguments free you from the need to remember or to look up the order of parameters in the parameter lists of called methods.</span></span> <span data-ttu-id="f8951-112">Der Parameter für jedes Argument kann vom Parameternamen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f8951-112">The parameter for each argument can be specified by parameter name.</span></span> <span data-ttu-id="f8951-113">Z. B. eine Funktion, die Bestelldetails ausgibt (z. B. Verkäufer Name, Order Anzahl & Product Name) kann auf die übliche Weise aufgerufen werden, durch das Senden von Argumenten nach Position in der Reihenfolge von der Funktion definiert.</span><span class="sxs-lookup"><span data-stu-id="f8951-113">For example, a function that prints order details (such as, seller name, order number & product name) can be called in the standard way by sending arguments by position, in the order defined by the function.</span></span>
  
 `PrintOrderDetails("Gift Shop", 31, "Red Mug");`
  
 <span data-ttu-id="f8951-114">Wenn Sie sich nicht auf die Reihenfolge der Parameter erinnern, aber ihre Namen kennen, können Sie die Argumente in beliebiger Reihenfolge senden.</span><span class="sxs-lookup"><span data-stu-id="f8951-114">If you do not remember the order of the parameters but know their names, you can send the arguments in any order.</span></span>  
  
 `PrintOrderDetails(orderNum: 31, productName: "Red Mug", sellerName: "Gift Shop");`
  
 `PrintOrderDetails(productName: "Red Mug", sellerName: "Gift Shop", orderNum: 31);`
  
 <span data-ttu-id="f8951-115">Benannte Argumente verbessern auch die Lesbarkeit des Codes, indem sie identifizieren, was jedes Argument darstellt.</span><span class="sxs-lookup"><span data-stu-id="f8951-115">Named arguments also improve the readability of your code by identifying what each argument represents.</span></span> <span data-ttu-id="f8951-116">In der folgenden Beispielmethode der `sellerName` darf nicht Null oder leer sein.</span><span class="sxs-lookup"><span data-stu-id="f8951-116">In the example method below, the `sellerName` cannot be null or whitespace.</span></span> <span data-ttu-id="f8951-117">Beide `sellerName` und `productName` sind Zeichenfolgentypen, anstatt das Senden von Argumenten nach Position, ist es sinnvoll, benannte Argumente verwenden, um die beiden eindeutig und weniger Verwirrung für jede Person beim Lesen des Codes.</span><span class="sxs-lookup"><span data-stu-id="f8951-117">As both `sellerName` and `productName` are string types, instead of sending arguments by position, it makes sense to use named arguments to disambiguate the two and reduce confusion for anyone reading the code.</span></span>
  
 <span data-ttu-id="f8951-118">Benannte Argumente, bei der Verwendung mit Positionsargumenten, gelten als</span><span class="sxs-lookup"><span data-stu-id="f8951-118">Named arguments, when used with positional arguments, are valid as long as</span></span> 

- <span data-ttu-id="f8951-119">Sie sind keine Positionsargumente gefolgt oder</span><span class="sxs-lookup"><span data-stu-id="f8951-119">they're not followed by any positional arguments, or</span></span>

 `PrintOrderDetails("Gift Shop", 31, productName: "Red Mug");`

- <span data-ttu-id="f8951-120">_beginnend mit c# 7.2_, sie sind in der richtigen Position verwendet.</span><span class="sxs-lookup"><span data-stu-id="f8951-120">_starting with C# 7.2_, they're used in the correct position.</span></span> <span data-ttu-id="f8951-121">Im folgenden Beispiel ist der Parameter `orderNum` befindet sich in der richtigen Position aber wird nicht explizit benannt.</span><span class="sxs-lookup"><span data-stu-id="f8951-121">In the example below, the parameter `orderNum` is in the correct position but isn't explicitly named.</span></span>

 `PrintOrderDetails(sellerName: "Gift Shop", 31, productName: "Red Mug");`
  
 <span data-ttu-id="f8951-122">Benannte Argumente außerhalb der normalen Reihenfolge sind jedoch ungültig, wenn sie von positionellen Argumenten befolgt werden.</span><span class="sxs-lookup"><span data-stu-id="f8951-122">However, out-of-order named arguments are invalid if they're followed by positional arguments.</span></span>

 ```csharp
 // This generates CS1738: Named argument specifications must appear after all fixed arguments have been specified.
 PrintOrderDetails(productName: "Red Mug", 31, "Gift Shop");
 ```
  
## <a name="example"></a><span data-ttu-id="f8951-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f8951-123">Example</span></span>  
 <span data-ttu-id="f8951-124">Der folgende Code implementiert die Beispielen in diesem Abschnitt sowie einige zusätzlichen Spalten.</span><span class="sxs-lookup"><span data-stu-id="f8951-124">The following code implements the examples from this section along with some additional ones.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_1.cs)]  
  
## <a name="optional-arguments"></a><span data-ttu-id="f8951-125">Optionale Argumente</span><span class="sxs-lookup"><span data-stu-id="f8951-125">Optional Arguments</span></span>  
 <span data-ttu-id="f8951-126">Die Definition einer Methode, eines Konstruktors, eines Indexers oder Delegaten kann angeben, dass deren Parameter benötigt werden oder optional sind.</span><span class="sxs-lookup"><span data-stu-id="f8951-126">The definition of a method, constructor, indexer, or delegate can specify that its parameters are required or that they are optional.</span></span> <span data-ttu-id="f8951-127">Jeder Aufruf muss Argumente für alle benötigten Parameter bereitstellen, kann aber Argumente für optionale Parameter auslassen.</span><span class="sxs-lookup"><span data-stu-id="f8951-127">Any call must provide arguments for all required parameters, but can omit arguments for optional parameters.</span></span>  
  
 <span data-ttu-id="f8951-128">Jeder optionale Parameter hat einen Standardwert als Teil seiner Definition.</span><span class="sxs-lookup"><span data-stu-id="f8951-128">Each optional parameter has a default value as part of its definition.</span></span> <span data-ttu-id="f8951-129">Wenn für diesen Parameter kein Argument gesendet wird, wird der Standardwert verwendet.</span><span class="sxs-lookup"><span data-stu-id="f8951-129">If no argument is sent for that parameter, the default value is used.</span></span> <span data-ttu-id="f8951-130">Ein Standardwert muss einer der folgenden Typen von Ausdrücken sein:</span><span class="sxs-lookup"><span data-stu-id="f8951-130">A default value must be one of the following types of expressions:</span></span>  
  
-   <span data-ttu-id="f8951-131">Ein konstanter Ausdruck</span><span class="sxs-lookup"><span data-stu-id="f8951-131">a constant expression;</span></span>  
  
-   <span data-ttu-id="f8951-132">Ein Ausdruck der Form `new ValType()`, wobei `ValType` ein Werttyp wie [enum](../../../csharp/language-reference/keywords/enum.md) oder [struct](../../../csharp/programming-guide/classes-and-structs/structs.md) ist</span><span class="sxs-lookup"><span data-stu-id="f8951-132">an expression of the form `new ValType()`, where `ValType` is a value type, such as an [enum](../../../csharp/language-reference/keywords/enum.md) or a [struct](../../../csharp/programming-guide/classes-and-structs/structs.md);</span></span>  
  
-   <span data-ttu-id="f8951-133">Ein Ausdruck in Form von [default(ValType)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md), wobei `ValType` ein Werttyp ist</span><span class="sxs-lookup"><span data-stu-id="f8951-133">an expression of the form [default(ValType)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md),  where `ValType` is a value type.</span></span>  
  
 <span data-ttu-id="f8951-134">Optionale Parameter werden am Ende der Parameterliste nach den erforderlichen Parametern definiert.</span><span class="sxs-lookup"><span data-stu-id="f8951-134">Optional parameters are defined at the end of the parameter list, after any required parameters.</span></span> <span data-ttu-id="f8951-135">Wenn der Aufrufer ein Argument für einen beliebigen Parameter aus einer Folge von optionalen Parametern bereitstellt, muss er Argumente für alle vorherigen optionalen Parameter bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f8951-135">If the caller provides an argument for any one of a succession of optional parameters, it must provide arguments for all preceding optional parameters.</span></span> <span data-ttu-id="f8951-136">Durch Trennzeichen getrennte Lücken in der Argumentliste werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f8951-136">Comma-separated gaps in the argument list are not supported.</span></span> <span data-ttu-id="f8951-137">Im folgenden Code wird z.B. die Instanzmethode `ExampleMethod` mit einem erforderlichen und zwei optionalen Parametern definiert.</span><span class="sxs-lookup"><span data-stu-id="f8951-137">For example, in the following code, instance method `ExampleMethod` is defined with one required and two optional parameters.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_2.cs)]  
  
 <span data-ttu-id="f8951-138">Der folgende Aufruf von `ExampleMethod` verursacht einen Compilerfehler, da ein Argument für den dritten Parameter, aber nicht für den zweiten, bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f8951-138">The following call to `ExampleMethod` causes a compiler error, because an argument is provided for the third parameter but not for the second.</span></span>  
  
 `//anExample.ExampleMethod(3, ,4);`  
  
 <span data-ttu-id="f8951-139">Wenn Sie den Namen des dritten Parameters kennen, können Sie ein benanntes Argument zum Ausführen der Aufgabe verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8951-139">However, if you know the name of the third parameter, you can use a named argument to accomplish the task.</span></span>  
  
 `anExample.ExampleMethod(3, optionalint: 4);`  
  
 <span data-ttu-id="f8951-140">IntelliSense verwendet zum Anzeigen von optionalen Parametern Klammern, wie in folgender Abbildung veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="f8951-140">IntelliSense uses brackets to indicate optional parameters, as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="f8951-141">![IntelliSense-QuickInfo für die Methode „ExampleMethod.“](../../../csharp/programming-guide/classes-and-structs/media/optional_parameters.png "Optional_Parameters")</span><span class="sxs-lookup"><span data-stu-id="f8951-141">![IntelliSense Quick Info for method ExampleMethod.](../../../csharp/programming-guide/classes-and-structs/media/optional_parameters.png "Optional_Parameters")</span></span>  
<span data-ttu-id="f8951-142">Optionale Parameter in ExampleMethod</span><span class="sxs-lookup"><span data-stu-id="f8951-142">Optional parameters in ExampleMethod</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8951-143">Sie können auch optionale Parameter mit der .NET-Klasse <xref:System.Runtime.InteropServices.OptionalAttribute> deklarieren.</span><span class="sxs-lookup"><span data-stu-id="f8951-143">You can also declare optional parameters by using the .NET <xref:System.Runtime.InteropServices.OptionalAttribute> class.</span></span> <span data-ttu-id="f8951-144">`OptionalAttribute`-Parameter erfordern keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="f8951-144">`OptionalAttribute` parameters do not require a default value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8951-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f8951-145">Example</span></span>  
 <span data-ttu-id="f8951-146">Im folgenden Beispiel hat der Konstruktor für `ExampleClass` einen Parameter, der optional ist.</span><span class="sxs-lookup"><span data-stu-id="f8951-146">In the following example, the constructor for `ExampleClass` has one parameter, which is optional.</span></span> <span data-ttu-id="f8951-147">Instanzmethode `ExampleMethod` hat einen erforderlichen Parameter (`required`) und zwei optionale Parameter (`optionalstr` und `optionalint`).</span><span class="sxs-lookup"><span data-stu-id="f8951-147">Instance method `ExampleMethod` has one required parameter, `required`, and two optional parameters, `optionalstr` and `optionalint`.</span></span> <span data-ttu-id="f8951-148">Der Code in `Main` veranschaulicht die unterschiedlichen Methoden, in denen der Konstruktor und die Methode aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="f8951-148">The code in `Main` shows the different ways in which the constructor and method can be invoked.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_3.cs)]  
  
## <a name="com-interfaces"></a><span data-ttu-id="f8951-149">COM-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f8951-149">COM Interfaces</span></span>  
 <span data-ttu-id="f8951-150">Benannte und optionale Argumente verbessern zusammen mit der Unterstützung von dynamischen Objekten und anderen Verbesserungen deutlich die Interoperabilität mit COM-APIs wie Office-Automatisierungs-APIs.</span><span class="sxs-lookup"><span data-stu-id="f8951-150">Named and optional arguments, along with support for dynamic objects and other enhancements, greatly improve interoperability with COM APIs, such as Office Automation APIs.</span></span>  
  
 <span data-ttu-id="f8951-151">Die Methode [AutoFormat](http://go.microsoft.com/fwlink/?LinkId=148201) hat z.B. in der Schnittstelle [Bereich](http://go.microsoft.com/fwlink/?LinkId=148196) von Microsoft Office Excel sieben Parameter, von denen alle optional sind.</span><span class="sxs-lookup"><span data-stu-id="f8951-151">For example, the [AutoFormat](http://go.microsoft.com/fwlink/?LinkId=148201) method in the Microsoft Office Excel [Range](http://go.microsoft.com/fwlink/?LinkId=148196) interface has seven parameters, all of which are optional.</span></span> <span data-ttu-id="f8951-152">Diese Parameter sind in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f8951-152">These parameters are shown in the following illustration.</span></span>  
  
 <span data-ttu-id="f8951-153">![IntelliSense-QuickInfo für die AutoFormat-Methode.](../../../csharp/programming-guide/classes-and-structs/media/autoformat_parameters.png "AutoFormat_Parameters")</span><span class="sxs-lookup"><span data-stu-id="f8951-153">![IntelliSense Quick Info for the AutoFormat method.](../../../csharp/programming-guide/classes-and-structs/media/autoformat_parameters.png "AutoFormat_Parameters")</span></span>  
<span data-ttu-id="f8951-154">AutoFormat-Parameter</span><span class="sxs-lookup"><span data-stu-id="f8951-154">AutoFormat parameters</span></span>  
  
 <span data-ttu-id="f8951-155">In C# 3.0 und früheren Versionen wird ein Argument für jeden Parameter benötigt, wie im folgenden Beispiel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f8951-155">In C# 3.0 and earlier versions, an argument is required for each parameter, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_4.cs)]  
  
 <span data-ttu-id="f8951-156">Sie können jedoch den Aufruf an `AutoFormat` erheblich vereinfachen, indem Sie benannte und optionale Argumente verwenden, die in C# 4.0 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="f8951-156">However, you can greatly simplify the call to `AutoFormat` by using named and optional arguments, introduced in C# 4.0.</span></span> <span data-ttu-id="f8951-157">Benannte und optionale Parameter helfen Ihnen dabei, das Argument für einen optionalen Parameter auszulassen, wenn Sie den Standardwert des Parameters nicht ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="f8951-157">Named and optional arguments enable you to omit the argument for an optional parameter if you do not want to change the parameter's default value.</span></span> <span data-ttu-id="f8951-158">Im folgenden Aufruf wird ein Wert für nur einen der sieben Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="f8951-158">In the following call, a value is specified for only one of the seven parameters.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_5.cs)]  
  
 <span data-ttu-id="f8951-159">Weitere Informationen und Beispiele finden Sie unter [Vorgehensweise: Verwenden von benannten und optionalen Argumenten in der Office-Programmierung](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) und [Vorgehensweise: Zugreifen auf Office Interop-Objekte mithilfe von Visual C#-Funktionen](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span><span class="sxs-lookup"><span data-stu-id="f8951-159">For more information and examples, see [How to: Use Named and Optional Arguments in Office Programming](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) and [How to: Access Office Interop Objects by Using Visual C# Features](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span></span>  
  
## <a name="overload-resolution"></a><span data-ttu-id="f8951-160">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="f8951-160">Overload Resolution</span></span>  
 <span data-ttu-id="f8951-161">Das Verwenden von benannten und optionalen Argumenten wirkt sich auf die Überladungsauflösung folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="f8951-161">Use of named and optional arguments affects overload resolution in the following ways:</span></span>  
  
-   <span data-ttu-id="f8951-162">Eine Methode, ein Indexer oder ein Konstruktor ist ein Kandidat für die Ausführung, wenn jeder der Parameter entweder optional ist oder über Namen oder Position auf ein einzelnes Argument in der aufrufenden Anweisung reagiert. Dieses Argument kann in dem Typ des Parameters konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="f8951-162">A method, indexer, or constructor is a candidate for execution if each of its parameters either is optional or corresponds, by name or by position, to a single argument in the calling statement, and that argument can be converted to the type of the parameter.</span></span>  
  
-   <span data-ttu-id="f8951-163">Wenn mehr als ein Kandidat gefunden wird, werden die Regeln der Überladungsauflösung als bevorzugte Konvertierungen auf die Argumente angewandt, die ausdrücklich angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="f8951-163">If more than one candidate is found, overload resolution rules for preferred conversions are applied to the arguments that are explicitly specified.</span></span> <span data-ttu-id="f8951-164">Ausgelassene Argumente für optionale Parameter werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="f8951-164">Omitted arguments for optional parameters are ignored.</span></span>  
  
-   <span data-ttu-id="f8951-165">Wenn zwei Kandidaten gleich gut geeignet sind, wird ein Kandidat bevorzugt, der keine optionalen Parameter besitzt, für die Argumente im Aufruf ausgelassen wurden.</span><span class="sxs-lookup"><span data-stu-id="f8951-165">If two candidates are judged to be equally good, preference goes to a candidate that does not have optional parameters for which arguments were omitted in the call.</span></span> <span data-ttu-id="f8951-166">Dies ist die Folge einer allgemeinen Präferenz bei der Überladungsauflösung für Kandidaten, die weniger Parameter besitzen.</span><span class="sxs-lookup"><span data-stu-id="f8951-166">This is a consequence of a general preference in overload resolution for candidates that have fewer parameters.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f8951-167">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="f8951-167">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f8951-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8951-168">See Also</span></span>  
 [<span data-ttu-id="f8951-169">Gewusst wie: Verwenden von benannten und optionalen Argumenten in der Office-Programmierung</span><span class="sxs-lookup"><span data-stu-id="f8951-169">How to: Use Named and Optional Arguments in Office Programming</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)  
 [<span data-ttu-id="f8951-170">Verwenden von dynamischen Typen</span><span class="sxs-lookup"><span data-stu-id="f8951-170">Using Type dynamic</span></span>](../../../csharp/programming-guide/types/using-type-dynamic.md)  
 [<span data-ttu-id="f8951-171">Verwenden von Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="f8951-171">Using Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
 [<span data-ttu-id="f8951-172">Verwenden von Indexern</span><span class="sxs-lookup"><span data-stu-id="f8951-172">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)
