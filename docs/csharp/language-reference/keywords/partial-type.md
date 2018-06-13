---
title: partial (Typ) (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
ms.openlocfilehash: 4f57149dd18deb08aa11b72d0a6d5f71b3838bd1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33266688"
---
# <a name="partial-type-c-reference"></a><span data-ttu-id="ce9aa-102">partial (Typ) (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ce9aa-102">partial (Type) (C# Reference)</span></span>
<span data-ttu-id="ce9aa-103">Partielle Typdefinitionen ermöglichen, dass die Definition einer Klasse, Struktur oder Schnittstelle in mehrere Dateien aufgeteilt wird.</span><span class="sxs-lookup"><span data-stu-id="ce9aa-103">Partial type definitions allow for the definition of a class, struct, or interface to be split into multiple files.</span></span>  
  
 <span data-ttu-id="ce9aa-104">In File1.cs:</span><span class="sxs-lookup"><span data-stu-id="ce9aa-104">In File1.cs:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_1.cs)]  
  
 <span data-ttu-id="ce9aa-105">Die Deklaration in File2.cs:</span><span class="sxs-lookup"><span data-stu-id="ce9aa-105">In File2.cs the declaration:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_2.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="ce9aa-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ce9aa-106">Remarks</span></span>  
 <span data-ttu-id="ce9aa-107">Das Aufteilen eines Klassen-, Struktur- oder Schnittstellentyps auf mehrere Dateien kann nützlich sein, wenn Sie mit großen Projekten oder mit automatisch erzeugten Codes arbeiten, wie z.B. denjenigen, die vom [Windows Forms-Designer](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md) bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ce9aa-107">Splitting a class, struct or interface type over several files can be useful when you are working with large projects, or with automatically generated code such as that provided by the [Windows Forms Designer](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span></span> <span data-ttu-id="ce9aa-108">Ein partieller Typ kann eine [partielle Methode](../../../csharp/language-reference/keywords/partial-method.md) enthalten.</span><span class="sxs-lookup"><span data-stu-id="ce9aa-108">A partial type may contain a [partial method](../../../csharp/language-reference/keywords/partial-method.md).</span></span> <span data-ttu-id="ce9aa-109">Weitere Informationen finden Sie unter [Partielle Klassen und Methoden](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="ce9aa-109">For more information, see [Partial Classes and Methods](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="ce9aa-110">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="ce9aa-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ce9aa-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce9aa-111">See Also</span></span>  
 [<span data-ttu-id="ce9aa-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ce9aa-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ce9aa-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ce9aa-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ce9aa-114">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="ce9aa-114">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="ce9aa-115">Einführung in Generika</span><span class="sxs-lookup"><span data-stu-id="ce9aa-115">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)
