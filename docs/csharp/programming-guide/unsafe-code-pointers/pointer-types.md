---
title: Zeigertypen (C#-Programmierhandbuch)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.assetid: 3319faf9-336d-4148-9af2-1da2579cdd1e
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fe7b926bdf9f662d25f2fe960b51fc8254b7aa3a
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
# <a name="pointer-types-c-programming-guide"></a><span data-ttu-id="d9c8c-102">Zeigertypen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="d9c8c-102">Pointer types (C# Programming Guide)</span></span>
<span data-ttu-id="d9c8c-103">In einem unsicheren Kontext kann ein Typ sowohl ein Zeigertyp als auch ein Werttyp oder Verweistyp sein.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-103">In an unsafe context, a type may be a pointer type, a value type, or a reference type.</span></span> <span data-ttu-id="d9c8c-104">Eine Zeigertypdeklaration erfolgt in einer der folgenden Formen:</span><span class="sxs-lookup"><span data-stu-id="d9c8c-104">A pointer type declaration takes one of the following forms:</span></span>  
  
```  
type* identifier;  
void* identifier; //allowed but not recommended  
```  
  
 <span data-ttu-id="d9c8c-105">Die folgenden Typen können Zeigertypen sein:</span><span class="sxs-lookup"><span data-stu-id="d9c8c-105">Any of the following types may be a pointer type:</span></span>  
  
-   <span data-ttu-id="d9c8c-106">[sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [char](../../../csharp/language-reference/keywords/char.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), [decimal](../../../csharp/language-reference/keywords/decimal.md) oder [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="d9c8c-106">[sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [char](../../../csharp/language-reference/keywords/char.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), [decimal](../../../csharp/language-reference/keywords/decimal.md), or [bool](../../../csharp/language-reference/keywords/bool.md).</span></span>  
  
-   <span data-ttu-id="d9c8c-107">Beliebiger [enum](../../../csharp/language-reference/keywords/enum.md)-Typ.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-107">Any [enum](../../../csharp/language-reference/keywords/enum.md) type.</span></span>  
  
-   <span data-ttu-id="d9c8c-108">Beliebiger Zeigertyp.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-108">Any pointer type.</span></span>  
  
-   <span data-ttu-id="d9c8c-109">Beliebiger benutzerdefinierter Strukturtyp, der nur Felder von nicht verwalteten Typen enthält.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-109">Any user-defined struct type that contains fields of unmanaged types only.</span></span>  
  
 <span data-ttu-id="d9c8c-110">Zeigertypen erben nicht von [object`object`, und es ist keine Konvertierung zwischen Zeigertypen und ](../../../csharp/language-reference/keywords/object.md) möglich.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-110">Pointer types do not inherit from [object](../../../csharp/language-reference/keywords/object.md) and no conversions exist between pointer types and `object`.</span></span> <span data-ttu-id="d9c8c-111">Weiterhin unterstützen Boxing und Unboxing keine Zeiger.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-111">Also, boxing and unboxing do not support pointers.</span></span> <span data-ttu-id="d9c8c-112">Es ist jedoch möglich, Konvertierungen zwischen verschiedenen Zeigertypen sowie zwischen Zeigertypen und ganzzahligen Typen durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-112">However, you can convert between different pointer types and between pointer types and integral types.</span></span>  
  
 <span data-ttu-id="d9c8c-113">Wenn Sie mehrere Zeiger innerhalb ein- und derselben Deklaration deklarieren, wird das Sternchen (\*) nur einmal mit dem zugrunde liegenden Typ notiert und nicht als Präfix für jeden Zeigernamen verwendet.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-113">When you declare multiple pointers in the same declaration, the asterisk (\*) is written together with the underlying type only; it is not used as a prefix to each pointer name.</span></span> <span data-ttu-id="d9c8c-114">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d9c8c-114">For example:</span></span>  
  
```  
int* p1, p2, p3;   // Ok  
int *p1, *p2, *p3;   // Invalid in C#  
```  
  
 <span data-ttu-id="d9c8c-115">Ein Zeiger kann nicht auf einen Verweis oder eine [Struktur](../../../csharp/language-reference/keywords/struct.md) verweisen, die Verweise enthält, da ein Objektverweis auch dann in die Garbage Collection aufgenommen werden kann, wenn ein Zeiger darauf verweist.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-115">A pointer cannot point to a reference or to a [struct](../../../csharp/language-reference/keywords/struct.md) that contains references, because an object reference can be garbage collected even if a pointer is pointing to it.</span></span> <span data-ttu-id="d9c8c-116">In der Garbage Collection wird nicht nachgehalten, ob von einem der Zeigertypen auf ein Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-116">The garbage collector does not keep track of whether an object is being pointed to by any pointer types.</span></span>  
  
 <span data-ttu-id="d9c8c-117">Der Wert der Zeigervariablen vom Typ `myType*` ist die Adresse einer Variablen vom Typ `myType`.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-117">The value of the pointer variable of type `myType*` is the address of a variable of type `myType`.</span></span> <span data-ttu-id="d9c8c-118">Im Folgenden finden Sie Beispiele für Zeigertypdeklarationen:</span><span class="sxs-lookup"><span data-stu-id="d9c8c-118">The following are examples of pointer type declarations:</span></span>  
  
|<span data-ttu-id="d9c8c-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d9c8c-119">Example</span></span>|<span data-ttu-id="d9c8c-120">description</span><span class="sxs-lookup"><span data-stu-id="d9c8c-120">Description</span></span>|  
|-------------|-----------------|  
|`int* p`|<span data-ttu-id="d9c8c-121">`p` ist ein Zeiger auf einen ganzzahligen Wert.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-121">`p` is a pointer to an integer.</span></span>|  
|`int** p`|<span data-ttu-id="d9c8c-122">`p` ist ein Zeiger auf einen Zeiger auf einen ganzzahligen Wert.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-122">`p` is a pointer to a pointer to an integer.</span></span>|  
|`int*[] p`|<span data-ttu-id="d9c8c-123">`p` ist ein eindimensionales Array von Zeigern auf ganzzahlige Werte.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-123">`p` is a single-dimensional array of pointers to integers.</span></span>|  
|`char* p`|<span data-ttu-id="d9c8c-124">`p` ist ein Zeiger auf eine char-Variable.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-124">`p` is a pointer to a char.</span></span>|  
|`void* p`|<span data-ttu-id="d9c8c-125">`p` ist ein Zeiger auf einen unbekannten Typ.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-125">`p` is a pointer to an unknown type.</span></span>|  
  
 <span data-ttu-id="d9c8c-126">Sie können den Zeigerdereferenzierungsoperator \* verwenden, um auf den Inhalt an der Speicherstelle zuzugreifen, auf die die Zeigervariable zeigt.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-126">The pointer indirection operator \* can be used to access the contents at the location pointed to by the pointer variable.</span></span> <span data-ttu-id="d9c8c-127">Betrachten Sie beispielsweise die folgende Deklaration:</span><span class="sxs-lookup"><span data-stu-id="d9c8c-127">For example, consider the following declaration:</span></span>  
  
```  
int* myVariable;  
```  
  
 <span data-ttu-id="d9c8c-128">Der Ausdruck `*myVariable` kennzeichnet die `int`-Variable, die sich an der in `myVariable` enthaltenen Adresse befindet.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-128">The expression `*myVariable` denotes the `int` variable found at the address contained in `myVariable`.</span></span>  
  
 <span data-ttu-id="d9c8c-129">Es gibt mehrere Beispiele von Zeigern in den Themen [fixed-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md) und [Zeigerkonvertierungen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="d9c8c-129">There are several examples of pointers in the topics [fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) and [Pointer Conversions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md).</span></span>  <span data-ttu-id="d9c8c-130">Im folgenden Beispiel wird die Notwendigkeit für das `unsafe`-Schlüsselwort und die `fixed`-Anweisung sowie die Vorgehensweise zum Erhöhen eines inneren Zeigers veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-130">The following example shows the need for the `unsafe` keyword and the `fixed` statement, and how to increment an interior pointer.</span></span>  <span data-ttu-id="d9c8c-131">Sie können diesen Code in die Hauptmethode einer Konsolenanwendung einfügen, um ihn auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-131">You can paste this code into the Main function of a console application to run it.</span></span> <span data-ttu-id="d9c8c-132">(Denken Sie daran, unsicheren Code im **Projekt-Designer** zu aktivieren. Wählen Sie in der Menüleiste **Projekt**, **Eigenschaften** aus, und wählen Sie anschließend **Unsicheren Code zulassen** auf der Registerkarte **Erstellen** aus.)</span><span class="sxs-lookup"><span data-stu-id="d9c8c-132">(Remember to enable unsafe code in the **Project Designer**; choose **Project**, **Properties** on the menu bar, and then select **Allow unsafe code** in the **Build** tab.)</span></span>  
  
```  
// Normal pointer to an object.  
int[] a = new int[5] {10, 20, 30, 40, 50};  
// Must be in unsafe code to use interior pointers.  
unsafe  
{  
    // Must pin object on heap so that it doesn't move while using interior pointers.  
    fixed (int* p = &a[0])  
    {  
        // p is pinned as well as object, so create another pointer to show incrementing it.  
        int* p2 = p;  
        Console.WriteLine(*p2);  
        // Incrementing p2 bumps the pointer by four bytes due to its type ...  
        p2 += 1;  
        Console.WriteLine(*p2);  
        p2 += 1;  
        Console.WriteLine(*p2);  
        Console.WriteLine("--------");  
        Console.WriteLine(*p);  
        // Deferencing p and incrementing changes the value of a[0] ...  
        *p += 1;  
        Console.WriteLine(*p);  
        *p += 1;  
        Console.WriteLine(*p);  
    }  
}  
  
Console.WriteLine("--------");  
Console.WriteLine(a[0]);  
Console.ReadLine();  
  
// Output:  
//10  
//20  
//30  
//--------  
//10  
//11  
//12  
//--------  
//12  
```  
  
 <span data-ttu-id="d9c8c-133">Der Dereferenzierungsoperator kann nicht auf Zeiger vom Typ `void*` angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-133">You cannot apply the indirection operator to a pointer of type `void*`.</span></span> <span data-ttu-id="d9c8c-134">Sie können jedoch eine Umwandlung verwenden, um einen void-Zeiger in einen anderen Zeigertyp und umgekehrt zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-134">However, you can use a cast to convert a void pointer to any other pointer type, and vice versa.</span></span>  
  
 <span data-ttu-id="d9c8c-135">Ein Zeiger kann den Wert `null` annehmen.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-135">A pointer can be `null`.</span></span> <span data-ttu-id="d9c8c-136">Die Anwendung des Dereferenzierungsoperators auf einen NULL-Zeiger führt zu einem in der Implementierung definierten Verhalten.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-136">Applying the indirection operator to a null pointer causes an implementation-defined behavior.</span></span>  
  
 <span data-ttu-id="d9c8c-137">Beachten Sie, dass die Übergabe von Zeigern zwischen Methoden zu nicht definiertem Verhalten führen kann.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-137">Be aware that passing pointers between methods can cause undefined behavior.</span></span> <span data-ttu-id="d9c8c-138">Ziehen Sie eine Methode in Betracht, die einen Zeiger auf eine lokale Variable als einen `in`-, `out`- oder `ref`-Parameter oder als Funktionsergebnis zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-138">Consider a method that returns a pointer to a local variable through an `in`, `out` or `ref` parameter or as the function result.</span></span> <span data-ttu-id="d9c8c-139">Wenn der Zeiger in einem fixed-Block festgelegt wurde, ist die Variable, auf die der Zeiger verweist, möglicherweise nicht fixiert.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-139">If the pointer was set in a fixed block, the variable to which it points may no longer be fixed.</span></span>  
  
 <span data-ttu-id="d9c8c-140">In der folgenden Tabelle werden die Operatoren und Anweisungen aufgelistet, die in einem unsicheren Kontext auf Zeiger angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-140">The following table lists the operators and statements that can operate on pointers in an unsafe context:</span></span>  
  
|<span data-ttu-id="d9c8c-141">Operator/Anweisung</span><span class="sxs-lookup"><span data-stu-id="d9c8c-141">Operator/Statement</span></span>|<span data-ttu-id="d9c8c-142">Mit</span><span class="sxs-lookup"><span data-stu-id="d9c8c-142">Use</span></span>|  
|-------------------------|---------|  
|*|<span data-ttu-id="d9c8c-143">Führt eine Zeigerdereferenzierung aus.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-143">Performs pointer indirection.</span></span>|  
|->|<span data-ttu-id="d9c8c-144">Greift über einen Zeiger auf einen Member einer Struktur zu.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-144">Accesses a member of a struct through a pointer.</span></span>|  
|<span data-ttu-id="d9c8c-145">[]</span><span class="sxs-lookup"><span data-stu-id="d9c8c-145">[]</span></span>|<span data-ttu-id="d9c8c-146">Indiziert einen Zeiger.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-146">Indexes a pointer.</span></span>|  
|`&`|<span data-ttu-id="d9c8c-147">Ruft die Adresse einer Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-147">Obtains the address of a variable.</span></span>|  
|<span data-ttu-id="d9c8c-148">++ und --</span><span class="sxs-lookup"><span data-stu-id="d9c8c-148">++ and --</span></span>|<span data-ttu-id="d9c8c-149">Inkrementiert und dekrementiert Zeiger.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-149">Increments and decrements pointers.</span></span>|  
|<span data-ttu-id="d9c8c-150">+ und -</span><span class="sxs-lookup"><span data-stu-id="d9c8c-150">+ and -</span></span>|<span data-ttu-id="d9c8c-151">Führt Zeigerarithmetik aus.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-151">Performs pointer arithmetic.</span></span>|  
|<span data-ttu-id="d9c8c-152">==, !=, \<, >, \<=, und >=</span><span class="sxs-lookup"><span data-stu-id="d9c8c-152">==, !=, \<, >, \<=, and >=</span></span>|<span data-ttu-id="d9c8c-153">Vergleicht Zeiger.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-153">Compares pointers.</span></span>|  
|`stackalloc`|<span data-ttu-id="d9c8c-154">Belegt Speicher für den Stapel.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-154">Allocates memory on the stack.</span></span>|  
|<span data-ttu-id="d9c8c-155">`fixed`-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d9c8c-155">`fixed` statement</span></span>|<span data-ttu-id="d9c8c-156">Fixiert eine Variable vorübergehend, damit ihre Adresse gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="d9c8c-156">Temporarily fixes a variable so that its address may be found.</span></span>|  
  
## <a name="c-language-specification"></a><span data-ttu-id="d9c8c-157">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="d9c8c-157">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d9c8c-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9c8c-158">See Also</span></span>  
 [<span data-ttu-id="d9c8c-159">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d9c8c-159">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d9c8c-160">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="d9c8c-160">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="d9c8c-161">Zeigerkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="d9c8c-161">Pointer Conversions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md)  
 [<span data-ttu-id="d9c8c-162">Zeigerausdrücke</span><span class="sxs-lookup"><span data-stu-id="d9c8c-162">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="d9c8c-163">Typen</span><span class="sxs-lookup"><span data-stu-id="d9c8c-163">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="d9c8c-164">unsafe</span><span class="sxs-lookup"><span data-stu-id="d9c8c-164">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="d9c8c-165">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d9c8c-165">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="d9c8c-166">stackalloc</span><span class="sxs-lookup"><span data-stu-id="d9c8c-166">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)  
 [<span data-ttu-id="d9c8c-167">Boxing und Unboxing</span><span class="sxs-lookup"><span data-stu-id="d9c8c-167">Boxing and Unboxing</span></span>](../../../csharp/programming-guide/types/boxing-and-unboxing.md)
