---
title: "Gewusst wie: Unterschiede zwischen dem Übergeben einer Struktur und dem Übergeben eines Klassenverweises an eine Methode (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- structs [C#], passing as method parameter
- passing parameters [C#], structs vs. classes
- methods [C#], passing classes vs. structs
ms.assetid: 9c1313a6-32a8-4ea7-a59f-450f66af628b
caps.latest.revision: 25
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1a4508c8765ac678fd371180cb0c3ece3e1d9a44
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-know-the-difference-between-passing-a-struct-and-passing-a-class-reference-to-a-method-c-programming-guide"></a><span data-ttu-id="060d7-102">Gewusst wie: Unterschiede zwischen dem Übergeben einer Struktur und dem Übergeben eines Klassenverweises an eine Methode (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="060d7-102">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method (C# Programming Guide)</span></span>
<span data-ttu-id="060d7-103">Das folgende Beispiel stellt dar, wie die Übergabe einer [Struktur](../../../csharp/language-reference/keywords/struct.md) an eine Methode sich von der Übergabe einer [Klasseninstanz](../../../csharp/language-reference/keywords/class.md) an eine Methode unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="060d7-103">The following example demonstrates how passing a [struct](../../../csharp/language-reference/keywords/struct.md) to a method differs from passing a [class](../../../csharp/language-reference/keywords/class.md) instance to a method.</span></span> <span data-ttu-id="060d7-104">Im Beispiel werden beide Argumente (Struktur und Klasseninstanz) nach Wert übergeben, und beide Methoden ändern den Wert eines Felds des Arguments.</span><span class="sxs-lookup"><span data-stu-id="060d7-104">In the example, both of the arguments (struct and class instance) are passed by value, and both methods change the value of one field of the argument.</span></span> <span data-ttu-id="060d7-105">Allerdings sind die Ergebnisse der beiden Methoden nicht identisch, denn wenn Sie eine Struktur übergeben, unterscheidet sich dies von dem, wenn Sie eine Instanz einer Klasse übergeben.</span><span class="sxs-lookup"><span data-stu-id="060d7-105">However, the results of the two methods are not the same because what is passed when you pass a struct differs from what is passed when you pass an instance of a class.</span></span>  
  
 <span data-ttu-id="060d7-106">Da eine Struktur ein [Werttyp](../../../csharp/language-reference/keywords/value-types.md) ist, wenn Sie [eine Struktur nach Wert](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md) an eine Methode übergeben, erhält und funktioniert die Methode nur mit einer Kopie des Strukturarguments.</span><span class="sxs-lookup"><span data-stu-id="060d7-106">Because a struct is a [value type](../../../csharp/language-reference/keywords/value-types.md), when you [pass a struct by value](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md) to a method, the method receives and operates on a copy of the struct argument.</span></span> <span data-ttu-id="060d7-107">Die Methode hat keinen Zugriff auf die ursprüngliche Struktur in der aufrufenden Methode und kann sie deshalb nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="060d7-107">The method has no access to the original struct in the calling method and therefore can't change it in any way.</span></span> <span data-ttu-id="060d7-108">Die Methode kann nur die Kopie ändern.</span><span class="sxs-lookup"><span data-stu-id="060d7-108">The method can change only the copy.</span></span>  
  
 <span data-ttu-id="060d7-109">Eine Instanz der Klasse ist ein [Verweistyp](../../../csharp/language-reference/keywords/reference-types.md), kein Werttyp.</span><span class="sxs-lookup"><span data-stu-id="060d7-109">A class instance is a [reference type](../../../csharp/language-reference/keywords/reference-types.md), not a value type.</span></span> <span data-ttu-id="060d7-110">Wenn [ein Verweistyp als Wert](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md) an eine Methode übergeben wird, erhält die Methode eine Kopie des Verweises auf die Klasseninstanz.</span><span class="sxs-lookup"><span data-stu-id="060d7-110">When [a reference type is passed by value](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md) to a method, the method receives a copy of the reference to the class instance.</span></span> <span data-ttu-id="060d7-111">Die Methode erhält also eine Kopie der Adresse der Instanz, keine Kopie der Instanz selbst.</span><span class="sxs-lookup"><span data-stu-id="060d7-111">That is, the method receives a copy of the address of the instance, not a copy of the instance itself.</span></span> <span data-ttu-id="060d7-112">Die Klasseninstanz in der aufrufenden Methode verfügt über eine Adresse, der Parameter in der aufgerufenen Methode verfügt über eine Kopie der Adresse und beide Adressen verweisen auf dasselbe Objekt.</span><span class="sxs-lookup"><span data-stu-id="060d7-112">The class instance in the calling method has an address, the parameter in the called method has a copy of the address, and both addresses refer to the same object.</span></span> <span data-ttu-id="060d7-113">Da der Parameter nur eine Kopie der Adresse enthält, kann die aufgerufene Methode nicht die Adresse der Klasseninstanz in der aufrufenden Methode ändern.</span><span class="sxs-lookup"><span data-stu-id="060d7-113">Because the parameter contains only a copy of the address, the called method cannot change the address of the class instance in the calling method.</span></span> <span data-ttu-id="060d7-114">Allerdings kann die aufgerufene Methode die Adresse verwenden, um auf die Klassenmember zuzugreifen, auf die sich die ursprüngliche Adresse sowie die Kopie beziehen.</span><span class="sxs-lookup"><span data-stu-id="060d7-114">However, the called method can use the address to access the class members that both the original address and the copy reference.</span></span> <span data-ttu-id="060d7-115">Wenn die aufgerufene Methode einen Klassenmember ändert, ändert sich auch die ursprüngliche Klasseninstanz in der aufrufenden Methode.</span><span class="sxs-lookup"><span data-stu-id="060d7-115">If the called method changes a class member, the original class instance in the calling method also changes.</span></span>  
  
 <span data-ttu-id="060d7-116">Die Ausgabe des folgenden Beispiels veranschaulicht den Unterschied.</span><span class="sxs-lookup"><span data-stu-id="060d7-116">The output of the following example illustrates the difference.</span></span> <span data-ttu-id="060d7-117">Der Wert des Felds `willIChange` der Klasseninstanz wird durch den Aufruf auf die Methode `ClassTaker` geändert, da die Methode die Adresse im Parameter verwendet, um das angegebene Feld der Klasseninstanz zu finden.</span><span class="sxs-lookup"><span data-stu-id="060d7-117">The value of the `willIChange` field of the class instance is changed by the call to method `ClassTaker` because the method uses the address in the parameter to find the specified field of the class instance.</span></span> <span data-ttu-id="060d7-118">Das Feld `willIChange` der Struktur in der aufrufenden Methode wird nicht durch den Aufruf auf die Methode `StructTaker` geändert, da der Wert des Arguments eine Kopie der Struktur selbst ist und keine Kopie deren Adresse.</span><span class="sxs-lookup"><span data-stu-id="060d7-118">The `willIChange` field of the struct in the calling method is not changed by the call to method `StructTaker` because the value of the argument is a copy of the struct itself, not a copy of its address.</span></span> <span data-ttu-id="060d7-119">`StructTaker` ändert die Kopie, und die Kopie wird abgebrochen, wenn der Aufruf auf `StructTaker` abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="060d7-119">`StructTaker` changes the copy, and the copy is lost when the call to `StructTaker` is completed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="060d7-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="060d7-120">Example</span></span>  
 <span data-ttu-id="060d7-121">[!code-cs[csProgGuideObjects#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="060d7-121">[!code-cs[csProgGuideObjects#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="060d7-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="060d7-122">See Also</span></span>  
 <span data-ttu-id="060d7-123">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="060d7-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="060d7-124">[Klassen](../../../csharp/programming-guide/classes-and-structs/classes.md) </span><span class="sxs-lookup"><span data-stu-id="060d7-124">[Classes](../../../csharp/programming-guide/classes-and-structs/classes.md) </span></span>  
 <span data-ttu-id="060d7-125">[Strukturen](../../../csharp/programming-guide/classes-and-structs/structs.md) </span><span class="sxs-lookup"><span data-stu-id="060d7-125">[Structs](../../../csharp/programming-guide/classes-and-structs/structs.md) </span></span>  
 [<span data-ttu-id="060d7-126">Übergeben von Parametern</span><span class="sxs-lookup"><span data-stu-id="060d7-126">Passing Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)

