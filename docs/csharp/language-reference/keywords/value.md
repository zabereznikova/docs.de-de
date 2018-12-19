---
title: value – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: f0b9e2927eb288a27f926a740a967742b8cdaa9e
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236465"
---
# <a name="value-c-reference"></a><span data-ttu-id="9e59c-102">value (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="9e59c-102">value (C# Reference)</span></span>
<span data-ttu-id="9e59c-103">Das kontextabhängige Schlüsselwort `value` wird im Set-Accessor in normalen Eigenschaftendeklarationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="9e59c-103">The contextual keyword `value` is used in the set accessor in ordinary property declarations.</span></span> <span data-ttu-id="9e59c-104">Es ähnelt einem Eingabeparameter einer Methode.</span><span class="sxs-lookup"><span data-stu-id="9e59c-104">It is similar to an input parameter on a method.</span></span> <span data-ttu-id="9e59c-105">Das Wort `value` verweist auf den Wert, den Clientcode der Eigenschaft zuweisen möchte.</span><span class="sxs-lookup"><span data-stu-id="9e59c-105">The word `value` references the value that client code is attempting to assign to the property.</span></span> <span data-ttu-id="9e59c-106">Im folgenden Beispiel verfügt `MyDerivedClass` über eine Eigenschaft mit dem Namen `Name`, die den Parameter `value` verwendet, um dem Unterstützungsfeld `name` eine neue Zeichenfolge zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="9e59c-106">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="9e59c-107">Aus Sicht des Clientcodes ist der Vorgang als einfache Zuweisung geschrieben.</span><span class="sxs-lookup"><span data-stu-id="9e59c-107">From the point of view of client code, the operation is written as a simple assignment.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/value_1.cs)]  
  
 <span data-ttu-id="9e59c-108">Weitere Informationen zur Verwendung von `value` finden Sie unter [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="9e59c-108">For more information about the use of `value`, see [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="9e59c-109">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="9e59c-109">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9e59c-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e59c-110">See Also</span></span>

- [<span data-ttu-id="9e59c-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="9e59c-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="9e59c-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9e59c-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="9e59c-113">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="9e59c-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
