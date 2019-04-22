---
title: Methoden von „System.Nullable(Of T)“ können nicht als Operanden des Operators „AddressOf“ verwendet werden
ms.date: 07/20/2015
f1_keywords:
- vbc32126
- bc32126
helpviewer_keywords:
- BC32126
ms.assetid: 2325668b-e2ad-40ee-a1ec-30450236c20d
ms.openlocfilehash: 54d66a60d20a6add4c2b4a160f87b58b5a1d00e9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58817265"
---
# <a name="methods-of-systemnullableof-t-cannot-be-used-as-operands-of-the-addressof-operator"></a><span data-ttu-id="c4e78-102">Methoden von „System.Nullable(Of T)“ können nicht als Operanden des Operators „AddressOf“ verwendet werden</span><span class="sxs-lookup"><span data-stu-id="c4e78-102">Methods of 'System.Nullable(Of T)' cannot be used as operands of the 'AddressOf' operator</span></span>
<span data-ttu-id="c4e78-103">Eine Anweisung verwendet die `AddressOf` -Operator mit einem Operanden, eine Prozedur darstellt. die <xref:System.Nullable%601> Struktur.</span><span class="sxs-lookup"><span data-stu-id="c4e78-103">A statement uses the `AddressOf` operator with an operand that represents a procedure of the <xref:System.Nullable%601> structure.</span></span>  
  
 <span data-ttu-id="c4e78-104">**Fehler-ID:** BC32126</span><span class="sxs-lookup"><span data-stu-id="c4e78-104">**Error ID:** BC32126</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c4e78-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c4e78-105">To correct this error</span></span>  
  
-   <span data-ttu-id="c4e78-106">Ersetzen Sie den Namen der Prozedur in der `AddressOf` -Klausel mit einem Operanden, die nicht Mitglied ist <xref:System.Nullable%601>.</span><span class="sxs-lookup"><span data-stu-id="c4e78-106">Replace the procedure name in the `AddressOf` clause with an operand that is not a member of <xref:System.Nullable%601>.</span></span>  
  
-   <span data-ttu-id="c4e78-107">Schreiben Sie eine Klasse, die die Methode umschließt <xref:System.Nullable%601> , die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c4e78-107">Write a class that wraps the method of <xref:System.Nullable%601> that you want to use.</span></span> <span data-ttu-id="c4e78-108">Im folgenden Beispiel die `NullableWrapper` -Klasse definiert eine neue Methode namens `GetValueOrDefault`.</span><span class="sxs-lookup"><span data-stu-id="c4e78-108">In the following example, the `NullableWrapper` class defines a new method named `GetValueOrDefault`.</span></span> <span data-ttu-id="c4e78-109">Da diese neue Methode kein Mitglied ist <xref:System.Nullable%601>, dieses angewendet werden kann, um `nullInstance`, eine Instanz der einen nullable-Typ, um ein Argument für bilden `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="c4e78-109">Because this new method is not a member of <xref:System.Nullable%601>, it can be applied to `nullInstance`, an instance of a nullable type, to form an argument for `AddressOf`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c4e78-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4e78-110">See also</span></span>

- <xref:System.Nullable%601>
- [<span data-ttu-id="c4e78-111">AddressOf-Operator</span><span class="sxs-lookup"><span data-stu-id="c4e78-111">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="c4e78-112">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="c4e78-112">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="c4e78-113">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c4e78-113">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
