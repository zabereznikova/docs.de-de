---
title: 'Gewusst wie: Beschleunigen des Zugriffs auf ein Objekt mit langem Qualifizierungspfad (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5d91eeaeb034a4c8b4fefcffdf2fdebe72127d66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a>Gewusst wie: Beschleunigen des Zugriffs auf ein Objekt mit langem Qualifizierungspfad (Visual Basic)
Wenn Sie häufig auf ein Objekt, die einen Qualifizierungspfad mehrere Methoden und Eigenschaften erforderlich sind zugreifen, können Sie den Code durch die Wiederholung nicht des Qualifizierungspfads beschleunigen.  
  
 Es gibt zwei Möglichkeiten, die Sie wiederholt den Qualifizierungspfad vermeiden können. Sie können das Objekt einer Variablen zuweisen oder können Sie ihn in ein `With`... `End With` Block.  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a>Einrichten des Zugriffs an ein stark qualifiziertes Objekt beschleunigen, indem Sie einer Variablen zuweisen  
  
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
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a>Zugriff auf ein Objekt Qualifizierungspfad beschleunigen mithilfe ein With... End With-block  
  
1.  Geben Sie den Qualifizierungspfad einer `With` Anweisung.  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2.  Zugriff auf Member des Objekts innerhalb der `With` -Block vor der `End With` Anweisung.  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [With...End With-Anweisung](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
