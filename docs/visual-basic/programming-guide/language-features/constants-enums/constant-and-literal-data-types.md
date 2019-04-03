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
ms.openlocfilehash: 50e36aa13439bafcca27a7153a8c5d6043f03975
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58833502"
---
# <a name="constant-and-literal-data-types-visual-basic"></a><span data-ttu-id="3abb6-102">Konstanten und literale Datentypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3abb6-102">Constant and Literal Data Types (Visual Basic)</span></span>
<span data-ttu-id="3abb6-103">Ein Literal ist ein Wert, der als sich selbst und nicht als der Wert einer Variablen oder das Ergebnis eines Ausdrucks, z. B. die Zahl 3 oder die Zeichenfolge "Hello" ausgedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="3abb6-103">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span></span> <span data-ttu-id="3abb6-104">Eine Konstante ist, einen aussagekräftigen Namen, der tritt an die Stelle eines Literals und behält den gleichen Wert in der gesamten Anwendung, im Gegensatz zu einer Variablen, deren Wert ändern kann.</span><span class="sxs-lookup"><span data-stu-id="3abb6-104">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span></span>  
  
 <span data-ttu-id="3abb6-105">Wenn [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) ist `Off` und [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) ist `On`, müssen Sie alle Konstanten mit einem Datentyp explizit deklarieren.</span><span class="sxs-lookup"><span data-stu-id="3abb6-105">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span></span> <span data-ttu-id="3abb6-106">Im folgenden Beispiel ist der Datentyp des `MyByte` wird als Datentyp explizit deklariert `Byte`:</span><span class="sxs-lookup"><span data-stu-id="3abb6-106">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span></span>  
  
 [!code-vb[VbVbalrConstants#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#1)]  
  
 <span data-ttu-id="3abb6-107">Wenn `Option Infer` ist `On` oder `Option Strict` ist `Off`, Deklarieren einer Konstante können Sie ohne Angabe von einem Datentyp mit einer `As` Klausel.</span><span class="sxs-lookup"><span data-stu-id="3abb6-107">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="3abb6-108">Der Compiler bestimmt den Typ der Konstante vom Typ des Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="3abb6-108">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="3abb6-109">Ein numerisches Ganzzahlliteral umgewandelt wird, werden standardmäßig die `Integer` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="3abb6-109">A numeric integer literal is cast by default to the `Integer` data type.</span></span> <span data-ttu-id="3abb6-110">Der Standarddatentyp für Gleitkommazahlen ist `Double`, Schlüsselwörter und `True` und `False` Geben Sie einen `Boolean` Konstanten.</span><span class="sxs-lookup"><span data-stu-id="3abb6-110">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span></span>  
  
## <a name="literals-and-type-coercion"></a><span data-ttu-id="3abb6-111">Literale und Typkoersion</span><span class="sxs-lookup"><span data-stu-id="3abb6-111">Literals and Type Coercion</span></span>  
 <span data-ttu-id="3abb6-112">In einigen Fällen empfiehlt es sich um ein Literal für einen bestimmten Datentyp zu erzwingen; z. B., wenn Sie eine Variable des Typs einer besonders großen Ganzzahlliteralwert zuweisen `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="3abb6-112">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span></span> <span data-ttu-id="3abb6-113">Im folgenden Beispiel wird einen Fehler an:</span><span class="sxs-lookup"><span data-stu-id="3abb6-113">The following example produces an error:</span></span>  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 <span data-ttu-id="3abb6-114">Der Fehler resultiert aus der Darstellung des Literals.</span><span class="sxs-lookup"><span data-stu-id="3abb6-114">The error results from the representation of the literal.</span></span> <span data-ttu-id="3abb6-115">Die `Decimal` -Datentyp kann einen Wert enthalten dieser Größe, aber das Literal wird implizit als dargestellt eine `Long`, welche nicht.</span><span class="sxs-lookup"><span data-stu-id="3abb6-115">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span></span>  
  
 <span data-ttu-id="3abb6-116">Sie können coerce-Literal in einen bestimmten Datentyp, gibt es zwei Möglichkeiten: ein Typzeichen, Anfügen oder legen Sie das Element innerhalb der umschließenden Zeichen.</span><span class="sxs-lookup"><span data-stu-id="3abb6-116">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span></span> <span data-ttu-id="3abb6-117">Ein Typzeichen oder Zeichen einschließen muss unmittelbar vorangestellt sein und/oder führen Sie das Literal, ohne Leerzeichen oder Zeichen jeglicher Art.</span><span class="sxs-lookup"><span data-stu-id="3abb6-117">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span></span>  
  
 <span data-ttu-id="3abb6-118">Damit wird das vorherige Beispiel funktioniert, fügen Sie der `D` Typzeichen, dem Literal, das als dargestellt wird ein `Decimal`:</span><span class="sxs-lookup"><span data-stu-id="3abb6-118">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span></span>  
  
 [!code-vb[VbVbalrConstants#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#2)]  
  
 <span data-ttu-id="3abb6-119">Das folgende Beispiel veranschaulicht die richtige Verwendung von Typzeichen und umschließenden Zeichen:</span><span class="sxs-lookup"><span data-stu-id="3abb6-119">The following example demonstrates correct usage of type characters and enclosing characters:</span></span>  
  
 [!code-vb[VbVbalrConstants#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#3)]  
  
 <span data-ttu-id="3abb6-120">Die folgende Tabelle zeigt die umschließenden Zeichen und ein Typzeichen, die in Visual Basic verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3abb6-120">The following table shows the enclosing characters and type characters available in Visual Basic.</span></span>  
  
|<span data-ttu-id="3abb6-121">Datentyp</span><span class="sxs-lookup"><span data-stu-id="3abb6-121">Data type</span></span>|<span data-ttu-id="3abb6-122">Zeichen</span><span class="sxs-lookup"><span data-stu-id="3abb6-122">Enclosing character</span></span>|<span data-ttu-id="3abb6-123">Angefügte Typzeichen</span><span class="sxs-lookup"><span data-stu-id="3abb6-123">Appended type character</span></span>|  
|---|---|---|  
|`Boolean`|<span data-ttu-id="3abb6-124">(keine)</span><span class="sxs-lookup"><span data-stu-id="3abb6-124">(none)</span></span>|<span data-ttu-id="3abb6-125">(keine)</span><span class="sxs-lookup"><span data-stu-id="3abb6-125">(none)</span></span>|  
|`Byte`|<span data-ttu-id="3abb6-126">(keine)</span><span class="sxs-lookup"><span data-stu-id="3abb6-126">(none)</span></span>|<span data-ttu-id="3abb6-127">(keine)</span><span class="sxs-lookup"><span data-stu-id="3abb6-127">(none)</span></span>|  
|`Char`|<span data-ttu-id="3abb6-128">"</span><span class="sxs-lookup"><span data-stu-id="3abb6-128">"</span></span>|<span data-ttu-id="3abb6-129">C</span><span class="sxs-lookup"><span data-stu-id="3abb6-129">C</span></span>|  
|`Date`|#|<span data-ttu-id="3abb6-130">(keine)</span><span class="sxs-lookup"><span data-stu-id="3abb6-130">(none)</span></span>|  
|`Decimal`|<span data-ttu-id="3abb6-131">(keine)</span><span class="sxs-lookup"><span data-stu-id="3abb6-131">(none)</span></span>|<span data-ttu-id="3abb6-132">D oder @</span><span class="sxs-lookup"><span data-stu-id="3abb6-132">D or @</span></span>|  
|`Double`|<span data-ttu-id="3abb6-133">(keine)</span><span class="sxs-lookup"><span data-stu-id="3abb6-133">(none)</span></span>|<span data-ttu-id="3abb6-134">R "oder" #</span><span class="sxs-lookup"><span data-stu-id="3abb6-134">R or #</span></span>|  
|`Integer`|<span data-ttu-id="3abb6-135">(keine)</span><span class="sxs-lookup"><span data-stu-id="3abb6-135">(none)</span></span>|<span data-ttu-id="3abb6-136">Ich oder %</span><span class="sxs-lookup"><span data-stu-id="3abb6-136">I or %</span></span>|  
|`Long`|<span data-ttu-id="3abb6-137">(keine)</span><span class="sxs-lookup"><span data-stu-id="3abb6-137">(none)</span></span>|<span data-ttu-id="3abb6-138">L oder &</span><span class="sxs-lookup"><span data-stu-id="3abb6-138">L or &</span></span>|  
|`Short`|<span data-ttu-id="3abb6-139">(keine)</span><span class="sxs-lookup"><span data-stu-id="3abb6-139">(none)</span></span>|<span data-ttu-id="3abb6-140">S</span><span class="sxs-lookup"><span data-stu-id="3abb6-140">S</span></span>|  
|`Single`|<span data-ttu-id="3abb6-141">(keine)</span><span class="sxs-lookup"><span data-stu-id="3abb6-141">(none)</span></span>|<span data-ttu-id="3abb6-142">F oder!</span><span class="sxs-lookup"><span data-stu-id="3abb6-142">F or !</span></span>|  
|`String`|<span data-ttu-id="3abb6-143">"</span><span class="sxs-lookup"><span data-stu-id="3abb6-143">"</span></span>|<span data-ttu-id="3abb6-144">(keine)</span><span class="sxs-lookup"><span data-stu-id="3abb6-144">(none)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3abb6-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3abb6-145">See also</span></span>

- [<span data-ttu-id="3abb6-146">Benutzerdefinierte Konstanten</span><span class="sxs-lookup"><span data-stu-id="3abb6-146">User-Defined Constants</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)
- [<span data-ttu-id="3abb6-147">Vorgehensweise: Deklarieren einer Konstante</span><span class="sxs-lookup"><span data-stu-id="3abb6-147">How to: Declare A Constant</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)
- [<span data-ttu-id="3abb6-148">Übersicht über Konstanten</span><span class="sxs-lookup"><span data-stu-id="3abb6-148">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="3abb6-149">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3abb6-149">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="3abb6-150">Option Explicit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3abb6-150">Option Explicit Statement</span></span>](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="3abb6-151">Übersicht über Enumerationen</span><span class="sxs-lookup"><span data-stu-id="3abb6-151">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [<span data-ttu-id="3abb6-152">Vorgehensweise: Deklarieren einer Enumeration</span><span class="sxs-lookup"><span data-stu-id="3abb6-152">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="3abb6-153">Enumerationen und Namensqualifikation</span><span class="sxs-lookup"><span data-stu-id="3abb6-153">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="3abb6-154">Datentypen</span><span class="sxs-lookup"><span data-stu-id="3abb6-154">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="3abb6-155">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="3abb6-155">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
