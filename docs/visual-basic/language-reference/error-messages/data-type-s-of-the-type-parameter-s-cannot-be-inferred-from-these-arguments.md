---
title: Die Datentypen der Typparameter können nicht von diesen Argumenten abgeleitet werden
ms.date: 07/20/2015
f1_keywords:
- bc36644
- bc36647
- vbc36647
- vbc36644
helpviewer_keywords:
- BC36644
- BC36647
ms.assetid: 0e0050f2-2039-4311-b260-f0ebfde84189
ms.openlocfilehash: 85798e6453bc6cea6174ecc536b35835865e0459
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163453"
---
# <a name="bc36647-and-bc36644-data-types-of-the-type-parameters-cannot-be-inferred-from-these-arguments"></a>BC36647 und BC36644: die Datentypen der Typparameter können nicht von diesen Argumenten abgeleitet werden.

Die Datentypen der Typparameter können nicht von diesen Argumenten abgeleitet werden. Sie können diesen Fehler möglicherweise beheben, indem Sie die Datentypen explizit angeben.

Dieser Fehler tritt auf, wenn bei der Überladungsauflösung ein Fehler auftritt. Er wird als untergeordnete Meldung angezeigt, die den Grund für die Entfernung einer bestimmten Überladung angibt. In der Fehlermeldung wird erläutert, dass der Compiler den Typrückschluss nicht zum Suchen von Datentypen für die Typparameter verwenden kann.

> [!NOTE]
> Wenn die Angabe von Argumenten keine Option ist (z. B. für Abfrageoperatoren in Abfrageausdrücken), wird nur der erste Satz der Fehlermeldung angezeigt.

Im folgenden Code wird der Fehler veranschaulicht.

```vb
Module Module1

    Sub Main()

        '' Not Valid.
        'OverloadedGenericMethod("Hello", "World")

    End Sub

    Sub OverloadedGenericMethod(Of T)(ByVal x As String,
                                      ByVal y As InterfaceExample(Of T))
    End Sub

    Sub OverloadedGenericMethod(Of T, R)(ByVal x As T,
                                         ByVal y As InterfaceExample(Of R))
    End Sub

End Module

Interface InterfaceExample(Of T)
End Interface
```

**Fehler-ID:** BC36647 und BC36644

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

Anstelle des Typrückschlusses können Sie einen Datentyp für den oder die Typparameter angeben.

## <a name="see-also"></a>Siehe auch

- [Gelockerte Delegatenkonvertierung](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Generic Procedures in Visual Basic](../../programming-guide/language-features/data-types/generic-procedures.md)
- [Typkonvertierung in Visual Basic](../../programming-guide/language-features/data-types/type-conversions.md)
