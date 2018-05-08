---
title: Objektvariablen in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: 8383261c1806732c4c8abea9834000f003a848a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="object-variables-in-visual-basic"></a>Objektvariablen in Visual Basic
Zusätzlich zum Speichern von Werten direkt, kann eine Variable auf ein Objekt verweisen. Sie können eine Variable ein Objekt zuweisen, denselben Gründen, die Sie einen beliebigen Wert einer Variablen zuweisen:  
  
-   Ein Variablenname ist häufig kürzer und leichter merken als der vollständige Pfad der Methoden und Eigenschaften, die Zugriff auf das Objekt selbst erforderlich.  
  
-   Verwenden eine Variable, die auf ein Objekt verweist, ist effizienter als wiederholt den Zugriff auf das Objekt selbst, über die erforderlichen Methoden oder Eigenschaften.  
  
-   Sie können ändern, eine Variable, die auf andere Objekte verweisen, während Ihr Code ausgeführt wird.  
  
## <a name="making-code-shorter"></a>Verkürzen des Codes  
 Sie können Objektvariablen verwenden, um den Code zu kürzen, den Sie eingeben müssen. Im folgenden Beispiel wird den vollständigen Pfad der Methoden und Eigenschaften den Zugriff auf eine <xref:System.Windows.Forms.Control> Objekt.  
  
```  
' Assume Me is a valid Form, or replace Me with a valid Form.  
Me.ActiveForm.ActiveControl.Text = "Test"  
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)  
Me.ActiveForm.ActiveControl.Show()  
```  
  
 Sie können diesen Code kürzen, und Sie können Ausführung beschleunigt wird, wenn Sie eine Objektvariable für das Steuerelement verwendet. Sie sollten die Objektvariable mit der Klasse, die Sie zuweisen möchten deklarieren (`Control` in diesem Fall). Nachdem Sie die Variable ein Objekt zuweisen, können Sie sie genauso behandeln wie das Objekt zu behandeln, auf dem verwiesen. Festlegen oder Abrufen der Eigenschaften des Objekts, oder verwenden keine der Methoden. Im folgenden Beispiel wird eine Objektvariable, um den Code im vorhergehenden Beispiel zu vereinfachen.  
  
```  
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl  
ctrlActv.Text = "Test"  
ctrlActv.Location = New Point(100, 100)  
ctrlActv.Show()  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Gewusst wie: Beschleunigen des Zugriffs auf ein Objekt mit langem Qualifizierungspfad](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)  
 [Deklaration von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [Zuweisen von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [Werte von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
