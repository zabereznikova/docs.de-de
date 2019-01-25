---
title: NULL-Bedingte Operatoren (Visual Basic)
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: d30d452a7c140a0c56529386b14ef3a3512df490
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722152"
---
# <a name="-and--null-conditional-operators-visual-basic"></a><span data-ttu-id="155c4-102">?.</span><span class="sxs-lookup"><span data-stu-id="155c4-102">?.</span></span> <span data-ttu-id="155c4-103">und? ()-Null-Bedingte Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="155c4-103">and ?() null-conditional operators (Visual Basic)</span></span>

<span data-ttu-id="155c4-104">Testet, ob der Wert des linken Operanden für Null-Zeichen (`Nothing`) vor dem Ausführen einer Memberzugriff (`?.`) oder eines Indexes (`?()`) Vorgang; gibt `Nothing` , wenn der linke Operand `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="155c4-104">Tests the value of the left-hand operand for null (`Nothing`) before performing a member access (`?.`) or index (`?()`) operation; returns `Nothing` if the left-hand operand evaluates to `Nothing`.</span></span> <span data-ttu-id="155c4-105">Beachten Sie, dass in den Ausdrücken, die normalerweise Werttypen zurückgibt, der Null-bedingten Operator gibt einen <xref:System.Nullable%601>.</span><span class="sxs-lookup"><span data-stu-id="155c4-105">Note that, in the expressions that would ordinarily return value types, the null-conditional operator returns a <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="155c4-106">Diese Operatoren können Sie weniger Code zum Behandeln von null-Überprüfungen, insbesondere dann, wenn in Datenstrukturen absteigend zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="155c4-106">These operators help you write less code to handle null checks, especially when descending into data structures.</span></span> <span data-ttu-id="155c4-107">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="155c4-107">For example:</span></span>

```vb
Dim length As Integer? = customers?.Length  ' Nothing if customers is Nothing  
Dim first As Customer = customers?(0)  ' Nothing if customers is Nothing  
Dim count As Integer? = customers?(0)?.Orders?.Count()  ' Nothing if customers, the first customer, or Orders is Nothing  
```

<span data-ttu-id="155c4-108">Zum Vergleich wird die alternative Code für das erste der folgenden Ausdrücke ohne ein Null-bedingten Operator:</span><span class="sxs-lookup"><span data-stu-id="155c4-108">For comparison, the alternative code for the first of these expressions without a null-conditional operator is:</span></span>

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

<span data-ttu-id="155c4-109">Die NULL-bedingten Operatoren sind Kurzschlussoperatoren.</span><span class="sxs-lookup"><span data-stu-id="155c4-109">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="155c4-110">Wenn ein Vorgang in einer Kette von Zugriffs- und Index-Vorgänge der bedingte Member "Nothing" zurückgibt, beendet die restliche Ausführung der Kette.</span><span class="sxs-lookup"><span data-stu-id="155c4-110">If one operation in a chain of conditional member access and index operations returns Nothing, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="155c4-111">Im folgenden Beispiel wird nicht C(E) ausgewertet, wenn `A`, `B`, oder `C` zu "Nothing" ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="155c4-111">In the following example, C(E) isn't evaluated if `A`, `B`, or `C` evaluates to Nothing.</span></span>

```vb
A?.B?.C?(E);
```

<span data-ttu-id="155c4-112">Ein weiterer Verwendungszweck für den bedingten Null-Memberzugriff ist zum Aufrufen von Delegaten auf threadsichere Weise mit viel weniger Code.</span><span class="sxs-lookup"><span data-stu-id="155c4-112">Another use for null-conditional member access is to invoke delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="155c4-113">Die bisherige Methode erfordert Code wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="155c4-113">The old way requires code like the following:</span></span>  

```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
```

<span data-ttu-id="155c4-114">Die neue Methode ist viel einfacher:</span><span class="sxs-lookup"><span data-stu-id="155c4-114">The new way is much simpler:</span></span>  

```vb
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="155c4-115">Die neue Methode ist threadsicher, da der Compiler Code zum Auswerten von `PropertyChanged` nur einmal generiert und das Ergebnis in einer temporären Variablen behält.</span><span class="sxs-lookup"><span data-stu-id="155c4-115">The new way is thread-safe because the compiler generates code to evaluate `PropertyChanged` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="155c4-116">Sie müssen die `Invoke`-Methode explizit aufrufen, da es keine Aufrufsyntax für Null-Bedingungsdelegate gibt `PropertyChanged?(e)`.</span><span class="sxs-lookup"><span data-stu-id="155c4-116">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `PropertyChanged?(e)`.</span></span>  

## <a name="see-also"></a><span data-ttu-id="155c4-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="155c4-117">See also</span></span>

- [<span data-ttu-id="155c4-118">Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="155c4-118">Operators (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="155c4-119">Visual Basic-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="155c4-119">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="155c4-120">Sprachreferenz zu Visual Basic</span><span class="sxs-lookup"><span data-stu-id="155c4-120">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)
