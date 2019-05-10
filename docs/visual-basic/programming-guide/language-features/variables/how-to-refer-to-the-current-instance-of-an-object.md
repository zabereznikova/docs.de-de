---
title: 'Vorgehensweise: Verweisen Sie auf die aktuelle Instanz eines Objekts (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 70955cd55dfb91d4111e59ae58bfe409a4470433
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663532"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a>Vorgehensweise: Verweisen Sie auf die aktuelle Instanz eines Objekts (Visual Basic)
Die *kurveninstanz* eines Objekts ist die Instanz, die in der der Code derzeit ausgeführt wird.  
  
 Sie verwenden die `Me` -Schlüsselwort auf die aktuelle Instanz verweisen.  
  
### <a name="to-refer-to-the-current-instance"></a>Zum Verweisen auf die aktuelle Instanz  
  
- Verwenden Sie die `Me` Schlüsselwort, in denen Sie normalerweise den Namen einer Objektvariablen verwenden würden.  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     Obwohl `Me` verhält sich wie ein Objekt Variablen, Sie können nicht deklariert oder nichts zuweisen. `Me` bezieht sich immer auf die aktuelle Instanz.  
  
## <a name="see-also"></a>Siehe auch

- [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Zuweisen von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
