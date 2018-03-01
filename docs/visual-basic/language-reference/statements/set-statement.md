---
title: Set-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Set
helpviewer_keywords:
- property procedures [Visual Basic], Set statements
- Set statement [Visual Basic]
- Set statement [Visual Basic], syntax
- write-only properties
- properties [Visual Basic], write-only
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3b18e6c858e64e78d7ab85fdaafd70e510f7a02f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="set-statement-visual-basic"></a>Set-Anweisung (Visual Basic)
Deklariert eine `Set` Eigenschaftenprozedur, mit der eine Eigenschaft einen Wert zuweisen.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a>Teile  
 `attributelist`  
 Dies ist optional. Finden Sie unter [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 Optional für höchstens eine der `Get` und `Set` Anweisungen in dieser Eigenschaft. Einer der folgenden Werte ist möglich:  
  
-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
-   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
-   `Protected Friend`  
  
 Finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `value`  
 Erforderlich. Parameter, die den neuen Wert für die Eigenschaft enthält.  
  
 `datatype`  
 Erforderlich, wenn `Option Strict` ist `On`. Datentyp der `value` Parameter. Der angegebene Datentyp muss den Datentyp der Eigenschaft identisch sein, in denen dies `Set` -Anweisung deklariert wird.  
  
 `statements`  
 Dies ist optional. Eine oder mehrere Anweisungen, die beim Ausführen der `Set` -Eigenschaftenprozedur aufgerufen wird.  
  
 `End Set`  
 Erforderlich. Beendet die Definition des der `Set` -Eigenschaftenprozedur.  
  
## <a name="remarks"></a>Hinweise  
 Jede Eigenschaft benötigen eine `Set` Eigenschaftenprozedur, solange die Eigenschaft `ReadOnly`. Die `Set` Prozedur dient zum Festlegen des Werts der Eigenschaft.  
  
 Visual Basic automatisch ruft einer Eigenschaft `Set` Prozedur, wenn eine zuweisungsanweisung einen Wert in der Eigenschaft zu speichernde bereitstellt.  
  
 Visual Basic übergibt die Parameter für die `Set` Prozedur während der eigenschaftenzuweisungen. Wenn Sie keine Parameter für angeben `Set`, der integrierten Entwicklungsumgebung (IDE) verwendet einen impliziten Parameter mit dem Namen `value`. Der Parameter enthält den Wert der Eigenschaft zugewiesen werden soll. In der Regel speichern den Wert in einer privaten lokalen Variable und gibt es immer die `Get` Prozedur aufgerufen wird.  
  
 Der Hauptteil der Deklaration der Eigenschaft kann nur der Eigenschaft enthalten `Get` und `Set` Prozeduren zwischen den [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md) und die `End Property` Anweisung. Es kann keine etwas anderes als diese Prozeduren speichern. Es kann nicht insbesondere aktuellen Wert der Eigenschaft gespeichert. Dieser Wert außerhalb der Eigenschaft müssen gespeichert werden, da, wenn Sie es in eine der Eigenschaftenprozeduren speichern, die andere Eigenschaftenprozedur nicht darauf zugreifen kann. Die übliche Vorgehensweise wird zum Speichern des Werts in einer [Private](../../../visual-basic/language-reference/modifiers/private.md) Variable, die auf derselben Ebene wie die Eigenschaft deklariert. Definieren Sie eine `Set` -Prozedur in der Eigenschaft, für die er gilt.  
  
 Die `Set` Prozedur wird standardmäßig auf die Zugriffsebene der enthaltenden Eigenschaft, es sei denn, Sie verwenden `accessmodifier` in der `Set` Anweisung.  
  
## <a name="rules"></a>Regeln  
  
-   **Gemischte Zugriffsebenen.** Wenn Sie eine Eigenschaft mit Lese-/ Schreibzugriff definieren, können Sie optional eine andere Zugriffsebene angeben, entweder die `Get` oder `Set` Prozedur, aber nicht beides. Wenn in diesem Fall muss die Zugriffsebene der Prozedur restriktiver ist als die Zugriffsebene der Eigenschaft. Z. B., wenn die Eigenschaft deklariert wird `Friend`, Sie können deklarieren, die `Set` Prozedur `Private`, aber nicht `Public`.  
  
     Wenn Sie definieren eine `WriteOnly` -Eigenschaft, die `Set` Prozedur die gesamte Eigenschaft dar. Kann nicht deklariert eine unterschiedliche Zugriffsberechtigungen für `Set`, da hierdurch zwei Zugriffsebenen für die Eigenschaft festgelegt werden.  
  
## <a name="behavior"></a>Verhalten  
  
-   **Zurückgeben aus einer Eigenschaftenprozedur.** Wenn die `Set` Prozedur werden an den aufrufenden Code zurückgibt, die Ausführung wird fortgeführt, nach der Anweisung, die das zu speichernde Wert bereitgestellt.  
  
     `Set`-Eigenschaftenprozeduren können entweder Zurückgeben der [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md) oder [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md).  
  
     Die `Exit Property` und `Return` Anweisungen bewirken, dass eine sofortige Beendigung einer Eigenschaftenprozedur. Eine beliebige Anzahl von `Exit Property` und `Return` Anweisungen können an beliebiger Stelle in der Prozedur, und Sie können kombinieren `Exit Property` und `Return` Anweisungen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Set` Anweisung zum Festlegen des Werts einer Eigenschaft.  
  
 [!code-vb[VbVbalrStatements#55](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/set-statement_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Get-Anweisung](../../../visual-basic/language-reference/statements/get-statement.md)  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Eigenschaftenprozeduren](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
