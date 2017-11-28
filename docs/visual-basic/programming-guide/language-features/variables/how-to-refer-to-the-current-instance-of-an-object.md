---
title: 'Gewusst wie: Verweisen auf die aktuelle Instanz eines Objekts (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 33ea612253b00e12f47258189da4ac7d8d98ade5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a>Gewusst wie: Verweisen auf die aktuelle Instanz eines Objekts (Visual Basic)
Die *aktuelle Instanz* eines Objekts ist die Instanz, in der der Code derzeit ausgeführt wird.  
  
 Sie verwenden die `Me` Schlüsselwort zum Verweisen auf die aktuelle Instanz.  
  
### <a name="to-refer-to-the-current-instance"></a>Zum Verweisen auf die aktuelle Instanz  
  
-   Verwenden Sie die `Me` Schlüsselwort, in denen Sie normalerweise den Namen einer Objektvariablen verwenden würden.  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     Obwohl `Me` verhält sich wie ein Objekt Variablen, Sie können nicht deklariert oder nichts zuweisen. `Me`bezieht sich immer auf die aktuelle Instanz.  
  
## <a name="see-also"></a>Siehe auch  
 [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Zuweisen von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
