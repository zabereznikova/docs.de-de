---
title: Konstanten und literale Datentypen
ms.date: 07/20/2015
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
ms.openlocfilehash: b94259326b42104db05d9fc5bb09f686075d0759
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414530"
---
# <a name="constant-and-literal-data-types-visual-basic"></a><span data-ttu-id="7db45-102">Konstanten und literale Datentypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7db45-102">Constant and Literal Data Types (Visual Basic)</span></span>
<span data-ttu-id="7db45-103">Ein Literalwert ist ein Wert, der als sich selbst und nicht als Variablen Wert oder als Ergebnis eines Ausdrucks ausgedrückt wird, z. b. die Zahl 3 oder die Zeichenfolge "Hello".</span><span class="sxs-lookup"><span data-stu-id="7db45-103">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span></span> <span data-ttu-id="7db45-104">Eine Konstante ist ein sinnvoller Name, der den Speicherort eines Literals annimmt und denselben Wert im gesamten Programm beibehält, im Gegensatz zu einer Variablen, deren Wert sich ändern kann.</span><span class="sxs-lookup"><span data-stu-id="7db45-104">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span></span>  
  
 <span data-ttu-id="7db45-105">Wenn die [Option Infer](../../../language-reference/statements/option-infer-statement.md) ist `Off` und [Option Strict](../../../language-reference/statements/option-strict-statement.md) ist `On` , müssen Sie alle Konstanten explizit mit einem-Datentyp deklarieren.</span><span class="sxs-lookup"><span data-stu-id="7db45-105">When [Option Infer](../../../language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span></span> <span data-ttu-id="7db45-106">Im folgenden Beispiel wird der Datentyp von `MyByte` explizit als-Datentyp deklariert `Byte` :</span><span class="sxs-lookup"><span data-stu-id="7db45-106">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span></span>  
  
 [!code-vb[VbVbalrConstants#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#1)]  
  
 <span data-ttu-id="7db45-107">Wenn auf oder festgelegt ist `Option Infer` `On` `Option Strict` `Off` , können Sie eine Konstante deklarieren, ohne einen-Datentyp mit einer- `As` Klausel anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7db45-107">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="7db45-108">Der Compiler bestimmt den Typ der Konstante vom Typ des Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="7db45-108">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="7db45-109">Ein numerisches Ganzzahlliteral wird standardmäßig in den- `Integer` Datentyp umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="7db45-109">A numeric integer literal is cast by default to the `Integer` data type.</span></span> <span data-ttu-id="7db45-110">Der Standard Datentyp für Gleit Komma Zahlen ist `Double` , und die Schlüsselwörter `True` und `False` geben eine `Boolean` Konstante an.</span><span class="sxs-lookup"><span data-stu-id="7db45-110">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span></span>  
  
## <a name="literals-and-type-coercion"></a><span data-ttu-id="7db45-111">Literale und Typumwandlung</span><span class="sxs-lookup"><span data-stu-id="7db45-111">Literals and Type Coercion</span></span>  
 <span data-ttu-id="7db45-112">In einigen Fällen möchten Sie möglicherweise einen Literalwert für einen bestimmten Datentyp erzwingen. beispielsweise beim Zuweisen eines besonders großen ganzzahligen Literalwerts zu einer Variablen vom Typ `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="7db45-112">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span></span> <span data-ttu-id="7db45-113">Im folgenden Beispiel wird ein Fehler erzeugt:</span><span class="sxs-lookup"><span data-stu-id="7db45-113">The following example produces an error:</span></span>  
  
```vb  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 <span data-ttu-id="7db45-114">Der Fehler ergibt sich aus der Darstellung des Literals.</span><span class="sxs-lookup"><span data-stu-id="7db45-114">The error results from the representation of the literal.</span></span> <span data-ttu-id="7db45-115">Der- `Decimal` Datentyp kann einen Wert enthalten, der groß ist, aber das Literale wird implizit als dargestellt `Long` , was nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="7db45-115">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span></span>  
  
 <span data-ttu-id="7db45-116">Sie können einen Literalwert auf zwei Arten in einen bestimmten Datentyp umwandeln: indem Sie ein Typzeichen an ihn anfügen oder ihn in einschließende Zeichen platzieren.</span><span class="sxs-lookup"><span data-stu-id="7db45-116">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span></span> <span data-ttu-id="7db45-117">Ein Typzeichen oder einschließende Zeichen muss unmittelbar vor und/oder nach dem Literalzeichen stehen, ohne dass dazwischen liegende Leerzeichen oder Zeichen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="7db45-117">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span></span>  
  
 <span data-ttu-id="7db45-118">Damit das vorherige Beispiel funktioniert, können Sie das `D` Typzeichen an das Literale anfügen, wodurch es als dargestellt wird `Decimal` :</span><span class="sxs-lookup"><span data-stu-id="7db45-118">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span></span>  
  
 [!code-vb[VbVbalrConstants#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#2)]  
  
 <span data-ttu-id="7db45-119">Das folgende Beispiel veranschaulicht die korrekte Verwendung von Typzeichen und einschließenden Zeichen:</span><span class="sxs-lookup"><span data-stu-id="7db45-119">The following example demonstrates correct usage of type characters and enclosing characters:</span></span>  
  
 [!code-vb[VbVbalrConstants#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#3)]  
  
 <span data-ttu-id="7db45-120">In der folgenden Tabelle werden die in Visual Basic verfügbaren einschließenden Zeichen und Typzeichen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7db45-120">The following table shows the enclosing characters and type characters available in Visual Basic.</span></span>  
  
|<span data-ttu-id="7db45-121">Datentyp</span><span class="sxs-lookup"><span data-stu-id="7db45-121">Data type</span></span>|<span data-ttu-id="7db45-122">Einschließendes Zeichen</span><span class="sxs-lookup"><span data-stu-id="7db45-122">Enclosing character</span></span>|<span data-ttu-id="7db45-123">Angefügtes Typzeichen</span><span class="sxs-lookup"><span data-stu-id="7db45-123">Appended type character</span></span>|  
|---|---|---|  
|`Boolean`|<span data-ttu-id="7db45-124">(none)</span><span class="sxs-lookup"><span data-stu-id="7db45-124">(none)</span></span>|<span data-ttu-id="7db45-125">(none)</span><span class="sxs-lookup"><span data-stu-id="7db45-125">(none)</span></span>|  
|`Byte`|<span data-ttu-id="7db45-126">(none)</span><span class="sxs-lookup"><span data-stu-id="7db45-126">(none)</span></span>|<span data-ttu-id="7db45-127">(none)</span><span class="sxs-lookup"><span data-stu-id="7db45-127">(none)</span></span>|  
|`Char`|<span data-ttu-id="7db45-128">"</span><span class="sxs-lookup"><span data-stu-id="7db45-128">"</span></span>|<span data-ttu-id="7db45-129">C</span><span class="sxs-lookup"><span data-stu-id="7db45-129">C</span></span>|  
|`Date`|#|<span data-ttu-id="7db45-130">(none)</span><span class="sxs-lookup"><span data-stu-id="7db45-130">(none)</span></span>|  
|`Decimal`|<span data-ttu-id="7db45-131">(none)</span><span class="sxs-lookup"><span data-stu-id="7db45-131">(none)</span></span>|<span data-ttu-id="7db45-132">D oder @</span><span class="sxs-lookup"><span data-stu-id="7db45-132">D or @</span></span>|  
|`Double`|<span data-ttu-id="7db45-133">(none)</span><span class="sxs-lookup"><span data-stu-id="7db45-133">(none)</span></span>|<span data-ttu-id="7db45-134">R oder #</span><span class="sxs-lookup"><span data-stu-id="7db45-134">R or #</span></span>|  
|`Integer`|<span data-ttu-id="7db45-135">(none)</span><span class="sxs-lookup"><span data-stu-id="7db45-135">(none)</span></span>|<span data-ttu-id="7db45-136">I oder%</span><span class="sxs-lookup"><span data-stu-id="7db45-136">I or %</span></span>|  
|`Long`|<span data-ttu-id="7db45-137">(none)</span><span class="sxs-lookup"><span data-stu-id="7db45-137">(none)</span></span>|<span data-ttu-id="7db45-138">L oder &</span><span class="sxs-lookup"><span data-stu-id="7db45-138">L or &</span></span>|  
|`Short`|<span data-ttu-id="7db45-139">(none)</span><span class="sxs-lookup"><span data-stu-id="7db45-139">(none)</span></span>|<span data-ttu-id="7db45-140">E</span><span class="sxs-lookup"><span data-stu-id="7db45-140">S</span></span>|  
|`Single`|<span data-ttu-id="7db45-141">(none)</span><span class="sxs-lookup"><span data-stu-id="7db45-141">(none)</span></span>|<span data-ttu-id="7db45-142">F oder!</span><span class="sxs-lookup"><span data-stu-id="7db45-142">F or !</span></span>|  
|`String`|<span data-ttu-id="7db45-143">"</span><span class="sxs-lookup"><span data-stu-id="7db45-143">"</span></span>|<span data-ttu-id="7db45-144">(none)</span><span class="sxs-lookup"><span data-stu-id="7db45-144">(none)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7db45-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7db45-145">See also</span></span>

- [<span data-ttu-id="7db45-146">Benutzerdefinierte Konstanten</span><span class="sxs-lookup"><span data-stu-id="7db45-146">User-Defined Constants</span></span>](user-defined-constants.md)
- [<span data-ttu-id="7db45-147">Vorgehensweise: Deklarieren einer Konstante</span><span class="sxs-lookup"><span data-stu-id="7db45-147">How to: Declare A Constant</span></span>](how-to-declare-a-constant.md)
- [<span data-ttu-id="7db45-148">Übersicht über Konstanten</span><span class="sxs-lookup"><span data-stu-id="7db45-148">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="7db45-149">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7db45-149">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="7db45-150">Option Explicit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7db45-150">Option Explicit Statement</span></span>](../../../language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="7db45-151">Übersicht über Enumerationen</span><span class="sxs-lookup"><span data-stu-id="7db45-151">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="7db45-152">Gewusst wie: Deklarieren einer Enumeration</span><span class="sxs-lookup"><span data-stu-id="7db45-152">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="7db45-153">Enumerationen und Namensqualifikation</span><span class="sxs-lookup"><span data-stu-id="7db45-153">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="7db45-154">Datentypen</span><span class="sxs-lookup"><span data-stu-id="7db45-154">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="7db45-155">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="7db45-155">Constants and Enumerations</span></span>](../../../language-reference/constants-and-enumerations.md)
