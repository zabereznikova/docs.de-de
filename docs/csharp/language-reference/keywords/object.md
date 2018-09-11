---
title: object (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- object_CSharpKeyword
- object
helpviewer_keywords:
- object keyword [C#]
ms.assetid: 93f60c0b-e17a-40a9-9362-cca5fb77b0e7
ms.openlocfilehash: b36703828e6027a89297ac88edaf2b55ec18f42e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44191806"
---
# <a name="object-c-reference"></a><span data-ttu-id="f4ad4-102">object (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f4ad4-102">object (C# Reference)</span></span>

<span data-ttu-id="f4ad4-103">Der `object`-Typ ist ein Alias für <xref:System.Object> in .NET.</span><span class="sxs-lookup"><span data-stu-id="f4ad4-103">The `object` type is an alias for <xref:System.Object> in .NET.</span></span> <span data-ttu-id="f4ad4-104">Im vereinheitlichen Typsystem von C# erben alle Typen, vordefiniert und benutzerdefiniert sowie Verweis- und Werttypen, direkt oder indirekt von <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="f4ad4-104">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span> <span data-ttu-id="f4ad4-105">Sie können Werte eines beliebigen Typs Variablen des Typs `object` zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f4ad4-105">You can assign values of any type to variables of type `object`.</span></span> <span data-ttu-id="f4ad4-106">Wenn eine Variable eines Werttyps in ein Objekt konvertiert wird, gilt es als *geschachtelt*.</span><span class="sxs-lookup"><span data-stu-id="f4ad4-106">When a variable of a value type is converted to object, it is said to be *boxed*.</span></span> <span data-ttu-id="f4ad4-107">Wenn eine Variable eines Typobjekts in ein Wertobjekt konvertiert wird, gilt es als *nicht geschachtelt*.</span><span class="sxs-lookup"><span data-stu-id="f4ad4-107">When a variable of type object is converted to a value type, it is said to be *unboxed*.</span></span> <span data-ttu-id="f4ad4-108">Weitere Informationen finden Sie unter [Boxing und Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span><span class="sxs-lookup"><span data-stu-id="f4ad4-108">For more information, see [Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span>

## <a name="example"></a><span data-ttu-id="f4ad4-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f4ad4-109">Example</span></span>

<span data-ttu-id="f4ad4-110">Im folgenden Beispiel wird gezeigt, wie Variablen des `object`-Typs Werte von jedem Datentyp akzeptieren können und Variablen des `object`-Typs Methoden auf <xref:System.Object> von .NET Framework verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f4ad4-110">The following sample shows how variables of type `object` can accept values of any data type and how variables of type `object` can use methods on <xref:System.Object> from the .NET Framework.</span></span>

[!code-csharp[csrefKeywordsTypes#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#16)]

## <a name="c-language-specification"></a><span data-ttu-id="f4ad4-111">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="f4ad4-111">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f4ad4-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4ad4-112">See also</span></span>

- [<span data-ttu-id="f4ad4-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f4ad4-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f4ad4-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f4ad4-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f4ad4-115">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f4ad4-115">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f4ad4-116">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="f4ad4-116">Reference Types</span></span>](reference-types.md)
- [<span data-ttu-id="f4ad4-117">Werttypen</span><span class="sxs-lookup"><span data-stu-id="f4ad4-117">Value Types</span></span>](value-types.md)