---
title: Der Typ für die Variable '<variablename>' wird nicht abgeleitet, da er an ein Feld in einem einschließenden Bereich gebunden ist
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: bcd142785d8ee736c6a1b41950fae80e4d26fa18
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838813"
---
# <a name="the-type-for-variable-variablename-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a>Der Typ für die Variable "\<Variablenname >' wird nicht abgeleitet werden, da er auf ein Feld in einem einschließenden Bereich gebunden ist
Der Typ für die Variable "\<Variablenname >' wird nicht abgeleitet werden, da er auf ein Feld in einem einschließenden Bereich gebunden ist. Ändern Sie den Namen des "\<Variablenname >', oder verwenden Sie den vollqualifizierten Namen (z. B. 'Me.Variablenname' oder 'MyBase.Variablenname').  
  
 Eine Schleifensteuerungsvariable im Code hat den gleichen Namen wie ein Feld der Klasse oder andere einschließende Bereiche. Da die Steuerelementvariable ohne eine `As`-Klausel verwendet wird, ist sie an das Feld im einschließenden Bereich gebunden, und der Compiler erstellt weder eine neue Variable für sie noch leitet er ihren Typ ab.  
  
 Im folgenden Beispiel `Index` ist die Steuerelementvariable in der `For`-Anweisung an das `Index`-Feld in der `Customer`-Klasse gebunden. Vom Compiler wird keine neue Variable für die Steuerelementvariable `Index` erstellt und ihr Typ nicht abgeleitet.  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
    ' The following line will raise this warning.  
        For Index = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen und zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42110  
  
### <a name="to-address-this-warning"></a>So reagieren Sie auf diese Warnung  
  
-   Machen Sie die Schleifensteuerungsvariable lokal verfügbar, indem Sie ihren Namen in einen Bezeichner ändern, der nicht mit dem Feldnamen der Klasse übereinstimmt.  
  
    ```  
    For I = 1 To 10  
    ```  
  
-   Stellen Sie sicher, dass die Schleifensteuerungsvariable an das Klassenfeld gebunden ist, indem Sie dem Variablennamen als Präfix `Me.` voranstellen.  
  
    ```  
    For Me.Index = 1 To 10  
    ```  
  
-   Verwenden Sie eine `As`-Klausel, um einen Typ für die Schleifensteuerungsvariable festzulegen, anstatt sich auf den lokalen Typrückschluss zu verlassen.  
  
    ```  
    For Index As Integer = 1 To 10  
    ```  
  
## <a name="example"></a>Beispiel  
 Der folgende Code veranschaulicht das vorherige Beispiel mit der ersten Korrektur.  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
        For I = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
## <a name="see-also"></a>Siehe auch

- [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [For Each...Next-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Vorgehensweise: Verweisen Sie auf die aktuelle Instanz eines Objekts](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Me, My, MyBase und MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
