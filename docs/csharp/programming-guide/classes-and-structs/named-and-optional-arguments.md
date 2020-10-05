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
ms.openlocfilehash: 4c9c932e3df4035024c90e92e4d80309fffe3ce3
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406231"
---
# <a name="named-and-optional-arguments-c-programming-guide"></a><span data-ttu-id="81be0-104">Benannte und optionale Argumente (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="81be0-104">Named and Optional Arguments (C# Programming Guide)</span></span>

<span data-ttu-id="81be0-105">C# 4 führt benannte und optionale Argumente ein.</span><span class="sxs-lookup"><span data-stu-id="81be0-105">C# 4 introduces named and optional arguments.</span></span> <span data-ttu-id="81be0-106">Mithilfe von *benannten Argumenten* können Sie ein Argument für einen Parameter angeben, indem Sie das Argument mit dem Namen des Parameters anstatt mit seiner Position in der Parameterliste abgleichen.</span><span class="sxs-lookup"><span data-stu-id="81be0-106">*Named arguments* enable you to specify an argument for a parameter by matching the argument with its name rather than with its position in the parameter list.</span></span> <span data-ttu-id="81be0-107">*Optionale Argumente* ermöglichen es Ihnen, Argumente für einige Parameter auszulassen.</span><span class="sxs-lookup"><span data-stu-id="81be0-107">*Optional arguments* enable you to omit arguments for some parameters.</span></span> <span data-ttu-id="81be0-108">Beide Techniken können mit Methoden, Indexern, Konstruktoren und Delegaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="81be0-108">Both techniques can be used with methods, indexers, constructors, and delegates.</span></span>

<span data-ttu-id="81be0-109">Wenn Sie benannte und optionale Argumente verwenden, werden die Argumente in der Reihenfolge ausgewertet, in der sie in der Argumentliste, nicht in der Parameterliste, erscheinen.</span><span class="sxs-lookup"><span data-stu-id="81be0-109">When you use named and optional arguments, the arguments are evaluated in the order in which they appear in the argument list, not the parameter list.</span></span>

<span data-ttu-id="81be0-110">Mit benannten und optionalen Parametern können Sie Argumente für ausgewählte Parameter bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="81be0-110">Named and optional parameters enable you to supply arguments for selected parameters.</span></span> <span data-ttu-id="81be0-111">Diese Funktion erleichtert den Zugriff auf COM-Schnittstellen wie etwa die Automation-APIs in Microsoft Office erheblich.</span><span class="sxs-lookup"><span data-stu-id="81be0-111">This capability greatly eases calls to COM interfaces such as the Microsoft Office Automation APIs.</span></span>

## <a name="named-arguments"></a><span data-ttu-id="81be0-112">Benannte Argumente</span><span class="sxs-lookup"><span data-stu-id="81be0-112">Named Arguments</span></span>

<span data-ttu-id="81be0-113">Bei Verwendung benannter Argumente bleibt es Ihnen erspart, die Reihenfolge von Parametern in den Parameterlisten von aufgerufenen Methoden abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="81be0-113">Named arguments free you from matching the order of parameters in the parameter lists of called methods.</span></span> <span data-ttu-id="81be0-114">Der Parameter für jedes Argument kann vom Parameternamen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="81be0-114">The parameter for each argument can be specified by parameter name.</span></span> <span data-ttu-id="81be0-115">Eine Funktion, die beispielsweise Details zu einer Bestellung ausgibt (z. B. Verkäufername, Bestellnummer und Produktname), kann aufgerufen werden, indem anhand der Position Argumente in der Reihenfolge gesendet werden, die von der Funktion definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="81be0-115">For example, a function that prints order details (such as, seller name, order number & product name) can be called by sending arguments by position, in the order defined by the function.</span></span>

```csharp
PrintOrderDetails("Gift Shop", 31, "Red Mug");
```

<span data-ttu-id="81be0-116">Wenn Sie sich nicht an die Reihenfolge der Parameter erinnern, aber deren Namen kennen, können Sie die Argumente in einer beliebigen Reihenfolge senden.</span><span class="sxs-lookup"><span data-stu-id="81be0-116">If you don't remember the order of the parameters but know their names, you can send the arguments in any order.</span></span>

```csharp
PrintOrderDetails(orderNum: 31, productName: "Red Mug", sellerName: "Gift Shop");
PrintOrderDetails(productName: "Red Mug", sellerName: "Gift Shop", orderNum: 31);
```

<span data-ttu-id="81be0-117">Benannte Argumente verbessern auch die Lesbarkeit des Codes, indem sie identifizieren, was jedes Argument darstellt.</span><span class="sxs-lookup"><span data-stu-id="81be0-117">Named arguments also improve the readability of your code by identifying what each argument represents.</span></span> <span data-ttu-id="81be0-118">In der folgenden Beispielmethode darf `sellerName` nicht NULL sein oder Leerzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="81be0-118">In the example method below, the `sellerName` can't be null or white space.</span></span> <span data-ttu-id="81be0-119">Da es sich bei `sellerName` und `productName` um Zeichenfolgentypen handelt, sollten Sie benannte Argumente verwenden, anstatt Argumente nach Position zu senden, um die beiden Parameter zu unterscheiden und die Leser des Codes nicht zu verwirren.</span><span class="sxs-lookup"><span data-stu-id="81be0-119">As both `sellerName` and `productName` are string types, instead of sending arguments by position, it makes sense to use named arguments to disambiguate the two and reduce confusion for anyone reading the code.</span></span>
  
<span data-ttu-id="81be0-120">Benannte Argumente sind länger gültig, wenn sie mit positionellen Argumenten verwendet werden, da</span><span class="sxs-lookup"><span data-stu-id="81be0-120">Named arguments, when used with positional arguments, are valid as long as</span></span>

- <span data-ttu-id="81be0-121">ihnen keine positionellen Argumente folgen, bzw. da</span><span class="sxs-lookup"><span data-stu-id="81be0-121">they're not followed by any positional arguments, or</span></span>

    ```csharp
    PrintOrderDetails("Gift Shop", 31, productName: "Red Mug");
    ```

- <span data-ttu-id="81be0-122">sie _ab C# 7.2_ in der richtigen Position verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="81be0-122">_starting with C# 7.2_, they're used in the correct position.</span></span> <span data-ttu-id="81be0-123">Im folgenden Beispiel befindet sich der Parameter `orderNum` in der richtigen Position, ist jedoch nicht explizit benannt.</span><span class="sxs-lookup"><span data-stu-id="81be0-123">In the example below, the parameter `orderNum` is in the correct position but isn't explicitly named.</span></span>

    ```csharp
    PrintOrderDetails(sellerName: "Gift Shop", 31, productName: "Red Mug");
    ```

<span data-ttu-id="81be0-124">Positionelle Argumente, die auf fehlerhafte benannte Argumente folgen, sind ungültig.</span><span class="sxs-lookup"><span data-stu-id="81be0-124">Positional arguments that follow any out-of-order named arguments are invalid.</span></span>

```csharp
// This generates CS1738: Named argument specifications must appear after all fixed arguments have been specified.
PrintOrderDetails(productName: "Red Mug", 31, "Gift Shop");
```

## <a name="example"></a><span data-ttu-id="81be0-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="81be0-125">Example</span></span>

<span data-ttu-id="81be0-126">Der folgende Code implementiert die Beispiele in diesem Abschnitt sowie einige zusätzliche Beispiele.</span><span class="sxs-lookup"><span data-stu-id="81be0-126">The following code implements the examples from this section along with some additional ones.</span></span>  

[!code-csharp[csProgGuideNamedAndOptional#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/program.cs#1)]

## <a name="optional-arguments"></a><span data-ttu-id="81be0-127">Optionale Argumente</span><span class="sxs-lookup"><span data-stu-id="81be0-127">Optional Arguments</span></span>

<span data-ttu-id="81be0-128">Die Definition einer Methode, eines Konstruktors, eines Indexers oder eines Delegaten kann angeben, dass deren Parameter benötigt werden oder optional sind.</span><span class="sxs-lookup"><span data-stu-id="81be0-128">The definition of a method, constructor, indexer, or delegate can specify its parameters are required or optional.</span></span> <span data-ttu-id="81be0-129">Jeder Aufruf muss Argumente für alle benötigten Parameter bereitstellen, kann aber Argumente für optionale Parameter auslassen.</span><span class="sxs-lookup"><span data-stu-id="81be0-129">Any call must provide arguments for all required parameters, but can omit arguments for optional parameters.</span></span>

<span data-ttu-id="81be0-130">Jeder optionale Parameter hat einen Standardwert als Teil seiner Definition.</span><span class="sxs-lookup"><span data-stu-id="81be0-130">Each optional parameter has a default value as part of its definition.</span></span> <span data-ttu-id="81be0-131">Wenn für diesen Parameter kein Argument gesendet wird, wird der Standardwert verwendet.</span><span class="sxs-lookup"><span data-stu-id="81be0-131">If no argument is sent for that parameter, the default value is used.</span></span> <span data-ttu-id="81be0-132">Ein Standardwert muss einer der folgenden Typen von Ausdrücken sein:</span><span class="sxs-lookup"><span data-stu-id="81be0-132">A default value must be one of the following types of expressions:</span></span>
  
- <span data-ttu-id="81be0-133">Ein konstanter Ausdruck</span><span class="sxs-lookup"><span data-stu-id="81be0-133">a constant expression;</span></span>  
- <span data-ttu-id="81be0-134">Ein Ausdruck der Form `new ValType()`, wobei `ValType` ein Werttyp wie [enum](../../language-reference/builtin-types/enum.md) oder [struct](../../language-reference/builtin-types/struct.md) ist</span><span class="sxs-lookup"><span data-stu-id="81be0-134">an expression of the form `new ValType()`, where `ValType` is a value type, such as an [enum](../../language-reference/builtin-types/enum.md) or a [struct](../../language-reference/builtin-types/struct.md);</span></span>
- <span data-ttu-id="81be0-135">Ein Ausdruck in Form von [default(ValType)](../../language-reference/operators/default.md), wobei `ValType` ein Werttyp ist</span><span class="sxs-lookup"><span data-stu-id="81be0-135">an expression of the form [default(ValType)](../../language-reference/operators/default.md),  where `ValType` is a value type.</span></span>

<span data-ttu-id="81be0-136">Optionale Parameter werden am Ende der Parameterliste nach den erforderlichen Parametern definiert.</span><span class="sxs-lookup"><span data-stu-id="81be0-136">Optional parameters are defined at the end of the parameter list, after any required parameters.</span></span> <span data-ttu-id="81be0-137">Wenn der Aufrufer ein Argument für einen beliebigen Parameter aus einer Folge von optionalen Parametern bereitstellt, muss er Argumente für alle vorherigen optionalen Parameter bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="81be0-137">If the caller provides an argument for any one of a succession of optional parameters, it must provide arguments for all preceding optional parameters.</span></span> <span data-ttu-id="81be0-138">Durch Trennzeichen getrennte Lücken in der Argumentliste werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="81be0-138">Comma-separated gaps in the argument list aren't supported.</span></span> <span data-ttu-id="81be0-139">Im folgenden Code wird z.B. die Instanzmethode `ExampleMethod` mit einem erforderlichen und zwei optionalen Parametern definiert.</span><span class="sxs-lookup"><span data-stu-id="81be0-139">For example, in the following code, instance method `ExampleMethod` is defined with one required and two optional parameters.</span></span>

[!code-csharp[csProgGuideNamedAndOptional#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/optional.cs#15)]

<span data-ttu-id="81be0-140">Der folgende Aufruf von `ExampleMethod` verursacht einen Compilerfehler, da ein Argument für den dritten Parameter, aber nicht für den zweiten, bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="81be0-140">The following call to `ExampleMethod` causes a compiler error, because an argument is provided for the third parameter but not for the second.</span></span>

```csharp
//anExample.ExampleMethod(3, ,4);
```

<span data-ttu-id="81be0-141">Wenn Sie den Namen des dritten Parameters kennen, können Sie ein benanntes Argument zum Ausführen der Aufgabe verwenden.</span><span class="sxs-lookup"><span data-stu-id="81be0-141">However, if you know the name of the third parameter, you can use a named argument to accomplish the task.</span></span>

```csharp
anExample.ExampleMethod(3, optionalint: 4);
```

<span data-ttu-id="81be0-142">IntelliSense verwendet wie in der folgenden Abbildung gezeigt zum Anzeigen von optionalen Parametern Klammern:</span><span class="sxs-lookup"><span data-stu-id="81be0-142">IntelliSense uses brackets to indicate optional parameters, as shown in the following illustration:</span></span>

![Screenshot der IntelliSense-QuickInfo für die Methode „ExampleMethod“](./media/named-and-optional-arguments/optional-examplemethod-parameters.png)

> [!NOTE]
> <span data-ttu-id="81be0-144">Sie können auch optionale Parameter mit der .NET-Klasse <xref:System.Runtime.InteropServices.OptionalAttribute> deklarieren.</span><span class="sxs-lookup"><span data-stu-id="81be0-144">You can also declare optional parameters by using the .NET <xref:System.Runtime.InteropServices.OptionalAttribute> class.</span></span> <span data-ttu-id="81be0-145">`OptionalAttribute`-Parameter erfordern keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="81be0-145">`OptionalAttribute` parameters do not require a default value.</span></span>

## <a name="example"></a><span data-ttu-id="81be0-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="81be0-146">Example</span></span>

<span data-ttu-id="81be0-147">Im folgenden Beispiel hat der Konstruktor für `ExampleClass` einen Parameter, der optional ist.</span><span class="sxs-lookup"><span data-stu-id="81be0-147">In the following example, the constructor for `ExampleClass` has one parameter, which is optional.</span></span> <span data-ttu-id="81be0-148">Instanzmethode `ExampleMethod` hat einen erforderlichen Parameter (`required`) und zwei optionale Parameter (`optionalstr` und `optionalint`).</span><span class="sxs-lookup"><span data-stu-id="81be0-148">Instance method `ExampleMethod` has one required parameter, `required`, and two optional parameters, `optionalstr` and `optionalint`.</span></span> <span data-ttu-id="81be0-149">Der Code in `Main` veranschaulicht die unterschiedlichen Methoden, in denen der Konstruktor und die Methode aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="81be0-149">The code in `Main` shows the different ways in which the constructor and method can be invoked.</span></span>

[!code-csharp[csProgGuideNamedAndOptional#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/optional.cs#2)]

<span data-ttu-id="81be0-150">Der obige Code zeigt eine Reihe von Beispielen, in denen optionale Parameter nicht ordnungsgemäß angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="81be0-150">The preceding code shows a number of examples where optional parameters aren't applied correctly.</span></span> <span data-ttu-id="81be0-151">Das erste Beispiel veranschaulicht, dass für den ersten Parameter, der erforderlich ist, ein Argument angegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="81be0-151">The first illustrates that an argument must be supplied for the first parameter, which is required.</span></span>
  
## <a name="com-interfaces"></a><span data-ttu-id="81be0-152">COM-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="81be0-152">COM Interfaces</span></span>

<span data-ttu-id="81be0-153">Benannte und optionale Argumente verbessern zusammen mit der Unterstützung von dynamischen Objekten deutlich die Interoperabilität mit COM-APIs wie Office Automation-APIs.</span><span class="sxs-lookup"><span data-stu-id="81be0-153">Named and optional arguments, along with support for dynamic objects, greatly improve interoperability with COM APIs, such as Office Automation APIs.</span></span>

<span data-ttu-id="81be0-154">Beispielsweise verfügt die Methode <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> in der <xref:Microsoft.Office.Interop.Excel.Range>-Schnittstelle von Microsoft Office Excel über sieben Parameter, von denen alle optional sind.</span><span class="sxs-lookup"><span data-stu-id="81be0-154">For example, the <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> method in the Microsoft Office Excel <xref:Microsoft.Office.Interop.Excel.Range> interface has seven parameters, all of which are optional.</span></span> <span data-ttu-id="81be0-155">Diese Parameter sind in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="81be0-155">These parameters are shown in the following illustration:</span></span>

![Screenshot der IntelliSense-QuickInfo für die Methode „AutoFormat“](./media/named-and-optional-arguments/autoformat-method-parameters.png)

<span data-ttu-id="81be0-157">In C# 3.0 und früheren Versionen wird ein Argument für jeden Parameter benötigt, wie im folgenden Beispiel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="81be0-157">In C# 3.0 and earlier versions, an argument is required for each parameter, as shown in the following example.</span></span>

[!code-csharp[csProgGuideNamedAndOptional#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/namedandoptcom.cs#3)]

<span data-ttu-id="81be0-158">Sie können jedoch den Aufruf an `AutoFormat` erheblich vereinfachen, indem Sie benannte und optionale Argumente verwenden, die in C# 4.0 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="81be0-158">However, you can greatly simplify the call to `AutoFormat` by using named and optional arguments, introduced in C# 4.0.</span></span> <span data-ttu-id="81be0-159">Benannte und optionale Parameter helfen Ihnen dabei, das Argument für einen optionalen Parameter auszulassen, wenn Sie den Standardwert des Parameters nicht ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="81be0-159">Named and optional arguments enable you to omit the argument for an optional parameter if you don't want to change the parameter's default value.</span></span> <span data-ttu-id="81be0-160">Im folgenden Aufruf wird ein Wert für nur einen der sieben Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="81be0-160">In the following call, a value is specified for only one of the seven parameters.</span></span>

[!code-csharp[csProgGuideNamedAndOptional#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/namedandoptcom.cs#13)]

<span data-ttu-id="81be0-161">Weitere Informationen und Beispiele finden Sie unter [Vorgehensweise: Verwenden von benannten und optionalen Argumenten in der Office-Programmierung](./how-to-use-named-and-optional-arguments-in-office-programming.md) und [Vorgehensweise: Zugreifen auf Office Interop-Objekte mithilfe von C#-Funktionen](../interop/how-to-access-office-onterop-objects.md).</span><span class="sxs-lookup"><span data-stu-id="81be0-161">For more information and examples, see [How to use named and optional arguments in Office programming](./how-to-use-named-and-optional-arguments-in-office-programming.md) and [How to access Office interop objects by using C# features](../interop/how-to-access-office-onterop-objects.md).</span></span>
  
## <a name="overload-resolution"></a><span data-ttu-id="81be0-162">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="81be0-162">Overload Resolution</span></span>

<span data-ttu-id="81be0-163">Das Verwenden von benannten und optionalen Argumenten wirkt sich auf die Überladungsauflösung folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="81be0-163">Use of named and optional arguments affects overload resolution in the following ways:</span></span>

- <span data-ttu-id="81be0-164">Eine Methode, ein Indexer oder ein Konstruktor ist ein Kandidat für die Ausführung, wenn jeder der Parameter entweder optional ist oder über Namen oder Position auf ein einzelnes Argument in der aufrufenden Anweisung reagiert. Dieses Argument kann in dem Typ des Parameters konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="81be0-164">A method, indexer, or constructor is a candidate for execution if each of its parameters either is optional or corresponds, by name or by position, to a single argument in the calling statement, and that argument can be converted to the type of the parameter.</span></span>  
- <span data-ttu-id="81be0-165">Wenn mehr als ein Kandidat gefunden wird, werden die Regeln der Überladungsauflösung als bevorzugte Konvertierungen auf die Argumente angewandt, die ausdrücklich angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="81be0-165">If more than one candidate is found, overload resolution rules for preferred conversions are applied to the arguments that are explicitly specified.</span></span> <span data-ttu-id="81be0-166">Ausgelassene Argumente für optionale Parameter werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="81be0-166">Omitted arguments for optional parameters are ignored.</span></span>
- <span data-ttu-id="81be0-167">Wenn zwei Kandidaten gleich gut geeignet sind, wird ein Kandidat bevorzugt, der keine optionalen Parameter besitzt, für die Argumente im Aufruf ausgelassen wurden.</span><span class="sxs-lookup"><span data-stu-id="81be0-167">If two candidates are judged to be equally good, preference goes to a candidate that doesn't have optional parameters for which arguments were omitted in the call.</span></span> <span data-ttu-id="81be0-168">Bei der Überladungsauflösung werden normalerweise Kandidaten mit weniger Parametern bevorzugt.</span><span class="sxs-lookup"><span data-stu-id="81be0-168">Overload resolution generally prefers candidates that have fewer parameters.</span></span>
  
## <a name="c-language-specification"></a><span data-ttu-id="81be0-169">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="81be0-169">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]
