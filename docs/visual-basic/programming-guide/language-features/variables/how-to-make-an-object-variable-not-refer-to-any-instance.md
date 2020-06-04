---
title: 'Vorgehensweise: Entfernen aller Verweise einer Objektvariablen auf Instanzen'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: cce2e59cb76652937868a731ad308872d1aba2f3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410450"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a>Gewusst wie: Entfernen aller Verweise einer Objektvariablen auf Instanzen (Visual Basic)
Sie können eine Objekt Variable von einer beliebigen Objektinstanz trennen, indem Sie Sie auf " [Nothing](../../../language-reference/nothing.md)" festlegen.  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a>So trennen Sie eine Objekt Variable zu einer Objektinstanz  
  
- Legen Sie die Variable `Nothing` in einer Zuweisungsanweisung auf fest.  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Wenn Ihr Code versucht, auf einen Member einer Objektvariablen zuzugreifen, die auf festgelegt wurde `Nothing` , <xref:System.NullReferenceException> tritt ein auf. Wenn Sie eine Objekt Variable häufig auf festlegen `Nothing` , oder wenn es möglich ist, die Variable nicht zu initialisieren, empfiehlt es sich, die Member-Zugriffe in einem- `Try...Catch...Finally` Block zu schließen.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Wenn Sie eine Objekt Variable für Objekte verwenden, die vertrauliche oder sensible Daten enthalten, können Sie die Variable auf festlegen, `Nothing` Wenn Sie nicht aktiv mit einem dieser Objekte arbeiten. Dadurch wird die Wahrscheinlichkeit verringert, dass bösartiger Code Zugriff auf die Daten erhält.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.NullReferenceException>
- [Objektvariablen](object-variables.md)
- [Zuweisung von Objektvariablen](object-variable-assignment.md)
- [Schweigen](../../../language-reference/nothing.md)
- [Try...Catch...Finally-Anweisung](../../../language-reference/statements/try-catch-finally-statement.md)
