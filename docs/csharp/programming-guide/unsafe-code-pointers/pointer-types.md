---
title: Zeigertypen (C#-Programmierhandbuch)
ms.date: 04/20/2018
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.openlocfilehash: 124cc98b6f73b6014ab845ce5b9331e9f5292757
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53146836"
---
# <a name="pointer-types-c-programming-guide"></a><span data-ttu-id="610ee-102">Zeigertypen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="610ee-102">Pointer types (C# Programming Guide)</span></span>

<span data-ttu-id="610ee-103">In einem unsicheren Kontext kann ein Typ sowohl ein Zeigertyp als auch ein Werttyp oder Verweistyp sein.</span><span class="sxs-lookup"><span data-stu-id="610ee-103">In an unsafe context, a type may be a pointer type, a value type, or a reference type.</span></span> <span data-ttu-id="610ee-104">Eine Zeigertypdeklaration erfolgt in einer der folgenden Formen:</span><span class="sxs-lookup"><span data-stu-id="610ee-104">A pointer type declaration takes one of the following forms:</span></span>

``` csharp
type* identifier;
void* identifier; //allowed but not recommended
```

<span data-ttu-id="610ee-105">Der Typ, der vor `*` in einem Zeigertyp angegeben wird, wird als **Verweistyp** bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="610ee-105">The type specified before the `*` in a pointer type is called the **referent type**.</span></span> <span data-ttu-id="610ee-106">Die folgenden Typen können Verweistypen sein:</span><span class="sxs-lookup"><span data-stu-id="610ee-106">Any of the following types may be a referent type:</span></span>

- <span data-ttu-id="610ee-107">Ein beliebiger integraler Typ: [sbyte](../../language-reference/keywords/sbyte.md), [byte](../../language-reference/keywords/byte.md), [short](../../language-reference/keywords/short.md), [ushort](../../language-reference/keywords/ushort.md), [int](../../language-reference/keywords/int.md), [uint](../../language-reference/keywords/uint.md), [long](../../language-reference/keywords/long.md) oder [ulong](../../language-reference/keywords/ulong.md).</span><span class="sxs-lookup"><span data-stu-id="610ee-107">Any integral type: [sbyte](../../language-reference/keywords/sbyte.md), [byte](../../language-reference/keywords/byte.md), [short](../../language-reference/keywords/short.md), [ushort](../../language-reference/keywords/ushort.md), [int](../../language-reference/keywords/int.md), [uint](../../language-reference/keywords/uint.md), [long](../../language-reference/keywords/long.md), [ulong](../../language-reference/keywords/ulong.md).</span></span>
- <span data-ttu-id="610ee-108">Ein beliebiger Gleitkommatyp: [float](../../language-reference/keywords/float.md) oder [double](../../language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="610ee-108">Any floating-point type: [float](../../language-reference/keywords/float.md), [double](../../language-reference/keywords/double.md).</span></span>
- <span data-ttu-id="610ee-109">[char](../../language-reference/keywords/char.md).</span><span class="sxs-lookup"><span data-stu-id="610ee-109">[char](../../language-reference/keywords/char.md).</span></span>
- <span data-ttu-id="610ee-110">[bool](../../language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="610ee-110">[bool](../../language-reference/keywords/bool.md).</span></span>
- <span data-ttu-id="610ee-111">[decimal](../../language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="610ee-111">[decimal](../../language-reference/keywords/decimal.md).</span></span>
- <span data-ttu-id="610ee-112">Beliebiger [enum](../../language-reference/keywords/enum.md)-Typ.</span><span class="sxs-lookup"><span data-stu-id="610ee-112">Any [enum](../../language-reference/keywords/enum.md) type.</span></span>
- <span data-ttu-id="610ee-113">Beliebiger Zeigertyp.</span><span class="sxs-lookup"><span data-stu-id="610ee-113">Any pointer type.</span></span> <span data-ttu-id="610ee-114">Dadurch können Sie Ausdrücke wie `void**` verwenden.</span><span class="sxs-lookup"><span data-stu-id="610ee-114">This allows expressions such as `void**`.</span></span>
- <span data-ttu-id="610ee-115">Beliebiger benutzerdefinierter Strukturtyp, der nur Felder von nicht verwalteten Typen enthält.</span><span class="sxs-lookup"><span data-stu-id="610ee-115">Any user-defined struct type that contains fields of unmanaged types only.</span></span>

<span data-ttu-id="610ee-116">Zeigertypen erben nicht von [object`object`, und es ist keine Konvertierung zwischen Zeigertypen und ](../../language-reference/keywords/object.md) möglich.</span><span class="sxs-lookup"><span data-stu-id="610ee-116">Pointer types do not inherit from [object](../../language-reference/keywords/object.md) and no conversions exist between pointer types and `object`.</span></span> <span data-ttu-id="610ee-117">Weiterhin unterstützen Boxing und Unboxing keine Zeiger.</span><span class="sxs-lookup"><span data-stu-id="610ee-117">Also, boxing and unboxing do not support pointers.</span></span> <span data-ttu-id="610ee-118">Es ist jedoch möglich, Konvertierungen zwischen verschiedenen Zeigertypen sowie zwischen Zeigertypen und ganzzahligen Typen durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="610ee-118">However, you can convert between different pointer types and between pointer types and integral types.</span></span>

<span data-ttu-id="610ee-119">Wenn Sie mehrere Zeiger innerhalb ein- und derselben Deklaration deklarieren, wird das Sternchen (\*) nur einmal mit dem zugrunde liegenden Typ notiert und nicht als Präfix für jeden Zeigernamen verwendet.</span><span class="sxs-lookup"><span data-stu-id="610ee-119">When you declare multiple pointers in the same declaration, the asterisk (\*) is written together with the underlying type only; it is not used as a prefix to each pointer name.</span></span> <span data-ttu-id="610ee-120">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="610ee-120">For example:</span></span>

```csharp
int* p1, p2, p3;   // Ok
int *p1, *p2, *p3;   // Invalid in C#
```

<span data-ttu-id="610ee-121">Ein Zeiger kann nicht auf einen Verweis oder eine [Struktur](../../language-reference/keywords/struct.md) verweisen, die Verweise enthält, da ein Objektverweis auch dann in die Garbage Collection aufgenommen werden kann, wenn ein Zeiger darauf verweist.</span><span class="sxs-lookup"><span data-stu-id="610ee-121">A pointer cannot point to a reference or to a [struct](../../language-reference/keywords/struct.md) that contains references, because an object reference can be garbage collected even if a pointer is pointing to it.</span></span> <span data-ttu-id="610ee-122">In der Garbage Collection wird nicht nachgehalten, ob von einem der Zeigertypen auf ein Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="610ee-122">The garbage collector does not keep track of whether an object is being pointed to by any pointer types.</span></span>

<span data-ttu-id="610ee-123">Der Wert der Zeigervariablen vom Typ `myType*` ist die Adresse einer Variablen vom Typ `myType`.</span><span class="sxs-lookup"><span data-stu-id="610ee-123">The value of the pointer variable of type `myType*` is the address of a variable of type `myType`.</span></span> <span data-ttu-id="610ee-124">Im Folgenden finden Sie Beispiele für Zeigertypdeklarationen:</span><span class="sxs-lookup"><span data-stu-id="610ee-124">The following are examples of pointer type declarations:</span></span>

|<span data-ttu-id="610ee-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="610ee-125">Example</span></span>|<span data-ttu-id="610ee-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="610ee-126">Description</span></span>|
|-------------|-----------------|
|`int* p`|<span data-ttu-id="610ee-127">`p` ist ein Zeiger auf einen ganzzahligen Wert.</span><span class="sxs-lookup"><span data-stu-id="610ee-127">`p` is a pointer to an integer.</span></span>|
|`int** p`|<span data-ttu-id="610ee-128">`p` ist ein Zeiger auf einen Zeiger auf einen ganzzahligen Wert.</span><span class="sxs-lookup"><span data-stu-id="610ee-128">`p` is a pointer to a pointer to an integer.</span></span>|
|`int*[] p`|<span data-ttu-id="610ee-129">`p` ist ein eindimensionales Array von Zeigern auf ganzzahlige Werte.</span><span class="sxs-lookup"><span data-stu-id="610ee-129">`p` is a single-dimensional array of pointers to integers.</span></span>|
|`char* p`|<span data-ttu-id="610ee-130">`p` ist ein Zeiger auf eine char-Variable.</span><span class="sxs-lookup"><span data-stu-id="610ee-130">`p` is a pointer to a char.</span></span>|
|`void* p`|<span data-ttu-id="610ee-131">`p` ist ein Zeiger auf einen unbekannten Typ.</span><span class="sxs-lookup"><span data-stu-id="610ee-131">`p` is a pointer to an unknown type.</span></span>|

<span data-ttu-id="610ee-132">Sie können den Zeigerdereferenzierungsoperator \* verwenden, um auf den Inhalt an der Speicherstelle zuzugreifen, auf die die Zeigervariable zeigt.</span><span class="sxs-lookup"><span data-stu-id="610ee-132">The pointer indirection operator \* can be used to access the contents at the location pointed to by the pointer variable.</span></span> <span data-ttu-id="610ee-133">Betrachten Sie beispielsweise die folgende Deklaration:</span><span class="sxs-lookup"><span data-stu-id="610ee-133">For example, consider the following declaration:</span></span>

```csharp
int* myVariable;
```

<span data-ttu-id="610ee-134">Der Ausdruck `*myVariable` kennzeichnet die `int`-Variable, die sich an der in `myVariable` enthaltenen Adresse befindet.</span><span class="sxs-lookup"><span data-stu-id="610ee-134">The expression `*myVariable` denotes the `int` variable found at the address contained in `myVariable`.</span></span>

<span data-ttu-id="610ee-135">Es gibt mehrere Beispiele von Zeigern in den Themen [fixed-Anweisung](../../language-reference/keywords/fixed-statement.md) und [Zeigerkonvertierungen](../../programming-guide/unsafe-code-pointers/pointer-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="610ee-135">There are several examples of pointers in the topics [fixed Statement](../../language-reference/keywords/fixed-statement.md) and [Pointer Conversions](../../programming-guide/unsafe-code-pointers/pointer-conversions.md).</span></span> <span data-ttu-id="610ee-136">Im folgenden Beispiel wird die Verwendung des `unsafe`-Schlüsselworts und der `fixed`-Anweisung sowie die Vorgehensweise zum Erhöhen eines inneren Zeigers veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="610ee-136">The following example uses the `unsafe` keyword and the `fixed` statement, and shows how to increment an interior pointer.</span></span>  <span data-ttu-id="610ee-137">Sie können diesen Code in die Hauptmethode einer Konsolenanwendung einfügen, um ihn auszuführen.</span><span class="sxs-lookup"><span data-stu-id="610ee-137">You can paste this code into the Main function of a console application to run it.</span></span> <span data-ttu-id="610ee-138">Diese Beispiele müssen mithilfe der Compileroption [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="610ee-138">These examples must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option set.</span></span>

[!code-csharp[Using pointer types](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#5)]

<span data-ttu-id="610ee-139">Der Dereferenzierungsoperator kann nicht auf Zeiger vom Typ `void*` angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="610ee-139">You cannot apply the indirection operator to a pointer of type `void*`.</span></span> <span data-ttu-id="610ee-140">Sie können jedoch eine Umwandlung verwenden, um einen void-Zeiger in einen anderen Zeigertyp und umgekehrt zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="610ee-140">However, you can use a cast to convert a void pointer to any other pointer type, and vice versa.</span></span>

<span data-ttu-id="610ee-141">Ein Zeiger kann den Wert `null` annehmen.</span><span class="sxs-lookup"><span data-stu-id="610ee-141">A pointer can be `null`.</span></span> <span data-ttu-id="610ee-142">Die Anwendung des Dereferenzierungsoperators auf einen NULL-Zeiger führt zu einem in der Implementierung definierten Verhalten.</span><span class="sxs-lookup"><span data-stu-id="610ee-142">Applying the indirection operator to a null pointer causes an implementation-defined behavior.</span></span>

<span data-ttu-id="610ee-143">Die Übergabe von Zeigern zwischen Methoden kann zu nicht definiertem Verhalten führen.</span><span class="sxs-lookup"><span data-stu-id="610ee-143">Passing pointers between methods can cause undefined behavior.</span></span> <span data-ttu-id="610ee-144">Ziehen Sie eine Methode in Betracht, die einen Zeiger auf eine lokale Variable als einen `in`-, `out`- oder `ref`-Parameter oder als Funktionsergebnis zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="610ee-144">Consider a method that returns a pointer to a local variable through an `in`, `out`, or `ref` parameter or as the function result.</span></span> <span data-ttu-id="610ee-145">Wenn der Zeiger in einem fixed-Block festgelegt wurde, ist die Variable, auf die der Zeiger verweist, möglicherweise nicht fixiert.</span><span class="sxs-lookup"><span data-stu-id="610ee-145">If the pointer was set in a fixed block, the variable to which it points may no longer be fixed.</span></span>

<span data-ttu-id="610ee-146">In der folgenden Tabelle werden die Operatoren und Anweisungen aufgelistet, die in einem unsicheren Kontext auf Zeiger angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="610ee-146">The following table lists the operators and statements that can operate on pointers in an unsafe context:</span></span>

|<span data-ttu-id="610ee-147">Operator/Anweisung</span><span class="sxs-lookup"><span data-stu-id="610ee-147">Operator/Statement</span></span>|<span data-ttu-id="610ee-148">Mit</span><span class="sxs-lookup"><span data-stu-id="610ee-148">Use</span></span>|
|-------------------------|---------|
|*|<span data-ttu-id="610ee-149">Führt eine Zeigerdereferenzierung aus.</span><span class="sxs-lookup"><span data-stu-id="610ee-149">Performs pointer indirection.</span></span>|
|->|<span data-ttu-id="610ee-150">Greift über einen Zeiger auf einen Member einer Struktur zu.</span><span class="sxs-lookup"><span data-stu-id="610ee-150">Accesses a member of a struct through a pointer.</span></span>|
|<span data-ttu-id="610ee-151">[]</span><span class="sxs-lookup"><span data-stu-id="610ee-151">[]</span></span>|<span data-ttu-id="610ee-152">Indiziert einen Zeiger.</span><span class="sxs-lookup"><span data-stu-id="610ee-152">Indexes a pointer.</span></span>|
|`&`|<span data-ttu-id="610ee-153">Ruft die Adresse einer Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="610ee-153">Obtains the address of a variable.</span></span>|
|<span data-ttu-id="610ee-154">++ und --</span><span class="sxs-lookup"><span data-stu-id="610ee-154">++ and --</span></span>|<span data-ttu-id="610ee-155">Inkrementiert und dekrementiert Zeiger.</span><span class="sxs-lookup"><span data-stu-id="610ee-155">Increments and decrements pointers.</span></span>|
|<span data-ttu-id="610ee-156">+ und -</span><span class="sxs-lookup"><span data-stu-id="610ee-156">+ and -</span></span>|<span data-ttu-id="610ee-157">Führt Zeigerarithmetik aus.</span><span class="sxs-lookup"><span data-stu-id="610ee-157">Performs pointer arithmetic.</span></span>|
|<span data-ttu-id="610ee-158">==, !=, \<, >, \<=, und >=</span><span class="sxs-lookup"><span data-stu-id="610ee-158">==, !=, \<, >, \<=, and >=</span></span>|<span data-ttu-id="610ee-159">Vergleicht Zeiger.</span><span class="sxs-lookup"><span data-stu-id="610ee-159">Compares pointers.</span></span>|
|`stackalloc`|<span data-ttu-id="610ee-160">Belegt Speicher für den Stapel.</span><span class="sxs-lookup"><span data-stu-id="610ee-160">Allocates memory on the stack.</span></span>|
|<span data-ttu-id="610ee-161">`fixed`-Anweisung</span><span class="sxs-lookup"><span data-stu-id="610ee-161">`fixed` statement</span></span>|<span data-ttu-id="610ee-162">Fixiert eine Variable vorübergehend, damit ihre Adresse gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="610ee-162">Temporarily fixes a variable so that its address may be found.</span></span>|

## <a name="c-language-specification"></a><span data-ttu-id="610ee-163">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="610ee-163">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="610ee-164">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="610ee-164">See Also</span></span>

- [<span data-ttu-id="610ee-165">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="610ee-165">C# Programming Guide</span></span>](../index.md)  
- [<span data-ttu-id="610ee-166">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="610ee-166">Unsafe Code and Pointers</span></span>](index.md)  
- [<span data-ttu-id="610ee-167">Zeigerkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="610ee-167">Pointer Conversions</span></span>](pointer-conversions.md)  
- [<span data-ttu-id="610ee-168">Zeigerausdrücke</span><span class="sxs-lookup"><span data-stu-id="610ee-168">Pointer Expressions</span></span>](pointer-expressions.md)  
- [<span data-ttu-id="610ee-169">Typen</span><span class="sxs-lookup"><span data-stu-id="610ee-169">Types</span></span>](../../language-reference/keywords/types.md)  
- [<span data-ttu-id="610ee-170">unsafe</span><span class="sxs-lookup"><span data-stu-id="610ee-170">unsafe</span></span>](../../language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="610ee-171">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="610ee-171">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="610ee-172">stackalloc</span><span class="sxs-lookup"><span data-stu-id="610ee-172">stackalloc</span></span>](../../language-reference/keywords/stackalloc.md)  
- [<span data-ttu-id="610ee-173">Boxing und Unboxing</span><span class="sxs-lookup"><span data-stu-id="610ee-173">Boxing and Unboxing</span></span>](../types/boxing-and-unboxing.md)
