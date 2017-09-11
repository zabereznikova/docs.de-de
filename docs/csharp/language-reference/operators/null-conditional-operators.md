---
title: NULL-bedingte Operatoren (C# und Visual Basic)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 6118956a5681ddbeb110f6e01f090b85cdd65089
ms.openlocfilehash: 465a395a33c027132b7890e02d540438096e2073
ms.contentlocale: de-de
ms.lasthandoff: 08/23/2017

---
# <a name="null-conditional-operators-c-and-visual-basic"></a><span data-ttu-id="49763-102">NULL-bedingte Operatoren (C# und Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49763-102">Null-conditional Operators (C# and Visual Basic)</span></span>
<span data-ttu-id="49763-103">Wird für eine Prüfung auf null verwendet, bevor Sie eine Operation für den Memberzugriff (`?.`) oder die Indizierung (`?[`) ausführen.</span><span class="sxs-lookup"><span data-stu-id="49763-103">Used to test for null before performing a member access (`?.`) or index (`?[`) operation.</span></span>  <span data-ttu-id="49763-104">Mithilfe dieser Operatoren müssen Sie für die Prüfung auf null weniger Code schreiben, insbesondere beim tieferen Eindringen in Datenstrukturen.</span><span class="sxs-lookup"><span data-stu-id="49763-104">These operators help you write less code to handle null checks, especially for descending into data structures.</span></span>  
  
```csharp  
int? length = customers?.Length; // null if customers is null   
Customer first = customers?[0];  // null if customers is null  
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
```  
  
```vb  
Dim length = customers?.Length  ' null if customers is null  
Dim first as Customer = customers?(0)  ' null if customers is null  
Dim count as Integer? = customers?(0)?.Orders?.Count()  ' null if customers, the first customer, or Orders is null  
```  
  
 <span data-ttu-id="49763-105">Im letzten Beispiel wird veranschaulicht, dass die Null-Bedingungsoperatoren Kurzschlussoperatoren sind.</span><span class="sxs-lookup"><span data-stu-id="49763-105">The last example demonstrates that the null-condition operators are short-circuiting.</span></span>  <span data-ttu-id="49763-106">Wenn ein Vorgang in einer Kette von bedingten Memberzugriffs- und Indexvorgängen null zurückgibt, wird die restliche Ausführung der Kette angehalten.</span><span class="sxs-lookup"><span data-stu-id="49763-106">If one operation in a chain of conditional member access and index operation returns null, then the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="49763-107">Andere Vorgänge mit niedrigerer Rangfolge im Ausdruck werden fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="49763-107">Other operations with lower precedence in the expression continue.</span></span>  <span data-ttu-id="49763-108">Beispielsweise wird im folgenden Codebeispiel `E` in der zweiten Zeile ausgeführt, und die Operatoren `??` und `==` werden ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="49763-108">For example, `E` in the following executes in the second line, and the `??` and `==` operations execute.</span></span>  <span data-ttu-id="49763-109">In der ersten Zeile ruft `??` einen Kurzschluss hervor, und `E` wird nicht ausgeführt, wenn die linke Seite ungleich NULL ist.</span><span class="sxs-lookup"><span data-stu-id="49763-109">In the first line, the `??` short circuits and `E` does not execute when the left side evaluates to non-null.</span></span>
  
```csharp
A?.B?.C?[0] ?? E  
A?.B?.C?[0] == E  
```

```vb
A?.B?.C?(0) ?? E  
A?.B?.C?(0) == E  
```  
  
 <span data-ttu-id="49763-110">Ein weiterer Verwendungszweck für den Null-Bedingungsmemberzugriff ist das Aufrufen von Delegaten auf threadsichere Weise mit viel weniger Code.</span><span class="sxs-lookup"><span data-stu-id="49763-110">Another use for the null-condition member access is invoking delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="49763-111">Die bisherige Methode erfordert Code wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="49763-111">The old way requires code like the following:</span></span>  
  
```csharp  
var handler = this.PropertyChanged;  
if (handler != null)  
    handler(…);
```  
  
```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
```  
  
 <span data-ttu-id="49763-112">Die neue Methode ist viel einfacher:</span><span class="sxs-lookup"><span data-stu-id="49763-112">The new way is much simpler:</span></span>  
  
```csharp
PropertyChanged?.Invoke(e)  
```  

```vb
PropertyChanged?.Invoke(e)
```  
  
 <span data-ttu-id="49763-113">Die neue Methode ist threadsicher, da der Compiler Code zum Auswerten von `PropertyChanged` nur einmal generiert und das Ergebnis in einer temporären Variablen behält.</span><span class="sxs-lookup"><span data-stu-id="49763-113">The new way is thread-safe because the compiler generates code to evaluate `PropertyChanged` one time only, keeping the result in a temporary variable.</span></span>  
  
 <span data-ttu-id="49763-114">Sie müssen die `Invoke`-Methode explizit aufrufen, da es keine Aufrufsyntax für Null-Bedingungsdelegate gibt `PropertyChanged?(e)`.</span><span class="sxs-lookup"><span data-stu-id="49763-114">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `PropertyChanged?(e)`.</span></span>  <span data-ttu-id="49763-115">Es gab zu viele mehrdeutige Analysesituationen.</span><span class="sxs-lookup"><span data-stu-id="49763-115">There were too many ambiguous parsing situations to allow it.</span></span>  
  
## <a name="language-specifications"></a><span data-ttu-id="49763-116">Sprachspezifikationen</span><span class="sxs-lookup"><span data-stu-id="49763-116">Language Specifications</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
 <span data-ttu-id="49763-117">Weitere Informationen finden Sie in der [Sprachreferenz für Visual Basic](../../../visual-basic/language-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="49763-117">For more information, see the [Visual Basic Language Reference](../../../visual-basic/language-reference/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49763-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49763-118">See Also</span></span>  
 <span data-ttu-id="49763-119">[?? (Nullzusammensetzungsoperator)](null-conditional-operator.md) </span><span class="sxs-lookup"><span data-stu-id="49763-119">[?? (null-coalescing operator)](null-conditional-operator.md) </span></span>  
 <span data-ttu-id="49763-120">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="49763-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="49763-121">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="49763-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="49763-122">[Sprachreferenz zu Visual Basic](../../../visual-basic/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="49763-122">[Visual Basic Language Reference](../../../visual-basic/language-reference/index.md) </span></span>  
 [<span data-ttu-id="49763-123">Visual Basic-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="49763-123">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)

