---
title: 'Gewusst wie: Entfernen aller Verweise einer Objektvariablen auf Instanzen (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3b33aef06300bf35b7138ec5b40747532a77140a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a>Gewusst wie: Entfernen aller Verweise einer Objektvariablen auf Instanzen (Visual Basic)
Sie können die Zuordnung einer Objektvariablen in jeder Objektinstanz aufheben, durch Festlegen auf [nichts](../../../../visual-basic/language-reference/nothing.md).  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a>Trennen Sie die Objektvariable in jeder Objektinstanz  
  
-   Legen Sie die Variable auf `Nothing` in einer zuweisungsanweisung.  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Wenn Ihr Code versucht, einen Member einer Objektvariablen zuzugreifen, die festgelegt wurde, dass `Nothing`ein <xref:System.NullReferenceException> auftritt. Wenn Sie eine Objektvariable auf `Nothing` häufig, oder wenn es möglich, die Variable wird nicht initialisiert ist, ist es eine gute Idee, schließen Sie die Memberzugriffe in einem `Try...Catch...Finally` Block.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Wenn Sie eine Objektvariable für Objekte, die vertrauliche oder sensible Daten enthalten verwenden, können Sie die Variable festlegen, um `Nothing` Wenn Sie nicht aktiv zuständig sind mit einem dieser Objekte. Dies reduziert die Wahrscheinlichkeit von bösartigem Code, die den Zugriff auf die Daten.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.NullReferenceException>  
 [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Zuweisen von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [Nothing](../../../../visual-basic/language-reference/nothing.md)  
 [Try...Catch...Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Problembehandlung bei Ausnahmen: System.NullReferenceException](http://msdn.microsoft.com/library/4822b0b4-8105-43fb-887a-3cc51ff02899)
