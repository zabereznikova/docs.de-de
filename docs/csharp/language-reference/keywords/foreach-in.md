---
title: foreach, in (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- foreach
- foreach_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
caps.latest.revision: 29
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
ms.openlocfilehash: aed1d4f086f0b1334df750fd912d20d66326a043
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="0fc0e-102">foreach, in (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="0fc0e-102">foreach, in (C# Reference)</span></span>
<span data-ttu-id="0fc0e-103">Mit der `foreach`-Anweisung wird eine Gruppe von eingebetteten Anweisungen für jedes Element in einem Array oder einer Objektauflistung wiederholt, das die Schnittstelle <xref:System.Collections.IEnumerable?displayProperty=fullName> oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> implementiert.</span><span class="sxs-lookup"><span data-stu-id="0fc0e-103">The `foreach` statement repeats a group of embedded statements for each element in an array or an object collection that implements the <xref:System.Collections.IEnumerable?displayProperty=fullName> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> interface.</span></span> <span data-ttu-id="0fc0e-104">Die `foreach`-Anweisung wird verwendet, um die Auflistung zu durchlaufen und dadurch die gewünschten Informationen zu erhalten. Setzen Sie sie nicht ein, um der Auflistung Elemente hinzuzufügen oder aus ihr zu entfernen, um unvorhersehbare Nebeneffekte zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="0fc0e-104">The `foreach` statement is used to iterate through the collection to get the information that you want, but can not be used to add or remove items from the source collection to avoid unpredictable side effects.</span></span> <span data-ttu-id="0fc0e-105">Wenn Sie Elemente zu der Quellauflistung hinzufügen oder daraus entfernen müssen, verwenden Sie eine [for](../../../csharp/language-reference/keywords/for.md)-Schleife.</span><span class="sxs-lookup"><span data-stu-id="0fc0e-105">If you need to add or remove items from the source collection, use a [for](../../../csharp/language-reference/keywords/for.md) loop.</span></span>  
  
 <span data-ttu-id="0fc0e-106">Die Ausführung der eingebetteten Anweisungen wird für jedes Element in dem Array oder der Auflistung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="0fc0e-106">The embedded statements continue to execute for each element in the array or collection.</span></span> <span data-ttu-id="0fc0e-107">Nachdem die Iteration alle Elemente in der Auflistung durchlaufen hat, wird die Steuerung an die nächste Anweisung, die auf den `foreach`-Block folgt, übergeben.</span><span class="sxs-lookup"><span data-stu-id="0fc0e-107">After the iteration has been completed for all the elements in the collection, control is transferred to the next statement following the `foreach` block.</span></span>  
  
 <span data-ttu-id="0fc0e-108">Sie können die Schleife an jedem Punkt im `foreach`-Block mit dem Schlüsselwort [break](../../../csharp/language-reference/keywords/break.md) unterbrechen oder mit dem Schlüsselwort [continue](../../../csharp/language-reference/keywords/continue.md) direkt zum nächsten Durchlauf der Schleife springen.</span><span class="sxs-lookup"><span data-stu-id="0fc0e-108">At any point within the `foreach` block, you can break out of the loop by using the [break](../../../csharp/language-reference/keywords/break.md) keyword, or step to the next iteration in the loop by using the [continue](../../../csharp/language-reference/keywords/continue.md) keyword.</span></span>  
  
 <span data-ttu-id="0fc0e-109">Eine `foreach`-Schleife kann durch die Anweisungen [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) oder [throw](../../../csharp/language-reference/keywords/throw.md) beendet werden.</span><span class="sxs-lookup"><span data-stu-id="0fc0e-109">A `foreach` loop can also be exited by the [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statements.</span></span>  
  
 <span data-ttu-id="0fc0e-110">Weitere Informationen zum `foreach`-Schlüsselwort und zu Codebeispielen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="0fc0e-110">For more information about the `foreach` keyword and code samples, see the following topics:</span></span>  
  
 [<span data-ttu-id="0fc0e-111">Verwenden von foreach mit Arrays</span><span class="sxs-lookup"><span data-stu-id="0fc0e-111">Using foreach with Arrays</span></span>](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
 [<span data-ttu-id="0fc0e-112">Gewusst wie: Zugreifen auf Sammlungsklassen mit foreach</span><span class="sxs-lookup"><span data-stu-id="0fc0e-112">How to: Access a Collection Class with foreach</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  
  
## <a name="example"></a><span data-ttu-id="0fc0e-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0fc0e-113">Example</span></span>  
 <span data-ttu-id="0fc0e-114">Der folgende Code zeigt drei Beispiele:</span><span class="sxs-lookup"><span data-stu-id="0fc0e-114">The following code shows three examples:</span></span>  
  
-   <span data-ttu-id="0fc0e-115">eine typische `foreach`-Schleife, die den Inhalt eines Arrays von Ganzzahlen anzeigt</span><span class="sxs-lookup"><span data-stu-id="0fc0e-115">a typical `foreach` loop that displays the contents of an array of integers</span></span>  
  
-   <span data-ttu-id="0fc0e-116">eine [for](../../../csharp/language-reference/keywords/for.md)-Schleife, die die gleiche Aufgabe ausführt</span><span class="sxs-lookup"><span data-stu-id="0fc0e-116">a [for](../../../csharp/language-reference/keywords/for.md) loop that does the same thing</span></span>  
  
-   <span data-ttu-id="0fc0e-117">eine `foreach`-Schleife, die die Anzahl von Elementen im Array enthält</span><span class="sxs-lookup"><span data-stu-id="0fc0e-117">a `foreach` loop that maintains a count of the number of elements in the array</span></span>  
  
 <span data-ttu-id="0fc0e-118">[!code-cs[csrefKeywordsIteration#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/foreach-in_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0fc0e-118">[!code-cs[csrefKeywordsIteration#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/foreach-in_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="0fc0e-119">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="0fc0e-119">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0fc0e-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0fc0e-120">See Also</span></span>  
 <span data-ttu-id="0fc0e-121">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="0fc0e-121">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="0fc0e-122">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0fc0e-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0fc0e-123">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="0fc0e-123">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="0fc0e-124">[Iterationsanweisungen](../../../csharp/language-reference/keywords/iteration-statements.md) </span><span class="sxs-lookup"><span data-stu-id="0fc0e-124">[Iteration Statements](../../../csharp/language-reference/keywords/iteration-statements.md) </span></span>  
 [<span data-ttu-id="0fc0e-125">for</span><span class="sxs-lookup"><span data-stu-id="0fc0e-125">for</span></span>](../../../csharp/language-reference/keywords/for.md)

