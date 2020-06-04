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
# <a name="-and--null-conditional-operators-visual-basic"></a>?. immer? () NULL-bedingte Operatoren (Visual Basic)

Testet den Wert des linken Operanden für NULL ( `Nothing` ), bevor ein Element Zugriffs `?.` Vorgang () oder Index ()- `?()` Vorgang durchgeführt wird. gibt zurück, `Nothing` Wenn der linke Operand als ausgewertet wird `Nothing` . Beachten Sie, dass der NULL bedingte Operator in Ausdrücken, die normalerweise Werttypen zurückgeben, eine zurückgibt <xref:System.Nullable%601> .

Diese Operatoren helfen Ihnen, weniger Code zum Behandeln von Null-Überprüfungen zu schreiben, insbesondere beim absteigend in Datenstrukturen. Beispiel:

```vb
' Nothing if customers is Nothing
Dim length As Integer? = customers?.Length

' Nothing if customers is Nothing
Dim first As Customer = customers?(0)

' Nothing if customers, the first customer, or Orders is Nothing
Dim count As Integer? = customers?(0)?.Orders?.Count()
```

Der Alternative Code für den ersten dieser Ausdrücke ohne einen NULL bedingten Operator lautet zum Vergleich:

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

Manchmal müssen Sie eine Aktion für ein Objekt durchführen, das möglicherweise NULL ist, basierend auf dem Wert eines booleschen Elements auf diesem Objekt (wie die boolesche Eigenschaft `IsAllowedFreeShipping` im folgenden Beispiel):

```vb
Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.

If customer IsNot Nothing AndAlso customer.IsAllowedFreeShipping Then
  ApplyFreeShippingToOrders(customer)
End If
```

Sie können den Code verkürzen und die manuelle Überprüfung auf NULL vermeiden, indem Sie den NULL-bedingten Operator wie folgt verwenden:

```vb
Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.

If customer?.IsAllowedFreeShipping Then ApplyFreeShippingToOrders(customer)
```

Die NULL-bedingten Operatoren sind Kurzschlussoperatoren.  Wenn ein Vorgang in einer Kette von bedingtem Element Zugriff und Index Vorgängen zurückgibt `Nothing` , wird der Rest der Ausführung der Kette angehalten.  Im folgenden Beispiel wird `C(E)` nicht ausgewertet, wenn `A` , `B` oder als ausgewertet wird `C` `Nothing` .

```vb
A?.B?.C?(E)
```

Eine andere Verwendung für den Zugriff auf NULL bedingte Member besteht darin, Delegaten auf Thread sichere Weise mit wesentlich geringerem Code aufzurufen.  Im folgenden Beispiel werden zwei Typen definiert: a `NewsBroadcaster` und `NewsReceiver` . News Items werden vom Delegaten an den Empfänger gesendet `NewsBroadcaster.SendNews` .

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

Wenn in der Aufruf Liste keine Elemente vorhanden sind, löst der Delegat `SendNews` `SendNews` einen aus <xref:System.NullReferenceException> . Vor bedingten NULL-Operatoren hat Code wie der folgende sichergestellt, dass die Aufruf Liste des Delegaten nicht war `Nothing` :

```vb
SendNews = SendNews.Combine({SendNews, client})
If SendNews IsNot Nothing Then
   SendNews("Just in...")
End If
```

Die neue Methode ist viel einfacher:

```vb
SendNews = SendNews.Combine({SendNews, client})
SendNews?.Invoke("Just in...")
```

Die neue Methode ist threadsicher, da der Compiler Code zum Auswerten von `SendNews` nur einmal generiert und das Ergebnis in einer temporären Variablen behält. Sie müssen die `Invoke`-Methode explizit aufrufen, da es keine Aufrufsyntax für Null-Bedingungsdelegate gibt `SendNews?(String)`.

## <a name="see-also"></a>Weitere Informationen

- [Operatoren (Visual Basic)](index.md)
- [Visual Basic-Programmierhandbuch](../../programming-guide/index.md)
- [Sprachreferenz zu Visual Basic](../index.md)
