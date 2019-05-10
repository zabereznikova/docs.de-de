---
title: Eine Konvertierung des anonymen Typs in eine Ausdrucksbaumstruktur ist nicht möglich, da sie ein Feld enthält, das in der Initialisierung eines anderen Feldes verwendet wird
ms.date: 07/20/2015
f1_keywords:
- bc36548
- vbc36548
helpviewer_keywords:
- BC36548
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
ms.openlocfilehash: 045061f403b301d460bc85d161c1d6dee9c7d9f1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64602403"
---
# <a name="cannot-convert-anonymous-type-to-expression-tree-because-it-contains-a-field-that-is-used-in-the-initialization-of-another-field"></a>Eine Konvertierung des anonymen Typs in eine Ausdrucksbaumstruktur ist nicht möglich, da sie ein Feld enthält, das in der Initialisierung eines anderen Feldes verwendet wird
Der Compiler nimmt keine Konvertierung eines anonymen in eine Ausdrucksbaumstruktur, wenn eine Eigenschaft des anonymen Typs verwendet wird, um eine andere Eigenschaft des anonymen Typs initialisieren. In den folgenden Code, z. B. `Prop1` in der Initialisierungsliste deklariert wird, und klicken Sie dann als der Anfangswert für verwendet `Prop2`.  
  
```vb  
Module M2  
  
    Sub ExpressionExample(Of T)(ByVal x As Expressions.Expression(Of Func(Of T)))  
    End Sub  
  
    Sub Main()  
        ' The following line causes the error.  
        ' ExpressionExample(Function() New With {.Prop1 = 2, .Prop2 = .Prop1})  
  
    End Sub  
End Module  
```  
  
 **Fehler-ID:** BC36548  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Weisen Sie den Anfangswert für `Prop1` an eine lokale Variable. Weisen Sie diese Variable sowohl `Prop1` und `Prop2`, wie im folgenden Code gezeigt.  
  
    ```  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Anonyme Typen (Visual Basic)](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Ausdrucksbaumstrukturen (Visual Basic)](../../programming-guide/concepts/expression-trees/index.md)
- [Vorgehensweise: Verwenden von Ausdrucksbaumstrukturen zum Erstellen dynamischer Abfragen (Visual Basic)](../../programming-guide/concepts/expression-trees/how-to-use-expression-trees-to-build-dynamic-queries.md)
