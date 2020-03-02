---
title: Benannte und optionale Argumente – C#-Programmierhandbuch
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
ms.openlocfilehash: 3685482caebd892c460a3cc2ecf3a22acbe3c9ec
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "77673406"
---
# <a name="named-and-optional-arguments-c-programming-guide"></a><span data-ttu-id="1c5b9-102">Benannte und optionale Argumente (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="1c5b9-102">Named and Optional Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="1c5b9-103">C# 4 führt benannte und optionale Argumente ein.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-103">C# 4 introduces named and optional arguments.</span></span> <span data-ttu-id="1c5b9-104">*Benannte Argumente* ermöglichen es Ihnen, ein Argument für einen bestimmten Parameter anzugeben, indem Sie das Argument dem Parameternamen anstatt der Position des Parameters in der Parameterliste zuordnen.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-104">*Named arguments* enable you to specify an argument for a particular parameter by associating the argument with the parameter's name rather than with the parameter's position in the parameter list.</span></span> <span data-ttu-id="1c5b9-105">*Optionale Argumente* ermöglichen es Ihnen, Argumente für einige Parameter auszulassen.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-105">*Optional arguments* enable you to omit arguments for some parameters.</span></span> <span data-ttu-id="1c5b9-106">Beide Techniken können mit Methoden, Indexern, Konstruktoren und Delegaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-106">Both techniques can be used with methods, indexers, constructors, and delegates.</span></span>  
  
 <span data-ttu-id="1c5b9-107">Wenn Sie benannte und optionale Argumente verwenden, werden die Argumente in der Reihenfolge ausgewertet, in der sie in der Argumentliste, nicht in der Parameterliste, erscheinen.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-107">When you use named and optional arguments, the arguments are evaluated in the order in which they appear in the argument list, not the parameter list.</span></span>  
  
 <span data-ttu-id="1c5b9-108">Wenn Sie benannte und optionale Parameter zusammen verwenden, können Sie Argumente für nur ein paar Parameter aus einer Liste von optionalen Parametern bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-108">Named and optional parameters, when used together, enable you to supply arguments for only a few parameters from a list of optional parameters.</span></span> <span data-ttu-id="1c5b9-109">Diese Funktion erleichtert den Zugriff auf COM-Schnittstellen wie etwa die Automatisierungs-APIs in Microsoft Office erheblich.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-109">This capability greatly facilitates calls to COM interfaces such as the Microsoft Office Automation APIs.</span></span>  
  
## <a name="named-arguments"></a><span data-ttu-id="1c5b9-110">Benannte Argumente</span><span class="sxs-lookup"><span data-stu-id="1c5b9-110">Named Arguments</span></span>  
 <span data-ttu-id="1c5b9-111">Bei Verwendung benannter Argumente bleibt es Ihnen erspart, sich an die Reihenfolge von Parametern in den Parameterlisten von aufgerufenen Methoden zu erinnern oder sie nachzuschauen.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-111">Named arguments free you from the need to remember or to look up the order of parameters in the parameter lists of called methods.</span></span> <span data-ttu-id="1c5b9-112">Der Parameter für jedes Argument kann vom Parameternamen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-112">The parameter for each argument can be specified by parameter name.</span></span> <span data-ttu-id="1c5b9-113">Eine Funktion, die beispielsweise Details zu einer Bestellung ausgibt (z.B. Verkäufername, Bestellnummer und Produktname), kann standardmäßig aufgerufen werden, indem anhand der Position Argumente in der Reihenfolge gesendet werden, die von der Funktion definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-113">For example, a function that prints order details (such as, seller name, order number & product name) can be called in the standard way by sending arguments by position, in the order defined by the function.</span></span>
  
 `PrintOrderDetails("Gift Shop", 31, "Red Mug");`
  
 <span data-ttu-id="1c5b9-114">Wenn Sie sich nicht an die Reihenfolge der Parameter erinnern, aber deren Namen wissen, können Sie die Argumente in einer beliebigen Reihenfolge senden.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-114">If you do not remember the order of the parameters but know their names, you can send the arguments in any order.</span></span>  
  
 `PrintOrderDetails(orderNum: 31, productName: "Red Mug", sellerName: "Gift Shop");`
  
 `PrintOrderDetails(productName: "Red Mug", sellerName: "Gift Shop", orderNum: 31);`
  
 <span data-ttu-id="1c5b9-115">Benannte Argumente verbessern auch die Lesbarkeit des Codes, indem sie identifizieren, was jedes Argument darstellt.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-115">Named arguments also improve the readability of your code by identifying what each argument represents.</span></span> <span data-ttu-id="1c5b9-116">In der folgenden Beispielmethode darf `sellerName` nicht NULL sein oder Leerraum enthalten.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-116">In the example method below, the `sellerName` cannot be null or white space.</span></span> <span data-ttu-id="1c5b9-117">Da es sich bei `sellerName` und `productName` um Zeichenfolgentypen handelt, sollten Sie benannte Argumente verwenden, anstatt Argumente nach Position zu senden, um die beiden Parameter zu unterscheiden und die Leser des Codes nicht zu verwirren.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-117">As both `sellerName` and `productName` are string types, instead of sending arguments by position, it makes sense to use named arguments to disambiguate the two and reduce confusion for anyone reading the code.</span></span>
  
 <span data-ttu-id="1c5b9-118">Benannte Argumente sind länger gültig, wenn sie mit positionellen Argumenten verwendet werden, da</span><span class="sxs-lookup"><span data-stu-id="1c5b9-118">Named arguments, when used with positional arguments, are valid as long as</span></span> 

- <span data-ttu-id="1c5b9-119">ihnen keine positionellen Argumente folgen, bzw. da</span><span class="sxs-lookup"><span data-stu-id="1c5b9-119">they're not followed by any positional arguments, or</span></span>

 `PrintOrderDetails("Gift Shop", 31, productName: "Red Mug");`

- <span data-ttu-id="1c5b9-120">sie _ab C# 7.2_ in der richtigen Position verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-120">_starting with C# 7.2_, they're used in the correct position.</span></span> <span data-ttu-id="1c5b9-121">Im folgenden Beispiel befindet sich der Parameter `orderNum` in der richtigen Position, ist jedoch nicht explizit benannt.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-121">In the example below, the parameter `orderNum` is in the correct position but isn't explicitly named.</span></span>

 `PrintOrderDetails(sellerName: "Gift Shop", 31, productName: "Red Mug");`
  
 <span data-ttu-id="1c5b9-122">Positionelle Argumente, die auf fehlerhafte benannte Argumente folgen, sind ungültig.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-122">Positional arguments that follow any out-of-order named arguments are invalid.</span></span>

 ```csharp
 // This generates CS1738: Named argument specifications must appear after all fixed arguments have been specified.
 PrintOrderDetails(productName: "Red Mug", 31, "Gift Shop");
 ```
  
## <a name="example"></a><span data-ttu-id="1c5b9-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1c5b9-123">Example</span></span>  
 <span data-ttu-id="1c5b9-124">Der folgende Code implementiert die Beispiele in diesem Abschnitt sowie einige zusätzliche Beispiele.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-124">The following code implements the examples from this section along with some additional ones.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/program.cs#1)]  
  
## <a name="optional-arguments"></a><span data-ttu-id="1c5b9-125">Optionale Argumente</span><span class="sxs-lookup"><span data-stu-id="1c5b9-125">Optional Arguments</span></span>  
 <span data-ttu-id="1c5b9-126">Die Definition einer Methode, eines Konstruktors, eines Indexers oder Delegaten kann angeben, dass deren Parameter benötigt werden oder optional sind.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-126">The definition of a method, constructor, indexer, or delegate can specify that its parameters are required or that they are optional.</span></span> <span data-ttu-id="1c5b9-127">Jeder Aufruf muss Argumente für alle benötigten Parameter bereitstellen, kann aber Argumente für optionale Parameter auslassen.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-127">Any call must provide arguments for all required parameters, but can omit arguments for optional parameters.</span></span>  
  
 <span data-ttu-id="1c5b9-128">Jeder optionale Parameter hat einen Standardwert als Teil seiner Definition.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-128">Each optional parameter has a default value as part of its definition.</span></span> <span data-ttu-id="1c5b9-129">Wenn für diesen Parameter kein Argument gesendet wird, wird der Standardwert verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-129">If no argument is sent for that parameter, the default value is used.</span></span> <span data-ttu-id="1c5b9-130">Ein Standardwert muss einer der folgenden Typen von Ausdrücken sein:</span><span class="sxs-lookup"><span data-stu-id="1c5b9-130">A default value must be one of the following types of expressions:</span></span>  
  
- <span data-ttu-id="1c5b9-131">Ein konstanter Ausdruck</span><span class="sxs-lookup"><span data-stu-id="1c5b9-131">a constant expression;</span></span>  
  
- <span data-ttu-id="1c5b9-132">Ein Ausdruck der Form `new ValType()`, wobei `ValType` ein Werttyp wie [enum](../../language-reference/builtin-types/enum.md) oder [struct](../../language-reference/builtin-types/struct.md) ist</span><span class="sxs-lookup"><span data-stu-id="1c5b9-132">an expression of the form `new ValType()`, where `ValType` is a value type, such as an [enum](../../language-reference/builtin-types/enum.md) or a [struct](../../language-reference/builtin-types/struct.md);</span></span>  
  
- <span data-ttu-id="1c5b9-133">Ein Ausdruck in Form von [default(ValType)](../../language-reference/operators/default.md), wobei `ValType` ein Werttyp ist</span><span class="sxs-lookup"><span data-stu-id="1c5b9-133">an expression of the form [default(ValType)](../../language-reference/operators/default.md),  where `ValType` is a value type.</span></span>  
  
 <span data-ttu-id="1c5b9-134">Optionale Parameter werden am Ende der Parameterliste nach den erforderlichen Parametern definiert.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-134">Optional parameters are defined at the end of the parameter list, after any required parameters.</span></span> <span data-ttu-id="1c5b9-135">Wenn der Aufrufer ein Argument für einen beliebigen Parameter aus einer Folge von optionalen Parametern bereitstellt, muss er Argumente für alle vorherigen optionalen Parameter bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-135">If the caller provides an argument for any one of a succession of optional parameters, it must provide arguments for all preceding optional parameters.</span></span> <span data-ttu-id="1c5b9-136">Durch Trennzeichen getrennte Lücken in der Argumentliste werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-136">Comma-separated gaps in the argument list are not supported.</span></span> <span data-ttu-id="1c5b9-137">Im folgenden Code wird z.B. die Instanzmethode `ExampleMethod` mit einem erforderlichen und zwei optionalen Parametern definiert.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-137">For example, in the following code, instance method `ExampleMethod` is defined with one required and two optional parameters.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/optional.cs#15)]  
  
 <span data-ttu-id="1c5b9-138">Der folgende Aufruf von `ExampleMethod` verursacht einen Compilerfehler, da ein Argument für den dritten Parameter, aber nicht für den zweiten, bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-138">The following call to `ExampleMethod` causes a compiler error, because an argument is provided for the third parameter but not for the second.</span></span>  
  
 `//anExample.ExampleMethod(3, ,4);`  
  
 <span data-ttu-id="1c5b9-139">Wenn Sie den Namen des dritten Parameters kennen, können Sie ein benanntes Argument zum Ausführen der Aufgabe verwenden.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-139">However, if you know the name of the third parameter, you can use a named argument to accomplish the task.</span></span>  
  
 `anExample.ExampleMethod(3, optionalint: 4);`  
  
 <span data-ttu-id="1c5b9-140">IntelliSense verwendet wie in der folgenden Abbildung gezeigt zum Anzeigen von optionalen Parametern Klammern:</span><span class="sxs-lookup"><span data-stu-id="1c5b9-140">IntelliSense uses brackets to indicate optional parameters, as shown in the following illustration:</span></span>  
  
 ![Screenshot der IntelliSense-QuickInfo für die Methode „ExampleMethod“](./media/named-and-optional-arguments/optional-examplemethod-parameters.png)  
  
> [!NOTE]
> <span data-ttu-id="1c5b9-142">Sie können auch optionale Parameter mit der .NET-Klasse <xref:System.Runtime.InteropServices.OptionalAttribute> deklarieren.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-142">You can also declare optional parameters by using the .NET <xref:System.Runtime.InteropServices.OptionalAttribute> class.</span></span> <span data-ttu-id="1c5b9-143">`OptionalAttribute`-Parameter erfordern keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-143">`OptionalAttribute` parameters do not require a default value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c5b9-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1c5b9-144">Example</span></span>  
 <span data-ttu-id="1c5b9-145">Im folgenden Beispiel hat der Konstruktor für `ExampleClass` einen Parameter, der optional ist.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-145">In the following example, the constructor for `ExampleClass` has one parameter, which is optional.</span></span> <span data-ttu-id="1c5b9-146">Instanzmethode `ExampleMethod` hat einen erforderlichen Parameter (`required`) und zwei optionale Parameter (`optionalstr` und `optionalint`).</span><span class="sxs-lookup"><span data-stu-id="1c5b9-146">Instance method `ExampleMethod` has one required parameter, `required`, and two optional parameters, `optionalstr` and `optionalint`.</span></span> <span data-ttu-id="1c5b9-147">Der Code in `Main` veranschaulicht die unterschiedlichen Methoden, in denen der Konstruktor und die Methode aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-147">The code in `Main` shows the different ways in which the constructor and method can be invoked.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/optional.cs#2)]  
  
## <a name="com-interfaces"></a><span data-ttu-id="1c5b9-148">COM-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1c5b9-148">COM Interfaces</span></span>  
 <span data-ttu-id="1c5b9-149">Benannte und optionale Argumente verbessern zusammen mit der Unterstützung von dynamischen Objekten und anderen Verbesserungen deutlich die Interoperabilität mit COM-APIs wie Office-Automatisierungs-APIs.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-149">Named and optional arguments, along with support for dynamic objects and other enhancements, greatly improve interoperability with COM APIs, such as Office Automation APIs.</span></span>  
  
 <span data-ttu-id="1c5b9-150">Beispielsweise verfügt die Methode <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> in der <xref:Microsoft.Office.Interop.Excel.Range>-Schnittstelle von Microsoft Office Excel über sieben Parameter, von denen alle optional sind.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-150">For example, the <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> method in the Microsoft Office Excel <xref:Microsoft.Office.Interop.Excel.Range> interface has seven parameters, all of which are optional.</span></span> <span data-ttu-id="1c5b9-151">Diese Parameter sind in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="1c5b9-151">These parameters are shown in the following illustration:</span></span>  
  
 ![Screenshot der IntelliSense-QuickInfo für die Methode „AutoFormat“](./media/named-and-optional-arguments/autoformat-method-parameters.png)  
  
 <span data-ttu-id="1c5b9-153">In C# 3.0 und früheren Versionen wird ein Argument für jeden Parameter benötigt, wie im folgenden Beispiel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-153">In C# 3.0 and earlier versions, an argument is required for each parameter, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/namedandoptcom.cs#3)]  
  
 <span data-ttu-id="1c5b9-154">Sie können jedoch den Aufruf an `AutoFormat` erheblich vereinfachen, indem Sie benannte und optionale Argumente verwenden, die in C# 4.0 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-154">However, you can greatly simplify the call to `AutoFormat` by using named and optional arguments, introduced in C# 4.0.</span></span> <span data-ttu-id="1c5b9-155">Benannte und optionale Parameter helfen Ihnen dabei, das Argument für einen optionalen Parameter auszulassen, wenn Sie den Standardwert des Parameters nicht ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-155">Named and optional arguments enable you to omit the argument for an optional parameter if you do not want to change the parameter's default value.</span></span> <span data-ttu-id="1c5b9-156">Im folgenden Aufruf wird ein Wert für nur einen der sieben Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-156">In the following call, a value is specified for only one of the seven parameters.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/namedandoptcom.cs#13)]  
  
 <span data-ttu-id="1c5b9-157">Weitere Informationen und Beispiele finden Sie unter [Vorgehensweise: Verwenden von benannten und optionalen Argumenten in der Office-Programmierung](./how-to-use-named-and-optional-arguments-in-office-programming.md) und [Vorgehensweise: Zugreifen auf Office Interop-Objekte mithilfe von C#-Funktionen](../interop/how-to-access-office-onterop-objects.md).</span><span class="sxs-lookup"><span data-stu-id="1c5b9-157">For more information and examples, see [How to use named and optional arguments in Office programming](./how-to-use-named-and-optional-arguments-in-office-programming.md) and [How to access Office interop objects by using C# features](../interop/how-to-access-office-onterop-objects.md).</span></span>  
  
## <a name="overload-resolution"></a><span data-ttu-id="1c5b9-158">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="1c5b9-158">Overload Resolution</span></span>  
 <span data-ttu-id="1c5b9-159">Das Verwenden von benannten und optionalen Argumenten wirkt sich auf die Überladungsauflösung folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="1c5b9-159">Use of named and optional arguments affects overload resolution in the following ways:</span></span>  
  
- <span data-ttu-id="1c5b9-160">Eine Methode, ein Indexer oder ein Konstruktor ist ein Kandidat für die Ausführung, wenn jeder der Parameter entweder optional ist oder über Namen oder Position auf ein einzelnes Argument in der aufrufenden Anweisung reagiert. Dieses Argument kann in dem Typ des Parameters konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-160">A method, indexer, or constructor is a candidate for execution if each of its parameters either is optional or corresponds, by name or by position, to a single argument in the calling statement, and that argument can be converted to the type of the parameter.</span></span>  
  
- <span data-ttu-id="1c5b9-161">Wenn mehr als ein Kandidat gefunden wird, werden die Regeln der Überladungsauflösung als bevorzugte Konvertierungen auf die Argumente angewandt, die ausdrücklich angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-161">If more than one candidate is found, overload resolution rules for preferred conversions are applied to the arguments that are explicitly specified.</span></span> <span data-ttu-id="1c5b9-162">Ausgelassene Argumente für optionale Parameter werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-162">Omitted arguments for optional parameters are ignored.</span></span>  
  
- <span data-ttu-id="1c5b9-163">Wenn zwei Kandidaten gleich gut geeignet sind, wird ein Kandidat bevorzugt, der keine optionalen Parameter besitzt, für die Argumente im Aufruf ausgelassen wurden.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-163">If two candidates are judged to be equally good, preference goes to a candidate that does not have optional parameters for which arguments were omitted in the call.</span></span> <span data-ttu-id="1c5b9-164">Dies ist die Folge einer allgemeinen Präferenz bei der Überladungsauflösung für Kandidaten, die weniger Parameter besitzen.</span><span class="sxs-lookup"><span data-stu-id="1c5b9-164">This is a consequence of a general preference in overload resolution for candidates that have fewer parameters.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="1c5b9-165">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="1c5b9-165">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1c5b9-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c5b9-166">See also</span></span>

- [<span data-ttu-id="1c5b9-167">Vorgehensweise: Verwenden von benannten und optionalen Argumenten in der Office-Programmierung</span><span class="sxs-lookup"><span data-stu-id="1c5b9-167">How to use named and optional arguments in Office programming</span></span>](./how-to-use-named-and-optional-arguments-in-office-programming.md)
- [<span data-ttu-id="1c5b9-168">Verwenden von dynamischen Typen</span><span class="sxs-lookup"><span data-stu-id="1c5b9-168">Using Type dynamic</span></span>](../types/using-type-dynamic.md)
- [<span data-ttu-id="1c5b9-169">Verwenden von Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="1c5b9-169">Using Constructors</span></span>](./using-constructors.md)
- [<span data-ttu-id="1c5b9-170">Verwenden von Indexern</span><span class="sxs-lookup"><span data-stu-id="1c5b9-170">Using Indexers</span></span>](../indexers/using-indexers.md)
