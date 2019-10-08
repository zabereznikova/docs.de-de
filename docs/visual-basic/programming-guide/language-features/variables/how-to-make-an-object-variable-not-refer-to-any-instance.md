---
title: 'Vorgehensweise: Festlegen, dass eine Objekt Variable nicht auf eine Instanz verweist (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: e647f2f891b06aa1767faac49b01df98ea31ec1c
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004914"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a>Vorgehensweise: Festlegen, dass eine Objekt Variable nicht auf eine Instanz verweist (Visual Basic)
Sie können eine Objekt Variable von einer beliebigen Objektinstanz trennen, indem Sie Sie auf " [Nothing](../../../../visual-basic/language-reference/nothing.md)" festlegen.  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a>So trennen Sie eine Objekt Variable zu einer Objektinstanz  
  
- Legen Sie die Variable in einer Zuweisungsanweisung auf `Nothing` fest.  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Wenn Ihr Code versucht, auf einen Member einer Objektvariablen zuzugreifen, die auf `Nothing` festgelegt wurde, tritt ein <xref:System.NullReferenceException> auf. Wenn Sie eine Objekt Variable häufig auf `Nothing` festlegen, oder wenn es möglich ist, dass die Variable nicht initialisiert ist, empfiehlt es sich, die Member-Zugriffe in einem `Try...Catch...Finally`-Block zu schließen.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Wenn Sie eine Objekt Variable für Objekte verwenden, die vertrauliche oder sensible Daten enthalten, können Sie die Variable auf `Nothing` festlegen, wenn Sie nicht aktiv mit einem dieser Objekte arbeiten. Dadurch wird die Wahrscheinlichkeit verringert, dass bösartiger Code Zugriff auf die Daten erhält.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.NullReferenceException>
- [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Zuweisen von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Nothing](../../../../visual-basic/language-reference/nothing.md)
- [Try...Catch...Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
