---
title: Strukturvariablen
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 16b6cdc5a849b50f6caa8b7963dac5c12d63cf3e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346295"
---
# <a name="structure-variables-visual-basic"></a>Strukturvariablen (Visual Basic)

Nachdem Sie eine Struktur erstellt haben, können Sie Variablen auf Prozedur-und Modulebene als diesen Typ deklarieren. Beispielsweise können Sie eine Struktur erstellen, die Informationen zu einem Computersystem aufzeichnet. Dies wird im folgenden Beispiel veranschaulicht:

```vb
Public Structure systemInfo
    Public cPU As String
    Public memory As Long
    Public purchaseDate As Date
End Structure
```

Sie können jetzt Variablen dieses Typs deklarieren. Dies wird in der folgenden Deklaration veranschaulicht.

```vb
Dim mySystem, yourSystem As systemInfo
```

> [!NOTE]
> In Klassen und Modulen werden Strukturen, die mithilfe der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) deklariert werden, standardmäßig auf öffentlichen Zugriff eingestellt. Wenn Sie beabsichtigen, eine Struktur als privat zu verwenden, stellen Sie sicher, dass Sie Sie mit dem [privaten](../../../../visual-basic/language-reference/modifiers/private.md) Schlüsselwort deklarieren.

## <a name="access-to-structure-values"></a>Zugriff auf Struktur Werte

Zum Zuweisen und Abrufen von Werten aus den Elementen einer Struktur Variablen verwenden Sie dieselbe Syntax wie zum Festlegen und Abrufen von Eigenschaften für ein Objekt. Sie platzieren den Member Access Operator (`.`) zwischen dem Struktur Variablennamen und dem Elementnamen. Im folgenden Beispiel wird auf Elemente der Variablen zugegriffen, die zuvor als Typ `systemInfo`deklariert wurden.

```vb
mySystem.cPU = "486"
Dim tooOld As Boolean
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True
```

## <a name="assigning-structure-variables"></a>Zuweisen von Struktur Variablen

Sie können eine Variable auch einer anderen zuweisen, wenn beide denselben Strukturtyp haben. Dadurch werden alle Elemente einer Struktur in die entsprechenden Elemente in der anderen kopiert. Dies wird in der folgenden Deklaration veranschaulicht.

```vb
yourSystem = mySystem
```

Wenn ein Strukturelement ein Referenztyp ist, z. b. eine `String`, `Object`oder ein Array, wird der Zeiger auf die Daten kopiert. Wenn `systemInfo` im vorherigen Beispiel eine Objekt Variable enthalten hätte, hätte das vorangehende Beispiel den Zeiger von `mySystem` auf `yourSystem`kopiert, und eine Änderung an den Daten des Objekts durch eine Struktur wäre wirksam, wenn über die andere Struktur darauf zugegriffen wird.

## <a name="see-also"></a>Siehe auch

- [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Zusammengesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Gewusst wie: Deklarieren einer Struktur](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Strukturen und andere Programmierelemente](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [Strukturen und Klassen](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)
