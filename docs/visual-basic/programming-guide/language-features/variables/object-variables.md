---
title: "Object Variables in Visual Basic | Microsoft Docs"
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
  - "object variables, about object variables"
  - "variables [Visual Basic], object"
  - "objects [Visual Basic], accessing"
  - "object variables"
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Object Variables in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Variablen können nicht nur Werte, sondern auch Verweise auf ein Objekt enthalten.  Ein Objekt wird einer Variablen aus den gleichen Gründen zugewiesen wie ein Wert:  
  
-   In der Regel ist der Name einer Variablen kürzer und einprägsamer als der vollständige Pfad mit den Methoden und Eigenschaften, die zum Zugriff auf das Objekt selbst erforderlich sind.  
  
-   Eine auf ein Objekt verweisende Variable ist effizienter als der wiederholte Zugriff auf das Objekt selbst über die erforderlichen Methoden oder Eigenschaften.  
  
-   Sie können eine Variable ändern, damit sie auf andere Objekte verweist, während der Code ausgeführt wird.  
  
## Verkürzen des Codes  
 Mit Objektvariablen verringert sich die Codemenge, die Sie eingeben müssen.  Im folgenden Beispiel wird unter Angabe des vollständigen Pfads von Methoden und Eigenschaften auf ein <xref:System.Windows.Forms.Control>\-Objekt zugegriffen.  
  
```  
' Assume Me is a valid Form, or replace Me with a valid Form.  
Me.ActiveForm.ActiveControl.Text = "Test"  
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)  
Me.ActiveForm.ActiveControl.Show()  
```  
  
 Durch eine Objektvariable als Steuerelement wird dieser Code gekürzt und die Ausführung beschleunigt.  Sie sollten die Objektvariable mit der Klasse deklarieren, die Sie ihr zuweisen möchten \(hier `Control`\).  Sobald Sie der Variablen ein Objekt zugewiesen haben, kann sie genauso verwendet werden wie das Objekt, auf das sie verweist.  Sie können die Eigenschaften des Objekts festlegen oder abrufen und jede Methode des Objekts ausführen.  Im folgenden Beispiel wird eine Objektvariable verwendet, um den Code im vorangehenden Beispiel zu vereinfachen.  
  
```  
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl  
ctrlActv.Text = "Test"  
ctrlActv.Location = New Point(100, 100)  
ctrlActv.Show()  
```  
  
## Siehe auch  
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [How to: Speed Up Access to an Object with a Long Qualification Path](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)   
 [Object Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Object Variable Assignment](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [Object Variable Values](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)