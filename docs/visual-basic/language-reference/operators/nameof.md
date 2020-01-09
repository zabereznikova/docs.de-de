---
title: Nameof-Operator
description: Erfahren Sie, wie Sie den nameof-Operator in Visual Basic
ms.date: 10/27/2019
helpviewer_keywords:
- NameOf operator [Visual Basic]
ms.openlocfilehash: e7dd55bfd98b34449b9f1a35375198598f57b46f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347023"
---
# <a name="nameof-operator---visual-basic"></a>Nameof-Operator-Visual Basic

Der Operator `NameOf` ruft den Namen einer Variablen, eines Typs oder eines Members als Zeichenfolgenkonstante ab:

```vb
Console.WriteLine(NameOf(System.Collections.Generic))  ' output: Generic
Console.WriteLine(NameOf(List(Of Integer)))  ' output: List
Console.WriteLine(NameOf(List(Of Integer).Count))  ' output: Count
Console.WriteLine(NameOf(List(Of Integer).Add))  ' output: Add

Dim numbers As New List(Of Integer) From { 1, 2, 3 }
Console.WriteLine(NameOf(numbers))  ' output: numbers
Console.WriteLine(NameOf(numbers.Count))  ' output: Count
Console.WriteLine(NameOf(numbers.Add))  ' output: Add
```

Im Falle eines Typs und eines Namespace ist der erzeugte Name in der Regel nicht [vollqualifiziert](~/_csharplang/spec/basic-concepts.md#fully-qualified-names), wie im obigen Beispiel zu sehen.

Der Operator `NameOf` wird zur Kompilierzeit ausgewertet und hat zur Laufzeit keine Auswirkung.

Der Operator `NameOf` kann zur besseren Verwaltbarkeit des Argumentüberprüfungscodes beitragen:

```vb
Private _name As String

Public Property Name As String
    Get
        Return _name
    End Get
    Set
        If value Is Nothing Then
            Throw New ArgumentNullException(NameOf(value), $"{NameOf(name)} cannot be null.")
        End If
    End Set
End Property
```

Der `NameOf`-Operator ist in Visual Basic 14 und höher verfügbar.

## <a name="see-also"></a>Siehe auch

- [Sprachreferenz zu Visual Basic](../index.md)
- [Operatoren (Visual Basic)](index.md)
