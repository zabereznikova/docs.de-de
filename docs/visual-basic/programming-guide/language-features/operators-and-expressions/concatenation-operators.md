---
title: Verkettungsoperatoren in Visual Basic | Microsoft-Dokumentation
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
- '& operator [Visual Basic], concatenation'
- concatenation operators
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- + operator [Visual Basic], concatenation
- concatenation operators, Visual Basic strings
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
caps.latest.revision: 18
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
ms.openlocfilehash: f255e168b9eb794ef846e0cc18dbbdba5941bec5
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="concatenation-operators-in-visual-basic"></a><span data-ttu-id="9e950-102">Verkettungsoperatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9e950-102">Concatenation Operators in Visual Basic</span></span>
<span data-ttu-id="9e950-103">Verkettungsoperatoren verbinden mehrere Zeichenfolgen zu einer einzelnen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9e950-103">Concatenation operators join multiple strings into a single string.</span></span> <span data-ttu-id="9e950-104">Es gibt zwei Verkettungsoperatoren: `+` und `&`.</span><span class="sxs-lookup"><span data-stu-id="9e950-104">There are two concatenation operators, `+` and `&`.</span></span> <span data-ttu-id="9e950-105">Beide führen einen grundlegende Verkettungsvorgang durch, wie das nachfolgende Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="9e950-105">Both carry out the basic concatenation operation, as the following example shows.</span></span>  
  
```vb
Dim x As String = "Mic" & "ro" & "soft" 
Dim y As String = "Mic" + "ro" + "soft" 
' The preceding statements set both x and y to "Microsoft".
```  
  
 <span data-ttu-id="9e950-106">Diese Operatoren können auch `String`-Variablen verketten, wie das folgende Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="9e950-106">These operators can also concatenate `String` variables, as the following example shows.</span></span>  
  
 <span data-ttu-id="9e950-107">[!code-vb[VbVbalrOperators&#76;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operators_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="9e950-107">[!code-vb[VbVbalrOperators#76](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operators_1.vb)]</span></span>  
  
## <a name="differences-between-the-two-concatenation-operators"></a><span data-ttu-id="9e950-108">Unterschiede zwischen den beiden Verkettungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="9e950-108">Differences Between the Two Concatenation Operators</span></span>  
 <span data-ttu-id="9e950-109">Die [+-Operator](../../../../visual-basic/language-reference/operators/addition-operator.md) ist den primären Zweck von zwei Zahlen hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="9e950-109">The [+ Operator](../../../../visual-basic/language-reference/operators/addition-operator.md) has the primary purpose of adding two numbers.</span></span> <span data-ttu-id="9e950-110">Damit können jedoch auch numerische Operanden mit Zeichenfolgenoperanden verkettet werden.</span><span class="sxs-lookup"><span data-stu-id="9e950-110">However, it can also concatenate numeric operands with string operands.</span></span> <span data-ttu-id="9e950-111">Die `+` Operator verfügt über einen komplexen Satz von Regeln, die bestimmen, ob die hinzufügen, verkettet, ein Compilerfehler signalisiert oder eine Laufzeit <xref:System.InvalidCastException>Ausnahme.</xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="9e950-111">The `+` operator has a complex set of rules that determine whether to add, concatenate, signal a compiler error, or throw a run-time <xref:System.InvalidCastException> exception.</span></span>  
  
 <span data-ttu-id="9e950-112">Die [& Operator](../../../../visual-basic/language-reference/operators/concatenation-operator.md) ist nur für definiert `String` -Operanden verwendet und erweitert seine Operanden zu immer `String`, unabhängig von der Einstellung der `Option Strict`.</span><span class="sxs-lookup"><span data-stu-id="9e950-112">The [& Operator](../../../../visual-basic/language-reference/operators/concatenation-operator.md) is defined only for `String` operands, and it always widens its operands to `String`, regardless of the setting of `Option Strict`.</span></span> <span data-ttu-id="9e950-113">Der `&`-Operator wird für die Zeichenfolgenverkettung empfohlen, da er ausschließlich für Zeichenfolgen definiert wurde und da er die Gefahr einer unbeabsichtigten Konvertierung reduziert.</span><span class="sxs-lookup"><span data-stu-id="9e950-113">The `&` operator is recommended for string concatenation because it is defined exclusively for strings and reduces your chances of generating an unintended conversion.</span></span>  
  
## <a name="performance-string-and-stringbuilder"></a><span data-ttu-id="9e950-114">Leistung: Zeichenfolgen und StringBuilder</span><span class="sxs-lookup"><span data-stu-id="9e950-114">Performance: String and StringBuilder</span></span>  
 <span data-ttu-id="9e950-115">Wenn Sie eine große Anzahl von Manipulationen an einer Zeichenfolge, z. B. Verkettungen, löschungen und Ersetzungen, führen Sie die Leistung möglicherweise Gewinn der <xref:System.Text.StringBuilder>-Klasse in die <xref:System.Text>Namespace.</xref:System.Text> </xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="9e950-115">If you do a significant number of manipulations on a string, such as concatenations, deletions, and replacements, your performance might profit from the <xref:System.Text.StringBuilder> class in the <xref:System.Text> namespace.</span></span> <span data-ttu-id="9e950-116">Dauert es eine zusätzliche Anweisung erstellt und initialisiert ein <xref:System.Text.StringBuilder>Objekt und eine andere Anweisung für den endgültigen Wert zu konvertieren einer `String`, aber diesmal kann wiederhergestellt werden, da <xref:System.Text.StringBuilder>schneller ausführen können.</xref:System.Text.StringBuilder> </xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="9e950-116">It takes an extra instruction to create and initialize a <xref:System.Text.StringBuilder> object, and another instruction to convert its final value to a `String`, but you might recover this time because <xref:System.Text.StringBuilder> can perform faster.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e950-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e950-117">See Also</span></span>  
 <span data-ttu-id="9e950-118">[Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="9e950-118">[Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="9e950-119"> [Typen von Zeichenfolgenbearbeitungsmethoden in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md) </span><span class="sxs-lookup"><span data-stu-id="9e950-119"> [Types of String Manipulation Methods in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md) </span></span>  
<span data-ttu-id="9e950-120"> [Arithmetische Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="9e950-120"> [Arithmetic Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) </span></span>  
<span data-ttu-id="9e950-121"> [Vergleichsoperatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) </span><span class="sxs-lookup"><span data-stu-id="9e950-121"> [Comparison Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) </span></span>  
<span data-ttu-id="9e950-122"> [Logische und bitweise Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)</span><span class="sxs-lookup"><span data-stu-id="9e950-122"> [Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)</span></span>
