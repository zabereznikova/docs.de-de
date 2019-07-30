---
title: 'Vorgehensweise: Neue Variable erstellen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: a6cb7225ea203f0b38b731795684bfb0cfdfd2d1
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630897"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a>Vorgehensweise: Neue Variable erstellen (Visual Basic)

Sie erstellen eine Variable mit einer [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md).

### <a name="to-create-a-new-variable"></a>So erstellen Sie eine neue Variable

1. Deklarieren Sie die Variable `Dim` in einer-Anweisung.

    ```vb
    Dim newCustomer
    ```

2. Fügen Sie Spezifikationen für die Merkmale der Variablen ein, z. b. [private](../../../../visual-basic/language-reference/modifiers/private.md), [statische](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)oder [wiwitvents](../../../../visual-basic/language-reference/modifiers/withevents.md). Weitere Informationen finden Sie unter [deklarierte Element Eigenschaften](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).

    ```vb
    Public Static newCustomer
    ```

    Das `Dim` Schlüsselwort ist nicht erforderlich, wenn Sie andere Schlüsselwörter in der Deklaration verwenden.

3. Befolgen Sie die Spezifikationen mit dem Variablennamen, der Visual Basic Regeln und Konventionen befolgt werden muss. Weitere Informationen finden Sie unter [deklarierte Element Namen](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).

    ```vb
    Public Static newCustomer
    ```

4. Befolgen Sie den Namen mit der [As](../../../../visual-basic/language-reference/statements/as-clause.md) -Klausel, um den Datentyp der Variablen anzugeben.

    ```vb
    Public Static newCustomer As Customer
    ```

    Wenn Sie den-Datentyp nicht angeben, wird der Standardwert verwendet `Object`:.

5. Befolgen Sie `As` die-Klausel mit einem Gleichheitszeichen (`=`), und befolgen Sie das Gleichheitszeichen mit dem Anfangswert der Variablen.

    Visual Basic weist der Variablen bei jedem Ausführen der `Dim` Anweisung den angegebenen Wert zu. Wenn Sie keinen Anfangswert angeben, weist Visual Basic den Standard Anfangswert für den Datentyp der Variablen zu, wenn er zum ersten Mal in den Code wechselt `Dim` , der die Anweisung enthält.

    Wenn die Variable ein Verweistyp ist, können Sie eine Instanz der zugehörigen Klasse erstellen, indem Sie das [neue Operator](../../../../visual-basic/language-reference/operators/new-operator.md) Schlüsselwort in die `As` -Klausel einschließen. Wenn Sie nicht verwenden `New`, ist der Anfangswert der Variablen " [Nothing](../../../../visual-basic/language-reference/nothing.md)".

    ```vb
    Public Static newCustomer As New Customer
    ```

## <a name="see-also"></a>Siehe auch

- [Variablen](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Namen deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Merkmale deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Anweisungen](../../../../visual-basic/language-reference/statements/index.md)
- [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
