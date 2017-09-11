---
title: readonly (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- readonly_CSharpKeyword
- readonly
dev_langs:
- CSharp
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
caps.latest.revision: 16
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
ms.openlocfilehash: 2660aa56721815cbbeb668328863956473cce8f1
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="readonly-c-reference"></a><span data-ttu-id="1cf34-102">readonly (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="1cf34-102">readonly (C# Reference)</span></span>
<span data-ttu-id="1cf34-103">Das Schlüsselwort `readonly` ist ein Modifizierer, den Sie für Felder verwenden können.</span><span class="sxs-lookup"><span data-stu-id="1cf34-103">The `readonly` keyword is a modifier that you can use on fields.</span></span> <span data-ttu-id="1cf34-104">Wenn eine Felddeklaration einen `readonly`-Modifizierer enthält, können Zuweisungen an die Felder, die von der Deklaration eingeführt wurden, nur als Teil der Deklaration oder in einem Konstruktor in derselben Klasse auftreten.</span><span class="sxs-lookup"><span data-stu-id="1cf34-104">When a field declaration includes a `readonly` modifier, assignments to the fields introduced by the declaration can only occur as part of the declaration or in a constructor in the same class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1cf34-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1cf34-105">Example</span></span>  
 <span data-ttu-id="1cf34-106">In diesem Beispiel kann der Wert des Felds `year` nicht zur Methode `ChangeYear` geändert werden, obwohl ihm im Klassenkonstruktor ein Wert zugewiesen ist:</span><span class="sxs-lookup"><span data-stu-id="1cf34-106">In this example, the value of the field `year` cannot be changed in the method `ChangeYear`, even though it is assigned a value in the class constructor:</span></span>  
  
 <span data-ttu-id="1cf34-107">[!code-cs[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1cf34-107">[!code-cs[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]</span></span>  
  
 <span data-ttu-id="1cf34-108">Sie können einem `readonly`-Feld nur in den folgenden Kontexten einen Wert zuweisen:</span><span class="sxs-lookup"><span data-stu-id="1cf34-108">You can assign a value to a `readonly` field only in the following contexts:</span></span>  
  
-   <span data-ttu-id="1cf34-109">Wenn die Variable in der Deklaration initialisiert ist, z.B.:</span><span class="sxs-lookup"><span data-stu-id="1cf34-109">When the variable is initialized in the declaration, for example:</span></span>  
  
    ```  
    public readonly int y = 5;  
    ```  
  
-   <span data-ttu-id="1cf34-110">Für ein Instanzenfeld, in den Instanzkonstruktoren der Klasse, die die Felddeklaration enthält oder für ein statisches Feld im statischen Konstruktor der Klasse, die die Felddeklaration enthält.</span><span class="sxs-lookup"><span data-stu-id="1cf34-110">For an instance field, in the instance constructors of the class that contains the field declaration, or for a static field, in the static constructor of the class that contains the field declaration.</span></span> <span data-ttu-id="1cf34-111">Hierbei handelt es sich auch um die einzigen Kontexte, in denen es gültig ist, ein `readonly`-Feld als [out](../../../csharp/language-reference/keywords/out.md) oder [ref](../../../csharp/language-reference/keywords/ref.md)-Parameter zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="1cf34-111">These are also the only contexts in which it is valid to pass a `readonly` field as an [out](../../../csharp/language-reference/keywords/out.md) or [ref](../../../csharp/language-reference/keywords/ref.md) parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1cf34-112">Das Schlüsselwort `readonly` unterscheidet sich vom Schlüsselwort [const](../../../csharp/language-reference/keywords/const.md).</span><span class="sxs-lookup"><span data-stu-id="1cf34-112">The `readonly` keyword is different from the [const](../../../csharp/language-reference/keywords/const.md) keyword.</span></span> <span data-ttu-id="1cf34-113">Ein `const`-Feld kann nur bei der Deklaration des Felds initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="1cf34-113">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="1cf34-114">Ein `readonly`-Feld kann entweder bei der Deklaration oder in einem Konstruktor initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="1cf34-114">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="1cf34-115">Daher können `readonly`-Felder abhängig vom verwendeten Konstruktor über unterschiedliche Werte verfügen.</span><span class="sxs-lookup"><span data-stu-id="1cf34-115">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="1cf34-116">Außerdem ist ein `const`-Feld eine Kompilierzeitkonstante, während ein `readonly`-Feld wie im folgenden Beispiel für Laufzeitkonstanten verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="1cf34-116">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>  
  
```  
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```  
  
## <a name="example"></a><span data-ttu-id="1cf34-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1cf34-117">Example</span></span>  
 <span data-ttu-id="1cf34-118">[!code-cs[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="1cf34-118">[!code-cs[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]</span></span>  
  
 <span data-ttu-id="1cf34-119">Im vorherigen Beispiel, wenn Sie eine Anweisung wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="1cf34-119">In the preceding example, if you use a statement like this:</span></span>  
  
 `p2.y = 66;        // Error`  
  
 <span data-ttu-id="1cf34-120">erhalten Sie die Compilerfehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="1cf34-120">you will get the compiler error message:</span></span>  
  
 `The left-hand side of an assignment must be an l-value`  
  
 <span data-ttu-id="1cf34-121">Es handelt sich um den gleichen Fehler, den Sie erhalten, wenn Sie versuchen, einen Wert einer Konstanten zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="1cf34-121">which is the same error you get when you attempt to assign a value to a constant.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="1cf34-122">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="1cf34-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1cf34-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1cf34-123">See Also</span></span>  
 <span data-ttu-id="1cf34-124">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="1cf34-124">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="1cf34-125">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1cf34-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1cf34-126">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="1cf34-126">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="1cf34-127">[Modifizierer](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="1cf34-127">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="1cf34-128">[const](../../../csharp/language-reference/keywords/const.md) </span><span class="sxs-lookup"><span data-stu-id="1cf34-128">[const](../../../csharp/language-reference/keywords/const.md) </span></span>  
 [<span data-ttu-id="1cf34-129">Felder</span><span class="sxs-lookup"><span data-stu-id="1cf34-129">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)

