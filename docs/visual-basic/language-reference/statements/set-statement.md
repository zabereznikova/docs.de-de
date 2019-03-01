---
title: Set-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Set
helpviewer_keywords:
- property procedures [Visual Basic], Set statements
- Set statement [Visual Basic]
- Set statement [Visual Basic], syntax
- write-only properties
- properties [Visual Basic], write-only
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
ms.openlocfilehash: c6bb924a3c41e1c586f66c9473a94d1971ee262f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973768"
---
# <a name="set-statement-visual-basic"></a>Set-Anweisung (Visual Basic)
Deklariert eine `Set` Eigenschaftenprozedur, mit einer Eigenschaft einen Wert zuweisen.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a>Teile  
 `attributelist`  
 Dies ist optional. Finden Sie unter [Liste](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 Optional Klicken Sie auf höchstens die `Get` und `Set` Anweisungen in dieser Eigenschaft. Einer der folgenden Werte ist möglich:  
  
-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
-   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
-   `Protected Friend`  
  
 Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `value`  
 Erforderlich. Parameter, der den neuen Wert für die Eigenschaft enthält.  
  
 `datatype`  
 Erforderlich, wenn `Option Strict` ist `On`. Typ der `value` Parameter. Der angegebene Datentyp muss den Datentyp der Eigenschaft identisch sein, in denen dies `Set` -Anweisung deklariert wird.  
  
 `statements`  
 Dies ist optional. Eine oder mehrere Anweisungen, die beim Ausführen der `Set` -Eigenschaftenprozedur aufgerufen.  
  
 `End Set`  
 Erforderlich. Beendet die Definition der `Set` Eigenschaftenprozedur.  
  
## <a name="remarks"></a>Hinweise  
 Jede Eigenschaft müssen einen `Set` Eigenschaftenprozedur, wenn die Eigenschaft markiert ist `ReadOnly`. Die `Set` Verfahren dient zum Festlegen des Werts der Eigenschaft.  
  
 Visual Basic automatisch ruft einer Eigenschaft des `Set` Prozedur, wenn eine zuweisungsanweisung einen Wert in der Eigenschaft gespeichert werden bereitstellt.  
  
 Visual Basic übergibt einen Parameter für die `Set` Prozedur während der eigenschaftenzuweisungen. Wenn Sie keine Parameter für angeben `Set`, die integrierte Entwicklungsumgebung (IDE) verwendet einen impliziten Parameter mit dem Namen `value`. Der Parameter enthält den Wert der Eigenschaft zugewiesen werden soll. In der Regel diesen Wert in einer privaten lokalen Variable speichern und zurückgeben immer die `Get` Prozedur aufgerufen wird.  
  
 Der Hauptteil der Deklaration der Eigenschaft darf nur der Eigenschaft des `Get` und `Set` Prozeduren zwischen der [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) und `End Property` Anweisung. Es kann nicht als diese Prozeduren gespeichert werden. Insbesondere kann nicht der aktuelle Eigenschaftswert speichern. Sie müssen diesen Wert außerhalb der Eigenschaft speichern, da Wenn Sie es in einer der Eigenschaftenprozeduren speichern, die andere Eigenschaftenprozedur nicht darauf zugreifen kann. Der übliche Ansatz ist zum Speichern des Werts in einem [Private](../../../visual-basic/language-reference/modifiers/private.md) Variable, die auf derselben Ebene wie die Eigenschaft deklariert. Definieren Sie eine `Set` -Prozedur in der Eigenschaft, die auf die es angewendet.  
  
 Die `Set` Prozedur standardmäßig auf die Zugriffsebene der enthaltenden Eigenschaft auf, es sei denn, Sie verwenden `accessmodifier` in die `Set` Anweisung.  
  
## <a name="rules"></a>Regeln  
  
-   **Gemischte Zugriffsebenen.** Wenn Sie eine Eigenschaft mit Lese-/ Schreibzugriff definieren, können Sie optional eine andere Zugriffsebene angeben, entweder die `Get` oder `Set` Prozedur, aber nicht beides. Wenn Sie dies tun, muss die Zugriffsebene der Prozedur restriktiver ist als die Zugriffsebene der Eigenschaft. Z. B., wenn die Eigenschaft deklariert ist `Friend`, Sie können deklarieren, die `Set` Prozedur `Private`, aber nicht `Public`.  
  
     Wenn Sie definieren eine `WriteOnly` -Eigenschaft, die `Set` Prozedur darstellt, die gesamte Eigenschaft. Sie können nicht deklarieren eine andere Zugriffsebene für `Set`, da hierdurch zwei Zugriffsebenen für die Eigenschaft festgelegt werden.  
  
## <a name="behavior"></a>Verhalten  
  
-   **Zurückgeben einer Eigenschaftenprozedur.** Wenn die `Set` Prozedur werden an den aufrufenden Code zurückgibt, die Ausführung wird fortgeführt, nach der Anweisung, die den zu speichernde Wert bereitgestellt.  
  
     `Set` Property-Prozeduren können entweder Zurückgeben der [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md) oder [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md).  
  
     Die `Exit Property` und `Return` Anweisungen bewirken, dass eine sofortige Beendigung einer Eigenschaftenprozedur. Eine beliebige Anzahl von `Exit Property` und `Return` Anweisungen können an beliebiger Stelle in der Prozedur, und Sie können kombinieren `Exit Property` und `Return` Anweisungen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Set` Anweisung, um den Wert einer Eigenschaft festzulegen.  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a>Siehe auch
- [Get-Anweisung](../../../visual-basic/language-reference/statements/get-statement.md)
- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)
- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Eigenschaftenprozeduren](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
