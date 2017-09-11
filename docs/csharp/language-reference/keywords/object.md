---
title: object (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- object_CSharpKeyword
- object
dev_langs:
- CSharp
helpviewer_keywords:
- object keyword [C#]
ms.assetid: 93f60c0b-e17a-40a9-9362-cca5fb77b0e7
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
ms.openlocfilehash: 744debc51f68cc52f03bce09c9f276a66ae085e1
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="object-c-reference"></a><span data-ttu-id="283b5-102">object (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="283b5-102">object (C# Reference)</span></span>
<span data-ttu-id="283b5-103">Der `object`-Typ ist ein Alias für <xref:System.Object> in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="283b5-103">The `object` type is an alias for <xref:System.Object> in the .NET Framework.</span></span> <span data-ttu-id="283b5-104">Im vereinheitlichen Typsystem von C# erben alle Typen, vordefiniert und benutzerdefiniert sowie Verweis- und Werttypen, direkt oder indirekt von <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="283b5-104">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span> <span data-ttu-id="283b5-105">Sie können Werte eines beliebigen Typs Variablen des Typs `object` zuweisen.</span><span class="sxs-lookup"><span data-stu-id="283b5-105">You can assign values of any type to variables of type `object`.</span></span> <span data-ttu-id="283b5-106">Wenn eine Variable eines Werttyps in ein Objekt konvertiert wird, gilt es als *geschachtelt*.</span><span class="sxs-lookup"><span data-stu-id="283b5-106">When a variable of a value type is converted to object, it is said to be *boxed*.</span></span> <span data-ttu-id="283b5-107">Wenn eine Variable eines Typobjekts in ein Wertobjekt konvertiert wird, gilt es als *nicht geschachtelt*.</span><span class="sxs-lookup"><span data-stu-id="283b5-107">When a variable of type object is converted to a value type, it is said to be *unboxed*.</span></span> <span data-ttu-id="283b5-108">Weitere Informationen finden Sie unter [Boxing und Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span><span class="sxs-lookup"><span data-stu-id="283b5-108">For more information, see [Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="283b5-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="283b5-109">Example</span></span>  
 <span data-ttu-id="283b5-110">Im folgenden Beispiel wird gezeigt, wie Variablen des `object`-Typs Werte von jedem Datentyp akzeptieren können und Variablen des `object`-Typs Methoden auf <xref:System.Object> von .NET Framework verwenden können.</span><span class="sxs-lookup"><span data-stu-id="283b5-110">The following sample shows how variables of type `object` can accept values of any data type and how variables of type `object` can use methods on <xref:System.Object> from the .NET Framework.</span></span>  
  
 <span data-ttu-id="283b5-111">[!code-cs[csrefKeywordsTypes#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/object_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="283b5-111">[!code-cs[csrefKeywordsTypes#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/object_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="283b5-112">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="283b5-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="283b5-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="283b5-113">See Also</span></span>  
 <span data-ttu-id="283b5-114">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="283b5-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="283b5-115">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="283b5-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="283b5-116">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="283b5-116">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="283b5-117">[Verweistypen](../../../csharp/language-reference/keywords/reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="283b5-117">[Reference Types](../../../csharp/language-reference/keywords/reference-types.md) </span></span>  
 [<span data-ttu-id="283b5-118">Werttypen</span><span class="sxs-lookup"><span data-stu-id="283b5-118">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)

