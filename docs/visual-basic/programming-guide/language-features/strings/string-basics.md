---
title: Grundlagen zu Zeichenfolgen
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Like operator
- strings [Visual Basic], Visual Basic
- strings [Visual Basic], regular expressions
ms.assetid: 5674418d-f00d-4f72-9f98-d15897793350
ms.openlocfilehash: 44736f4db9977d9f69a0571cc80fa327dcf96581
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072508"
---
# <a name="string-basics-in-visual-basic"></a><span data-ttu-id="17091-102">Grundlagen zu Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="17091-102">String Basics in Visual Basic</span></span>

<span data-ttu-id="17091-103">Der `String`-Datentyp stellt eine Reihe von Zeichen dar (wobei jedes Zeichen wiederum eine Instanz des `Char`-Datentyps darstellt).</span><span class="sxs-lookup"><span data-stu-id="17091-103">The `String` data type represents a series of characters (each representing in turn an instance of the `Char` data type).</span></span> <span data-ttu-id="17091-104">In diesem Thema werden die grundlegenden Konzepte von Zeichen folgen in Visual Basic vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="17091-104">This topic introduces the basic concepts of strings in Visual Basic.</span></span>  
  
## <a name="string-variables"></a><span data-ttu-id="17091-105">Zeichenfolgenvariablen</span><span class="sxs-lookup"><span data-stu-id="17091-105">String Variables</span></span>  

 <span data-ttu-id="17091-106">Einer Instanz einer Zeichenfolge kann ein Literalwert zugewiesen werden, der eine Reihe von Zeichen darstellt.</span><span class="sxs-lookup"><span data-stu-id="17091-106">An instance of a string can be assigned a literal value that represents a series of characters.</span></span> <span data-ttu-id="17091-107">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="17091-107">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#63)]  
  
 <span data-ttu-id="17091-108">Eine `String`-Variable kann auch einen beliebigen Ausdruck annehmen, der eine Zeichenfolge ergibt.</span><span class="sxs-lookup"><span data-stu-id="17091-108">A `String` variable can also accept any expression that evaluates to a string.</span></span> <span data-ttu-id="17091-109">Beispiele werden unten gezeigt:</span><span class="sxs-lookup"><span data-stu-id="17091-109">Examples are shown below:</span></span>  
  
 [!code-vb[VbVbalrStrings#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#64)]  
  
 <span data-ttu-id="17091-110">Jedes Literal, das einer `String`-Variable zugewiesen ist, muss in Anführungszeichen eingeschlossen werden („“).</span><span class="sxs-lookup"><span data-stu-id="17091-110">Any literal that is assigned to a `String` variable must be enclosed in quotation marks ("").</span></span> <span data-ttu-id="17091-111">Dies bedeutet, dass ein Anführungszeichen in einer Zeichenfolge nicht durch ein Anführungszeichen dargestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="17091-111">This means that a quotation mark within a string cannot be represented by a quotation mark.</span></span> <span data-ttu-id="17091-112">Beispielsweise verursacht der folgende Code einen Compilerfehler:</span><span class="sxs-lookup"><span data-stu-id="17091-112">For example, the following code causes a compiler error:</span></span>  
  
 [!code-vb[VbVbalrStrings#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#65)]  
  
 <span data-ttu-id="17091-113">Dieser Code verursacht einen Fehler, da der Compiler die Zeichenfolge nach dem zweiten Anführungszeichen beendet, und der Rest der Zeichenfolge wird als Code interpretiert.</span><span class="sxs-lookup"><span data-stu-id="17091-113">This code causes an error because the compiler terminates the string after the second quotation mark, and the remainder of the string is interpreted as code.</span></span> <span data-ttu-id="17091-114">Um dieses Problem zu beheben, interpretiert Visual Basic zwei Anführungszeichen in einem zeichenfolgenliteralformat als ein Anführungszeichen in der Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="17091-114">To solve this problem, Visual Basic interprets two quotation marks in a string literal as one quotation mark in the string.</span></span> <span data-ttu-id="17091-115">Das folgende Beispiel zeigt die korrekte Methode zum Einschließen eines Anführungszeichens in eine Zeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="17091-115">The following example demonstrates the correct way to include a quotation mark in a string:</span></span>  
  
 [!code-vb[VbVbalrStrings#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#66)]  
  
 <span data-ttu-id="17091-116">Im vorherigen Beispiel werden die beiden Anführungszeichen, die vor dem Wort `Look` vorhanden sind, zu einem Anführungszeichen in der Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="17091-116">In the preceding example, the two quotation marks preceding the word `Look` become one quotation mark in the string.</span></span> <span data-ttu-id="17091-117">Die drei Anführungszeichen am Ende der Zeile stellen ein Anführungszeichen in der Zeichenfolge und das Abschlusszeichen der Zeichenfolge dar.</span><span class="sxs-lookup"><span data-stu-id="17091-117">The three quotation marks at the end of the line represent one quotation mark in the string and the string termination character.</span></span>  
  
 <span data-ttu-id="17091-118">Zeichenfolgenliterale können mehrere Zeilen enthalten:</span><span class="sxs-lookup"><span data-stu-id="17091-118">String literals can contain multiple lines:</span></span>  
  
```vb  
Dim x = "hello  
world"  
```  
  
 <span data-ttu-id="17091-119">Die resultierende Zeichenfolge enthält Zeilenumbruchsequenzen, die Sie in Ihrem Zeichenfolgenliteral (vbcr, vbcrlf usw.) verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="17091-119">The resulting string contains newline sequences that you used in your string literal (vbcr, vbcrlf, etc.).</span></span>  <span data-ttu-id="17091-120">Sie müssen nicht mehr die bisherige Problemumgehung verwenden:</span><span class="sxs-lookup"><span data-stu-id="17091-120">You no longer need to use the old workaround:</span></span>  
  
```vb  
Dim x = <xml><![CDATA[Hello  
World]]></xml>.Value  
```  
  
## <a name="characters-in-strings"></a><span data-ttu-id="17091-121">Zeichen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="17091-121">Characters in Strings</span></span>  

 <span data-ttu-id="17091-122">Eine Zeichenfolge kann als eine Reihe von `Char`-Werten betrachtet werden, und der `String`-Typ verfügt über integrierte Funktionen, mit denen Sie zahlreiche Bearbeitungen an einer Zeichenfolge vornehmen können, die den durch Arrays zulässigen Bearbeitungen ähneln.</span><span class="sxs-lookup"><span data-stu-id="17091-122">A string can be thought of as a series of `Char` values, and the `String` type has built-in functions that allow you to perform many manipulations on a string that resemble the manipulations allowed by arrays.</span></span> <span data-ttu-id="17091-123">Wie bei allen Arrays in .NET Framework handelt es sich hierbei um null basierte Arrays.</span><span class="sxs-lookup"><span data-stu-id="17091-123">Like all array in .NET Framework, these are zero-based arrays.</span></span> <span data-ttu-id="17091-124">Sie möchten möglicherweise auf ein bestimmtes Zeichen in einer Zeichenfolge durch die `Chars`-Eigenschaft verweisen, die eine Möglichkeit bietet, auf ein Zeichen durch die Position zuzugreifen, in der es in der Zeichenfolge auftritt.</span><span class="sxs-lookup"><span data-stu-id="17091-124">You may refer to a specific character in a string through the `Chars` property, which provides a way to access a character by the position in which it appears in the string.</span></span> <span data-ttu-id="17091-125">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="17091-125">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#67)]  
  
 <span data-ttu-id="17091-126">Im obigen Beispiel gibt die `Chars`-Eigenschaft der Zeichenfolge das vierte Zeichen in der Zeichenfolge zurück, wobei es sich um `D` handelt, und weist dieses `myChar` zu.</span><span class="sxs-lookup"><span data-stu-id="17091-126">In the above example, the `Chars` property of the string returns the fourth character in the string, which is `D`, and assigns it to `myChar`.</span></span> <span data-ttu-id="17091-127">Sie können auch die Länge einer bestimmten Zeichenfolge durch die `Length`-Eigenschaft abrufen.</span><span class="sxs-lookup"><span data-stu-id="17091-127">You can also get the length of a particular string through the `Length` property.</span></span> <span data-ttu-id="17091-128">Wenn Sie mehrere Bearbeitungen hinsichtlich des Arraytyps an einer Zeichenfolge durchführen müssen, können Sie sie in ein Array von `Char`-Instanzen mit der `ToCharArray`-Funktion der Zeichenfolge konvertieren.</span><span class="sxs-lookup"><span data-stu-id="17091-128">If you need to perform multiple array-type manipulations on a string, you can convert it to an array of `Char` instances using the `ToCharArray` function of the string.</span></span> <span data-ttu-id="17091-129">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="17091-129">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#68)]  
  
 <span data-ttu-id="17091-130">Die Variable `myArray` enthält jetzt ein Array von `Char`-Werten, die jeweils ein Zeichen aus `myString` darstellen.</span><span class="sxs-lookup"><span data-stu-id="17091-130">The variable `myArray` now contains an array of `Char` values, each representing a character from `myString`.</span></span>  
  
## <a name="the-immutability-of-strings"></a><span data-ttu-id="17091-131">Die Unveränderlichkeit von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="17091-131">The Immutability of Strings</span></span>  

 <span data-ttu-id="17091-132">Eine Zeichenfolge ist *unveränderlich*, was bedeutet, dass der Wert nicht geändert werden kann, nachdem er erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="17091-132">A string is *immutable*, which means its value cannot be changed once it has been created.</span></span> <span data-ttu-id="17091-133">Sie können einer Zeichenfolgenvariablen trotzdem mehr als einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="17091-133">However, this does not prevent you from assigning more than one value to a string variable.</span></span> <span data-ttu-id="17091-134">Betrachten Sie das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="17091-134">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#69)]  
  
 <span data-ttu-id="17091-135">Hier wird eine Zeichenfolgenvariable erstellt, ein Wert zugewiesen, und dann wird der Wert geändert.</span><span class="sxs-lookup"><span data-stu-id="17091-135">Here, a string variable is created, given a value, and then its value is changed.</span></span>  
  
 <span data-ttu-id="17091-136">Genauer gesagt wird in der ersten Zeile eine Instanz des Typs `String` erstellt und der Wert `This string is immutable` zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="17091-136">More specifically, in the first line, an instance of type `String` is created and given the value `This string is immutable`.</span></span> <span data-ttu-id="17091-137">In der zweiten Zeile des Beispiels wird eine neue Instanz erstellt und der Wert `Or is it?` zugewiesen. Die Zeichenfolgenvariable verwirft den Verweis auf die erste Instanz und speichert einen Verweis auf die neue Instanz.</span><span class="sxs-lookup"><span data-stu-id="17091-137">In the second line of the example, a new instance is created and given the value `Or is it?`, and the string variable discards its reference to the first instance and stores a reference to the new instance.</span></span>  
  
 <span data-ttu-id="17091-138">Im Gegensatz zu anderen systeminternen Datentypen ist `String` ein Verweistyp.</span><span class="sxs-lookup"><span data-stu-id="17091-138">Unlike other intrinsic data types, `String` is a reference type.</span></span> <span data-ttu-id="17091-139">Wenn eine Variable des Verweistyps als Argument an eine Funktion oder Unterroutine übergeben wird, wird ein Verweis auf die Speicheradresse, wo die Daten gespeichert werden, anstelle des tatsächlichen Werts der Zeichenfolge übergeben.</span><span class="sxs-lookup"><span data-stu-id="17091-139">When a variable of reference type is passed as an argument to a function or subroutine, a reference to the memory address where the data is stored is passed instead of the actual value of the string.</span></span> <span data-ttu-id="17091-140">Damit bleibt der Name der Variable im vorherigen Beispiel gleich, aber es wird auf eine neue und andere Instanz der `String`-Klasse verwiesen, die den neuen Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="17091-140">So in the previous example, the name of the variable remains the same, but it points to a new and different instance of the `String` class, which holds the new value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17091-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17091-141">See also</span></span>

- [<span data-ttu-id="17091-142">Einführung in Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="17091-142">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
- [<span data-ttu-id="17091-143">String-Datentyp</span><span class="sxs-lookup"><span data-stu-id="17091-143">String Data Type</span></span>](../../../language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="17091-144">Char-Datentyp</span><span class="sxs-lookup"><span data-stu-id="17091-144">Char Data Type</span></span>](../../../language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="17091-145">Grundlegende Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="17091-145">Basic String Operations</span></span>](../../../../standard/base-types/basic-string-operations.md)
