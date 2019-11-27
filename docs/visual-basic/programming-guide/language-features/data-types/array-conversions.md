---
title: Arraykonvertierungen
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
ms.openlocfilehash: 622ebe8a77f2dfbeb35e0408be48622d93d409c6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345861"
---
# <a name="array-conversions-visual-basic"></a><span data-ttu-id="ad27c-102">Arraykonvertierungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad27c-102">Array Conversions (Visual Basic)</span></span>
<span data-ttu-id="ad27c-103">Sie können einen Arraytyp in einen anderen Arraytyp konvertieren, wenn die folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="ad27c-103">You can convert an array type to a different array type provided you meet the following conditions:</span></span>  
  
- <span data-ttu-id="ad27c-104">**Gleicher Rang.**</span><span class="sxs-lookup"><span data-stu-id="ad27c-104">**Equal Rank.**</span></span> <span data-ttu-id="ad27c-105">Die Ränge der beiden Arrays müssen identisch sein, d. h., Sie müssen über die gleiche Anzahl von Dimensionen verfügen.</span><span class="sxs-lookup"><span data-stu-id="ad27c-105">The ranks of the two arrays must be the same, that is, they must have the same number of dimensions.</span></span> <span data-ttu-id="ad27c-106">Die Längen der jeweiligen Dimensionen müssen jedoch nicht identisch sein.</span><span class="sxs-lookup"><span data-stu-id="ad27c-106">However, the lengths of the respective dimensions do not need to be the same.</span></span>  
  
- <span data-ttu-id="ad27c-107">**Der Element Datentyp.**</span><span class="sxs-lookup"><span data-stu-id="ad27c-107">**Element Data Type.**</span></span> <span data-ttu-id="ad27c-108">Die Datentypen der Elemente beider Arrays müssen Verweis Typen sein.</span><span class="sxs-lookup"><span data-stu-id="ad27c-108">The data types of the elements of both arrays must be reference types.</span></span> <span data-ttu-id="ad27c-109">Sie können ein `Integer` Array nicht in ein `Long` Array oder sogar in ein `Object` Array konvertieren, da mindestens ein Werttyp beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="ad27c-109">You cannot convert an `Integer` array to a `Long` array, or even to an `Object` array, because at least one value type is involved.</span></span> <span data-ttu-id="ad27c-110">Weitere Informationen finden Sie unter [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="ad27c-110">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
- <span data-ttu-id="ad27c-111">**Konvertierbarkeit.**</span><span class="sxs-lookup"><span data-stu-id="ad27c-111">**Convertibility.**</span></span> <span data-ttu-id="ad27c-112">Eine Konvertierung, die erweitert oder einschränkend ist, muss zwischen den Elementtypen der beiden Arrays möglich sein.</span><span class="sxs-lookup"><span data-stu-id="ad27c-112">A conversion, either widening or narrowing, must be possible between the element types of the two arrays.</span></span> <span data-ttu-id="ad27c-113">Ein Beispiel, bei dem diese Anforderung nicht erfüllt wird, ist eine versuchte Konvertierung zwischen einem `String` Array und einem Array einer Klasse, die von <xref:System.Attribute?displayProperty=nameWithType>abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="ad27c-113">An example that fails this requirement is an attempted conversion between a `String` array and an array of a class derived from <xref:System.Attribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ad27c-114">Diese beiden Typen haben nichts gemeinsam, und es besteht keine Konvertierung zwischen Ihnen.</span><span class="sxs-lookup"><span data-stu-id="ad27c-114">These two types have nothing in common, and no conversion of any kind exists between them.</span></span>  
  
 <span data-ttu-id="ad27c-115">Eine Konvertierung von einem Arraytyp in einen anderen wird erweitert oder einschränkend, abhängig davon, ob die Konvertierung der entsprechenden Elemente zunimmt oder einschränkend ist.</span><span class="sxs-lookup"><span data-stu-id="ad27c-115">A conversion of one array type to another is widening or narrowing depending on whether the conversion of the respective elements is widening or narrowing.</span></span> <span data-ttu-id="ad27c-116">Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="ad27c-116">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
## <a name="conversion-to-an-object-array"></a><span data-ttu-id="ad27c-117">Konvertieren in ein Objekt Array</span><span class="sxs-lookup"><span data-stu-id="ad27c-117">Conversion to an Object Array</span></span>  
 <span data-ttu-id="ad27c-118">Wenn Sie ein `Object` Array deklarieren, ohne es zu initialisieren, wird der Elementtyp `Object`, solange es nicht initialisiert bleibt.</span><span class="sxs-lookup"><span data-stu-id="ad27c-118">When you declare an `Object` array without initializing it, its element type is `Object` as long as it remains uninitialized.</span></span> <span data-ttu-id="ad27c-119">Wenn Sie es auf ein Array einer bestimmten Klasse festlegen, wird der Typ dieser Klasse benötigt.</span><span class="sxs-lookup"><span data-stu-id="ad27c-119">When you set it to an array of a specific class, it takes on the type of that class.</span></span> <span data-ttu-id="ad27c-120">Allerdings ist der zugrunde liegende Typ weiterhin `Object`, und Sie können ihn anschließend auf ein anderes Array einer nicht verknüpften Klasse festlegen.</span><span class="sxs-lookup"><span data-stu-id="ad27c-120">However, its underlying type is still `Object`, and you can subsequently set it to another array of an unrelated class.</span></span> <span data-ttu-id="ad27c-121">Da alle Klassen von `Object`abgeleitet werden, können Sie den Elementtyp des Arrays von einer beliebigen Klasse in eine beliebige andere Klasse ändern.</span><span class="sxs-lookup"><span data-stu-id="ad27c-121">Since all classes derive from `Object`, you can change the array's element type from any class to any other class.</span></span>  
  
 <span data-ttu-id="ad27c-122">Im folgenden Beispiel ist keine Konvertierung zwischen Typen `student` und `String`vorhanden, beide werden jedoch von `Object`abgeleitet, sodass alle Zuweisungen gültig sind.</span><span class="sxs-lookup"><span data-stu-id="ad27c-122">In the following example, no conversion exists between types `student` and `String`, but both derive from `Object`, so all assignments are valid.</span></span>  
  
```vb  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### <a name="underlying-type-of-an-array"></a><span data-ttu-id="ad27c-123">Zugrunde liegender Typ eines Arrays</span><span class="sxs-lookup"><span data-stu-id="ad27c-123">Underlying Type of an Array</span></span>  
 <span data-ttu-id="ad27c-124">Wenn Sie ein Array ursprünglich mit einer bestimmten Klasse deklariert haben, ist der zugrunde liegende Elementtyp diese Klasse.</span><span class="sxs-lookup"><span data-stu-id="ad27c-124">If you originally declare an array with a specific class, its underlying element type is that class.</span></span> <span data-ttu-id="ad27c-125">Wenn Sie anschließend ein Array einer anderen Klasse festlegen, muss eine Konvertierung zwischen den beiden Klassen erfolgen.</span><span class="sxs-lookup"><span data-stu-id="ad27c-125">If you subsequently set it to an array of another class, there must be a conversion between the two classes.</span></span>  
  
 <span data-ttu-id="ad27c-126">Im folgenden Beispiel ist `students` ein `student` Array.</span><span class="sxs-lookup"><span data-stu-id="ad27c-126">In the following example, `students` is a `student` array.</span></span> <span data-ttu-id="ad27c-127">Da zwischen `String` und `student`keine Konvertierung vorhanden ist, schlägt die letzte Anweisung fehl.</span><span class="sxs-lookup"><span data-stu-id="ad27c-127">Since no conversion exists between `String` and `student`, the last statement fails.</span></span>  
  
```vb  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a><span data-ttu-id="ad27c-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad27c-128">See also</span></span>

- [<span data-ttu-id="ad27c-129">Datentypen</span><span class="sxs-lookup"><span data-stu-id="ad27c-129">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="ad27c-130">Typkonvertierungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ad27c-130">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="ad27c-131">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="ad27c-131">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="ad27c-132">Konvertierungen zwischen Zeichenfolgen und anderen Typen</span><span class="sxs-lookup"><span data-stu-id="ad27c-132">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="ad27c-133">Gewusst wie: Konvertieren eines Objekts in einen anderen Typ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ad27c-133">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="ad27c-134">Datentypen</span><span class="sxs-lookup"><span data-stu-id="ad27c-134">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="ad27c-135">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="ad27c-135">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="ad27c-136">Arrays</span><span class="sxs-lookup"><span data-stu-id="ad27c-136">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
