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
ms.openlocfilehash: a179b7cf5b82132db88fb5412f0ca4be207f0987
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651465"
---
# <a name="array-conversions-visual-basic"></a><span data-ttu-id="1bce6-102">Arraykonvertierungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1bce6-102">Array Conversions (Visual Basic)</span></span>
<span data-ttu-id="1bce6-103">Sie können einen Arraytyp in einen anderen Arraytyp konvertieren, falls Sie die folgenden Bedingungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="1bce6-103">You can convert an array type to a different array type provided you meet the following conditions:</span></span>  
  
-   <span data-ttu-id="1bce6-104">**Gleich Rang.**</span><span class="sxs-lookup"><span data-stu-id="1bce6-104">**Equal Rank.**</span></span> <span data-ttu-id="1bce6-105">Der Rang der beiden Arrays müssen identisch sein, also verfügen, müssen die gleiche Anzahl von Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="1bce6-105">The ranks of the two arrays must be the same, that is, they must have the same number of dimensions.</span></span> <span data-ttu-id="1bce6-106">Die Länge der jeweiligen Dimensionen müssen jedoch nicht identisch sein.</span><span class="sxs-lookup"><span data-stu-id="1bce6-106">However, the lengths of the respective dimensions do not need to be the same.</span></span>  
  
-   <span data-ttu-id="1bce6-107">**Datentyp des Elements.**</span><span class="sxs-lookup"><span data-stu-id="1bce6-107">**Element Data Type.**</span></span> <span data-ttu-id="1bce6-108">Die Datentypen der Elemente beider Arrays, müssen es sich um Verweistypen sein.</span><span class="sxs-lookup"><span data-stu-id="1bce6-108">The data types of the elements of both arrays must be reference types.</span></span> <span data-ttu-id="1bce6-109">Sie können nicht konvertiert ein `Integer` array an eine `Long` array oder sogar ein `Object` array, da mindestens ein Werttyp ist.</span><span class="sxs-lookup"><span data-stu-id="1bce6-109">You cannot convert an `Integer` array to a `Long` array, or even to an `Object` array, because at least one value type is involved.</span></span> <span data-ttu-id="1bce6-110">Weitere Informationen finden Sie unter [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="1bce6-110">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
-   <span data-ttu-id="1bce6-111">**Konvertibilität.**</span><span class="sxs-lookup"><span data-stu-id="1bce6-111">**Convertibility.**</span></span> <span data-ttu-id="1bce6-112">Eine Konvertierung, erweiternd oder einschränkend, muss zwischen den Elementtypen der beiden Arrays möglich sein.</span><span class="sxs-lookup"><span data-stu-id="1bce6-112">A conversion, either widening or narrowing, must be possible between the element types of the two arrays.</span></span> <span data-ttu-id="1bce6-113">Ein Beispiel, das diese Anforderung ein Fehler auftritt, wird eine versuchte Konvertierung zwischen einem `String` und Array einer Klasse abgeleitet <xref:System.Attribute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1bce6-113">An example that fails this requirement is an attempted conversion between a `String` array and an array of a class derived from <xref:System.Attribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1bce6-114">Diese beiden Typen haben nichts gemeinsam, und keine Konvertierung jeglicher Art, die zwischen ihnen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1bce6-114">These two types have nothing in common, and no conversion of any kind exists between them.</span></span>  
  
 <span data-ttu-id="1bce6-115">Eine Konvertierung von einem Arraytyp ist erweiternde oder einschränkende je nach gibt an, ob die Konvertierung der entsprechenden Elemente erweiternde oder einschränkende ist.</span><span class="sxs-lookup"><span data-stu-id="1bce6-115">A conversion of one array type to another is widening or narrowing depending on whether the conversion of the respective elements is widening or narrowing.</span></span> <span data-ttu-id="1bce6-116">Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="1bce6-116">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
## <a name="conversion-to-an-object-array"></a><span data-ttu-id="1bce6-117">Die Konvertierung in einem Objektarray</span><span class="sxs-lookup"><span data-stu-id="1bce6-117">Conversion to an Object Array</span></span>  
 <span data-ttu-id="1bce6-118">Beim Deklarieren einer `Object` Array ohne initialisieren, dessen Elementtyp ist `Object` solange er nicht initialisiert ist.</span><span class="sxs-lookup"><span data-stu-id="1bce6-118">When you declare an `Object` array without initializing it, its element type is `Object` as long as it remains uninitialized.</span></span> <span data-ttu-id="1bce6-119">Wenn Sie es auf ein Array von einer bestimmten Klasse festlegen, dauert es für den Typ dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="1bce6-119">When you set it to an array of a specific class, it takes on the type of that class.</span></span> <span data-ttu-id="1bce6-120">Der zugrunde liegende Typ ist jedoch weiterhin `Object`, und Sie können Sie später in ein anderes Array einer unabhängigen Klasse festlegen.</span><span class="sxs-lookup"><span data-stu-id="1bce6-120">However, its underlying type is still `Object`, and you can subsequently set it to another array of an unrelated class.</span></span> <span data-ttu-id="1bce6-121">Da von allen Klassen abgeleitet werden `Object`, Sie können der Arrayelementtyp beliebiger Klassen in jeder anderen Klasse ändern.</span><span class="sxs-lookup"><span data-stu-id="1bce6-121">Since all classes derive from `Object`, you can change the array's element type from any class to any other class.</span></span>  
  
 <span data-ttu-id="1bce6-122">Im folgenden Beispiel keine Konvertierungen zwischen Typen `student` und `String`, aber beide abgeleitet `Object`, sodass alle Zuweisungen gültig sind.</span><span class="sxs-lookup"><span data-stu-id="1bce6-122">In the following example, no conversion exists between types `student` and `String`, but both derive from `Object`, so all assignments are valid.</span></span>  
  
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
  
### <a name="underlying-type-of-an-array"></a><span data-ttu-id="1bce6-123">Zugrunde liegender Typ eines Arrays</span><span class="sxs-lookup"><span data-stu-id="1bce6-123">Underlying Type of an Array</span></span>  
 <span data-ttu-id="1bce6-124">Wenn Sie ursprünglich ein Array mit einer bestimmten Klasse deklarieren, wird dessen zugrunde liegendem Elementtyp dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="1bce6-124">If you originally declare an array with a specific class, its underlying element type is that class.</span></span> <span data-ttu-id="1bce6-125">Wenn Sie anschließend auf ein Array von einer anderen Klasse festlegen, muss eine Konvertierung zwischen den beiden Klassen sein.</span><span class="sxs-lookup"><span data-stu-id="1bce6-125">If you subsequently set it to an array of another class, there must be a conversion between the two classes.</span></span>  
  
 <span data-ttu-id="1bce6-126">Im folgenden Beispiel `students` ist ein `student` Array.</span><span class="sxs-lookup"><span data-stu-id="1bce6-126">In the following example, `students` is a `student` array.</span></span> <span data-ttu-id="1bce6-127">Da keine zwischen Konvertierungen `String` und `student`, die letzte Anweisung schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="1bce6-127">Since no conversion exists between `String` and `student`, the last statement fails.</span></span>  
  
```  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a><span data-ttu-id="1bce6-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1bce6-128">See Also</span></span>  
 [<span data-ttu-id="1bce6-129">Datentypen</span><span class="sxs-lookup"><span data-stu-id="1bce6-129">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="1bce6-130">Konvertierungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1bce6-130">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="1bce6-131">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="1bce6-131">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="1bce6-132">Konvertierungen zwischen Zeichenfolgen und anderen Typen</span><span class="sxs-lookup"><span data-stu-id="1bce6-132">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [<span data-ttu-id="1bce6-133">Vorgehensweise: Konvertieren eines Objekts in einen anderen Typ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1bce6-133">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [<span data-ttu-id="1bce6-134">Datentypen</span><span class="sxs-lookup"><span data-stu-id="1bce6-134">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="1bce6-135">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="1bce6-135">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="1bce6-136">Arrays</span><span class="sxs-lookup"><span data-stu-id="1bce6-136">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
