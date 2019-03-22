---
title: NULL-Bedingte Operatoren (Visual Basic)
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: b83435b8448b53eca63aac0519e9eed2f7dfa9f3
ms.sourcegitcommit: 344d82456f27d09a210671214a14cfd7daf1f97c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2019
ms.locfileid: "58348764"
---
# <a name="-and--null-conditional-operators-visual-basic"></a><span data-ttu-id="c18e4-102">?.</span><span class="sxs-lookup"><span data-stu-id="c18e4-102">?.</span></span> <span data-ttu-id="c18e4-103">und? ()-Null-Bedingte Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c18e4-103">and ?() null-conditional operators (Visual Basic)</span></span>

<span data-ttu-id="c18e4-104">Testet, ob der Wert des linken Operanden für Null-Zeichen (`Nothing`) vor dem Ausführen einer Memberzugriff (`?.`) oder eines Indexes (`?()`) Vorgang; gibt `Nothing` , wenn der linke Operand `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="c18e4-104">Tests the value of the left-hand operand for null (`Nothing`) before performing a member access (`?.`) or index (`?()`) operation; returns `Nothing` if the left-hand operand evaluates to `Nothing`.</span></span> <span data-ttu-id="c18e4-105">Beachten Sie, dass die in Ausdrücken, die normalerweise Wert zurückgeben, die Null-bedingten Operator gibt einen <xref:System.Nullable%601>.</span><span class="sxs-lookup"><span data-stu-id="c18e4-105">Note that in expressions that ordinarily return value types, the null-conditional operator returns a <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="c18e4-106">Diese Operatoren können Sie weniger Code zum Behandeln von null-Überprüfungen, insbesondere dann, wenn in Datenstrukturen absteigend zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="c18e4-106">These operators help you write less code to handle null checks, especially when descending into data structures.</span></span> <span data-ttu-id="c18e4-107">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c18e4-107">For example:</span></span>

```vb
' Nothing if customers is Nothing  
Dim length As Integer? = customers?.Length  

' Nothing if customers is Nothing
Dim first As Customer = customers?(0)

' Nothing if customers, the first customer, or Orders is Nothing
Dim count As Integer? = customers?(0)?.Orders?.Count()   
```

<span data-ttu-id="c18e4-108">Zum Vergleich wird die alternative Code für das erste der folgenden Ausdrücke ohne ein Null-bedingten Operator:</span><span class="sxs-lookup"><span data-stu-id="c18e4-108">For comparison, the alternative code for the first of these expressions without a null-conditional operator is:</span></span>

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

<span data-ttu-id="c18e4-109">Die NULL-bedingten Operatoren sind Kurzschlussoperatoren.</span><span class="sxs-lookup"><span data-stu-id="c18e4-109">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="c18e4-110">Wenn ein Vorgang in einer Kette von Zugriffs- und Index-Vorgänge der bedingte Member zurückgibt `Nothing`, die restlichen der Kette Ausführung beendet.</span><span class="sxs-lookup"><span data-stu-id="c18e4-110">If one operation in a chain of conditional member access and index operations returns `Nothing`, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="c18e4-111">Im folgenden Beispiel `C(E)` wird nicht ausgewertet, wenn `A`, `B`, oder `C` ergibt `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="c18e4-111">In the following example, `C(E)` isn't evaluated if `A`, `B`, or `C` evaluates to `Nothing`.</span></span>

```vb
A?.B?.C?(E);
```

<span data-ttu-id="c18e4-112">Ein weiterer Verwendungszweck für den bedingten Null-Memberzugriff ist zum Aufrufen von Delegaten auf threadsichere Weise mit viel weniger Code.</span><span class="sxs-lookup"><span data-stu-id="c18e4-112">Another use for null-conditional member access is to invoke delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="c18e4-113">Das folgende Beispiel definiert zwei Typen: ein `NewsBroadcaster` und `NewsReceiver`.</span><span class="sxs-lookup"><span data-stu-id="c18e4-113">The following example defines two types, a `NewsBroadcaster` and a `NewsReceiver`.</span></span> <span data-ttu-id="c18e4-114">Nachrichtenelemente gesendet werden, an den Empfänger, durch die `NewsBroadcaster.SendNews` delegieren.</span><span class="sxs-lookup"><span data-stu-id="c18e4-114">News items are sent to the receiver by the `NewsBroadcaster.SendNews` delegate.</span></span>

```vb
Public Module NewsBroadcaster
   Dim SendNews As Action(Of String) 

   Public Sub Main()
      Dim rec As New NewsReceiver()
      Dim rec2 As New NewsReceiver()
      SendNews?.Invoke("Just in: A newsworthy item...")
   End Sub

   Public Sub Register(client As Action(Of String))
      SendNews = SendNews.Combine({SendNews, client})
   End Sub
End Module

Public Class NewsReceiver
   Public Sub New()
      NewsBroadcaster.Register(AddressOf Me.DisplayNews)
   End Sub

   Public Sub DisplayNews(newsItem As String)
      Console.WriteLine(newsItem)
   End Sub
End Class
```

<span data-ttu-id="c18e4-115">Wenn keine in Elemente der `SendNews` Aufrufliste, die `SendNews` Delegat löst eine <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="c18e4-115">If there are no elements in the `SendNews` invocation list, the `SendNews` delegate throws a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="c18e4-116">Vor dem null-Bedingte Operatoren, wie code zu Folgendes sichergestellt, dass die Aufrufliste des Delegaten nicht war `Nothing`:</span><span class="sxs-lookup"><span data-stu-id="c18e4-116">Before null conditional operators, code like the following ensured that the delegate invocation list was not `Nothing`:</span></span>

```vb  
SendNews = SendNews.Combine({SendNews, client})  
If SendNews IsNot Nothing Then 
   SendNews("Just in...")
End If
```

<span data-ttu-id="c18e4-117">Die neue Methode ist viel einfacher:</span><span class="sxs-lookup"><span data-stu-id="c18e4-117">The new way is much simpler:</span></span>  

```vb
SendNews = SendNews.Combine({SendNews, client})  
SendNews?.Invoke("Just in...")
```

<span data-ttu-id="c18e4-118">Die neue Methode ist threadsicher, da der Compiler Code zum Auswerten von `SendNews` nur einmal generiert und das Ergebnis in einer temporären Variablen behält.</span><span class="sxs-lookup"><span data-stu-id="c18e4-118">The new way is thread-safe because the compiler generates code to evaluate `SendNews` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="c18e4-119">Sie müssen die `Invoke`-Methode explizit aufrufen, da es keine Aufrufsyntax für Null-Bedingungsdelegate gibt `SendNews?(String)`.</span><span class="sxs-lookup"><span data-stu-id="c18e4-119">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `SendNews?(String)`.</span></span>  

## <a name="see-also"></a><span data-ttu-id="c18e4-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c18e4-120">See also</span></span>

- [<span data-ttu-id="c18e4-121">Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c18e4-121">Operators (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="c18e4-122">Visual Basic-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c18e4-122">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="c18e4-123">Sprachreferenz zu Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c18e4-123">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)
