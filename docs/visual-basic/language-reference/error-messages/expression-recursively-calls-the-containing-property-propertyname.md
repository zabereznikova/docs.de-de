---
title: Der Ausdruck ruft rekursiv die enthaltende <propertyname>-Eigenschaft auf.
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: f5b8b226d46afa0555559de0930f20025ba27f2b
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162764"
---
# <a name="bc42026-expression-recursively-calls-the-containing-property-propertyname"></a>BC42026: der Ausdruck ruft rekursiv die enthaltende Eigenschaft ' ' auf. \<propertyname>

Eine-Anweisung in der `Set` Prozedur einer Eigenschafts Definition speichert einen Wert in den Namen der Eigenschaft.

 Die empfohlene Vorgehensweise, um den Wert einer Eigenschaft zu speichern, besteht darin, eine `Private` Variable im Container der Eigenschaft zu definieren und Sie in den `Get` `Set` Prozeduren und zu verwenden. `Set`In der Prozedur sollte dann der eingehende Wert in dieser Variablen gespeichert werden `Private` .

 Die `Get` Prozedur verhält sich wie eine `Function` Prozedur, sodass Sie dem Eigenschaftsnamen einen Wert zuweisen und die Steuerung zurückgeben kann, indem Sie die- `End Get` Anweisung trifft. Die empfohlene Vorgehensweise besteht jedoch darin, die `Private` Variable als Wert in eine Return- [Anweisung](../statements/return-statement.md)aufzunehmen.

 Die `Set` Prozedur verhält sich wie eine `Sub` Prozedur, die keinen Wert zurückgibt. Daher hat der Name der Prozedur oder Eigenschaft in einer Prozedur keine besondere Bedeutung `Set` , und Sie können keinen Wert in der Prozedur speichern.

 Im folgenden Beispiel wird die Vorgehensweise veranschaulicht, die diesen Fehler verursachen kann, gefolgt von der empfohlenen Vorgehensweise.

```vb
Public Class illustrateProperties
' The code in the following property causes this error.
    Public Property badProp() As Char
        Get
            Dim charValue As Char
            ' Insert code to update charValue.
            badProp = charValue
        End Get
        Set(ByVal Value As Char)
            ' The following statement causes this error.
            badProp = Value
            ' The value stored in the local variable badProp
            ' is not used by the Get procedure in this property.
        End Set
    End Property
' The following code uses the recommended approach.
    Private propValue As Char
    Public Property goodProp() As Char
        Get
            ' Insert code to update propValue.
            Return propValue
        End Get
        Set(ByVal Value As Char)
            propValue = Value
        End Set
    End Property
End Class
```

 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Fehler-ID:** BC42026

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Schreiben Sie die Eigenschafts Definition so um, dass die empfohlene Vorgehensweise verwendet wird, wie im vorherigen Beispiel veranschaulicht.

## <a name="see-also"></a>Siehe auch

- [Eigenschaftenprozeduren](../../programming-guide/language-features/procedures/property-procedures.md)
- [Property Statement](../statements/property-statement.md)
- [Set-Anweisung](../statements/set-statement.md)
