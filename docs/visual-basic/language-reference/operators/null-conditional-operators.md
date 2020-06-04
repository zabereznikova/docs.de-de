---
title: NULL-bedingte Operatoren
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: bffbba859968e0a050397cd9e685c142f801798a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401471"
---
# <a name="-and--null-conditional-operators-visual-basic"></a><span data-ttu-id="5a556-102">?.</span><span class="sxs-lookup"><span data-stu-id="5a556-102">?.</span></span> <span data-ttu-id="5a556-103">immer? () NULL-bedingte Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a556-103">and ?() null-conditional operators (Visual Basic)</span></span>

<span data-ttu-id="5a556-104">Testet den Wert des linken Operanden für NULL ( `Nothing` ), bevor ein Element Zugriffs `?.` Vorgang () oder Index ()- `?()` Vorgang durchgeführt wird. gibt zurück, `Nothing` Wenn der linke Operand als ausgewertet wird `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="5a556-104">Tests the value of the left-hand operand for null (`Nothing`) before performing a member access (`?.`) or index (`?()`) operation; returns `Nothing` if the left-hand operand evaluates to `Nothing`.</span></span> <span data-ttu-id="5a556-105">Beachten Sie, dass der NULL bedingte Operator in Ausdrücken, die normalerweise Werttypen zurückgeben, eine zurückgibt <xref:System.Nullable%601> .</span><span class="sxs-lookup"><span data-stu-id="5a556-105">Note that in expressions that ordinarily return value types, the null-conditional operator returns a <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="5a556-106">Diese Operatoren helfen Ihnen, weniger Code zum Behandeln von Null-Überprüfungen zu schreiben, insbesondere beim absteigend in Datenstrukturen.</span><span class="sxs-lookup"><span data-stu-id="5a556-106">These operators help you write less code to handle null checks, especially when descending into data structures.</span></span> <span data-ttu-id="5a556-107">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5a556-107">For example:</span></span>

```vb
' Nothing if customers is Nothing
Dim length As Integer? = customers?.Length

' Nothing if customers is Nothing
Dim first As Customer = customers?(0)

' Nothing if customers, the first customer, or Orders is Nothing
Dim count As Integer? = customers?(0)?.Orders?.Count()
```

<span data-ttu-id="5a556-108">Der Alternative Code für den ersten dieser Ausdrücke ohne einen NULL bedingten Operator lautet zum Vergleich:</span><span class="sxs-lookup"><span data-stu-id="5a556-108">For comparison, the alternative code for the first of these expressions without a null-conditional operator is:</span></span>

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

<span data-ttu-id="5a556-109">Manchmal müssen Sie eine Aktion für ein Objekt durchführen, das möglicherweise NULL ist, basierend auf dem Wert eines booleschen Elements auf diesem Objekt (wie die boolesche Eigenschaft `IsAllowedFreeShipping` im folgenden Beispiel):</span><span class="sxs-lookup"><span data-stu-id="5a556-109">Sometimes you need to take an action on an object that may be null, based on the value of a Boolean member on that object (like the Boolean property `IsAllowedFreeShipping` in the following example):</span></span>

```vb
Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.

If customer IsNot Nothing AndAlso customer.IsAllowedFreeShipping Then
  ApplyFreeShippingToOrders(customer)
End If
```

<span data-ttu-id="5a556-110">Sie können den Code verkürzen und die manuelle Überprüfung auf NULL vermeiden, indem Sie den NULL-bedingten Operator wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="5a556-110">You can shorten your code and avoid manually checking for null by using the null-conditional operator as follows:</span></span>

```vb
Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.

If customer?.IsAllowedFreeShipping Then ApplyFreeShippingToOrders(customer)
```

<span data-ttu-id="5a556-111">Die NULL-bedingten Operatoren sind Kurzschlussoperatoren.</span><span class="sxs-lookup"><span data-stu-id="5a556-111">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="5a556-112">Wenn ein Vorgang in einer Kette von bedingtem Element Zugriff und Index Vorgängen zurückgibt `Nothing` , wird der Rest der Ausführung der Kette angehalten.</span><span class="sxs-lookup"><span data-stu-id="5a556-112">If one operation in a chain of conditional member access and index operations returns `Nothing`, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="5a556-113">Im folgenden Beispiel wird `C(E)` nicht ausgewertet, wenn `A` , `B` oder als ausgewertet wird `C` `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="5a556-113">In the following example, `C(E)` isn't evaluated if `A`, `B`, or `C` evaluates to `Nothing`.</span></span>

```vb
A?.B?.C?(E)
```

<span data-ttu-id="5a556-114">Eine andere Verwendung für den Zugriff auf NULL bedingte Member besteht darin, Delegaten auf Thread sichere Weise mit wesentlich geringerem Code aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="5a556-114">Another use for null-conditional member access is to invoke delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="5a556-115">Im folgenden Beispiel werden zwei Typen definiert: a `NewsBroadcaster` und `NewsReceiver` .</span><span class="sxs-lookup"><span data-stu-id="5a556-115">The following example defines two types, a `NewsBroadcaster` and a `NewsReceiver`.</span></span> <span data-ttu-id="5a556-116">News Items werden vom Delegaten an den Empfänger gesendet `NewsBroadcaster.SendNews` .</span><span class="sxs-lookup"><span data-stu-id="5a556-116">News items are sent to the receiver by the `NewsBroadcaster.SendNews` delegate.</span></span>

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

<span data-ttu-id="5a556-117">Wenn in der Aufruf Liste keine Elemente vorhanden sind, löst der Delegat `SendNews` `SendNews` einen aus <xref:System.NullReferenceException> .</span><span class="sxs-lookup"><span data-stu-id="5a556-117">If there are no elements in the `SendNews` invocation list, the `SendNews` delegate throws a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="5a556-118">Vor bedingten NULL-Operatoren hat Code wie der folgende sichergestellt, dass die Aufruf Liste des Delegaten nicht war `Nothing` :</span><span class="sxs-lookup"><span data-stu-id="5a556-118">Before null conditional operators, code like the following ensured that the delegate invocation list was not `Nothing`:</span></span>

```vb
SendNews = SendNews.Combine({SendNews, client})
If SendNews IsNot Nothing Then
   SendNews("Just in...")
End If
```

<span data-ttu-id="5a556-119">Die neue Methode ist viel einfacher:</span><span class="sxs-lookup"><span data-stu-id="5a556-119">The new way is much simpler:</span></span>

```vb
SendNews = SendNews.Combine({SendNews, client})
SendNews?.Invoke("Just in...")
```

<span data-ttu-id="5a556-120">Die neue Methode ist threadsicher, da der Compiler Code zum Auswerten von `SendNews` nur einmal generiert und das Ergebnis in einer temporären Variablen behält.</span><span class="sxs-lookup"><span data-stu-id="5a556-120">The new way is thread-safe because the compiler generates code to evaluate `SendNews` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="5a556-121">Sie müssen die `Invoke`-Methode explizit aufrufen, da es keine Aufrufsyntax für Null-Bedingungsdelegate gibt `SendNews?(String)`.</span><span class="sxs-lookup"><span data-stu-id="5a556-121">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `SendNews?(String)`.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a556-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5a556-122">See also</span></span>

- [<span data-ttu-id="5a556-123">Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a556-123">Operators (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="5a556-124">Visual Basic-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="5a556-124">Visual Basic Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5a556-125">Sprachreferenz zu Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5a556-125">Visual Basic Language Reference</span></span>](../index.md)
