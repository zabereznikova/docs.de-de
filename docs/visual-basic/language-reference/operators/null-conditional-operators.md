---
title: NULL-Bedingte Operatoren (Visual Basic)
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: c29362a1e335e18b66821919e266b1ce57774692
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50195991"
---
# <a name="-and--null-conditional-operators-visual-basic"></a>?. und? ()-Null-Bedingte Operatoren (Visual Basic)

Testet, ob der Wert des linken Operanden für Null-Zeichen (`Nothing`) vor dem Ausführen einer Memberzugriff (`?.`) oder eines Indexes (`?()`) Vorgang; gibt `Nothing` , wenn der linke Operand `Nothing`. Beachten Sie, dass in den Ausdrücken, die normalerweise Werttypen zurückgibt, der Null-bedingten Operator gibt einen <xref:System.Nullable%601>.

Diese Operatoren können Sie weniger Code zum Behandeln von null-Überprüfungen, insbesondere dann, wenn in Datenstrukturen absteigend zu schreiben. Zum Beispiel:

```vb
Dim length As Integer? = customers?.Length  ' Nothing if customers is Nothing  
Dim first As Customer = customers?(0)  ' Nothing if customers is Nothing  
Dim count As Integer? = customers?(0)?.Orders?.Count()  ' Nothing if customers, the first customer, or Orders is Nothing  
```

Zum Vergleich wird die alternative Code für das erste der folgenden Ausdrücke ohne ein Null-bedingten Operator:

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

Die NULL-bedingten Operatoren sind Kurzschlussoperatoren.  Wenn ein Vorgang in einer Kette von Zugriffs- und Index-Vorgänge der bedingte Member "Nothing" zurückgibt, beendet die restliche Ausführung der Kette.  Im folgenden Beispiel wird nicht C(E) ausgewertet, wenn `A`, `B`, oder `C` zu "Nothing" ausgewertet wird.

```vb
A?.B?.C?(E);
```

Ein weiterer Verwendungszweck für den bedingten Null-Memberzugriff ist zum Aufrufen von Delegaten auf threadsichere Weise mit viel weniger Code.  Die bisherige Methode erfordert Code wie den folgenden:  

```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
```

Die neue Methode ist viel einfacher:  

```vb
PropertyChanged?.Invoke(…)
```

Die neue Methode ist threadsicher, da der Compiler Code zum Auswerten von `PropertyChanged` nur einmal generiert und das Ergebnis in einer temporären Variablen behält. Sie müssen die `Invoke`-Methode explizit aufrufen, da es keine Aufrufsyntax für Null-Bedingungsdelegate gibt `PropertyChanged?(e)`.  

## <a name="see-also"></a>Siehe auch

- [Operatoren (Visual Basic)](index.md)
- [Visual Basic-Programmierhandbuch](../../../visual-basic/programming-guide/index.md)
- [Sprachreferenz zu Visual Basic](../../../visual-basic/language-reference/index.md)  
