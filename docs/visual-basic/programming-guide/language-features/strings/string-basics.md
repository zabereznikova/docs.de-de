---
title: String-Grundlagen in Visual Basic | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], Like operator
- strings [Visual Basic], Visual Basic
- strings [Visual Basic], regular expressions
ms.assetid: 5674418d-f00d-4f72-9f98-d15897793350
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 98c2707ef8aabc77951b21cfe9f4edcd3a88c863
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="string-basics-in-visual-basic"></a><span data-ttu-id="e835f-102">Grundlagen zu Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e835f-102">String Basics in Visual Basic</span></span>
<span data-ttu-id="e835f-103">Der `String`-Datentyp stellt eine Reihe von Zeichen dar (wobei jedes Zeichen wiederum eine Instanz des `Char`-Datentyps darstellt).</span><span class="sxs-lookup"><span data-stu-id="e835f-103">The `String` data type represents a series of characters (each representing in turn an instance of the `Char` data type).</span></span> <span data-ttu-id="e835f-104">In diesem Thema werden die grundlegenden Konzepte von Zeichenfolgen in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] erläutert.</span><span class="sxs-lookup"><span data-stu-id="e835f-104">This topic introduces the basic concepts of strings in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
## <a name="string-variables"></a><span data-ttu-id="e835f-105">Zeichenfolgenvariablen</span><span class="sxs-lookup"><span data-stu-id="e835f-105">String Variables</span></span>  
 <span data-ttu-id="e835f-106">Einer Instanz einer Zeichenfolge kann ein Literalwert zugewiesen werden, der eine Reihe von Zeichen darstellt.</span><span class="sxs-lookup"><span data-stu-id="e835f-106">An instance of a string can be assigned a literal value that represents a series of characters.</span></span> <span data-ttu-id="e835f-107">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e835f-107">For example:</span></span>  
  
 <span data-ttu-id="e835f-108">[!code-vb[VbVbalrStrings&#63;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e835f-108">[!code-vb[VbVbalrStrings#63](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_1.vb)]</span></span>  
  
 <span data-ttu-id="e835f-109">Eine `String`-Variable kann auch einen beliebigen Ausdruck annehmen, der eine Zeichenfolge ergibt.</span><span class="sxs-lookup"><span data-stu-id="e835f-109">A `String` variable can also accept any expression that evaluates to a string.</span></span> <span data-ttu-id="e835f-110">Beispiele werden unten gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e835f-110">Examples are shown below:</span></span>  
  
 <span data-ttu-id="e835f-111">[!code-vb[VbVbalrStrings&#64;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="e835f-111">[!code-vb[VbVbalrStrings#64](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_2.vb)]</span></span>  
  
 <span data-ttu-id="e835f-112">Jedes Literal, das einer `String`-Variable zugewiesen ist, muss in Anführungszeichen eingeschlossen werden („“).</span><span class="sxs-lookup"><span data-stu-id="e835f-112">Any literal that is assigned to a `String` variable must be enclosed in quotation marks ("").</span></span> <span data-ttu-id="e835f-113">Dies bedeutet, dass ein Anführungszeichen in einer Zeichenfolge nicht durch ein Anführungszeichen dargestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e835f-113">This means that a quotation mark within a string cannot be represented by a quotation mark.</span></span> <span data-ttu-id="e835f-114">Beispielsweise verursacht der folgende Code einen Compilerfehler:</span><span class="sxs-lookup"><span data-stu-id="e835f-114">For example, the following code causes a compiler error:</span></span>  
  
 <span data-ttu-id="e835f-115">[!code-vb[VbVbalrStrings&#65;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="e835f-115">[!code-vb[VbVbalrStrings#65](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_3.vb)]</span></span>  
  
 <span data-ttu-id="e835f-116">Dieser Code verursacht einen Fehler, da der Compiler die Zeichenfolge nach dem zweiten Anführungszeichen beendet, und der Rest der Zeichenfolge wird als Code interpretiert.</span><span class="sxs-lookup"><span data-stu-id="e835f-116">This code causes an error because the compiler terminates the string after the second quotation mark, and the remainder of the string is interpreted as code.</span></span> <span data-ttu-id="e835f-117">Zur Lösung dieses Problems interpretiert [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] zwei Anführungszeichen in einem Zeichenfolgenliteral als ein Anführungszeichen in der Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e835f-117">To solve this problem, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] interprets two quotation marks in a string literal as one quotation mark in the string.</span></span> <span data-ttu-id="e835f-118">Das folgende Beispiel zeigt die korrekte Methode zum Einschließen eines Anführungszeichens in eine Zeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="e835f-118">The following example demonstrates the correct way to include a quotation mark in a string:</span></span>  
  
 <span data-ttu-id="e835f-119">[!code-vb[VbVbalrStrings&#66;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="e835f-119">[!code-vb[VbVbalrStrings#66](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_4.vb)]</span></span>  
  
 <span data-ttu-id="e835f-120">Im vorherigen Beispiel werden die beiden Anführungszeichen, die vor dem Wort `Look` vorhanden sind, zu einem Anführungszeichen in der Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e835f-120">In the preceding example, the two quotation marks preceding the word `Look` become one quotation mark in the string.</span></span> <span data-ttu-id="e835f-121">Die drei Anführungszeichen am Ende der Zeile stellen ein Anführungszeichen in der Zeichenfolge und das Abschlusszeichen der Zeichenfolge dar.</span><span class="sxs-lookup"><span data-stu-id="e835f-121">The three quotation marks at the end of the line represent one quotation mark in the string and the string termination character.</span></span>  
  
 <span data-ttu-id="e835f-122">Zeichenfolgenliterale können mehrere Zeilen enthalten:</span><span class="sxs-lookup"><span data-stu-id="e835f-122">String literals can contain multiple lines:</span></span>  
  
```vb  
Dim x = "hello  
world"  
  
```  
  
 <span data-ttu-id="e835f-123">Die resultierende Zeichenfolge enthält Zeilenumbruchsequenzen, die Sie in Ihrem Zeichenfolgenliteral (vbcr, vbcrlf usw.) verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="e835f-123">The resulting string contains newline sequences that you used in your string literal (vbcr, vbcrlf, etc.).</span></span>  <span data-ttu-id="e835f-124">Sie müssen nicht mehr die bisherige Problemumgehung verwenden:</span><span class="sxs-lookup"><span data-stu-id="e835f-124">You no longer need to use the old workaround:</span></span>  
  
```vb  
Dim x = <xml><![CDATA[Hello  
World]]></xml>.Value  
  
```  
  
## <a name="characters-in-strings"></a><span data-ttu-id="e835f-125">Zeichen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="e835f-125">Characters in Strings</span></span>  
 <span data-ttu-id="e835f-126">Eine Zeichenfolge kann als eine Reihe von `Char`-Werten betrachtet werden, und der `String`-Typ verfügt über integrierte Funktionen, mit denen Sie zahlreiche Bearbeitungen an einer Zeichenfolge vornehmen können, die den durch Arrays zulässigen Bearbeitungen ähneln.</span><span class="sxs-lookup"><span data-stu-id="e835f-126">A string can be thought of as a series of `Char` values, and the `String` type has built-in functions that allow you to perform many manipulations on a string that resemble the manipulations allowed by arrays.</span></span> <span data-ttu-id="e835f-127">Wie bei allen Arrays in [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)], handelt es sich dabei um nullbasierte Arrays.</span><span class="sxs-lookup"><span data-stu-id="e835f-127">Like all array in [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)], these are zero-based arrays.</span></span> <span data-ttu-id="e835f-128">Sie möchten möglicherweise auf ein bestimmtes Zeichen in einer Zeichenfolge durch die `Chars`-Eigenschaft verweisen, die eine Möglichkeit bietet, auf ein Zeichen durch die Position zuzugreifen, in der es in der Zeichenfolge auftritt.</span><span class="sxs-lookup"><span data-stu-id="e835f-128">You may refer to a specific character in a string through the `Chars` property, which provides a way to access a character by the position in which it appears in the string.</span></span> <span data-ttu-id="e835f-129">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e835f-129">For example:</span></span>  
  
 <span data-ttu-id="e835f-130">[!code-vb[VbVbalrStrings&#67;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="e835f-130">[!code-vb[VbVbalrStrings#67](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_5.vb)]</span></span>  
  
 <span data-ttu-id="e835f-131">Im obigen Beispiel gibt die `Chars`-Eigenschaft der Zeichenfolge das vierte Zeichen in der Zeichenfolge zurück, wobei es sich um `D` handelt, und weist dieses `myChar` zu.</span><span class="sxs-lookup"><span data-stu-id="e835f-131">In the above example, the `Chars` property of the string returns the fourth character in the string, which is `D`, and assigns it to `myChar`.</span></span> <span data-ttu-id="e835f-132">Sie können auch die Länge einer bestimmten Zeichenfolge durch die `Length`-Eigenschaft abrufen.</span><span class="sxs-lookup"><span data-stu-id="e835f-132">You can also get the length of a particular string through the `Length` property.</span></span> <span data-ttu-id="e835f-133">Wenn Sie mehrere Bearbeitungen hinsichtlich des Arraytyps an einer Zeichenfolge durchführen müssen, können Sie sie in ein Array von `Char`-Instanzen mit der `ToCharArray`-Funktion der Zeichenfolge konvertieren.</span><span class="sxs-lookup"><span data-stu-id="e835f-133">If you need to perform multiple array-type manipulations on a string, you can convert it to an array of `Char` instances using the `ToCharArray` function of the string.</span></span> <span data-ttu-id="e835f-134">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e835f-134">For example:</span></span>  
  
 <span data-ttu-id="e835f-135">[!code-vb[VbVbalrStrings&#68;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="e835f-135">[!code-vb[VbVbalrStrings#68](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_6.vb)]</span></span>  
  
 <span data-ttu-id="e835f-136">Die Variable `myArray` enthält jetzt ein Array von `Char`-Werten, die jeweils ein Zeichen aus `myString` darstellen.</span><span class="sxs-lookup"><span data-stu-id="e835f-136">The variable `myArray` now contains an array of `Char` values, each representing a character from `myString`.</span></span>  
  
## <a name="the-immutability-of-strings"></a><span data-ttu-id="e835f-137">Die Unveränderlichkeit von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="e835f-137">The Immutability of Strings</span></span>  
 <span data-ttu-id="e835f-138">Eine Zeichenfolge ist *unveränderliche*, d. h. der Wert nicht werden, wenn geändert kann es erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e835f-138">A string is *immutable*, which means its value cannot be changed once it has been created.</span></span> <span data-ttu-id="e835f-139">Sie können einer Zeichenfolgenvariablen trotzdem mehr als einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e835f-139">However, this does not prevent you from assigning more than one value to a string variable.</span></span> <span data-ttu-id="e835f-140">Betrachten Sie das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e835f-140">Consider the following example:</span></span>  
  
 <span data-ttu-id="e835f-141">[!code-vb[VbVbalrStrings&#69;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="e835f-141">[!code-vb[VbVbalrStrings#69](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_7.vb)]</span></span>  
  
 <span data-ttu-id="e835f-142">Hier wird eine Zeichenfolgenvariable erstellt, ein Wert zugewiesen, und dann wird der Wert geändert.</span><span class="sxs-lookup"><span data-stu-id="e835f-142">Here, a string variable is created, given a value, and then its value is changed.</span></span>  
  
 <span data-ttu-id="e835f-143">Genauer gesagt wird in der ersten Zeile eine Instanz des Typs `String` erstellt und der Wert `This string is immutable` zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="e835f-143">More specifically, in the first line, an instance of type `String` is created and given the value `This string is immutable`.</span></span> <span data-ttu-id="e835f-144">In der zweiten Zeile des Beispiels wird eine neue Instanz erstellt und der Wert `Or is it?` zugewiesen. Die Zeichenfolgenvariable verwirft den Verweis auf die erste Instanz und speichert einen Verweis auf die neue Instanz.</span><span class="sxs-lookup"><span data-stu-id="e835f-144">In the second line of the example, a new instance is created and given the value `Or is it?`, and the string variable discards its reference to the first instance and stores a reference to the new instance.</span></span>  
  
 <span data-ttu-id="e835f-145">Im Gegensatz zu anderen systeminternen Datentypen ist `String` ein Verweistyp.</span><span class="sxs-lookup"><span data-stu-id="e835f-145">Unlike other intrinsic data types, `String` is a reference type.</span></span> <span data-ttu-id="e835f-146">Wenn eine Variable des Verweistyps als Argument an eine Funktion oder Unterroutine übergeben wird, wird ein Verweis auf die Speicheradresse, wo die Daten gespeichert werden, anstelle des tatsächlichen Werts der Zeichenfolge übergeben.</span><span class="sxs-lookup"><span data-stu-id="e835f-146">When a variable of reference type is passed as an argument to a function or subroutine, a reference to the memory address where the data is stored is passed instead of the actual value of the string.</span></span> <span data-ttu-id="e835f-147">Damit bleibt der Name der Variable im vorherigen Beispiel gleich, aber es wird auf eine neue und andere Instanz der `String`-Klasse verwiesen, die den neuen Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="e835f-147">So in the previous example, the name of the variable remains the same, but it points to a new and different instance of the `String` class, which holds the new value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e835f-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e835f-148">See Also</span></span>  
 <span data-ttu-id="e835f-149">[Einführung in Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md) </span><span class="sxs-lookup"><span data-stu-id="e835f-149">[Introduction to Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md) </span></span>  
<span data-ttu-id="e835f-150"> [String-Datentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="e835f-150"> [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) </span></span>  
<span data-ttu-id="e835f-151"> [Char-Datentyp](../../../../visual-basic/language-reference/data-types/char-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="e835f-151"> [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md) </span></span>  
<span data-ttu-id="e835f-152"> [Grundlegende Zeichenfolgenoperationen](http://msdn.microsoft.com/library/8133d357-90b5-4b62-9927-43323d99b6b6)</span><span class="sxs-lookup"><span data-stu-id="e835f-152"> [Basic String Operations](http://msdn.microsoft.com/library/8133d357-90b5-4b62-9927-43323d99b6b6)</span></span>
