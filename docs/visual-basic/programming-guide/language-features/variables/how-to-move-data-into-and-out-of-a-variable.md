---
title: 'Gewusst wie: Verschieben von Daten in und aus einer Variablen (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fefb1979e35cd7b5fa1917f8f1a57af575e51234
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
