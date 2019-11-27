---
title: ReadOnly
ms.date: 07/20/2015
f1_keywords:
- vb.ReadOnly
helpviewer_keywords:
- ReadOnly keyword [Visual Basic]
- variables [Visual Basic], read-only
- ReadOnly property
- properties [Visual Basic], read-only
- read-only variables
ms.assetid: e868185d-6142-4359-a2fd-a7965cadfce8
ms.openlocfilehash: 8c7e7e7c1571fd7c595ebfd54fb5767078ef41f8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351281"
---
# <a name="readonly-visual-basic"></a>ReadOnly (Visual Basic)
Gibt an, dass eine Variable oder Eigenschaft gelesen, aber nicht geschrieben werden kann.

## <a name="remarks"></a>Hinweise

## <a name="rules"></a>Regeln

- **Deklarations Kontext.** Sie können `ReadOnly` nur auf Modulebene verwenden. Dies bedeutet, dass der Deklarations Kontext für ein `ReadOnly` Element eine Klasse, eine Struktur oder ein Modul sein muss und weder eine Quelldatei, ein Namespace noch eine Prozedur sein darf.

- **Kombinierte modifiziererer.** Sie können `ReadOnly` nicht mit `Static` in derselben Deklaration angeben.

- **Zuweisen eines Werts.** Code, der eine `ReadOnly` Eigenschaft beansprucht, kann seinen Wert nicht festlegen. Code, der Zugriff auf den zugrunde liegenden Speicher hat, kann den Wert jedoch jederzeit zuweisen oder ändern.

     Sie können einer `ReadOnly` Variable nur in der Deklaration oder im Konstruktor einer Klasse oder Struktur, in der Sie definiert ist, einen Wert zuweisen.

## <a name="when-to-use-a-readonly-variable"></a>Verwendung einer schreibgeschützten Variablen

Es gibt Situationen, in denen Sie keine Konstanten- [Anweisung](../../../visual-basic/language-reference/statements/const-statement.md) verwenden können, um einen konstanten Wert zu deklarieren und zuzuweisen. Beispielsweise akzeptiert die `Const`-Anweisung möglicherweise nicht den Datentyp, den Sie zuweisen möchten, oder Sie können den Wert möglicherweise nicht zur Kompilierzeit mit einem konstanten Ausdruck berechnen. Möglicherweise wissen Sie den Wert zum Zeitpunkt der Kompilierung nicht einmal. In diesen Fällen können Sie eine `ReadOnly` Variable verwenden, um einen konstanten Wert zu speichern.

> [!IMPORTANT]
> Wenn der Datentyp der Variablen ein Referenztyp ist, z. b. ein Array oder eine Klasseninstanz, können die zugehörigen Member auch dann geändert werden, wenn die Variable selbst `ReadOnly`ist. Das folgende Beispiel veranschaulicht dies.

```vb
ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}
Sub ChangeArrayElement()
    characterArray(1) = "M"c
End Sub
```

Bei der Initialisierung zeigt das Array, auf das von `characterArray()` verwiesen wird, "x", "y" und "z". Da die Variable `characterArray` `ReadOnly`ist, können Sie Ihren Wert nicht ändern, nachdem Sie initialisiert wurde. Das heißt, Sie können kein neues Array zuweisen. Sie können jedoch die Werte von einem oder mehreren Arraymembern ändern. Im Anschluss an einen aufzurufenden Prozedur `ChangeArrayElement`enthält das Array, auf das von `characterArray()` verwiesen wird, "x", "M" und "z".

Beachten Sie, dass dies dem Deklarieren eines Prozedur Parameters als [ByVal](byval.md)ähnelt, wodurch verhindert wird, dass die Prozedur das aufrufende Argument selbst ändert, aber seine Member ändern kann.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine `ReadOnly`-Eigenschaft für das Datum definiert, an dem ein Mitarbeiter eingestellt wurde. Die-Klasse speichert den Eigenschafts Wert intern als `Private` Variable, und nur Code in der Klasse kann diesen Wert ändern. Die-Eigenschaft ist jedoch `Public`, und jeder Code, der auf die-Klasse zugreifen kann, kann die-Eigenschaft lesen.

[!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]

Der `ReadOnly`-Modifizierer kann in folgenden Kontexten verwendet werden:

- [Dim-Anweisung](../statements/dim-statement.md)
- [Property-Anweisung](../statements/property-statement.md)

## <a name="see-also"></a>Siehe auch

- [WriteOnly](writeonly.md)
- [Schlüsselwörter](../keywords/index.md)
