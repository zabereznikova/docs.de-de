---
title: Benannte und optionale Argumente – C#-Programmierhandbuch
description: Benannte Argumente in C# geben Argumente nach Name und nicht nach Position an. Optionale Argumente können ausgelassen werden.
ms.date: 07/20/2015
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
ms.openlocfilehash: 46b9dc23644e68aea2767f2b990fe7f243a4f357
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864981"
---
# <a name="named-and-optional-arguments-c-programming-guide"></a><span data-ttu-id="c8505-104">Benannte und optionale Argumente (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="c8505-104">Named and Optional Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="c8505-105">C# 4 führt benannte und optionale Argumente ein.</span><span class="sxs-lookup"><span data-stu-id="c8505-105">C# 4 introduces named and optional arguments.</span></span> <span data-ttu-id="c8505-106">*Benannte Argumente* ermöglichen es Ihnen, ein Argument für einen bestimmten Parameter anzugeben, indem Sie das Argument dem Parameternamen anstatt der Position des Parameters in der Parameterliste zuordnen.</span><span class="sxs-lookup"><span data-stu-id="c8505-106">*Named arguments* enable you to specify an argument for a particular parameter by associating the argument with the parameter's name rather than with the parameter's position in the parameter list.</span></span> <span data-ttu-id="c8505-107">*Optionale Argumente* ermöglichen es Ihnen, Argumente für einige Parameter auszulassen.</span><span class="sxs-lookup"><span data-stu-id="c8505-107">*Optional arguments* enable you to omit arguments for some parameters.</span></span> <span data-ttu-id="c8505-108">Beide Techniken können mit Methoden, Indexern, Konstruktoren und Delegaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c8505-108">Both techniques can be used with methods, indexers, constructors, and delegates.</span></span>  
  
 <span data-ttu-id="c8505-109">Wenn Sie benannte und optionale Argumente verwenden, werden die Argumente in der Reihenfolge ausgewertet, in der sie in der Argumentliste, nicht in der Parameterliste, erscheinen.</span><span class="sxs-lookup"><span data-stu-id="c8505-109">When you use named and optional arguments, the arguments are evaluated in the order in which they appear in the argument list, not the parameter list.</span></span>  
  
 <span data-ttu-id="c8505-110">Wenn Sie benannte und optionale Parameter zusammen verwenden, können Sie Argumente für nur ein paar Parameter aus einer Liste von optionalen Parametern bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c8505-110">Named and optional parameters, when used together, enable you to supply arguments for only a few parameters from a list of optional parameters.</span></span> <span data-ttu-id="c8505-111">Diese Funktion erleichtert den Zugriff auf COM-Schnittstellen wie etwa die Automatisierungs-APIs in Microsoft Office erheblich.</span><span class="sxs-lookup"><span data-stu-id="c8505-111">This capability greatly facilitates calls to COM interfaces such as the Microsoft Office Automation APIs.</span></span>  
  
## <a name="named-arguments"></a><span data-ttu-id="c8505-112">Benannte Argumente</span><span class="sxs-lookup"><span data-stu-id="c8505-112">Named Arguments</span></span>  
 <span data-ttu-id="c8505-113">Bei Verwendung benannter Argumente bleibt es Ihnen erspart, sich an die Reihenfolge von Parametern in den Parameterlisten von aufgerufenen Methoden zu erinnern oder sie nachzuschauen.</span><span class="sxs-lookup"><span data-stu-id="c8505-113">Named arguments free you from the need to remember or to look up the order of parameters in the parameter lists of called methods.</span></span> <span data-ttu-id="c8505-114">Der Parameter für jedes Argument kann vom Parameternamen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c8505-114">The parameter for each argument can be specified by parameter name.</span></span> <span data-ttu-id="c8505-115">Eine Funktion, die beispielsweise Details zu einer Bestellung ausgibt (z.B. Verkäufername, Bestellnummer und Produktname), kann standardmäßig aufgerufen werden, indem anhand der Position Argumente in der Reihenfolge gesendet werden, die von der Funktion definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c8505-115">For example, a function that prints order details (such as, seller name, order number & product name) can be called in the standard way by sending arguments by position, in the order defined by the function.</span></span>
  
 `PrintOrderDetails("Gift Shop", 31, "Red Mug");`
  
 <span data-ttu-id="c8505-116">Wenn Sie sich nicht an die Reihenfolge der Parameter erinnern, aber deren Namen wissen, können Sie die Argumente in einer beliebigen Reihenfolge senden.</span><span class="sxs-lookup"><span data-stu-id="c8505-116">If you do not remember the order of the parameters but know their names, you can send the arguments in any order.</span></span>  
  
 `PrintOrderDetails(orderNum: 31, productName: "Red Mug", sellerName: "Gift Shop");`
  
 `PrintOrderDetails(productName: "Red Mug", sellerName: "Gift Shop", orderNum: 31);`
  
 <span data-ttu-id="c8505-117">Benannte Argumente verbessern auch die Lesbarkeit des Codes, indem sie identifizieren, was jedes Argument darstellt.</span><span class="sxs-lookup"><span data-stu-id="c8505-117">Named arguments also improve the readability of your code by identifying what each argument represents.</span></span> <span data-ttu-id="c8505-118">In der folgenden Beispielmethode darf `sellerName` nicht NULL sein oder Leerraum enthalten.</span><span class="sxs-lookup"><span data-stu-id="c8505-118">In the example method below, the `sellerName` cannot be null or white space.</span></span> <span data-ttu-id="c8505-119">Da es sich bei `sellerName` und `productName` um Zeichenfolgentypen handelt, sollten Sie benannte Argumente verwenden, anstatt Argumente nach Position zu senden, um die beiden Parameter zu unterscheiden und die Leser des Codes nicht zu verwirren.</span><span class="sxs-lookup"><span data-stu-id="c8505-119">As both `sellerName` and `productName` are string types, instead of sending arguments by position, it makes sense to use named arguments to disambiguate the two and reduce confusion for anyone reading the code.</span></span>
  
 <span data-ttu-id="c8505-120">Benannte Argumente sind länger gültig, wenn sie mit positionellen Argumenten verwendet werden, da</span><span class="sxs-lookup"><span data-stu-id="c8505-120">Named arguments, when used with positional arguments, are valid as long as</span></span>

- <span data-ttu-id="c8505-121">ihnen keine positionellen Argumente folgen, bzw. da</span><span class="sxs-lookup"><span data-stu-id="c8505-121">they're not followed by any positional arguments, or</span></span>

 `PrintOrderDetails("Gift Shop", 31, productName: "Red Mug");`

- <span data-ttu-id="c8505-122">sie _ab C# 7.2_ in der richtigen Position verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c8505-122">_starting with C# 7.2_, they're used in the correct position.</span></span> <span data-ttu-id="c8505-123">Im folgenden Beispiel befindet sich der Parameter `orderNum` in der richtigen Position, ist jedoch nicht explizit benannt.</span><span class="sxs-lookup"><span data-stu-id="c8505-123">In the example below, the parameter `orderNum` is in the correct position but isn't explicitly named.</span></span>

 `PrintOrderDetails(sellerName: "Gift Shop", 31, productName: "Red Mug");`
  
 <span data-ttu-id="c8505-124">Positionelle Argumente, die auf fehlerhafte benannte Argumente folgen, sind ungültig.</span><span class="sxs-lookup"><span data-stu-id="c8505-124">Positional arguments that follow any out-of-order named arguments are invalid.</span></span>

 ```csharp
 // This generates CS1738: Named argument specifications must appear after all fixed arguments have been specified.
 PrintOrderDetails(productName: "Red Mug", 31, "Gift Shop");
 ```
  
## <a name="example"></a><span data-ttu-id="c8505-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c8505-125">Example</span></span>  
 <span data-ttu-id="c8505-126">Der folgende Code implementiert die Beispiele in diesem Abschnitt sowie einige zusätzliche Beispiele.</span><span class="sxs-lookup"><span data-stu-id="c8505-126">The following code implements the examples from this section along with some additional ones.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/program.cs#1)]  
  
## <a name="optional-arguments"></a><span data-ttu-id="c8505-127">Optionale Argumente</span><span class="sxs-lookup"><span data-stu-id="c8505-127">Optional Arguments</span></span>  
 <span data-ttu-id="c8505-128">Die Definition einer Methode, eines Konstruktors, eines Indexers oder Delegaten kann angeben, dass deren Parameter benötigt werden oder optional sind.</span><span class="sxs-lookup"><span data-stu-id="c8505-128">The definition of a method, constructor, indexer, or delegate can specify that its parameters are required or that they are optional.</span></span> <span data-ttu-id="c8505-129">Jeder Aufruf muss Argumente für alle benötigten Parameter bereitstellen, kann aber Argumente für optionale Parameter auslassen.</span><span class="sxs-lookup"><span data-stu-id="c8505-129">Any call must provide arguments for all required parameters, but can omit arguments for optional parameters.</span></span>  
  
 <span data-ttu-id="c8505-130">Jeder optionale Parameter hat einen Standardwert als Teil seiner Definition.</span><span class="sxs-lookup"><span data-stu-id="c8505-130">Each optional parameter has a default value as part of its definition.</span></span> <span data-ttu-id="c8505-131">Wenn für diesen Parameter kein Argument gesendet wird, wird der Standardwert verwendet.</span><span class="sxs-lookup"><span data-stu-id="c8505-131">If no argument is sent for that parameter, the default value is used.</span></span> <span data-ttu-id="c8505-132">Ein Standardwert muss einer der folgenden Typen von Ausdrücken sein:</span><span class="sxs-lookup"><span data-stu-id="c8505-132">A default value must be one of the following types of expressions:</span></span>  
  
- <span data-ttu-id="c8505-133">Ein konstanter Ausdruck</span><span class="sxs-lookup"><span data-stu-id="c8505-133">a constant expression;</span></span>  
  
- <span data-ttu-id="c8505-134">Ein Ausdruck der Form `new ValType()`, wobei `ValType` ein Werttyp wie [enum](../../language-reference/builtin-types/enum.md) oder [struct](../../language-reference/builtin-types/struct.md) ist</span><span class="sxs-lookup"><span data-stu-id="c8505-134">an expression of the form `new ValType()`, where `ValType` is a value type, such as an [enum](../../language-reference/builtin-types/enum.md) or a [struct](../../language-reference/builtin-types/struct.md);</span></span>  
  
- <span data-ttu-id="c8505-135">Ein Ausdruck in Form von [default(ValType)](../../language-reference/operators/default.md), wobei `ValType` ein Werttyp ist</span><span class="sxs-lookup"><span data-stu-id="c8505-135">an expression of the form [default(ValType)](../../language-reference/operators/default.md),  where `ValType` is a value type.</span></span>  
  
 <span data-ttu-id="c8505-136">Optionale Parameter werden am Ende der Parameterliste nach den erforderlichen Parametern definiert.</span><span class="sxs-lookup"><span data-stu-id="c8505-136">Optional parameters are defined at the end of the parameter list, after any required parameters.</span></span> <span data-ttu-id="c8505-137">Wenn der Aufrufer ein Argument für einen beliebigen Parameter aus einer Folge von optionalen Parametern bereitstellt, muss er Argumente für alle vorherigen optionalen Parameter bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c8505-137">If the caller provides an argument for any one of a succession of optional parameters, it must provide arguments for all preceding optional parameters.</span></span> <span data-ttu-id="c8505-138">Durch Trennzeichen getrennte Lücken in der Argumentliste werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c8505-138">Comma-separated gaps in the argument list are not supported.</span></span> <span data-ttu-id="c8505-139">Im folgenden Code wird z.B. die Instanzmethode `ExampleMethod` mit einem erforderlichen und zwei optionalen Parametern definiert.</span><span class="sxs-lookup"><span data-stu-id="c8505-139">For example, in the following code, instance method `ExampleMethod` is defined with one required and two optional parameters.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/optional.cs#15)]  
  
 <span data-ttu-id="c8505-140">Der folgende Aufruf von `ExampleMethod` verursacht einen Compilerfehler, da ein Argument für den dritten Parameter, aber nicht für den zweiten, bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c8505-140">The following call to `ExampleMethod` causes a compiler error, because an argument is provided for the third parameter but not for the second.</span></span>  
  
 `//anExample.ExampleMethod(3, ,4);`  
  
 <span data-ttu-id="c8505-141">Wenn Sie den Namen des dritten Parameters kennen, können Sie ein benanntes Argument zum Ausführen der Aufgabe verwenden.</span><span class="sxs-lookup"><span data-stu-id="c8505-141">However, if you know the name of the third parameter, you can use a named argument to accomplish the task.</span></span>  
  
 `anExample.ExampleMethod(3, optionalint: 4);`  
  
 <span data-ttu-id="c8505-142">IntelliSense verwendet wie in der folgenden Abbildung gezeigt zum Anzeigen von optionalen Parametern Klammern:</span><span class="sxs-lookup"><span data-stu-id="c8505-142">IntelliSense uses brackets to indicate optional parameters, as shown in the following illustration:</span></span>  
  
 ![Screenshot der IntelliSense-QuickInfo für die Methode „ExampleMethod“](./media/named-and-optional-arguments/optional-examplemethod-parameters.png)  
  
> [!NOTE]
> <span data-ttu-id="c8505-144">Sie können auch optionale Parameter mit der .NET-Klasse <xref:System.Runtime.InteropServices.OptionalAttribute> deklarieren.</span><span class="sxs-lookup"><span data-stu-id="c8505-144">You can also declare optional parameters by using the .NET <xref:System.Runtime.InteropServices.OptionalAttribute> class.</span></span> <span data-ttu-id="c8505-145">`OptionalAttribute`-Parameter erfordern keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="c8505-145">`OptionalAttribute` parameters do not require a default value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8505-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c8505-146">Example</span></span>  
 <span data-ttu-id="c8505-147">Im folgenden Beispiel hat der Konstruktor für `ExampleClass` einen Parameter, der optional ist.</span><span class="sxs-lookup"><span data-stu-id="c8505-147">In the following example, the constructor for `ExampleClass` has one parameter, which is optional.</span></span> <span data-ttu-id="c8505-148">Instanzmethode `ExampleMethod` hat einen erforderlichen Parameter (`required`) und zwei optionale Parameter (`optionalstr` und `optionalint`).</span><span class="sxs-lookup"><span data-stu-id="c8505-148">Instance method `ExampleMethod` has one required parameter, `required`, and two optional parameters, `optionalstr` and `optionalint`.</span></span> <span data-ttu-id="c8505-149">Der Code in `Main` veranschaulicht die unterschiedlichen Methoden, in denen der Konstruktor und die Methode aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="c8505-149">The code in `Main` shows the different ways in which the constructor and method can be invoked.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/optional.cs#2)]  
  
## <a name="com-interfaces"></a><span data-ttu-id="c8505-150">COM-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c8505-150">COM Interfaces</span></span>  
 <span data-ttu-id="c8505-151">Benannte und optionale Argumente verbessern zusammen mit der Unterstützung von dynamischen Objekten und anderen Verbesserungen deutlich die Interoperabilität mit COM-APIs wie Office-Automatisierungs-APIs.</span><span class="sxs-lookup"><span data-stu-id="c8505-151">Named and optional arguments, along with support for dynamic objects and other enhancements, greatly improve interoperability with COM APIs, such as Office Automation APIs.</span></span>  
  
 <span data-ttu-id="c8505-152">Beispielsweise verfügt die Methode <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> in der <xref:Microsoft.Office.Interop.Excel.Range>-Schnittstelle von Microsoft Office Excel über sieben Parameter, von denen alle optional sind.</span><span class="sxs-lookup"><span data-stu-id="c8505-152">For example, the <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> method in the Microsoft Office Excel <xref:Microsoft.Office.Interop.Excel.Range> interface has seven parameters, all of which are optional.</span></span> <span data-ttu-id="c8505-153">Diese Parameter sind in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="c8505-153">These parameters are shown in the following illustration:</span></span>  
  
 ![Screenshot der IntelliSense-QuickInfo für die Methode „AutoFormat“](./media/named-and-optional-arguments/autoformat-method-parameters.png)  
  
 <span data-ttu-id="c8505-155">In C# 3.0 und früheren Versionen wird ein Argument für jeden Parameter benötigt, wie im folgenden Beispiel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c8505-155">In C# 3.0 and earlier versions, an argument is required for each parameter, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/namedandoptcom.cs#3)]  
  
 <span data-ttu-id="c8505-156">Sie können jedoch den Aufruf an `AutoFormat` erheblich vereinfachen, indem Sie benannte und optionale Argumente verwenden, die in C# 4.0 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="c8505-156">However, you can greatly simplify the call to `AutoFormat` by using named and optional arguments, introduced in C# 4.0.</span></span> <span data-ttu-id="c8505-157">Benannte und optionale Parameter helfen Ihnen dabei, das Argument für einen optionalen Parameter auszulassen, wenn Sie den Standardwert des Parameters nicht ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="c8505-157">Named and optional arguments enable you to omit the argument for an optional parameter if you do not want to change the parameter's default value.</span></span> <span data-ttu-id="c8505-158">Im folgenden Aufruf wird ein Wert für nur einen der sieben Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="c8505-158">In the following call, a value is specified for only one of the seven parameters.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/namedandoptcom.cs#13)]  
  
 <span data-ttu-id="c8505-159">Weitere Informationen und Beispiele finden Sie unter [Vorgehensweise: Verwenden von benannten und optionalen Argumenten in der Office-Programmierung](./how-to-use-named-and-optional-arguments-in-office-programming.md) und [Vorgehensweise: Zugreifen auf Office Interop-Objekte mithilfe von C#-Funktionen](../interop/how-to-access-office-onterop-objects.md).</span><span class="sxs-lookup"><span data-stu-id="c8505-159">For more information and examples, see [How to use named and optional arguments in Office programming](./how-to-use-named-and-optional-arguments-in-office-programming.md) and [How to access Office interop objects by using C# features](../interop/how-to-access-office-onterop-objects.md).</span></span>  
  
## <a name="overload-resolution"></a><span data-ttu-id="c8505-160">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="c8505-160">Overload Resolution</span></span>  
 <span data-ttu-id="c8505-161">Das Verwenden von benannten und optionalen Argumenten wirkt sich auf die Überladungsauflösung folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="c8505-161">Use of named and optional arguments affects overload resolution in the following ways:</span></span>  
  
- <span data-ttu-id="c8505-162">Eine Methode, ein Indexer oder ein Konstruktor ist ein Kandidat für die Ausführung, wenn jeder der Parameter entweder optional ist oder über Namen oder Position auf ein einzelnes Argument in der aufrufenden Anweisung reagiert. Dieses Argument kann in dem Typ des Parameters konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="c8505-162">A method, indexer, or constructor is a candidate for execution if each of its parameters either is optional or corresponds, by name or by position, to a single argument in the calling statement, and that argument can be converted to the type of the parameter.</span></span>  
  
- <span data-ttu-id="c8505-163">Wenn mehr als ein Kandidat gefunden wird, werden die Regeln der Überladungsauflösung als bevorzugte Konvertierungen auf die Argumente angewandt, die ausdrücklich angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="c8505-163">If more than one candidate is found, overload resolution rules for preferred conversions are applied to the arguments that are explicitly specified.</span></span> <span data-ttu-id="c8505-164">Ausgelassene Argumente für optionale Parameter werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c8505-164">Omitted arguments for optional parameters are ignored.</span></span>  
  
- <span data-ttu-id="c8505-165">Wenn zwei Kandidaten gleich gut geeignet sind, wird ein Kandidat bevorzugt, der keine optionalen Parameter besitzt, für die Argumente im Aufruf ausgelassen wurden.</span><span class="sxs-lookup"><span data-stu-id="c8505-165">If two candidates are judged to be equally good, preference goes to a candidate that does not have optional parameters for which arguments were omitted in the call.</span></span> <span data-ttu-id="c8505-166">Dies ist die Folge einer allgemeinen Präferenz bei der Überladungsauflösung für Kandidaten, die weniger Parameter besitzen.</span><span class="sxs-lookup"><span data-stu-id="c8505-166">This is a consequence of a general preference in overload resolution for candidates that have fewer parameters.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c8505-167">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="c8505-167">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c8505-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8505-168">See also</span></span>

- [<span data-ttu-id="c8505-169">Vorgehensweise: Verwenden von benannten und optionalen Argumenten in der Office-Programmierung</span><span class="sxs-lookup"><span data-stu-id="c8505-169">How to use named and optional arguments in Office programming</span></span>](./how-to-use-named-and-optional-arguments-in-office-programming.md)
- [<span data-ttu-id="c8505-170">Verwenden von dynamischen Typen</span><span class="sxs-lookup"><span data-stu-id="c8505-170">Using Type dynamic</span></span>](../types/using-type-dynamic.md)
- [<span data-ttu-id="c8505-171">Verwenden von Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="c8505-171">Using Constructors</span></span>](./using-constructors.md)
- [<span data-ttu-id="c8505-172">Verwenden von Indexern</span><span class="sxs-lookup"><span data-stu-id="c8505-172">Using Indexers</span></span>](../indexers/using-indexers.md)
