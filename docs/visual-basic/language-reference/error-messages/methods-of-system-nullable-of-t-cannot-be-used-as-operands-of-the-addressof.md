---
title: "Methods of &#39;System.Nullable(Of T)&#39; cannot be used as operands of the &#39;AddressOf&#39; operator | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc32126"
  - "bc32126"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32126"
ms.assetid: 2325668b-e2ad-40ee-a1ec-30450236c20d
caps.latest.revision: 5
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 5
---
# Methods of &#39;System.Nullable(Of T)&#39; cannot be used as operands of the &#39;AddressOf&#39; operator
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Eine Anweisung verwendet den Operator `AddressOf` mit einem Operanden, der eine Prozedur der <xref:System.Nullable%601>\-Struktur darstellt.  
  
 **Fehler\-ID:** BC32126  
  
### So beheben Sie diesen Fehler  
  
-   Ersetzen Sie den Prozedurnamen in der `AddressOf`\-Klausel durch einen Operanden, der kein Member von <xref:System.Nullable%601> ist.  
  
-   Schreiben Sie eine Klasse, die die Methode von <xref:System.Nullable%601> umschließt, den Sie verwenden möchten.  Im folgenden Beispiel wird durch die `NullableWrapper`\-Klasse eine neue Methode mit dem Namen `GetValueOrDefault` definiert.  Da diese neue Methode kein Member von <xref:System.Nullable%601> ist, kann sie auf `nullInstance`, eine Instanz eines Typs, der NULL\-Werte zulässt, angewendet werden, um ein Argument für `AddressOf` zu bilden.  
  
    ```vb#  
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
  
## Siehe auch  
 <xref:System.Nullable%601>   
 [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Nullable Value Types](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)