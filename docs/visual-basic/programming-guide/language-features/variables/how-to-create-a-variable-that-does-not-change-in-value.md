---
title: "Gewusst wie: Erstellen einer Variablen mit unveränderlichem Wert (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d1475553e64fef92ec3f3bb7e1b4fbfb357dbec8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a>Gewusst wie: Erstellen einer Variablen mit unveränderlichem Wert (Visual Basic)
Das Konzept einer Variablen, die nicht mit seinen Wert ändert möglicherweise widersprüchlich werden angezeigt. Aber es gibt Situationen, wenn eine Konstante nicht möglich ist, und es ist sinnvoll, eine Variable mit einem festen Wert aufweisen. In diesem Fall definieren Sie eine Membervariable mit dem [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) Schlüsselwort.  
  
 Sie können keine der [Const-Anweisung](../../../../visual-basic/language-reference/statements/const-statement.md) zu deklarieren und Zuweisen eines konstanten Werts in den folgenden Situationen:  
  
-   Die `Const` Anweisung nimmt nicht an den Datentyp, die Sie verwenden möchten  
  
-   Sie den Wert zum Zeitpunkt der Kompilierung nicht bekannt.  
  
-   Sie sind nicht zum Zeitpunkt der Kompilierung den konstanten Wert zu berechnen  
  
### <a name="to-create-a-variable-that-does-not-change-in-value"></a>So erstellen eine Variable, die nicht geändert wird, Wert  
  
1.  Auf Modulebene, deklarieren Sie eine Membervariable mit dem [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md), und enthalten die [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) Schlüsselwort.  
  
    ```  
    Dim ReadOnly timeStarted  
    ```  
  
     Sie können angeben, `ReadOnly` nur in einer Membervariablen gespeichert. Dies bedeutet, dass Sie die Variable auf Modulebene außerhalb einer Prozedur definieren müssen.  
  
2.  Wenn Sie den Wert in einer einzelnen Anweisung zum Zeitpunkt der Kompilierung berechnen können, verwenden Sie eine Initialisierungsklausel in der `Dim` Anweisung. Führen Sie die [als](../../../../visual-basic/language-reference/statements/as-clause.md) -Klausel mit einem Gleichheitszeichen (`=`), gefolgt von einem Ausdruck. Achten Sie darauf, dass der Compiler diesen Ausdruck mit einem konstanten Wert ausgewertet werden kann.  
  
    ```  
    Dim ReadOnly timeStarted As Date = Now  
    ```  
  
     Sie können einen Wert zuweisen einer `ReadOnly` Variable nur einmal. Sobald dies geschehen ist, kann kein Code sein Wert jemals ändern.  
  
     Wenn Sie den Wert zum Zeitpunkt der Kompilierung nicht bekannt, oder können nicht zum Zeitpunkt der Kompilierung in einer einzelnen Anweisung berechnet, können Sie immer noch zur Laufzeit in einem Konstruktor zuweisen. Zu diesem Zweck müssen Sie deklarieren die `ReadOnly` Variable Ebene der Klasse oder Struktur. Berechnen Sie im Konstruktor für diese Klasse oder Struktur die Variable festen Wert zu, und weisen sie der Variablen vor der Rückgabe aus dem Konstruktor.  
  
## <a name="see-also"></a>Siehe auch  
 [WriteOnly](../../../../visual-basic/language-reference/modifiers/writeonly.md)  
 [Const-Anweisung](../../../../visual-basic/language-reference/statements/const-statement.md)
