---
title: 'Gewusst wie: Zuweisen eines Arrays zu einem anderen Array (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
ms.openlocfilehash: 63c7d187152fcb5ea84378c677aa687f334f63de
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647929"
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a>Gewusst wie: Zuweisen eines Arrays zu einem anderen Array (Visual Basic)
Da Arrays Objekte sind, können Sie sie in zuweisungsanweisungen wie andere Objekttypen. Eine Arrayvariable enthält einen Zeiger auf die Daten enthalten sind, die die Elemente des Arrays und die Informationen Rang und die Länge und eine Zuordnung kopiert nur this-Zeiger.  
  
### <a name="to-assign-one-array-to-another-array"></a>Zuweisen eines Arrays in ein anderes array  
  
1.  Stellen Sie sicher, dass die beiden Arrays den gleichen Rang (Anzahl der Dimensionen) und kompatible Datentypen haben.  
  
2.  Verwenden Sie eine standardmäßige zuweisungsanweisung Zielarray Quellarray zuweisen. Führen Sie nicht entweder Arrayname mit Klammern.  
  
    ```  
    Dim formArray() As System.Windows.Forms.Form  
    Dim controlArray() As System.Windows.Forms.Control  
    controlArray = formArray  
    ```  
  
 Wenn Sie ein Array in einen anderen zuweisen, gelten die folgenden Regeln:  
  
-   **Gleicher Rang.** Der Rang (Anzahl der Dimensionen) des Zielarrays muss das Quellarray identisch sein.  
  
     Bereitgestellten den Rang der zwei Arrays gleich sind, müssen die Dimensionen nicht identisch sein. Die Anzahl der Elemente in einer bestimmten Dimension kann bei der Zuordnung ändern.  
  
-   **Elementtypen.** Entweder beide Arrays müssen *Verweistyp* Elemente oder beide Arrays müssen *Werttyp* Elemente. Weitere Informationen finden Sie unter [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
    -   Wenn beide Arrays Wertelemente-Typ haben, müssen die Element-Datentypen dem genau übereinstimmen. Die einzige Ausnahme hierbei ist, dass Sie ein Array von zuweisen können `Enum` Elemente in ein Array des Basistyps dieses `Enum`.  
  
    -   Wenn beide Arrays Referenztyp Elemente verfügen, muss die Datenquellen-Elementtyp der Ziel-Elementtyp abgeleitet werden. Wenn dies der Fall ist, haben die beiden Arrays den gleichen vererbungsbeziehung als ihre Elemente. Hierbei spricht *Array-Kovarianz*.  
  
 Der Compiler meldet einen Fehler, wenn die oben genannten Regeln, z. B. verletzt werden die Datentypen nicht kompatibel sind oder die Ränge ungleich sind. Sie können die Fehlerbehandlung in den Code, um sicherzustellen, dass die Arrays kompatibel sind, bevor Sie versuchen, eine Zuordnung hinzufügen. Sie können auch die [TryCast-Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md) Schlüsselwort, wenn Sie, um zu vermeiden, dass eine Ausnahme ausgelöst möchten.  
  
## <a name="see-also"></a>Siehe auch  
 [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Problembehandlung bei Arrays](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)  
 [Enum-Anweisung](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Arraykonvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
