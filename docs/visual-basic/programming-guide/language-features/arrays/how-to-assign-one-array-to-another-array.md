---
title: 'Vorgehensweise: Zuweisen eines Arrays zu einem anderen Array (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
ms.openlocfilehash: a39888f19e5033a5c6622313fb7451d6463b2f7c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64858886"
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a>Vorgehensweise: Zuweisen eines Arrays zu einem anderen Array (Visual Basic)

Da Arrays Objekte sind, können Sie sie in zuweisungsanweisungen wie andere Objekttypen. Eine Array-Variable enthält einen Zeiger auf die Daten enthalten sind, die die Elemente des Arrays und die Informationen Rang und die Länge und eine Zuordnung kopiert nur this-Zeiger.

### <a name="to-assign-one-array-to-another-array"></a>Zuweisen eines Arrays zu einem anderen array

1. Stellen Sie sicher, dass die beiden Arrays den gleichen Rang (Anzahl der Dimensionen) und kompatiblen Elements-Datentypen aufweisen.

2. Verwenden Sie eine standardmäßige zuweisungsanweisung, um das Quellarray in den Zielarray zuzuweisen. Führen Sie nicht entweder Arrayname mit Klammern.

    ```vb
    Dim formArray() As System.Windows.Forms.Form
    Dim controlArray() As System.Windows.Forms.Control
    controlArray = formArray
    ```

Wenn Sie ein Array zu einem anderen zuweisen, gelten die folgenden Regeln:

- **Gleicher Rang.** Der Rang (Anzahl der Dimensionen) des Zielarrays muss des Quellarrays, identisch sein.

  Sofern die Ränge von zwei Arrays gleich sind, müssen die Dimensionen nicht gleich sind. Die Anzahl der Elemente in der angegebenen Dimension kann bei der Zuordnung ändern.

- **Elementtypen.** Es müssen entweder beide Arrays *Verweistyp* Elemente oder beide Arrays müssen *Werttyp* Elemente. Weitere Informationen finden Sie unter [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).

  - Wenn beide Arrays Elementen mit Werttyp haben, müssen die Element-Datentypen genau übereinstimmen. Die einzige Ausnahme hierbei ist, dass Sie ein Array von zuweisen können `Enum` Elemente in ein Array des Basistyps dieses `Enum`.

  - Wenn beide Arrays Elemente aufweisen, muss der Elementtyp der Datenquelle von der Ziel-Elementtyp abgeleitet werden. Wenn dies der Fall ist, müssen die beiden Arrays die gleiche vererbungsbeziehung als ihre Elemente. Dies wird als bezeichnet *Array-Kovarianz*.

Der Compiler meldet, dass ein Fehler, wenn die oben genannten Regeln, z. B. verletzt werden die Datentypen nicht kompatibel sind oder die Ränge ungleich sind. Sie können die Fehlerbehandlung in Ihrem Code, um sicherzustellen, dass die Arrays kompatibel sind, bevor Sie versuchen, eine Zuordnung hinzufügen. Sie können auch die [TryCast-Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md) Schlüsselwort, wenn Sie das Auslösen einer Ausnahme vermeiden möchten.

## <a name="see-also"></a>Siehe auch

- [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Problembehandlung bei Arrays](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
- [Enum-Anweisung](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [Arraykonvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
