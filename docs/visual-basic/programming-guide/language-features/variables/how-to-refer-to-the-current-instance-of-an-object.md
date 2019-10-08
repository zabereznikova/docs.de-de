---
title: 'Vorgehensweise: Verweisen auf die aktuelle Instanz eines Objekts (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 6c216dbc59bcad7a9f24bb01f856c3d29c288dbb
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005658"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a>Vorgehensweise: Verweisen auf die aktuelle Instanz eines Objekts (Visual Basic)
Die *aktuelle Instanz* eines-Objekts ist die Instanz, in der der Code gerade ausgeführt wird.  
  
 Verwenden Sie das Schlüsselwort "`Me`", um auf die aktuelle-Instanz zu verweisen.  
  
### <a name="to-refer-to-the-current-instance"></a>So verweisen Sie auf die aktuelle Instanz  
  
- Verwenden Sie das Schlüsselwort "`Me`", bei dem Sie normalerweise den Namen einer Objektvariablen verwenden.  
  
    ```vb  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     Obwohl sich `Me` wie eine Objekt Variable verhält, können Sie Sie nicht deklarieren oder ihr etwas zuweisen. `Me` verweist immer auf die aktuelle Instanz.  
  
## <a name="see-also"></a>Siehe auch

- [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Zuweisen von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
