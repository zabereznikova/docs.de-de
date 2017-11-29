---
title: 'Gewusst wie: Zugreifen auf Auflistungsklassen mit foreach (C#-Programmierhandbuch)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: collection classes [C#], foreach statement
ms.assetid: a6b9cf5c-6c8d-4223-b12c-288949434493
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0cf827e958d4dc3b951d17b53effd155356c0ca5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-a-collection-class-with-foreach-c-programming-guide"></a><span data-ttu-id="e8144-102">Gewusst wie: Zugreifen auf Auflistungsklassen mit foreach (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="e8144-102">How to: Access a Collection Class with foreach (C# Programming Guide)</span></span>
<span data-ttu-id="e8144-103">Das folgende Codebeispiel zeigt, wie Sie eine nicht generische Auflistungsklasse schreiben, die mit [foreach](../../../csharp/language-reference/keywords/foreach-in.md) verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e8144-103">The following code example illustrates how to write a non-generic collection class that can be used with [foreach](../../../csharp/language-reference/keywords/foreach-in.md).</span></span> <span data-ttu-id="e8144-104">Das Beispiel definiert eine Zeichenfolgen-Tokenisierungsklasse.</span><span class="sxs-lookup"><span data-stu-id="e8144-104">The example defines a string tokenizer class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e8144-105">Das Beispiel stellt nur die empfohlene Vorgehensweise dar, wenn Sie keine generische Auflistungsklasse verwenden können.</span><span class="sxs-lookup"><span data-stu-id="e8144-105">This example represents recommended practice only when you cannot use a generic collection class.</span></span> <span data-ttu-id="e8144-106">Ein Beispiel wie eine typsichere generische Auflistungsklasse implementiert wird, die <xref:System.Collections.Generic.IEnumerable%601> unterstützt, finden Sie unter [Iterators (Iteratoren)](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="e8144-106">For an example of how to implement a type-safe generic collection class that supports <xref:System.Collections.Generic.IEnumerable%601>, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
 <span data-ttu-id="e8144-107">Im Beispiel verwendet das folgende Codesegment die `Tokens`-Klasse, um den Satz „Dies ist ein Beispielsatz“.</span><span class="sxs-lookup"><span data-stu-id="e8144-107">In the example, the following code segment uses the `Tokens` class to break the sentence "This is a sample sentence."</span></span> <span data-ttu-id="e8144-108">in Token aufzuteilen, indem „ “ und „-“ als Trennzeichen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e8144-108">into tokens by using ' ' and '-' as separators.</span></span> <span data-ttu-id="e8144-109">Der Code zeigt anschließend diese Tokens mithilfe einer `foreach`-Anweisung an.</span><span class="sxs-lookup"><span data-stu-id="e8144-109">The code then displays those tokens by using a `foreach` statement.</span></span>  
  
 [!code-csharp[csProgGuideCollections#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="e8144-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e8144-110">Example</span></span>  
 <span data-ttu-id="e8144-111">Die `Tokens`-Klasse verwendet intern ein Array, um die Token zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e8144-111">Internally, the `Tokens` class uses an array to store the tokens.</span></span> <span data-ttu-id="e8144-112">Da Arrays <xref:System.Collections.IEnumerator> und <xref:System.Collections.IEnumerable> implementieren, hätte das Codebeispiel die Enumerationsmethoden des Arrays (<xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A> und <xref:System.Collections.IEnumerator.Current%2A>) verwenden können, anstatt sie in der Klasse `Tokens` zu definieren.</span><span class="sxs-lookup"><span data-stu-id="e8144-112">Because arrays implement <xref:System.Collections.IEnumerator> and <xref:System.Collections.IEnumerable>, the code example could have used the array's enumeration methods (<xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A>, and <xref:System.Collections.IEnumerator.Current%2A>) instead of defining them in the `Tokens` class.</span></span> <span data-ttu-id="e8144-113">Die Methodendefinitionen sind im Beispiel enthalten, um zu verdeutlichen, wie sie definiert sind und was jede Definition tut.</span><span class="sxs-lookup"><span data-stu-id="e8144-113">The method definitions are included in the example to clarify how they are defined and what each does.</span></span>  
  
 [!code-csharp[csProgGuideCollections#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_2.cs)]  
  
 <span data-ttu-id="e8144-114">In C# muss eine Auflistungsklasse nicht <xref:System.Collections.IEnumerable> und <xref:System.Collections.IEnumerator> implementieren, um mit `foreach` kompatibel zu sein.</span><span class="sxs-lookup"><span data-stu-id="e8144-114">In C#, it is not necessary for a collection class to implement <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> to be compatible with `foreach`.</span></span> <span data-ttu-id="e8144-115">Wenn die Klasse über die erforderlichen Elemente <xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A> und <xref:System.Collections.IEnumerator.Current%2A> verfügt, wird sie mit `foreach` arbeiten.</span><span class="sxs-lookup"><span data-stu-id="e8144-115">If the class has the required <xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A>, and <xref:System.Collections.IEnumerator.Current%2A> members, it will work with `foreach`.</span></span> <span data-ttu-id="e8144-116">Das Auslassen der Schnittstellen hat den Vorteil, dass Sie einen Rückgabetyp für `Current` definieren können, der spezifischer als <xref:System.Object> ist.</span><span class="sxs-lookup"><span data-stu-id="e8144-116">Omitting the interfaces has the advantage of enabling you to define a return type for `Current` that is more specific than <xref:System.Object>.</span></span> <span data-ttu-id="e8144-117">Dadurch wird Typsicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e8144-117">This provides type safety.</span></span>  
  
 <span data-ttu-id="e8144-118">Ändern Sie z.B. die folgenden Zeilen im vorherigen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="e8144-118">For example, change the following lines in the previous example.</span></span>  
  
```csharp  
// Change the Tokens class so that it no longer implements IEnumerable.  
public class Tokens  
{  
    // . . .  
  
    // Change the return type for the GetEnumerator method.  
    public TokenEnumerator GetEnumerator()  
    {   }  
  
    // Change TokenEnumerator so that it no longer implements IEnumerator.  
    public class TokenEnumerator  
    {  
        // . . .  
  
        // Change the return type of method Current to string.  
        public string Current  
        {   }  
    }  
 }  
```  
  
 <span data-ttu-id="e8144-119">Da `Current` eine Zeichenfolge zurückgibt, kann der Compiler erkennen, wenn ein nicht kompatibler Typ in einer `foreach`-Anweisung verwendet wird, so wie in folgendem Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e8144-119">Because `Current` returns a string, the compiler can detect when an incompatible type is used in a `foreach` statement, as shown in the following code.</span></span>  
  
```csharp  
// Error: Cannot convert type string to int.  
foreach (int item in f)    
```  
  
 <span data-ttu-id="e8144-120">Wenn <xref:System.Collections.IEnumerator> und `foreach` ausgelassen werden, besteht der Nachteil darin, dass die Auflistungsklasse nicht länger mit den <xref:System.Collections.IEnumerable>-Anweisungen oder entsprechenden Anweisungen anderer Common Language Runtime-Sprachen interoperabel ist.</span><span class="sxs-lookup"><span data-stu-id="e8144-120">The disadvantage of omitting <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> is that the collection class is no longer interoperable with the `foreach` statements, or equivalent statements, of other common language runtime languages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8144-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8144-121">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="e8144-122">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="e8144-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e8144-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e8144-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e8144-124">Arrays</span><span class="sxs-lookup"><span data-stu-id="e8144-124">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="e8144-125">Sammlungen</span><span class="sxs-lookup"><span data-stu-id="e8144-125">Collections</span></span>](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)
