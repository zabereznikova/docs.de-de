---
title: "How to: Assign One Array to Another Array (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "covariance, arrays"
  - "arrays [Visual Basic], assigning"
  - "arrays [Visual Basic], covariance"
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Assign One Array to Another Array (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Da Arrays Objekte sind, können Sie sie wie andere Objekttypen in Zuweisungsanweisungen verwenden.  Eine Arrayvariable enthält einen Zeiger auf die Daten, die die Arrayelemente sowie die Rang\- und Längeninformationen bilden. Eine Zuweisung kopiert nur diesen Zeiger.  
  
### So weisen Sie ein Array einem anderen Array zu  
  
1.  Stellen Sie sicher, dass die beiden Arrays den gleichen Rang \(Anzahl der Dimensionen\) und kompatible Elementdatentypen haben.  
  
2.  Weisen Sie mit einer Standardzuweisungsanweisung das Quellarray dem Zielarray zu.  Setzen Sie nach dem Arraynamen keine Klammern.  
  
    ```  
    Dim formArray() As System.Windows.Forms.Form  
    Dim controlArray() As System.Windows.Forms.Control  
    controlArray = formArray  
    ```  
  
 Wenn Sie ein Array einem anderen Array zuweisen, gelten folgende Regeln:  
  
-   **Gleicher Rang.** Der Rang \(Anzahl der Dimensionen\) des Zielarrays muss dem des Quellarrays entsprechen.  
  
     Wenn die Rangwerte der beiden Arrays übereinstimmen, müssen die Dimensionen nicht übereinstimmen.  Die Anzahl der Elemente in einer bestimmten Dimension kann sich während der Zuweisung ändern.  
  
-   **Elementtypen.** Beide Arrays müssen entweder über *Verweistyp*elemente oder über *Werttyp*elemente verfügen.  Weitere Informationen finden Sie unter [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
    -   Wenn beide Arrays über Werttypelemente verfügen, müssen die Elementdatentypen genau identisch sein.  Einzige Ausnahme: Sie können ein Array von `Enum`\-Elementen einem Array des Basistyps dieser `Enum`\-Elemente zuweisen.  
  
    -   Wenn beide Arrays über Verweistypelemente verfügen, muss der Quellelementtyp aus dem Zielelementtyp abgeleitet werden.  In diesem Fall haben die beiden Arrays die gleiche Vererbungsbeziehung wie ihre Elemente.  Dies wird als *Arraykovarianz* bezeichnet.  
  
 Wenn die oben genannten Regeln verletzt werden, meldet der Compiler einen Fehler. Dies ist z. B. der Fall, wenn die Datentypen nicht kompatibel oder die Rangwerte nicht identisch sind.  Sie können dem Code vor der Durchführung der Zuweisung Fehlerbehandlung hinzufügen, um sicherzustellen, dass die Arrays kompatibel sind.  Sie können auch das [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md)\-Schlüsselwort verwenden, wenn Sie das Auslösen einer Ausnahme vermeiden möchten.  
  
## Siehe auch  
 [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Troubleshooting Arrays](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)   
 [Enum Statement](../../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)