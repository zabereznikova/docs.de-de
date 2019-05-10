---
title: 'Vorgehensweise: Verschieben von Daten in und aus einer Variablen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: 033d1cb0116b78ca9e3677c920ee5745117573d2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663520"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a>Vorgehensweise: Verschieben von Daten in und aus einer Variablen (Visual Basic)
Sie können einen Wert in einer Variablen speichern, indem Sie den Namen den Variablen auf der linken Seite einer zuweisungsanweisung einfügen.  
  
## <a name="putting-data-in-a-variable"></a>Einfügen von Daten in einer Variablen  
  
#### <a name="to-store-a-value-in-a-variable"></a>Einen Wert in einer Variablen gespeichert.  
  
- Verwenden Sie den Namen den Variablen auf der linken Seite einer zuweisungsanweisung.  
  
     Im folgenden Beispiel wird den Wert der Variablen `alpha`.  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     Der Wert, der auf der rechten Seite der Zuweisung generiert wird in der Variablen gespeichert.  
  
## <a name="getting-data-from-a-variable"></a>Abrufen von Daten aus einer Variablen  
 Sie rufen den Wert einer Variable, indem Sie den Namen den Variablen in einen Ausdruck einschließen.  
  
#### <a name="to-retrieve-a-value-from-a-variable"></a>Zum Abrufen eines Werts aus einer Variablen  
  
- Verwenden Sie den Namen den Variablen in einem Ausdruck. Sie können eine Variable an einer beliebigen Stelle können Sie eine Konstante oder ein Literal ist, außer in einem Ausdruck, der den Wert einer Konstante definiert.  
  
     - oder -   
  
- Verwenden Sie den Namen den Variablen nach dem Gleichheitszeichen (`=`) in einer zuweisungsanweisung anmelden.  
  
     Das folgende Beispiel liest den Wert der Variablen `startValue` und verwendet dann den Wert der Variablen `counter` in einem Ausdruck.  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     Der Wert der Variablen ist Teil des Ausdrucks wie würden eine Konstante, und wird dann in der Variablen oder Eigenschaft auf der linken Seite der Zuweisung gespeichert.  
  
## <a name="see-also"></a>Siehe auch

- [Variablen](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
