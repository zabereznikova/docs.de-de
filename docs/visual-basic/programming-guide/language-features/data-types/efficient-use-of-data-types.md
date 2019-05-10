---
title: Effiziente Verwendung von Datentypen (Visual Basic)
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
ms.openlocfilehash: f85acfe7592d7b90423107e0d45bb007fce5f4a8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64601155"
---
# <a name="efficient-use-of-data-types-visual-basic"></a><span data-ttu-id="2b5f4-102">Effiziente Verwendung von Datentypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b5f4-102">Efficient Use of Data Types (Visual Basic)</span></span>
<span data-ttu-id="2b5f4-103">Nicht deklarierte Variablen und Variablen, die ohne einen Datentyp zugewiesen sind die `Object` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="2b5f4-103">Undeclared variables and variables declared without a data type are assigned the `Object` data type.</span></span> <span data-ttu-id="2b5f4-104">Dies erleichtert es, Programme zu schreiben, schnell, aber es kann dazu führen, dass sie langsamer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2b5f4-104">This makes it easy to write programs quickly, but it can cause them to execute more slowly.</span></span>  
  
## <a name="strong-typing"></a><span data-ttu-id="2b5f4-105">Starke Typisierung</span><span class="sxs-lookup"><span data-stu-id="2b5f4-105">Strong Typing</span></span>  
 <span data-ttu-id="2b5f4-106">Die Angabe von Datentypen für alle Variablen wird bezeichnet als *starke Typisierung*.</span><span class="sxs-lookup"><span data-stu-id="2b5f4-106">Specifying data types for all your variables is known as *strong typing*.</span></span> <span data-ttu-id="2b5f4-107">Mit starker Typisierung hat mehrere Vorteile:</span><span class="sxs-lookup"><span data-stu-id="2b5f4-107">Using strong typing has several advantages:</span></span>  
  
- <span data-ttu-id="2b5f4-108">Sie können IntelliSense-Unterstützung für Variablen.</span><span class="sxs-lookup"><span data-stu-id="2b5f4-108">It enables IntelliSense support for your variables.</span></span> <span data-ttu-id="2b5f4-109">Dadurch können Sie die Eigenschaften und andere Member anzeigen, während der Eingabe im Code.</span><span class="sxs-lookup"><span data-stu-id="2b5f4-109">This allows you to see their properties and other members as you type in the code.</span></span>  
  
- <span data-ttu-id="2b5f4-110">Es nutzt die Vorteile der typüberprüfung zur Compiler.</span><span class="sxs-lookup"><span data-stu-id="2b5f4-110">It takes advantage of compiler type checking.</span></span> <span data-ttu-id="2b5f4-111">Anweisungen, die zur Laufzeit aufgrund von Fehlern wie z. B. Überlauf möglich abzufangen.</span><span class="sxs-lookup"><span data-stu-id="2b5f4-111">This catches statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="2b5f4-112">Es fängt auch Aufrufe von Methoden für Objekte, die diese nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="2b5f4-112">It also catches calls to methods on objects that do not support them.</span></span>  
  
- <span data-ttu-id="2b5f4-113">Es führt zu einer schnelleren Ausführung Ihres Codes.</span><span class="sxs-lookup"><span data-stu-id="2b5f4-113">It results in faster execution of your code.</span></span>  
  
## <a name="most-efficient-data-types"></a><span data-ttu-id="2b5f4-114">Die effizienteste-Datentypen</span><span class="sxs-lookup"><span data-stu-id="2b5f4-114">Most Efficient Data Types</span></span>  
 <span data-ttu-id="2b5f4-115">Für Variablen, die niemals Bruchzahlen enthalten, werden die ganzzahligen Datentypen effizienter als die nicht ganzzahligen Typen.</span><span class="sxs-lookup"><span data-stu-id="2b5f4-115">For variables that never contain fractions, the integral data types are more efficient than the nonintegral types.</span></span> <span data-ttu-id="2b5f4-116">In Visual Basic `Integer` und `UInteger` die effizientesten numerischen Typen sind.</span><span class="sxs-lookup"><span data-stu-id="2b5f4-116">In Visual Basic, `Integer` and `UInteger` are the most efficient numeric types.</span></span>  
  
 <span data-ttu-id="2b5f4-117">Für Bruchzahlen `Double` der effizienteste Datentyp ist, da die Prozessoren auf den aktuellen Plattformen Operationen mit Gleitkommazahlen mit doppelter Genauigkeit ausführen.</span><span class="sxs-lookup"><span data-stu-id="2b5f4-117">For fractional numbers, `Double` is the most efficient data type, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="2b5f4-118">Allerdings Vorgänge mit `Double` sind nicht so schnell wie bei ganzzahligen Typen wie z. B. `Integer`.</span><span class="sxs-lookup"><span data-stu-id="2b5f4-118">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>  
  
## <a name="specifying-data-type"></a><span data-ttu-id="2b5f4-119">Angeben eines Datentyps</span><span class="sxs-lookup"><span data-stu-id="2b5f4-119">Specifying Data Type</span></span>  
 <span data-ttu-id="2b5f4-120">Verwenden der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) zum Deklarieren einer Variablen eines bestimmten Typs.</span><span class="sxs-lookup"><span data-stu-id="2b5f4-120">Use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) to declare a variable of a specific type.</span></span> <span data-ttu-id="2b5f4-121">Können Sie gleichzeitig ihre Zugriffsebene angeben, mit der [öffentliche](../../../../visual-basic/language-reference/modifiers/public.md), [geschützte](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), oder [Private](../../../../visual-basic/language-reference/modifiers/private.md) Schlüsselwort, wie in der folgende Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2b5f4-121">You can simultaneously specify its access level by using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, as in the following example.</span></span>  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a><span data-ttu-id="2b5f4-122">Zeichen-Konvertierung</span><span class="sxs-lookup"><span data-stu-id="2b5f4-122">Character Conversion</span></span>  
 <span data-ttu-id="2b5f4-123">Die `AscW` und `ChrW` Funktionen, die im Unicode-Format verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2b5f4-123">The `AscW` and `ChrW` functions operate in Unicode.</span></span> <span data-ttu-id="2b5f4-124">Verwenden Sie diese vorzuziehen, `Asc` und `Chr`, die müssen in und aus Unicode-übersetzen.</span><span class="sxs-lookup"><span data-stu-id="2b5f4-124">You should use them in preference to `Asc` and `Chr`, which must translate into and out of Unicode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b5f4-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b5f4-125">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="2b5f4-126">Datentypen</span><span class="sxs-lookup"><span data-stu-id="2b5f4-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="2b5f4-127">Numerische Datentypen</span><span class="sxs-lookup"><span data-stu-id="2b5f4-127">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [<span data-ttu-id="2b5f4-128">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="2b5f4-128">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="2b5f4-129">Verwenden von IntelliSense</span><span class="sxs-lookup"><span data-stu-id="2b5f4-129">Using IntelliSense</span></span>](/visualstudio/ide/using-intellisense)
