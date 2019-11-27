---
title: Effiziente Verwendung von Datentypen
ms.date: 07/20/2015
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function [Visual Basic], preferred to Asc
- data types [Visual Basic], using efficiently
- optimization [Visual Basic], data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function [Visual Basic], preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
ms.openlocfilehash: 621dec7537e9c993024e271b96ab8706baf89885
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350108"
---
# <a name="efficient-use-of-data-types-visual-basic"></a><span data-ttu-id="71017-102">Effiziente Verwendung von Datentypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71017-102">Efficient Use of Data Types (Visual Basic)</span></span>
<span data-ttu-id="71017-103">Nicht deklarierte Variablen und Variablen, die ohne Datentyp deklariert werden, wird der `Object`-Datentyp zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="71017-103">Undeclared variables and variables declared without a data type are assigned the `Object` data type.</span></span> <span data-ttu-id="71017-104">Dies vereinfacht das schnelle Schreiben von Programmen, kann jedoch dazu führen, dass Sie langsamer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="71017-104">This makes it easy to write programs quickly, but it can cause them to execute more slowly.</span></span>

## <a name="strong-typing"></a><span data-ttu-id="71017-105">Starke Typisierung</span><span class="sxs-lookup"><span data-stu-id="71017-105">Strong Typing</span></span>
 <span data-ttu-id="71017-106">Das Angeben von Datentypen für alle Variablen wird als *starke Typisierung*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="71017-106">Specifying data types for all your variables is known as *strong typing*.</span></span> <span data-ttu-id="71017-107">Die Verwendung der starken Typisierung bietet mehrere Vorteile:</span><span class="sxs-lookup"><span data-stu-id="71017-107">Using strong typing has several advantages:</span></span>

- <span data-ttu-id="71017-108">Sie ermöglicht die IntelliSense-Unterstützung für die Variablen.</span><span class="sxs-lookup"><span data-stu-id="71017-108">It enables IntelliSense support for your variables.</span></span> <span data-ttu-id="71017-109">Dies ermöglicht es Ihnen, ihre Eigenschaften und andere Member anzuzeigen, während Sie den Code eingeben.</span><span class="sxs-lookup"><span data-stu-id="71017-109">This allows you to see their properties and other members as you type in the code.</span></span>

- <span data-ttu-id="71017-110">Es nutzt die Compilertypüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="71017-110">It takes advantage of compiler type checking.</span></span> <span data-ttu-id="71017-111">Dadurch werden Anweisungen abgefangen, die zur Laufzeit aufgrund von Fehlern wie einem Überlauf fehlschlagen können.</span><span class="sxs-lookup"><span data-stu-id="71017-111">This catches statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="71017-112">Sie fängt auch Aufrufe von Methoden für Objekte ab, die Sie nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="71017-112">It also catches calls to methods on objects that do not support them.</span></span>

- <span data-ttu-id="71017-113">Dies führt zu einer schnelleren Ausführung des Codes.</span><span class="sxs-lookup"><span data-stu-id="71017-113">It results in faster execution of your code.</span></span>

## <a name="most-efficient-data-types"></a><span data-ttu-id="71017-114">Effizienteste Datentypen</span><span class="sxs-lookup"><span data-stu-id="71017-114">Most Efficient Data Types</span></span>
 <span data-ttu-id="71017-115">Für Variablen, die niemals Bruchteile enthalten, sind die ganzzahligen Datentypen effizienter als die nicht ganzzahligen Typen.</span><span class="sxs-lookup"><span data-stu-id="71017-115">For variables that never contain fractions, the integral data types are more efficient than the nonintegral types.</span></span> <span data-ttu-id="71017-116">In Visual Basic sind `Integer` und `UInteger` die effizientesten numerischen Typen.</span><span class="sxs-lookup"><span data-stu-id="71017-116">In Visual Basic, `Integer` and `UInteger` are the most efficient numeric types.</span></span>

 <span data-ttu-id="71017-117">Bei Bruchzahlen ist `Double` der effizienteste Datentyp, da die Prozessoren auf aktuellen Plattformen Gleit Komma Vorgänge mit doppelter Genauigkeit ausführen.</span><span class="sxs-lookup"><span data-stu-id="71017-117">For fractional numbers, `Double` is the most efficient data type, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="71017-118">Vorgänge mit `Double` sind jedoch nicht so schnell wie bei den ganzzahligen Typen wie `Integer`.</span><span class="sxs-lookup"><span data-stu-id="71017-118">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>

## <a name="specifying-data-type"></a><span data-ttu-id="71017-119">Angeben von Datentyp</span><span class="sxs-lookup"><span data-stu-id="71017-119">Specifying Data Type</span></span>
 <span data-ttu-id="71017-120">Verwenden Sie die [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) , um eine Variable eines bestimmten Typs zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="71017-120">Use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) to declare a variable of a specific type.</span></span> <span data-ttu-id="71017-121">Sie können die Zugriffsebene gleichzeitig mithilfe des Schlüssel Worts [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)oder [private](../../../../visual-basic/language-reference/modifiers/private.md) angeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="71017-121">You can simultaneously specify its access level by using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, as in the following example.</span></span>

```vb
Private x As Double
Protected s As String
```

## <a name="character-conversion"></a><span data-ttu-id="71017-122">Zeichen Konvertierung</span><span class="sxs-lookup"><span data-stu-id="71017-122">Character Conversion</span></span>
 <span data-ttu-id="71017-123">Die Funktionen `AscW` und `ChrW` funktionieren in Unicode.</span><span class="sxs-lookup"><span data-stu-id="71017-123">The `AscW` and `ChrW` functions operate in Unicode.</span></span> <span data-ttu-id="71017-124">Sie sollten diese bevorzugt für `Asc` und `Chr`verwenden, die in und aus Unicode übersetzt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="71017-124">You should use them in preference to `Asc` and `Chr`, which must translate into and out of Unicode.</span></span>

## <a name="see-also"></a><span data-ttu-id="71017-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71017-125">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="71017-126">Datentypen</span><span class="sxs-lookup"><span data-stu-id="71017-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="71017-127">Numerische Datentypen</span><span class="sxs-lookup"><span data-stu-id="71017-127">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [<span data-ttu-id="71017-128">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="71017-128">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="71017-129">Verwenden von IntelliSense</span><span class="sxs-lookup"><span data-stu-id="71017-129">Using IntelliSense</span></span>](/visualstudio/ide/using-intellisense)
