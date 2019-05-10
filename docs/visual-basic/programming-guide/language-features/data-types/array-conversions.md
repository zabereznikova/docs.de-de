---
title: Arraykonvertierungen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], converting type
- type conversion [Visual Basic], arrays
- conversions [Visual Basic], type
- arrays [Visual Basic], data types
- conversions [Visual Basic], data type
- object arrays [Visual Basic], converting type
- data type conversion [Visual Basic], array conversions
- conversions [Visual Basic], array types
- object arrays
ms.assetid: fceff7d2-a1b7-44c7-b9aa-8bd831d8a444
ms.openlocfilehash: f69ed6e0040f33f810d324a76859d448e9dc7632
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64601139"
---
# <a name="array-conversions-visual-basic"></a><span data-ttu-id="7fed3-102">Arraykonvertierungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7fed3-102">Array Conversions (Visual Basic)</span></span>
<span data-ttu-id="7fed3-103">Sie können einen Arraytyp in einen anderen Arraytyp konvertieren, sofern Sie die folgenden Bedingungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="7fed3-103">You can convert an array type to a different array type provided you meet the following conditions:</span></span>  
  
- <span data-ttu-id="7fed3-104">**Gleich Rang.**</span><span class="sxs-lookup"><span data-stu-id="7fed3-104">**Equal Rank.**</span></span> <span data-ttu-id="7fed3-105">Die Zahl der die beiden Arrays müssen identisch sein, also verfügen, müssen die gleiche Anzahl von Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="7fed3-105">The ranks of the two arrays must be the same, that is, they must have the same number of dimensions.</span></span> <span data-ttu-id="7fed3-106">Die Länge der jeweiligen Dimensionen müssen allerdings nicht identisch sein.</span><span class="sxs-lookup"><span data-stu-id="7fed3-106">However, the lengths of the respective dimensions do not need to be the same.</span></span>  
  
- <span data-ttu-id="7fed3-107">**Datentyp des Elements.**</span><span class="sxs-lookup"><span data-stu-id="7fed3-107">**Element Data Type.**</span></span> <span data-ttu-id="7fed3-108">Die Datentypen der Elemente beider Arrays müssen Referenztypen sein.</span><span class="sxs-lookup"><span data-stu-id="7fed3-108">The data types of the elements of both arrays must be reference types.</span></span> <span data-ttu-id="7fed3-109">Sie können nicht konvertiert werden ein `Integer` array an eine `Long` array oder sogar um eine `Object` array, da mindestens ein Werttyp ist.</span><span class="sxs-lookup"><span data-stu-id="7fed3-109">You cannot convert an `Integer` array to a `Long` array, or even to an `Object` array, because at least one value type is involved.</span></span> <span data-ttu-id="7fed3-110">Weitere Informationen finden Sie unter [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="7fed3-110">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
- <span data-ttu-id="7fed3-111">**Die Konvertierung.**</span><span class="sxs-lookup"><span data-stu-id="7fed3-111">**Convertibility.**</span></span> <span data-ttu-id="7fed3-112">Eine Konvertierung, erweiternd oder einschränkend, muss zwischen den Elementtypen der beiden Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="7fed3-112">A conversion, either widening or narrowing, must be possible between the element types of the two arrays.</span></span> <span data-ttu-id="7fed3-113">Ein Beispiel, das diese Anforderung nicht erfüllt, wird ein Versuch einer Konvertierung zwischen einem `String` Array und einem Array von einer Klasse abgeleitet <xref:System.Attribute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7fed3-113">An example that fails this requirement is an attempted conversion between a `String` array and an array of a class derived from <xref:System.Attribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7fed3-114">Diese beiden Typen haben nichts gemeinsam, und keine Konvertierung jeglicher Art, die zwischen ihnen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7fed3-114">These two types have nothing in common, and no conversion of any kind exists between them.</span></span>  
  
 <span data-ttu-id="7fed3-115">Eine Konvertierung von einem Arraytyp ist erweiternde oder einschränkende, je nachdem, ob die Konvertierung der jeweiligen Elemente erweiternde oder einschränkende ist.</span><span class="sxs-lookup"><span data-stu-id="7fed3-115">A conversion of one array type to another is widening or narrowing depending on whether the conversion of the respective elements is widening or narrowing.</span></span> <span data-ttu-id="7fed3-116">Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="7fed3-116">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
## <a name="conversion-to-an-object-array"></a><span data-ttu-id="7fed3-117">Konvertierung in ein Objektarray</span><span class="sxs-lookup"><span data-stu-id="7fed3-117">Conversion to an Object Array</span></span>  
 <span data-ttu-id="7fed3-118">Wenn Sie deklarieren eine `Object` Array ohne Initialisierung hinzuzufügen, den Elementtyp `Object` solange er nicht initialisiert ist.</span><span class="sxs-lookup"><span data-stu-id="7fed3-118">When you declare an `Object` array without initializing it, its element type is `Object` as long as it remains uninitialized.</span></span> <span data-ttu-id="7fed3-119">Wenn Sie es in ein Array von einer bestimmten Klasse festlegen, dauert es für den Typ dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="7fed3-119">When you set it to an array of a specific class, it takes on the type of that class.</span></span> <span data-ttu-id="7fed3-120">Die zugrunde liegende Typ ist jedoch weiterhin `Object`, können Sie ihn anschließend in ein anderes Array einer unabhängigen Klasse festlegen.</span><span class="sxs-lookup"><span data-stu-id="7fed3-120">However, its underlying type is still `Object`, and you can subsequently set it to another array of an unrelated class.</span></span> <span data-ttu-id="7fed3-121">Da alle Klassen abgeleitet `Object`, können Sie Elementtyp des Arrays aus einer Klasse in einer beliebigen anderen Klasse ändern.</span><span class="sxs-lookup"><span data-stu-id="7fed3-121">Since all classes derive from `Object`, you can change the array's element type from any class to any other class.</span></span>  
  
 <span data-ttu-id="7fed3-122">Im folgenden Beispiel keine Konvertierungen zwischen Typen `student` und `String`, aber beide abgeleitet `Object`, sodass alle Zuweisungen gültig sind.</span><span class="sxs-lookup"><span data-stu-id="7fed3-122">In the following example, no conversion exists between types `student` and `String`, but both derive from `Object`, so all assignments are valid.</span></span>  
  
```  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### <a name="underlying-type-of-an-array"></a><span data-ttu-id="7fed3-123">Der zugrunde liegende Typ eines Arrays</span><span class="sxs-lookup"><span data-stu-id="7fed3-123">Underlying Type of an Array</span></span>  
 <span data-ttu-id="7fed3-124">Wenn Sie ursprünglich ein Array mit einer bestimmten Klasse deklarieren, ist die zugrunde liegende Elementtyp dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="7fed3-124">If you originally declare an array with a specific class, its underlying element type is that class.</span></span> <span data-ttu-id="7fed3-125">Wenn Sie anschließend auf ein Array von einer anderen Klasse festlegen, muss eine Konvertierung zwischen den beiden Klassen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="7fed3-125">If you subsequently set it to an array of another class, there must be a conversion between the two classes.</span></span>  
  
 <span data-ttu-id="7fed3-126">Im folgenden Beispiel `students` ist eine `student` Array.</span><span class="sxs-lookup"><span data-stu-id="7fed3-126">In the following example, `students` is a `student` array.</span></span> <span data-ttu-id="7fed3-127">Da keine Konvertierung vorhanden, zwischen ist `String` und `student`, die letzte Anweisung schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="7fed3-127">Since no conversion exists between `String` and `student`, the last statement fails.</span></span>  
  
```  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a><span data-ttu-id="7fed3-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7fed3-128">See also</span></span>

- [<span data-ttu-id="7fed3-129">Datentypen</span><span class="sxs-lookup"><span data-stu-id="7fed3-129">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="7fed3-130">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7fed3-130">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="7fed3-131">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="7fed3-131">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="7fed3-132">Konvertierungen zwischen Zeichenfolgen und anderen Typen</span><span class="sxs-lookup"><span data-stu-id="7fed3-132">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="7fed3-133">Vorgehensweise: Konvertieren eines Objekts in einen anderen Typ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7fed3-133">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="7fed3-134">Datentypen</span><span class="sxs-lookup"><span data-stu-id="7fed3-134">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="7fed3-135">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="7fed3-135">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="7fed3-136">Arrays</span><span class="sxs-lookup"><span data-stu-id="7fed3-136">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
