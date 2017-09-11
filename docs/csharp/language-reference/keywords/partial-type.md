---
title: partial (Typ) (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
caps.latest.revision: 24
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
ms.openlocfilehash: 5405455d933f6512cfa3a18e1a545556c5715151
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="partial-type-c-reference"></a><span data-ttu-id="d407d-102">partial (Typ) (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d407d-102">partial (Type) (C# Reference)</span></span>
<span data-ttu-id="d407d-103">Partielle Typdefinitionen ermöglichen, dass die Definition einer Klasse, Struktur oder Schnittstelle in mehrere Dateien aufgeteilt wird.</span><span class="sxs-lookup"><span data-stu-id="d407d-103">Partial type definitions allow for the definition of a class, struct, or interface to be split into multiple files.</span></span>  
  
 <span data-ttu-id="d407d-104">In File1.cs:</span><span class="sxs-lookup"><span data-stu-id="d407d-104">In File1.cs:</span></span>  
  
 <span data-ttu-id="d407d-105">[!code-cs[csrefKeywordsContextual#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d407d-105">[!code-cs[csrefKeywordsContextual#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_1.cs)]</span></span>  
  
 <span data-ttu-id="d407d-106">Die Deklaration in File2.cs:</span><span class="sxs-lookup"><span data-stu-id="d407d-106">In File2.cs the declaration:</span></span>  
  
 <span data-ttu-id="d407d-107">[!code-cs[csrefKeywordsContextual#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d407d-107">[!code-cs[csrefKeywordsContextual#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_2.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d407d-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d407d-108">Remarks</span></span>  
 <span data-ttu-id="d407d-109">Das Aufteilen eines Klassen-, Struktur- oder Schnittstellentyps auf mehrere Dateien kann nützlich sein, wenn Sie mit großen Projekten oder mit automatisch erzeugten Codes arbeiten, wie z.B. denjenigen, die vom [Windows Forms-Designer](http://msdn.microsoft.com/en-us/3c3d61f8-f36c-4d41-b9c3-398376fabb15) bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d407d-109">Splitting a class, struct or interface type over several files can be useful when you are working with large projects, or with automatically generated code such as that provided by the [Windows Forms Designer](http://msdn.microsoft.com/en-us/3c3d61f8-f36c-4d41-b9c3-398376fabb15).</span></span> <span data-ttu-id="d407d-110">Ein partieller Typ kann eine [partielle Methode](../../../csharp/language-reference/keywords/partial-method.md) enthalten.</span><span class="sxs-lookup"><span data-stu-id="d407d-110">A partial type may contain a [partial method](../../../csharp/language-reference/keywords/partial-method.md).</span></span> <span data-ttu-id="d407d-111">Weitere Informationen finden Sie unter [Partielle Klassen und Methoden](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="d407d-111">For more information, see [Partial Classes and Methods](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d407d-112">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="d407d-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d407d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d407d-113">See Also</span></span>  
 <span data-ttu-id="d407d-114">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d407d-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d407d-115">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d407d-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d407d-116">[Modifizierer](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="d407d-116">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 [<span data-ttu-id="d407d-117">Einführung in Generika</span><span class="sxs-lookup"><span data-stu-id="d407d-117">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)

