---
title: 'Gewusst wie: Deklarieren einer Objektvariablen und Zuweisen eines Objekts'
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: eaaeda2a986584e6e1a2e0d2cda3890fb6187598
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344233"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a>Gewusst wie: Deklarieren einer Objektvariablen und Zuweisen eines entsprechenden Objekts in Visual Basic

Sie deklarieren eine Variable des [Object-Datentyps](../../../../visual-basic/language-reference/data-types/object-data-type.md) , indem Sie `As Object` in einer [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)angeben. Sie weisen einer solchen Variablen ein Objekt zu, indem Sie das-Objekt nach dem Gleichheitszeichen (`=`) in einer Zuweisungsanweisung oder Initialisierungs Klausel platzieren.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine `Object` Variable deklariert und der aktuellen Instanz zugewiesen.

```vb
Dim thisObject As Object
thisObject = "This is an Object"
```

Sie können die Deklaration und Zuweisung kombinieren, indem Sie die Variable als Teil der Deklaration initialisieren. Das folgende Beispiel entspricht dem vorherigen Beispiel.

```vb
Dim thisObject As Object= "This is an Object"
```

## <a name="compile-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

- Einen Verweis auf den <xref:System>-Namespace

- Eine Klasse, Struktur oder ein Modul, in das die `Dim`-Anweisung eingefügt werden soll.

- Eine Prozedur, in der die Zuweisungsanweisung eingefügt wird.

## <a name="see-also"></a>Siehe auch

- [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Deklaration von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
