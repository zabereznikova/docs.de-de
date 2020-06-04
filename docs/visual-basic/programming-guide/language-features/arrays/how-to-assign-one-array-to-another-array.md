---
title: 'Vorgehensweise: Zuweisen eines Arrays zu einem anderen Array'
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
ms.openlocfilehash: c38def1ba9f3720bc760d6f6e4264510c884c930
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413078"
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a>Gewusst wie: Zuweisen eines Arrays zu einem anderen Array (Visual Basic)

Da Arrays Objekte sind, können Sie Sie in Zuweisungs Anweisungen wie anderen Objekttypen verwenden. Eine Array Variable enthält einen Zeiger auf die Daten, die die Array Elemente und die Rang-und Längen Informationen bilden, und eine Zuweisung kopiert nur diesen Zeiger.

### <a name="to-assign-one-array-to-another-array"></a>So weisen Sie ein Array einem anderen Array zu

1. Stellen Sie sicher, dass die beiden Arrays denselben Rang (Anzahl von Dimensionen) und kompatible Element Datentypen aufweisen.

2. Verwenden Sie eine Standard Zuweisungsanweisung zum Zuweisen des Quell Arrays zum Zielarray. Folgen Sie keinem der Array Namen mit Klammern.

    ```vb
    Dim formArray() As System.Windows.Forms.Form
    Dim controlArray() As System.Windows.Forms.Control
    controlArray = formArray
    ```

Wenn Sie ein Array einem anderen zuweisen, gelten die folgenden Regeln:

- **Gleiche Ränge.** Der Rang (Anzahl der Dimensionen) des Zielarrays muss mit dem des Quell Arrays identisch sein.

  Wenn die Ränge der beiden Arrays gleich sind, müssen die Dimensionen nicht gleich sein. Die Anzahl von Elementen in einer bestimmten Dimension kann sich während der Zuweisung ändern.

- **Element Typen.** Beide Arrays müssen über *Verweistyp* Elemente verfügen, oder beide Arrays müssen *Werttyp* Elemente aufweisen. Weitere Informationen finden Sie unter [Werttypen und Verweis Typen](../data-types/value-types-and-reference-types.md).

  - Wenn beide Arrays Werttyp Elemente aufweisen, müssen die Element Datentypen exakt identisch sein. Die einzige Ausnahme besteht darin, dass Sie ein Array von- `Enum` Elementen einem Array des Basistyps dieses zuweisen können `Enum` .

  - Wenn beide Arrays Verweistyp Elemente aufweisen, muss der Quell Elementtyp vom Ziel Elementtyp abgeleitet werden. Wenn dies der Fall ist, haben die beiden Arrays dieselbe Vererbungs Beziehung wie ihre Elemente. Dies wird als *Array Kovarianz*bezeichnet.

Der Compiler meldet einen Fehler, wenn die oben genannten Regeln verletzt werden, z. b. wenn die Datentypen nicht kompatibel sind oder die Ränge ungleich sind. Sie können dem Code Fehlerbehandlung hinzufügen, um sicherzustellen, dass die Arrays kompatibel sind, bevor Sie eine Zuweisung versuchen. Sie können auch das [TryCast-Operator](../../../language-reference/operators/trycast-operator.md) Schlüsselwort verwenden, wenn Sie keine Ausnahme auslösen möchten.

## <a name="see-also"></a>Weitere Informationen

- [Arrays](index.md)
- [Problembehandlung bei Arrays](troubleshooting-arrays.md)
- [Enum-Anweisung](../../../language-reference/statements/enum-statement.md)
- [Arraykonvertierungen](../data-types/array-conversions.md)
