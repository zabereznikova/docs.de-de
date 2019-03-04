---
title: Verwenden von Konvertierungsoperatoren – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
- implicit conversion operators [C#]
- explicit conversion operators [C#]
ms.assetid: caf36e89-c6c0-4b87-9f9e-85780a45c9a4
ms.openlocfilehash: 888339661ba1cb2e0b702f284d9f27b3217e74c1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973157"
---
# <a name="using-conversion-operators-c-programming-guide"></a><span data-ttu-id="10686-102">Verwenden von Konvertierungsoperatoren (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="10686-102">Using Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="10686-103">Sie können die einfacheren `implicit`-Konvertierungsoperatoren verwenden oder die `explicit`-Konvertierungsoperatoren, die eindeutig signalisieren, dass ein Typ konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="10686-103">You can use `implicit` conversion operators, which are easier to use, or `explicit` conversion operators, which clearly indicate to anyone reading the code that you're converting a type.</span></span> <span data-ttu-id="10686-104">In diesem Thema werden beide Typen von Konvertierungsoperatoren veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="10686-104">This topic demonstrates both types of conversion operator.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10686-105">Weitere Informationen über einfache Typkonvertierungen finden Sie unter [Vorgehensweise: Konvertieren einer Zeichenfolge in eine Zahl](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [Vorgehensweise: Konvertieren eines Bytearrays in einen ganzzahligen Typ](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [Vorgehensweise: Konvertieren zwischen Hexadezimalzeichenfolgen und numerischen Typen](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md) oder <xref:System.Convert>.</span><span class="sxs-lookup"><span data-stu-id="10686-105">For information about simple type conversions, see [How to: Convert a String to a Number](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [How to: Convert a byte Array to an int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [How to: Convert Between Hexadecimal Strings and Numeric Types](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md), or <xref:System.Convert>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10686-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10686-106">Example</span></span>  
 <span data-ttu-id="10686-107">Dies ist ein Beispiel eines expliziten Konvertierungsoperators.</span><span class="sxs-lookup"><span data-stu-id="10686-107">This is an example of an explicit conversion operator.</span></span> <span data-ttu-id="10686-108">Dieser Operator konvertiert den Typ <xref:System.Byte> in den Wertetyp `Digit`.</span><span class="sxs-lookup"><span data-stu-id="10686-108">This operator converts from the type <xref:System.Byte> to a value type called `Digit`.</span></span> <span data-ttu-id="10686-109">Da nicht alle Bytes in eine Ziffer konvertiert werden können, ist die Konvertierung explizit. Das bedeutet, dass eine Umwandlung verwendet werden muss, wie in der `Main`-Methode dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="10686-109">Because not all bytes can be converted to a digit, the conversion is explicit, meaning that a cast must be used, as shown in the `Main` method.</span></span>  
  
 [!code-csharp[csProgGuideStatements#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#11)]  
  
## <a name="example"></a><span data-ttu-id="10686-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10686-110">Example</span></span>  
 <span data-ttu-id="10686-111">In diesem Beispiel wird ein impliziter Konvertierungsoperator dargestellt. Es wird ein Konvertierungsoperator definiert, der das Ergebnis des vorherigen Beispiels rückgängig macht: Er konvertiert die Wertklasse `Digit` in den ganzzahligen Typ <xref:System.Byte>.</span><span class="sxs-lookup"><span data-stu-id="10686-111">This example demonstrates an implicit conversion operator by defining a conversion operator that undoes what the previous example did: it converts from a value class called `Digit` to the integral <xref:System.Byte> type.</span></span> <span data-ttu-id="10686-112">Da sich alle Ziffern in ein <xref:System.Byte> konvertieren lassen, besteht kein Anlass, die explizite Konvertierung zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="10686-112">Because any digit can be converted to a <xref:System.Byte>, there's no need to force users to be explicit about the conversion.</span></span>  
  
 [!code-csharp[csProgGuideStatements#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#12)]  
  
## <a name="see-also"></a><span data-ttu-id="10686-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10686-113">See also</span></span>

- [<span data-ttu-id="10686-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="10686-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="10686-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="10686-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="10686-116">Konvertierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="10686-116">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)
- [<span data-ttu-id="10686-117">is</span><span class="sxs-lookup"><span data-stu-id="10686-117">is</span></span>](../../../csharp/language-reference/keywords/is.md)
