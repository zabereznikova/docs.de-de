---
title: Der Typ für die Variable '<variablename>' wird nicht abgeleitet, da er an ein Feld in einem einschließenden Bereich gebunden ist
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: 3e76ffea283de2843fc5586179074c01a053ece8
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161282"
---
# <a name="bc42110-the-type-for-variable-variablename-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a>BC42110: der Typ für die Variable " \<variablename> " wird nicht abgeleitet, da er an ein Feld in einem einschließenden Bereich gebunden ist.

Der Typ für die Variable ' \<variablename> ' wird nicht abgeleitet, da er an ein Feld in einem einschließenden Bereich gebunden ist. Ändern Sie den Namen von ' \<variablename> ', oder verwenden Sie den voll qualifizierten Namen (z. b. ' me. variablename ' oder ' MyBase. variablename ').

Eine Schleifensteuerungsvariable im Code hat den gleichen Namen wie ein Feld der Klasse oder andere einschließende Bereiche. Da die Steuerelementvariable ohne eine `As`-Klausel verwendet wird, ist sie an das Feld im einschließenden Bereich gebunden, und der Compiler erstellt weder eine neue Variable für sie noch leitet er ihren Typ ab.

Im folgenden Beispiel `Index` ist die Steuerelementvariable in der `For`-Anweisung an das `Index`-Feld in der `Customer`-Klasse gebunden. Vom Compiler wird keine neue Variable für die Steuerelementvariable `Index` erstellt und ihr Typ nicht abgeleitet.

```vb
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

## <a name="to-address-this-warning"></a>So reagieren Sie auf diese Warnung

- Machen Sie die Schleifensteuerungsvariable lokal verfügbar, indem Sie ihren Namen in einen Bezeichner ändern, der nicht mit dem Feldnamen der Klasse übereinstimmt.

  ```vb
  For I = 1 To 10
  ```

- Stellen Sie sicher, dass die Schleifensteuerungsvariable an das Klassenfeld gebunden ist, indem Sie dem Variablennamen als Präfix `Me.` voranstellen.

  ```vb
  For Me.Index = 1 To 10
  ```

- Verwenden Sie eine `As`-Klausel, um einen Typ für die Schleifensteuerungsvariable festzulegen, anstatt sich auf den lokalen Typrückschluss zu verlassen.

  ```vb
  For Index As Integer = 1 To 10
  ```

## <a name="example"></a>Beispiel

 Der folgende Code veranschaulicht das vorherige Beispiel mit der ersten Korrektur.

```vb
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

- [Option Infer-Anweisung](../statements/option-infer-statement.md)
- [For Each...Next-Anweisung](../statements/for-each-next-statement.md)
- [For...Next-Anweisung](../statements/for-next-statement.md)
- [Vorgehensweise: Verweisen auf die aktuelle Instanz eines Objekts](../../programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [Lokaler Typrückschluss](../../programming-guide/language-features/variables/local-type-inference.md)
- [Me, My, MyBase und MyClass](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
