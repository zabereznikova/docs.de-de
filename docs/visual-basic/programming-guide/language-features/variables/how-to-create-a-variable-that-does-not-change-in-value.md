---
title: 'Gewusst wie: Erstellen einer Variablen mit unveränderlichem Wert'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: d5d8a6b066ae7e8795afd2f788b60823d8efdafa
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348646"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a>Gewusst wie: Erstellen einer Variablen mit unveränderlichem Wert (Visual Basic)

Das Konzept einer Variablen, deren Wert nicht geändert wird, mag widersprüchlich erscheinen. Es gibt jedoch Situationen, in denen eine Konstante nicht realisierbar ist, und es sinnvoll ist, eine Variable mit einem Fixed-Wert zu haben. In einem solchen Fall können Sie eine Member-Variable [mit dem Schlüssel](../../../../visual-basic/language-reference/modifiers/readonly.md) Wort "schreibgeschützt" definieren.

In den folgenden Situationen können Sie die Konstante [Anweisung](../../../../visual-basic/language-reference/statements/const-statement.md) nicht verwenden, um einen konstanten Wert zu deklarieren und zuzuweisen:

- Die `Const`-Anweisung akzeptiert nicht den Datentyp, den Sie verwenden möchten.

- Der Wert ist zur Kompilierzeit nicht bekannt.

- Der Konstante Wert kann zur Kompilierzeit nicht berechnet werden.

### <a name="to-create-a-variable-that-does-not-change-in-value"></a>So erstellen Sie eine Variable, die den Wert nicht ändert

1. Deklarieren Sie auf Modulebene eine Member-Variable mit der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md), und schließen Sie [das Schlüsselwort](../../../../visual-basic/language-reference/modifiers/readonly.md) "schreibgeschützt" ein.

    ```vb
    Dim ReadOnly timeStarted
    ```

    Sie können `ReadOnly` nur für eine Element Variable angeben. Dies bedeutet, dass Sie die Variable auf Modulebene außerhalb der Prozeduren definieren müssen.

2. Wenn Sie den Wert in einer einzelnen Anweisung zur Kompilierzeit berechnen können, verwenden Sie eine Initialisierungs Klausel in der `Dim`-Anweisung. Befolgen Sie die [As](../../../../visual-basic/language-reference/statements/as-clause.md) -Klausel mit einem Gleichheitszeichen (`=`), gefolgt von einem Ausdruck. Stellen Sie sicher, dass der Compiler diesen Ausdruck mit einem konstanten Wert auswerten kann.

    ```vb
    Dim ReadOnly timeStarted As Date = Now
    ```

    Sie können einer `ReadOnly` Variable nur einmal einen Wert zuweisen. Nachdem Sie dies getan haben, kann kein Code mehr seinen Wert ändern.

    Wenn Sie den Wert zur Kompilierzeit nicht kennen oder ihn zur Kompilierzeit nicht in einer einzelnen Anweisung berechnen können, können Sie ihn trotzdem zur Laufzeit in einem Konstruktor zuweisen. Zu diesem Zweck müssen Sie die `ReadOnly` Variable auf Klassen-oder Struktur Ebene deklarieren. Berechnen Sie im Konstruktor für diese Klasse oder Struktur den festgelegten Wert der Variablen, und weisen Sie ihn der Variablen zu, bevor Sie den Konstruktor zurückgeben.

## <a name="see-also"></a>Siehe auch

- [WriteOnly](../../../../visual-basic/language-reference/modifiers/writeonly.md)
- [Const-Anweisung](../../../../visual-basic/language-reference/statements/const-statement.md)
