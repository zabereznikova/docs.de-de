---
title: 'Gewusst wie: Verschieben von Daten in und aus einer Variablen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: bfda451cefff699561253910715d8450414b00ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a>Gewusst wie: Verschieben von Daten in und aus einer Variablen (Visual Basic)
Sie können einen Wert in einer Variablen speichern, indem Sie den Variablennamen auf der linken Seite einer zuweisungsanweisung.  
  
## <a name="putting-data-in-a-variable"></a>Einfügen von Daten in einer Variablen  
  
#### <a name="to-store-a-value-in-a-variable"></a>Zum Speichern eines Werts in einer Variablen  
  
-   Verwenden Sie den Variablennamen an, auf der linken Seite einer zuweisungsanweisung.  
  
     Im folgenden Beispiel wird den Wert der Variablen `alpha`.  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     Der Wert, der auf der rechten Seite der Zuweisung generiert wird in der Variablen gespeichert.  
  
## <a name="getting-data-from-a-variable"></a>Abrufen von Daten aus einer Variablen  
 Rufen Sie die Werte einer Variable den Variablennamen in einen Ausdruck einschließen.  
  
#### <a name="to-retrieve-a-value-from-a-variable"></a>Zum Abrufen eines Werts aus einer Variablen  
  
-   Verwenden Sie den Variablennamen in einem Ausdruck. Sie können eine Variable an einer beliebigen Stelle können Sie eine Konstante oder ein Literal außer in einem Ausdruck, der den Wert einer Konstante definiert.  
  
     - oder -   
  
-   Verwenden Sie den Variablennamen, die nach dem Gleichheitszeichen (`=`) in einer zuweisungsanweisung signieren.  
  
     Das folgende Beispiel liest den Wert der Variablen `startValue` und verwendet dann den Wert der Variablen `counter` in einem Ausdruck.  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     Der Wert der Variablen teilnimmt im Ausdruck, ebenso wie eine Konstante ist, und klicken Sie dann in der Variablen oder Eigenschaft auf der linken Seite der Zuweisung gespeichert.  
  
## <a name="see-also"></a>Siehe auch  
 [Variablen](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
