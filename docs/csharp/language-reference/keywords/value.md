---
title: value (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- value_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
caps.latest.revision: 14
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
ms.openlocfilehash: 012cf622091687996fec477a8b5b821b190bbc29
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="value-c-reference"></a><span data-ttu-id="0ef41-102">value (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="0ef41-102">value (C# Reference)</span></span>
<span data-ttu-id="0ef41-103">Das kontextabhängige Schlüsselwort `value` wird im Set-Accessor in normalen Eigenschaftendeklarationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="0ef41-103">The contextual keyword `value` is used in the set accessor in ordinary property declarations.</span></span> <span data-ttu-id="0ef41-104">Es ähnelt einem Eingabeparameter einer Methode.</span><span class="sxs-lookup"><span data-stu-id="0ef41-104">It is similar to an input parameter on a method.</span></span> <span data-ttu-id="0ef41-105">Das Wort `value` verweist auf den Wert, den Clientcode der Eigenschaft zuweisen möchte.</span><span class="sxs-lookup"><span data-stu-id="0ef41-105">The word `value` references the value that client code is attempting to assign to the property.</span></span> <span data-ttu-id="0ef41-106">Im folgenden Beispiel verfügt `MyDerivedClass` über eine Eigenschaft mit dem Namen `Name`, die den Parameter `value` verwendet, um dem Unterstützungsfeld `name` eine neue Zeichenfolge zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="0ef41-106">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="0ef41-107">Aus Sicht des Clientcodes ist der Vorgang als einfache Zuweisung geschrieben.</span><span class="sxs-lookup"><span data-stu-id="0ef41-107">From the point of view of client code, the operation is written as a simple assignment.</span></span>  
  
 <span data-ttu-id="0ef41-108">[!code-cs[CsrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/value_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0ef41-108">[!code-cs[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/value_1.cs)]</span></span>  
  
 <span data-ttu-id="0ef41-109">Weitere Informationen zur Verwendung von `value` finden Sie unter [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="0ef41-109">For more information about the use of `value`, see [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="0ef41-110">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="0ef41-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0ef41-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ef41-111">See Also</span></span>  
 <span data-ttu-id="0ef41-112">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="0ef41-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="0ef41-113">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0ef41-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="0ef41-114">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="0ef41-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)

