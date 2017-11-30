---
title: Objektvariablen in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 44689d649a381618e5d6c934deb2b7b9bea463ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
