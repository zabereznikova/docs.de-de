---
title: 'Vorgehensweise: Beschleunigen des Zugriffs auf ein Objekt mit langem Qualifizierungspfad (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: b10876c22d2f6dd5832baa0d498db7c4205a3fcb
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816290"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a>Vorgehensweise: Beschleunigen des Zugriffs auf ein Objekt mit langem Qualifizierungspfad (Visual Basic)
Wenn Sie häufig ein Objekt, die einen Qualifizierungspfad, der mehrere Methoden und Eigenschaften erforderlich sind zugreifen, können Sie Ihren Code beschleunigen, indem nicht wiederholt den Qualifizierungspfad.  
  
 Es gibt zwei Möglichkeiten, die Sie vermeiden können, wiederholen den Qualifizierungspfad. Sie können das Objekt einer Variablen zuweisen oder können Sie sie in einem `With`... `End With` Block.  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a>Um den Zugriff auf ein stark qualifiziertes Objekt beschleunigen durch eine Variable zuweisen  
  
1.  Deklarieren Sie eine Variable des Typs des Objekts, das Sie häufig zugreifen. Geben Sie den Qualifizierungspfad im Initialisierungsteil der Deklaration.  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2.  Verwenden Sie die Variable, um die Member des Objekts zuzugreifen.  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a>Um den Zugriff auf ein stark qualifiziertes Objekt beschleunigen mithilfe einer With... End-With-block  
  
1.  Fügen Sie den Qualifizierungspfad in einem `With` Anweisung.  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2.  Zugriff auf die Member des Objekts in der `With` blockieren, bevor die `End With` Anweisung.  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [With...End With-Anweisung](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
