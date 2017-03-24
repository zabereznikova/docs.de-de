---
title: 'Gewusst wie: Erstellen einer neuen Variablen (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Dim statement
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
caps.latest.revision: 29
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2856fe19ddc48a14385aaae7b1c331fcb96c0554
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-new-variable-visual-basic"></a>Gewusst wie: Erstellen einer neuen Variablen (Visual Basic)
Erstellen Sie eine Variable mit einem [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md).  
  
### <a name="to-create-a-new-variable"></a>So erstellen Sie eine neue Variable  
  
1.  Deklarieren Sie die Variable in eine `Dim` Anweisung.  
  
    ```  
  
    Dim newCustomer  
    ```  
  
2.  Nehmen Sie Angaben zur Merkmale der Variablen, wie z. B. [Private](../../../../visual-basic/language-reference/modifiers/private.md), [statische](../../../../visual-basic/language-reference/modifiers/static.md), [Schatten](../../../../visual-basic/language-reference/modifiers/shadows.md), oder [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md). Weitere Informationen finden Sie unter [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
     Sie müssen nicht die `Dim` -Schlüsselwort verwenden, wenn Sie andere Schlüsselwörter in der Deklaration verwenden.  
  
3.  Führen Sie die Namen der Variablen muss die Spezifikationen [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Regeln und Konventionen. Weitere Informationen finden Sie unter [Elementnamen deklariert](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
4.  Führen Sie den Namen der [als](../../../../visual-basic/language-reference/statements/as-clause.md) -Klausel, um den Datentyp der Variablen angeben.  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     Wenn Sie den Datentyp nicht angeben, wird standardmäßig verwendet: `Object`.  
  
5.  Führen Sie die `As` -Klausel mit einem Gleichheitszeichen (`=`) und nach dem Gleichheitszeichen Anfangswert der Variablen.  
  
     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]weist den angegebenen Wert der Variable, jeder Ausführung der `Dim` Anweisung. Wenn Sie keinen Anfangswert angeben [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] der anfängliche Standardwert für den Datentyp der Variablen zugewiesen, wenn sie zunächst den Code eingibt, der enthält die `Dim` Anweisung.  
  
     Wenn die Variable ein Verweistyp ist, können Sie eine Instanz der Klasse erstellen, mit der [Operator New](../../../../visual-basic/language-reference/operators/new-operator.md) -Schlüsselwort in der `As` Klausel. Wenn Sie keine verwenden `New`, ist der Anfangswert der Variablen [nichts](../../../../visual-basic/language-reference/nothing.md).  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Variablen](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Deklaration von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Namen deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Merkmale deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Anweisungen](../../../../visual-basic/language-reference/statements/index.md)   
 [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
