---
title: Methoden von „System.Nullable(Of T)“ können nicht als Operanden des Operators „AddressOf“ verwendet werden
ms.date: 07/20/2015
f1_keywords:
- vbc32126
- bc32126
helpviewer_keywords:
- BC32126
ms.assetid: 2325668b-e2ad-40ee-a1ec-30450236c20d
ms.openlocfilehash: 173cf19537e3f9ffc4cff6cef71f34b6d365e5d3
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160391"
---
# <a name="bc32126-methods-of-systemnullableof-t-cannot-be-used-as-operands-of-the-addressof-operator"></a>BC32126: die Methoden von "System. Nullable (of T)" können nicht als Operanden des Operators "AddressOf" verwendet werden.

Eine-Anweisung verwendet den- `AddressOf` Operator mit einem Operanden, der eine Prozedur der- <xref:System.Nullable%601> Struktur darstellt.

 **Fehler-ID:** BC32126

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Ersetzen Sie den Prozedur Namen in der- `AddressOf` Klausel durch einen Operanden, der kein Member von ist <xref:System.Nullable%601> .

- Schreiben Sie eine Klasse, die die Methode von umschließt <xref:System.Nullable%601> , die Sie verwenden möchten. Im folgenden Beispiel definiert die- `NullableWrapper` Klasse eine neue Methode mit dem Namen `GetValueOrDefault` . Da diese neue Methode kein Member von ist <xref:System.Nullable%601> , kann Sie auf `nullInstance` eine Instanz eines Typs, der NULL-Werte zulässt, angewendet werden, um ein Argument für zu bilden `AddressOf` .

```vb
Module Module1

    Delegate Function Deleg() As Integer

    Sub Main()
        Dim nullInstance As New Nullable(Of Integer)(1)

        Dim del As Deleg

        ' GetValueOrDefault is a method of the Nullable generic
        ' type. It cannot be used as an operand of AddressOf.
        ' del = AddressOf nullInstance.GetValueOrDefault

        ' The following line uses the GetValueOrDefault method
        ' defined in the NullableWrapper class.
        del = AddressOf (New NullableWrapper(
            Of Integer)(nullInstance)).GetValueOrDefault

        Console.WriteLine(del.Invoke())
    End Sub

    Class NullableWrapper(Of T As Structure)
        Private m_Value As Nullable(Of T)

        Sub New(ByVal Value As Nullable(Of T))
            m_Value = Value
        End Sub

        Public Function GetValueOrDefault() As T
            Return m_Value.Value
        End Function
    End Class
End Module
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Nullable%601>
- [AddressOf-Operator](../operators/addressof-operator.md)
- [Auf NULL festlegbare Werttypen](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Generische Typen in Visual Basic (Visual Basic)](../../programming-guide/language-features/data-types/generic-types.md)
