---
title: 'Vorgehensweise: Konvertieren eines Objekts in einen anderen Typ'
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: b89e996324d9ec22fc243b59502f3d36fefdee60
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91090221"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a><span data-ttu-id="43b5b-102">Gewusst wie: Konvertieren eines Objekts in einen anderen Typ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="43b5b-102">How to: Convert an Object to Another Type in Visual Basic</span></span>

<span data-ttu-id="43b5b-103">Sie konvertieren eine `Object` Variable in einen anderen Datentyp, indem Sie ein Konvertierungs Schlüsselwort wie die [CType-Funktion](../../../language-reference/functions/ctype-function.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="43b5b-103">You convert an `Object` variable to another data type by using a conversion keyword such as [CType Function](../../../language-reference/functions/ctype-function.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="43b5b-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="43b5b-104">Example</span></span>  

 <span data-ttu-id="43b5b-105">Im folgenden Beispiel wird eine `Object` -Variable in eine `Integer` und eine konvertiert `String` .</span><span class="sxs-lookup"><span data-stu-id="43b5b-105">The following example converts an `Object` variable to an `Integer` and a `String`.</span></span>  
  
```vb  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 <span data-ttu-id="43b5b-106">Wenn Sie wissen, dass der Inhalt einer `Object` Variablen einen bestimmten Datentyp hat, ist es besser, die Variable in diesen Datentyp zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="43b5b-106">If you know that the contents of an `Object` variable are of a particular data type, it is better to convert the variable to that data type.</span></span> <span data-ttu-id="43b5b-107">Wenn Sie die Variable weiterhin verwenden `Object` , werden entweder *Boxing* und *Unboxing* (bei einem Werttyp) oder eine *späte Bindung* (für einen Verweistyp) verursacht.</span><span class="sxs-lookup"><span data-stu-id="43b5b-107">If you continue to use the `Object` variable, you incur either *boxing* and *unboxing* (for a value type) or *late binding* (for a reference type).</span></span> <span data-ttu-id="43b5b-108">Diese Vorgänge erfordern eine zusätzliche Ausführungszeit und machen die Leistung langsamer.</span><span class="sxs-lookup"><span data-stu-id="43b5b-108">These operations all take extra execution time and make your performance slower.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="43b5b-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="43b5b-109">Compile the code</span></span>  

 <span data-ttu-id="43b5b-110">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="43b5b-110">This example requires:</span></span>  
  
- <span data-ttu-id="43b5b-111">Einen Verweis auf den <xref:System?displayProperty=nameWithType>-Namespace</span><span class="sxs-lookup"><span data-stu-id="43b5b-111">A reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43b5b-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43b5b-112">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="43b5b-113">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="43b5b-113">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="43b5b-114">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="43b5b-114">Widening and Narrowing Conversions</span></span>](widening-and-narrowing-conversions.md)
- [<span data-ttu-id="43b5b-115">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="43b5b-115">Implicit and Explicit Conversions</span></span>](implicit-and-explicit-conversions.md)
- [<span data-ttu-id="43b5b-116">Konvertierungen zwischen Zeichenfolgen und anderen Typen</span><span class="sxs-lookup"><span data-stu-id="43b5b-116">Conversions Between Strings and Other Types</span></span>](conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="43b5b-117">Arraykonvertierungen</span><span class="sxs-lookup"><span data-stu-id="43b5b-117">Array Conversions</span></span>](array-conversions.md)
- [<span data-ttu-id="43b5b-118">Strukturen</span><span class="sxs-lookup"><span data-stu-id="43b5b-118">Structures</span></span>](structures.md)
- [<span data-ttu-id="43b5b-119">Datentypen</span><span class="sxs-lookup"><span data-stu-id="43b5b-119">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="43b5b-120">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="43b5b-120">Type Conversion Functions</span></span>](../../../language-reference/functions/type-conversion-functions.md)
