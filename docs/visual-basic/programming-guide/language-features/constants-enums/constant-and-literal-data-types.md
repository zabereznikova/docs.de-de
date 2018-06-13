---
title: Konstanten und literale Datentypen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
ms.openlocfilehash: 8d110ec17bcdb03f339d779b2950ba56d77957cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649847"
---
# <a name="constant-and-literal-data-types-visual-basic"></a><span data-ttu-id="eeb9a-102">Konstanten und literale Datentypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eeb9a-102">Constant and Literal Data Types (Visual Basic)</span></span>
<span data-ttu-id="eeb9a-103">Ein Literal ist ein Wert, der als selbst und nicht als Wert einer Variablen oder das Ergebnis eines Ausdrucks, z. B. die Zahl 3 oder die Zeichenfolge "Hello" ausgedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="eeb9a-103">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span></span> <span data-ttu-id="eeb9a-104">Eine Konstante ist, einen aussagekräftigen Namen, der anstelle eines Literals und behält der gleiche Wert in der gesamten Anwendung, im Gegensatz zu einer Variablen, deren Wert sich ändern kann.</span><span class="sxs-lookup"><span data-stu-id="eeb9a-104">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span></span>  
  
 <span data-ttu-id="eeb9a-105">Wenn [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) ist `Off` und [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) ist `On`, müssen Sie alle Konstanten explizit mit einem Datentyp deklarieren.</span><span class="sxs-lookup"><span data-stu-id="eeb9a-105">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span></span> <span data-ttu-id="eeb9a-106">Im folgenden Beispiel der Datentyp des `MyByte` wird als Datentyp explizit deklariert `Byte`:</span><span class="sxs-lookup"><span data-stu-id="eeb9a-106">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span></span>  
  
 [!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 <span data-ttu-id="eeb9a-107">Wenn `Option Infer` ist `On` oder `Option Strict` ist `Off`, Sie Deklarieren einer Konstante, ohne dass einen Datentyp mit einer `As` Klausel.</span><span class="sxs-lookup"><span data-stu-id="eeb9a-107">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="eeb9a-108">Der Compiler bestimmt den Typ der Konstante vom Typ des Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="eeb9a-108">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="eeb9a-109">Ein numerisches Ganzzahlliteral umgewandelt wird, werden standardmäßig die `Integer` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="eeb9a-109">A numeric integer literal is cast by default to the `Integer` data type.</span></span> <span data-ttu-id="eeb9a-110">Der Standarddatentyp für Gleitkommazahlen ist `Double`, Schlüsselwörter und `True` und `False` Geben Sie einen `Boolean` konstant.</span><span class="sxs-lookup"><span data-stu-id="eeb9a-110">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span></span>  
  
## <a name="literals-and-type-coercion"></a><span data-ttu-id="eeb9a-111">Literale und Typkoersion</span><span class="sxs-lookup"><span data-stu-id="eeb9a-111">Literals and Type Coercion</span></span>  
 <span data-ttu-id="eeb9a-112">In einigen Fällen empfiehlt es sich um ein Literal in einen bestimmten Datentyp erzwingen; beispielsweise, wenn Sie eine Variable des Typs einer besonders großen Ganzzahlliteralwert zuweisen `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="eeb9a-112">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span></span> <span data-ttu-id="eeb9a-113">Im folgende Beispiel wird einen Fehler generiert:</span><span class="sxs-lookup"><span data-stu-id="eeb9a-113">The following example produces an error:</span></span>  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 <span data-ttu-id="eeb9a-114">Der Fehler resultiert aus der Darstellung des Literals.</span><span class="sxs-lookup"><span data-stu-id="eeb9a-114">The error results from the representation of the literal.</span></span> <span data-ttu-id="eeb9a-115">Die `Decimal` -Datentyp kann einen Wert enthalten dieser Größe, aber das Literal liegt implizit als eine `Long`, welche nicht.</span><span class="sxs-lookup"><span data-stu-id="eeb9a-115">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span></span>  
  
 <span data-ttu-id="eeb9a-116">Sie können ein Literal in einen bestimmten Datentyp auf zwei Arten coerce: durch Anhängen ein Typzeichen, oder legen Sie das Element innerhalb der einschließenden Zeichen.</span><span class="sxs-lookup"><span data-stu-id="eeb9a-116">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span></span> <span data-ttu-id="eeb9a-117">Ein Typzeichen oder umschließende Zeichen muss unmittelbar vorangestellt und/oder führen Sie das Literal, ohne Leerzeichen oder Zeichen jeglicher Art.</span><span class="sxs-lookup"><span data-stu-id="eeb9a-117">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span></span>  
  
 <span data-ttu-id="eeb9a-118">Um das vorherige Beispiel arbeiten zu machen, können Sie Anfügen der `D` -Typzeichen dem Literal, wodurch es als dargestellt wird ein `Decimal`:</span><span class="sxs-lookup"><span data-stu-id="eeb9a-118">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span></span>  
  
 [!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 <span data-ttu-id="eeb9a-119">Das folgende Beispiel veranschaulicht die richtige Verwendung von Typzeichen und umschließenden Zeichen:</span><span class="sxs-lookup"><span data-stu-id="eeb9a-119">The following example demonstrates correct usage of type characters and enclosing characters:</span></span>  
  
 [!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 <span data-ttu-id="eeb9a-120">Die folgende Tabelle zeigt die umschließenden Zeichen und Typzeichen, die in Visual Basic verfügbar.</span><span class="sxs-lookup"><span data-stu-id="eeb9a-120">The following table shows the enclosing characters and type characters available in Visual Basic.</span></span>  
  
|<span data-ttu-id="eeb9a-121">Datentyp</span><span class="sxs-lookup"><span data-stu-id="eeb9a-121">Data type</span></span>|<span data-ttu-id="eeb9a-122">Einschließen von Zeichen</span><span class="sxs-lookup"><span data-stu-id="eeb9a-122">Enclosing character</span></span>|<span data-ttu-id="eeb9a-123">Angefügte Typzeichen</span><span class="sxs-lookup"><span data-stu-id="eeb9a-123">Appended type character</span></span>|  
|---|---|---|  
|`Boolean`|<span data-ttu-id="eeb9a-124">(keine)</span><span class="sxs-lookup"><span data-stu-id="eeb9a-124">(none)</span></span>|<span data-ttu-id="eeb9a-125">(keine)</span><span class="sxs-lookup"><span data-stu-id="eeb9a-125">(none)</span></span>|  
|`Byte`|<span data-ttu-id="eeb9a-126">(keine)</span><span class="sxs-lookup"><span data-stu-id="eeb9a-126">(none)</span></span>|<span data-ttu-id="eeb9a-127">(keine)</span><span class="sxs-lookup"><span data-stu-id="eeb9a-127">(none)</span></span>|  
|`Char`|<span data-ttu-id="eeb9a-128">"</span><span class="sxs-lookup"><span data-stu-id="eeb9a-128">"</span></span>|<span data-ttu-id="eeb9a-129">C</span><span class="sxs-lookup"><span data-stu-id="eeb9a-129">C</span></span>|  
|`Date`|#|<span data-ttu-id="eeb9a-130">(keine)</span><span class="sxs-lookup"><span data-stu-id="eeb9a-130">(none)</span></span>|  
|`Decimal`|<span data-ttu-id="eeb9a-131">(keine)</span><span class="sxs-lookup"><span data-stu-id="eeb9a-131">(none)</span></span>|<span data-ttu-id="eeb9a-132">D oder @</span><span class="sxs-lookup"><span data-stu-id="eeb9a-132">D or @</span></span>|  
|`Double`|<span data-ttu-id="eeb9a-133">(keine)</span><span class="sxs-lookup"><span data-stu-id="eeb9a-133">(none)</span></span>|<span data-ttu-id="eeb9a-134">R oder #</span><span class="sxs-lookup"><span data-stu-id="eeb9a-134">R or #</span></span>|  
|`Integer`|<span data-ttu-id="eeb9a-135">(keine)</span><span class="sxs-lookup"><span data-stu-id="eeb9a-135">(none)</span></span>|<span data-ttu-id="eeb9a-136">I oder %</span><span class="sxs-lookup"><span data-stu-id="eeb9a-136">I or %</span></span>|  
|`Long`|<span data-ttu-id="eeb9a-137">(keine)</span><span class="sxs-lookup"><span data-stu-id="eeb9a-137">(none)</span></span>|<span data-ttu-id="eeb9a-138">L oder &</span><span class="sxs-lookup"><span data-stu-id="eeb9a-138">L or &</span></span>|  
|`Short`|<span data-ttu-id="eeb9a-139">(keine)</span><span class="sxs-lookup"><span data-stu-id="eeb9a-139">(none)</span></span>|<span data-ttu-id="eeb9a-140">S</span><span class="sxs-lookup"><span data-stu-id="eeb9a-140">S</span></span>|  
|`Single`|<span data-ttu-id="eeb9a-141">(keine)</span><span class="sxs-lookup"><span data-stu-id="eeb9a-141">(none)</span></span>|<span data-ttu-id="eeb9a-142">F oder!</span><span class="sxs-lookup"><span data-stu-id="eeb9a-142">F or !</span></span>|  
|`String`|<span data-ttu-id="eeb9a-143">"</span><span class="sxs-lookup"><span data-stu-id="eeb9a-143">"</span></span>|<span data-ttu-id="eeb9a-144">(keine)</span><span class="sxs-lookup"><span data-stu-id="eeb9a-144">(none)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eeb9a-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eeb9a-145">See Also</span></span>  
 [<span data-ttu-id="eeb9a-146">Benutzerdefinierte Konstanten</span><span class="sxs-lookup"><span data-stu-id="eeb9a-146">User-Defined Constants</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)  
 [<span data-ttu-id="eeb9a-147">Gewusst wie: Deklarieren einer Konstante</span><span class="sxs-lookup"><span data-stu-id="eeb9a-147">How to: Declare A Constant</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)  
 [<span data-ttu-id="eeb9a-148">Übersicht über Konstanten</span><span class="sxs-lookup"><span data-stu-id="eeb9a-148">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [<span data-ttu-id="eeb9a-149">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="eeb9a-149">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="eeb9a-150">Option Explicit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="eeb9a-150">Option Explicit Statement</span></span>](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="eeb9a-151">Übersicht über Enumerationen</span><span class="sxs-lookup"><span data-stu-id="eeb9a-151">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [<span data-ttu-id="eeb9a-152">Vorgehensweise: Deklarieren einer Enumeration</span><span class="sxs-lookup"><span data-stu-id="eeb9a-152">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="eeb9a-153">Enumerationen und Namensqualifikation</span><span class="sxs-lookup"><span data-stu-id="eeb9a-153">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="eeb9a-154">Datentypen</span><span class="sxs-lookup"><span data-stu-id="eeb9a-154">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="eeb9a-155">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="eeb9a-155">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
