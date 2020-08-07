---
title: Zeigertypen – C#-Programmierhandbuch
description: Erfahren Sie mehr über Zeigertypen. Hier finden Sie Beispiele für verschiedene Zeiger, Codebeispiele und zusätzliche verfügbare Ressourcen.
ms.date: 04/20/2018
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.openlocfilehash: 9c62a31f9a4a090fe56fb10ac45fe2f93f1b036e
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382034"
---
# <a name="pointer-types-c-programming-guide"></a><span data-ttu-id="bac2f-104">Zeigertypen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="bac2f-104">Pointer types (C# Programming Guide)</span></span>

<span data-ttu-id="bac2f-105">In einem unsicheren Kontext kann ein Typ sowohl ein Zeigertyp als auch ein Werttyp oder Verweistyp sein.</span><span class="sxs-lookup"><span data-stu-id="bac2f-105">In an unsafe context, a type may be a pointer type, a value type, or a reference type.</span></span> <span data-ttu-id="bac2f-106">Eine Zeigertypdeklaration erfolgt in einer der folgenden Formen:</span><span class="sxs-lookup"><span data-stu-id="bac2f-106">A pointer type declaration takes one of the following forms:</span></span>

``` csharp
type* identifier;
void* identifier; //allowed but not recommended
```

<span data-ttu-id="bac2f-107">Der Typ, der vor `*` in einem Zeigertyp angegeben wird, wird als **Verweistyp** bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="bac2f-107">The type specified before the `*` in a pointer type is called the **referent type**.</span></span> <span data-ttu-id="bac2f-108">Nur ein [nicht verwalteter Typ](../../language-reference/builtin-types/unmanaged-types.md) kann ein Verweistyp sein.</span><span class="sxs-lookup"><span data-stu-id="bac2f-108">Only an [unmanaged type](../../language-reference/builtin-types/unmanaged-types.md) can be a referent type.</span></span>

<span data-ttu-id="bac2f-109">Zeigertypen erben nicht von [object`object`, und es ist keine Konvertierung zwischen Zeigertypen und ](../../language-reference/builtin-types/reference-types.md) möglich.</span><span class="sxs-lookup"><span data-stu-id="bac2f-109">Pointer types do not inherit from [object](../../language-reference/builtin-types/reference-types.md) and no conversions exist between pointer types and `object`.</span></span> <span data-ttu-id="bac2f-110">Weiterhin unterstützen Boxing und Unboxing keine Zeiger.</span><span class="sxs-lookup"><span data-stu-id="bac2f-110">Also, boxing and unboxing do not support pointers.</span></span> <span data-ttu-id="bac2f-111">Es ist jedoch möglich, Konvertierungen zwischen verschiedenen Zeigertypen sowie zwischen Zeigertypen und ganzzahligen Typen durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="bac2f-111">However, you can convert between different pointer types and between pointer types and integral types.</span></span>

<span data-ttu-id="bac2f-112">Wenn Sie mehrere Zeiger innerhalb ein- und derselben Deklaration deklarieren, wird das Sternchen (\*) nur einmal mit dem zugrunde liegenden Typ notiert und nicht als Präfix für jeden Zeigernamen verwendet.</span><span class="sxs-lookup"><span data-stu-id="bac2f-112">When you declare multiple pointers in the same declaration, the asterisk (\*) is written together with the underlying type only; it is not used as a prefix to each pointer name.</span></span> <span data-ttu-id="bac2f-113">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bac2f-113">For example:</span></span>

```csharp
int* p1, p2, p3;   // Ok
int *p1, *p2, *p3;   // Invalid in C#
```

<span data-ttu-id="bac2f-114">Ein Zeiger kann nicht auf einen Verweis oder eine [Struktur](../../language-reference/builtin-types/struct.md) verweisen, die Verweise enthält, da ein Objektverweis auch dann in die Garbage Collection aufgenommen werden kann, wenn ein Zeiger darauf verweist.</span><span class="sxs-lookup"><span data-stu-id="bac2f-114">A pointer cannot point to a reference or to a [struct](../../language-reference/builtin-types/struct.md) that contains references, because an object reference can be garbage collected even if a pointer is pointing to it.</span></span> <span data-ttu-id="bac2f-115">In der Garbage Collection wird nicht nachgehalten, ob von einem der Zeigertypen auf ein Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="bac2f-115">The garbage collector does not keep track of whether an object is being pointed to by any pointer types.</span></span>

<span data-ttu-id="bac2f-116">Der Wert der Zeigervariablen vom Typ `myType*` ist die Adresse einer Variablen vom Typ `myType`.</span><span class="sxs-lookup"><span data-stu-id="bac2f-116">The value of the pointer variable of type `myType*` is the address of a variable of type `myType`.</span></span> <span data-ttu-id="bac2f-117">Im Folgenden finden Sie Beispiele für Zeigertypdeklarationen:</span><span class="sxs-lookup"><span data-stu-id="bac2f-117">The following are examples of pointer type declarations:</span></span>

|<span data-ttu-id="bac2f-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bac2f-118">Example</span></span>|<span data-ttu-id="bac2f-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bac2f-119">Description</span></span>|
|-------------|-----------------|
|`int* p`|<span data-ttu-id="bac2f-120">`p` ist ein Zeiger auf einen ganzzahligen Wert.</span><span class="sxs-lookup"><span data-stu-id="bac2f-120">`p` is a pointer to an integer.</span></span>|
|`int** p`|<span data-ttu-id="bac2f-121">`p` ist ein Zeiger auf einen Zeiger auf einen ganzzahligen Wert.</span><span class="sxs-lookup"><span data-stu-id="bac2f-121">`p` is a pointer to a pointer to an integer.</span></span>|
|`int*[] p`|<span data-ttu-id="bac2f-122">`p` ist ein eindimensionales Array von Zeigern auf ganzzahlige Werte.</span><span class="sxs-lookup"><span data-stu-id="bac2f-122">`p` is a single-dimensional array of pointers to integers.</span></span>|
|`char* p`|<span data-ttu-id="bac2f-123">`p` ist ein Zeiger auf eine char-Variable.</span><span class="sxs-lookup"><span data-stu-id="bac2f-123">`p` is a pointer to a char.</span></span>|
|`void* p`|<span data-ttu-id="bac2f-124">`p` ist ein Zeiger auf einen unbekannten Typ.</span><span class="sxs-lookup"><span data-stu-id="bac2f-124">`p` is a pointer to an unknown type.</span></span>|

<span data-ttu-id="bac2f-125">Sie können den Zeigerdereferenzierungsoperator \* verwenden, um auf den Inhalt an der Speicherstelle zuzugreifen, auf die die Zeigervariable zeigt.</span><span class="sxs-lookup"><span data-stu-id="bac2f-125">The pointer indirection operator \* can be used to access the contents at the location pointed to by the pointer variable.</span></span> <span data-ttu-id="bac2f-126">Betrachten Sie beispielsweise die folgende Deklaration:</span><span class="sxs-lookup"><span data-stu-id="bac2f-126">For example, consider the following declaration:</span></span>

```csharp
int* myVariable;
```

<span data-ttu-id="bac2f-127">Der Ausdruck `*myVariable` kennzeichnet die `int`-Variable, die sich an der in `myVariable` enthaltenen Adresse befindet.</span><span class="sxs-lookup"><span data-stu-id="bac2f-127">The expression `*myVariable` denotes the `int` variable found at the address contained in `myVariable`.</span></span>

<span data-ttu-id="bac2f-128">Es gibt mehrere Beispiele von Zeigern in den Themen [fixed-Anweisung](../../language-reference/keywords/fixed-statement.md) und [Zeigerkonvertierungen](./pointer-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="bac2f-128">There are several examples of pointers in the topics [fixed Statement](../../language-reference/keywords/fixed-statement.md) and [Pointer Conversions](./pointer-conversions.md).</span></span> <span data-ttu-id="bac2f-129">Im folgenden Beispiel wird die Verwendung des `unsafe`-Schlüsselworts und der `fixed`-Anweisung sowie die Vorgehensweise zum Erhöhen eines inneren Zeigers veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="bac2f-129">The following example uses the `unsafe` keyword and the `fixed` statement, and shows how to increment an interior pointer.</span></span>  <span data-ttu-id="bac2f-130">Sie können diesen Code in die Hauptmethode einer Konsolenanwendung einfügen, um ihn auszuführen.</span><span class="sxs-lookup"><span data-stu-id="bac2f-130">You can paste this code into the Main function of a console application to run it.</span></span> <span data-ttu-id="bac2f-131">Diese Beispiele müssen mithilfe der Compileroption [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="bac2f-131">These examples must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option set.</span></span>

[!code-csharp[Using pointer types](snippets/FixedKeywordExamples.cs#5)]

<span data-ttu-id="bac2f-132">Der Dereferenzierungsoperator kann nicht auf Zeiger vom Typ `void*` angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="bac2f-132">You cannot apply the indirection operator to a pointer of type `void*`.</span></span> <span data-ttu-id="bac2f-133">Sie können jedoch eine Umwandlung verwenden, um einen void-Zeiger in einen anderen Zeigertyp und umgekehrt zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="bac2f-133">However, you can use a cast to convert a void pointer to any other pointer type, and vice versa.</span></span>

<span data-ttu-id="bac2f-134">Ein Zeiger kann den Wert `null` annehmen.</span><span class="sxs-lookup"><span data-stu-id="bac2f-134">A pointer can be `null`.</span></span> <span data-ttu-id="bac2f-135">Die Anwendung des Dereferenzierungsoperators auf einen NULL-Zeiger führt zu einem in der Implementierung definierten Verhalten.</span><span class="sxs-lookup"><span data-stu-id="bac2f-135">Applying the indirection operator to a null pointer causes an implementation-defined behavior.</span></span>

<span data-ttu-id="bac2f-136">Die Übergabe von Zeigern zwischen Methoden kann zu nicht definiertem Verhalten führen.</span><span class="sxs-lookup"><span data-stu-id="bac2f-136">Passing pointers between methods can cause undefined behavior.</span></span> <span data-ttu-id="bac2f-137">Ziehen Sie eine Methode in Betracht, die einen Zeiger auf eine lokale Variable als einen `in`-, `out`- oder `ref`-Parameter oder als Funktionsergebnis zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="bac2f-137">Consider a method that returns a pointer to a local variable through an `in`, `out`, or `ref` parameter or as the function result.</span></span> <span data-ttu-id="bac2f-138">Wenn der Zeiger in einem fixed-Block festgelegt wurde, ist die Variable, auf die der Zeiger verweist, möglicherweise nicht fixiert.</span><span class="sxs-lookup"><span data-stu-id="bac2f-138">If the pointer was set in a fixed block, the variable to which it points may no longer be fixed.</span></span>

<span data-ttu-id="bac2f-139">In der folgenden Tabelle werden die Operatoren und Anweisungen aufgelistet, die in einem unsicheren Kontext auf Zeiger angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="bac2f-139">The following table lists the operators and statements that can operate on pointers in an unsafe context:</span></span>

|<span data-ttu-id="bac2f-140">Operator/Anweisung</span><span class="sxs-lookup"><span data-stu-id="bac2f-140">Operator/Statement</span></span>|<span data-ttu-id="bac2f-141">Verwendung</span><span class="sxs-lookup"><span data-stu-id="bac2f-141">Use</span></span>|
|-------------------------|---------|
|`*`|<span data-ttu-id="bac2f-142">Führt eine Zeigerdereferenzierung aus.</span><span class="sxs-lookup"><span data-stu-id="bac2f-142">Performs pointer indirection.</span></span>|
|`->`|<span data-ttu-id="bac2f-143">Greift über einen Zeiger auf einen Member einer Struktur zu.</span><span class="sxs-lookup"><span data-stu-id="bac2f-143">Accesses a member of a struct through a pointer.</span></span>|
|`[]`|<span data-ttu-id="bac2f-144">Indiziert einen Zeiger.</span><span class="sxs-lookup"><span data-stu-id="bac2f-144">Indexes a pointer.</span></span>|
|`&`|<span data-ttu-id="bac2f-145">Ruft die Adresse einer Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="bac2f-145">Obtains the address of a variable.</span></span>|
|<span data-ttu-id="bac2f-146">`++` und `--`</span><span class="sxs-lookup"><span data-stu-id="bac2f-146">`++` and `--`</span></span>|<span data-ttu-id="bac2f-147">Inkrementiert und dekrementiert Zeiger.</span><span class="sxs-lookup"><span data-stu-id="bac2f-147">Increments and decrements pointers.</span></span>|
|<span data-ttu-id="bac2f-148">`+` und `-`</span><span class="sxs-lookup"><span data-stu-id="bac2f-148">`+` and `-`</span></span>|<span data-ttu-id="bac2f-149">Führt Zeigerarithmetik aus.</span><span class="sxs-lookup"><span data-stu-id="bac2f-149">Performs pointer arithmetic.</span></span>|
|<span data-ttu-id="bac2f-150">`==`, `!=`, `<`, `>`, `<=` und `>=`</span><span class="sxs-lookup"><span data-stu-id="bac2f-150">`==`, `!=`, `<`, `>`, `<=`, and `>=`</span></span>|<span data-ttu-id="bac2f-151">Vergleicht Zeiger.</span><span class="sxs-lookup"><span data-stu-id="bac2f-151">Compares pointers.</span></span>|
|[`stackalloc`](../../language-reference/operators/stackalloc.md)|<span data-ttu-id="bac2f-152">Belegt Speicher für den Stapel.</span><span class="sxs-lookup"><span data-stu-id="bac2f-152">Allocates memory on the stack.</span></span>|
|[<span data-ttu-id="bac2f-153">`fixed`-Anweisung</span><span class="sxs-lookup"><span data-stu-id="bac2f-153">`fixed` statement</span></span>](../../language-reference/keywords/fixed-statement.md)|<span data-ttu-id="bac2f-154">Fixiert eine Variable vorübergehend, damit ihre Adresse gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="bac2f-154">Temporarily fixes a variable so that its address may be found.</span></span>|

<span data-ttu-id="bac2f-155">Weitere Informationen zu Zeigeroperatoren finden Sie unter [Operatoren im Zusammenhang mit Zeigern](../../language-reference/operators/pointer-related-operators.md).</span><span class="sxs-lookup"><span data-stu-id="bac2f-155">For more information about pointer related operators, see [Pointer related operators](../../language-reference/operators/pointer-related-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bac2f-156">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="bac2f-156">C# language specification</span></span>

<span data-ttu-id="bac2f-157">Weitere Informationen finden Sie im Abschnitt [Zeigertypen](~/_csharplang/spec/unsafe-code.md#pointer-types) der [Spezifikation für die Sprache C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="bac2f-157">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bac2f-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bac2f-158">See also</span></span>

- [<span data-ttu-id="bac2f-159">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="bac2f-159">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="bac2f-160">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="bac2f-160">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="bac2f-161">Zeigerkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="bac2f-161">Pointer Conversions</span></span>](pointer-conversions.md)
- [<span data-ttu-id="bac2f-162">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="bac2f-162">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="bac2f-163">Werttypen</span><span class="sxs-lookup"><span data-stu-id="bac2f-163">Value types</span></span>](../../language-reference/builtin-types/value-types.md)
- [<span data-ttu-id="bac2f-164">unsafe</span><span class="sxs-lookup"><span data-stu-id="bac2f-164">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
