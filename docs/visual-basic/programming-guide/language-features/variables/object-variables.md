---
title: Objektvariablen in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: 046119664fc0277a6a5305d0cf086b4438b13f9d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685463"
---
# <a name="object-variables-in-visual-basic"></a>Objektvariablen in Visual Basic
Zusätzlich zum Speichern von Werten direkt aus, kann eine Variable auf ein Objekt verweisen. Sie können ein Objekt einer Variablen zuweisen, aus denselben Gründen, die Sie einen beliebigen Wert einer Variablen zuweisen:  
  
-   Ein Variablenname ist oftmals kürzer und leichter merken als den vollständigen Pfad der Methoden und Eigenschaften, die zum Zugriff auf das Objekt selbst.  
  
-   Verwenden eine Variable, die auf ein Objekt verweist, ist effizienter als die wiederholt den Zugriff auf das Objekt selbst, über die erforderlichen Methoden oder Eigenschaften.  
  
-   Sie können ändern, dass eine Variable, die auf andere Objekte verweisen, während Ihr Code ausgeführt wird.  
  
## <a name="making-code-shorter"></a>Verkürzen des Codes  
 Sie können Objektvariablen verwenden, um den Code zu verkürzen, den Sie eingeben müssen. Im folgenden Beispiel wird den vollständigen Pfad der Methoden und Eigenschaften den Zugriff auf eine <xref:System.Windows.Forms.Control> Objekt.  
  
```  
' Assume Me is a valid Form, or replace Me with a valid Form.  
Me.ActiveForm.ActiveControl.Text = "Test"  
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)  
Me.ActiveForm.ActiveControl.Show()  
```  
  
 Sie können diesen Code zu verkürzen und Ausführung beschleunigt wird, wenn Sie eine Objektvariablen für das Steuerelement verwenden. Sie sollten deklarieren und mit der Klasse, die Sie zuweisen möchten (`Control` in diesem Fall). Nachdem Sie ein Objekt der Variablen zugewiesen haben, können Sie es genauso behandeln wie behandeln Sie das Objekt auf den er verweist. Sie können festlegen oder Abrufen der Eigenschaften des Objekts oder keine ihrer Methoden verwenden. Im folgenden Beispiel wird eine Objektvariable, um den Code im vorherigen Beispiel zu vereinfachen.  
  
```  
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl  
ctrlActv.Text = "Test"  
ctrlActv.Location = New Point(100, 100)  
ctrlActv.Show()  
```  
  
## <a name="see-also"></a>Siehe auch
- [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Vorgehensweise: Beschleunigen des Zugriffs auf ein Objekt mit langem Qualifizierungspfad](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)
- [Deklaration von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Zuweisen von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Werte von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
