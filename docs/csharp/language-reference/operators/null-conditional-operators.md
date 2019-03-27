---
title: NULL-Bedingte Operatoren – C#-Referenz
ms.custom: seodec18
ms.date: 04/03/2015
helpviewer_keywords:
- null-conditional operators [C#]
- ?. operator [C#]
- ?[] operator [C#]
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
ms.openlocfilehash: 9cbf8a0f860f0bc0328cd98e558b20b5e8e1bf8f
ms.sourcegitcommit: 344d82456f27d09a210671214a14cfd7daf1f97c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2019
ms.locfileid: "58348842"
---
# <a name="-and--null-conditional-operators-c-reference"></a>?. und ?[] NULL-bedingte Operatoren (C#-Referenz)

Diese Operatoren testen, ob der Wert des linken Operanden NULL ist, bevor ein Memberzugriffs- (`?.`) oder Indexzugriffsvorgang (`?[]`) ausgeführt wird. Sie geben `null` zurück, wenn der linke Operand `null` ergibt.

Mithilfe dieser Operatoren müssen Sie für die Prüfung auf null weniger Code schreiben, insbesondere beim tieferen Eindringen in Datenstrukturen.

```csharp
int? length = customers?.Length; // null if customers is null
Customer first = customers?[0];  // null if customers is null
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null
```

Die NULL-bedingten Operatoren sind Kurzschlussoperatoren.  Wenn ein Vorgang in einer Kette von bedingten Memberzugriffs- und Indexvorgängen NULL zurückgibt, wird die restliche Ausführung der Kette angehalten.  Im folgenden Beispiel wird `E` nicht ausgeführt, wenn das Ergebnis der Auswertung von `A`, `B` oder `C` NULL ist.

```csharp
A?.B?.C?.Do(E);
A?.B?.C?[E];
```

Ein weiterer Verwendungszweck für den NULL-bedingten Memberzugriff ist das Aufrufen von Delegaten auf threadsichere Weise mit viel weniger Code.  Die bisherige Methode erfordert Code wie den folgenden:

```csharp
var handler = this.PropertyChanged;
if (handler != null)
    handler(…);
```

Die neue Methode ist viel einfacher:

```csharp
PropertyChanged?.Invoke(…)
```

Die neue Methode ist threadsicher, da der Compiler Code zum Auswerten von `PropertyChanged` nur einmal generiert und das Ergebnis in einer temporären Variablen behält. Sie müssen die `Invoke`-Methode explizit aufrufen, da es keine Aufrufsyntax für Null-Bedingungsdelegate gibt `PropertyChanged?(e)`.

## <a name="language-specifications"></a>Sprachspezifikationen

Weitere Informationen finden Sie unter [NULL-bedingter Operator](~/_csharplang/spec/expressions.md#null-conditional-operator) in der [C#-Sprachspezifikation](../language-specification/index.md). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.

## <a name="see-also"></a>Siehe auch

- [?? (NULL-Sammeloperator)](null-coalescing-operator.md)
- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)