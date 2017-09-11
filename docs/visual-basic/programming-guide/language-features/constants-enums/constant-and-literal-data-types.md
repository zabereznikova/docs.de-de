---
title: Konstanten und Literale Datentypen (Visual Basic) | Microsoft-Dokumentation
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
- declaring constants, literal data types
- data types [Visual Basic], declaring
- constants, declaring
- explicit declarations
- literals, coercing data type
- declarations, data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
caps.latest.revision: 19
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
ms.openlocfilehash: 29a997ee0dd847e8505d1a5c24cacfdfdb0a42cc
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="constant-and-literal-data-types-visual-basic"></a><span data-ttu-id="8bcc8-102">Konstanten und literale Datentypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8bcc8-102">Constant and Literal Data Types (Visual Basic)</span></span>
<span data-ttu-id="8bcc8-103">Ein Literal ist ein Wert, der als selbst und nicht als Wert einer Variablen oder das Ergebnis eines Ausdrucks, z. B. die Zahl 3 oder die Zeichenfolge "Hello" ausgedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="8bcc8-103">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span></span> <span data-ttu-id="8bcc8-104">Eine Konstante ist ein aussagekräftiger Name, der anstelle eines Literals und behält diese denselben Wert in der gesamten Anwendung, im Gegensatz zu einer Variablen, deren Wert sich ändern kann.</span><span class="sxs-lookup"><span data-stu-id="8bcc8-104">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span></span>  
  
 <span data-ttu-id="8bcc8-105">Wenn [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) ist `Off` und [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) ist `On`, müssen Sie alle Konstanten explizit mit einem Datentyp deklarieren.</span><span class="sxs-lookup"><span data-stu-id="8bcc8-105">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span></span> <span data-ttu-id="8bcc8-106">Im folgenden Beispiel der Datentyp des `MyByte` explizit als Datentyp deklariert `Byte`:</span><span class="sxs-lookup"><span data-stu-id="8bcc8-106">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span></span>  
  
 <span data-ttu-id="8bcc8-107">[!code-vb[VbVbalrConstants&#1;](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8bcc8-107">[!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]</span></span>  
  
 <span data-ttu-id="8bcc8-108">Wenn `Option Infer` ist `On` oder `Option Strict` ist `Off`, kann zum Deklarieren von Konstanten ohne Angabe eines Datentyps mit einer `As` Klausel.</span><span class="sxs-lookup"><span data-stu-id="8bcc8-108">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="8bcc8-109">Der Compiler bestimmt den Typ der Konstante vom Typ des Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="8bcc8-109">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="8bcc8-110">Ein numerisches Ganzzahlliteral umgewandelt wird, werden standardmäßig die `Integer` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="8bcc8-110">A numeric integer literal is cast by default to the `Integer` data type.</span></span> <span data-ttu-id="8bcc8-111">Der Standarddatentyp für Gleitkommazahlen lautet `Double`, Schlüsselwörter und `True` und `False` geben einen `Boolean` konstant.</span><span class="sxs-lookup"><span data-stu-id="8bcc8-111">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span></span>  
  
## <a name="literals-and-type-coercion"></a><span data-ttu-id="8bcc8-112">Literale und Typumwandlung</span><span class="sxs-lookup"><span data-stu-id="8bcc8-112">Literals and Type Coercion</span></span>  
 <span data-ttu-id="8bcc8-113">In einigen Fällen empfiehlt es sich um ein Literal in einen bestimmten Datentyp zu erzwingen; z. B. beim Zuweisen einer besonders großen Ganzzahlliteralwert einer Variable vom Typ `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="8bcc8-113">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span></span> <span data-ttu-id="8bcc8-114">Im folgende Beispiel erzeugt einen Fehler:</span><span class="sxs-lookup"><span data-stu-id="8bcc8-114">The following example produces an error:</span></span>  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 <span data-ttu-id="8bcc8-115">Der Fehler resultiert aus der Darstellung des Literals.</span><span class="sxs-lookup"><span data-stu-id="8bcc8-115">The error results from the representation of the literal.</span></span> <span data-ttu-id="8bcc8-116">Die `Decimal` -Datentyp kann einen Wert dieser Größe enthalten das Literal wird implizit als eine `Long`, welche nicht.</span><span class="sxs-lookup"><span data-stu-id="8bcc8-116">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span></span>  
  
 <span data-ttu-id="8bcc8-117">Sie können coerce-Literal in einen bestimmten Datentyp auf zwei Arten: durch ein Typzeichen an sie angehängt oder durch Platzieren innerhalb der einschließenden Zeichen.</span><span class="sxs-lookup"><span data-stu-id="8bcc8-117">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span></span> <span data-ttu-id="8bcc8-118">Ein Typzeichen oder umschließende Zeichen muss unmittelbar vorangehen und/oder das Literal ohne Leerzeichen oder Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="8bcc8-118">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span></span>  
  
 <span data-ttu-id="8bcc8-119">Um des vorherigen Beispiels zu machen, fügen Sie der `D` -Typzeichen das Literal, wodurch es als dargestellt, eine `Decimal`:</span><span class="sxs-lookup"><span data-stu-id="8bcc8-119">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span></span>  
  
 <span data-ttu-id="8bcc8-120">[!code-vb[VbVbalrConstants&#2;](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="8bcc8-120">[!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]</span></span>  
  
 <span data-ttu-id="8bcc8-121">Das folgende Beispiel veranschaulicht die richtige Verwendung von Typzeichen und umschließenden Zeichen:</span><span class="sxs-lookup"><span data-stu-id="8bcc8-121">The following example demonstrates correct usage of type characters and enclosing characters:</span></span>  
  
 <span data-ttu-id="8bcc8-122">[!code-vb[VbVbalrConstants&3;](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="8bcc8-122">[!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]</span></span>  
  
 <span data-ttu-id="8bcc8-123">Die folgende Tabelle zeigt die umschließenden Zeichen und Typzeichen Zeichen in verfügbar [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="8bcc8-123">The following table shows the enclosing characters and type characters available in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
|<span data-ttu-id="8bcc8-124">Datentyp</span><span class="sxs-lookup"><span data-stu-id="8bcc8-124">Data type</span></span>|<span data-ttu-id="8bcc8-125">Zeichen</span><span class="sxs-lookup"><span data-stu-id="8bcc8-125">Enclosing character</span></span>|<span data-ttu-id="8bcc8-126">Angehängtes Typzeichen</span><span class="sxs-lookup"><span data-stu-id="8bcc8-126">Appended type character</span></span>|  
|---|---|---|  
|`Boolean`|<span data-ttu-id="8bcc8-127">(keine)</span><span class="sxs-lookup"><span data-stu-id="8bcc8-127">(none)</span></span>|<span data-ttu-id="8bcc8-128">(keine)</span><span class="sxs-lookup"><span data-stu-id="8bcc8-128">(none)</span></span>|  
|`Byte`|<span data-ttu-id="8bcc8-129">(keine)</span><span class="sxs-lookup"><span data-stu-id="8bcc8-129">(none)</span></span>|<span data-ttu-id="8bcc8-130">(keine)</span><span class="sxs-lookup"><span data-stu-id="8bcc8-130">(none)</span></span>|  
|`Char`|<span data-ttu-id="8bcc8-131">"</span><span class="sxs-lookup"><span data-stu-id="8bcc8-131">"</span></span>|<span data-ttu-id="8bcc8-132">A</span><span class="sxs-lookup"><span data-stu-id="8bcc8-132">C</span></span>|  
|`Date`|#|<span data-ttu-id="8bcc8-133">(keine)</span><span class="sxs-lookup"><span data-stu-id="8bcc8-133">(none)</span></span>|  
|`Decimal`|<span data-ttu-id="8bcc8-134">(keine)</span><span class="sxs-lookup"><span data-stu-id="8bcc8-134">(none)</span></span>|<span data-ttu-id="8bcc8-135">D oder @</span><span class="sxs-lookup"><span data-stu-id="8bcc8-135">D or @</span></span>|  
|`Double`|<span data-ttu-id="8bcc8-136">(keine)</span><span class="sxs-lookup"><span data-stu-id="8bcc8-136">(none)</span></span>|<span data-ttu-id="8bcc8-137">R oder</span><span class="sxs-lookup"><span data-stu-id="8bcc8-137">R or</span></span> #|  
|`Integer`|<span data-ttu-id="8bcc8-138">(keine)</span><span class="sxs-lookup"><span data-stu-id="8bcc8-138">(none)</span></span>|<span data-ttu-id="8bcc8-139">I oder %</span><span class="sxs-lookup"><span data-stu-id="8bcc8-139">I or %</span></span>|  
|`Long`|<span data-ttu-id="8bcc8-140">(keine)</span><span class="sxs-lookup"><span data-stu-id="8bcc8-140">(none)</span></span>|<span data-ttu-id="8bcc8-141">L oder &</span><span class="sxs-lookup"><span data-stu-id="8bcc8-141">L or &</span></span>|  
|`Short`|<span data-ttu-id="8bcc8-142">(keine)</span><span class="sxs-lookup"><span data-stu-id="8bcc8-142">(none)</span></span>|<span data-ttu-id="8bcc8-143">S</span><span class="sxs-lookup"><span data-stu-id="8bcc8-143">S</span></span>|  
|`Single`|<span data-ttu-id="8bcc8-144">(keine)</span><span class="sxs-lookup"><span data-stu-id="8bcc8-144">(none)</span></span>|<span data-ttu-id="8bcc8-145">F oder!</span><span class="sxs-lookup"><span data-stu-id="8bcc8-145">F or !</span></span>|  
|`String`|<span data-ttu-id="8bcc8-146">"</span><span class="sxs-lookup"><span data-stu-id="8bcc8-146">"</span></span>|<span data-ttu-id="8bcc8-147">(keine)</span><span class="sxs-lookup"><span data-stu-id="8bcc8-147">(none)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8bcc8-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8bcc8-148">See Also</span></span>  
 <span data-ttu-id="8bcc8-149">[Benutzerdefinierte Konstanten](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md) </span><span class="sxs-lookup"><span data-stu-id="8bcc8-149">[User-Defined Constants](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md) </span></span>  
<span data-ttu-id="8bcc8-150"> [Gewusst wie: Deklarieren einer Konstante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md) </span><span class="sxs-lookup"><span data-stu-id="8bcc8-150"> [How to: Declare A Constant](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md) </span></span>  
<span data-ttu-id="8bcc8-151"> [Übersicht über Konstanten](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span><span class="sxs-lookup"><span data-stu-id="8bcc8-151"> [Constants Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span></span>  
<span data-ttu-id="8bcc8-152"> [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8bcc8-152"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="8bcc8-153"> [Option Explicit-Anweisung](../../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8bcc8-153"> [Option Explicit Statement](../../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span></span>  
<span data-ttu-id="8bcc8-154"> [Übersicht über Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span><span class="sxs-lookup"><span data-stu-id="8bcc8-154"> [Enumerations Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span></span>  
<span data-ttu-id="8bcc8-155"> [Gewusst wie: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="8bcc8-155"> [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span></span>  
<span data-ttu-id="8bcc8-156"> [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span><span class="sxs-lookup"><span data-stu-id="8bcc8-156"> [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span></span>  
<span data-ttu-id="8bcc8-157"> [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="8bcc8-157"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="8bcc8-158"> [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="8bcc8-158"> [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span></span>
