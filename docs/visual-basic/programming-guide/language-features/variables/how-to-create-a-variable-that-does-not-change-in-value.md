---
title: 'Vorgehensweise: Erstellen Sie eine Variable, die nicht geändert wird, im Wert (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: 7180e5141572d219ed02c57103e9d4b80cde536e
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59342933"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a>Vorgehensweise: Erstellen Sie eine Variable, die nicht geändert wird, im Wert (Visual Basic)
Das Konzept einer Variablen, die nicht den Wert geändert wird möglicherweise angezeigt, widersprüchliche sein. Aber es gibt Situationen, wenn eine Konstante nicht möglich ist, und es ist sinnvoll, eine Variable mit einem festen Wert aufweisen. In diesem Fall können Sie eine Membervariable mit definieren die [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) Schlüsselwort.  
  
 Sie können keine der [Const-Anweisung](../../../../visual-basic/language-reference/statements/const-statement.md) zu deklarieren und Zuweisen eines konstanten Werts in den folgenden Situationen:  
  
-   Die `Const` Anweisung akzeptiert nicht den Datentyp, die Sie verwenden möchten  
  
-   Sie ist der Wert zum Zeitpunkt der Kompilierung nicht bekannt.  
  
-   Sie werden kann nicht den konstanten Wert zur Kompilierungszeit berechnet  
  
### <a name="to-create-a-variable-that-does-not-change-in-value"></a>Erstellen Sie eine Variable, die nicht geändert wird, Wert  
  
1. Auf Modulebene, deklarieren Sie eine Membervariable mit dem [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md), und fügen die [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) Schlüsselwort.  
  
    ```  
    Dim ReadOnly timeStarted  
    ```  
  
     Sie können angeben, `ReadOnly` nur in einer Membervariablen gespeichert. Dies bedeutet, dass Sie die Variable auf Modulebene außerhalb einer Prozedur definieren müssen.  
  
2. Wenn Sie den Wert in einer einzelnen Anweisung zum Zeitpunkt der Kompilierung berechnen können, verwenden Sie eine Initialisierungsklausel in der `Dim` Anweisung. Führen Sie die [als](../../../../visual-basic/language-reference/statements/as-clause.md) -Klausel mit einem Gleichheitszeichen (`=`), gefolgt von einem Ausdruck. Achten Sie darauf, dass der Compiler diesen Ausdruck mit einem konstanten Wert auswerten kann.  
  
    ```  
    Dim ReadOnly timeStarted As Date = Now  
    ```  
  
     Sie können einen Wert zuweisen einer `ReadOnly` Variable nur einmal. Sobald Sie dies tun, kann keinen Code immer den Wert ändern.  
  
     Wenn Sie den Wert zur Kompilierzeit nicht kennen, oder können nicht zum Zeitpunkt der Kompilierung in einer einzelnen Anweisung berechnen, können Sie es noch zur Laufzeit in einem Konstruktor zuweisen. Zu diesem Zweck müssen Sie deklarieren die `ReadOnly` Variable, Klasse oder Struktur auf. Klicken Sie im Konstruktor für diese Klasse oder Struktur berechnen Sie festen Wert für den Wert der Variablen zu, und weisen sie der Variablen vor der Rückgabe aus dem Konstruktor.  
  
## <a name="see-also"></a>Siehe auch

- [WriteOnly](../../../../visual-basic/language-reference/modifiers/writeonly.md)
- [Const-Anweisung](../../../../visual-basic/language-reference/statements/const-statement.md)
