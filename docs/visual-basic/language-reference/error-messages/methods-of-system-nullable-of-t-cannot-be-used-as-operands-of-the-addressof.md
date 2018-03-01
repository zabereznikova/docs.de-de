---
title: Methoden der &#39; System.Nullable (Of T) &#39; kann nicht verwendet werden, als Operanden der &#39; AddressOf &#39; Operator
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32126
- bc32126
helpviewer_keywords:
- BC32126
ms.assetid: 2325668b-e2ad-40ee-a1ec-30450236c20d
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ce0e9bc6abd71f22e3f6c3486ef40493e74d820f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="methods-of-39systemnullableof-t39-cannot-be-used-as-operands-of-the-39addressof39-operator"></a>Methoden der &#39; System.Nullable (Of T) &#39; kann nicht verwendet werden, als Operanden der &#39; AddressOf &#39; Operator
Eine Anweisung verwendet die `AddressOf` Operator mit einem Operanden, die für eine Prozedur mit der <xref:System.Nullable%601> Struktur.  
  
 **Fehler-ID:** BC32126  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Ersetzen Sie den Namen der Prozedur in der `AddressOf` -Klausel mit einem Operanden, der kein Mitglied von ist <xref:System.Nullable%601>.  
  
-   Schreiben Sie eine Klasse, die die Methode umschließt <xref:System.Nullable%601> , die Sie verwenden möchten. Im folgenden Beispiel die `NullableWrapper` Klasse definiert eine neue Methode mit dem Namen `GetValueOrDefault`. Da diese neue Methode kein Mitglied von ist <xref:System.Nullable%601>, auf angewendet werden können `nullInstance`, eine Instanz von dem nullable-Typ, um ein Argument für bilden `AddressOf`.  
  
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
 <xref:System.Nullable%601>  
 [AddressOf-Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Auf NULL festlegbare Werttypen](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
