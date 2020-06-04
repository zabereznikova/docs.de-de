---
title: 'Vorgehensweise: Deklarieren einer Objektvariablen und Zuweisen eines entsprechenden Objekts'
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: d9a8c1fb30bfa5988d48202e41202e7ede0f5f27
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410502"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a>Gewusst wie: Deklarieren einer Objektvariablen und Zuweisen eines entsprechenden Objekts in Visual Basic

Sie deklarieren eine Variable des [Object-Datentyps](../../../language-reference/data-types/object-data-type.md) , indem Sie `As Object` in einer [Dim-Anweisung](../../../language-reference/statements/dim-statement.md)angeben. Sie weisen einer solchen Variablen ein Objekt zu, indem Sie das-Objekt nach dem Gleichheitszeichen ( `=` ) in einer Zuweisungsanweisung oder Initialisierungs Klausel platzieren.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine `Object` -Variable deklariert und der aktuellen Instanz zugewiesen.

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

- Eine Klasse, Struktur oder ein Modul, in das die Anweisung eingefügt werden soll `Dim` .

- Eine Prozedur, in der die Zuweisungsanweisung eingefügt wird.

## <a name="see-also"></a>Weitere Informationen

- [Variablen Deklaration](variable-declaration.md)
- [Objektvariablen](object-variables.md)
- [Deklaration von Objektvariablen](object-variable-declaration.md)
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [Dim-Anweisung](../../../language-reference/statements/dim-statement.md)
- [Lokaler Typrückschluss](local-type-inference.md)
- [Option Strict-Anweisung](../../../language-reference/statements/option-strict-statement.md)
