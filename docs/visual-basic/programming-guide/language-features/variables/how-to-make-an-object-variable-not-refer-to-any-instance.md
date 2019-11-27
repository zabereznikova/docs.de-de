---
title: 'Gewusst wie: Entfernen aller Verweise einer Objektvariablen auf Instanzen'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 320dadb61c12f3339c5328dcef31c41503892c56
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352896"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a>Gewusst wie: Entfernen aller Verweise einer Objektvariablen auf Instanzen (Visual Basic)
Sie können eine Objekt Variable von einer beliebigen Objektinstanz trennen, indem Sie Sie auf " [Nothing](../../../../visual-basic/language-reference/nothing.md)" festlegen.  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a>So trennen Sie eine Objekt Variable zu einer Objektinstanz  
  
- Legen Sie die Variable auf `Nothing` in einer Zuweisungsanweisung fest.  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Wenn Ihr Code versucht, auf einen Member einer Objektvariablen zuzugreifen, die auf `Nothing`festgelegt wurde, tritt ein <xref:System.NullReferenceException> auf. Wenn Sie festgelegt haben, dass eine Objekt Variable häufig `Nothing` wird, oder wenn es möglich ist, dass die Variable nicht initialisiert ist, empfiehlt es sich, die Member-Zugriffe in einem `Try...Catch...Finally` Block zu schließen.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Wenn Sie eine Objekt Variable für Objekte verwenden, die vertrauliche oder sensible Daten enthalten, können Sie die Variable auf `Nothing` festlegen, wenn Sie nicht aktiv mit einem dieser Objekte arbeiten. Dadurch wird die Wahrscheinlichkeit verringert, dass bösartiger Code Zugriff auf die Daten erhält.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.NullReferenceException>
- [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Zuweisen von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Nothing](../../../../visual-basic/language-reference/nothing.md)
- [Try...Catch...Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
