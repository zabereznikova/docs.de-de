---
title: readonly (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: d2f8a2f192dc319ad806aeef4bfbaeecc44b07a3
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2018
---
# <a name="readonly-c-reference"></a><span data-ttu-id="7233a-102">readonly (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="7233a-102">readonly (C# Reference)</span></span>
<span data-ttu-id="7233a-103">Das Schlüsselwort `readonly` ist ein Modifizierer, den Sie für Felder verwenden können.</span><span class="sxs-lookup"><span data-stu-id="7233a-103">The `readonly` keyword is a modifier that you can use on fields.</span></span> <span data-ttu-id="7233a-104">Wenn eine Felddeklaration einen `readonly`-Modifizierer enthält, können Zuweisungen an die Felder, die von der Deklaration eingeführt wurden, nur als Teil der Deklaration oder in einem Konstruktor in derselben Klasse auftreten.</span><span class="sxs-lookup"><span data-stu-id="7233a-104">When a field declaration includes a `readonly` modifier, assignments to the fields introduced by the declaration can only occur as part of the declaration or in a constructor in the same class.</span></span>  
  
## <a name="readonly-field-example"></a><span data-ttu-id="7233a-105">Beispiel für ein readonly-Feld</span><span class="sxs-lookup"><span data-stu-id="7233a-105">Readonly field example</span></span>  
 <span data-ttu-id="7233a-106">In diesem Beispiel kann der Wert des Felds `year` nicht zur Methode `ChangeYear` geändert werden, obwohl ihm im Klassenkonstruktor ein Wert zugewiesen ist:</span><span class="sxs-lookup"><span data-stu-id="7233a-106">In this example, the value of the field `year` cannot be changed in the method `ChangeYear`, even though it is assigned a value in the class constructor:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]  
  
 <span data-ttu-id="7233a-107">Sie können einem `readonly`-Feld nur in den folgenden Kontexten einen Wert zuweisen:</span><span class="sxs-lookup"><span data-stu-id="7233a-107">You can assign a value to a `readonly` field only in the following contexts:</span></span>  
  
-   <span data-ttu-id="7233a-108">Wenn die Variable in der Deklaration initialisiert ist, z.B.:</span><span class="sxs-lookup"><span data-stu-id="7233a-108">When the variable is initialized in the declaration, for example:</span></span>  
  
    ```csharp  
    public readonly int y = 5;  
    ```  
  
-   <span data-ttu-id="7233a-109">Für ein Instanzenfeld, in den Instanzkonstruktoren der Klasse, die die Felddeklaration enthält oder für ein statisches Feld im statischen Konstruktor der Klasse, die die Felddeklaration enthält.</span><span class="sxs-lookup"><span data-stu-id="7233a-109">For an instance field, in the instance constructors of the class that contains the field declaration, or for a static field, in the static constructor of the class that contains the field declaration.</span></span> <span data-ttu-id="7233a-110">Hierbei handelt es sich auch um die einzigen Kontexte, in denen es gültig ist, ein `readonly`-Feld als [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) oder [ref](../../../csharp/language-reference/keywords/ref.md)-Parameter zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="7233a-110">These are also the only contexts in which it is valid to pass a `readonly` field as an [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) or [ref](../../../csharp/language-reference/keywords/ref.md) parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7233a-111">Das Schlüsselwort `readonly` unterscheidet sich vom Schlüsselwort [const](../../../csharp/language-reference/keywords/const.md).</span><span class="sxs-lookup"><span data-stu-id="7233a-111">The `readonly` keyword is different from the [const](../../../csharp/language-reference/keywords/const.md) keyword.</span></span> <span data-ttu-id="7233a-112">Ein `const`-Feld kann nur bei der Deklaration des Felds initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="7233a-112">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="7233a-113">Ein `readonly`-Feld kann entweder bei der Deklaration oder in einem Konstruktor initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="7233a-113">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="7233a-114">Daher können `readonly`-Felder abhängig vom verwendeten Konstruktor über unterschiedliche Werte verfügen.</span><span class="sxs-lookup"><span data-stu-id="7233a-114">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="7233a-115">Außerdem ist ein `const`-Feld eine Kompilierzeitkonstante, während ein `readonly`-Feld wie im folgenden Beispiel für Laufzeitkonstanten verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="7233a-115">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>  
  
```csharp  
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```  
  
## <a name="comparing-readonly-and-non-readonly-instance-fields"></a><span data-ttu-id="7233a-116">Vergleich von readonly-Instanzfeldern und Instanzfeldern, für die readonly nicht gilt</span><span class="sxs-lookup"><span data-stu-id="7233a-116">Comparing readonly and non-readonly instance fields</span></span>  
 [!code-csharp[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]  
  
 <span data-ttu-id="7233a-117">Im vorherigen Beispiel, wenn Sie eine Anweisung wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="7233a-117">In the preceding example, if you use a statement like this:</span></span>  
  
 `p2.y = 66;        // Error`  
  
 <span data-ttu-id="7233a-118">erhalten Sie die Compilerfehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="7233a-118">you will get the compiler error message:</span></span>  
  
 `The left-hand side of an assignment must be an l-value`  
  
 <span data-ttu-id="7233a-119">Es handelt sich um den gleichen Fehler, den Sie erhalten, wenn Sie versuchen, einen Wert einer Konstanten zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="7233a-119">which is the same error you get when you attempt to assign a value to a constant.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="7233a-120">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="7233a-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7233a-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7233a-121">See Also</span></span>  
 [<span data-ttu-id="7233a-122">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="7233a-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="7233a-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="7233a-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7233a-124">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="7233a-124">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="7233a-125">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="7233a-125">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="7233a-126">const</span><span class="sxs-lookup"><span data-stu-id="7233a-126">const</span></span>](../../../csharp/language-reference/keywords/const.md)  
 [<span data-ttu-id="7233a-127">Felder</span><span class="sxs-lookup"><span data-stu-id="7233a-127">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)
