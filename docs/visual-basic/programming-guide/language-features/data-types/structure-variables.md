---
title: Strukturvariablen
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 270e8ca26185e4a68def3b95f4ce6ab4c57a629c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393584"
---
# <a name="structure-variables-visual-basic"></a>Strukturvariablen (Visual Basic)

Nachdem Sie eine Struktur erstellt haben, können Sie Variablen auf Prozedur-und Modulebene als diesen Typ deklarieren. Beispielsweise können Sie eine Struktur erstellen, die Informationen zu einem Computersystem aufzeichnet. Das wird im folgenden Beispiel veranschaulicht.

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
> In Klassen und Modulen werden Strukturen, die mithilfe der [Dim-Anweisung](../../../language-reference/statements/dim-statement.md) deklariert werden, standardmäßig auf öffentlichen Zugriff eingestellt. Wenn Sie beabsichtigen, eine Struktur als privat zu verwenden, stellen Sie sicher, dass Sie Sie mit dem [privaten](../../../language-reference/modifiers/private.md) Schlüsselwort deklarieren.

## <a name="access-to-structure-values"></a>Zugriff auf Struktur Werte

Zum Zuweisen und Abrufen von Werten aus den Elementen einer Struktur Variablen verwenden Sie dieselbe Syntax wie zum Festlegen und Abrufen von Eigenschaften für ein Objekt. Der Member Access Operator () wird `.` zwischen dem Namen der Struktur Variablen und dem Elementnamen platziert. Im folgenden Beispiel wird auf Elemente der Variablen zugegriffen, die zuvor als Typ deklariert wurden `systemInfo` .

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

Wenn ein Strukturelement ein Verweistyp ist, z. b `String` . ein-,- `Object` oder-Array, wird der Zeiger auf die Daten kopiert. Wenn im vorherigen Beispiel `systemInfo` eine Objekt Variable eingefügt hätte, hätte das vorangehende Beispiel den Zeiger von `mySystem` in kopiert `yourSystem` , und eine Änderung an den Daten des Objekts durch eine Struktur wäre wirksam, wenn über die andere Struktur auf Sie zugegriffen wird.

## <a name="see-also"></a>Weitere Informationen

- [Datentypen](index.md)
- [Elementare Datentypen](elementary-data-types.md)
- [Zusammengesetzte Datentypen](composite-data-types.md)
- [Wert- und Verweistypen](value-types-and-reference-types.md)
- [Strukturen](structures.md)
- [Problembehandlung bei Datentypen](troubleshooting-data-types.md)
- [Vorgehensweise: Deklarieren einer Struktur](how-to-declare-a-structure.md)
- [Strukturen und andere Programmierelemente](structures-and-other-programming-elements.md)
- [Strukturen und Klassen](structures-and-classes.md)
- [Structure Statement](../../../language-reference/statements/structure-statement.md)
