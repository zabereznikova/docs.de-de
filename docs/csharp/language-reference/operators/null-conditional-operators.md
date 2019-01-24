---
title: NULL-Bedingte Operatoren – C#-Referenz
ms.custom: seodec18
ms.date: 04/03/2015
helpviewer_keywords:
- null-conditional operators [C#]
- ?. operator [C#]
- ?[] operator [C#]
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
ms.openlocfilehash: 38298cded904cbfedeaf3c6b66c74d610d714902
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333238"
---
# <a name="-and--null-conditional-operators-c-and-visual-basic"></a><span data-ttu-id="84964-102">?.</span><span class="sxs-lookup"><span data-stu-id="84964-102">?.</span></span> <span data-ttu-id="84964-103">und ?[]: NULL-Bedingte Operatoren (C# und Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84964-103">and ?[] null-conditional operators (C# and Visual Basic)</span></span>

<span data-ttu-id="84964-104">Diese Operatoren testen, ob der Wert des linken Operanden NULL ist, bevor ein Memberzugriffs- (`?.`) oder Indexzugriffsvorgang (`?[]`) ausgeführt wird. Sie geben `null` zurück, wenn der linke Operand `null` ergibt.</span><span class="sxs-lookup"><span data-stu-id="84964-104">Tests the value of the left-hand operand for null before performing a member access (`?.`) or index (`?[]`) operation; returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="84964-105">Mithilfe dieser Operatoren müssen Sie für die Prüfung auf null weniger Code schreiben, insbesondere beim tieferen Eindringen in Datenstrukturen.</span><span class="sxs-lookup"><span data-stu-id="84964-105">These operators help you write less code to handle null checks, especially for descending into data structures.</span></span>

```csharp
int? length = customers?.Length; // null if customers is null
Customer first = customers?[0];  // null if customers is null
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null
```

<span data-ttu-id="84964-106">Die NULL-bedingten Operatoren sind Kurzschlussoperatoren.</span><span class="sxs-lookup"><span data-stu-id="84964-106">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="84964-107">Wenn ein Vorgang in einer Kette von bedingten Memberzugriffs- und Indexvorgängen NULL zurückgibt, wird die restliche Ausführung der Kette angehalten.</span><span class="sxs-lookup"><span data-stu-id="84964-107">If one operation in a chain of conditional member access and index operations returns null, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="84964-108">Im folgenden Beispiel wird `E` nicht ausgeführt, wenn das Ergebnis der Auswertung von `A`, `B` oder `C` NULL ist.</span><span class="sxs-lookup"><span data-stu-id="84964-108">In the following example, `E` doesn't execute if `A`, `B`, or `C` evaluates to null.</span></span>

```csharp
A?.B?.C?.Do(E);
A?.B?.C?[E];
```

<span data-ttu-id="84964-109">Ein weiterer Verwendungszweck für den NULL-bedingten Memberzugriff ist das Aufrufen von Delegaten auf threadsichere Weise mit viel weniger Code.</span><span class="sxs-lookup"><span data-stu-id="84964-109">Another use for the null-conditional member access is invoking delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="84964-110">Die bisherige Methode erfordert Code wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="84964-110">The old way requires code like the following:</span></span>

```csharp
var handler = this.PropertyChanged;
if (handler != null)
    handler(…);
```

<span data-ttu-id="84964-111">Die neue Methode ist viel einfacher:</span><span class="sxs-lookup"><span data-stu-id="84964-111">The new way is much simpler:</span></span>

```csharp
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="84964-112">Die neue Methode ist threadsicher, da der Compiler Code zum Auswerten von `PropertyChanged` nur einmal generiert und das Ergebnis in einer temporären Variablen behält.</span><span class="sxs-lookup"><span data-stu-id="84964-112">The new way is thread-safe because the compiler generates code to evaluate `PropertyChanged` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="84964-113">Sie müssen die `Invoke`-Methode explizit aufrufen, da es keine Aufrufsyntax für Null-Bedingungsdelegate gibt `PropertyChanged?(e)`.</span><span class="sxs-lookup"><span data-stu-id="84964-113">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `PropertyChanged?(e)`.</span></span>

## <a name="language-specifications"></a><span data-ttu-id="84964-114">Sprachspezifikationen</span><span class="sxs-lookup"><span data-stu-id="84964-114">Language specifications</span></span>

<span data-ttu-id="84964-115">Weitere Informationen finden Sie unter [NULL-bedingter Operator](~/_csharplang/spec/expressions.md#null-conditional-operator) in der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="84964-115">For more information, see [Null-conditional operator](~/_csharplang/spec/expressions.md#null-conditional-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="84964-116">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="84964-116">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="84964-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84964-117">See also</span></span>

- [<span data-ttu-id="84964-118">?? (NULL-Sammeloperator)</span><span class="sxs-lookup"><span data-stu-id="84964-118">?? (null-coalescing operator)</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="84964-119">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="84964-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="84964-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="84964-120">C# Programming Guide</span></span>](../../programming-guide/index.md)