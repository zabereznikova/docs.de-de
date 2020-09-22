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
ms.openlocfilehash: 3ca322da4e5f0edcbe12bf29bded863daabffe3d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867697"
---
# <a name="readonly-visual-basic"></a>ReadOnly (Visual Basic)

Gibt an, dass eine Variable oder Eigenschaft gelesen, aber nicht geschrieben werden kann.

## <a name="remarks"></a>Bemerkungen

## <a name="rules"></a>Regeln

- **Deklarationskontext.** Sie können `ReadOnly` nur auf Modulebene verwenden. Dies bedeutet, dass der Deklarations Kontext für ein- `ReadOnly` Element eine Klasse, eine Struktur oder ein Modul sein muss und weder eine Quelldatei, ein Namespace noch eine Prozedur sein darf.

- **Kombinierte Modifizierer.** Sie können nicht `ReadOnly` mit `Static` in der gleichen Deklaration angeben.

- **Zuweisen eines Werts.** Code, der eine Eigenschaft beansprucht, `ReadOnly` kann seinen Wert nicht festlegen. Code, der Zugriff auf den zugrunde liegenden Speicher hat, kann den Wert jedoch jederzeit zuweisen oder ändern.

     Sie können einer Variablen einen Wert `ReadOnly` nur in der Deklaration oder im Konstruktor einer Klasse oder Struktur zuweisen, in der Sie definiert ist.

## <a name="when-to-use-a-readonly-variable"></a>Verwendung einer schreibgeschützten Variablen

Es gibt Situationen, in denen Sie keine Konstanten- [Anweisung](../statements/const-statement.md) verwenden können, um einen konstanten Wert zu deklarieren und zuzuweisen. Beispielsweise akzeptiert die- `Const` Anweisung möglicherweise nicht den Datentyp, den Sie zuweisen möchten, oder Sie können den Wert möglicherweise nicht zur Kompilierzeit mit einem konstanten Ausdruck berechnen. Möglicherweise wissen Sie den Wert zum Zeitpunkt der Kompilierung nicht einmal. In diesen Fällen können Sie eine Variable verwenden, `ReadOnly` um einen konstanten Wert zu speichern.

> [!IMPORTANT]
> Wenn der Datentyp der Variablen ein Referenztyp ist, z. b. ein Array oder eine Klasseninstanz, können die Member auch dann geändert werden, wenn die Variable selbst ist `ReadOnly` . Dies wird anhand des folgenden Beispiels veranschaulicht.

```vb
ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}
Sub ChangeArrayElement()
    characterArray(1) = "M"c
End Sub
```

Bei der Initialisierung enthält das Array, auf das verweist, `characterArray()` "x", "y" und "z". Da die Variable `characterArray` ist `ReadOnly` , können Sie Ihren Wert nicht ändern, nachdem Sie initialisiert wurde, d. h., Sie können kein neues Array zuweisen. Sie können jedoch die Werte von einem oder mehreren Arraymembern ändern. Im Anschluss an einen aufzurufenden Vorgang `ChangeArrayElement` enthält das Array, auf das verweist, das Zeichen `characterArray()` "x", "M" und "z".

Beachten Sie, dass dies dem Deklarieren eines Prozedur Parameters als [ByVal](byval.md)ähnelt, wodurch verhindert wird, dass die Prozedur das aufrufende Argument selbst ändert, aber seine Member ändern kann.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine- `ReadOnly` Eigenschaft für das Datum definiert, an dem ein Mitarbeiter eingestellt wurde. Die-Klasse speichert den Eigenschafts Wert intern als `Private` Variable, und nur Code in der Klasse kann diesen Wert ändern. Die-Eigenschaft ist jedoch `Public` , und jeder Code, der auf die-Klasse zugreifen kann, kann die-Eigenschaft lesen.

[!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]

Der `ReadOnly`-Modifizierer kann in folgenden Kontexten verwendet werden:

- [Dim-Anweisung](../statements/dim-statement.md)
- [Property Statement](../statements/property-statement.md)

## <a name="see-also"></a>Weitere Informationen

- [WriteOnly](writeonly.md)
- [Schlüsselwörter](../keywords/index.md)
