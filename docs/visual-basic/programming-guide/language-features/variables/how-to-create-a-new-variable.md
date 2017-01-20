---
title: "How to: Create a New Variable (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Dim statement"
  - "variables [Visual Basic], creating"
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
caps.latest.revision: 29
caps.handback.revision: 29
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Create a New Variable (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Variablen werden mit einer [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) erstellt.  
  
### So erstellen Sie eine neue Variable  
  
1.  Deklarieren Sie die Variable mit einer `Dim`\-Anweisung.  
  
    ```  
  
    Dim newCustomer  
    ```  
  
2.  Nehmen Sie Angaben zur Definition der Merkmale der Variablen, wie [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) oder [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md), in die Anweisung auf.  Weitere Informationen finden Sie unter [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
     Sie müssen das `Dim`\-Schlüsselwort nicht angeben, wenn Sie andere Schlüsselwörter in der Deklaration verwenden.  
  
3.  Geben Sie nach den Spezifikationen den Namen der Variablen an. Dieser muss den für [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] geltenden Regeln und Konventionen entsprechen.  Weitere Informationen finden Sie unter [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
4.  Geben Sie nach dem Namen eine [As](../../../../visual-basic/language-reference/statements/as-clause.md)\-Klausel an, um den Datentyp der Variablen festzulegen.  
  
    ```  
    Public Static newCustomer As Customer   
    ```  
  
     Wenn Sie den Datentyp nicht angeben, wird standardmäßig der Typ `Object` verwendet.  
  
5.  Geben Sie nach der `As`\-Klausel ein Gleichheitszeichen \(`=`\) und nach dem Gleichheitszeichen den Anfangswert der Variablen an.  
  
     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] weist der Variablen den angegebenen Wert jedes Mal zu, wenn die `Dim`\-Anweisung ausgeführt wird.  Wenn kein Anfangswert angegeben wird, weist [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] der Variablen den Standardanfangswert ihres Datentyps zu, sobald mit der Ausführung des Codes begonnen wird, der die `Dim`\-Anweisung enthält.  
  
     Handelt es sich bei der Variablen um einen Referenztyp, kann durch die Angabe des [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md)\-Schlüsselworts in der `As`\-Klausel eine Instanz der betreffenden Klasse erstellt werden.  Wenn Sie `New` nicht verwenden, ist der Anfangswert der Variablen [Nothing](../../../../visual-basic/language-reference/nothing.md).  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## Siehe auch  
 [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Statements](../../../../visual-basic/language-reference/statements/index.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md)