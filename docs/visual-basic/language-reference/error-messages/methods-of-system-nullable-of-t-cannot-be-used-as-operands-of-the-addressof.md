---
title: Methoden von „System.Nullable(Of T)“ können nicht als Operanden des Operators „AddressOf“ verwendet werden
ms.date: 07/20/2015
f1_keywords:
- vbc32126
- bc32126
helpviewer_keywords:
- BC32126
ms.assetid: 2325668b-e2ad-40ee-a1ec-30450236c20d
ms.openlocfilehash: 59e89b24eca6a034dc1df2216f6f0d68e8191a18
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278559"
---
# <a name="methods-of-systemnullableof-t-cannot-be-used-as-operands-of-the-addressof-operator"></a>Methoden von „System.Nullable(Of T)“ können nicht als Operanden des Operators „AddressOf“ verwendet werden
Eine Anweisung verwendet die `AddressOf` -Operator mit einem Operanden, eine Prozedur darstellt. die <xref:System.Nullable%601> Struktur.  
  
 **Fehler-ID:** BC32126  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Ersetzen Sie den Namen der Prozedur in der `AddressOf` -Klausel mit einem Operanden, die nicht Mitglied ist <xref:System.Nullable%601>.  
  
-   Schreiben Sie eine Klasse, die die Methode umschließt <xref:System.Nullable%601> , die Sie verwenden möchten. Im folgenden Beispiel die `NullableWrapper` -Klasse definiert eine neue Methode namens `GetValueOrDefault`. Da diese neue Methode kein Mitglied ist <xref:System.Nullable%601>, dieses angewendet werden kann, um `nullInstance`, eine Instanz der einen nullable-Typ, um ein Argument für bilden `AddressOf`.  
  
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
- [AddressOf-Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Auf NULL festlegbare Werttypen](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
