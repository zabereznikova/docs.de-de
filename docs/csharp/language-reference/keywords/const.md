---
title: const (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- const_CSharpKeyword
- const
dev_langs:
- CSharp
helpviewer_keywords:
- const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
caps.latest.revision: 28
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
ms.openlocfilehash: b8f6d567deed513ff5693fe39bd21c8607677402
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="const-c-reference"></a><span data-ttu-id="5ab3c-102">const (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="5ab3c-102">const (C# Reference)</span></span>
<span data-ttu-id="5ab3c-103">Sie verwenden das `const`-Schlüsselwort, um ein konstantes Feld oder eine konstante lokale Variable zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="5ab3c-103">You use the `const` keyword to declare a constant field or a constant local.</span></span> <span data-ttu-id="5ab3c-104">Konstante Felder und lokale Felder sind keine Variablen und können daher nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="5ab3c-104">Constant fields and locals aren't variables and may not be modified.</span></span> <span data-ttu-id="5ab3c-105">Konstanten können Nummern, boolesche Werte, Zeichenfolgen oder ein NULL-Verweis sein.</span><span class="sxs-lookup"><span data-stu-id="5ab3c-105">Constants can be numbers, Boolean values, strings, or a null reference.</span></span> <span data-ttu-id="5ab3c-106">Erstellen Sie keine Konstante, um Informationen darzustellen, von denen Sie ausgehen, dass sie sich einmal ändern.</span><span class="sxs-lookup"><span data-stu-id="5ab3c-106">Don’t create a constant to represent information that you expect to change at any time.</span></span> <span data-ttu-id="5ab3c-107">Verwenden Sie beispielsweise kein konstantes Feld, um den Preis einer Dienstleistung, einer Produktversionsnummer oder den Markennamen eines Unternehmens zu speichern.</span><span class="sxs-lookup"><span data-stu-id="5ab3c-107">For example, don’t use a constant field to store the price of a service, a product version number, or the brand name of a company.</span></span> <span data-ttu-id="5ab3c-108">Diese Werte können sich im Laufe der Zeit ändern, und da Compiler Konstanten weitergeben, muss anderer Code, der mit Ihren Bibliotheken kompiliert wird, neu kompiliert werden, damit die Änderungen sichtbar werden.</span><span class="sxs-lookup"><span data-stu-id="5ab3c-108">These values can change over time, and because compilers propagate constants, other code compiled with your libraries will have to be recompiled to see the changes.</span></span> <span data-ttu-id="5ab3c-109">Weitere Informationen finden Sie auch unter dem [readonly](../../../csharp/language-reference/keywords/readonly.md)-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="5ab3c-109">See also the [readonly](../../../csharp/language-reference/keywords/readonly.md) keyword.</span></span> <span data-ttu-id="5ab3c-110">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5ab3c-110">For example:</span></span>  
  
```csharp
const int x = 0;  
public const double gravitationalConstant = 6.673e-11;  
private const string productName = "Visual C#";  
```  
  
## <a name="remarks"></a><span data-ttu-id="5ab3c-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5ab3c-111">Remarks</span></span>  
 <span data-ttu-id="5ab3c-112">Der Typ einer Konstantendeklaration gibt den Typ der Member an, die durch die Deklaration eingeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5ab3c-112">The type of a constant declaration specifies the type of the members that the declaration introduces.</span></span> <span data-ttu-id="5ab3c-113">Der Initialisierer einer konstanten lokalen Variable oder eines konstanten Felds muss ein konstanter Ausdruck sein, der implizit in den Zieltyp konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5ab3c-113">The initializer of a constant local or a constant field must be a constant expression that can be implicitly converted to the target type.</span></span>  
  
 <span data-ttu-id="5ab3c-114">Ein konstanter Ausdruck ist ein Ausdruck, der während der Kompilierung vollständig ausgewertet werden kann.</span><span class="sxs-lookup"><span data-stu-id="5ab3c-114">A constant expression is an expression that can be fully evaluated at compile time.</span></span> <span data-ttu-id="5ab3c-115">Daher sind `string` und ein NULL-Verweis die einzig möglichen Werte für Verweistypkonstanten.</span><span class="sxs-lookup"><span data-stu-id="5ab3c-115">Therefore, the only possible values for constants of reference types are `string` and a null reference.</span></span>  
  
 <span data-ttu-id="5ab3c-116">In der Konstantendeklaration können mehrere Konstanten deklariert werden, z. B.:</span><span class="sxs-lookup"><span data-stu-id="5ab3c-116">The constant declaration can declare multiple constants, such as:</span></span>  
  
```csharp
public const double x = 1.0, y = 2.0, z = 3.0;  
```  
  
 <span data-ttu-id="5ab3c-117">Der `static`-Modifizierer ist in einer Konstantendeklaration nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="5ab3c-117">The `static` modifier is not allowed in a constant declaration.</span></span>  
  
 <span data-ttu-id="5ab3c-118">Eine Konstante kann wie folgt einen Teil eines konstanten Ausdrucks darstellen:</span><span class="sxs-lookup"><span data-stu-id="5ab3c-118">A constant can participate in a constant expression, as follows:</span></span>  
  
```csharp
public const int c1 = 5;  
public const int c2 = c1 + 100;  
```  
  
> [!NOTE]
>  <span data-ttu-id="5ab3c-119">Das [readonly](../../../csharp/language-reference/keywords/readonly.md)-Schlüsselwort unterscheidet sich vom `const`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="5ab3c-119">The [readonly](../../../csharp/language-reference/keywords/readonly.md) keyword differs from the `const` keyword.</span></span> <span data-ttu-id="5ab3c-120">Ein `const`-Feld kann nur bei der Deklaration des Felds initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="5ab3c-120">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="5ab3c-121">Ein `readonly`-Feld kann entweder bei der Deklaration oder in einem Konstruktor initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="5ab3c-121">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="5ab3c-122">Daher können `readonly`-Felder abhängig vom verwendeten Konstruktor über unterschiedliche Werte verfügen.</span><span class="sxs-lookup"><span data-stu-id="5ab3c-122">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="5ab3c-123">Außerdem ist ein `const`-Feld eine Kompilierzeitkonstante, während ein `readonly`-Feld für Laufzeitkonstanten verwendet werden kann, wie in der folgenden Codezeile: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`.</span><span class="sxs-lookup"><span data-stu-id="5ab3c-123">Also, although a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants, as in this line: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ab3c-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5ab3c-124">Example</span></span>  
 <span data-ttu-id="5ab3c-125">[!code-cs[csrefKeywordsModifiers#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5ab3c-125">[!code-cs[csrefKeywordsModifiers#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ab3c-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5ab3c-126">Example</span></span>  
 <span data-ttu-id="5ab3c-127">In diesem Beispiel wird das Verwenden von Konstanten als lokale Variablen demonstriert.</span><span class="sxs-lookup"><span data-stu-id="5ab3c-127">This example demonstrates how to use constants as local variables.</span></span>  
  
 <span data-ttu-id="5ab3c-128">[!code-cs[csrefKeywordsModifiers#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="5ab3c-128">[!code-cs[csrefKeywordsModifiers#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="5ab3c-129">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="5ab3c-129">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5ab3c-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ab3c-130">See Also</span></span>  
 <span data-ttu-id="5ab3c-131">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="5ab3c-131">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="5ab3c-132">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5ab3c-132">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="5ab3c-133">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="5ab3c-133">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="5ab3c-134">[Modifizierer](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="5ab3c-134">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 [<span data-ttu-id="5ab3c-135">readonly</span><span class="sxs-lookup"><span data-stu-id="5ab3c-135">readonly</span></span>](../../../csharp/language-reference/keywords/readonly.md)

