---
title: 'Gewusst wie: Sichere Umwandlung von bool? in bool (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- casting [C#], nullable types
- nullable types [C#], casting bool? to bool
ms.assetid: e06e4274-a443-422d-8ef1-9dbf9df55237
caps.latest.revision: 9
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
ms.openlocfilehash: c8a3dc3280b7dca802b327d9454c7f0ba9ed44be
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-safely-cast-from-bool-to-bool-c-programming-guide"></a><span data-ttu-id="1c259-102">Gewusst wie: Sichere Umwandlung von bool? in bool (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="1c259-102">How to: Safely Cast from bool? to bool (C# Programming Guide)</span></span>
<span data-ttu-id="1c259-103">Der `bool?`-Typ, der NULL-Werte zulässt, kann drei verschiedene Werte enthalten: `true`, `false` und `null`.</span><span class="sxs-lookup"><span data-stu-id="1c259-103">The `bool?` nullable type can contain three different values: `true`, `false`, and `null`.</span></span> <span data-ttu-id="1c259-104">Aus diesem Grund kann der `bool?`-Typ nicht in Bedingungen mit `if`, `for` oder `while` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1c259-104">Therefore, the `bool?` type cannot be used in conditionals such as with `if`, `for`, or `while`.</span></span> <span data-ttu-id="1c259-105">Beispielsweise verursacht der folgende Code einen Compilerfehler:</span><span class="sxs-lookup"><span data-stu-id="1c259-105">For example, the following code causes a compiler error.</span></span>  
  
```  
bool? b = null;  
if (b) // Error CS0266.  
{  
}  
```  
  
 <span data-ttu-id="1c259-106">Dies ist nicht zulässig, da unklar ist, was `null` im Kontext eines bedingten Ausdrucks bedeutet.</span><span class="sxs-lookup"><span data-stu-id="1c259-106">This is not allowed because it is unclear what `null` means in the context of a conditional.</span></span> <span data-ttu-id="1c259-107">Wenn Sie `bool?` in einer bedingten Anweisung verwenden möchten, überprüfen Sie zunächst die <xref:System.Nullable%601.HasValue%2A>-Eigenschaft, um sicherzustellen, dass der Wert nicht `null` ist, und wandeln Sie den Typ dann in `bool` um.</span><span class="sxs-lookup"><span data-stu-id="1c259-107">To use a `bool?` in a conditional statement, first check its <xref:System.Nullable%601.HasValue%2A> property to ensure that its value is not `null`, and then cast it to `bool`.</span></span> <span data-ttu-id="1c259-108">Weitere Informationen finden Sie unter [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="1c259-108">For more information, see [bool](../../../csharp/language-reference/keywords/bool.md).</span></span> <span data-ttu-id="1c259-109">Wenn Sie die Umwandlung für einen `bool?`-Typ mit dem Wert `null` durchführen, wird bei der Prüfung eine <xref:System.InvalidOperationException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1c259-109">If you perform the cast on a `bool?` with a value of `null`, a <xref:System.InvalidOperationException> will be thrown in the conditional test.</span></span> <span data-ttu-id="1c259-110">Das folgende Beispiel zeigt eine Möglichkeit, `bool?` sicher in `bool` umzuwandeln:</span><span class="sxs-lookup"><span data-stu-id="1c259-110">The following example shows one way to safely cast from `bool?` to `bool`:</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c259-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1c259-111">Example</span></span>  
  
```csharp  
bool? test = null;  
// Other code that may or may not  
// give a value to test.  
if(!test.HasValue) //check for a value  
{  
    // Assume that IsInitialized  
    // returns either true or false.  
    test = IsInitialized();  
}  
if((bool)test) //now this cast is safe  
{  
   // Do something.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="1c259-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c259-112">See Also</span></span>  
 <span data-ttu-id="1c259-113">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1c259-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1c259-114">[Literalschlüsselwörter](../../../csharp/language-reference/keywords/literal-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="1c259-114">[Literal Keywords](../../../csharp/language-reference/keywords/literal-keywords.md) </span></span>  
 <span data-ttu-id="1c259-115">[Typen, die NULL-Werte zulassen](../../../csharp/programming-guide/nullable-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="1c259-115">[Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) </span></span>  
 [<span data-ttu-id="1c259-116">?? Operator</span><span class="sxs-lookup"><span data-stu-id="1c259-116">?? Operator</span></span>](../../../csharp/language-reference/operators/null-conditional-operator.md)

