---
title: implicit (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- implicit
- implicit_CSharpKeyword
helpviewer_keywords:
- implicit keyword [C#]
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
ms.openlocfilehash: 70379136fd4b14403eac919ac15590250b17b416
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932730"
---
# <a name="implicit-c-reference"></a><span data-ttu-id="f7673-102">implicit (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f7673-102">implicit (C# Reference)</span></span>

<span data-ttu-id="f7673-103">Das `implicit`-Schlüsselwort wird verwendet, um einen impliziten benutzerdefinierten Typkonvertierungsoperator zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="f7673-103">The `implicit` keyword is used to declare an implicit user-defined type conversion operator.</span></span> <span data-ttu-id="f7673-104">Verwenden Sie es zur Aktivierung impliziter Konvertierungen zwischen einem benutzerdefinierten Typ und einen anderen Typ, wenn die Konvertierung mit Sicherheit nicht zu einem Datenverlust führt.</span><span class="sxs-lookup"><span data-stu-id="f7673-104">Use it to enable implicit conversions between a user-defined type and another type, if the conversion is guaranteed not to cause a loss of data.</span></span>

## <a name="example"></a><span data-ttu-id="f7673-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f7673-105">Example</span></span>

[!code-csharp[csrefKeywordsConversion#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#5)]

<span data-ttu-id="f7673-106">Durch Eliminierung unnötiger Umwandlungen können implizite Konvertierungen die Lesbarkeit des Quellcodes verbessern.</span><span class="sxs-lookup"><span data-stu-id="f7673-106">By eliminating unnecessary casts, implicit conversions can improve source code readability.</span></span> <span data-ttu-id="f7673-107">Da implizite Konvertierungen aber nicht erfordern, dass Programmierer explizit von einem Typ in den anderen umwandeln, muss darauf geachtet werden, um unerwartete Ergebnisse zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="f7673-107">However, because implicit conversions do not require programmers to explicitly cast from one type to the other, care must be taken to prevent unexpected results.</span></span> <span data-ttu-id="f7673-108">Im Allgemeinen sollten implizite Konvertierungsoperatoren keine Ausnahmen auslösen und keine Informationen verlieren, sodass sie problemlos ohne Wissen des Programmierers verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="f7673-108">In general, implicit conversion operators should never throw exceptions and never lose information so that they can be used safely without the programmer's awareness.</span></span> <span data-ttu-id="f7673-109">Wenn ein Konvertierungsoperator diese Kriterien nicht erfüllen kann, sollte er als `explicit` markiert werden.</span><span class="sxs-lookup"><span data-stu-id="f7673-109">If a conversion operator cannot meet those criteria, it should be marked `explicit`.</span></span> <span data-ttu-id="f7673-110">Weitere Informationen finden Sie unter [Verwenden von Konvertierungsoperatoren](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="f7673-110">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f7673-111">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="f7673-111">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f7673-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7673-112">See also</span></span>

- [<span data-ttu-id="f7673-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f7673-113">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="f7673-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f7673-114">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="f7673-115">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f7673-115">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="f7673-116">explicit</span><span class="sxs-lookup"><span data-stu-id="f7673-116">explicit</span></span>](explicit.md)  
- [<span data-ttu-id="f7673-117">Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f7673-117">operator (C# Reference)</span></span>](operator.md)  
- [<span data-ttu-id="f7673-118">Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen</span><span class="sxs-lookup"><span data-stu-id="f7673-118">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
