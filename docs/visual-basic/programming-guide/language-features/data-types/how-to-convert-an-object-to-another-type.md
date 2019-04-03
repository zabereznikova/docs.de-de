---
title: 'Vorgehensweise: Konvertieren eines Objekts in einen anderen Typ in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: 1e515c0f4ce8e787754c61a9b53d247fa93c49f2
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814379"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a><span data-ttu-id="1f3eb-102">Vorgehensweise: Konvertieren eines Objekts in einen anderen Typ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1f3eb-102">How to: Convert an Object to Another Type in Visual Basic</span></span>
<span data-ttu-id="1f3eb-103">Konvertieren Sie eine `Object` Variable in einen anderen Datentyp mithilfe einer wie [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md).</span><span class="sxs-lookup"><span data-stu-id="1f3eb-103">You convert an `Object` variable to another data type by using a conversion keyword such as [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f3eb-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1f3eb-104">Example</span></span>  
 <span data-ttu-id="1f3eb-105">Im folgenden Beispiel wird ein `Object` Variable eine `Integer` und `String`.</span><span class="sxs-lookup"><span data-stu-id="1f3eb-105">The following example converts an `Object` variable to an `Integer` and a `String`.</span></span>  
  
```  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 <span data-ttu-id="1f3eb-106">Wenn Sie wissen, dass der Inhalt des ein `Object` Variablen sind eines bestimmten Datentyps, es ist besser, die die Variable in diesen Datentyp zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="1f3eb-106">If you know that the contents of an `Object` variable are of a particular data type, it is better to convert the variable to that data type.</span></span> <span data-ttu-id="1f3eb-107">Wenn Sie weiterhin die `Object` Variablen, es fallen entweder *Boxing* und *unboxing* (für einen Werttyp) oder *späte Bindung* (für einen Verweistyp).</span><span class="sxs-lookup"><span data-stu-id="1f3eb-107">If you continue to use the `Object` variable, you incur either *boxing* and *unboxing* (for a value type) or *late binding* (for a reference type).</span></span> <span data-ttu-id="1f3eb-108">Diese Vorgänge alle zusätzlichen Ausführung Zeit in Anspruch nehmen, und stellen die Leistung langsamer.</span><span class="sxs-lookup"><span data-stu-id="1f3eb-108">These operations all take extra execution time and make your performance slower.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1f3eb-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="1f3eb-109">Compiling the Code</span></span>  
 <span data-ttu-id="1f3eb-110">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1f3eb-110">This example requires:</span></span>  
  
-   <span data-ttu-id="1f3eb-111">Einen Verweis auf den <xref:System?displayProperty=nameWithType>-Namespace</span><span class="sxs-lookup"><span data-stu-id="1f3eb-111">A reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f3eb-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f3eb-112">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="1f3eb-113">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1f3eb-113">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="1f3eb-114">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="1f3eb-114">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="1f3eb-115">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="1f3eb-115">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="1f3eb-116">Konvertierungen zwischen Zeichenfolgen und anderen Typen</span><span class="sxs-lookup"><span data-stu-id="1f3eb-116">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="1f3eb-117">Arraykonvertierungen</span><span class="sxs-lookup"><span data-stu-id="1f3eb-117">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [<span data-ttu-id="1f3eb-118">Strukturen</span><span class="sxs-lookup"><span data-stu-id="1f3eb-118">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="1f3eb-119">Datentypen</span><span class="sxs-lookup"><span data-stu-id="1f3eb-119">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="1f3eb-120">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="1f3eb-120">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
