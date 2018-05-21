---
title: 'Gewusst wie: Sichere Umwandlung von bool? in bool (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- casting [C#], nullable types
- nullable types [C#], casting bool? to bool
ms.assetid: e06e4274-a443-422d-8ef1-9dbf9df55237
ms.openlocfilehash: 18f44018621182427199dee56146f29b8d3068f4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-safely-cast-from-bool-to-bool-c-programming-guide"></a><span data-ttu-id="ebda9-102">Gewusst wie: Sichere Umwandlung von bool? in bool (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ebda9-102">How to: Safely Cast from bool? to bool (C# Programming Guide)</span></span>
<span data-ttu-id="ebda9-103">Der `bool?`-Typ, der NULL-Werte zulässt, kann drei verschiedene Werte enthalten: `true`, `false` und `null`.</span><span class="sxs-lookup"><span data-stu-id="ebda9-103">The `bool?` nullable type can contain three different values: `true`, `false`, and `null`.</span></span> <span data-ttu-id="ebda9-104">Aus diesem Grund kann der `bool?`-Typ nicht in Bedingungen mit `if`, `for` oder `while` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ebda9-104">Therefore, the `bool?` type cannot be used in conditionals such as with `if`, `for`, or `while`.</span></span> <span data-ttu-id="ebda9-105">Beispielsweise verursacht der folgende Code einen Compilerfehler:</span><span class="sxs-lookup"><span data-stu-id="ebda9-105">For example, the following code causes a compiler error.</span></span>  
  
```  
bool? b = null;  
if (b) // Error CS0266.  
{  
}  
```  
  
 <span data-ttu-id="ebda9-106">Dies ist nicht zulässig, da unklar ist, was `null` im Kontext eines bedingten Ausdrucks bedeutet.</span><span class="sxs-lookup"><span data-stu-id="ebda9-106">This is not allowed because it is unclear what `null` means in the context of a conditional.</span></span> <span data-ttu-id="ebda9-107">Wenn Sie `bool?` in einer bedingten Anweisung verwenden möchten, überprüfen Sie zunächst die <xref:System.Nullable%601.HasValue%2A>-Eigenschaft, um sicherzustellen, dass der Wert nicht `null` ist, und wandeln Sie den Typ dann in `bool` um.</span><span class="sxs-lookup"><span data-stu-id="ebda9-107">To use a `bool?` in a conditional statement, first check its <xref:System.Nullable%601.HasValue%2A> property to ensure that its value is not `null`, and then cast it to `bool`.</span></span> <span data-ttu-id="ebda9-108">Weitere Informationen finden Sie unter [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="ebda9-108">For more information, see [bool](../../../csharp/language-reference/keywords/bool.md).</span></span> <span data-ttu-id="ebda9-109">Wenn Sie die Umwandlung für einen `bool?`-Typ mit dem Wert `null` durchführen, wird bei der Prüfung eine <xref:System.InvalidOperationException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="ebda9-109">If you perform the cast on a `bool?` with a value of `null`, a <xref:System.InvalidOperationException> will be thrown in the conditional test.</span></span> <span data-ttu-id="ebda9-110">Das folgende Beispiel zeigt eine Möglichkeit, `bool?` sicher in `bool` umzuwandeln:</span><span class="sxs-lookup"><span data-stu-id="ebda9-110">The following example shows one way to safely cast from `bool?` to `bool`:</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebda9-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ebda9-111">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ebda9-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebda9-112">See Also</span></span>  
 [<span data-ttu-id="ebda9-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ebda9-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ebda9-114">Literalschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ebda9-114">Literal Keywords</span></span>](../../../csharp/language-reference/keywords/literal-keywords.md)  
 [<span data-ttu-id="ebda9-115">Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="ebda9-115">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="ebda9-116">?? Operator</span><span class="sxs-lookup"><span data-stu-id="ebda9-116">?? Operator</span></span>](../../../csharp/language-reference/operators/null-conditional-operator.md)
