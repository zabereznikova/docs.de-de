---
title: Gültigkeitsbereich
ms.date: 07/20/2015
helpviewer_keywords:
- module scope [Visual Basic]
- scope [Visual Basic], levels
- module level
- procedures [Visual Basic], scope
- declared elements [Visual Basic], scope
- namespaces [Visual Basic], scope
- scope [Visual Basic], declared elements
- scope [Visual Basic], about scope
- levels of scope [Visual Basic]
- block scope [Visual Basic]
- scope [Visual Basic], Visual Basic
- procedure scope [Visual Basic]
ms.assetid: 208106fe-79c9-4eec-93c6-55f08548895f
ms.openlocfilehash: 37fcfa897accb23e9c8c56407ce4ebd956b39c4d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345290"
---
# <a name="scope-in-visual-basic"></a>Gültigkeitsbereich in Visual Basic

Der Gültigkeits *Bereich* eines deklarierten Elements ist der Satz des gesamten Codes, der darauf verweisen kann, ohne den Namen zu qualifizieren oder über eine [Imports-Anweisung (.NET-Namespace und-Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)verfügbar zu gemacht. Ein Element kann einen Bereich auf einer der folgenden Ebenen aufweisen:

|Level|Beschreibung|
|-----------|-----------------|
|Blockbereich|Nur innerhalb des Codeblocks verfügbar, in dem er deklariert ist.|
|Prozedur Bereich|Verfügbar für den gesamten Code in der Prozedur, in der er deklariert ist|
|Modul Bereich|Verfügbar für den gesamten Code im Modul, der Klasse oder Struktur, in der er deklariert ist|
|Namespace Bereich|Verfügbar für den gesamten Code im Namespace, in dem er deklariert ist.|

Diese Ebenen des Bereichs werden vom engsten (Block) zum breiteste (-Namespace), wobei der *engste* Gültigkeitsbereich die kleinste Codemenge bedeutet, die ohne Qualifizierung auf das Element verweisen kann. Weitere Informationen finden Sie auf dieser Seite unter "Ebenen des Bereichs".

## <a name="specifying-scope-and-defining-variables"></a>Festlegen des Bereichs und Definieren von Variablen

Sie geben den Bereich eines Elements an, wenn Sie es deklarieren. Der Bereich kann von folgenden Faktoren abhängen:

- Der Bereich (Block, Prozedur, Modul, Klasse oder Struktur), in dem Sie das Element deklarieren.

- Der Namespace, der die Deklaration des Elements enthält.

- Die Zugriffsebene, die Sie für das Element deklarieren.

Verwenden Sie Vorsicht, wenn Sie Variablen mit demselben Namen, aber unterschiedlichen Gültigkeitsbereich definieren, da dies zu unerwarteten Ergebnissen führen kann. Weitere Informationen finden Sie unter [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).

## <a name="levels-of-scope"></a>Ebenen des Gültigkeits Bereichs

Ein Programmier Element ist in der Region verfügbar, in der Sie es deklarieren. Der gesamte Code in der gleichen Region kann auf das Element verweisen, ohne den Namen zu qualifizieren.

### <a name="block-scope"></a>Block Bereich

Ein-Block ist ein Satz von-Anweisungen, die in initiieren und Beenden von Deklarations Anweisungen eingeschlossen sind, wie z. b.:

- `Do` und `Loop`

- `For` [`Each`] und `Next`

- `If` und `End If`

- `Select` und `End Select`

- `SyncLock` und `End SyncLock`

- `Try` und `End Try`

- `While` und `End While`

- `With` und `End With`

Wenn Sie eine Variable innerhalb eines-Blocks deklarieren, können Sie Sie nur innerhalb dieses Blocks verwenden. Im folgenden Beispiel ist der Gültigkeitsbereich der ganzzahligen Variablen `cube` der Block zwischen `If` und `End If`, und Sie können nicht mehr auf `cube` verweisen, wenn die Ausführung aus dem Block besteht.

```vb
If n < 1291 Then
    Dim cube As Integer
    cube = n ^ 3
End If
```

> [!NOTE]
> Auch wenn der Gültigkeitsbereich einer Variablen auf einen-Block beschränkt ist, liegt seine Lebensdauer immer noch bei der gesamten Prozedur. Wenn Sie den Block während der Prozedur mehrmals eingeben, behält jede Block Variable ihren vorherigen Wert bei. Um unerwartete Ergebnisse in einem solchen Fall zu vermeiden, ist es ratsam, Block Variablen am Anfang des Blocks zu initialisieren.

### <a name="procedure-scope"></a>Prozedur Bereich

Ein innerhalb einer Prozedur deklariertes Element ist außerhalb dieses Verfahrens nicht verfügbar. Nur die Prozedur, die die Deklaration enthält, kann diese verwenden. Variablen auf dieser Ebene werden auch als *lokale Variablen*bezeichnet. Sie deklarieren Sie mit der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)mit oder ohne das [static](../../../../visual-basic/language-reference/modifiers/static.md) -Schlüsselwort.

Prozedur-und Block Bereich sind eng miteinander verknüpft. Wenn Sie eine Variable innerhalb einer Prozedur, aber außerhalb eines Blocks innerhalb dieser Prozedur deklarieren, können Sie sich die Variable als Block Bereich vorstellen, in dem der Block die gesamte Prozedur ist.

> [!NOTE]
> Alle lokalen Elemente, selbst wenn Sie `Static` Variablen sind, sind privat für die Prozedur, in der Sie angezeigt werden. Sie können ein beliebiges Element nicht mithilfe des [Public](../../../../visual-basic/language-reference/modifiers/public.md) -Schlüssel Worts innerhalb einer Prozedur deklarieren.

### <a name="module-scope"></a>Modul Bereich

Der Vorteil ist, dass die einzelne Begriffs *Modulebene* gleichermaßen auf Module, Klassen und Strukturen angewendet wird. Sie können Elemente auf dieser Ebene deklarieren, indem Sie die Deklarations Anweisung außerhalb einer Prozedur oder eines Blocks, aber innerhalb des Moduls, der Klasse oder der Struktur platzieren.

Wenn Sie auf Modulebene eine Deklaration erstellen, bestimmt die von Ihnen gewählte Zugriffsebene den Bereich. Der Namespace, der das Modul, die Klasse oder die Struktur enthält, wirkt sich auch auf den Bereich aus.

Elemente, für die Sie die [private](../../../../visual-basic/language-reference/modifiers/private.md) Zugriffsebene deklarieren, sind für jede Prozedur in diesem Modul verfügbar, aber nicht für Code in einem anderen Modul. Die `Dim`-Anweisung auf Modulebene wird standardmäßig `Private`, wenn Sie keine Zugriffsebenen-Schlüsselwörter verwenden. Sie können jedoch den Bereich und die Zugriffsebene deutlicher machen, indem Sie das `Private`-Schlüsselwort in der `Dim`-Anweisung verwenden.

Im folgenden Beispiel können alle im Modul definierten Prozeduren auf die Zeichen folgen Variable `strMsg`verweisen. Wenn die zweite Prozedur aufgerufen wird, wird der Inhalt der Zeichen folgen Variablen `strMsg` in einem Dialogfeld angezeigt.

```vb
' Put the following declaration at module level (not in any procedure).
Private strMsg As String
' Put the following Sub procedure in the same module.
Sub initializePrivateVariable()
    strMsg = "This variable cannot be used outside this module."
End Sub
' Put the following Sub procedure in the same module.
Sub usePrivateVariable()
    MsgBox(strMsg)
End Sub
```

### <a name="namespace-scope"></a>Namespace Bereich

Wenn Sie ein Element auf Modulebene mit dem [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) -oder [Public](../../../../visual-basic/language-reference/modifiers/public.md) -Schlüsselwort deklarieren, steht es allen Prozeduren im gesamten Namespace zur Verfügung, in dem das Element deklariert wird. Mit der folgenden Änderung am vorangehenden Beispiel kann auf die Zeichen folgen Variable `strMsg` von Code an beliebiger Stelle im Namespace der zugehörigen Deklaration verwiesen werden.

```vb
' Include this declaration at module level (not inside any procedure).
Public strMsg As String
```

Der Namespace Bereich schließt schsted Namespaces ein. Ein Element, das in einem Namespace verfügbar ist, steht auch in allen Namespaces zur Verfügung, die in diesem Namespace geschachtelt sind.

Wenn das Projekt keine [Namespace-Anweisung](../../../../visual-basic/language-reference/statements/namespace-statement.md)s enthält, befindet sich alles im Projekt im selben Namespace. In diesem Fall kann sich der Namespace Bereich als Projektbereich vorstellen. `Public` Elemente in einem Modul, einer Klasse oder einer Struktur sind auch für jedes Projekt verfügbar, das auf das Projekt verweist.

## <a name="choice-of-scope"></a>Auswahl des Bereichs

Wenn Sie eine Variable deklarieren, sollten Sie die folgenden Punkte berücksichtigen, wenn Sie Ihren Bereich auswählen.

### <a name="advantages-of-local-variables"></a>Vorteile lokaler Variablen

Lokale Variablen sind aus folgenden Gründen eine gute Wahl für jede Art von temporärer Berechnung:

- **Vermeiden von Namenskonflikten.** Lokale Variablennamen sind nicht anfällig für Konflikte. Beispielsweise können Sie mehrere verschiedene Prozeduren erstellen, die eine Variable namens `intTemp`enthalten. Solange jede `intTemp` als lokale Variable deklariert ist, erkennt jede Prozedur nur Ihre eigene Version von `intTemp`. Jede Prozedur kann den Wert in der lokalen `intTemp` ändern, ohne `intTemp` Variablen in anderen Prozeduren zu beeinflussen.

- **Arbeitsspeicher Nutzung.** Lokale Variablen belegen nur Speicher, während Ihre Prozedur ausgeführt wird. Der Arbeitsspeicher wird freigegeben, wenn die Prozedur an den aufrufenden Code zurückgegeben wird. Im Gegensatz dazu verbrauchen frei [gegebene](../../../../visual-basic/language-reference/modifiers/shared.md) und [statische](../../../../visual-basic/language-reference/modifiers/static.md) Variablen Speicherressourcen, bis Ihre Anwendung nicht mehr ausgeführt wird. verwenden Sie Sie daher nur bei Bedarf. *Instanzvariablen* belegen Arbeitsspeicher, während Ihre Instanz weiterhin vorhanden ist. dadurch sind Sie weniger effizient als lokale Variablen, aber potenziell effizienter als `Shared` oder `Static` Variablen.

### <a name="minimizing-scope"></a>Minimieren des Bereichs

Beim Deklarieren einer Variablen oder Konstanten empfiehlt es sich im Allgemeinen, den Bereich so schmal wie möglich zu machen (Block Bereich ist die engste). Dadurch wird Speicherplatz gespart, und die Wahrscheinlichkeit, dass Ihr Code fälschlicherweise auf die falsche Variable verweist, wird minimiert. Ebenso sollten Sie eine Variable so deklarieren, dass Sie nur [statisch](../../../../visual-basic/language-reference/modifiers/static.md) ist, wenn der Wert zwischen Prozedur aufrufen beibehalten werden muss.

## <a name="see-also"></a>Siehe auch

- [Merkmale deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Gewusst wie: Steuern des Gültigkeitsbereichs einer Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)
- [Lebensdauer in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
