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
ms.openlocfilehash: 6e71c4e2225bbcde3bb2bd20ae098f5600990051
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647760"
---
# <a name="efficient-use-of-data-types-visual-basic"></a><span data-ttu-id="7d798-102">Effiziente Verwendung von Datentypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d798-102">Efficient Use of Data Types (Visual Basic)</span></span>
<span data-ttu-id="7d798-103">Nicht deklarierte Variablen und Variablen, die ohne ein Datentyp zugewiesen sind die `Object` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="7d798-103">Undeclared variables and variables declared without a data type are assigned the `Object` data type.</span></span> <span data-ttu-id="7d798-104">Dies erleichtert es schnell Programme zu schreiben, aber es kann dazu führen, dass sie langsamer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7d798-104">This makes it easy to write programs quickly, but it can cause them to execute more slowly.</span></span>  
  
## <a name="strong-typing"></a><span data-ttu-id="7d798-105">Starke Typisierung</span><span class="sxs-lookup"><span data-stu-id="7d798-105">Strong Typing</span></span>  
 <span data-ttu-id="7d798-106">Das Festlegen von Datentypen für alle Variablen wird bezeichnet als *starke Typisierung*.</span><span class="sxs-lookup"><span data-stu-id="7d798-106">Specifying data types for all your variables is known as *strong typing*.</span></span> <span data-ttu-id="7d798-107">Mit starker Typisierung hat mehrere Vorteile:</span><span class="sxs-lookup"><span data-stu-id="7d798-107">Using strong typing has several advantages:</span></span>  
  
-   <span data-ttu-id="7d798-108">Dadurch werden IntelliSense-Unterstützung für Variablen.</span><span class="sxs-lookup"><span data-stu-id="7d798-108">It enables IntelliSense support for your variables.</span></span> <span data-ttu-id="7d798-109">Dadurch können Sie ihre Eigenschaften und andere Elemente anzeigen, während der Eingabe im Code.</span><span class="sxs-lookup"><span data-stu-id="7d798-109">This allows you to see their properties and other members as you type in the code.</span></span>  
  
-   <span data-ttu-id="7d798-110">Es nutzt die Vorteile der typüberprüfung Compiler.</span><span class="sxs-lookup"><span data-stu-id="7d798-110">It takes advantage of compiler type checking.</span></span> <span data-ttu-id="7d798-111">Anweisungen, die zur Laufzeit aufgrund von Fehlern, z. B. Überlauf fehlschlagen können abzufangen.</span><span class="sxs-lookup"><span data-stu-id="7d798-111">This catches statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="7d798-112">Auch fängt Sie Aufrufe von Methoden für Objekte, die sie unterstützen.</span><span class="sxs-lookup"><span data-stu-id="7d798-112">It also catches calls to methods on objects that do not support them.</span></span>  
  
-   <span data-ttu-id="7d798-113">Es führt zu einer schnelleren Ausführung des Codes.</span><span class="sxs-lookup"><span data-stu-id="7d798-113">It results in faster execution of your code.</span></span>  
  
## <a name="most-efficient-data-types"></a><span data-ttu-id="7d798-114">Die effizienteste-Datentypen</span><span class="sxs-lookup"><span data-stu-id="7d798-114">Most Efficient Data Types</span></span>  
 <span data-ttu-id="7d798-115">Für Variablen, die nie Addieren von Brüchen enthalten, sind die ganzzahlige Datentypen effizienter als die nicht ganzzahligen Typen.</span><span class="sxs-lookup"><span data-stu-id="7d798-115">For variables that never contain fractions, the integral data types are more efficient than the nonintegral types.</span></span> <span data-ttu-id="7d798-116">In Visual Basic `Integer` und `UInteger` sind die effizientesten numerischen Typen.</span><span class="sxs-lookup"><span data-stu-id="7d798-116">In Visual Basic, `Integer` and `UInteger` are the most efficient numeric types.</span></span>  
  
 <span data-ttu-id="7d798-117">Bei Bruchzahlen `Double` ist der effizienteste Datentyp aus, da die Prozessoren auf den aktuellen Plattformen Operationen mit Gleitkommazahlen mit doppelter Genauigkeit ausführen.</span><span class="sxs-lookup"><span data-stu-id="7d798-117">For fractional numbers, `Double` is the most efficient data type, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="7d798-118">Allerdings Vorgänge mit `Double` sind nicht so schnell wie bei ganzzahligen Typen wie z. B. `Integer`.</span><span class="sxs-lookup"><span data-stu-id="7d798-118">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>  
  
## <a name="specifying-data-type"></a><span data-ttu-id="7d798-119">Angeben eines Datentyps</span><span class="sxs-lookup"><span data-stu-id="7d798-119">Specifying Data Type</span></span>  
 <span data-ttu-id="7d798-120">Verwenden der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) zum Deklarieren einer Variablen eines bestimmten Typs.</span><span class="sxs-lookup"><span data-stu-id="7d798-120">Use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) to declare a variable of a specific type.</span></span> <span data-ttu-id="7d798-121">Gleichzeitig können Sie ihre Zugriffsebene angeben, mit der [öffentlichen](../../../../visual-basic/language-reference/modifiers/public.md), [geschützte](../../../../visual-basic/language-reference/modifiers/protected.md), ["Friend"](../../../../visual-basic/language-reference/modifiers/friend.md), oder [Private](../../../../visual-basic/language-reference/modifiers/private.md) Schlüsselworts, wie in der folgende.</span><span class="sxs-lookup"><span data-stu-id="7d798-121">You can simultaneously specify its access level by using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, as in the following example.</span></span>  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a><span data-ttu-id="7d798-122">Zeichen-Konvertierung</span><span class="sxs-lookup"><span data-stu-id="7d798-122">Character Conversion</span></span>  
 <span data-ttu-id="7d798-123">Die `AscW` und `ChrW` Funktionen, die im Unicode-Format ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7d798-123">The `AscW` and `ChrW` functions operate in Unicode.</span></span> <span data-ttu-id="7d798-124">Verwenden Sie diese vorzuziehen, `Asc` und `Chr`, müssen die in und aus Unicode übersetzen.</span><span class="sxs-lookup"><span data-stu-id="7d798-124">You should use them in preference to `Asc` and `Chr`, which must translate into and out of Unicode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d798-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d798-125">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 [<span data-ttu-id="7d798-126">Datentypen</span><span class="sxs-lookup"><span data-stu-id="7d798-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="7d798-127">Numerische Datentypen</span><span class="sxs-lookup"><span data-stu-id="7d798-127">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [<span data-ttu-id="7d798-128">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="7d798-128">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="7d798-129">Verwenden von IntelliSense</span><span class="sxs-lookup"><span data-stu-id="7d798-129">Using IntelliSense</span></span>](/visualstudio/ide/using-intellisense)
