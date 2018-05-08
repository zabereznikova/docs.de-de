---
title: 'Gewusst wie: Entfernen aller Verweise einer Objektvariablen auf Instanzen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: bf918b762261e1dd1fc4161a10203f3d0067e454
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
