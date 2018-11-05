---
title: NULL-bedingte Operatoren (C#-Referenz)
ms.date: 04/03/2015
helpviewer_keywords:
- null-conditional operators [C#]
- ?. operator [C#]
- ?[] operator [C#]
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
ms.openlocfilehash: 823b9dc886bf2448ca9da4ac640bfe56f90d3ff3
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50194851"
---
# <a name="-and--null-conditional-operators-c-and-visual-basic"></a><span data-ttu-id="eb068-102">?.</span><span class="sxs-lookup"><span data-stu-id="eb068-102">?.</span></span> <span data-ttu-id="eb068-103">und ?[]: NULL-bedingte Operatoren (C# und Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eb068-103">and ?[] null-conditional Operators (C# and Visual Basic)</span></span>
<span data-ttu-id="eb068-104">Diese Operatoren testen, ob der Wert des linken Operanden NULL ist, bevor ein Memberzugriffs- (`?.`) oder Indexzugriffsvorgang (`?[]`) ausgeführt wird. Sie geben `null` zurück, wenn der linke Operand `null` ergibt.</span><span class="sxs-lookup"><span data-stu-id="eb068-104">Tests the value of the left-hand operand for null before performing a member access (`?.`) or index (`?[]`) operation; returns `null` if the left-hand operand evaluates to `null`.</span></span> 

<span data-ttu-id="eb068-105">Mithilfe dieser Operatoren müssen Sie für die Prüfung auf null weniger Code schreiben, insbesondere beim tieferen Eindringen in Datenstrukturen.</span><span class="sxs-lookup"><span data-stu-id="eb068-105">These operators help you write less code to handle null checks, especially for descending into data structures.</span></span>  
  
```csharp  
int? length = customers?.Length; // null if customers is null   
Customer first = customers?[0];  // null if customers is null  
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
```  
  
 <span data-ttu-id="eb068-106">Die NULL-bedingten Operatoren sind Kurzschlussoperatoren.</span><span class="sxs-lookup"><span data-stu-id="eb068-106">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="eb068-107">Wenn ein Vorgang in einer Kette von bedingten Memberzugriffs- und Indexvorgängen NULL zurückgibt, wird die restliche Ausführung der Kette angehalten.</span><span class="sxs-lookup"><span data-stu-id="eb068-107">If one operation in a chain of conditional member access and index operations returns null, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="eb068-108">Im folgenden Beispiel wird `E` nicht ausgeführt, wenn das Ergebnis der Auswertung von `A`, `B` oder `C` NULL ist.</span><span class="sxs-lookup"><span data-stu-id="eb068-108">In the following example, `E` doesn't execute if `A`, `B`, or `C` evaluates to null.</span></span>
  
```csharp
A?.B?.C?.Do(E);
A?.B?.C?[E];
```

 <span data-ttu-id="eb068-109">Ein weiterer Verwendungszweck für den NULL-bedingten Memberzugriff ist das Aufrufen von Delegaten auf threadsichere Weise mit viel weniger Code.</span><span class="sxs-lookup"><span data-stu-id="eb068-109">Another use for the null-conditional member access is invoking delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="eb068-110">Die bisherige Methode erfordert Code wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="eb068-110">The old way requires code like the following:</span></span>  
  
```csharp  
var handler = this.PropertyChanged;  
if (handler != null)  
    handler(…);
```  
  
  
 <span data-ttu-id="eb068-111">Die neue Methode ist viel einfacher:</span><span class="sxs-lookup"><span data-stu-id="eb068-111">The new way is much simpler:</span></span>  
  
```csharp
PropertyChanged?.Invoke(…)  
```  

 <span data-ttu-id="eb068-112">Die neue Methode ist threadsicher, da der Compiler Code zum Auswerten von `PropertyChanged` nur einmal generiert und das Ergebnis in einer temporären Variablen behält.</span><span class="sxs-lookup"><span data-stu-id="eb068-112">The new way is thread-safe because the compiler generates code to evaluate `PropertyChanged` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="eb068-113">Sie müssen die `Invoke`-Methode explizit aufrufen, da es keine Aufrufsyntax für Null-Bedingungsdelegate gibt `PropertyChanged?(e)`.</span><span class="sxs-lookup"><span data-stu-id="eb068-113">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `PropertyChanged?(e)`.</span></span>  
  
## <a name="language-specifications"></a><span data-ttu-id="eb068-114">Sprachspezifikationen</span><span class="sxs-lookup"><span data-stu-id="eb068-114">Language Specifications</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="eb068-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb068-115">See Also</span></span>

- [<span data-ttu-id="eb068-116">?? (NULL-Sammeloperator)</span><span class="sxs-lookup"><span data-stu-id="eb068-116">?? (null-coalescing operator)</span></span>](null-coalescing-operator.md)  
- [<span data-ttu-id="eb068-117">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="eb068-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="eb068-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="eb068-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
