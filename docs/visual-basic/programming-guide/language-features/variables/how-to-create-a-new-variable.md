---
title: 'Gewusst wie: Erstellen einer neuen Variablen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: f2e6a97e78bc42ebea9519eb0aa4411e9aec24cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-new-variable-visual-basic"></a>Gewusst wie: Erstellen einer neuen Variablen (Visual Basic)
Erstellen Sie eine Variable mit einem [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md).  
  
### <a name="to-create-a-new-variable"></a>So erstellen Sie eine neue Variable  
  
1.  Deklarieren Sie die Variable in einem `Dim` Anweisung.  
  
    ```  
    Dim newCustomer  
    ```  
  
2.  Nehmen Sie Angaben zur Merkmale der Variablen, wie z. B. [Private](../../../../visual-basic/language-reference/modifiers/private.md), [statische](../../../../visual-basic/language-reference/modifiers/static.md), [Schatten](../../../../visual-basic/language-reference/modifiers/shadows.md), oder [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md). Weitere Informationen finden Sie unter [Elementmerkmale deklariert](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
     Sie müssen nicht die `Dim` Schlüsselwort, wenn Sie andere Schlüsselwörter in der Deklaration verwenden.  
  
3.  Führen Sie die Spezifikationen mit dem Variablennamen, die Visual Basic-Regeln und Konventionen folgen müssen. Weitere Informationen finden Sie unter [deklarierte Elementnamen](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
4.  Führen Sie den Namen der [als](../../../../visual-basic/language-reference/statements/as-clause.md) -Klausel zur Angabe der Datentyp der Variablen.  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     Wenn Sie den Datentyp nicht angeben, verwendet er den Standardwert: `Object`.  
  
5.  Führen Sie die `As` -Klausel mit einem Gleichheitszeichen (`=`), und führen Sie das Gleichheitszeichen Anfangswert der Variablen.  
  
     Visual Basic weist den angegebenen Wert der Variablen, jeder Ausführung der `Dim` Anweisung. Wenn Sie keinen Anfangswert angeben, weist Visual Basic der anfängliche Standardwert für den Datentyp der Variablen an, wenn er zuerst enthält den Code wird die `Dim` Anweisung.  
  
     Wenn die Variable ein Verweistyp ist, können Sie eine Instanz der Klasse erstellen, indem Sie z. B. die [New-Operator](../../../../visual-basic/language-reference/operators/new-operator.md) -Schlüsselwort in der `As` Klausel. Wenn Sie nicht verwenden `New`, ist der Anfangswert der Variablen [nichts](../../../../visual-basic/language-reference/nothing.md).  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Variablen](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Namen deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Merkmale deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Anweisungen](../../../../visual-basic/language-reference/statements/index.md)  
 [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
