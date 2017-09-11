---
title: Effiziente Verwendung von Datentypen (Visual Basic) | Microsoft-Dokumentation
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
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function, preferred to Asc
- data types [Visual Basic], using efficiently
- optimization, data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function, preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
caps.latest.revision: 16
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
ms.openlocfilehash: ca8d5885aea12a3f1f9cb35f08bf63c1a89e7ebc
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="efficient-use-of-data-types-visual-basic"></a><span data-ttu-id="96dca-102">Effiziente Verwendung von Datentypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96dca-102">Efficient Use of Data Types (Visual Basic)</span></span>
<span data-ttu-id="96dca-103">Nicht deklarierte Variablen und Variablen, die ohne einen Datentyp zugewiesen sind die `Object` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="96dca-103">Undeclared variables and variables declared without a data type are assigned the `Object` data type.</span></span> <span data-ttu-id="96dca-104">Ganz einfach, schnell Programme zu schreiben, aber es kann dazu führen, dass sie langsamer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="96dca-104">This makes it easy to write programs quickly, but it can cause them to execute more slowly.</span></span>  
  
## <a name="strong-typing"></a><span data-ttu-id="96dca-105">Starke Typisierung</span><span class="sxs-lookup"><span data-stu-id="96dca-105">Strong Typing</span></span>  
 <span data-ttu-id="96dca-106">Die Angabe von Datentypen für alle Variablen wird als bezeichnet *starke Typisierung*.</span><span class="sxs-lookup"><span data-stu-id="96dca-106">Specifying data types for all your variables is known as *strong typing*.</span></span> <span data-ttu-id="96dca-107">Mit starker Typisierung hat mehrere Vorteile:</span><span class="sxs-lookup"><span data-stu-id="96dca-107">Using strong typing has several advantages:</span></span>  
  
-   <span data-ttu-id="96dca-108">Sie können IntelliSense-Unterstützung für Variablen.</span><span class="sxs-lookup"><span data-stu-id="96dca-108">It enables IntelliSense support for your variables.</span></span> <span data-ttu-id="96dca-109">Dadurch können Sie die Eigenschaften und andere Member finden Sie unter während der Eingabe im Code.</span><span class="sxs-lookup"><span data-stu-id="96dca-109">This allows you to see their properties and other members as you type in the code.</span></span>  
  
-   <span data-ttu-id="96dca-110">Nutzt die Vorteile der Compiler Typ überprüft.</span><span class="sxs-lookup"><span data-stu-id="96dca-110">It takes advantage of compiler type checking.</span></span> <span data-ttu-id="96dca-111">Anweisungen, die zur Laufzeit aufgrund von Fehlern, z. B. Überlauf fehlschlagen können abzufangen.</span><span class="sxs-lookup"><span data-stu-id="96dca-111">This catches statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="96dca-112">Es fängt auch Aufrufe von Methoden für Objekte, die diese nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="96dca-112">It also catches calls to methods on objects that do not support them.</span></span>  
  
-   <span data-ttu-id="96dca-113">Schnellere Ausführung des Codes führt.</span><span class="sxs-lookup"><span data-stu-id="96dca-113">It results in faster execution of your code.</span></span>  
  
## <a name="most-efficient-data-types"></a><span data-ttu-id="96dca-114">Die effizientesten Datentypen</span><span class="sxs-lookup"><span data-stu-id="96dca-114">Most Efficient Data Types</span></span>  
 <span data-ttu-id="96dca-115">Für Variablen, die generell keine Nachkommastellen enthalten, sind Ganzzahldatentypen effizienter als die Ganzzahltypen.</span><span class="sxs-lookup"><span data-stu-id="96dca-115">For variables that never contain fractions, the integral data types are more efficient than the nonintegral types.</span></span> <span data-ttu-id="96dca-116">In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], `Integer` und `UInteger` sind die effizientesten numerischen Typen.</span><span class="sxs-lookup"><span data-stu-id="96dca-116">In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], `Integer` and `UInteger` are the most efficient numeric types.</span></span>  
  
 <span data-ttu-id="96dca-117">Bei Bruchzahlen `Double` ist der effizienteste Datentyp, da die Prozessoren auf den aktuellen Plattformen Gleitkommaoperationen mit doppelter Genauigkeit ausführen.</span><span class="sxs-lookup"><span data-stu-id="96dca-117">For fractional numbers, `Double` is the most efficient data type, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="96dca-118">Allerdings Vorgänge mit `Double` sind nicht so schnell wie bei ganzzahligen Typen wie z. B. `Integer`.</span><span class="sxs-lookup"><span data-stu-id="96dca-118">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>  
  
## <a name="specifying-data-type"></a><span data-ttu-id="96dca-119">Angeben eines Datentyps</span><span class="sxs-lookup"><span data-stu-id="96dca-119">Specifying Data Type</span></span>  
 <span data-ttu-id="96dca-120">Verwenden der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) zum Deklarieren einer Variablen eines bestimmten Typs.</span><span class="sxs-lookup"><span data-stu-id="96dca-120">Use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) to declare a variable of a specific type.</span></span> <span data-ttu-id="96dca-121">Sie können die Zugriffsebene gleichzeitig angeben, mit der [öffentlichen](../../../../visual-basic/language-reference/modifiers/public.md), [geschützt](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), oder [Private](../../../../visual-basic/language-reference/modifiers/private.md) -Schlüsselwort, wie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="96dca-121">You can simultaneously specify its access level by using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, as in the following example.</span></span>  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a><span data-ttu-id="96dca-122">Zeichen-Konvertierung</span><span class="sxs-lookup"><span data-stu-id="96dca-122">Character Conversion</span></span>  
 <span data-ttu-id="96dca-123">Die `AscW` und `ChrW` Funktionen werden in Unicode.</span><span class="sxs-lookup"><span data-stu-id="96dca-123">The `AscW` and `ChrW` functions operate in Unicode.</span></span> <span data-ttu-id="96dca-124">Verwenden Sie diese den Vorzug `Asc` und `Chr`, die in und aus Unicode übersetzen.</span><span class="sxs-lookup"><span data-stu-id="96dca-124">You should use them in preference to `Asc` and `Chr`, which must translate into and out of Unicode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96dca-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96dca-125">See Also</span></span>  
 <span data-ttu-id="96dca-126"><xref:Microsoft.VisualBasic.Strings.Asc%2A></xref:Microsoft.VisualBasic.Strings.Asc%2A></span><span class="sxs-lookup"><span data-stu-id="96dca-126"><xref:Microsoft.VisualBasic.Strings.Asc%2A></span></span>   
 <span data-ttu-id="96dca-127"><xref:Microsoft.VisualBasic.Strings.AscW%2A></xref:Microsoft.VisualBasic.Strings.AscW%2A></span><span class="sxs-lookup"><span data-stu-id="96dca-127"><xref:Microsoft.VisualBasic.Strings.AscW%2A></span></span>   
 <span data-ttu-id="96dca-128"><xref:Microsoft.VisualBasic.Strings.Chr%2A></xref:Microsoft.VisualBasic.Strings.Chr%2A></span><span class="sxs-lookup"><span data-stu-id="96dca-128"><xref:Microsoft.VisualBasic.Strings.Chr%2A></span></span>   
 <span data-ttu-id="96dca-129"><xref:Microsoft.VisualBasic.Strings.ChrW%2A></xref:Microsoft.VisualBasic.Strings.ChrW%2A></span><span class="sxs-lookup"><span data-stu-id="96dca-129"><xref:Microsoft.VisualBasic.Strings.ChrW%2A></span></span>   
<span data-ttu-id="96dca-130"> [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="96dca-130"> [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="96dca-131"> [Numerische Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="96dca-131"> [Numeric Data Types](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md) </span></span>  
<span data-ttu-id="96dca-132"> [Deklaration von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="96dca-132"> [Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
<span data-ttu-id="96dca-133"> [Verwenden von IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense)</span><span class="sxs-lookup"><span data-stu-id="96dca-133"> [Using IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense)</span></span>
