---
title: 'Vorgehensweise: Erstellen einer neuen Variablen'
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: 501c8f3aff4c5b204d231bdc26213e13d125a7cf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410528"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a>Gewusst wie: Erstellen einer neuen Variablen (Visual Basic)

Sie erstellen eine Variable mit einer [Dim-Anweisung](../../../language-reference/statements/dim-statement.md).

### <a name="to-create-a-new-variable"></a>So erstellen Sie eine neue Variable

1. Deklarieren Sie die Variable in einer- `Dim` Anweisung.

    ```vb
    Dim newCustomer
    ```

2. Fügen Sie Spezifikationen für die Merkmale der Variablen ein, z. b. [private](../../../language-reference/modifiers/private.md), [statische](../../../language-reference/modifiers/static.md), [Shadows](../../../language-reference/modifiers/shadows.md)oder [wiwitvents](../../../language-reference/modifiers/withevents.md). Weitere Informationen finden Sie unter [deklarierte Element Eigenschaften](../declared-elements/declared-element-characteristics.md).

    ```vb
    Public Static newCustomer
    ```

    Das `Dim` Schlüsselwort ist nicht erforderlich, wenn Sie andere Schlüsselwörter in der Deklaration verwenden.

3. Befolgen Sie die Spezifikationen mit dem Variablennamen, der Visual Basic Regeln und Konventionen befolgt werden muss. Weitere Informationen finden Sie unter [deklarierte Element Namen](../declared-elements/declared-element-names.md).

    ```vb
    Public Static newCustomer
    ```

4. Befolgen Sie den Namen mit der [As](../../../language-reference/statements/as-clause.md) -Klausel, um den Datentyp der Variablen anzugeben.

    ```vb
    Public Static newCustomer As Customer
    ```

    Wenn Sie den-Datentyp nicht angeben, wird der Standardwert verwendet: `Object` .

5. Befolgen Sie die `As` -Klausel mit einem Gleichheitszeichen ( `=` ), und befolgen Sie das Gleichheitszeichen mit dem Anfangswert der Variablen.

    Visual Basic weist der Variablen bei jedem Ausführen der Anweisung den angegebenen Wert zu `Dim` . Wenn Sie keinen Anfangswert angeben, weist Visual Basic den Standard Anfangswert für den Datentyp der Variablen zu, wenn er zum ersten Mal in den Code wechselt, der die `Dim` Anweisung enthält.

    Wenn die Variable ein Verweistyp ist, können Sie eine Instanz der zugehörigen Klasse erstellen, indem Sie das [neue Operator](../../../language-reference/operators/new-operator.md) Schlüsselwort in die- `As` Klausel einschließen. Wenn Sie nicht verwenden `New` , ist der Anfangswert der Variablen " [Nothing](../../../language-reference/nothing.md)".

    ```vb
    Public Static newCustomer As New Customer
    ```

## <a name="see-also"></a>Weitere Informationen

- [Variablen](index.md)
- [Variablen Deklaration](variable-declaration.md)
- [Declared Element Names](../declared-elements/declared-element-names.md)
- [Merkmale deklarierter Elemente](../declared-elements/declared-element-characteristics.md)
- [Wert- und Verweistypen](../data-types/value-types-and-reference-types.md)
- [Anweisungen](../../../language-reference/statements/index.md)
- [Lokaler Typrückschluss](local-type-inference.md)
- [Option Infer-Anweisung](../../../language-reference/statements/option-infer-statement.md)
