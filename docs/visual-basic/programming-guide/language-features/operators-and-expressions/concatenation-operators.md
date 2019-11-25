---
title: Verkettungsoperatoren
ms.date: 07/20/2015
helpviewer_keywords:
- '& operator [Visual Basic], concatenation'
- concatenation operators [Visual Basic]
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- + operator [Visual Basic], concatenation
- concatenation operators [Visual Basic]
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
ms.openlocfilehash: f86245c649647be4e040a61083d8b93eee4d7422
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353690"
---
# <a name="concatenation-operators-in-visual-basic"></a><span data-ttu-id="a5845-102">Verkettungsoperatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a5845-102">Concatenation Operators in Visual Basic</span></span>

<span data-ttu-id="a5845-103">Verkettungsoperatoren verbinden mehrere Zeichenfolgen zu einer einzelnen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a5845-103">Concatenation operators join multiple strings into a single string.</span></span> <span data-ttu-id="a5845-104">Es gibt zwei Verkettungsoperatoren: `+` und `&`.</span><span class="sxs-lookup"><span data-stu-id="a5845-104">There are two concatenation operators, `+` and `&`.</span></span> <span data-ttu-id="a5845-105">Beide führen einen grundlegende Verkettungsvorgang durch, wie das nachfolgende Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="a5845-105">Both carry out the basic concatenation operation, as the following example shows.</span></span>

```vb
Dim x As String = "Mic" & "ro" & "soft"
Dim y As String = "Mic" + "ro" + "soft"
' The preceding statements set both x and y to "Microsoft".
```

<span data-ttu-id="a5845-106">Diese Operatoren können auch `String`-Variablen verketten, wie das folgende Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="a5845-106">These operators can also concatenate `String` variables, as the following example shows.</span></span>

[!code-vb[VbVbalrOperators#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#76)]

## <a name="differences-between-the-two-concatenation-operators"></a><span data-ttu-id="a5845-107">Unterschiede zwischen den beiden Verkettungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="a5845-107">Differences Between the Two Concatenation Operators</span></span>

<span data-ttu-id="a5845-108">The [+ Operator](../../../../visual-basic/language-reference/operators/addition-operator.md) has the primary purpose of adding two numbers.</span><span class="sxs-lookup"><span data-stu-id="a5845-108">The [+ Operator](../../../../visual-basic/language-reference/operators/addition-operator.md) has the primary purpose of adding two numbers.</span></span> <span data-ttu-id="a5845-109">Damit können jedoch auch numerische Operanden mit Zeichenfolgenoperanden verkettet werden.</span><span class="sxs-lookup"><span data-stu-id="a5845-109">However, it can also concatenate numeric operands with string operands.</span></span> <span data-ttu-id="a5845-110">Der `+`-Operator verfügt über einen komplexen Satz an Regeln, die bestimmen, ob eine Addition oder Verkettung stattfindet, ob ein Compilerfehler signalisiert wird oder ob eine <xref:System.InvalidCastException>-Ausnahme bei Laufzeit ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="a5845-110">The `+` operator has a complex set of rules that determine whether to add, concatenate, signal a compiler error, or throw a run-time <xref:System.InvalidCastException> exception.</span></span>

<span data-ttu-id="a5845-111">The [& Operator](../../../../visual-basic/language-reference/operators/concatenation-operator.md) is defined only for `String` operands, and it always widens its operands to `String`, regardless of the setting of `Option Strict`.</span><span class="sxs-lookup"><span data-stu-id="a5845-111">The [& Operator](../../../../visual-basic/language-reference/operators/concatenation-operator.md) is defined only for `String` operands, and it always widens its operands to `String`, regardless of the setting of `Option Strict`.</span></span> <span data-ttu-id="a5845-112">Der `&`-Operator wird für die Zeichenfolgenverkettung empfohlen, da er ausschließlich für Zeichenfolgen definiert wurde und da er die Gefahr einer unbeabsichtigten Konvertierung reduziert.</span><span class="sxs-lookup"><span data-stu-id="a5845-112">The `&` operator is recommended for string concatenation because it is defined exclusively for strings and reduces your chances of generating an unintended conversion.</span></span>

## <a name="performance-string-and-stringbuilder"></a><span data-ttu-id="a5845-113">Performance: String and StringBuilder</span><span class="sxs-lookup"><span data-stu-id="a5845-113">Performance: String and StringBuilder</span></span>

<span data-ttu-id="a5845-114">Wenn Sie zahlreiche Manipulationen an einer Zeichenfolge durchführen, z. B. Verkettungen, Löschungen und Ersetzungen, kann Ihre Leistung von der <xref:System.Text.StringBuilder>-Klasse im <xref:System.Text>-Namespace profitieren.</span><span class="sxs-lookup"><span data-stu-id="a5845-114">If you do a significant number of manipulations on a string, such as concatenations, deletions, and replacements, your performance might profit from the <xref:System.Text.StringBuilder> class in the <xref:System.Text> namespace.</span></span> <span data-ttu-id="a5845-115">Sie benötigen eine zusätzliche Anweisung, um ein <xref:System.Text.StringBuilder>-Objekt zu erstellen und zu initialisieren, sowie eine weitere Anweisung, um den endgültigen Wert in einen `String` zu konvertieren. Diese Zeit können Sie jedoch wieder einholen, da <xref:System.Text.StringBuilder> eine schnellere Leistung bietet.</span><span class="sxs-lookup"><span data-stu-id="a5845-115">It takes an extra instruction to create and initialize a <xref:System.Text.StringBuilder> object, and another instruction to convert its final value to a `String`, but you might recover this time because <xref:System.Text.StringBuilder> can perform faster.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5845-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5845-116">See also</span></span>

- [<span data-ttu-id="a5845-117">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a5845-117">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="a5845-118">Types of String Manipulation Methods in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a5845-118">Types of String Manipulation Methods in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md)
- [<span data-ttu-id="a5845-119">Arithmetic Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a5845-119">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="a5845-120">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a5845-120">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="a5845-121">Logical and Bitwise Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a5845-121">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
