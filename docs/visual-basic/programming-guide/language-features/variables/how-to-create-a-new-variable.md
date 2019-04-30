---
title: 'Vorgehensweise: Erstellen einer neuen Variablen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: ee1e93b4e9819992f17738eb024004a4d66210d1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938241"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a>Vorgehensweise: Erstellen einer neuen Variablen (Visual Basic)
Erstellen Sie eine Variable mit einem [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md).  
  
### <a name="to-create-a-new-variable"></a>So erstellen Sie eine neue Variable  
  
1. Deklarieren Sie die Variable in einem `Dim` Anweisung.  
  
    ```  
    Dim newCustomer  
    ```  
  
2. Nehmen Sie die Angaben zur der Merkmale der Variablen, wie z. B. [Private](../../../../visual-basic/language-reference/modifiers/private.md), [statische](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), oder [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md). Weitere Informationen finden Sie unter [Merkmale der deklarierten Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
     Sie müssen nicht die `Dim` Schlüsselwort, wenn Sie andere Schlüsselwörter in der Deklaration verwenden.  
  
3. Führen Sie die Spezifikationen mit den Namen der Variablen, die Visual Basic-Regeln und Konventionen folgen müssen. Weitere Informationen finden Sie unter [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
4. Führen Sie den Namen der [als](../../../../visual-basic/language-reference/statements/as-clause.md) -Klausel, um die Variable den Datentyp anzugeben.  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     Wenn Sie den Datentyp nicht angeben, verwendet dieser den Standardwert: `Object`.  
  
5. Führen Sie die `As` -Klausel mit einem Gleichheitszeichen (`=`), und befolgen Sie das Gleichheitszeichen mit dem Anfangswert der Variablen.  
  
     Visual Basic weist den angegebenen Wert der Variable, jeder Ausführung der `Dim` Anweisung. Wenn Sie keinen Anfangswert angeben, weist Visual Basic der anfängliche Standardwert für die Variable den Datentyp an, wenn es zuerst den Code eingibt, der enthält die `Dim` Anweisung.  
  
     Wenn die Variable ein Verweistyp ist, können Sie eine Instanz der Klasse erstellen, mit der [neuer Operator](../../../../visual-basic/language-reference/operators/new-operator.md) -Schlüsselwort in der `As` Klausel. Wenn Sie nicht verwenden `New`, ist der Anfangswert der Variablen [nichts](../../../../visual-basic/language-reference/nothing.md).  
  
    ```  
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
